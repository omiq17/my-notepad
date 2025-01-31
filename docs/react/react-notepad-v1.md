---
layout: default
title: React Note V1
parent: React
---

Here I note down some topics as my learning procedure of React.

## Ecosystem

- Declarative
- Unidirectional
- Dataflow
- Composition
- Explicit Mutation
- "It's just JS"

## Code Techniques

#### Imperative

You tell your program how to do something.

#### Declarative

You tell your program what you want to do.

#### Pure Functions

- Evaluates the same result for same arguments
- Doesn't depend on and doesn't modify the states of variables out of its scope.
- No side effects (mutatoions, async reqs)

## Important Terms

#### Webpack

Allows you to take your code, run some sort of transformation on it, compile it all together and runs in one/multiple file.
In other words: Webpack, at its core, is a code bundler. It takes your code, transforms and bundles it, then returns a brand new version of your code.

#### Babel

This allows us to do that transformations.It compiles JSX to JavaScript.
A "Code Transformation" you can say.

#### Axios

It is used to make HTTP request.

## First Time Setup

- Open terminal
- mkdir yourFolder
- cd yourFolder
- npm init
- npm install --save react react-dom
- npm install --save-dev html-webpack-plugin webpack webpack-dev-server babel-core babel-loader babel-preset-react
- then configure your webpack.config.js, .babel.rc packege.json file and so on...

## Appendix

#### Modules

A module is just some code that we've decided to group together.
If we think about the underlying architecture of writing software, our application is usually made up of a bunch of different modules.

#### NPM

A JavaScript package manager that allows us to easily manage different packages (modules) and keep track of which version we've installed.

#### package.json file in npm

This file will, among other things, keep track of which packages or modules we've installed in your project.

#### Learn React Router

[React Router Tutorial](https://github.com/reactjs/react-router-tutorial)

#### Four Rules of "this"

- Implicit Binding(regular)
- Explicit Binding(call, apply, bind)
- New Binding
- Window Binding
