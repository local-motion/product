# Identity and access management
This section describes the enrollment and authentication of regular users.

## Authentication systems
User registration and authentication is done outside the LocalMotion system. Currently the users are registered in AWS Cognito, but in the 
future users from Facebook, Google, etc. could also be granted access to LocalMotion.

LocalMotion maintains its own administration of users and keeps track of the authentication system belonging to a user (that is the authentication
system that the user signed up with).


## User enrollment
The user first enrolls into the authentication system. After enrollment the user should log in into the authentication system and then access
LocalMotion. 
In LocalMotion the record of the external authentication system (for instance a JWT token) is bound to a (potential) LocalMotion user. Currently this is
done on the email address.

The following situations can be distinguished:
- the user exists and is active in the system. The user is logged in LocalMotion and any user attrbutes as such user name provided by the authentication system 
are updated in the LocalMotion system. (The user is prompted to approve this update, but will only be logged in to LocalMotion when he approves.)
- the user does not exist yet. The user is automatically onboarded. (At least for Cognito users as the Cognito signup is transparant and integrated into the
  LocalMotion frontend. When other ('external') authentication systems are used, the user should be asked to confirm that he wants to enroll.)
- the user exists, but was offboarded. The user can be revived by the frontend. The user is prompted to explicitly state that he intends to enroll and when
  applicable with changed user attributes such as the user name. Note that it is currently not possible to signup with the same email address (and the same authentication provider) as an offboarded user without reviving that users. (The only option to do such a thing would be to deleted the personal data of the offboarded user.)


Anyone can enroll into the system and become a regular user by completing the steps below.

### Step 1: Specify username, e-mail address and password
The user selects a username that will identify the user to other users in the system. (Note that the
e-mail address of the user will not be disclosed to other anonymous or regular users.) The username
must be unique among the active users in the system.


The email address must be unique amongst all users in the system (both active and offboarded). (Introduction of other authentication systems
next to AWS Cognito may soften this constraint.)


The password must meet these criteria:
 - minimum length is 8 characters
 - includes a numeric character, capital and non-capital letter and a special character
 - the special characters include: ^ $ * . [ ] { } ( ) ? - " ! @ # % & / \\ , > < ' : ; | _ ~ \

### Step 2: Verify e-mail address
The system will send an e-mail to the specified e-mail address containing a code and a url that the
user should enter / click to confirm his ownership of the e-mail account.
- Entering the code or clicking the verification link will confirm the user registration.
- The verification link is valid for 24 hours. After this period the user is prompted to re-apply.
- A verification link can only be used one time.

### Step 3: Create the user and log in
When the user logs in a new user is recorded into the system and an authenticated session is created.
A technical user id will be generated and used to identify the user in the system. 


## User authentication
For anonymous users a login button will be displayed in the menu bar. Clicking this button takes the user
to a login dialog. The user has three attempts to specify the correct password. When successful the user
receives an authenticated session and continues where he left off.
(Note that an anonymous user is by definition a user without a valid session, so a user that did not (successfully) log in. Because the user is 
anonymous the system does not know whether this person is actually registed in the system as a user and will therefore treat all anonymous users in the same way.)

In case the user provides a wrong password three times the password is revoked. When this happens or when the
user has forgotten the password the user can request a password reset, in which case a mail will be sent to
the e-mail address provided by the user containing a link that will allow to user to set a new password. This link will be
valid for 24 hours and can only be used once.

## User session
The system relies on JWT tokens to maintain the user session. Technically the user authenticates himself with an ID token.
The validity of this token is verified by checking the signatures against a well-known public key of the authentication provider.
The token contains an expiry date/time after which the user must re-authenticate. Often this can happen transparantly through
the use of a refresh token. This should be handled by the frontend.

## Log off
Users with an authenticated session are presented with a logoff button in the
menu bar. This will result in logging off the user at the authentication provider and removing any tokens from the browser cache.

## Change password
From his user profile page the user has the option to change his password.
He will need to specify both the current and the new password.
