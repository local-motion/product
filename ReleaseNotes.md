# Release Notes

This document lists the major features that were introduced or changed in a release. For a detailed view of the internal 
changes please review the git logs of the involved repositories.

## Release 1.0.23-beta - 22/10/2019
Just another upgrade of the RDS certificate. (This is a backend-only release.)

## Release 1.0.22-beta - 21/10/2019
In this release several Java packages are updated, a new RDS certificate is installed and a bug in the 'resend verification code' link in the onboarding form is fixed.

## Release 1.0.21-beta - 07/10/2019
This release:
- Upgrades some frontend and backend dependencies
- Fixes a bug in the statistics admin job
- Disables selection of a smokefree date in the past and correctly displays the selected date
- Introduces a developer settings page that (as a first feature) allows the developer to set the log level of the browser console log. This also gets rid of the log messages for regular users.

## Release 1.0.20-patch1 - 20/09/2019
Fixes a problem with the migration of chat messages.
This version only applies to the smokefree service.

## Release 1.0.20-beta - 20/09/2019
In this release the chat functionalty has been refactored mainly to allow for future upgrades. Additionally:
- When a user's name changes this is now reflected in the chat history
- Chat migration job, that migrates the chat history to the new model
- Fixed a bug in the cognito import file generation

## Release 1.0.19-beta - 30/07/2019
This is an internal infrastructure release. It does not contain any changes in the application.

## Release 1.0.18-beta - 26/07/2019
This release contains:
- The ability to run (technical) administrator jobs
- Cognito-import-file-generation job
- Delete-personal-data job, to 'forget' the personal data of a deleted user
- Statistics job, that presents count of the major (technical) entities in the system
- Some fixes in handling (deleted) users of which the personal data has been deleted
- Preparation of the system for dealing with multiple authentication providers (currently only AWS Cognito is supported)
- Users that sign up again with the same e-mail address after having offboarded before are recognised as the same user and 'revived'
- Revival may happen with a different user name, providing the users with a (somewhat crude) option to change their user name
- Steps that have been completed receive a checkmark in the navigation menu
- Improved workspace navigation on mobile devices
- Facebook workgroups social button removed

## Release 1.0.17-beta - 24/06/2019
In this release we:
- redesigned the signup and authentication dialogs
- implemented the password change and enabling/disabling notification on the user profile page
- added a notification 'drawer' that shows an audit trail of the recent activities in the initiatives that the user is involved in
- display a non-blocking notification in the bottom of the page when the network connection is lost
- refresh Cognito tokens every 20 minutes
- decrease the polling frequency of update streams when consecutive polls return no updates

## Release 1.0.16-beta - 06/06/2019
This release includes:
- a user profile page displaying all user related information and providing options to modify user attributes and to offboard. (Note that not all features have actually been implemented yet.)
- a page containing the initiatives that the user is involved in ('mijn acties'). (Note that the initiatives shown are a random selection at the moment.)
- improved signin, signup and password reset logic with better error feedback, routing and a password assist.
- proper email is sent when the user requests to resend to signup verification code.
- application now works in the Edge browser

## Release 1.0.15-alpha - 17/05/2019
In this release:
- the playground selection and creation takes place in the workspace resulting in one smooth process
- displaying a list of playgrounds in the vincinity of the search location of the user
- improved playground creation dialog
- user offboarding includes offboarding from Cognito, resulting in a complete offboarding process
- it is no longer possible to enroll multiple users with the same email address (Note that it is possible to reclaim an email address once a user has offboarded)
- the password reset and signup verification mails now contain links so the user no longer has to copy the verification codes
- fixed safari bug that blocked logged-in user from retrieving information from the server
- several small improvements

## Release 1.0.14-alpha - 30/04/2019
This release contains:
- a completely redesigned landing page that looks more attractive, has a better explanation of the smokefree playgrounds initiative and a stronger call-to-action for people to participate
- the workspace now has call-to-action buttons for each step
- improved date and time display for chat message (also works on Safari now)
- login step in the workspace has a more attractive design
- a collect opinions step has been introduced in the process (preparation phase)
- terms of usage and privacy statement now pop up from the signup screen so the user flow is no longer disturbed

## Release 1.0.13-alpha - 17/04/2019
The workspace has been redesigned to accomodate the feedback we got during the first series of alphatests:
- All navigation is on the left of the page now
- Card content has moved to occupy most of the page
- More textual content in each step
- More elaborate call-to-action (to be extended in the next release)
- Chat has moved to the same menu structure and content area as the steps
- Login integrated as step in the workspace
- Redesigned workspace welcome page

In the backend code:
- More strict validations were implemented
- Extended automated test cases
- Some technical improvements

## Release 1.0.12-alpha - 04/04/2019
This release contains a refactored backend and some usabilities changes in the frontend:
- Refactored java code: new package structure and better separation between Localmotion platform code and smokefree initiative code
- Make cities of NL searchable on the map
- Various visual improvements
- Enable map zoom by scrolling wheel (no more need to hold the control key)
- Remove business point-of-interest from playground map

## Release 1.0.11-alpha - 27/03/2019
A number of changes have been made to the front-end:
- Some styling improvements
- Add-playground dialogue is now full screen
- Improved map pins
- Upgraded chat polling mechanism
- Unauthenticated users that have chosen to join a workspace will automatically signup after login
- Sign-in bug fix
- Workspace cards that are still in development are hidden

## Release 1.0.10-alpha - 21/03/2019
This is an internal infrastructure release. It does not contain any changes in the application.

## Release 1.0.9-alpha - 20/03/2019
A large part of the infra stack has been refactored. These are the major changes:
- Stacks are more loosely coupled now. Generic stacks still export their attributes, but stacks are no longer tied together using on environment indicator. 
Dependent stacks can select the results from other stacks by specifying a prefix per stack.
- User pools are now sufficiently detached to support multiple pool in the account.
- More cloudwatch facilities

## Release 1.0.8-alpha - 11/03/2019
In this release:
- The validate-playground-is-smokefree card is connected to the backend and now keeps track of the total number of observations. Also the business rule that only one observation per day can be registered is implemented.
- The playground information in the front-end is continuously refreshed in the background. This allows for changes made by other users in the platform to appear within a few seconds.
- The workspace welcome page is redesigned and now provides a better explanation to users about what is expected of them.
- A new footer explains the purpose of the smokefree playgrounds initiative

## Release 1.0.7-alpha - 28/02/2019
This release features several improvements:
- Styling and scrolling related improvements have been made to the chat dialog.
- Managers are now automatically included in the list of volunteers for their playground workspace.
- The user name is now shown in the profile menu.
- The buttons on the action cards are disabled when users are not logged in or not a volunteer of that workspace.

## Release 1.0.6-alpha - 25/02/2019
A separate Team page in each workspace is introduced. It show the list of volunteers and hosts the chatbox.

New visitors are now greeted by a welcome page (with dummy content for now) that will explain the goal and workings of
the application. The workspace dashboard is prepared to be converted to a workspace welcome / onboarding page. Onboarding is done on this page and it is no longer required to visit a playground. Members of the workspace will skip this page and are 
automatically directed to the action page.

## Release 1.0.5-alpha - 21/02/2019
Many steps in the workspace are now complete as an initial version:
- Get support
- Flyers (was already done)
- Involve playground manager
- Decide to become smokefree
- Set a date
- Share decision
- Make it visible
- Share smokefree result
The validate step is partially implemented (not yet connected to the server-side logic)

On the playground map the marker are colored depending on the state of the playground:
- white = initial state
- blue = in progress
- green = smokefree

## Release 1.0.4-alpha - 19/02/2019
All steps of the process to become smokefree have been included in the workspace. Note that not all of them are implemented yet. The 'Flyers' component has been completed.

## Release 1.0.3-alpha - 18/02/2019
A http-to-https redirect is configured in the load balancer, so users that just type in the application's url without the scheme will automatically be redirected to the proper https endpoint.

## Release 1.0.2-alpha - 14/2/2019
This release upgrades our infrastructure, no new software was released.

## Release 1.0.1-alpha - 5/2/2019
This release provides a number of usability improvements:
- no more page reloads in the application, so instant navigation
- navigation links in the header bar
- playground search now matches any part of the playground name instead of just the beginning
- phase indicator in the workspace shows both the active phase (blue) as the selected phase (bigger circle)

In addition it is now possible for users that are not (yet) logged in to use the application in read-only mode:
- all workspace are accessible including the chatboxes
- no modifications can be made by these users neither can they enter chat messages
- when a user logs in via the link in the header he is direct back to the location where he initiated the login process

## Release 1.0.0-alpha - 23/1/2019
The initial launch of the local-motion platform. This release is an alpha version that will be used to gather feedback from a
limited group of alpha testers.


The main features include:
- a google maps overview of all playgrounds in The Netherlands
- statistics on the overall progress
- the ability to add a playground
- a workspace of each playground where volunteers can interact
- basic chat box for each workspace
- first set of action items to facilitate becoming a smoke-free playground:
  - inviting people through e-mail
  - sharing progress to social media
  - deciding to become smoke-free
  - setting a date to become smoke-free
- users can sign up to the platform and chose a nickname
