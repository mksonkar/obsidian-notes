## Transpiler
A transpiler is a source to source converter. 
It translates one source code to another source code.

It can parse modern code and re-write it using older syntax, so that it works with older engines.

For e.g. **Babel**

When new JavaScript features roll on, you can use them right away without worrying 
if they will be supported in older browsers because Babel can be used to convert the modern source code into
older source code so it can be supported by older browser engines.

#### Use cases:
- **ES6+ to ES5 (Backward compatibility)** : Newer versions of JavaScript ES6+, can introduce newer syntax and features that may not be supported by older or legacy browsers. A transpiler like Babel can convert the newer JavaScript code into older JavaScript code so that it can be supported by legacy browsers.
		For e.g. Features like arrow functions, let, const, class 
