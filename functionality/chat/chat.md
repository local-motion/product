# Chat

## Chat boxes
All (authenticated) users in a playground workspace can chat with each other. There is one chat box per playground workspace.

The system retains these attributes per message:
- timestamp
- author
- message text
- deleted by moderator y/n

## Message formatting
A chat message can only be plain text. The characters must be constrained to a well-defined set. Characters that lie outside this set will
not be accepted as user input.
Chat messages will be displayed as they were entered without any interpretation (so for instance web links will not be clickable).

## Chat bot
The system will post messages of significant events. It will do so as a recognisable chat bot.

## Moderation
Both playground moderators and global moderators can delete messages that they deem unfit. Such messages will be marked as deleted (and
therefore not be physically deleted). Messages marked as deleted will still be displayed with timestamp and author, but instead of
the message text an indication 'deleted by moderator' will be shown.

Chat bot messages cannot be moderated.

## Constraints
- A chat message has a minimum length of 1 and a maximum length of 300 characters
- A user can submit no more than 100 messages per day in total over all chat boxes in LocalMotion
- The chatbox of a single playground workspace can contain no more than 1000 messages, including messages deleted by the moderator
- The text message must match this regular expression: TBD
