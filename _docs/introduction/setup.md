---
title: Setup
category: Introduction
order: 1
---

WebQuery is disabled per default, and must be enabled using a command switch when starting up the ts3server. For that the `query_protocols` parameter must be made to include `http`. For example via `./ts3server_minimal_runscript.sh query_protocols=raw,ssh,http` that will start `http` in addition to `raw` and `ssh` that are enabled per default.

### Getting an API-Key

#### New Server

When starting a brand new ts3server, a API-Key is being created for the server admin. Look for
```
------------------------------------------------------------------
                      I M P O R T A N T                           
------------------------------------------------------------------
               Server Query Admin Account created                 
         loginname= "serveradmin", password= "NNbz7d20"
         apikey= "BADW79srwjTzm1sdkCYeoLB0DQtGiV6QW8Fjb1u"
------------------------------------------------------------------
```
with the api-key being `BADW79srwjTzm1sdkCYeoLB0DQtGiV6QW8Fjb1u`

#### Existing Server

With an existing ts3server api-keys must be created manually. For you must access the query system using either `raw`(telnet) or `ssh`, and run the command `apikeyadd scope=manage lifetime=0`. For example:

```
TS3
Welcome to the TeamSpeak 3 ServerQuery interface, type "help" for a list of commands and "help <command>" for information on a specific command.
login serveradmin NNbz7d20
error id=0 msg=ok
apikeyadd scope=manage lifetime=0
apikey=BADW79srwjTzm1sdkCYeoLB0DQtGiV6QW8Fjb1u id=1 sid=0 cldbid=1 scope=manage time_left=unlimited created_at=1581921236 expires_at=1581921236
error id=0 msg=ok
```
with the api-key being `BADW79srwjTzm1sdkCYeoLB0DQtGiV6QW8Fjb1u`

### Testing

When having a running ts3server with WebQuery running on the default port can be tested using `curl` and `jq`. For example:

```shell
$ curl -sH 'x-api-key: BADW79srwjTzm1sdkCYeoLB0DQtGiV6QW8Fjb1u' http://127.0.0.1:10080/version | jq
{
  "body": [
    {
      "build": "1582105527",
      "platform": "Linux",
      "version": "3.12.0-beta.1"
    }
  ],
  "status": {
    "code": 0,
    "message": "ok"
  }
}
```