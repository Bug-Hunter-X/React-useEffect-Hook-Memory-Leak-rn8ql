# React useEffect Hook Memory Leak

This repository demonstrates a common mistake when using the `useEffect` hook in React: forgetting to return a cleanup function to clear intervals or timeouts.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Bug Description:

The `MyComponent` component uses `setInterval` to update a counter every second.  However, it's missing a cleanup function within the `useEffect` hook.  This leads to a memory leak because the interval continues to run even when the component unmounts, consuming resources unnecessarily.

## Solution:

The solution involves adding a return statement within the `useEffect` hook. This statement returns a function that uses `clearInterval` to stop the interval before the component unmounts.