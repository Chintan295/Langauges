# Unions

* Unions in C are a type of data structure that allows storing different types of data in the same memory location.
* Only one member of the union can be used at a time.
* Unions are useful for conserving memory.
* Unions can be used in structures and classes to create more complex data types.

```c
// Declaration
union Data {
    int i;
    float f;
    char str[20];
};

// Accessing an union data
union Data data;
data.i = 10;
printf("%d", data.i); // prints 10

data.f = 3.14;
printf("%f", data.f); // prints 3.14

strcpy(data.str, "Hello");
printf("%s", data.str); // prints "Hello"

// Size of the union is largest element in union
printf("%lu", sizeof(union Data)); // 20

```

### Usecase
Suppose we want to implement a binary tree data structure where each leaf node has a double data value, while each internal node has pointers to two children, but no data. If we declare this as: 

```c
struct NODE {
	struct NODE* left;
	struct NODE* right;
	double data;        // this is not required for internal nodes
};
```

* Every node requires 24 bytes, with half the bytes wasted for each type of node. It can be optimised as below.

```c
struct NODE {
	bool is_leaf;
	union {
		struct {
			struct NODE* left;
			struct NODE* right;
		} internal;
		double data;
	} info;
};
```

* Size = 17 Bytes without padding