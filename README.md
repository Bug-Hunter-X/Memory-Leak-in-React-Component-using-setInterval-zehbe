# React setInterval Memory Leak
This example demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook.  Without proper cleanup, the interval continues to run even after the component is unmounted, leading to memory leaks and unexpected behavior.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides the corrected code that addresses the memory leak.

**Key Issue:** Failure to return a cleanup function from `useEffect` to stop the interval when the component is unmounted.

**Solution:** Return a function from `useEffect` that uses `clearInterval` to stop the interval.