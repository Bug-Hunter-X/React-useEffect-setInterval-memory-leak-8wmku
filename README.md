# React useEffect setInterval Memory Leak
This example demonstrates a common error in React when using the `useEffect` hook with `setInterval`.  Forgetting to return a cleanup function from `useEffect` when using `setInterval` or `setTimeout` leads to memory leaks.  The `setInterval` continues to run even after the component unmounts causing the counter to increment even when the component is not rendered.

## Bug:
The bug is in `bug.js`. The `setInterval` function is called inside the `useEffect` hook without a cleanup function. This causes the interval to continue even after the component unmounts.

## Solution:
The `bugSolution.js` file provides a corrected version. The solution uses a cleanup function returned from `useEffect` that calls `clearInterval` to stop the interval when the component unmounts.