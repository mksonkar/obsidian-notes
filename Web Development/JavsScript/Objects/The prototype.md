1. In JavaScript all objects have a prototype
2. A prototype is just another object
	The value of the Object Constructor's `.prototype` property (i.e. `Player.prototype`) contains the prototype object.
1. that the original object inherits from.
	 ie. the original object has access to all of the prototype's methods and properties.

### Accessing an object's prototype.
```js
Object.getPrototypeOf(player1) === Player.prototype;
```

### Object.getPrototypeOf() vs .\_\_proto\_\_  vs \[\[Prototype\]\]
- `__proto__` is the same as `Object.getPrototypeOf()`
- It is a non-standard way and is depricated.

```js
player1.__proto__ === Player.prototype;
```

- `[[Prototype]]` may be found in legacy code.
- `player1.[[Prototype]]` is another way of talking about `.__proto__` property.

### Prototypal inheritance
_What use is an object's prototype?_
_What is the use of defining functions and properties on the prototype?_

We can narrow it down to two reasons?
1. We can define properties and functions common among all objects on the prototype **to save memory.**
2. The second reason is prototypal inheritance. All objects inherit from the prototype object, this helps in reducing code redundancy i.e. writing same methods and properties separately for every object.
