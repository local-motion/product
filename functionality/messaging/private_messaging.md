# Private messaging

Because of privacy considerations the e-mail addresses of user are not shown to
other (regular) users. This presents a problem when user want to exchange private information
like their actual name or address details as all communication on the platform's chatboxes is public.


To address this problem the platform provides a private messaging feature.

## Sending a private message from the platform
An authenticated user has to option to send a private message to any other user in the platform. The recipient of
the message is identified by the nickname. When the user select the private message option and (explicitly or derived from context)
select the recipient the user's standard email client is opened showing a new e-mail:
- from: &lt;e-mail address of sender&gt;
- to: &lt;nickname of recipient&gt;@berichten.rookvrijspelen.nl
- title: empty
- content: empty
(Note the e-mail domain is still to be determined)
It is left to the user to complete and send this e-mail. The system does not record that the user has initiated a private message.

## Opt-out
A user can choose to opt-out from private messages. This is a setting in the user profile. Opting out prevents the user
both from receiving messages and sending messages.

## E-mail gateway
An e-mail gateway receives all e-mails sent to berichten.rookvrijspelen.nl and:
- checks whether the sender's e-mail address corresponds to an active user in the system and bounces the mail otherwise
- looks up the recipient user in the system from nickname of the receiver
- checks whether the recipient has opted-out from private messages, in which case the mail is bounced to the receiver
- substitutes the e-mail address of the sender by <nickname of the sender>@berichten.rookvrijspelen.nl
- prepends 'Rookvrij spelen:' to the title of the mail
- appends a footer to the mail with a link to the platform and an opt-out option for private e-mail

### Example
Consider two users: alice@wonderland.com with nickname butterfly and bob@outlook.com with nickname grasshopper

Now Alice sends Bob this e-mail:
```
from: alice@wonderland.com
to: grasshopper@berichten.rookvrijspelen.nl
title: meeting
content:
Hi grasshopper,
Let's meet next Wednesday at the playground at 15:00.
Regards butterfly
```
The gateway translates this into:
```
from: butterfly@berichten.rookvrijspelen.nl
to: bob@outlook.com
title: Rookvrij spelen: meeting
content:
Hi grasshopper,
Let's meet next Wednesday at the playground at 15:00.
Regards butterfly
This is a message from the rookvrijspelen platform. Click here to opt-out.
```


## Sending a private message using regular e-mail

Users are free to initiate messages from their e-mail client. Any e-mail send to &lt;nickname of recipient&gt;@berichten.rookvrijspelen.nl
will end up at the e-mail gateway and be processed as described. This allows recipients to respond to private messages and ensures
that the response will also be private for both sender and receiver.

Note that when someone initiates an e-mail conversation from an e-mail client they will have to do so with the e-mail with which they are registered
in the system otherwise the gateway will bounce the mail in order to avoid exposure of the sender's e-mail address.

## Issue
In order to prevent anyone from sending messages on behalf of any user by using a forged sender e-mail address we will need some assurance to
legitimacy of the sender's e-mail address.
Ideas:
- Include a conversation id. BTW this blocks the option of initiating a conversation from outside the system.
- Use Sender Policy Framework
- First send a reply mail to the sender with a conversation id and ask the sender to reply to this mail
