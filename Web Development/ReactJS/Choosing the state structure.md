Structuring state well can make a difference between a component that is pleasant to modify and debug, and one that is a constant source of bugs.

### Key things to learn
- When to use single vs multiple state variables
- What to avoid when organizing state
- How to fix common issues with the state structure.

## Principles for structuring state
Whenever you write a component that holds some state, 
1. You have to choose how many state variables to use, and
2. What the shape of their data will be.

Here are some principles to make better choices while structuring state:
1. **Group related state**. If you always update two or more state variables at the same time, consider merging them into a single state variable.
2. **Avoid contradictions in state.**  When the state is structured in such a way that they conflict with each other, chances of bugs is increased. Try to avoid this.
3. **Avoid redundant state** If you can calculate some value at render time using existing state variables, then you don't not create a state for that data.
4. **Avoid duplication in state** If the same data is duplicated between multiple states, then its difficult to keep then in sync, and chances of bugs increases.
5. **Avoid deeply nested state** Whenever state is nested deep in a hierarchical structure, its difficult to update. Whenever possible, prefer to structure state in a flat way.

The goal of these principles is to make state easy to update without introducing mistakes.

This is similar to how a database engineer might want to **normalize** the database structure to reduce the chances of bugs.
"Make your state as simple as possible"