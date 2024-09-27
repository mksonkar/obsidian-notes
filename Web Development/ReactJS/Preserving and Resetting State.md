State is isolated between components. 
React keeps track of which state belongs to which component, based on their place in the UI tree.
You can control when to reset state and when to preserve it between re-renders.

### To Learn: 
- When React chooses to preserve or reset the state.
- How to force React to reset a component's state.
- How keys and types affect whether the state is preserved.

## State is tied to a position in the render tree
- React builds render trees for the component structure in your UI.
- When you give a component state, you might think the state lives inside the component, but the state is actually held inside React.
- React associates each state with the correct component based on where the component sits in the render tree.

In React, each component has fully isolated state.
Eg. if you render two <Counter /> components side by side, both of them will have separate isolated states.
That's because both will have it's own position in the render tree.
![[Pasted image 20240927145140.png]]
When one component is updated, only state of that component is updated.
![[Pasted image 20240927145258.png]]
React will keep the state as long as the same component is rendered at the same position in the render tree.
**React preserves a component's state as long as it's rendered at the same position in the UI Tree.**
If it gets removed, or a different component is rendered at the same position, React discards the state.

## Same component at the same position preserves state
## Different components at the same position resets state
When you render a different component in the same position, it resets the state of its entire subtree.

As a rule of thumb, 
**if you want to preserve state between re-renders, the structure of the tree should be the same across renders.**
If the structure changes, then react destroys the state associated with part of the tree that changed including its subtrees.