---
title: Snapshots
category: Reference
order: 1
---

### serversnapshotcreate

Scopes: `manage`

Return a snapshot of the selected virtual server containing all settings, groups and known client identities. The data from a server snapshot can be used to restore a virtual servers configuration, channels and permissions using the serversnapshotdeploy command.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `password`    | string    | no       | encrypt the snapshot using the supplied password

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_snapshot_create          | always

### serversnapshotdeploy

Scopes: `manage`

Restores the selected virtual servers configuration using the data from a previously created server snapshot. Please note that the TeamSpeak 3 Server does NOT check for necessary permissions while deploying a snapshot so the command could be abused to gain additional privileges. With `-keepfiles` set, the 

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `-mapping`    | flag      | no       | return a list that shows how channel id changed from backup to deployed server
| `-keepfiles`  | flag      | no       | channels that exist on the virtualserver and the backup will have there files preserved
| `password`    | string    | no       | decrypt the snapshot using the supplied password

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_snapshot_deploy          | always
