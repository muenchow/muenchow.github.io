---
title: Query Logins
category: Reference
order: 1
---

### queryloginadd

Scopes: `manage`, `write`

Adds a new query client login, or enables query login for existing clients. When no virtual server has been selected, the command will create global query logins.  Otherwise the command enables query login for existing client, and cldbid must be specified.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `client_login_name` | string    | yes      | requested login name
| `cldbid`      | integer   | no       | id of client  in the database<br>Defaults to invoker

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverquery_login_create               | always

### querylogindel

Scopes: `manage`, `write`

Deletes an existing server query login on selected server. When no virtual server has been selected, deletes global query logins instead. 

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | no       | id of client  in the database

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverquery_login_delete               | always

### queryloginlist

Scopes: `manage`, `write`, `read`

List existing query client logins. The pattern parameter can include regular characters and SQL wildcard characters (e.g. %). Only displays query logins of the selected virtual server, or all query logins when no virtual server have been selected.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `pattern`     | string    | no       | matches the value, allowing for sql style pattern matching
| `start`       | integer   | no       | skip the first `n` entries
| `duration`    | integer   | no       | only return `n` entries
| `-count`      | flag      | no       | also return the total number of entries

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverquery_login_list                 | always
