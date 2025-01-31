---
layout: note
title: Node.js Architecture
parent: Node
---

Nodes.js is runtime environment, built on V8 engine, that includes everything we need to execute a program written in JS on server-side.

V8 engine: built on C/C++, by Google, open souce. Converts JS code to machine code using JIT (Just In Time) compiler.

V8 + Node bindings + Thread pool + Event loop = Node.js

LibUv: Library, handles event loop, asynchronous I/O opeartions.

--- Node.js uses Concurrent operation style to implement non-blocking I/O. LibUv helps it by an Event Queue, a Event Loop, a Thread Pool.

--- Concurrent and Parallel operations are different. Parallel operations are totally different from each other and needs to be run on different CPU's. Concurrent operations can be run on a single CPU, for sharing resources between them, they use shceduling or some kind of similar techniques.
