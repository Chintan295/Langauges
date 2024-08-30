# Type conversion

Type conversion in C refers to the process of converting a value of one data type to another data type.

### Implicit conversion

when one type value is assigned to another type of value, it will be converted implicitly

    int x = 5;      // x is an integer
    float y = x;    // y is a float, and x is implicitly converted to float

### Explicit conversion(casting)

    int x = 5;
    float y = (float)x;  // cast int to float

### Type conversion rules

* integer to double|float
* double|float to integer, but may lose precision
* char to int
* int to char, but may lose information
* Smaller type automatically promoted to larger type when used in expression with larger types:
    * char -> short -> int -> long -> long long int -> float -> double -> long double

### Type promotion
* Type promotion occurs when a value of a smaller type is converted to a larger type.

        char c = 'a';
        int x = c;  // c is promoted to int

### Type demotion
* Type demotion occurs when a value of a larger type is converted to a smaller type.
* demotion may result in loss of information.

        int x = 5;
        char c = x;  // x is demoted to char

