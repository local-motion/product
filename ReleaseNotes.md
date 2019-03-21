# Release Notes

This document lists the major features that were introduced or changed in a release. For a detailed view of the internal 
changes please review the git logs of the involved repositories.

# Release 1.0.9-alpha - 21/03/2019
This release contains some technical upgrades:
- Refactored and improved polling mechanism for both the playgrounds and chat
- Environment-specific front-end configuration for Cognito and Google maps is fetched from the server
- SSL policy is changed for loadbalancer according to cbsp requirement

# Release 1.0.8-alpha - 11/03/2019
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
