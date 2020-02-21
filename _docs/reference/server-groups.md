---
title: Server Groups
category: Reference
order: 1
---

### servergroupadd

Scopes: `manage`

Creates a new server group using the name specified with name and displays its ID. The optional type parameter can be used to create ServerQuery groups and template groups.
For detailed information, see Definitions.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `name`        | string    | yes      | name of the server group
| `type`        | integer   | no       | `0` (template)<br/>`1` (regular)<br/>`2` (query);<br/>Default: `1`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_servergroup_create       | always

### servergroupaddperm

Scopes: `manage`

Add a specified permissions to the server group specified with `sgid`. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission
| `permvalue`   | string    | yes      | value of the permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### servergroupautoaddperm

Scopes: `manage`

Adds a set of specified permission to *all* regular server groups on all virtual servers. The target groups will be identified by the value of their i_group_auto_update_type permission specified with `sgtype`. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgtype`      | integer   | yes      | `10` (Channel Guest)<br/>`15` (Server Guest)<br/>`20` (Query Guest)<br/>`25` (Channel Voice)<br/>`30` (Server Normal)<br/>`35` (Channel Operator)<br/>`40` (Channel dmin)<br/>`45` (Server Admin)<br/>`50` (Query Admin)<br/>
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission
| `permvalue`   | string    | yes      | value of the permission
| `permnegated` | integer   | yes      |
| `permskip`    | integer   | yes      |

| Permission                               | Required for
|------------------------------------------|-------------
| b_permission_modify_power_ignore         | always

### servergroupautodelperm

Scopes: `manage`

Removes a specified permission from *all* regular server groups on all virtual servers. The target groups will be identified by the value of their i_group_auto_update_type permission specified with sgtype. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgtype`      | integer   | yes      | `10` (Channel Guest)<br/>`15` (Server Guest)<br/>`20` (Query Guest)<br/>`25` (Channel Voice)<br/>`30` (Server Normal)<br/>`35` (Channel Operator)<br/>`40` (Channel dmin)<br/>`45` (Server Admin)<br/>`50` (Query Admin)<br/>
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| b_permission_modify_power_ignore         | always

### servergroupclientlist

Scopes: `manage`

Returns the IDs of all clients currently residing in the server group specified with `sgid`. If you're using the optional `-names` option, the output will also contain the last known nickname and the unique identifier of the clients.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `-names`      | flag      | no       | include `client_nickname` and `client_unique_identifier`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_servergroup_client_list  | always

### servergroupcopy

Scopes: `manage`

Creates a copy of the channel group specified with `scgid`. If `tcgid` is set to `0`, the server will create a new group. To overwrite an existing group, simply set `tcgid` to the ID of a designated target group. If a target group is set, the name parameter will be ignored. The type parameter can be used to create template groups.
For detailed information, see Definitions.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `scgid`       | integer   | yes      | id of sorce server group
| `tcgid`       | integer   | yes      | id of target server group
| `name`        | string    | yes      | name of new server group
| `type`        | integer   | yes      | `0` (template)<br/>`1` (regular)<br/>`2` (query)


| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelgroup_create      | always
| i_group_modify_power                     | always

### servergroupdel

Scopes: `manage`

Deletes the server group specified with `sgid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `force`       | integer   | no       | when `1`, delete non empty server groups

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_servergroup_delete      | always

### servergroupdelclient

Scopes: `manage`

Removes a client specified with `cldbid` from the server group specified with `sgid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `cldbid`      | integer   | yes      | id of client in database

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_member_remove_power              | always

### servergroupdelperm

Scopes: `manage`

Removes a specified permission from the server group specified with
`sgid`. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always
  
### servergrouplist

Scopes: `manage`

Returns a list of server groups available.

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_servergroup_list         | always

### servergrouppermlist

Scopes: `manage`

Returns a list of permissions assigned to the server group specified with
`sgid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `-permsid`    | flag      | no       | include `permsid`, instead of `permid`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_servergroup_permission_list | always
| b_serverinstance_modify_querygroup       | when checking a query group
| b_serverinstance_modify_templates        | when checking a template group

### servergrouprename

Scopes: `manage`

Changes the name of the server group specified with `sgid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `sgid`        | integer   | yes      | id of server group
| `name`        | string    | yes      | new name of server group

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always

### servergroupsbyclientid

Scopes: `manage`

Returns all server groups the client specified with cldbid is currently residing in.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
