---
layout: default
title: ES6 Notepad
---

Important notes on ES6 fearures.

## var, let & const dilemma

### var

Js var is **hoisted**.
_Examples where var creates problems_:

    function counter () {
        for(var i = 0; i<3; i++) {
            console.log(i);
        }
         console.log("after loop", i)
    }
    counter()
    :: 0
    :: 1
    :: 2
    :: after loop 3

    (function () {
        for(var i = 0; i<3; i++) {
            console.log(i);
        }
    }
     )()
    console.log("after loop", i)
    :: 0
    :: 1
    :: 2
    :: Uncaught ReferenceError: i is not defined

_An horrible example:_

    (function () {
        for(var i = 0; i<3; i++) {
            console.log(i);
        }
    }
     )()
    console.log("after loop", i)
    :: 0
    :: 1
    :: 2
    :: after loop 3

### let

let is block scoped and only going to accessible within the block.

### const

just like let except that we cannot change it. More specifically, you cannot reassign it. So, it is immutable.

    const x = { y : 5 }
    :: undefined
    x.y = 7
    :: 7
    const x = { z : 7 }
    :: Uncaught SyntaxError: Identifier 'x' has already been declared

## Arrow Function

Sorter form of the regular function or a shorter function syntax. One side effect of the arrow function is they can be named.
It allows us to make function:

- simple
- inline
- single-purpose

      const dragonEvents = [
        { type: 'attack', value: 12, target: 'player-dorkman' },
        { type: 'yawn', value: 40 },
        { type: 'eat', target: 'horse' },
        { type: 'attack', value: 23, target: 'player-fluffykins' },
        { type: 'attack', value: 12, target: 'player-dorkman' },
      ]

  From this:

      const totalDamageOnDorkman = dragonEvents
        .filter(function (event) {
          return event.type === 'attack'
        })
        .filter(function (event) {
          return event.target === 'player-dorkman'
        })
        .map(function(event) {
          return event.value
        })
        .reduce(function(prev, value) {
          return (prev || 0) + value
        })

  To this:

       const totalDamageOnDorkman = dragonEvents
      .filter(e => e.type === 'attack')
      .filter(e => e.target === 'player-dorkman')
      .map(e => e.value)
      .reduce((prev, x) => (prev || 0) + x)

## Class

**Inheritance**
_super():_ basically used to call constructor of the inherited class

     class aussie {
        constructor(captain) {
            this.captain = captain;
        }
        callCap() {
            return this.captain;
        }
    }

    class tigers extends aussie {
        constructor() {
            super("Musfiq");
        }
        callCap() {
            return this.captain;
        }
    }

    let bd = new tigers()
    bd.callCap()
    :: Musfiq

_Classes has no Private variable which can be seen by this example_

    bd.captain = "Smith"
    bd.callcap()
    :: Smith

## Destructuring

Allows us to break an objects or array into variables.

    let evan = {
        name: "Mahbub Evan",
        versity: "AIUB" }
    let {name, versity} = evan

## Appendix

### Final Lesson

- _Always use "const", if you need to change state then use "let", "var" is dead. We do this to minimize mutable state_
- _JS has no classes, it's all fake. It's just a thin layer above the prototypal inheritance of JS._
- _Better to use natural prototypal nature of JS rather than using classes._

### Immediately Invoked Function Expression

(function () {
for(var i = 0; i<3; i++) {
console.log(i);
}
console.log("after loop", i)
}
)()

## Sources

Fun Fun Function [https://www.youtube.com/channel/UCO1cgjhGzsSYb1rsB4bFe4Q]
