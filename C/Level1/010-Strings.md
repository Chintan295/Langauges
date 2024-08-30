# Strings

In C, a string is an array of characters terminated by a null character (\0). Strings are used to represent text, such as words, sentences, or messages.

```c
char str[10]; // initializing string
char str[] = "Hello"; // sizeof(str) -> 6
char* str = "Hello";
```

### String functions

#### printf()
```c
char str[6] = "Hello";
printf("%s", str);
```

#### scanf()
```c
char str[6];
scanf("%s", str);
```

#### gets()
```c
char str[6];
gets(str);  // take string from user input
```

#### puts()
```c
char str[6];
puts(str); // print string on console
```

#### str___ functions

```c
char str[] = "Hello";
char dst[5];

int length = strlen(str); // length = 5
strcpy(dst, src); // copies "Hello" into dst
strcat(str, dst); // str = "HelloHello"
int result = strcmp(str, dst); // result = -1  if (str1 < str2)
char* ptr = strchr(str, 'l'); // ptr = "lloHello" finds the first occurance of character in string
char* ptr = strrchr(str, 'l'); // ptr = "lo" finds the last occurence
char* ptr = strstr(str, "lo");  // ptr = "loHello" finds first substring

char long_str[] = "Hello,World,Foo,Bar";
char* token = strtok(long_str, ","); // token = "Hello"
strrev(str); // olleHolleH

```

### Best Practices
* Always null-terminate strings.
* Use const correctness for string literals.
* Avoid using gets() due to buffer overflow risks.
* Use strncpy() instead of strcpy() for safer copying.

