---
layout: note
title: Design patterns overview
parent: Design Patterns
---

### Benfits

- Implementing solutions that use design patterns save us hours of time in debugging making the codebase robust and reusable.
- Design pattern helps to develop structured codebase and maintain it easily in check with SOLID principles.

### Categories

1. Creational
2. Structural
3. Behavioral

### Creational Patterns

- Concerned with improving the process of object creation.
- It enforce to follow a structure while create an object.
- Avoids unnecessary manipulation.

#### Sigleton Pattern

- Sometimes we want to restrict the total number of instances that can be created of a particular object.
- Example: Wifi router is shared by all family members. In this case single wifi connection being consumed by multiple members.

### Structural Patterns

- Ensure that the structure defined for our classes/objects is efficient and flexible so that it can be easily composed with other objects.
- When we use `extends` or `implements`, we use some form of Structural Design Pattern.

#### Adapter Pattern

- Allows two completely different objects to understand and communicate with each other.
- Example: There will be a wrapper class which will take input/recieve information from different sources. Then convert all inputs to a particular format of cosumer needs.

#### Module Pattern

- Best way to facilitate compostion into our application.
- Each module will represent an independent part of our applicaion which can be assembled into a more complex application.
- Make codebase organized and extremely reusable.
- Example: Implementing Auth in different applications. There will a an Auth class with `authorize()` method in it. User class will call this method to login.

#### Composite Pattern

- Extension of Module pattern.
- Once we create independent modules, all of these can be implement to form a complex application.
- Like our smartphone, that is made of so many different pieces like a display, battery, microphone, memory unit, camera, and so on.
- Example: We can implement a Logger module in our User service. Thus User service will have two modules: Auth, Logger.

### Behavioral Patterns

- Aim at defining how objects can communicate each other in a flexible way.
- If we ever user a Publiser/Subscriber model, message queue or UI framework, then we used that pattern.
- 2 main flavour:
  - Push based: Change notification is pushed to subscribers. Like socket.
  - Pull based: Objects keep polling from subscriber to get updates. Like REST APIs.
- Example: When we follow someone in social media, we except to recieve all of the updates of the publisher. Push based observer pattern is the perfect solution in this case.

References:

- [https://programmingwithmosh.com/javascript/top-design-patterns-to-master-in-typescript/](https://programmingwithmosh.com/javascript/top-design-patterns-to-master-in-typescript/)
