# React useEffect Infinite Loop Bug
This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug occurs when a dependency array is missing or incomplete in `useEffect`, leading to an infinite render loop.

## Bug Description
The provided code contains a `useEffect` hook that logs the current `count` state to the console.  However, because the dependency array `[count]` is missing, the effect is triggered on *every* render, causing an infinite loop.  The `setCount` function, triggered by the button click, causes the component to re-render, and then the `useEffect` runs again, and so on.

## Solution
The solution is to correctly specify the dependency array in `useEffect`.  If you want the effect to only run when `count` changes, include `count` in the dependency array.  If you don't need it to run on every render, remove the useEffect altogether.  See `bugSolution.js` for the corrected code.
