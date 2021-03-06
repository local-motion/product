# Code structuring

## Standards for Java packages

All packages in LocalMotion must be subpackages of `io.localmotion`.

Main module reside in their own subpackage at the top level, for instance: `io.localmotion.chatbox`.

Infrastructure related packages should reside under `io.localmotion.infrastructure`.

The main classes / entrypoints of the application reside in `io.localmotion.application`.

It is important to separate the generic logic in LocalMotion from the logic that relates towards a particular type of initiative.
Therefore generic logic should reside in separate packages with name describing the function that the logic provides, for example
`io.localmotion.initiative`. Specific logic goes into it's own package, for example `io.localmotion.smokefreeplaygrounds`.


Within a functional package (either io.localmotion.platform or a specific one), create the following substructure:
- command: command classes that can be submitted on the (Axon) command bus
- event: event classes that can be submitted on the (Axon) event bus. These classes will also end up in the database and therefore cannot easily be refactored. So take care when designing these classes and be sure to put them in the right package.
- domain: enumeration, data and value classes that represent the entities in the system and can be used thoughout the system.
- controller: any rest controller classes and graphql controller and resolver classes along with specific input and result classes. (When more generic classes such as commands are use do not include them here, but leave them in their own package.)
- aggregate: the aggregate classes that will handle the commands
- projection: the projection/view classes and including any data/value classes served by these projections.
For all the above holds that any helper classes should be included in the same packages as the class that uses them.


## Resulting package structure

- io.localmotion.application
- io.localmotion.chatbox
- io.localmotion.configuration
- io.localmotion.personaldata
- io.localmotion.security.aws.cognito
- io.localmotion.storage.database
- io.localmotion.storage.aws.rds.secretmanager
- io.localmotion.eventsourcing.axon
- io.localmotion.interfacing.graphql
- io.localmotion.initiative.command
- io.localmotion.initiative.event
- io.localmotion.initiative.domain
- io.localmotion.initiative.controller
- io.localmotion.initiative.aggregate
- io.localmotion.initiative.projection
- io.localmotion.user.command
- io.localmotion.user.event
- io.localmotion.user.domain
- io.localmotion.user.controller
- io.localmotion.user.aggregate
- io.localmotion.user.projection
- io.localmotion.smokefreeplaygrounds.command
- io.localmotion.smokefreeplaygrounds.event
- io.localmotion.smokefreeplaygrounds.domain
- io.localmotion.smokefreeplaygrounds.controller
- io.localmotion.smokefreeplaygrounds.aggregate
- io.localmotion.smokefreeplaygrounds.projection







