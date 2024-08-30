# Structures

* In C, a structure (also known as a struct) is a user-defined data type that allows you to combine multiple variables of different types into a single unit.
* A structure is a collection of variables that can be accessed individually or as a whole.

```c
// Declaring a structure
struct Person {
    int age;
    char name[20];
    float height;
};

// Accessing members
struct Person person;
person.age = 25;
person.name = "John";
person.height = 5.9;

// Structure arrays
struct Person people[10];

// Structure pointers
struct Person *personPtr;
personPtr = (struct Person*) malloc(sizeof(struct Person));
personPtr->age = 25;
personPtr->name = "John";
personPtr->height = 5.9;


// Struct Typedef
typedef struct Person {
    int age;
    char name[20];
    float height;
} Person, Person*;

Person person1; // declares a variable of type Person
Person* person1Ptr = &person1; // declares a pointer to Person and assigns it the address of person1


```

### Structure Benefits
* Encapsulation: Structures allow you to group related variables together, making it easier to manage and maintain code.
* Code reuse: Structures can be reused throughout a program, reducing code duplication.
* Flexibility: Structures can be easily modified or extended to meet changing requirements.

### Structure size
* total amount of memory required to store all its members.
* sum of the sizes of its individual members, plus any padding bytes that may be added to ensure proper alignment.
* Padding is the process of adding extra bytes to a structure to ensure that its members are properly aligned in memory.

```c
struct Person {
    int age;        // 4 Bytes
    char name[20];  // 20 bytes
    float height;   // 4 bytes
};
```

**How to calculate structure size?**
* Finalise alignment using largest variable size(1(default), 2, 4 or 8)
* Arrange all variables sequencially using alignment


```c
struct Person {
    int age;        // 4 Bytes
    char name[20];  // 20 bytes
    float height;   // 4 bytes
};
// Size = 28 with 4 Bytes allignment

struct example {
    int a;              // 4 Bytes
    char b;             // 1 Byte + 3 Bytes
    char str_name[20];  // 20 Bytes + 4 Bytes
    double c;           // 8 Bytes
    float d;            // 4 Bytes + 4 Bytes
};
// Size = 48, Alignment 8 Bytes

struct Address {
    char street[20];    // 20 Bytes => 2*8 + 4 = 20
    char city[20];      // 20 Bytes => 4 + 2*8 = 20
    char state[20];     // 20 Bytes => 2*8 + 4 = 20
    int zip;            // 4 Bytes => 4         = 4
    double x;           // 8 bytes => 8         = 8
};
// Size = 72, alignment 8 Bytes

struct Person {
    int age;                // 4 Bytes
    char name[20];          // 4 + 8*2 Bytes
    struct Address address; // 8*9 Bytes
    double height;          // 8 Bytes
};
// Size = 104, alignment 8 bytes

struct example {
    int a;              // 4 Bytes
    char b;             // 1 Byte
    char str_name[20];  // 20 Bytes
    float d;            // 4 Bytes
}__attribute__((packed));
// Size = 29, Alignment 1 Bytes

struct example {
    int a;              // 4 Bytes
    char b;             // 1 Byte + 1 Byte
    char str_name[20];  // 20 Bytes
    float d;            // 4 Bytes
}__attribute__((packed, aligned(2)));
// Size = 30, Alignment 2 Bytes

```

* ![How to calculate structure size?](https://www.geeksforgeeks.org/is-sizeof-for-a-struct-equal-to-the-sum-of-sizeof-of-each-member/)

**Why is padding important?**
* Performance -  Proper alignment can improve performance by reducing the number of memory accesses required.
* Correctness - Improper alignment can lead to incorrect behavior or crashes.
* Portability - Different compilers and architectures may have different alignment requirements, so padding ensures that your code is portable.

**How to minimize padding?**
* Reorder members
* Use packed structures: Use the __attribute__((packed)) attribute to tell the compiler to pack the structure tightly, without padding.
* Use bitfields: Use bitfields to store small integer values in a compact format.



