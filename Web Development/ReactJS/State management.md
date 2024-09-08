### Prop drilling
It is a situation where you are passing data from a parent to a child and then to a grandchild and so on, until it reaches a more distant component down the line where data is required.

It refers to the process of passing data from a parent component down to nested child components through **props**, even if some of the intermediate components may not need that data. It is a way to get the necessary data to a deeply nested component.
But it can lead to inefficient and hard-to-maintain code.

```php
<App />
  ├── <Parent />
        ├── <Child />
              ├── <Grandchild />
```

### Problems with prop drilling
- **Unnecessary passing of props**: Component that don't need the data still receive the props, cluttering the component logic.
- **Harder to maintain**: As the codebase grows with more and more components, prop drilling can make the codebase harder to read, understand and maintain.
- **Harder to debug and error-prone**: It's easy to lose track of which props are passed where and used where, leading to code being more error prone. 
- **Reduced reusability**: Since prop drilling makes the components tightly coupled to data flow, this goes against the core principles of React, which is modularity and readability.

### Solutions to prop drilling
- **Context-API**: React's Context API allows you to share data between components without explicitly passing props through every level of the tree.
- **State management libraries**: Tools like Redux allow you to store global state in your app without prop drilling.
- **Restructuring**: Restructuring your component tree in such a way that it doesn't have deep nesting.
- **Custom hooks**: can be used to encapsulate commonly used state logic.

