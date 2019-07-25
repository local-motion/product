# Users

## User types
Each user in the system is of one particular type.

### Anonymous user
Anonymous users are users that have not authenticated themselves. As most data in the system is public, these users can access most data, 
however they cannot initiate any change in the system.

### Regular user
Anyone can register themselves as a regular user. During registration an authentication method is established. After such an user
has properly authenticated himself by a login procedure that user qualifies as a regular user.

### Technical administrator
These users have the backend permissions to run jobs in the system. Currently these jobs need to be triggered through the frontend.
The jobs have the email address configured of the user that is allowed to trigger the job (typically that of the technical administrator).
Therefore there is no need to distinguish a technical administrator role in the system itself. Usually jobs will only be available to the
system at the time that they are actually run preventing too much exposure.


## User roles
Roles are assigned to regular users to grant additional privileges. A user may be assigned multiple roles.

### Global moderator
Global moderators have overall access to data (except user credentials) and are able to intervene when local groups
get into trouble.

### Functional administrator
These users will generally be small in number and authorised to assign privileges (such as the global moderator role) to other users.


## User roles within an playground workspace
With the context of a playground workspace a regular user can have one or more of these special roles. The roles that are assigned to a user
are publicly visible.

### Playground manager
The playground manager represents the manager of the actual playground.
- Actions that modify the formal state of the playground such as the decision to become
smoke-free are restricted to users with the playground manager role
- The playground manager role is self-assigned, the system performs no validation on whether
the user that claims this role occupies such a role in the actual playground.
- Multiple users can claim this role for the same playground

### Future extension: Playground moderator
The playground moderator is able to intervene in discussion within the playground
workspace and the playground moderator has to accept invitation requests to the
playground workspace.
- The user that starts the process for particular playground and thereby creates the
playground workspace automatically becomes the playground moderator.
- The playground moderator can assign this role to other users and take away this
role from other users or himself.
- The number of users that can have the playground moderator role is unlimited.


## User attributes
The system records the following attributes of a user:
- username: a self-chosen name that is set by the user during enrollment. The name can be changed, but this may require re-enrollment depending on the authenication method.
The username is unique throughout the system. The system will only display the username to other regular or
anonymous users when referring to this user.
- e-mail address: alias for the username and also unique. It is only disclosed to moderators and administrators. The e-mail address can be used to restore the user's credentials.
- preferences: for example notification settings
- personalisation: user profile picture (future)
