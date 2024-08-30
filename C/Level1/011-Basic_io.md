# Basic input/output

### Input
* scanf(): Reads input from the standard input (usually the keyboard) and stores it in variables.
* fgets(): Reads a line of text from the standard input.
* getchar(): Reads a single character from the standard input.

### Output
* printf(): Prints output to the standard output (usually the screen).
* putchar(): Prints a single character to the standard output.
* puts(): Prints a line of text to the standard output.

```c
#include <stdio.h>

int main() {
    int x;
    char name[20];
    char c;

    // Input using scanf
    printf("Enter a number: ");
    scanf("%d", &x);

    // Input using getchar
    printf("Enter a character: ");
    c = getchar();

    // Output using printf
    printf("You entered: %d\n", x);

    // Output using puts
    puts("Hello world !!");

    // Output using putchar
    putchar(c);

    return 0;
}
```

```c
#include<stdio.h>
int main()
{
    char string[20];
    printf("Enter the string: ");
    fgets(string, 20, stdin);         //input from stdin stream
    printf("\nThe string is: %s",string);
    return 0;
}
```