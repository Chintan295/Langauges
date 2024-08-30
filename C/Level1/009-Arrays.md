# Arrays

Arrays in C are a fundamental data structure that store a collection of elements of the same data type in contiguous memory locations.

```c
int a[10];  // Declaring an array

int a[5] = {1, 2, 3, 4, 5};  // Initializing array
int a[] = {1, 2, 3, 4, 5};
int a[5] = {[0] = 1, [3] = 4}; // designated initializers

a[0] = 5; // Accessing array element
a[x]

int a[10][20]; // Multidimensional array
int a[10][20] = {{1, 2, ... , 10}, {11, 12, ..., 13}, ...};

//size of an array
int size = sizeof(arr);

// length of an array
int length = sizeof(arr) / sizeof(arr[0]);

```

### Array pointers

```c
int *arr_ptr = arr;
*(arr_ptr + index) => arr[index]
```

### Dynamic arrays

```c
int* my_array = malloc(size * sizeof(int));
free(my_array);
```

### Array decay
When an array is passed to a function, it "decays" into a pointer to its first element.

```c
#include<stdio.h>
int fun(int arr[]) {
    printf("%d\n", sizeof(arr)/ sizeof(arr[0])); // 2
}

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    printf("%d\n", sizeof(arr)/ sizeof(arr[0])); // 5
    fun(arr);
}
```

### Array operations

```c
int compare_function(const void* a, const void* b) {
    int x = *((int*)a);
    int y = *((int*)b);
    if (x < y) return -1;
    if (x > y) return 1;
    return 0;
}

// Sorting
int my_array[5] = {3, 2, 5, 1, 4};
qsort(my_array, 5, sizeof(int), compare_function); // my_array = {1, 2, 3, 4, 5}

// Searching
int my_array[5] = {1, 2, 3, 4, 5};
int x = 3;
int result = bsearch(&x, my_array, 5, sizeof(int), compare_function); // result = 2 (index of x in my_array)

// strlen
char str[] = "Hello, World!";
int length = strlen(str); // length = 13

// memcpy
char src[] = "Hello";
char dst[5];
memcpy(dst, src, 5); // copies "Hello" into dst

// memmove
char src[] = "Hello";
char dst[5];
memcpy(dst, src, 5); // copies "Hello" into dst

// memcpy and memmove are similar, but memmove is safer when the source and destination overlap.

// memset
char str[5];
memset(str, 'x', 5); // sets all elements of str to 'x'
```