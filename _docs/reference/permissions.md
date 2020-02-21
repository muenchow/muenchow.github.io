---
title: Permissions
category: Reference
order: 1
---

### permfind

Scopes: `manage`, `write`, `read`

Displays detailed information about all assignments of the permission specified with `permid`. The output is similar to permoverview which includes the type and the id of client, channel or group associated with the permission. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_permission_find          | listing permission in virtual server
| b_serverinstance_permission_find         | listing permission in server instance

### permget

Scopes: `manage`, `write`, `read`

Displays the current value of the permission specified with `permid` or `permsid` for your own connection. This can be useful when you need to check your own privileges.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `permid`      | integer   | no       | id of permission
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_permissionoverview_own          | always

### permidgetbyname

Scopes: `manage`, `write`, `read`

Displays the database ID of one or more permissions specified by `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_permission_list         | always

### permissionlist

Scopes:`manage`, `write`, `read`

Displays a list of permissions available on the server instance including ID, name and description.

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_permission_list         | always

### permoverview

Scopes: `manage`, `write`, `read`

Displays all permissions assigned to a client for the channel specified with
`cid`. If `permid` is set to 0, all permissions will be displayed. A permission can be specified by `permid` or `permsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cid`         | integer   | yes      | id of channel
| `cldbid`      | integer   | yes      | id of client in database
| `permid`      | integer   | no       | id of permission;<br>when `0` all m permissions are returned
| `permsid`     | string    | no       | server id of permission

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_permissionoverview_view         | always

### permreset

Scopes: `manage`

Restores the default permission settings on the selected virtual server and creates a new initial administrator token.
Please note that in case of an error during the permreset call - e.g. when the database has been modified or corrupted - the virtual server will be deleted from the database.

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_permission_reset         | always

