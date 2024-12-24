# React Native: Handling Asynchronous Data Loading

This repository demonstrates a common error in React Native applications: attempting to access data before it has been fully loaded from an asynchronous operation.

The `bug.js` file shows the problematic code that attempts to render data from an API before it's available.  The `bugSolution.js` file provides the corrected code that handles this situation gracefully.

## Problem

When a component fetches data asynchronously using `useEffect` and `fetch`, there's a race condition: the component might render before the `setData` function is called.  This results in the 'Cannot read properties of undefined' error when the component tries to access the `data` object's properties (e.g., `data.name`).

## Solution

The solution involves using conditional rendering or optional chaining to check if the data is available before accessing it.  This prevents the runtime error and provides a better user experience by showing a loading indicator or fallback content while data is being fetched.