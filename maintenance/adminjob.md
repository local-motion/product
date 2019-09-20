# Administrator jobs

Technical administrators have the ability to run jobs in the system. These jobs can be used to (for example) retrieve statistics, 
export and import data and do migrations.

## Commands
A command is a routine that can be run as a job. These commands are built into the system and registered under a command identifier.
In the code the commands are typically found in the `io.localmotion.adminjob.commands` package.
A command may accept input parameters and will produce a result record and a status code. Additionally command may read and write files.
Commands have full privilege in the system and can invoke any service of the system.

## Jobs
A job is the single execution of a command. It consist of:
- the command to run
- the input parameters
- email address of the user that is allowed to trigger the job
- the result record: result status, result message and (optionally) additional output parameters
- an entry in the job history log

The job history log is a separate folder that contains a file per job with the execution datetime as its name. A record in the history log
contains the job command, input parameters, result record, job initiator and execution datetime.

The job's parameters are stored in a command file. The file includes the email address of the user that is allowed to trigger the job.
The system has an administration user interface on the `/admin` url. Here the user with the specified e-mail address can inspect the
job parameters and trigger the execution. Note that only one command can be ready for execution at a time.

## Files
The job-related files are in a folder or S3 bucket that is specified in the system's configuration. A `command` file contains the job's
parameters. The job produces a `result` file that has the same contents as a record in the history log and thus contains 
the job command, input parameters, result record, job initiator and execution datetime. A `history` folder contains the job
history files. All files are in the json format.

The command file has the following structure:
- commandIdentifier: name of the command to execute
- comment: job specific comment to capture why the job was run
- operatorEmail: email address of the LocalMotion user that is allowed to trigger the execution of the job
- inputParameters: json string containing the command-specific input parameters

This is an example command file to delete the personal data of a user:
```
{
    "commandIdentifier" : "DeletePersonalData",
    "comment" : "on the user's request",
    "operatorEmail" : "lmadmin@example.com",
    "inputParameters" : "{
        \"userId\" : \"44dd587c-5c70-4c89-bcf5-ac84e9488e8e\"
    }"
}
```

During the execution of the job the system creates a `inexecution` file to avoid concurrent job executions. If somehow a job should complete
without removing this file and therefore locks up the execution of jobs then remove this file by hand. (Note that the system will auto-recover after 
some time.)


## Command index

### Cognito import

#### Command identifier
GenerateCognitoInputFile

#### Purpose
Generate a file that can be used to import the current users of the system into a new instance of AWS Cognito.

#### Input parameters
None

#### Output parameters
- recordsWritten: number of records that were produced
- hashcode: hash code of the data that was written

#### Additional output
A file named `cognitoimport` is produced in the job folder. It conforms to this format: https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-using-import-tool-csv-header.html

Only the `cognito:username`, `email`, `email_verified` (always set to TRUE) and `cognito:mfa_enabled` (always set to FALSE) are populated.

---
### Delete Personal Data

#### Command identifier
DeletePersonalData

#### Purpose
Remove all person identifiable information (PII) of a particular user from the system. Currently this involves only the username and email attributes.

#### Pre-conditions
The user must be offboarded.

### Post-conditions
The user is still (in offboarded) state present in the system, because all user actions (and chat messages) are retained. However the PII data has been 
removed, which also has the effect that the user cannot be revived. (Onboarding with the same email address will result in a new user being created.)

#### Input parameters
- userId: technical id of the (offboarded) user for which the PII data has to be removed

#### Output parameters
- recordsRemoved: number of records that were removed from the PersonalDataRecord table

---
### Statistics report

#### Command identifier
Statistics

#### Purpose
Show a number of technical statistics (mainly record counts) of the system

#### Input parameters
None

#### Output parameters
- chatMessageCount: number of rows in the chat_message table
- eventCount: number of rows in Axon's DomainEventEntry table
- snapshotCount: number of rows in Axon's SnapshotEventEntry table
- userDataCount: number of rows in the UserDataRecord table
- personalDataRecordCount: number of rows in the personalDataRecord table
- profileCount: number of active user profiles
- deletedProfileCount: number of deleted (offboarded) user profiles
- initiativeCount: number of initiatives


---
### Chat migration

#### Command identifier
ChatMigration1.0.18-1.0.19

#### Purpose
Migrates the chat messages to a new database schema from release v.0.18-beta to release v1.0.19-beta. (Note that this command was actually
run prior to release v1.0.20-beta as release v1.0.19-beta turned out to be an infrastructure release with no change to the application or its DB schema.)

#### Input parameters
- migrationAction: 
  - DRYRUN: performs all validations and counts but does not actually migrate the messages
  - MIGRATE: performs validations and migrates the messages. DO NOT run this command twice as duplicate messages will appear. Note that the migration is not atomic. Some chat messages may fail while others succeed. Therefore run the dry run first.
  - DROPTABLE: deletes the original chat table from the schema. To be run after the migration.
  - DELETENEWTABLE: deletes the chat messages from the new table. (Can be used to retry a migration.)

#### Output parameters
- conversion: a list of messages, one for each record either listing the migrated record or containing a error message

