There are mainly two types of programming languages: 
1. **Statically typed** - Each variable and expression type is already known at compile time. 
		- Eg. C, C++, Java
2. **Dynamically typed** - Each variable and hold different data types. 
		- Eg. Python, JavaScript, Ruby

#Data-types

JavaScript is a dynamically typed scripting language. 

The latest #ECMAScript standard defines 8 data types: 
7 Primitive data types 
1 Non-primitive data type. 

### Primitive Data types 
- Number
- String
- Boolean
- Null
- Undefined
- Symbol
- BigInt

### Non-Primitive data types
- Object

#### Number
```js
let num = 2; //Integer
let num2 = 1.3; //Floating point number
let num3 = Infinity; 
let num4 = 'something'/2; //NaN
```

#### String
```js
let str = "Hello There";
let str2 = 'Single quotes also works';
let str3 = `can embed another variable in a string ${str}`;
```

#### Boolean 
```js
let value = true;
let value2 = false;
```

#### NULL
The null data type is a special value that represents *'nothing'*, *'empty'* or *'value unknown'*.

```js
let age = null; 
```

#### Undefined
Undefined simply means *value not defined*.
```js
let x;
console.log(x); //undefined
```

#### Object 
Everything in JS is basically an object. 

```js
//method 1 - using object constructor syntax
let person = new Object(); 
//method 2 - using object literal syntax
let person = {} //empty object
```
