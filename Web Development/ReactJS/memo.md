- React.memo is a higher-order-component (HOC) provided by the React API.
- It helps to optimise performance in functional components by preventing unnecessary re-renders of a component when its parent re-renders.
- It does so by memoizing the component, ie chaching it's render output and only re-renders it if its props change.

```js
import memo from 'react';

const MyComponent = memo(function MyComponent(props) {
	return <>{props.value}</>
})

const AnotherComponent = memo((props) => {
	return <>{props.value}</>
})
```
- `memo` returns a memoized version of the component.

## Usage

### Skipping re-rendering when props are unchanged
