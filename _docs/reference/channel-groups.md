---
title: Channel Groups
category: Reference
order: 1
---

### channelgroupadd

Scopes: `manage`, `write`

Creates a new channel group using a given name. The 
For detailed information, see Definitions.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `name`        | string    | yes      | name of the channel group
| `type`        | integer   | no       | `0` (template)<br/>`1` (regular)<br/>`2` (query);<br/>Default: `1`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_create      | always

### channelgroupaddperm

Scopes: `manage`

Adds a permission to a channel group. 
Either `permid` or `permsid` must be set.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cgid`        | integer   | yes      | id of channel group
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission
| `permvalue`   | string    | yes      | value of the permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### channelgroupclientlist

Scopes: `manage`, `write`, `read`

Displays all the client and/or channel IDs currently assigned to channel
groups.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | no       | only list entries of this channel
| `cldbid`      | integer   | no       | only list entries of this client
| `cgid`        | integer   | no       | only lsit entries of this channel group

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_client_list | always

### channelgroupcopy

Scopes: `manage`

Creates a copy of the channel group specified with scgid. If tcgid is set to
0, the server will create a new group. To overwrite an existing group, simply
set tcgid to the ID of a designated target group. If a target group is set,
the name parameter will be ignored. The type parameter can be used to create
template groups.
For detailed information, see Definitions.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `scgid`       | integer   | yes      | 
| `tcgid`       | integer   | yes      |
| `name`        | string    | yes      |
| `type`        | integer   | yes      |


| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_create      | always
| i_group_modify_power                     |

### channelgroupdel

Scopes: `manage`

Deletes a channel group by ID.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cgid`        | integer   | yes      | id of channel group
| `force`       | integer   | no       | when `1`, delete non empty channel groups

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_delete      | always

### channelgroupdelperm

Scopes: `manage`

Removes a specified permission from the channel group. A permission can be specified by permid or permsid.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cgid`        | integer   | yes      | id of channel group
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### channelgrouplist

Scopes: `manage`, `write`, `read`

Returns a list of channel groups available on the selected virtual server.

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_list        | always

### channelgrouppermlist

Scopes: `manage`, `write`, `read`

Returns a list of permissions assigned to the channel group specified with
cgid.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cgid`        | integer   | yes      | id of channel group
| `-permsid`    | flag      | no       | include `permsid`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_list        | always

### channelgrouprename

Scopes: `manage`

Changes the name of a channel group.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cgid`        | integer   | yes      | id of channel group
| `name`        | string    | yes      | new name of the channel group

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always


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
