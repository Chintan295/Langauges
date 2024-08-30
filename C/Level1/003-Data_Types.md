# Data Types

A data type specifies the type of data that can be stored in a variable.

### Primary (Basic) Data Types

* Range depends on size(capacity) of data type(for ex. 4 bytes = -2^31 to 2^31-1)

* __int(%d)__: 4 bytes in 32-bit, 4 bytes in 64-bit, range: -2147483648 to 2147483647, format specifier: %d
* __unsigned int(%u)__: 4 bytes in 32-bit, 4 bytes in 64-bit, range: 0 to 4294967295, format specifier: %u
* __short int(%hd)__: 2 bytes in 32-bit, 2 bytes in 64-bit, range: -32768 to 32767, format specifier: %hd
* __unsigned short int(%hu)__: 2 bytes in 32-bit, 2 bytes in 64-bit, range: 0 to 65535, format specifier: %hu
* __long int(%ld)__: 4 bytes in 32-bit, 8 bytes in 64-bit, range: -2147483648 to 2147483647, format specifier: %ld
* __unsigned long int(%lu)__: 4 bytes in 32-bit, 8 bytes in 64-bit, range: 0 to 4294967295, format specifier: %lu
* __long long int(%lld)__: 8 bytes in 32-bit, 8 bytes in 64-bit, range: -9223372036854775808 to 9223372036854775807, format specifier: %lld
* __unsigned long long int(%llu)__: 8 bytes in 32-bit, 8 bytes in 64-bit, range: 0 to 18446744073709551615, format specifier: %llu
* __char(%c)__: 1 byte in 32-bit, 1 byte in 64-bit, range: -128 to 127, format specifier: %c
* __unsigned char(%c)__: 1 byte in 32-bit, 1 byte in 64-bit, range: 0 to 255, format specifier: %c
* __float(%f)__: 4 bytes in 32-bit, 4 bytes in 64-bit, range: 1.175494351e-38 to 3.402823466e+38, format specifier: %f
* __double(%lf)__: 8 bytes in 32-bit, 8 bytes in 64-bit, range: 2.2250738585072014e-308 to 1.7976931348623157e+308, format specifier: %lf
* __long double(%Lf)__: 12 bytes in 32-bit, 16 bytes in 64-bit, range: 1.189731495357231765e-4932 to 1.189731495357231765e+4932, format specifier: %Lf
* __bool(%d)__: 1 byte in 32-bit, 1 byte in 64-bit, range: true or false, format specifier: %d

Note: stdbool.h required to be included for bool

### Derived Data Types

* __int *(%p)__: 4 bytes in 32-bit, 8 bytes in 64-bit, pointer to int, format specifier: %p
* __char *(%s)__: 4 bytes in 32-bit, 8 bytes in 64-bit, pointer to char, format specifier: %s
* __void *(%p)__: 4 bytes in 32-bit, 8 bytes in 64-bit, pointer to void, format specifier: %p
* __int \[\](%d)__: depends on array size, array of ints, format specifier: %d
* __char \[\](%s)__: depends on array size, array of chars, format specifier: %s
* __struct__: depends on struct members, user-defined data type, format specifier: %d
* __union__: depends on union members, user-defined data type, format specifier: %d
* __int ()__: depends on function return type, function returning int, format specifier: %d
* __void ()__: depends on function return type, function returning void, format specifier: %d

### User-Defined Data Types
* __enum__: 4 bytes in 32-bit, 4 bytes in 64-bit, user-defined enumeration, format specifier: %d
* __typedef__: depends on underlying type, alias for existing data type, format specifier: depends on underlying type

### How data stored in memory

**Signed**:
* uses two's complement representation
* positive: with MSB 0
    * 5: 00000000 00000000 00000000 00000101
* negative: with MSB 1 and two's compliment of a number
    * -5: 11111111 11111111 11111111 11111011

**Unsigned**:
* uses binary representation
* 5: 00000000 00000000 00000000 00000101

### Reference

* [https://docs.oracle.com/cd/E19253-01/817-6223/chp-typeopexpr-2/index.html](https://docs.oracle.com/cd/E19253-01/817-6223/chp-typeopexpr-2/index.html)