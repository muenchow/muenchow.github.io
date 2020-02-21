---
title: Channels
category: Reference
order: 1
---

### clientaddperm

Scopes: `manage`

Add a specified permissions to a client. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission
| `permvalue`   | string    | yes      | value of the permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### clientaddservergroup

Scopes: `manage`, `write`

Add a client to a server group specified with `sgid`.
Please note that a client cannot be added to default groups or template groups.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `sgid`        | integer   | yes      | id of server group

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_member_add_power                 | always

### clientdbdelete

Scopes: `manage`, `write`

Deletes a clients properties from the database.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_delete_dbproperties             | always

### clientdbedit

Scopes: `manage`, `write`

Changes a clients settings using given properties.
For detailed information, see Client Properties.
  
| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `client_description` | string    | yes      | description of client
| ...           | ...       | ...      | ...

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_modify_dbproperties             | always
| b_client_modify_description              | when changing `client_description` of other clients
| b_client_modify_own_description          | when changing `client_description` of own client

### clientdbfind

Scopes: `manage`, `write`, `read`

Returns a list of client database IDs matching a given pattern. You can either search for a clients last known nickname or his unique identity by using the -uid option. The pattern parameter can include regular characters and SQL wildcard characters (e.g. %).

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `pattern`     | string    | yes      | matches the value, allowing for sql style pattern matching
| `-uid`        | flag      | no       | when set search in `client_unique_id`; otherwise search in `client_nickname`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_client_dbsearch          | always

### clientdbinfo

Scopes: `manage`, `write`, `read`

Return detailed database information about a client including unique ID, creation date, etc.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_client_dbinfo            | always

### clientdblist

Scopes: `manage`, `write`, `read`

Displays a list of client identities known by the server including their database ID, last nickname, etc.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `start`       | integer   | no       | skip the first `n` entries
| `duration`    | integer   | no       | only return `n` entries
| `-count`      | flag      | no       | also return the total number of entries

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_client_dblist            | always

### clientdelperm

Scopes: `manage`

Remove a permissions from a client. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### clientedit

Scopes: `manage`, `write`

Changes a clients settings using given properties.
For detailed information, see Client Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client
| ...           | ...       | ...      | ...

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_modify_description              | when changing `client_description` of other clients
| b_client_modify_own_description          | when changing `client_description` of own client
| b_client_set_flag_talker                 | when changing `client_is_talker`

### clientfind

Scopes: `manage`, `write`, `read`

Return a list of clients matching a given name pattern.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `pattern`     | string    | yes      | pattern must be part of the client nickname (case insensitive)

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_client_search            | always

### clientgetdbidfromuid

Scopes: `manage`, `write`, `read`

Return the database ID matching the unique identifier specified by `cluid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cluid`       | integer   | yes      | unique id of client

### clientgetids

Scopes: `manage`, `write`, `read`

Returns all client IDs matching the unique identifier specified by cluid.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cluid`       | integer   | yes      | unique id of client

### clientgetnamefromdbid

Scopes: `manage`, `write`, `read`

Displays the unique identifier and nickname matching the database ID specified by cldbid.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database

### clientgetnamefromuid

Scopes: `manage`, `write`, `read`

Displays the database ID and nickname matching the unique identifier specified by `cluid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cluid`       | integer   | yes      | unique id of client

### clientgetuidfromclid

Scopes: `manage`, `write`, `read`

Displays the unique identifier matching the clientID specified by `clid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client

### clientinfo

Scopes: `manage`, `write`, `read`

Displays detailed configuration information about a client including unique ID, nickname, client version, etc.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_info_view                       | always

### clientkick

Scopes: `manage`, `write`

Kicks one or more clients specified with `clid` from their currently joined
channel or from the server, depending on `reasonid`. The `reasonmsg parameter` specifies a text message sent to the kicked clients. This parameter is optional and may only have a maximum of 40 characters.
For detailed information, see Definitions.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client
| `reasonid`    | integer   | yes      | `4` (kick from channel),<br/>`5` (kick from server)
| `reasonmsg`   | string    | no       | message diplayed to kicked client

| Permission                               | Required for
|------------------------------------------|-------------
| i_client_kick_from_server_power          | kicking from server
| i_client_kick_from_channel_power         | kicking from channel

### clientlist

Scopes: `manage`, `write`, `read`

Displays a list of clients online on a virtual server including their ID, nickname, status flags, etc.
Please note that the output will only contain clients which are currently in channels you're able to subscribe to.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `-uid`        | flag      | no       | include `client_unique_identifier`
| `-away`       | flag      | no       | include `client_away` and `client_away_message`
| `-voice`      | flag      | no       | include `client_flag_talking`, `client_input_muted`, `client_output_muted`, `client_input_hardware`, `client_output_hardware`, `client_talk_power`, `client_is_talker`, `client_is_priority_speaker`, `client_is_recording` and `client_is_channel_commander`
| `-times`      | flag      | no       | include `client_idle_time`, `client_created` and `client_lastconnected`
| `-groups`     | flag      | no       | include `client_servergroups`, `client_channel_group_id` and `client_channel_group_inherited_channel_id`
| `-info`       | flag      | no       | include `client_version` and `client_platform`
| `-country`    | flag      | no       | incldue `client_country`
| `-ip`         | flag      | no       | include `connection_client_ip`
| `-badges`     | flag      | no       | include `client_badges`
| `-icon`       | flag      | no       | include `client_icon_id`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_client_list              | always
| i_channel_subscribe_power                | seeing clients in a channel
| b_client_remoteaddress_view              | using `-ip`

#### Example

```http
GET /clientlist?-ip HTTP/1.1
```

```json
{
  "body": [
    {
      "cid": "1",
      "clid": "1",
      "client_database_id": "1",
      "client_nickname": "serveradmin",
      "client_type": "1",
      "connection_client_ip": "0.0.0.0"
    }
  ],
  "status": {
    "code": 0,
    "message": "ok"
  }
}
```

### clientmove

Scopes: `manage`, `write`
 
Moves one or more clients specified with `clid` to the channel with ID `cid`. If the target channel has a password, it needs to be specified with `cpw`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client
| `cid`         | integer   | yes      | id of channel
| `cpw`         | string    | no       | password of channel


| Permission                               | Required for
|------------------------------------------|-------------
| i_client_move_power                      | always

### clientpermlist

Scopes: `manage`, `write`, `read`

Displays a list of permissions defined for a client.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `-permsid`    | flag      | no       | include `permsid`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_client_permission_list   | always

### clientpoke

Scopes: `manage`, `write`

Sends a poke message to the client specified with `clid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client
| `msg`         | string    | yes      | message

| Permission                               | Required for
|------------------------------------------|-------------
| i_client_poke_power                      | always

### clientsetserverquerylogin

Scopes: `manage`, `write`

Updates your own ServerQuery login credentials using a specified username.
The password will be auto-generated.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `client_login_name` | string    | yes      | requested login name

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_create_modify_serverquery_login | always

### clientupdate

Scopes: `manage`, `write`
  
Change your ServerQuery clients settings using given properties.
For detailed information, see Client Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| ...           | ...       | ...      | ...

### setclientchannelgroup

Scopes: `manage`, `write`

Sets the channel group of a client to the ID specified with `cgid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cgid`        | integer   | yes      | id of channel group
| `cid`         | integer   | yes      | id of channel
| `cldbid`      | integer   | yes      | if of client in database

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_member_add_power                 | always
| i_group_member_remove_power              | always
