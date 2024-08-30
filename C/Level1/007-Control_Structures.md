# Control structures

Control structures allow you to:
* Make decisions based on conditions
* Repeat code using loops
* Exit loops or functions
* Jump to specific code locations
* Organize code into reusable functions

#### Conditional Statements:
* if statement: 

        if (condition) { 
            //code 
        }

* if-else statement: 

        if (condition) { 
            // code 
        } else { 
            // code 
        }

* switch statement: 

        switch (expression) { 
            case value: 
            // code; 
            break; 
            default: 
            code; 
        }

#### Loops

* while loop: 

        while (condition) { 
            code 
        }

* for loop: 

        for (init; condition; increment) { 
            code 
        }

* do-while loop: 

        do { 
            code 
        } while (condition);

#### Jump Statements

* break: exits a loop or switch statement
* continue: skips to the next iteration of a loop
* return: exits a function and returns a value
* goto: jumps to a labeled statement

#### Subroutines:
Functions: reusable blocks of code that take arguments and return values

#### Goto Statement:
* goto label;
* Jumps to a labeled statement
* label:

```c
int main() {
    goto skip;
    printf("This will not be printed\n");
    skip:
    printf("This will be printed\n");
    return 0;
}
```

#### Async/await

```c
#include <libasync.h>
int main() {
    async_start();
    printf("This will be printed first\n");
    async_wait();
    printf("This will be printed second\n");
    return 0;
}
```

#### Try-Catch

```c
#include <setjmp.h>
jmp_buf buf;

int main() {
    setjmp(buf);
    printf("This will be printed first\n");
    longjmp(buf, 1);
    printf("This will not be printed\n");
    return 0;
}
```
    