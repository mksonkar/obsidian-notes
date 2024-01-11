#Objects
### Creating an object literal
```js
const person = {};
```

Example: c
```js
const person = {
	name: ['Mukesh', 'Kumar'],
	age: 26,
	bio: function () {
		console.log(`${this.name[0]} ${this.name[1]} is ${this.age} years old.`);
	},
	introduceSelf: function () {
		console.log(`Hi! I'm ${this.name[0]}.`)
	},
};
```

Output: 
```js
person.name;  
person.name[0];
person.age;
person.bio();
// "Bob Smith is 32 years old."
person.introduceSelf();
// "Hi! I'm Bob."
```

When the object's members are functions, there's a simpler syntax. 
Instead of `bio: function()` we can write just `bio()`
```js
const person = {
	name: ['Mukesh', 'Kumar'],
	age: 25,
	bio() {
		console.log(`...`);
	},
	introduceSelf() {
		console.log(`...`)
	},
};
```

**Properties** are the data items inside an object and 
**Methods** are the functions inside an object. 

### Dot notation
```js
person.age;
person.bio();
```
used to access object's properties. 

### Objects as object properties
```js
const person = {
	name: ['Mukesh', 'Kumar'],
};
```
to 
```js
const person = {
	name: {
		first: 'Mukesh',
		last: 'Kumar',
	},
}
```
to access this: 
```js
person.name.first; // 'Mukesh'
person.name.last; // 'Kumar'
```

### Bracket notation
Object's properties can also be accessed via:
```js
person['age'];
person["name"]["first"];
```
This is very similar to how you access items in an array and is basically the same thing -- instead of using index numbers to select an item, you are using the name associated with each member's value. Because of this reason, objects are also called **Associative arrays**.

