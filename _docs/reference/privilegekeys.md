---
title: Privilege-Keys
category: Reference
order: 1
---

### privilegekeyadd

Scopes: `manage`, `write`

Create a new token. If `tokentype` is set to `0`, the ID specified with `tokenid1` will be a server group ID. Otherwise, `tokenid1` is used as a channel group ID and you need to provide a valid channel ID using `tokenid2`.
The `tokencustomset` parameter allows you to specify a set of custom client properties. This feature can be used when generating tokens to combine a website account database with a TeamSpeak user. The syntax of the value needs to follow the general syntax of:
`ident=ident1 value=value1|ident=ident2 value=value2|ident=ident3 value=value3`

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `tokentype`   | integer   | yes      | `0` or `1`
| `tokenid1`    | integer   | yes      | see description
| `tokenid2`    | integer   | yes      | see description
| `tokencustomset` | string    | no       | see description
| `tokendescription` | string    |  no       | free text describing the token
       
| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_token_add                | always
| i_group_member_add_power                 | always

### privilegekeydelete

Scopes: `manage`, `write`

Deletes an existing token matching the token key specified with token.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `token`       | string    | yes      | token to be deleted

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_token_delete             | always

### privilegekeylist

Scopes: `manage`, `write`, `read`

Displays a list of privilege keys available including their type and group IDs. Tokens can be used to gain access to specified server or channel groups. A privilege key is similar to a client with administrator privileges that adds you to a certain permission group, but without the necessity of a such a client with administrator privileges to actually exist. It is a long (random looking) string that can be used as a ticket into a specific server group.

| Permission                               | Required for
|------------------------------------------|-------------
|   b_virtualserver_token_list             | always

### privilegekeyuse

Scopes: `manage`, `write`

Use a token key gain access to a server or channel group. Please note that the server will automatically deletes the token after it has been used.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| token         | string    | yes      | the token to be used

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_token_use                | always

### custominfo

Scopes: `manage`, `write`, `read`

Displays a list of custom properties for the client specified with `cldbid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | if of client in database

### customsearch

Scopes: `manage`, `write`, `read`

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `ident`       | string    | yes      | identifier
| `pattern`     | string    | yes      | matches the value, allowing for sql style pattern matching

### customset

Scopes: `manage`, `write`

Creates or updates a custom property for client specified by the `cldbid`. `ident` and `value` can be any value, and are the key value pair of the custom property.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `ident`       | string    | yes      | identifier
| `value`       | string    | yes      | value

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_modify_dbproperties             | always

### customdelete

Scopes: `manage`, `write`

Removes a custom property from a client specified by the `cldbid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | yes      | id of client in database
| `ident`       | string    | yes      | identifier

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_delete_dbproperties             | always
