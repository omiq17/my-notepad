---
layout: default
title: JS, TS, REACT, NODE Preparation
parent: Interview
---

1. JS this

   this is a keyword, it refers to an object, which object-depends on how this is being invoked.
   in object - refers to the object
   alone - global object
   function - global object
   function - strict mode - undefined
   event - refers to the HTML element that received by the event
   call(), apply(), bind() - refers to any object

2. useEffect useLayoutEffect

   useEffect runs asynchronously and after a render is painted to the screen (after browser paints the screen). useLayoutEffect, on the other hand, runs synchronously (before the browser paints) after a render but before the screen is updated. This means useLayoutEffect will block the screen update, causing potential performance issues if the effect takes too long.

3. React security

   escape variables, react does automatically by {}
   use HTTPS
   utitlize dangerouslySetInnerHTML, if used then sanitize HTML(with DOMPurify library)
   use two factor authentication
   use the rule of least previlege when interacting with DB

4. React refactor

   make resusable components/components breakdown
   use hooks
   optimize render - useMemo, useCallback
   use ESLint, Prettier
   write unit tests

5. Typscript
6. JS closure

   Global variables can be made local (private) with closures. It makes it possible for a function to have "private" variables.

7. Cybersecurity
8. Web perfomance
9. Web security
10. PostgreSQL
11. TS any vs unknown

    any, unknown:
    allow assigning any type

    any:
    allows being assigned to any type
    allows calling any method

    unknown:
    doesn't allow being assigned to any type
    doesn't allow calling any method

    const a: any = 'a'; // OK
    const b: unknown = 'b' // OK

    const v1: string = a; // OK
    const v2: string = b; // ERROR
    const v3: string = b as string; // OK

    a.trim() // OK
    b.trim() // ERROR

12. TS generic types

    Generics allow us to create flexible, reusable, and type-safe code by defining type variables instead of explicitly specifying types.
    Generics allow creating type variables which can be used to create class/function/type aliases.
    No need to explicitly define types.
    Makes it easier to write reusable code.

13. TS type vs interface
14. TS enum

    enum is a special class that represents a group of constants.
    Enums come in two flavors string and numeric.

15. TS Aliases

    Allow defining types with a custom name.

16. TS Interface

    Interfaces are similar to type aliases, except they only apply to object types.

17. TS Tuple

    A tuple is a typed array with a pre-defined length and types for each index.

18. TS type vs interface

    Types in TypeScript are more flexible and can define primitive, intersection, union, tuple, or different types of data, while interfaces are used to describe the shape of an object.

19. JS/ES6+

20. API Security

    1. Authentication - username/password. 2FA.
    2. Authorization - RBAC, access only to the authorized roles.
    3. Rate Limiting - Protect from brute-force/DOS attacks.
    4. Use tokens - JWT is good for maintaining user sessions.
    5. Error Handling - expose specific and short comprehensive error message. don't expose too much info.
    6. Input Validation - Protect from SQL injection, XSS attacks.
    7. Use HTTPS - this encrypts the data between the client and the server.
    8. Hide Sensitive Information - hide keys, secrets.
    9. Update dependencies - to get latest security patches.

21. REST API
    Client Server Arcitecture
    Stateless
    Cacheable
    Uniform Interface
    Layered System
    Code on Demand (optional)

- relational/non-relaional db - mongoDB

- web3, IPFS

- Rust

- Bash/shell scripting

- terraform

- vector db

- semantic search tech - elastic
