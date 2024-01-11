- Introduced in ES6
- It is a **blueprint** or **template** to create an object.

### Syntax 
```js
Class ClassName {
	constructor(parameter) {
		this.parameter = value;
	}
}
```

### Example
```js
Class Employee {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
}

// Creating an object of the class
var emp01 = new Employee("Mukesh", 25);
```
