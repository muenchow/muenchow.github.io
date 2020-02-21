---
title: Servers
category: Reference
order: 1
---

### sendtextmessage

Scopes: `manage`, `write`

Sends a text message to `target`. If `targetmode` is set to `1`, a
message is sent to the client with the ID specified by `target`. If `targetmode` is set to `2` or `3`, the target parameter will be ignored and a message is sent to the current channel or server respectively.


| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `targetmode`  | integer   | yes      | `1` (Client)<br>`2` (Channel)<br>`3` (Server)
| `target`      | integer   | no       | id of client to receive the message
| `msg`         | string    | yes      | message to be send

| Permission                               | Required for
|------------------------------------------|-------------
| i_client_private_textmessage_power       | sending a message to a client
| b_client_server_textmessage_send         | sending a message to the server
| b_client_channel_textmessage_send        | sending a message to the current channel

### servercreate

Scopes: `manage`

Creates a new virtual server using the given properties and displays its ID, port and initial administrator privilege key. If `virtualserver_port` is not specified, the server will test for the first unused UDP port. The first virtual server will be running on UDP port 9987 by default. Subsequently started virtual servers will be running on increasing UDP port
numbers.
For detailed information, see Virtual Server Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `virtualserver_name` | string    | yes      | name of the new virtual server
| ...           | ...       | ...      | ...

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_create                   | always

### serverdelete

Scopes: `manage`

Deletes the virtual server specified with sid. Please note that only virtual servers in stopped state can be deleted.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sid`         | integer   | yes      | id of virtual server

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_delete                   | always

### serveredit

Scopes: `manage`, `write`

Changes the selected virtual servers configuration using given properties. Note that this command accepts multiple properties which means that you're able to change all settings of the selected virtual server at once.
For detailed information, see Virtual Server Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| ...           | ...       | ...      | ...

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_modify_name
| b_virtualserver_modify_welcomemessage
| b_virtualserver_modify_maxclients
| b_virtualserver_modify_reserved_slots
| b_virtualserver_modify_password
| b_virtualserver_modify_default_servergroup
| b_virtualserver_modify_default_channelgroup
| b_virtualserver_modify_default_channeladmingroup
| b_virtualserver_modify_ft_settings
| b_virtualserver_modify_ft_quotas
| b_virtualserver_modify_channel_forced_silence
| b_virtualserver_modify_complain
| b_virtualserver_modify_antiflood
| b_virtualserver_modify_hostmessage
| b_virtualserver_modify_hostbanner
| b_virtualserver_modify_hostbutton
| b_virtualserver_modify_port
| b_virtualserver_modify_autostart
| b_virtualserver_modify_needed_identity_security_level
| b_virtualserver_modify_priority_speaker_dimm_modificator
| b_virtualserver_modify_log_settings
| b_virtualserver_modify_icon_id
| b_virtualserver_modify_weblist
| b_virtualserver_modify_min_client_version
| b_virtualserver_modify_codec_encryption_mode

### serveridgetbyport

Scopes: `manage`, `write`, `read`

Returns the database ID of the virtual server running on the UDP port
specified by `virtualserver_port`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `virtualserver_port` | integer   | yes      | port of the virtual server

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_virtualserver_list      | always

### serverinfo

Scopes: `manage`, `write`, `read`

Return detailed configuration information about the selected virtual server including unique ID, number of clients online, configuration, etc.
For detailed information, see Virtual Server Properties.

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_info_view                | always

### serverlist

Scopes: `manage`

Return a list of virtual servers including their ID, status, number of clients online, etc.
If you're using the `-all` option, the server will list all virtual servers stored in the database. This can be useful when multiple server instances with different machine IDs are using the same database. The machine ID is used to identify the server instance a virtual server is associated with.
The status of a virtual server can be either online, offline, booting up, shutting down or virtual online. While most of them are self-explanatory,
virtual online is a bit more complicated. Whenever you select a virtual server which is currently stopped with the `-virtual` parameter, it will be started in virtual mode which means you are able to change its configuration, create channels or change permissions, but no regular TeamSpeak 3 Client can connect. As soon as the last ServerQuery client deselects the virtual server, its status will be changed back to offline.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `-uid`        | flag      | no       | include `virtualserver_unique_identifier`
| `-short`      | flag      | no       | exclude `VIRTUALSERVER_CLIENTS_ONLINE`, `VIRTUALSERVER_QUERYCLIENTS_ONLINE`, `VIRTUALSERVER_MAXCLIENTS`, `VIRTUALSERVER_UPTIME`, `VIRTUALSERVER_NAME`, `VIRTUALSERVER_AUTOSTART`, `VIRTUALSERVER_MACHINE_ID`
| `-all`        | flag      | no       | list all servers regardless of `VIRTUALSERVER_MACHINE_ID`
| `-onlyoffline` | flag      | no       | list only servers with status offline

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_virtualserver_list      | always

### serverrequestconnectioninfo

Scopes: `manage`, `write`, `read`

Displays detailed connection information about the selected virtual server
including uptime, traffic information, etc.

| Permission                               | Required for
|------------------------------------------|------------
| b_virtualserver_connectioninfo_view      | always

### serverstart

Scopes: `manage`

Starts the virtual server specified with `sid`. Depending on your permissions, you're able to start either your own virtual server only or all virtual servers in the server instance.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sid`         | integer   | yes      | id of virtual server

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_start_any                | starting any server
| b_virtualserver_start                    | starting a specific server

### serverstop

Scopes: `manage`

Stops the virtual server specified with `sid`. Depending on your permissions, you're able to stop either your own virtual server only or all virtual servers in the server instance.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sid`         | integer   | yes      | id of virtual server
| `reasonmsg`   | string    | no       | text message that is sent to the clients before server stops

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_stop                    | always

### servertemppasswordadd

Scopes: `manage`, `write`

Sets a new temporary server password specified with `pw`. The temporary password will be valid for the number of seconds specified with `duration`. The client connecting with this password will automatically join the channel specified with `tcid`. If `tcid` is set to 0, the client will join the default channel.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `pw`          | string    | yes      | password to add
| `desc`        | string    | yes      | descriptive text
| `duration`    | integer   | yes      | number of seconds the password will be valid
| `tcid`        | integer   | no       | id of channel, where client to join when using the password
| `tcpw`        | string    | no       | password of the channel, specified by `tcid`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_modify_temporary_passwords | either
| b_virtualserver_modify_temporary_passwords_own | or

### servertemppassworddel

Scopes: `manage`, `write`

Deletes the temporary server password specified with `pw`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `pw`          | string    | yes      | password to delete

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_modify_temporary_passwords | deleting any password
| b_virtualserver_modify_temporary_passwords_own | deleting password created by invoker

### servertemppasswordlist

Scopes: `manage`, `write`, `read`

Returns a list of active temporary server passwords. The output contains the clear-text password, the nickname and unique identifier of the creating client.

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_modify_temporary_passwords | list all passwords
| b_virtualserver_modify_temporary_passwords_own | list passwords created by invoker

