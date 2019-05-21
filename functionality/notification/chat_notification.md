# Chat notification

## Introduction
Participants in a chatbox will get notified by e-mail about the chat messages they missed. By doing this LocalMotion's
users are not forced to check daily for new messages in their community's chatbox and the messages that get posted are
sure to the reach the community members.

## Who gets notified
Notifications are sent to users who:
- are members of the initiative that the chatbox belongs to (or to put in another way: the users who are able to post messages in the chatbox)
- did not opt out for these notifications
- were not already notified of the last message in the chatbox
- did not already see the last message in the chatbox in the application
- were a member of the initiative when the last message got posted

## Which messages are included in the notification
A user gets a notification including all messages starting from the first 'unread' message up to the most recent message.

The first unread message is the latest of these messages:
- the first message posted after the user has joined the chatbox (so in effect joined the initiative)
- the first message posted after the last successful notification to this user
- the first message posted after the last message read by the user in the application

## Which messages are considered to be read by the user in the application's front-end
For a message to be considered to be read it must have been displayed to the user (rendered on a visible part of web page) for at least 3 seconds. The system only keeps track of the latest message that was read by the user. All previous
messages are considered to be read even if they have not been displayed.

When a user posts a messages that message is of course considered to be read by that user and as that is by definition the latest message at that moment, all messages in the chatbox are considered to be read by the user.

## When and how is the user notified
Each morning at 7:00 the user get one e-mail per chatbox containing all unread messages in that chatbox. When there are no
unread messages the user does not receive an e-mail. When the user has multiple active chatboxes he will receive one
mail containing all messages for all each chatboxes.
