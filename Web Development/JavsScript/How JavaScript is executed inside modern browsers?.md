Every web browser has a JavaScript engine which is responsible for executing JavaScript code.

For e.g. - 
Chrome and Edge - V8 engine
Firefox - SpiderMonkey
Safari -  JavaScriptCore (Nitro)
Legacy Edge - Chakra

The execution of JavaScript by a browser involves the following steps:
## 1. **Parsing**
When the browser encounters JavaScript code, the engine parses the code in two phases:
	a. **Lexical analysis**: The JavaScript code is broken down into tokens.
	b. **Parsing**: These tokens are then converted into an **Abstract Syntax Tree (AST)**. The AST is like the blueprint of the entire code.
	For e.g. - 
```js
	let x = 10;
		```
		```
		VariableDeclaration
		
```
## 2. Compilation 
(JIT compilation)
Although, JavaScript is often said to be an interpreted language, 
modern JavaScript engines do not interpret JavaScript code directly as they did in early days.

Instead they compiler it for better performance.