- Using object literals if fine if you want to create one or two objects.
- But if you want to create multiple objects, using object literals is not adequate, 
	- as you need to write the same code again and again for each object.
	- and, if you want to update or add a property, you'll need to make sure to make that change in every object literal.

Ideally, we want to create a "*shape of an object*" - the set of methods and properties it can have, and then create as many objects as we want from that shape.

The first version of this is using a function:
```js
function createPerson(name) {
	const obj  = {};
	obj.name = name;
	obj.introduceSelf = function() {
		console.log(`Hi! I'm ${this.name}.`);
	}
	return obj;
}
```
This function creates and returns a new object each time we call it.
This is a very common pattern for creating objects.

```js
const p1 = createPerson("Mukesh");
p1.name; // Mukesh
p1.introduceSelf(); // "Hi! I'm Mukesh"
```
This works fine but it is long winded, 
we have to create an empty object, initialize it and return it.
A better way is to use a **constructor**.

*Def* - A constructor is just a function called using the `new` keyword.

When you call a constructor, it will:
- create a new object
- bind `this` to the new object, so that you can refer `this` in your constructor code.
- run the code in the constructor.
- return the new object.

```js
function Person(name) {
	this.name = name;
	this.introduceSelf = function () {
		console.log(`Hi! I'm ${this.name}.);	
	}
}
```
By convention we start constructor name with a capital letter.
to call the `Person()` as a constructor, we use the `new` keyword.
```js
const p1 = new Person("Mukesh");
p1.name;
p1.introduceSelf();
```
### Objects are everywhere
In JavaScript objects are everywhere.
when you create string, it is created as an instance of String object and therefore has several methods and properties available on it.
```js
const myDiv = document.createElement('div');
const myVideo = document.querySelector('video');
```
- when accessing DOM (document object model) like this, you are using methods available on Document object.

- For each webpage loaded, an instance of Document is created, called document, 
- which represents the entire page's structure, content and other features such as its URL.
- This is why, it has several methods and properties available on it.
- Same is true for Array, Math etc.