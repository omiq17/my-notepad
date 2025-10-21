---
layout: default
title: SOLID principles
parent: Coding Principles
---

## Symptoms of Poor Software Design

Known as Design Smell.

- **Rigidity**
    - Hard to change (legacy) design.
- **Fragility**
    - Program breaks in many places when new feature introduced.
    - Design is easy to break.
    - Tightly coupled.
- **Immobility**
    - Hard to reuse.
- **Software Viscosity**
    - Vescosity (hard to melt down).
    - Easier to hack the normal flow.
    - Like following the grass road is easier than go on the main road.
- **Environment Viscosity**
    - Deployment related.
    - Takes long build/compile/deployment time while added new feature.
- **Needless Complexity**
    - Premature optimization
    - Overdesigning, elements that are not currently useful in tht design.
- **Needless Repetition**
    - Reuse same code multiple times.
    - Has lots of repeated code.
- **Opacity**
    - A module is difficult to understand.
    
## SOLID SOLUTION

### Single Responsibility Principle

A class should have only one reason to change. A class should have only one job.

Method, Function, Class, Package, Module, Microservice - apply the same logic to all.

A given piece of responsibility should be bundled into a single class and hidden from other elements of the program.

Need to understand 2 points-

Cohesion: Keep things in same place those are interelated and have same responsibility. (High cohesion - Less coupling)

Encapsulation: Restrict a group of same things from the outside world (through API).


### Open Closed Principle

Open for extension, closed for modification. Add new functionality without changing existing code.

Solution is to use interface. Follow polymorphich approach instead of inheritance.

Implement polymorphism to remove conditionals(multiple if/else).

### Liskov Substitution Principle

States that the objects of a superclass should be replaced by the objects of its subclasses without breaking the application.

### Interface Segregation Principle

Client should not be forced to depend on methods that they do not need/use.

Split a fat interface to many smaller or relevant interfaces.

### Dependency Inversion Principle

High level module should not depend on low level modules. Both should depend on abstractions.

Abstractions should not depend on details. Details should depend on abstractions.