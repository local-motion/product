# Preparation phase specifications

The preparation phase is the first phase in the process. It can be initiated by anyone at anytime.

## Action 1: Get Support
The goal of this action is to get more volunteers involved in this playground workspace
and to get other kinds of contributions such as endorsements and donations.

### Share on social media
- By clicking an appropriate icon the user shares a predefined message (TBD but something like
   'I am volunteering to make playground [playground name] smoke-free. Please click [link]here[end_link] to join me!')
- Social media to be supported are: facebook, whatsapp, twitter, link to clipboard [CHECK: rookvrij.nl merely does facebook, mail and link]

### Send an invite
- A user can invite somebody to join this playground workspace by specifying an email address
- The e-mail is sent by the user's own e-mail program and is sent from the user's own e-mail address
- The mail is formatted according to this template [REF]
- This mail contains a invitation-specific link that the user is urged to click.
- The fact that the user clicked to invitation-specific link is recorded in the system.
- sprint 4: The link takes the user to the accept/decline/contribute page.
- The system stores the email addresses to which an invite was sent
- The system does not distinguish whether the e-mail address belongs to a user that
is already present in the system or not
- The system displays a list of all invitations that have been sent along with an indication
of whether the user has invitation-specific link. Note that the system does not disclose the decision
of the invitee whether to accept the invite and/or contribute in another way.
- sprint 4: invitations to users that are on the blacklist are presented in the playground workspace
as having been sent, but are not actually sent.
- If an invitee did not click the link and invitation is over a week old, then a remind button is shown.
- When a user click the remind button a reminder mail according to this template [REF] is prepared for sending
and opened in the user's own e-mail program
- Invitations older than 4 weeks are no longer displayed (no matter whether the invitee has acted or not)

## Action 2: Distribute flyers
A user can order paper flyer to distribute in the neighbourhood.
- At least three volunteers have to be part of the playground workspace before flyers can be ordered
- When flyers have already been ordered in the past for this playground then it is not possible to order
any more flyers. Volunteers should contain a global moderator ('Need help?') if they have a good reason to
order a second set of flyers
- The user enter his name and address details. These details are not stored in the system.
- The system sends an e-mail to a configured e-mail address containing the request for flyers, a link to the
playground workspace and the name and address details of the user. The people behind this mailbox will take
care of sending the stack of flyers to the user.
- The system records the fact that the user has ordered flyers. It is shown in the playground workspace which
user has ordered the flyers.
- The user can indicate that he has received the flyers at his home address by ticking a checkbox. Only the user that has ordered the flyers
is able to set this indication. This will trigger the chatbot to summon the other volunteers to assist in distributing the flyers.
- When distribution is complete any user can indicate this by ticking another checkbox. This can only be done when the 'flyers received'
indication has been set.

## Action 3: Involve playground manager
All playgrounds targeted by this application are managed either by volunteers, the municipality or a commercial organisation. A playground
can only become smoke-free when the playground's management decides as such and collaborates with the volunteers to convert the playground.

Some of the playgrounds have been preloaded into the system, while others are identified by users.
- For known playground the system will display the contact details (TBD what these are exactly)
- For the other playgrounds the system will display some tips (html content) to help the user to retrieve the playground's contact information

Once they have retrieved the contact information users can invite the playground manager by entering their e-mail address. The system will then
send an invitation to the specific playground workspace to the perceived manager. When the manager has joined he can indicate being the manager
of the actual playground, which completes this action.

Note that multiple users can indicate that they are the/a manager of a playground.

Also note that the system does not verify the validity of the claim that some-one is a manager.

## Action 4: Decision = smoke-free
The final step in the preparation phase is to taken the decision to become smoke-free. As it is only the playground's manager who can do so,
only he can manipulate the decision.

The manager can decide that the playground will become smoke-free, which will end this phase and start the execution phase. The manager can also
decide that the playground will not become smoke-free in which case he is asked to specify a reason.

### Drip-feed
When the manager has decided that the playground will not become smoke-free, the volunteers can opt to start a so-called drip-feed e-mail campaign.

After the campaign has been initiated:
- The system sends an e-mail to one of the volunteers in the playground workspace each day with the request to send an e-mail to the playground manager.
- The system provides an text template for the e-mail that is included in the mail to the volunteer.
- The system keeps track of which volunteers have been approached to send their e-mail and will display a progress indicator in the playground workspace.
