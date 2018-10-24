# Users

## User types
Each user in the system is of one particular type.

### Anonymous users
Anonymous users are users that have not authenticated themselves.
- this user type will be introduced in sprint 4

### Regular users
Anyone can register themselves as a user with their e-mail address. During
registration an authentication method is established. After such an user
has properly authenticated himself by a login procedure that user qualifies
as a regular user.

### Moderators
Moderators have overall access and are able to intervene when local groups
get into trouble. Longfonds employees and possibly assigned volunteers will
typically be a moderator.
- this user type will be introduced in sprint 4

### Administrators
These users have the highest permissions in the system and will generally be
small in number and authorised to assign privileges to other users.
- this user type will be introduced in sprint 4


## User roles within an playground workspace
With the context of a playground workspace a regular user (and only a regular user)
can have one or more of these special roles. The roles that are assigned to a user
are publicly visible.

### Playground moderator
The playground moderator is able to intervene in discussion within the playground
workspace and the playground moderator has to accept invitation requests to the
playground workspace.
- The user that starts the process for particular playground and thereby creates the
playground workspace automatically becomes the playground moderator.
- The playground moderator can assign this role to other users and take away this
role from other users or himself.
- The number of users that can have the playground moderator role is unlimited.
- There must always be at least one moderator for a playground workspace. This implies
that the last remaining moderator cannot remove himself from this role or leave the
playground workspace.

### Playground manager
The playground manager represent the manager of the actual playground.
- Actions that modify the formal state of the playground such as the decision to become
smoke-free are restricted to users with the playground manager role
- The playground manager role is self-assigned, the system performs no validation on whether
the user that claims this role occupies such a role in the actual playground.
- Multiple users can claim this role for the same playground

## User attributes
The system records the following attributes of a user:
- e-mail address: this is the user's identifier. It is only disclosed to moderators and administrators.
- nickname: a self-chosen name that is set by the user during enrolled and cannot be modified afterwards.
The nickname is unique throughout the system. The system will only display the nickname to other regular or
anonymous users when referring to this user.
- user type: a user has exactly one type. See the discussion in the previous section. The type of a user is publicly
visible throughout the system.
- playground roles: a set of [playground-user role] combinations. See the discussion in the previous section. The roles that are assigned to a user
are publicly visible.
