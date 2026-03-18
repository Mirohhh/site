---
date: '2026-03-18T23:53:55+02:00'
draft: false
title: "React's useEffect hook"
author: "Omar Shabana"
tags: ["web dev", "react"]
---

React's `useEffect` hook is a powerful tool for managing side effects in functional components. It allows you to perform tasks like data fetching, subscriptions, or manual DOM manipulations after the component has rendered.

### Basic Syntax

The `useEffect` hook accepts two arguments: a function for the effect and an optional array of dependencies.

```javascript
useEffect(() => {
  // Side effect logic goes here
}, [dependencies]);
```

### Dependency Behaviors

The way `useEffect` triggers depends on the dependency array provided:

1. **No array provided**: The effect runs after every single render.
2. **Empty array (`[]`)**: The effect runs only once, immediately after the initial mount.
3. **Array with values**: The effect runs on mount and whenever any of the values in the array change.

```javascript
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }, [count]); // Only re-run the effect if count changes

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

### Cleanup Functions

To prevent memory leaks, some effects require a cleanup phase (e.g., clearing a timeout or unsubscribing from an API). You can achieve this by returning a function from within the effect.

```javascript
useEffect(() => {
  const timer = setTimeout(() => {
    console.log('Action after 1 second');
  }, 1000);

  // Cleanup function
  return () => clearTimeout(timer);
}, []);
```

### Downsides and Pitfalls

While `useEffect` is a versatile tool, it comes with several downsides:

- **Infinite Loops**: It's easy to accidentally trigger an infinite loop if you update a state variable that is included in the dependency array.
- **Stale Closures**: If the dependency array is not correctly managed, the effect might capture outdated values from previous renders.
- **Complexity**: Components with many effects can become difficult to read, as the logic for a single feature may be spread across multiple lifecycle phases.
- **Race Conditions**: Asynchronous operations like data fetching can result in race conditions where an older request resolves after a newer one, potentially leading to inconsistent UI state.
- **Performance Overhead**: Frequent execution of effects can lead to performance issues if the logic inside the effect is computationally expensive.
