# Validations

## Introduction
This document contains all validations performed by the services in the LocalMotion system. Often, but not always,
these validations will be duplicated in the front-end code for an optimal user experience.

## Entity-level validations

### Playground
- the name of the playground is between 3 en 40 characters
- no whitespaces in the beginning and trailing of the playground name
- two playgrounds cannot be located within 100 metres of each other
- the maximum number of playgrounds that can exist within the system is 1000
- at least 4 decimal precisions required for longitude and latitude of the playground location, in order to avoid duplicate entries
- a user can join the playground where he is already a volunteer in, then server just returns success without making any changes to server
- the manager can not unsubscribe without choosing one from the recommended list of volunteers
- the id, name, lat, lng and status are required properties during creation of a new playground
- for onboarding non-smokefree playground, the smokeFreeDate must be future or present
- for onboarding smokefree playground, the smokeFreeDate must be past

### Playground workspace
- the maximum number of volunteers that can enter a playground workspace is 200
- the maximum number of managers in a workspace is volunteers/5

### Chat message
- a chat message cannot consist of whitespace only
- the minimum length of a chat message is 1 characters
- the maximum length of a chat message is 300 characters
- this is the set of valid characters for a chat message: [!@&(),.?":]

### Playground Observation
- a comment message can't consist of whitespaces only
- no whitespaces in the beginning or/and trailing of a comment
- the minimum length of a comment message is 100 characters
- the maximum length of a comment message is 2000 characters
- how frequently a volunteer can indicate his observations about the playground
- the indicated playground observation will be shown after verification of the comment by anyone of the managers
- consecutive 500 smokefree playground observations considered that The playground is now smokefree
- the maximum number of playground observations for the playground can be stored are 1000
- the smokefree indication, observer, initiativeId are required and no default value is set
- multiple volunteers can not indicate observation for a particular playground at the same time

## Cross-entity Validations
- a user can not be a volunteer in more than 3 playgrounds
