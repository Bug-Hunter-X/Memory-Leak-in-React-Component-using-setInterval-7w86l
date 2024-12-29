# React setInterval Memory Leak Bug

This repository demonstrates a common bug in React applications involving the improper use of `setInterval` within the `useEffect` hook, leading to memory leaks. 

The `bug.js` file contains the faulty component. The `bugSolution.js` file provides the corrected implementation.

## Bug Description
The component uses `setInterval` to update a counter every second. However, it lacks a cleanup function within the `useEffect` hook to clear the interval when the component unmounts. This causes the interval to continue running even after the component is removed from the DOM, resulting in a memory leak.

## Solution
The solution involves using the return value of `useEffect` to provide a cleanup function that calls `clearInterval` to stop the interval when the component is unmounted.