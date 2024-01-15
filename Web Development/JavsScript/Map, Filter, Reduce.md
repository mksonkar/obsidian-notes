## The `map` method

```js
let array = [1, 2, 3, 4, 5];
let newArray = array.map( (n)=>{
	return n*n;
})
console.log(newArray);
```
Output:
```js
[ 1, 4, 9, 16, 25 ]
```

- The map methods creates a new array by calling a function for every element of the original array.
- It does not run for empty elements.
- It does not modify the original array.

## The `filter` method

