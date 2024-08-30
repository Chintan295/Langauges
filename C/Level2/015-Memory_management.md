# Memory management

Memory management in C refers to the process of dynamically allocating and deallocating memory for variables and data structures.

### Memory Management Techniques
* __Dynamic Memory Allocation__: Use malloc() to allocate memory dynamically.
* __Memory Pools__: Use a pool of memory to allocate and deallocate memory blocks.
* __Stack memory Allocation__: Use the stack to allocate memory for local variables.
* __Garbage Collection__: Implement a garbage collector to automatically manage memory.

### Best practices
* Use malloc() and free() correctly.
* Check for memory allocation errors.
* Avoid memory leaks and dangling pointers(non-null pointer after memory deallocation).
* Use memory debugging tools.

### Allocation memory

#### malloc()

* It is used to dynamically allocate a block of memory of a specified size.
* returns pointer to the beginning of the allocated memory block, or NULL if the allocation fails.
* malloc does not initialize the memory block, so it's up to the programmer to initialize it before using it.
* It uses sbrk or brk system calls internally

```c
int* ptr = (int*) malloc(sizeof(int));
if(ptr == NULL) {
    printf("Allocation failed\n");
}
```

**How it works?**

When you call malloc, it searches for a contiguous block of free memory in the heap that is large enough to satisfy the requested size. If such a block is found, malloc returns a pointer to the beginning of that block. If no such block is found, malloc returns NULL.

**Best practices**
* Always check the return value of malloc for NULL.
* Use sizeof to ensure the correct size is allocated.
* Avoid using malloc for small allocations, as it can be slower than using the stack.
* Use free to release the memory when it's no longer needed.

#### calloc()

* It is used to dynamically allocate a block of memory for an array of elements of a specified size.
* returns pointer to the beginning of the allocated memory block, or NULL if the allocation fails.
* calloc initializes the memory block to zero, unlike malloc which leaves the memory uninitialized.
* It uses sbrk or brk system calls internally

```c
int* arr = (int*) calloc(10, sizeof(int));
if(arr == NULL) {
    printf("Allocation failed\n");
}
```
**How it works?**
When you call calloc, it allocates a block of memory large enough to hold given number of elements, each of given size. The memory block is initialized to zero.

#### Key differences between malloc and calloc
* malloc does not initialize the memory block, while calloc initializes it to zero.
* calloc takes two parameters (num and size), while malloc takes only one parameter (size).

#### realloc()

* It is used to change the size of a previously allocated block of memory.
* returns a pointer to the reallocated block of memory, or NULL if the reallocation fails.
* If realloc fails, the original block of memory remains unchanged.
* If the new size is larger than the original size, realloc initializes the additional memory to zero.
* Data can be lost in case the new size is smaller than the original size.

```c
int* arr = (int*) malloc(5 * sizeof(int));
// ...
arr = (int*) realloc(arr, 10 * sizeof(int));
```

**When new block is larger** - allocates a new block of memory and copies the contents of the original block to the new block and initialize extra memory to 0
**When new block is smaller** - truncate existing block


### Memory deallocation

#### realloc

#### free()
* It is used to release a block of memory that was previously allocated using malloc, calloc, or realloc.
* It allows the operating system to reclaim the memory
* free only releases the memory block, it does not delete the pointer itself.
* Accessing freed memory leads to an undefined behaviour.
* free can be called multiple times on the same pointer, but this is not recommended as it can lead to memory leaks.

```c
int* arr = (int*) malloc(5 * sizeof(int));
// ...
free(arr);
```

**How it works?**
When you call free, it releases the block of memory pointed to by ptr back to the operating system. The memory is then available for future allocations.

**Best practices**
* Always call free when you are done using a block of memory.
* Use free to release memory allocated using malloc, calloc, or realloc.
* Be aware of the potential for memory leaks if free is not called.
* Use tools such as Valgrind to detect memory leaks.

### Memory fragmentation
Memory fragmentation occurs when memory is broken into small, non-contiguous blocks. This can cause your program to run slowly or crash.

### Memory alignment
Memory alignment refers to the way memory is aligned on word boundaries. Proper alignment can improve performance and prevent crashes.