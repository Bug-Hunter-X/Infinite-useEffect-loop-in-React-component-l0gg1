# React Infinite useEffect Loop Bug

This repository demonstrates a common React bug involving an infinite loop within the `useEffect` hook.  The bug occurs because the effect's dependency array is incorrect, leading to an infinite re-render cycle.

## Bug Description
The provided `MyComponent` uses `useEffect` to log the current count to the console. However, the effect has no dependency array (or an incorrect one), causing it to run after every render, including the ones triggered by itself. This creates an infinite loop, consuming significant resources and potentially freezing the browser.

## Solution
The solution involves correctly specifying the dependencies for the `useEffect` hook. By including `count` in the dependency array `[count]`, the effect will only run when the value of `count` changes, thus resolving the infinite loop.