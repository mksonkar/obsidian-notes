- useCallback is a hook that returns a [memoized](Memoization) version of a function.
- i.e. it stores the result of function calls in memory, and when same inputs are encountered, it returns the stored output immediately instead of calling the function again.
- It only calls the function again if one of its dependencies (provided in the dependency array) changes.

### How `useCallback` memoizes a function
1. **Function recreation on every render:** Normally, in React, functions inside components are redefined every time the component re-renders. This can cause performance issues if the function is passed as a prop to child components, or is used inside `useEffect`, since re-creating the function e
```js
const memoizedFunction = useCallback(() => {
	// some function logic here
}, [dependency1, dependency2]);
```