---
title: Offline Messages
category: Reference
order: 1
---

### messageadd

Scopes: `manage`, `write`

Sends an offline message to the client specified by cluid.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cluid`       | integer   | yes      | id of client
| `subject`     | string    | yes      | subject line
| `message`     | string    | yes      | message text

### messagedel

Scopes: `manage`, `write`

Deletes an existing offline message with ID `msgid` from your inbox.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `msgid`       | integer   | yes      | id of message

### messageget

Scopes: `manage`, `write`, `read`

Displays an existing offline message with ID `msgid` from your inbox. Please note that this does not automatically set the flag_read property of the message.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `msgid`       | integer   | yes      | id of message

### messagelist

Scopes: `manage`, `write`, `read`

Displays a list of offline messages you've received. The output contains the senders unique identifier, the messages subject, etc.

### messageupdateflag

Scopes: `manage`, `write`

Updates the flag_read property of the offline message specified with `msgid`.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `msgid`       | integer   | yes      | id of message
| `flag`        | integer   | yes      | when `1`, mark as read; otherwise unread
