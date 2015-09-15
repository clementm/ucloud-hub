**Phoenixd**
===========


A new protocol and server/client implementation to optimize p2p file sharing in a small scale network.

----------


Features
----------

- Sharing "in the cloud" : files are aggregated into a time-persistent multimedia library allowing video and audio streaming

- Optimized sharing : chunks of data are distributed among the peers to improve the availability of the most wanted files


Protocol Specifications
---------------------------
### Introduction 

A phoenix query is introduced by the character `$`, and has three different parts :

> **Example query :**
> `$iinf server_core:phoenix|server_version:0.0.1`  
>  *This is sent by the hub on a new connection : it gives to the client informations about the hub he is connecting to*

- The first letter (`i`) identifies the recipient of the query :

| Letter  | Meaning   | Description      
| ------- | --------- | -------------
| h       | hub       | a message intended to the hub only
| i       | info      | sent by the hub to a client
| b       | broadcast | sent by a client to the hub to be broadcasted to all connected peers (depending on the query, it will be first analysed by the hub
| d       | direct    | a message sent by a client to a specific peer


- The three following letters (`inf`) identify the query

- Arguments for the query are made of `key:value` pairs seperated by a `|`. Keys are made of alphanumerical characters and `_` only, and are case sensitive. Values can contain any `utf-8` character except `|`, `$` and newline `\n`.
