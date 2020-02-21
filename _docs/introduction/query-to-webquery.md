---
title: Query to WebQuery
category: Introduction
order: 2
---

Nearly everything that can be done with 'normal' query session, can also be done with WebQuery. For that we mapped the our query syntax to json.
The format of an uri for a request, in WebQuery, must be either `/<command>?<arguments>` or `/<virtual server id>/<command>?<arguments>`. The difference being the leading `virtual server id`. If no `virtual server id` is send with a request, then the virtual server of the also supplied api-key will be used. Arguments to a command are send using either uri parameters, or when using POST uploaded in a json object. The Reply contains the full response generate by the server, with the error-line being handled individually. If additional lines of  response have been send along with the error-line, then they are converted into objects in the body-part of the response.

### GET

A request can is easily converted into GET request, as long as they are not either rather long and don't use `|`. If either or both is required a POST request must be used.
The required API key, needed to authenticate the request, can be send either as a http header(`x-api-key`) or as a uri parameter(`api-key`). All other uri parameters are interpreted as arguments for the commands first section.

> `channellist -topic -icon`
> becomes
> ```shell
> $ curl -H 'x-api-key: BAByFoiEXZfnSJyE6dbXFiW_nn_SdwkclpKNz9j' 'http://127.0.0.1:10080/1/channellist?-topic&-icon'
> ```

### POST

When using POST instead of GET all the features or a normal request remain available in addition it becomes possible to send the parameters as json object(s). The syntax is identical to the body-part of a response.

> `channellist -topic -icon`
> becomes
> ```shell
> $ curl -X POST -d '{ "-topic": "", "-icon": "" }' 'http://127.0.0.1:10080/1/channellist?api-key=BAByFoiEXZfnSJyE6dbXFiW_nn_SdwkclpKNz9j'
> ```

Additionally using POST it is possible to send commands that are using sections (`|`). For that instead of json object a whole array of them are send.

> `clientinfo clid=1|clid=2|clid=3|clid=4`
> becomes
> ```shell
> $ curl -X POST -d '[ { "clid": "1" }, { "clid": "2" }, { "clid": "3" }, { "clid": "4" } ]' 'http://127.0.0.1:10080/1/clientinfo?api-key=BAByFoiEXZfnSJyE6dbXFiW_nn_SdwkclpKNz9j'
> ```
