- React.memo is a higher-order-component (HOC) provided by the React API.
- It helps to optimise performance in functional components by preventing unnecessary re-renders of a component when its parent re-renders.
- It does so by memoizing the component, ie chaching it's render output and only re-renders it if its props change.

```react
import memo from 'raect'
```