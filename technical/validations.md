# Validations

## Introduction
This document contains all validations performed by the services in the LocalMotion system. Often, but not always,
these validations will be duplicated in the front-end code for an optimal user experience.

## Entity-level validations

### Playground
- The name of the playground is between 3 en 40 characters
- Two playgrounds cannot be located within .. metres of each other
- The maximum number of playgrounds that can exist within the system is ..

### Playground workspace
- The maximum number of volunteers that can enter a playground workspace is 200
- The maximum number of managers in a workspace is ..


### Chat message
- a chat message cannot consist of whitespace only
- the minimum length of a chat message is 1 characters
- the maximum length of a chat message is 300 characters
- this is the set of valid characters for a chat message: ...  (or provide a regexp)

## Cross-entity Validations
- a user can not be a volunteer in more than 3 playgrounds
