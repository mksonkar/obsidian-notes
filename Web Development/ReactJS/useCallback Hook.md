- useCallback is a hook that returns a [memoized](Memoization) version of a function.
- i.e. it stores the result of function calls in memory, and when same inputs are encountered, it returns the stored output immediately instead of calling the function again.
- It only calls the function again if one of its dependencies (provided in the dependency array) changes.

### How `useCallback` memoizes a function
1. **Function recreation on every render:** Normally, in React, functions inside components are redefined every time the component re-renders. This can cause performance issues if the function is passed as a prop to child components, or is used inside `useEffect`, since re-creating the function.
2. **Memoization with `useCallback` hook:** When you wrap a function with `useCallback`, React memoizes that function and only recreates it when any of the dependencies in the dependency array changes. Otherwise it returns a **cached version** of the function, hence preventing unnecessary re-creation.
```js
const memoizedFunction = useCallback(() => {
	// some function logic here
}, [dependency1, dependency2]);
```
3. **Why is it useful?** 
-  When a function is passed down as props to child components, memoization helps unnecessary re-renders of those children.
- When a function is used in `useEffect` as a dependency, memoization prevents `useEffect` from triggering it on every re-render, as React considers the memoized version as stable.