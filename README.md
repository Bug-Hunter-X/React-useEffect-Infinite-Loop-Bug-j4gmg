# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React's `useEffect` hook: an infinite loop caused by incorrectly including the state setter function in the dependency array.

## Bug Description
The `MyComponent` component uses `useEffect` to update a counter every second. However, the dependency array includes `setCount`, causing the effect to re-run every time the counter updates, leading to an infinite loop.

## Solution
The correct solution is to remove `setCount` from the dependency array. This ensures the effect only runs once after the initial render.  The `setInterval` method creates a closure over the `setCount` function, so it's unnecessary in the dependency array. 
