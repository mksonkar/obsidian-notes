Components with many state updates across many event handlers can get overwhelming.
In such a case, we can **separate all the state related logic inside a function called reducer**, placed outside the component.

### Learning objectives
- What a reducer function is?
- How to refactor `useState` to `useReducer`
- When to use `useReducer`
- How to write a `useReducer` function well.

### Consolidate state logic with a reducer
As your components grow in complexity, it can get harder to see at a glance at all the ways in 
which a component's state gets updated.