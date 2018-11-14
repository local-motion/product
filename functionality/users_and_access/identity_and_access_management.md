# Identity and access management 
This section describes the enrollment and authentication of regular users. 
I would like people to come in by putting a signature (like the campaign that is running now). And that that is directly their login, if they want to do more than just sign a petition. Then you start with the same screen (s) as the campaign. Identify on the map and indicate a location (note: with functionality of the duplication of two or more streets on the same playground). They then sign the petition and are asked to go directly to their own promotion page by creating a password. The rest of the data is already there. Something along the lines of: 'Come directly into action on your own promotion page, enter your password here'. Something for Yvette to describe that well.

## User enrollment
Anyone can enroll into the system and become a regular user.

### Step 1: Specify e-mail address
The e-mail address will be the primary identification of the user within
the system. (It is the logical primary key of a user, note that technically there
must be a numeric primary key).

### Step 2: Verify e-mail address
The system shall send an e-mail to the specified e-mail address containing a url that the
user should click to confirm is ownership of the e-mail account.
- Clicking the link will take the user into the system where he can set a password.
- The verification link is valid for 24 hours. After this period the user is prompted to re-apply.
- A verification link can only be used one time.

### Step 3: Select nickname and password
The user selects a nickname that will identify the user to other users in the system. (Note the
e-mail address of the user will not be disclosed to other anonymous or regular users.) The nickname
must be unique within the system including the nicknames of users that have been off-boarded.

The user has to option to specify a password:
- the password must meet these criteria:
 - minimum length is 8 characters
 - maximum length is 20 characters
 - must include a numeric character and a special character
 - consists only of these characters: a-z A-Z 0-9 [TBD: special characters]
- the user has the option the store the password on the device and therefore not having to
do an explicit login anymore. The system should warn the user when selecting this option
that anyone with access to the device will be able to take his identity.

Alternatively the user has the option to let the system generate a password:
- the generated password will consist of 20 characters randomly selected from the set of supported
characters (see above)
- the system will not display this password, but stores it on the device so the user does
not need to do an explicit login anymore. The system should warn the user when selecting this option
that anyone with access to the device will be able to take his identity.

### Step 4: Create the user and log in
A new user is recorded into the system and an authenticated session is created.

## User authentication
When the user accesses the system without a session the system will check whether the user's
password is stored on the device. If so, the user is logged in automatically. The log in/log out status
is displayed in the menu bar. When the user does not have a password stored on his device or the password is
incorrect the user will receive an unauthenticated session and will continue as an anonymous user.

For anonymous users a log in button will be displayed in the menu bar. Clicking this button takes the user
to a login dialog. The user has three attempts to specify the correct password. When successful the user
receives an authenticated session and continues where he left off.

In case the user provided a wrong password three times the password is revoked. When this happens or when the
user has forgotten the password the user can request a password reset, in which case a mail will be sent to
the e-mail address provided by the user containing a link that will allow to user to set a new password. This link will be
valid for 24 hours and can only be used once.

## User session
Each user that enters the system, including anonymous users, will receive a session. This session can be used to analyse user
behaviour and the retain user authentication.

A session has the following attributes:
- session id: number identifying the session
- timestamp of session creation
- timestamp for last user activity [CHECK: SHOULD IT BE LIKE THIS?]


The session should expire after 60 minutes of inactivity and after 24 hours after creation of the session.
When an expired session is detected then:
- in case a valid password is present on the device the user gets a new session without any disruption of the user experience
- in all other cases the user is presented with the login dialog. After this dialog the user should be able to continue where he left off with needing to navigate there.

## Log off
Users with an authenticated session are presented with a logoff button in the
menu bar.
- When the user clicks this button the system checks whether a password
is stored on the user device.
- If this is the case the user is asked to confirm the logoff and the fact that he
will need to reapply for a new password. After confirmation the password is revoked and the user is logged off.
- Otherwise the user is just logged off.

## Change password
From his user profile menu the user has the option to change his password.
He will first need to re-authenticate and is then presented with the set-password
dialog. Here the user can again make the choice whether he wants the password to
be generated and whether he wants it to be stored.
