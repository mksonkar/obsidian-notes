- In React, data flow is unidirectional.
- Data flows from the root component to the child components in the tree structure that require this data using props.
- Props are immutable, i.e. they cannot be changed.
- Two main benefits of this are:
	- It easier to comprehend the logic of React apps
	- Simplify data flow.
* If data were moving in all directions from different components, it would be very difficult to comprehend the logic and data flow of the React app.
- Because of which any optimization you tried to implement on the app would not be as efficient as it could be.

- Data in React can be props or state
- Props data belongs to the parent that renders the component, while state data belongs to the component itself 