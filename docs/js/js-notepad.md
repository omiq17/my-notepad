---
title: JS Note
parent: JS
---

Special notes on Javascript

## Clousers

- One way of supporting first-class functions
- A stack frame which is allocated when a function starts its execution, and not freed after the function returns.
- A closure is a function having access to the parent scope, even after the parent function has closed.
- In JavaScript, if you use the function keyword inside another function, you are creating a closure.
- The magic is that in JavaScript a function reference also has a secret reference to the closure it was created in — similar to how delegates are a method pointer plus a secret reference to an object.

      function sayHello2(name) {
        var text = 'Hello ' + name; // Local variable
        var say = function() { console.log(text); }
        return say;
      }
      var say2 = sayHello2('Bob');
      say2(); // logs "Hello Bob"

  A problem:

      function add() {
        var counter = 0;
        function plus() {counter += 1;}
        plus();
        return counter;
      }
      add() // 1
      add() // 1

Here we cannot increament the counter.

Solution with closure:

    var add = ( function() {
        counter = 0;
        return function(){ return counter += 1;}
    })();

    add() // 1
    add() // 2
    add() // 3

- The self-invoking function only runs once. It sets the counter to zero (0), and returns a function expression.
- This way add becomes a function. The "wonderful" part is that it can access the counter in the parent scope.
- This is called a JavaScript closure. It makes it possible for a function to have **Private** variables.
- The counter is protected by the scope of the anonymous function, and can only be changed using the add function.

## Sources:

- w3schools
- stackoverflow
