# React Stale Closure Bug

This repository demonstrates a common bug in React involving stale closures within `useEffect` hooks when used with `setInterval`.  The bug occurs because the callback function inside `setInterval` references the initial value of a state variable instead of its updated value.  The solution shows how to avoid this by using the functional update form of the `setCount` function.

## Bug Description

The `bug.js` file contains code that attempts to increment a counter every second using `setInterval` inside a `useEffect` hook. Due to the closure over the initial `count` value, the counter does not increment correctly.

## Solution

The `bugSolution.js` file provides the correct implementation. By using `setCount(prevCount => prevCount + 1)`, we ensure that the latest value of `count` is always used for updates.