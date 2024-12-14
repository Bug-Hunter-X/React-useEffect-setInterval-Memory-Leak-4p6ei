# React useEffect setInterval Memory Leak
This example demonstrates a common mistake when using setInterval within a React useEffect hook, leading to a memory leak.  The problem is that the setInterval function continues to run even after the component unmounts.  This can cause the component to continue updating even after it's no longer visible, leading to performance issues and memory leaks.

## Bug
The `bug.js` file contains a React component that uses `setInterval` inside a `useEffect` hook without proper cleanup.  This means that when the component unmounts, the `setInterval` continues running, consuming resources and potentially causing errors. 

## Solution
The `bugSolution.js` file provides a corrected version. The key is to return a cleanup function from the `useEffect` callback. This function clears the interval when the component unmounts, preventing the memory leak.