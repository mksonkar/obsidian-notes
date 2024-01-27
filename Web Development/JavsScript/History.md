1. In 1995, Netscape programmer **Brendan Eich** began the development of a scripting language called _Mocha_ which was later renamed as **_LiveScript_**. 

2. Netscape came in development collaboration with Suns Microsystems (creator of Java) to complete the development of LiveScript for Netscape Navigator 2. 

3. Before its release Netscape changed the name of LiveScript to JavaScript to capitalise on the buzz Java was getting from the press.

4. JavaScript 1.0 became a hit and Netscape established itself as a leading company in the market. 

5. At this time, Microsoft decided to put more resources in its browser Internet Explorer and came up with a different implementation of JavaScript and named it JScript to avoid any licencing issues with Netscape.

6. This created two different versions of JavaScript as there was no standard for governing syntax and features of JavaScript at the time.

7. Seeing the issue this could create in future, in 1997 JavaScript 1.1 was submitted to **European Computer Manufacturers Association (ECMA)** for standardisation. 

8. A committee was created consisting of programmers from Netscape, Sun, Microsoft, BORLAND, and others to standardise the syntax and semantics of a general purpose, cross-platform, vendor-neutral scripting language.

9. After a few months of meeting the committee created **ECMA-262**, a standard for the scripting language ECMAScript.

10. The next year, ISO (International Organisation for Standardisation) also adopted ECMAScript as a standard.

## JavaScript Implementations

Though JavaScript and ECMAScript are often used synonymously, JavaScript is much more than just what is defined in ECMA-262. 

A complete JavaScript implementation is made up of: 
1. The core (ECMAScript)
2. The Document Object Model (DOM)
3. The Browser Object Model (BOM)

![[c01f001.png]]

## ECMAScript
- ECMAScript is the language defined in ECMA-262. 
- It isn't tied to web browsers.
- In fact, ECMAScript has no methods for input or output.
- ECMA-262 defines ECMAScript as a base language upon which more robust scripting languages can be built. 
- ie. it is a standard for developing scripting languages.
- Web browsers are just *one host environment* where ECMAScript implementation can exist. 
	- A host environment provides the base implementation of ECMAScript and implementation extensions designed to interface with the environment itself.
	- Extensions such as the DOM, use ECMAScript's core types and syntax to provide additional functionality that's more specific to the environment.
- Other host environments include NodeJS - a server-side JavaScript platform, and almost obsolete Adobe Flash. 

#### What does ECMA-262 specify if it doesn't reference web browsers?
- Syntax
- Types
- Keywords
- Statements
- Reserved words
- Operators
- Global Objects

#### ECMAScript Editions
- ECMAScript has had many editions since its inception. 

- The **sixth edition of ECMA-262**, referred to as **ES6**, **ES2015**, or **ES Harmony** was published in **June 2015** added most important enhancements to ECMAScript since its inception.

- ES6 added: 
	- formal support for classes
	- modules
	- iterators
	- generators
	- **arrow function**
	- **promises**
	- reflections
	- proxies, etc...

- ES6 also marked the annual releases of ECMAScript editions. 
- As a result, instead of being referred as ES5, ES6, new editions were named after the year they are released like - ES2020, ES2021, etc. 
- Recent editions have added
	- More array and string methods. 
	- async/await
	- dynamic module imports, and 
	- new numerical types
