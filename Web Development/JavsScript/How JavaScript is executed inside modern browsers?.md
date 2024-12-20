Every web browser has a JavaScript engine which is responsible for executing JavaScript code.

For e.g. - 
Chrome and Edge - V8 engine
Firefox - SpiderMonkey
Safari -  JavaScriptCore (Nitro)
Legacy Edge - Chakra

![[Pasted image 20241219160700.png]]
The execution of JavaScript by a browser involves the following steps:
## 1. **Parsing**
When the browser encounters JavaScript code, the engine parses the code in two phases:
	a. **Lexical analysis**: The JavaScript code is broken down into tokens.
	b. **Parsing**: These tokens are then converted into an **Abstract Syntax Tree (AST)**. The AST is like the blueprint of the entire code.
	For e.g. 
```js
	let x = 10;
		```
	The AST would look something like this:
```
	VariableDeclaration
	  ├─ Identifier (x)
	  └─ Literal (10)
```

## 2. Compilation 
(JIT compilation)
JavaScript is often said to be an interpreted language, because in early days, JavaScript engines directly interpreted code line by line.
This made execution simple but slow for complex applications.

Modern JavaScript engines do not interpret JavaScript code directly as they did in early days.
Instead they compile it for better performance.

The compilation occurs as such:
a. **Bytecode**: 
- After parsing, the AST is converted into an intermediate code called bytecode.
- This bytecode is platform-independent and more efficient than raw JavaScript.
- The bytecode is then executed by the interpreter part of the JavaScript engine (e.g. Ignition in V8).

b. **Just-In-Time (JIT) Compilation**
- JIT is a hybrid approach that combines the interpretation and compilation.
- JIT compiles parts of code just before execution at runtime.
- As the code runs, the engine keeps track of **hot code** (frequently executed code, like loops and function calls).
- For hot code, JIT complies the bytecode into machine code at runtime.
- This **profiling** into hot and cold code, allows the user to optimise where necessary.
- e.g. V8 uses **TurboFan** for this optimisation process.

c. **Execution**
- Once the bytecode or machine code is ready, the engine executes it step by step.
- **Call stack**: It is a data structure to keep track of where the engine is in the program's execution.
		When a function is called, it is added to the top of the stack. Once the function finishes, it's removed from the stack.
- **Heap**: In the heap data structure, objects, arrays and other complex data are stored in memory.
	The heap is also used for dynamic allocations (e.g. creating new objects at runtime)
- **Garbage Collection**: It is a process where the engine automatically cleans up memory that is no longer in use.

d. **Optimisation**
- The JavaScript engine continuously monitors code while it's running to improve performance.
- It profiles the entire code, for **hot code**, and optimises it for better performance.