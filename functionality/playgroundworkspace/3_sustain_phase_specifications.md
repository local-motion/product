# Sustain phase specifications

When the smoke-free date is reached the sustain phase becomes the active phase. In contrast to the previous
 phases this phase is on-going. There is only one action to complete and the other items are a
continuous effort.

## Action 1: Share smoke-free
This first step is to share the happy news that the playground is now free of smoke.

Users can share this with the click of a button on social media where the system provides them
with template text. Additionally the system provides a template for a press announcement and the
possibility to indicate that the announcement has been made.

## Item 2: News
This item offers a list of news items. The items are listed in chronological order and are fetched from two sources:
- an external RSS newsfeeds (TBD source and whether this is actually RSS)
- a list of items created by the volunteers in the playground workspace

Note that the first source is the same for all playground workspaces while the second is only shown in the workspace
where the items are created.

User can create news items for their own playground workspace by entering a title and textual content.

A user may share any news item in the list on social media by clicking the associated button.


## Item 3: Validate
It is important that volunteers validate whether the playground actually is and remains smoke-free. When someone has done so
he can indicate to the system whether has found the playground to be smoke-free:
- when he found someone smoking in the playground the system will ask whether he addressed the issue with the smoker and whether
he successfully convinced the smoker not to smoke in the playground. The result and textual elaboration of the user is stored in the
system. (Sprint 3: The chat bot will report the result and textual content in the chat box).
- the system displays a grand total of all positive observations and all negative observations.
- additionally the system displays the length of the streak of positive observations. This is the number of positive observations
after the last negative observation.


## Item 4: What's next
Finally volunteers are encouraged to go help out other playgrounds. The system shows a zoomed in map of the area around
the playground and highlights other playgrounds that have not been converted yet. The zoom level should be such that
at least one other to-be-converted playground is shown while the current playground is displayed in the center. When other
to-be-converted playgrounds are sufficiently close, they should also be shown.
