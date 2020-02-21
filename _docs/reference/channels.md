---
title: Channels
category: Reference
order: 1
---

### channeladdperm

Scopes: `manage`

Adds a set of specified permissions to a channel.
Either `permid` or `permsid` must be set.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission
| `permvalue`   | string    | yes      | value of the permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### channelclientaddperm

Scopes: `manage`

Adds a set of specified permissions to a client in a specific channel.
Either `permid` or `permsid` must be set.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `cldbid`      | integer   | yes      | id of client
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission
| `permvalue`   | string    | yes      | value of the permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### channelclientdelperm

Scopes: `manage`

Removes a set of specified permissions from a client in a specific channel.
Either `permid` or `permsid` must be set.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `cldbid`      | integer   | yes      | id of client
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### channelclientpermlist

Scopes: `manage`, `write`, `read`

Displays a list of permissions defined for a client in a specific channel.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `cldbid`      | integer   | yes      | id of client
| `-permsid`    | flag      | no       | include `permsid`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channelclient_permission_list | always


### channelcreate

Scopes: `manage`, `write`

Creates a new channel using the given properties and displays its ID.
Note that this command accepts multiple properties which means that you're able to specifiy all settings of the new channel at once. For detailed information, see Channel Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `channel_name`| string    | yes      | Name of the channel

| Permission                               | Required for
|------------------------------------------|-------------
| i_channel_min_depth                      |
| i_channel_max_depth                      |
| b_channel_create_child                   |
| b_channel_create_permanent               |
| b_channel_create_semi_permanent          |
| b_channel_create_temporary               |
| b_channel_create_with_topic              |
| b_channel_create_with_description        |
| b_channel_create_with_password           |
| b_channel_create_with_banner             | 
| i_channel_create_modify_with_codec_maxquality |
| i_channel_create_modify_with_codec_latency_factor_min |
| b_channel_create_with_maxclients         |
| b_channel_create_with_maxfamilyclients   |
| b_channel_create_with_sortorder          |
| b_channel_create_with_default            |
| b_channel_create_with_needed_talk_power  |

### channeldelete

Scopes: `manage`, `write`

Deletes an existing channel by ID.
If force is set to 1, the channel will be deleted even if there are clients within. The clients will be kicked to the default channel with an appropriate reason message.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `force`       | integer   | no       |

| Permission                               | Required for
|------------------------------------------|-------------
| b_channel_delete_permanent               | deleting a permanent channel
| b_channel_delete_semi_permanent          | deleting a semi permanent channel
| b_channel_delete_temporary               | deleting a temporary channel
| b_channel_delete_flag_force              | force deleting a channel

### channeldelperm

Scopes: `manage`

Removes a specified permission from a channel.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| i_group_modify_power                     | always
| i_permission_modify_power                | always

### channeledit

Scopes: `manage`, `write`

Changes a channels configuration using given properties. Note that this
command accepts multiple properties which means that you're able to change
all settings of the channel specified with cid at once.
For detailed information, see Channel Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| ...           | ...       | ...      | ...

| Permission                               | Required for
|------------------------------------------|-------------
| i_channel_min_depth                      |
| i_channel_max_depth                      |
| b_channel_modify_parent                  |
| b_channel_modify_make_default            |
| b_channel_modify_make_permanent          |
| b_channel_modify_make_semi_permanent     |
| b_channel_modify_make_temporary          |
| b_channel_modify_name                    |
| b_channel_modify_topic                   |
| b_channel_modify_description             |
| b_channel_modify_password                |
| b_channel_modify_banner                  |
| b_channel_modify_codec                   |
| b_channel_modify_codec_quality           |
| b_channel_create_modify_with_codec_maxquality |
| b_channel_modify_codec_latency_factor    |
| b_channel_modify_make_codec_encrypted    |
| b_channel_modify_maxclients              |
| b_channel_modify_maxfamilyclients        |
| b_channel_modify_sortorder               |
| b_channel_modify_needed_talk_power       |
| i_channel_modify_power                   |
| i_channel_needed_modify_power            |

### channelfind

Scopes: `manage`, `write`, `read`

Displays a list of channels matching a given name pattern.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `pattern`     | string    | yes      | pattern must be part of the channels name (case insensitive)

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channel_search           | always

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


### channelinfo

Scopes: `manage`, `write`, `read`

Returns detailed configuration information about a channel including ID, topic, description, etc.
For detailed information, see Channel Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel

| Permission                               | Required for
|------------------------------------------|-------------
| b_channel_info_view                      | always

### channellist

Scopes: `manage`, `write`, `read`
 
Returns a list of channels created on a virtual server including their ID, order, name, etc.

| parameter     | type      | required | description
|---------------|-----------|----------|------------
| `-topic`      | flag      | no       | include `channel_topic`
| `-flags`      | flag      | no       | include `channel_flag_default`, `channel_flag_password`, `channel_flag_permanent` and `channel_flag_semi_permanent`
| `-voice`      | flag      | no       | include `channel_codec`, `channel_codec_quality` and `channel_needed_talk_power`
| `-limits`     | flag      | no       | include `total_clients_family`
| `-icon`       | flag      | no       | include `channel_icon_id`
| `-secondsempty` | flag      | no       | include `seconds_empty`
| `-banners`    | flag      | no       | include `channel_banner_gfx_url` and `channel_banner_mode`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channel_list             | always

### channelmove

Scopes: `manage`, `write`

Moves a channel to a new parent channel with the ID `cpid`. If `order` is
specified, the channel will be sorted right under the channel with the
specified ID. If `order` is set to `0`, the channel will be sorted right below
the new parent.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `cpid`        | integer   | yes      | id of parent channel
| `order`       | integer   | no       | id of upper sibling channel 

| Permission                               | Required for
|------------------------------------------|-------------
| i_channel_min_depth                      | always
| i_channel_max_depth                      | always
| b_channel_modify_parent                  | always
| b_channel_modify_sortorder               | always

### channelpermlist

Scopes: `manage`, `write`, `read`

Return a list of permissions defined for a channel.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `-permsid`    | flag      | no       | include `permsid`

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_channel_permission_list  |
