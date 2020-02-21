---
title: Complains
category: Reference
order: 1
---

### complainadd

Scopes: `manage`, `write`

Submits a complaint about a connected client with database ID `tcldbid` to the server.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `tcldbid`     | integer   | yes      | id of client in database
| `message`     | string    | yes      | complain text

| Permission                               | Required for
|------------------------------------------|-------------
| i_client_complain_power                  | always

### complaindel

Scopes: `manage`, `write`

Deletes the complaint about the client with ID `tcldbid` submitted by the client with ID `fcldbid` from the server.
  
| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `tcldbid`     | integer   | yes      | id if client in database, who was complained about
| `fcldbid`     | integer   | yes      | id if client in database, who complained

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_complain_delete                 | deleting complains from any client
| b_client_complain_delete_own             | deleting complains created by invoker

### complaindelall

Scopes: `manage`, `write`

Deletes all complaints about the client with database ID `tcldbid` from the
server.
  
| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `tcldbid`     | integer   | yes      | id if client in database, who was complained about

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_complain_delete                 | always

### complainlist

Scopes: `manage`, `write`, `read`

Displays a list of complaints on the selected virtual server. If `tcldbid` is specified, only complaints about the targeted client will be shown.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `tcldbid`     | integer   | no      | id if client in database, who was complained about

| Permission                               | Required for
|------------------------------------------|-------------
| b_client_complain_list                   | always
