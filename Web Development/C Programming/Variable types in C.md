### Static variable

- A _static_ variable has lifetime till the end of the program. It can only be initialised once. 
- Once its initialised, further initialisation will have no affect. 
- It's default value is 0. (as opposed to a local variable whose default value is garbage value.)
- It can be a local or global variable depending on where its defined. 
- For example: 
```c
#include <stdio.h>

void test()
{
	int x = 10;
	static int y = 10; // defining a static variable
	
	x += 10;
	y += 10;
	
	printf("\tLocal: %d\n\tStatic: %d\n", x, y);
}

int main()
{
	printf("First call: \n");
	function();
	
	printf("Second call: \n");
	function();
	
	printf("Third call: \n");
	function();
	
	return 0;
}
```
Output: 
```
First call: 
	Local: 20
	Static: 20
Second call: 
	Local: 20
	Static: 30
Third call: 
	Local: 20
	Static: 40
```

In this example, the function `test()` defines a local variable `x` and a static variable `y`, and sets their value to `x = 10` and `y = 10`.
```c
	void test() 
	{
		int x = 10;
		static int y = 10;
	}
	...
```
Explanation: 
- In the `main` function, the `test()` function is called three times. 
- In the output you can observe that the variable `x` is defined each time `test()` is called and assigned a value of `x = 10`. After incrementing its value by 10, 20 is printed on the output and the variable is destroyed after the function call ends because life of a local variable is till the end of block.
- Whereas, when the static variable y is initialised the first time when `test()` is called, it's value is set to 10, and after incrementing by 10, 20 is printed on the output, but the static variable is not destroyed (ie. it sticks around as it's life is till end of program) 
- So far we can't see a difference between the two variables x and y.
- But when `test()` is called again for the second time, we can see that the variable `x` is initialised again and its value is set to `x = 10` again, and after incrementing it prints the same value as before. 
- Whereas, the static variable `y` is not initialised again because it wasn't destroyed from before. Hence, it's value is 20 from the last call. Now its incremented again and its new value 30 is printed on the output. j


### Automatic variable

- All local variables are auto by default.
- Their scope is local and lifetime till end of block.
- Eg. 
```c 
	 auto int a = 10;
	 int b = 10;
```
both are same types of variable.

### External variable

- External variables can be shared between multiple files.
- Their scope is global and they exist between multiple files. 
- Eg. 
```c
	extern int a;
```
- Here, no memory is allocated for a, only the property of the variable is announced. 
- Multiple declarations of extern variable is allowed. (which is not the case for automatic variables).
- 
### Register variable
- Register variables are stored in the CPU register instead of a conventional storage place like RAM. 
- They are local scoped and life is till end of block.
- Their default value is garbage value. 

xyz testing line. delete afterwards
