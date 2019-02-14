# Validations

## Introduction
This document contains all validations performed by the services in the LocalMotion system. Often, but not always,
these validations will be duplicated in the front-end code for an optimal user experience.

## Entity-level validations

### Playground
- The name of the playground is between 3 en 40 characters ( no whitespaces in the beginning and trailing of the playground name )
- Two playgrounds cannot be located within .. metres of each other ( Are there any API/Service provided by Netherlands to verify entered/chosen address )
- The maximum number of playgrounds that can exist within the system is ..
- At least 4(TBD) decimal precisions required for Longitude and Latitude of the Playground location, in order to identify how close two Playgrounds are located
- A User must not be able to join a Playground twice
- The id, name, lat, lng and status are required properties during creation of a new Playground
- The smokeFreeDate must be Future or Present Date

### Playground workspace
- The maximum number of volunteers that can enter a playground workspace is 200
- The maximum number of managers in a workspace is ..

### Chat message
- a chat message cannot consist of whitespace only
- the minimum length of a chat message is 1 characters
- the maximum length of a chat message is 300 characters
- this is the set of valid characters for a chat message: ...  (or provide a regexp)

### Playground Observation
- A comment message can't consist of whitespaces only, and no whitespaces in the beginning or/and trailing of the comment
- The minimum length of a comment message is 100 characters
- The maximum length of a comment message is ... ( The maximum characters allowed in MySQL TEXT Data Type is 65k )
- How frequently a Volunteer can indicate his observations about The Playground
- The Volunteer can not indicate the Playground observation after the smokeFreeDate
- The indicated Playground observation will be shown after verification of the comment by ...
- ... number of smokefree Playground observations considered that The Playground is now smokefree
- The maximum number of playground observations for the playground can be stored are ...
- The smokefree, comment, observer, initiativeId are required and no default value is set
- Multiple Volunteers can not indicate playground observation at the same time( Maybe within 1 min )

## Cross-entity Validations
- a user can not be a volunteer in more than 3 playgrounds
