![[Screenshot_20241211_115015.png]]

## Scope
- **var**: function or global scope
- **let** and **const**: block scope

## Initialisation
- const must be initialised with a value, 
- var and let don't need to be initialised with a value.
```js
var foo; // Ok
let bar; // Ok
const baz; // SyntaxError: Missing initializer in const declaration
```
## Re-declaration
Only var can be re-declared,
let and const cannot be re-declared.
```js
var foo = 1;
var foo = 2;
console.log(foo); // 2

let baz = 3;
let baz = 4; // Uncaught SyntaxError: Identifier 'baz' has already been declared
```
## Re-initialisation
const cannot be re-initialised,
let and const can be re-initialised
```js
var foo = 1;
foo = 2; // This is fine.

let bar = 3;
bar = 4; // This is fine.

const baz = 5;
baz = 6; // Uncaught TypeError: Assignment to constant variable.
```

## Access before declaration
`var`, `let` and `const` declared variables are all ***hoisted***.

- var and let is auto-initialised with `undefined`
```js
var a;
let b;
console.log(a); // undefined
console.log(b); // undefined
```
- var can be accessed before initialisation,
- let and const cannot, and will raise `ReferenceError` 
- because they are in "**temporal dead zone**" from the start of the block until the declaration is processed.

```js
console.log(a); // undefined
var a = 1;

console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 2;

console.log(c); // ReferenceError: Cannot access 'c' before initialization
const c = 3
```
