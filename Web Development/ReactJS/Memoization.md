- Memoization is an [optimization technique](Optimization%20Techniques%20in%20React).
- It is used to increase the performance of expensive or frequently executed function calls.
- Instead of recomputing the result every time the function is called with the same inputs, it caches the results and returns the result immediately for same inputs. 

- In React, memoization, helps to avoid unnecessary recalculations and re-renders when components or functions are called with the same props.
- To achieve this React uses the [`useCallback`](useCallback%20Hook) hook.

### Ways to achieve memoization in React
- **[[memo]]**
- **[[useMemo Hook|useMemo]]**
- **[[useCallback Hook|useCallback]]**

### Difference between memo, useMemo & useCallback
