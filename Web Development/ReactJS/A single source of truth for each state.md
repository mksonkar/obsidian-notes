- For each unique piece of state, you will choose a component that "owns" it.
- This principle is known as having a "Single source of truth".

- This doesn't mean that all the state will be owned by a single component.
- But for each piece of state, there is a specific component that holds that information.

- Instead of duplicating shared state between components, **lift the state up** to a common parent, and pass it down via props to the children that need it.

- As you work on your app, it is common that you will move state down or lift it back up as you're still figuring out where each piece of the state lives. This is a part of the process.