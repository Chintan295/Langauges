# Complex pointer

1. Start from the variable name
2. Look for parentheses and evaluate the expression inside them first.
3. Identify the pointer operators (* and []) and their precedence.

Priority:
* Variable name
* ()
* *
* []

```c
    void ( *(*f[]) () ) ();  by applying the above rules:  
    void ( *(*f[]) () ) ();        "f is"  
              ^  
    void ( *(*f[]) () ) ();        "f is an array"  
               ^^ 
    void ( *(*f[]) () ) ();        "f is an array of pointers" 
             ^    
    void ( *(*f[]) () ) ();        "f is an array of pointers to function"   
                   ^^     
    void ( *(*f[]) () ) ();        "f is an array of pointers to function returning pointer"
           ^   
    void ( *(*f[]) () ) ();        "f is an array of pointers to function returning pointer to function" 
                        ^^              
    void ( *(*f[]) () ) ();        "f is an array of pointers to function returning pointer to function returning `void`"  
    ^^^^
```


* ptr is pointer to an int
```c
int *ptr;
```

* ptr is ointer to a pointer to an int
```c
int **ptr;
```

* arr is array of integer pointer
```c
int *arr[10];
```

* ptr is pointer to an array of length n
```c
int (*ptr)[10];
```

* ptr is pointer to an array of 10 pointers to integers.
```c
int *(*ptr)[10];
```

* ptr is pointer to an array of 5 pointers to arrays of 10 pointers to integers.
```c
int *(*(*ptr)[5])[10];
```

* fun is pointer to a function with argument int and return type int
```c
int (*fun)(int);
```

* fun is function returning pointer to a function with argument int returning pointer to function with argument int returning int
```c
int (*(*fun(int))(int))(int);
```

* fun is pointer array of 10 function pointers with void argument returning pointer to function with argument int returning int
```c
int (*(*fun[10])(void))(int);
```

* ptr is pointer to an array of 10 pointers to arrays of 5 pointers to functions that take two integers as arguments and return an integer.
```c
int (*(*(*ptr)[10])[5])(int, int);
```

* fun is a function with int argument returning pointer to a function with int argument returning pointer to a function with int argument returning pointer to a function with 2 int arguments returning int.
```c
int *(*(*(*fun(int))(int))(int))(int, int);
```