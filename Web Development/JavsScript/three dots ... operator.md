The three dots operator has two different meaning in js. 

## The Spread operator

### Spread operator syntax
```js
const newArray = ['firstItem', ...oldArray];
```

### Examples
#### Copy an array with spread operator.
```js
const array1 = ['Mukesh', 'Nikheel', 'Rakhee', 'Ram'];

const array2 = [...array1];

console.log(array2); // ['Mukesh', 'Nikheel', 'Rakhee', 'Ram']
```
The saves times instead of writing a loop to copy: 
```js
const array1 = ['Mukesh', 'Nikheel', 'Rakhee', 'Ram'];

const array2 = [];

array1.map((name) => {
	array2.push(name);
})
```

#### Copy an object with spread operator


## The Rest operator