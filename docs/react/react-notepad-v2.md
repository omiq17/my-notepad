---
layout: default
title: React Note V2
parent: React
---

Another React Notepad with lots of new notes on React.

### State

State is key trigger for us to update our UI. State is a thing which can be changed by the component itself. However, props can only changed by outside.

### Virtual DOM

Virtual representation of the Actual DOM written in JS.
React is very fast as:

- Comparison between old and new virtual dom.
- Re-renders only the changed parts in the actual dom.

### Stateless Component

- component without a state.
- only has props.

## Component Lifecycle

1. **componentWillMount**: ................immediately before initial rendering

- **componentDidMount**: ................immedialtely after initial rendering
- **componentWillRecieveProps**: ...when component receive new props
- **shouldComponentUpdate**: ........before rendering, after receiving new props or states.
- **componentWillUpdate**: ..............before rendering, after receiving new props or states
- **componentDidUpdate**: ...............after component's updates are flushed to DOM
- **componentWillUnmount**: ..........immediately before removing component from the DOM

(Returning false in shouldComponentUpdate will disable it's below components)
