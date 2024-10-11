React Fiber is a re-implementation of the React's core algorithm.

It's main feature is **Incremental Rendering**: the ability to split rendering work into multiple chunks and spread it out over multiple frames.

### Reconciliation
The algorithm React uses to diff one tree with another to determine which parts need to be updated.

Re-rendering the entire app on a change is only feasible for small apps, for real world applications, this can be very costly in terms of performance. 

React uses various optimization techniques to make this process as efficient as possible. A majority of these optimizations are a part of the Reconciliation algorithm.

##### Reconciliation is the algorithm behind 'Virtual-DOM'
- Whenever a React app is rendered, a tree of nodes comprising of components is created and saved in memory.
- Whenever the app is updated, usually by calling 'setState', a completely new tree is generated representing a new snapshot of the app at the current time. 
- Then the React reconciliation algorithm diffs both the tree to determine which parts have changed and computes the minimal necessary updates required to update the old snapshot with the new one.

	- If a new component is rendered, React will not diff them, and rather replace the old tree with the new nodes. 
	- In case of lists, React uses `keys` to determine, which items have changed. Hence, keys should always be unique and should not change during the lifetime of the React app.
### Reconciliation vs Rendering
The DOM is just one of environments where React can render to.
Other environments include, Android, IOS via React Native.

The reason React can support so many environments is because, 
React is designed in such a way that Reconciliation and Rendering are two separate phases.
The reconciler determines which parts of the Virtual DOM has changed, 
and the renderer the makes the necessary changes to the DOM to reflect the updates.

This separation means that different environments can have React DOM and React Native can use their own renderers while sharing the same reconciler provided by React core.

**React Fiber is a new implementation of the reconciliation algorithm.**