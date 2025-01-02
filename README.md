# React 19 useEffect Cleanup Issue: Memory Leak

This repository demonstrates a common error related to the `useEffect` hook in React 19.  Forgetting to properly clean up resources within the cleanup function can result in memory leaks and unexpected component behavior.  Specifically, this example focuses on the case of `setInterval`.

## The Bug

The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, it lacks a proper cleanup function in the `useEffect` hook. This means that when the component unmounts, the interval continues to run, leading to a memory leak.

## The Solution

The `bugSolution.js` file demonstrates the correct way to use `useEffect` with `setInterval`. The cleanup function now uses `clearInterval` to stop the interval when the component unmounts. This prevents the memory leak and ensures the component behaves as expected.

## How to reproduce

1. Clone this repository
2. Run `npm install`
3. Run `npm start`
4. Observe the behavior of both components.