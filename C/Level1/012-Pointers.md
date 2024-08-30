# Pointers

Pointers are variables that store the memory address of another variable. They are used to access and manipulate the value stored at that memory address.

```c
int *ptr;  // Declaration
int x = 5;
ptr = &x;  // Assignment or initialization
printf("%d", *ptr); // accessing value by dereferencing operator(*)
```

### Types of pointers

1. __Null pointer__: int* ptr = NULL;
2. __Wild pointer__: int *ptr; // wild pointer
3. __Dangling pointer__:  points to a memory location that has already been deleted or freed
4. __void pointer__: void *ptr -> can point any data type
5. __Array pointer__: points to the base location of array
6. __Function pointer__: int (*add)(int, int);
7. __Pointer to pointer__: int **ptr;
