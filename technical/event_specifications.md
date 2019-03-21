# Event specifications

## Introduction
LocalMotion uses an event sourcing approach. All events that occur in the system are persisted and from these events views (projections)
are created. The application uses these views to present information to the users and to take decisions.

The advantage of event sourcing is that all information is retained in the system, giving a perfect audit trail and allowing for newly
introduced logic to act on historic events.

The drawback is that events that are stored will (in theory) reside in the system's database forever and they are considered to be immutable.
This introduces a legacy problem as any refactoring of the events results in new versions without cleaning up the instances (=events) of the 
previous version. Therefore all software needs to be backwards compatible with respect to all events or other mechanisms such as event upcasting
need to be utilised.

To soften the backward-compatibility burden it is important to design the events with care in the first place in order to avoid refactoring that
could have been foreseen. This document sets the design standards for events.


## Design standards

- An event is a fact and thereby irrevocable. The event's name should reflect this. For instance `MemberJoinedInitiativeEvent`. Do not use an imperative
  to name an event. So don't do `joinInitiativeEvent`.
- The name of a event should end with 'Event'
- The name of an event (Java) class is equal to the name of the event
- Summarising, in general the format for an event should be 
- The event should only contain details about the fact that happened, not about the state before or after the fact and it should also not contain any
  derived information.
- Do not store metadata (like who caused the event to happen) in the event itself, instead supply the metadata along with the event. The timestamp of the
  event is already recorded by the event sourcing framework so this does not need to be recorded separately.
- Not withstanding the statement above, the event should in general be interpreted by the projections and aggregates without inspecting the meta-data. So     when an event pertains to a person that person should be stored in the event itself. For example the `MemberJoinedInitiativeEvent` should contain the id    of the member that joined. Never assume a relation between the acting user that may be stored in the meta-data and the contents of the event. In other      words, do not assume that if user X triggered the MemberJoinedInitiativeEvent that X will be the member that joined.
- When referring to a person in the event, use the role that the user plays in that event as a denominator and do not postfix with `Id`. For example the      MemberJoinedInitiativeEvent will have a field called `member` that contains the userid of the member that joined. Another example is `observer` referring
  to the user that recorded a playground observation.
- Use the terms from the [glossary](https://github.com/local-motion/product/tree/master/functionality/glossary.md) for defining events.

