---
title: Scopes
category: Introduction
order: 3
---

Every API key has a scope that limits what commands can be performed with this api key. There are three different possible values for scope: `manage`, `write` and `read`.

| Command                        | Available in              |
|--------------------------------|---------------------------|
| [apikeyadd]                    | `manage`                  |
| [apikeydel]                    | `manage`                  |
| [apikeylist]                   | `manage`                  |
| [banadd]                       | `manage`, `write`         |
| [banclient]                    | `manage`, `write`         |
| [bandel]                       | `manage`, `write`         |
| [bandelall]                    | `manage`, `write`         |
| [banlist]                      | `manage`, `write`, `read` |
| [bindinglist]                  | `manage`, `write`, `read` |
| [channeladdperm]               | `manage`                  |
| [channelclientaddperm]         | `manage`                  |
| [channelclientdelperm]         | `manage`                  |
| [channelclientpermlist]        | `manage`, `write`, `read` |
| [channelcreate]                | `manage`, `write`         |
| [channeldelete]                | `manage`, `write`         |
| [channeldelperm]               | `manage`                  |
| [channeledit]                  | `manage`, `write`         |
| [channelfind]                  | `manage`, `write`, `read` |
| [channelgroupadd]              | `manage`, `write`         |
| [channelgroupaddperm]          | `manage`                  |
| [channelgroupclientlist]       | `manage`, `write`, `read` |
| [channelgroupcopy]             | `manage`                  |
| [channelgroupdel]              | `manage`                  |
| [channelgroupdelperm]          | `manage`                  |
| [channelgrouplist]             | `manage`, `write`, `read` |
| [channelgrouppermlist]         | `manage`, `write`, `read` |
| [channelgrouprename]           | `manage`                  |
| [channelinfo]                  | `manage`, `write`, `read` |
| [channellist]                  | `manage`, `write`, `read` |
| [channelmove]                  | `manage`, `write`         |
| [channelpermlist]              | `manage`, `write`, `read` |
| [clientaddperm]                | `manage`                  |
| [clientdbdelete]               | `manage`, `write`         |
| [clientdbedit]                 | `manage`, `write`         |
| [clientdbfind]                 | `manage`, `write`, `read` |
| [clientdbinfo]                 | `manage`, `write`, `read` |
| [clientdblist]                 | `manage`, `write`, `read` |
| [clientdelperm]                | `manage`                  |
| [clientedit]                   | `manage`, `write`         |
| [clientfind]                   | `manage`, `write`, `read` |
| [clientgetdbidfromuid]         | `manage`, `write`, `read` |
| [clientgetids]                 | `manage`, `write`, `read` |
| [clientgetnamefromdbid]        | `manage`, `write`, `read` |
| [clientgetnamefromuid]         | `manage`, `write`, `read` |
| [clientgetuidfromclid]         | `manage`, `write`, `read` |
| [clientinfo]                   | `manage`, `write`, `read` |
| [clientkick]                   | `manage`, `write`         |
| [clientlist]                   | `manage`, `write`, `read` |
| [clientmove]                   | `manage`, `write`         |
| [clientpermlist]               | `manage`, `write`, `read` |
| [clientpoke]                   | `manage`, `write`         |
| [clientsetserverquerylogin]    | `manage`, `write`         |
| [clientupdate]                 | `manage`, `write`         |
| [complainadd]                  | `manage`, `write`         |
| [complaindel]                  | `manage`, `write`         |
| [complaindelall]               | `manage`, `write`         |
| [complainlist]                 | `manage`, `write`, `read` |
| [custominfo]                   | `manage`, `write`, `read` |
| [customsearch]                 | `manage`, `write`, `read` |
| [customset]                    | `manage`, `write`         |
| [customdelete]                 | `manage`, `write`         |
| [gm]                           | `manage`                  |
| [hostinfo]                     | `manage`, `write`, `read` |
| [instanceedit]                 | `manage`                  |
| [instanceinfo]                 | `manage`, `write`, `read` |
| [logadd]                       | `manage`, `write`         |
| [logview]                      | `manage`, `write`, `read` |
| [messageadd]                   | `manage`, `write`         |
| [messagedel]                   | `manage`, `write`         |
| [messageget]                   | `manage`, `write`, `read` |
| [messagelist]                  | `manage`, `write`, `read` |
| [messageupdateflag]            | `manage`, `write`         |
| [permfind]                     | `manage`, `write`, `read` |
| [permget]                      | `manage`, `write`, `read` |
| [permidgetbyname]              | `manage`, `write`, `read` |
| [permissionlist]               | `manage`, `write`, `read` |
| [permoverview]                 | `manage`, `write`, `read` |
| [permreset]                    | `manage`                  |
| [privilegekeyadd]              | `manage`, `write`         |
| [privilegekeydelete]           | `manage`, `write`         |
| [privilegekeylist]             | `manage`, `write`, `read` |
| [privilegekeyuse]              | `manage`, `write`         |
| [queryloginadd]                | `manage`, `write`         |
| [querylogindel]                | `manage`, `write`         |
| [queryloginlist]               | `manage`, `write`, `read` |
| [sendtextmessage]              | `manage`, `write`         |
| [servercreate]                 | `manage`                  |
| [serverdelete]                 | `manage`                  |
| [serveredit]                   | `manage`, `write`         |
| [servergroupadd]               | `manage`                  |
| [servergroupaddclient]         | `manage`                  |
| [servergroupaddperm]           | `manage`                  |
| [servergroupautoaddperm]       | `manage`                  |
| [servergroupautodelperm]       | `manage`                  |
| [servergroupclientlist]        | `manage`                  |
| [servergroupcopy]              | `manage`                  |
| [servergroupdel]               | `manage`                  |
| [servergroupdelclient]         | `manage`                  |
| [servergroupdelperm]           | `manage`                  |
| [servergrouplist]              | `manage`                  |
| [servergrouppermlist]          | `manage`                  |
| [servergrouprename]            | `manage`                  |
| [servergroupsbyclientid]       | `manage`                  |
| [serveridgetbyport]            | `manage`                  |
| [serverinfo]                   | `manage`                  |
| [serverlist]                   | `manage`                  |
| [serverprocessstop]            | `manage`                  |
| [serverrequestconnectioninfo]  | `manage`, `write`, `read` |
| [serversnapshotcreate]         | `manage`                  |
| [serversnapshotdeploy]         | `manage`                  |
| [serverstart]                  | `manage`                  |
| [serverstop]                   | `manage`                  |
| [servertemppasswordadd]        | `manage`, `write`         |
| [servertemppassworddel]        | `manage`, `write`         |
| [servertemppasswordlist]       | `manage`, `write`, `read` |
| [setclientchannelgroup]        | `manage`, `write`         |
| [version]                      | `manage`, `write`, `read` |
| [whoami]                       | `manage`, `write`, `read` |

[apikeyadd]: {% link _docs/reference/api-keys.md %}#apikeyadd
[apikeydel]: {% link _docs/reference/api-keys.md %}#apikeydel
[apikeylist]: {% link _docs/reference/api-keys.md %}#apikeylist
[banadd]: {% link _docs/reference/bans.md %}#banadd
[banclient]: {% link _docs/reference/bans.md %}#banclient
[bandel]: {% link _docs/reference/bans.md %}#bandel
[bandelall]: {% link _docs/reference/bans.md %}#bandelall
[banlist]: {% link _docs/reference/bans.md %}#banlist
[bindinglist]: {% link _docs/reference/instance.md %}#bindinglist
[channeladdperm]: {% link _docs/reference/channels.md %}#channeladdperm
[channelclientaddperm]: {% link _docs/reference/channels.md %}#channelclientaddperm
[channelclientdelperm]: {% link _docs/reference/channels.md %}#channelclientdelperm
[channelclientpermlist]: {% link _docs/reference/channels.md %}#channelclientpermlist
[channelcreate]: {% link _docs/reference/channels.md %}#channelcreate
[channeldelete]: {% link _docs/reference/channels.md %}#channeldelete
[channeldelperm]: {% link _docs/reference/channels.md %}#channeldelperm
[channeledit]: {% link _docs/reference/channels.md %}#channeledit
[channelfind]: {% link _docs/reference/channels.md %}#channelfind
[channelgroupadd]: {% link _docs/reference/channel-groups.md %}#channelgroupadd
[channelgroupaddperm]: {% link _docs/reference/channel-groups.md %}#channelgroupaddperm
[channelgroupclientlist]: {% link _docs/reference/channel-groups.md %}#channelgroupclientlist
[channelgroupcopy]: {% link _docs/reference/channel-groups.md %}#channelgroupcopy
[channelgroupdel]: {% link _docs/reference/channel-groups.md %}#channelgroupdel
[channelgroupdelperm]: {% link _docs/reference/channel-groups.md %}#channelgroupdelperm
[channelgrouplist]: {% link _docs/reference/channel-groups.md %}#channelgrouplist
[channelgrouppermlist]: {% link _docs/reference/channel-groups.md %}#channelgrouppermlist
[channelgrouprename]: {% link _docs/reference/channel-groups.md %}#channelgrouprename
[channelinfo]: {% link _docs/reference/channels.md %}#channelinfo
[channellist]: {% link _docs/reference/channels.md %}#channellist
[channelmove]: {% link _docs/reference/channels.md %}#channelmove
[channelpermlist]: {% link _docs/reference/channels.md %}#channelpermlist
[clientaddperm]: {% link _docs/reference/clients.md %}#clientaddperm
[clientdbdelete]: {% link _docs/reference/clients.md %}#clientdbdelete
[clientdbedit]: {% link _docs/reference/clients.md %}#clientdbedit
[clientdbfind]: {% link _docs/reference/clients.md %}#clientdbfind
[clientdbinfo]: {% link _docs/reference/clients.md %}#clientdbinfo
[clientdblist]: {% link _docs/reference/clients.md %}#clientdblist
[clientdelperm]: {% link _docs/reference/clients.md %}#clientdelperm
[clientedit]: {% link _docs/reference/clients.md %}#clientedit
[clientfind]: {% link _docs/reference/clients.md %}#clientfind
[clientgetdbidfromuid]: {% link _docs/reference/clients.md %}#clientgetdbidfromuid
[clientgetids]: {% link _docs/reference/clients.md %}#clientgetids
[clientgetnamefromdbid]: {% link _docs/reference/clients.md %}#clientgetnamefromdbid
[clientgetnamefromuid]: {% link _docs/reference/clients.md %}#clientgetnamefromuid
[clientgetuidfromclid]: {% link _docs/reference/clients.md %}#clientgetuidfromclid
[clientinfo]: {% link _docs/reference/clients.md %}#clientinfo
[clientkick]: {% link _docs/reference/clients.md %}#clientkick
[clientlist]: {% link _docs/reference/clients.md %}#clientlist
[clientmove]: {% link _docs/reference/clients.md %}#clientmove
[clientpermlist]: {% link _docs/reference/clients.md %}#clientpermlist
[clientpoke]: {% link _docs/reference/clients.md %}#clientpoke
[clientsetserverquerylogin]: {% link _docs/reference/clients.md %}#clientsetserverquerylogin
[clientupdate]: {% link _docs/reference/clients.md %}#clientupdate
[complainadd]: {% link _docs/reference/complains.md %}#complainadd
[complaindel]: {% link _docs/reference/complains.md %}#complaindel
[complaindelall]: {% link _docs/reference/complains.md %}#complaindelall
[complainlist]: {% link _docs/reference/complains.md %}#complainlist
[custominfo]: {% link _docs/reference/privilegekeys.md %}#custominfo
[customsearch]: {% link _docs/reference/privilegekeys.md %}#customsearch
[customset]: {% link _docs/reference/privilegekeys.md %}#customset
[customdelete]: {% link _docs/reference/privilegekeys.md %}#customdelete
[gm]: {% link _docs/reference/instance.md %}#gm
[hostinfo]: {% link _docs/reference/instance.md %}#hostinfo
[instanceedit]: {% link _docs/reference/instance.md %}#instanceedit
[instanceinfo]: {% link _docs/reference/instance.md %}#instanceinfo
[logadd]: {% link _docs/reference/logs.md %}#logadd
[logview]: {% link _docs/reference/logs.md %}#logview
[messageadd]: {% link _docs/reference/offline-messages.md %}#messageadd
[messagedel]: {% link _docs/reference/offline-messages.md %}#messagedel
[messageget]: {% link _docs/reference/offline-messages.md %}#messageget
[messagelist]: {% link _docs/reference/offline-messages.md %}#messagelist
[messageupdateflag]: {% link _docs/reference/offline-messages.md %}#messageupdateflag
[permfind]: {% link _docs/reference/permissions.md %}#permfind
[permget]: {% link _docs/reference/permissions.md %}#permget
[permidgetbyname]: {% link _docs/reference/permissions.md %}#permidgetbyname
[permissionlist]: {% link _docs/reference/permissions.md %}#permissionlist
[permoverview]: {% link _docs/reference/permissions.md %}#permoverview
[permreset]: {% link _docs/reference/permissions.md %}#permreset
[privilegekeyadd]: {% link _docs/reference/privilegekeys.md %}#privilegekeyadd
[privilegekeydelete]: {% link _docs/reference/privilegekeys.md %}#privilegekeydelete
[privilegekeylist]: {% link _docs/reference/privilegekeys.md %}#privilegekeylist
[privilegekeyuse]: {% link _docs/reference/privilegekeys.md %}#privilegekeyuse
[queryloginadd]: {% link _docs/reference/query-logins.md %}#queryloginadd
[querylogindel]: {% link _docs/reference/query-logins.md %}#querylogindel
[queryloginlist]: {% link _docs/reference/query-logins.md %}#queryloginlist
[sendtextmessage]: {% link _docs/reference/servers.md %}#sendtextmessage
[servercreate]: {% link _docs/reference/servers.md %}#servercreate
[serverdelete]: {% link _docs/reference/servers.md %}#serverdelete
[serveredit]: {% link _docs/reference/servers.md %}#serveredit
[servergroupadd]: {% link _docs/reference/server-groups.md %}#servergroupadd
[servergroupaddclient]: {% link _docs/reference/server-groups.md %}#servergroupaddclient
[servergroupaddperm]: {% link _docs/reference/server-groups.md %}#servergroupaddperm
[servergroupautoaddperm]: {% link _docs/reference/server-groups.md %}#servergroupautoaddperm
[servergroupautodelperm]: {% link _docs/reference/server-groups.md %}#servergroupautodelperm
[servergroupclientlist]: {% link _docs/reference/server-groups.md %}#servergroupclientlist
[servergroupcopy]: {% link _docs/reference/server-groups.md %}#servergroupcopy
[servergroupdel]: {% link _docs/reference/server-groups.md %}#servergroupdel
[servergroupdelclient]: {% link _docs/reference/server-groups.md %}#servergroupdelclient
[servergroupdelperm]: {% link _docs/reference/server-groups.md %}#servergroupdelperm
[servergrouplist]: {% link _docs/reference/server-groups.md %}#servergrouplist
[servergrouppermlist]: {% link _docs/reference/server-groups.md %}#servergrouppermlist
[servergrouprename]: {% link _docs/reference/server-groups.md %}#servergrouprename
[servergroupsbyclientid]: {% link _docs/reference/server-groups.md %}#servergroupsbyclientid
[serveridgetbyport]: {% link _docs/reference/servers.md %}#serveridgetbyport
[serverinfo]: {% link _docs/reference/servers.md %}#serverinfo
[serverlist]: {% link _docs/reference/servers.md %}#serverlist
[serverprocessstop]: {% link _docs/reference/instance.md %}#serverprocessstop
[serverrequestconnectioninfo]: {% link _docs/reference/servers.md %}#serverrequestconnectioninfo
[serversnapshotcreate]: {% link _docs/reference/snapshots.md %}#serversnapshotcreate
[serversnapshotdeploy]: {% link _docs/reference/snapshots.md %}#serversnapshotdeploy
[serverstart]: {% link _docs/reference/servers.md %}#serverstart
[serverstop]: {% link _docs/reference/servers.md %}#serverstop
[servertemppasswordadd]: {% link _docs/reference/servers.md %}#servertemppasswordadd
[servertemppassworddel]: {% link _docs/reference/servers.md %}#servertemppassworddel
[servertemppasswordlist]: {% link _docs/reference/servers.md %}#servertemppasswordlist
[setclientchannelgroup]: {% link _docs/reference/clients.md %}#setclientchannelgroup
[version]: {% link _docs/reference/instance.md %}#version
[whoami]: {% link _docs/reference/instance.md %}#whoami
