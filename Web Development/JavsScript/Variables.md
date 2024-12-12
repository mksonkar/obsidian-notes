1. Variables are used to store reusable data.
2. Each variable must have a unique name called **Identifier**.
### Rules for naming a variable:
	- Name are case sensitive.
	- Begin with a letter, _ or $ symbol. 
	- It cannot be a reserved keyword.

Since JavaScript is a dynamically typed programming language, we don't need to explicitly define the type of a variable. 
	- The type of a variable is automatically decided at runtime. 
### Declaring a variable
There are 3 ways to declare a variable in JS:
1. The **var** keyword : global or function scoped.
2. The **let** keyword : block scoped.
3. The **const** keyword : use for constant values.

[[var, let and const]]

| **var**                                                                        | **let**                                                                                                                                   | **const**                                                                                                                                   |
| ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| The scope of a var variable is functional scope.                               | The scope of a let variable is block scope.                                                                                               | The scope of a const variable is block scope.                                                                                               |
| It can be updated and re-declared into the scope.                              | It can be updated but cannot be re-declared into the scope.                                                                               | It cannot be updated or re-declared into the scope.                                                                                         |
| It can be declared without initialization.                                     | It can be declared without initialization.                                                                                                | It cannot be declared without initialization.                                                                                               |
| It can be accessed without initialization as its default value is “undefined”. | It cannot be accessed without initialization otherwise it will give ‘referenceError’.                                                     | It cannot be accessed without initialization, as it cannot be declared without initialization.                                              |
| hoisting done, with initializing as ‘default’ value                            | Hoisting is done, but not initialized (this is the reason for the error when we access the let variable before declaration/initialization | Hoisting is done, but not initialized (this is the reason for the error when we access the const variable before declaration/initialization |

| **Property**      | **var**                                 | **let**                                         | **const**                                       |
|-------------------|-----------------------------------------|-------------------------------------------------|-------------------------------------------------|
| **Scope**         | Function scoped                         | Block scoped                                    | Block scoped                                    |
| **Updation**      | Mutable                                 | Mutable                                         | Immutable                                       |
| **Redeclaration** | Can be redeclared                       | Cannot be redeclared                            | Cannot be redeclared                            |
| **Hoisting**      | Hoisted at top                          | Hoisted at top                                  | Hoisted at top                                  |
| **Origins**       | Pre ES2015                              | ES2015(ES6)                                     | ES2015(ES6)                                     |
| **Support**       | Supported in the old version of Browser | Not supported in the old version of the Browser | Not supported in the old version of the Browser |
