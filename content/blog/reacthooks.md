---
title: Learning React Hooks
description: Descriptive notes on commonly used React hooks with example code.
date: 2023-12-10
cover: react.jpg
tags:
  - react
---

# Table of Contents

1. [useState](#usestate)
2. [useEffect](#useeffect)
3. [useContext](#usecontext)
4. [useReducer](#usereducer)
5. [useCallback](#usecallback)
6. [useMemo](#usememo)
7. [useRef](#useref)
8. [useLayoutEffect](#uselayouteffect)

---

# Hooks

## useState

Allows functional components to manage state. It returns a stateful value and a function to update it.

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

Where count is the getter, setCount is the setter, and 0 is the initial state.

## useEffect

Performs side effects in functional components. It runs after every render by default.

```jsx
import React, { useState, useEffect } from "react";

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

Where the variable changes without re-rendering the entire component.

## **useContext**

Allows functional components to consume context. It accepts a context object and returns the current context value. This hook helps prevent the overusage of prop drilling

```jsx
import React, { useContext } from "react";
import ThemeContext from "./ThemeContext";

function ThemedButton() {
  const theme = useContext(ThemeContext);

  return (
    <button style={{ background: theme.background, color: theme.color }}>
      I am styled by theme context!
    </button>
  );
}
```

This can be used for several application wide contexts that the entire application may use such as SecurityContext, AuthContext, UserContext, ThemeContext, etc.

## useReducer

Allows you to manage complex state logic in a more predictable way. It is similar to **`useState`**, but instead of managing a single state value, it manages a state object and allows you to update it based on the previous state.

```jsx
import React, { useReducer } from "react";

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <div>
      Count: {state.count}
      <button onClick={() => dispatch({ type: "increment" })}>+</button>
      <button onClick={() => dispatch({ type: "decrement" })}>-</button>
    </div>
  );
}
```

## useCallback

Returns a memoized callback function that only changes if one of the dependencies has changed. It is useful for optimizing performance by preventing unnecessary re-renders.

```jsx
import React, { useState, useCallback } from "react";

function MyComponent() {
  const [count, setCount] = useState(0);
  const handleClick = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={handleClick}>Increment</button>
    </div>
  );
}
```

## useMemo

Returns a memoized value. It is similar to **`useCallback`**, but instead of memoizing a callback function, it memoizes a computed value.

```jsx
import React, { useMemo } from "react";

function MyComponent({ a, b }) {
  const result = useMemo(() => {
    return a + b;
  }, [a, b]);

  return <p>Result: {result}</p>;
}
```

## useRef

Returns a mutable ref object whose **`.current`** property is initialized to the passed argument (**`initialValue`**). The returned object will persist for the full lifetime of the component.

```jsx
import React, { useRef } from "react";

function MyComponent() {
  const inputRef = useRef(null);

  const handleClick = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={handleClick}>Focus Input</button>
    </div>
  );
}
```

Extra: useRef() can be used to retrieve global constants such as user authentication but it can also be used to retrieve validation and values of input using **`forwardRef`**and **`useImperativeHandle` .**

## useLayoutEffect

Similar to **`useEffect`**, but it fires synchronously after all DOM mutations. It is useful for reading from the DOM and performing custom layout effects. Note that it runs synchronously, so it may cause performance issues if used incorrectly.

```jsx
import React, { useState, useLayoutEffect } from "react";

function MeasureWindow() {
  const [width, setWidth] = useState(0);

  useLayoutEffect(() => {
    const handleResize = () => {
      setWidth(window.innerWidth);
    };

    window.addEventListener("resize", handleResize);
    handleResize(); // Initial measurement

    return () => {
      window.removeEventListener("resize", handleResize);
    };
  }, []);

  return <p>Window width: {width}px</p>;
}
```
