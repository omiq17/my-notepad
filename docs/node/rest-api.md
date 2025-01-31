---
layout: note
title: REST API Constraints
parent: Node
---

- Representational State Transfer Apllication Programming Interface.
- Rest api is a guideline (rather than a protocol). It uses HTTP protocol and applies some constraints on it.
- 6 constraints:

  - client-server separation
  - stateless
  - cacheable response
  - uniform interface
  - layered system
  - code on demand

- client-server separation: client and server should be separated. Client is defined as the machine that generates requests. Server can be defined as a machine that responses to those requests, request handler.
- stateless: server should need not know anything/ any state about client. Every request should be independent. Server treat each request as the first from client. We generally use token system here.
- cacheable: server should be explicitely lebel/say that the response is cacheable or not cacheable. For, cacheable response, server provides some sort of version number with its expiry. Client cached those response, it make new request if version gets expired and fetche new data.
- uniform interface: indentical communication system. Response should be same any request that comes from iPhone/tab/windows/android.
- layered system: client call to and endpoint of server-a, server-a call google-server, process data and provide response. Client do not need to bother about other servers/ underlying implementations.
- code on demand: optional constraint. Server can send response with codes like js code for execution on client side.

[lesson link](https://www.youtube.com/watch?v=IvHMM0huDZk)
