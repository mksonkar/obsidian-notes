- What is purity?
	A pure function has the following characteristics - 
		- **It minds its own business.** It does not change any objects or variables that existed before it was called.
		- **Same inputs, same outputs.** Given the same inputs, a pure function should always return the same result.
	React is designed around this concept.
	It assumes that every component you write is a pure function.
	ie. every React components must return the same JSX given the same inputs.
		
- How purity helps avoid bugs?
- How to keep components pure?
	- by keeping changes out of the render phase
- How to use Strict Mode to find mistakes in your components?

