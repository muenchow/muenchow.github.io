---
title: Logs
category: Reference
order: 1
---

### logadd

Scopes: `manage`, `write`

Writes a custom entry into the servers log. Depending on your permissions, you'll be able to add entries into the server instance log and/or your virtual servers log. The loglevel parameter specifies the type of the entry.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `loglevel`    | integer   | yes      | `1` (error),<br>`2` (warning),<br> `3` (debug),<br>`4` (info)
| `logmsg`      | integer   | yes      | message to be logged

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_log_add                 | add log entry into the server instance
| b_virtualserver_log_add                  | add log entry into the virtual server

### logview

Scopes: `manage`, `write`, `read`

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `lines`       | integer   | no       | reduce the number of lines in response; Default `100`
| `reverse`     | integer   | no       | when `1`, reverse the order of lines in response
| `instance`    | integer   | no       | when `1`, return log from instance; otherwise from virtual server
| `begin_pos`   | integer   | no       | skip `n` number of lines

| Permission                               | Required for
|------------------------------------------|-------------
| b_serverinstance_log_view                | viewing server instance entries
| b_virtualserver_log_view                 | viewing virtual server entries
