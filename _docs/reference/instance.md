---
title: Instance
category: Reference
order: 1
---

### bindinglist

Scopes: `manage`, `write`, `read`

Displays a list of IP addresses used by the server instance on multi-homed machines.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `subsystem`   | enum      | no       | `voice`, `query` or `filetransfer`; default `voice`

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_binding_list            | always

### gm

Scopes: `manage`, `write`

Sends a text message to all clients on all virtual servers in the TeamSpeak 3 Server instance.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `msg`         | Integer   | yes      | message

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_textmessage_send        | always

### hostinfo

Scopes: `manage`, `write`, `read`

Displays detailed connection information about the server instance including
uptime, number of virtual servers online, traffic information, etc.
For detailed information, see Server Instance Properties.

### instanceedit

Scopes: `manage`

Changes the server instance configuration using given properties.
For detailed information, see Server Instance Properties.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| ...           | ...       | ...      | ...

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_modify_settings         | always


### instanceinfo

Scopes: `manage`, `write`, `read`

Displays detailed connection information about the server instance including
uptime, number of virtual servers online, traffic information, etc.

For detailed information, see Server Instance Properties.

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_info_view               | always

### serverprocessstop

Scopes: `manage`

Stops the entire TeamSpeak 3 Server instance by shutting down the process. 

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `reasonmsg`   | string    | no       | text message that is sent to the clients before the client disconnects

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_stop                    | always

### version

Scopes: `manage`, `write`, `read`

Displays the servers version information including platform and build number.

### whoami

Scopes: `manage`, `write`, `read`

Displays information about your current ServerQuery connection including your loginname, etc.
