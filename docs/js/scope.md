---
layout: default
title: JS Scope
parent: JS
---

```js
if (true) {
  const message = "Hello";
}
console.log(message); // ReferenceError: message is not defined
```

The if code block creates a scope for message variable. And message variable can be accessed only within this scope.

The **`scope`** is a policy that **manages the accessibility of variables.**

#### Block Scope

A `code block ({...})` in JavaScript **defines a scope for variables declared using `let` and `const`.**

```js
if (true) {
  // "if" block scope
  const message = "Hello";
  console.log(message); // 'Hello'
}
console.log(message); // throws ReferenceError
```

**`var`** is not _block scoped_

```js
if (true) {
  // "if" block scope
  var count = 0;
  console.log(count); // 0
}
console.log(count); // 0
```

NB: A _code block does not create a scope_ for `var` variables, but a _function body does._

#### Function Scope

A `function` in JavaScript **defines a scope for variables declared using var, let and const.**

#### Module Scope

`ES2015` module also **creates a scope for variables, functions, classes.**

Looking from another angle, the scope is an _encapsulation mechanism_ for code blocks, functions, and modules.

##### Scopes can be nested

```js
function run() {
  // "run" function scope
  const message = "Run, Forrest, Run!";

  if (true) {
    // "if" code block scope
    const friend = "Bubba";
    console.log(message); // 'Run, Forrest, Run!'
  }

  console.log(friend); // throws ReferenceError
}

run();
```

NB: The _inner scope_ can access the variables of its _outer scope._

#### Global Scope

The global scope is the **outermost scope**. It is **accessible from any inner (aka local) scope.**

`window` and `document`, for example, are global variables supplied by the browser. In a Node environment, you can access `process` object as a global variable.

#### Lexical Scope

```js
function outerFunc() {
  // the outer scope: Lexical scope
  let outerVar = "I am from outside!";

  function innerFunc() {
    // the inner scope: Closure
    console.log(outerVar); // 'I am from outside!'
  }

  return innerFunc;
}

const inner = outerFunc();
inner();
```

JavaScript implements a scoping mechanism named lexical scoping (or static scoping). Lexical scoping means that the accessibility of variables is determined statically by the position of the variables within the nested function scopes: _the inner function scope can access variables from the outer function scope._

The **closure** is a function that accesses its lexical scope even executed outside of its lexical scope.

**Lexical scope** means that in a nested group of functions,_ the inner functions have access to the variables and other resources of their parent scope._

**Lexical Scoping** defines how variable names are resolved in nested functions: _inner functions contain the scope of parent functions even if the parent function has returned._

The last part: _"even if the parent function has returned"_ is called **Closure**.

# Hoisting

**Hoisting** is the mechanism of **moving the variables and functions declaration to the top of the function scope (or global scope if outside any function).**

Hoisting influences/affects/colute/contaminate the variable life-cycle, which consists of these 3 steps:

- **Declaration** - create a new variable. E.g. `var myValue`
- **Initialization** - initialize the variable with a value. E.g. `myValue = 150`
- **Usage** - access and use the variable value. E.g. `alert(myValue)`

`var`, `function` gets hoisted to the top of scope.

`let`, `const`, `class` is not hoisted _(rough hoised)_.

**Sources**

- https://dmitripavlutin.com/
- https://stackoverflow.com
