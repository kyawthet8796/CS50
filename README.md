**CS50**

Starting with simple C program
```
#include <stdio.h>
int main(void)
{
    printf("hello, world\n");
}
```
`include` is a keyword that indicates we want to include some other file in our program.`stdio.h` contains the standard input/output library.

Output in C
> printf("Hello World");

`while` loop and `for` loop examples
```
while (true)
{
    printf("hello, world\n");
}
```
```
for (int i = 0; i < 50; i++)
{
    printf("hello, world\n");
}
```
Check the conditions with `if`statements
```
if (x < y)
{
    printf("x is less than y\n");
}
else if (x > y)
{
    printf("x is greater than y\n");
}
else
{
    printf("x is equal to y\n");
}
```
Computers only understand binary, so the **source code** that we write need to be converted to 0s and 1s, or **machine code**. This conversion is done by software called a **compiler**.
`make` is a compiler command in linux.

**Data types in C** 
https://www.dummies.com/programming/c/c-language-numeric-data-types/

**Functions**
-   Some functions relating to input include:
    
    -   `get_char` - gets a character from the user
        
    -   `get_double`
        
    -   `get_float`
        
    -   `get_int`
        
    -   `get_long_long`
        
    -   `get_string`

**Arithmetic operators**
Addition is `+`,subtraction is `-`,multiplication is `*`, division is `/`, and the modulo (remainder) operator is `%`.

We use `==` for a comparison, since a single `=` assigns a value.

`||` to represent a logical **or**, where only one of the expressions need to be true for that condition to be followed and `&&` for **and**, where both expressions must be true.

**Overflow**
In C, each type of data has a fixed number of bytes allocated to instances of it. As a result, one problem we can run into is **integer overflow**.
