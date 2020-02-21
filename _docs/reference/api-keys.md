---
title: API keys
category: Reference
order: 1
---

### apikeyadd

Scopes: `manage`

Creates a new api-key using the specified scope, for the invoking user.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `scope`       | enum      | yes      | `manage`, `write` or `read`
| `lifetime`    | integer   | no       | lifetime of the token in days; default `14`, `0` means unlimited
| `cldbid`      | integer   | no       | id of owner; Default is invoker

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_apikey_add               | always
| b_virtualserver_apikey_manage            | using `cldbid`

#### Example

```http
GET /apikeyadd?scope=manage&lifetime=2 HTTP/1.1
```

```json
{
  "body": [
    {
      "apikey": "BACZ2Me9WOIhZjPn0_sWXjgkfOG-b5ypHIGbZ_b",
      "cldbid": "1",
      "created_at": "1581503621",
      "expires_at": "1581676421",
      "id": "3",
      "scope": "manage",
      "sid": "0",
      "time_left": "172799"
    }
  ],
  "status": {
    "code": 0,
    "message": "ok"
  }
}
```

### apikeydel

Scopes: `manage`

Delete an apikey.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `id`          | integer   | yes      | Id of API key to be deleted

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_apikey_manage            | deleting API keys of other clients

#### Example

```http
GET /apikeydel?id=3 HTTP/1.1
```

```json
{
  "status": {
    "code": 0,
    "message": "ok"
  }
}
```

### apikeylist

Scopes: `manage`

Lists API keys.

| Parameter     | Type      | Required | Description
|---------------|-----------|----------|------------
| `cldbid`      | integer   | no       | list the API keys of the client; Defaults to invoker,<br/>`*` to list API keys of all clients
| `start`       | integer   | no       | skip the first `n` entries
| `duration`    | integer   | no       | only return `n` entries
| `-count`      | flag      | no       | also return the total number of entries

| Permission                               | Required for
|------------------------------------------|-------------
| b_virtualserver_apikey_manage            | listing the keys of other clients


#### Example

```http
GET /apikeylist HTTP/1.1
```

```json
{
  "body": [
    {
      "cldbid": "1",
      "created_at": "1581413558",
      "expires_at": "1581413558",
      "id": "1",
      "scope": "manage",
      "sid": "0",
      "time_left": "unlimited"
    },
    {
      "cldbid": "7",
      "created_at": "1581502164",
      "expires_at": "1582711764",
      "id": "2",
      "scope": "read",
      "sid": "1",
      "time_left": "1206525"
    }
  ],
  "status": {
    "code": 0,
    "message": "ok"
  }
}
```
