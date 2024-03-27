JavaScript getters and setters are special methods that provide access to object properties.

Getters are used to read values of properties, and
Setters are used to write values of properties.

```js
let obj = {
	get propName() {
	// getter, the code executed on getting obj.propName	
	},
	set propName() {
	// setter, the code executed on setting obj.propName = value	
	},
};
```

The getter works when obj.propName is read, and 
the setter works when obj.propName is assigned.

