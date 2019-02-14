# Validations

## Introduction
This document contains all validations performed by the services in the LocalMotion system. Often, but not always,
these validations will be duplicated in the front-end code for an optimal user experience.

## Entity-level validations

### Playground
- the name of the playground is between 3 en 40 characters
- two playgrounds can not have the same name
- no whitespaces in the beginning and trailing of the playground name
- two playgrounds cannot be located within 100 metres of each other
- the maximum number of playgrounds that can exist within the system is 1000
- the id, name, lat, lng and status are required properties during creation of a new playground
- for onboarding playground with status 'finished' (that claims to be smokefree), the smokeFreeDate must be past
- the status can not be stopped unless the playground managers choose that the playground can not be smokefree
- the type can not be smokefree unless it get consecutive 500 smokefree playground observations and status must be finished (TBD)

### Playground workspace
- the maximum number of volunteers that can enter a playground workspace is 200
- the maximum number of managers in a workspace is 3
- only playground managers can decide whether playground can be smokefree or not
- the playground can not be decided if status is not_started or stopped
- only playground managers can set smokefreeDate and they cannot set smokefreeDate when the smokefree decision has not been made yet



### Chat message
- a chat message cannot consist of whitespace only
- the minimum length of a chat message is 1 characters
- the maximum length of a chat message is 3000 characters
- this is the set of valid characters for a chat message: [!@&(),.?":]

### Playground Observation
- a comment message can't consist of whitespaces only
- no whitespaces in the beginning or/and trailing of a comment
- the minimum length of a comment message is 1 characters
- the maximum length of a comment message is 2000 characters
- once a day the volunteer can indicate his observations about the playground
- consecutive 50 smokefree playground observations considered that The playground is now smokefree
- the maximum number of playground observations for the playground can be stored are 1000
- the smokefree indication, observer, initiativeId are required and no default value is set

## Cross-entity Validations
- a user can not be a volunteer in more than 3 playgrounds
