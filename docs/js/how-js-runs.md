---
layout: default
title: How JS Runs
parent: JS
---

- JS code => V8/SpiderMonkey/Chakra/JavaScriptCore (JS Engine) => Machine code => Output in browser
- Interpreter: slow process, easy to debug.
- Compiler: fast process, system crash, hard to debug.
- V8 Engine: back in 2008, introduces JIT Compiler, mixture of both.
- JIT(interpretation) Compiler(compilation): a function() gets invoked/called, converts to machine code just in time, then execute it. If any error occurs, JIT raise his hand, wait!

[lesson link](https://www.youtube.com/watch?v=Wk0-6b1W_VQ)

---

- JS has a heap, call stack, web apis, callback queue, event loop.
- In node.js: web apis replaced some by c++ libraries.
- Heap: deals with some kind of memory management.
- Call stack: single thread, synchronous, executes one operation at a time.
- Web APIs/C++ libraries: handles the bloking/asychronous I/O operations like timer, ajax call, file operations, some kind of dealing with memory.
- Callback queue: after finishing tasks at web apis, callback functions come here and stay.
- Event loop: simple thing that checks call stack and callback queue. If there is a cb() in queue, it checks if the call stack is empty (if not then waits), then pop the first item from queue and pushes it to empty call stack.

Some points to be noted here:

- If we do a huge sync operation (running a while loop billion times), call stack gets busy and event loop cannot able to transfer item. The browser also gets stuck, in that time user cannot interact.
- Sometimes it is good to use async for/while loop with callbacks. Callbacks will reside in queue and then go into the stack one by one. It will not block anything.
- Render Queue: the browser reprints the screen in every (ideally) 60ms. It invokes a callback function in render queue, then event loop passes that cb to call stack if it is empty. So, the browser will not get reprinted if call stack is busy.

[lesson link](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
