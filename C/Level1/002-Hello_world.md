# First program

    #include <stdio.h>

    int main() {
        printf("Hello, World!\n");
        return 0;
    }

Output:
'Hello world!'

* Compile with below command:

        gcc hello.c -o hello

* Execute:

        ./hello

### Compilation process

**1: Preprocessing**
* The preprocessor reads your C source code (e.g., hello.c) and expands any macros, includes header files, and removes comments.
* The preprocessor outputs a modified version of your code, which is then fed into the next stage.

**2: Compilation**
* The compiler (e.g., gcc) translates your preprocessed code into assembly code (e.g., hello.s).
* The compiler checks for syntax errors, type errors, and other issues, and reports any errors.

**3: Assembly**
* The assembler translates the assembly code into machine code (e.g., hello.o).
* This stage generates object files, which are machine-specific.

**4: Linking**
* The linker (or ld) takes the object files and libraries (if any) and creates an executable file (e.g., hello).
* The linker resolves external references and symbols, and relocates code as needed.

**5: Loading**
* When you run the executable file (e.g., ./hello), the loader loads the program into memory.
* The loader sets up the program's memory layout, including the stack, heap, and data segments.

**6: Execution**
The CPU executes the machine code instructions in the program.





