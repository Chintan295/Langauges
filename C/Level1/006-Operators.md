# Operators

#### Arithmetic Operators:
* Addition: a + b
* Subtraction: a - b
* Multiplication: a * b
* Division: a / b
* Modulus (remainder): a % b

#### Assignment Operators:
* Simple assignment: a = b
* Addition assignment: a += b
* Subtraction assignment: a -= b
* Multiplication assignment: a *= b
* Division assignment: a /= b
* Modulus assignment: a %= b

#### Comparison Operators:
* Equal to: a == b
* Not equal to: a != b
* Greater than: a > b
* Less than: a < b
* Greater than or equal to: a >= b
* Less than or equal to: a <= b

#### Logical Operators:
* AND: a && b
* OR: a || b
* NOT: !a

#### Bitwise Operators:
* AND: a & b
* OR: a | b
* XOR: a ^ b
* NOT: ~a
* Left shift: a << b
* Right shift: a >> b

#### Increment and Decrement Operators:
* Increment: a++ or ++a
* Decrement: a-- or --a

#### Conditional Operators:
* Ternary operator: a ? b : c

#### Comma Operator:
* ,
    * x = (y = 5, y + 3) - assigns 5 to y, then assigns the result of y + 3 to x
    * func(x = 5, y = 3)
    * #define MIN(a, b) ((a) < (b) ? (a) : (b))
    * for (i = 0, j = 5; i < 10; i++, j += 2)
    * int x = (1, 2, 3) - initializes x with the value 3, because the comma operator returns value of the last expression.
    * return (x = 5, y = 3)
    * if (x = 5, y = 3) { ... }

#### Cast Operator:
* (type) expression

#### sizeof Operator:
* sizeof(expression)

#### & (Address-of) Operator:
* &a

#### (Dereference) Operator:
* *a

#### Struct & pointer related Operator:
*  -> (Arrow) Operator - to access struct or union members via pointer
* . (Dot) Operator - to access struct or union members

#### Preprocessing Operators

**Strigizing operator:**
* converts #word into a string in macro 
* #define PRINT(x) printf(#x)
* PRINT(Hello\n) -> printf("Hello\\n")

**Charizing operator**
* converts #@x into a char in macro
* #define makechar(x)  #@x
* a = makechar(b) -> a = 'b'

**Token-Pasting Operator:**
* #define CONCAT(x, y) x ## y
* int CONCAT(foo, bar) = 10; expands to int foobar = 10;

**Conditional Compilation:**

    #if 0
    code will be commented out
    #endif

    #if condition
    #elif condition
    #else
    #endif

    #ifndef MY_HEADER_H
    #define MY_HEADER_H
    ...
    #endif

    #ifdef DEBUG
    printf("Debug mode enabled\n");
    #endif

**Line Continuation**

    #define LONG_MACRO \ = 5; \ = 3;

