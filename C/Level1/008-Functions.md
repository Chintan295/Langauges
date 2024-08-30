# Functions

Functions in C are reusable blocks of code that take arguments and return values. They are used to:
* Organize code into logical blocks
* Reduce code duplication
* Improve code readability
* Enhance code reusability

```c
int add(int a, int b) {
    return a + b;
}
add(5, 3); // call function
```

#### Function arguments
Pass-by-value: The function receives a copy of the argument.
Pass-by-reference: The function receives a pointer to the argument.
```c
void increment(int x) { x = x + 1; } // pass-by-value
void increment_ptr(int* x) { (*x) = (*x) + 1; } // pass-by-reference
```

#### Function pointers
Declare a pointer to a function. Use the pointer to call the function.
```c
int add(int a, int b) { return a + b; }
int (*ptr)(int, int) = &add; // declare pointer
int result = ptr(2, 3); // use pointer to call function
```

####  Recursive functions
Function calls itself
```c
int factorial(int n) { 
    if (n == 0) return 1; 
    else return n * factorial(n-1); 
}
```

#### Function Scope and Linkage
**Scope**
* The region where a variable or function is defined.
* Determines the visibility and accessibility of a variable or function.

**Linkage**
* The visibility of a variable or function outside its scope.
* Determines whether a variable or function can be accessed from other parts of the program.

**Types of Linkage:**

* Internal Linkage:
    * Variables and functions with internal linkage are only visible within the translation unit (source file).
    * when variable or functions declared with static keyword
* External Linkage: 
    * Variables and functions with external linkage are visible from other translation units (source files).
    * when variable or functions declared non-static

#### Inline functions
* The compiler expands the function inline at the point of call.
```c
inline int add(int a, int b) { return a + b; }
```

#### Variadic functions
* A function that takes a variable number of arguments.
```c
int printf(const char* format, ...) { 
    ... 
}
```

#### Static functions
* A function that is only visible within the file it is defined in.
```c
static int add(int a, int b) { return a + b; }
```