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

