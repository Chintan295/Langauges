# Pointer arithmetic

```c
#include <stdio.h>
int main()
{
    int arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int *ptr = arr;

    // Pointer increment
    ptr++;
    printf("%d\n", *ptr); // prints 2

    // Pointer decrement
    ptr--;
    printf("%d\n", *ptr); // prints 1

    // Pointer addition with an integer
    ptr = ptr + 3;
    printf("%d\n", *ptr); // prints 4

    // Pointer subtraction with an integer
    ptr = ptr - 2;
    printf("%d\n", *ptr); // prints 2

    // Pointer difference
    int *ptr2 = (arr + 7);
    printf("%ld\n", (ptr2 - ptr)); // prints 6

    // Pointer array indexing
    printf("%d\n", ptr[5]); // prints 7

    // Pointer comparision
    if(ptr == ptr2) {
        printf("ptr and ptr2 are equal\n");
    } else {
        printf("ptr and ptr2 are not equal\n");
    }

    // Pointer comparision with NULL
    if(ptr == NULL) {
        printf("ptr is NULL\n");
    } else {
        printf("ptr is NON-NULL\n");
    }

    // Pointer arithmetic with intptr_t or uintptr_t(pointer as an integer variable)
    uintptr_t ptr3 = arr;

    ptr3 = ptr3 + 20;           // Add
    ptr3 = ptr3*5 - ptr3*4;     // Multiply
    ptr3 = (ptr3*4/4);          // divide
    ptr3 = ptr3 - 20;           // Subtract

    printf("%d\n", *((int*)ptr3)); // prints 1
}
```