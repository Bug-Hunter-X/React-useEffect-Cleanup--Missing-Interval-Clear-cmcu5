# React useEffect Cleanup: Missing Interval Clear

This example demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement to clear an interval when the component unmounts.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Bug:

The `setInterval` function within the `useEffect` hook continuously updates the count.  However, the absence of a cleanup function using `clearInterval` results in a memory leak when the component unmounts.  The interval will keep running, consuming resources unnecessarily. 

## Solution:

The solution adds a return statement to the `useEffect` function. This return statement executes before the component unmounts, effectively clearing the interval using `clearInterval`.