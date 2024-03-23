Reference for later: https://www.freecodecamp.org/news/what-is-this-in-javascript/
The value of this is determined by how a function is called. (runtime binding).

- it cannot be assigned during runtime, 
- it may be different each time function is called. 

### Function.prototype.bind() 
The Function.prototype.bind() method can set the value of a function's this regardless of how its called.

- arrow functions don't provide their own this binding. (it retains the this value of its enclosing lexical context).

- In a method, _this_ refers to the **owner object** .
- In a function: 
	- in strict mode: _this_ is **undefined**.
	- in non-strict mode: _this_ refers to the **global object**.

### Types of binding in JS
1. Default binding
2. Implicit binding
3. Explicit binding
4. Constructor call binding

#### 1. Default Binding in JS
