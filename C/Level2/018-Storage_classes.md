# Storage classes

* Storage class allows us to determine a variable's or function's scope, visibility, and lifetime.
* Whenever we define a variable in the program we also define its data type and its storage class.
* Storage class determindes where data will be stored in memory

### Auto
* default storage class for local variables
* variables is destroyed when the function returns.
* will be stored in RAM
* Initialized with garbage value.
* Bad practice to use auto keyword because it has different meaning in cpp. So program not work when compiled as c++ code.

```c
auto int x;
```

### Register
* Same functionality as auto except compiler tries to store these variables in the register of the microprocessor if a free register is available.
* Allows faster access
* Address of register variable can not be obtained by pointers
* can't be used to declare global variables

```c
register int x;
```

### Extern
* The extern storage class is used to declare variables that are defined outside the current source file.
* extern variable is nothing but a global variable initialized with a legal value where it is declared in order to be used elsewhere.
* It can be used to declare local variables also.

```c
extern int x;  // x is declared and initialized in different file
```

### Static
* Static variables have the property of preserving their value even after they are out of their scope.
* Used to retain value between function calls
* they are initialized only once and exist till the termination of the program
* default value is 0
* stored in data segment
* static global vars/funs can not be accessed from another file 
* should be initialized with compile time constant(can not call function in initialization)
* variable inside a structure can not be static

```c
static int x;
```