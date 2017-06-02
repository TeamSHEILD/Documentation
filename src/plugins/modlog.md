# ModLog Plugin

The modlog plugin provides a mechanisim for logging various events and actions to one or more channels. The intention of the modlog is to provide a private feed of server events that administrators and moderators can use to better monitor and audit users actions. The modlog is extremely configurable, and thus fairly complex.

## Configuration Options

| Option | Description | Type | Default |
|--------|-------------|------|---------|
| ignored\_users | A list of user ids which are ignored in the modlog. This is useful for ignoring bots that regularly delete or edit their messages | list | empty |
| new\_member\_threshold | The number of seconds an account is considered new | int | 900 (15 minutes) |
| channels | Mapping of channel names/ids to channel configurations | dict | empty |

### Channel Configuration

| Option | Description | Type | Default |
|--------|-------------|------|---------|
| compact | Whether to render the mode in the compact format (vs rich) | bool | true |
| include | List of modlog actions to include. If empty this includes all mod log actions | list | empty |
| exclude | List of modlog actions to exclude. If empty this excludes no mod log actions | list | empty |
| rich | List of modlog actions to force render in rich mode | list | empty |
| timestamps | Whether to render timestamps along with loglines | bool | false |
| timezone | The timezone that timestamps are rendered in | timezone | US/Eastern |

## Actions

| Action | Description |
|--------|-------------|
| CHANNEL\_CREATE | A channel is created |
| CHANNEL\_DELETE | A channel is deleted |
| GUILD\_BAN\_ADD | A ban is added |
| GUILD\_SOFTBAN\_ADD | A softban is added |
| GUILD\_TEMPBAN\_ADD | A tempban is added |
| GUILD\_BAN\_ADD\_REASON | A ban (with a reason) is added |
| GUILD\_MEMBER\_ADD | A member joins |
| GUILD\_MEMBER\_REMOVE | A member leaves (or gets kicked) |
| GUILD\_MEMBER\_KICK | A member is kicked |
| GUILD\_MEMBER\_ROLES\_ADD | A role is added to a member |
| GUILD\_MEMBER\_ROLES\_RMV | A role is removed from a member |
| GUILD\_MEMBER\_AVATAR\_CHANGE | A member changes their avatar |
| GUILD\_ROLE\_CREATE | A role is created |
| GUILD\_ROLE\_RMV | A role is removed |
| ADD\_NICK | A user adds a nickname |
| RMV\_NICK | A user removes a nickname |
| CHANGE\_NICK | A user changes their nickname |
| CHANGE\_USERNAME | A user changes their username |
| MESSAGE\_EDIT | A message is edited |
| MESSAGE\_DELETE | A message is deleted |
| MESSAGE\_DELETE\_BULK | Multiple messages are deleted |
| VOICE\_CHANNEL\_JOIN | A user joins a voice channel |
| VOICE\_CHANNEL\_LEAVE | A user leaves a voice channel |
| VOICE\_CHANNEL\_MOVE | A user moves voice channels |
| COMMAND\_USED | A user uses a rowboat command |
| SPAM\_DEBUG | A user triggered spam protection |
| MEMBER\_RESTORE | A user rejoined and had their roles/nickname/etc restored |
| CENSOR | A user posted a message that was censored by the bot |