---
title: Bans
category: Reference
order: 1
---

### banadd

Scopes: `manage`, `write`

Adds a new ban rule on the selected virtual server. All parameters are
optional but at least one of the following must be set: `ip`, `name`, `uid`, or `mytsid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `ip`          | string    | no       | regex matching the client ip
| `name`        | string    | no       | regex matching the client nickname
| `uid`         | integer   | no       | Uid of client
| `mytsid`      | string    | no       | myTS id of client
| `time`        | integer   | no       | time in seconds the ban will be active
| `banreason`   | string    | no       | text describing the reason
| `lastnickname`| string    | no       | 

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_ban_create                      | always

### banclient

Scopes: `manage`, `write`

Bans the client specified with the clid from the server. Please note that this will create two or three separate ban rules for the targeted clients IP address, his unique identifier and, if available, the mytsid.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `clid`        | integer   | yes      | id of client to be banned
| `time`        | integer   | no       | time in seconds the ban will be active
| `banreason`   | string    | no       | text describing the reason

| Permission                               | Required for
|------------------------------------------|-------------
| i_client_ban_power                       | always

### bandel

Scopes: `manage`, `write`

Deletes a ban rule.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `banid`       | integer   | yes      | id of ban to be deleted

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_ban_delete                      | deleting any ban
| b_client_ban_delete_own                  | deleting a ban created by the invoker

### bandelall

Scopes: `manage`, `write`

Deletes all active ban rules from the server.

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_ban_delete                      | always

### banlist

Scopes: `manage`, `write`, `read`

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `start`       | integer   | no       | skip the first `n` entries
| `duration`    | integer   | no       | only return `n` entries
| `-count`      | flag      | no       | also return the total number of entries

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_ban_list                        | always
