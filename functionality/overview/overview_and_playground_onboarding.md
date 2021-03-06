# Overview

## Map
When users enter the system a map of The Netherlands is displayed. On this map all known playgrounds are highlighted.
The playground indicator shows whether the playground is:
- smoke-free (sustain phase)
- not smoke-free (no workspace opened yet, workspace opened but with no remaining volunteers or playground manager has indicated that the playground will not be smoke-free)
- in progress (all other cases)

The user is able to zoom in and out. When the map is zoomed out to a level that it would be become clogged with playground markers,
the markers should be combined into an aggregate marker.

When the user selects a playground a few statistics are presented:
- name
- number of volunteers
- number of signed petitions
- progress indication

The map screen also displays the progress on national level.

## Adding a playground
The system is pre-loaded with a set of known playgrounds. This set is incomplete, so users should have the option to add
playgrounds.

The user needs to specify these playground attributes:
- name
- location: latitude + longitude (set by pinning a marker on the map)
  - if a playground is placed within a radius of 100 meters of another playground, a verification question should be presented to the user, stating: 'Do you mean playground [reference to other playground]?' This is to avoid duplications (for example by two street names adjacent to the same playground)

When the user defines a playground he will automatically onboard himself as playground moderator in that playground. All rules
for onboarding apply. When the user is not able to onboard he will also not be able to add the playground.
