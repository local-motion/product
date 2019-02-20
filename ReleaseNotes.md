# Release Notes

This document lists the major features that were introduced or changed in a release. For a detailed view of the internal 
changes please review the git logs of the involved repositories.

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
