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

**Lecture 2**

*Compiling* 
There are four steps to process in compiling.

 - preprocessing
	 - In C, preprocessing involves replacing the lines that start with `#include` with the contents of the actual file.
 - compiling
	 - The compiler takes the complete source code and converts it to assembly code
 -   assembling
	 -  Finally, these lines of assembly are converted to 0s and 1s that the CPU can directly understand.
 - linking

	 - We also need to combine into our program the binary file for standard I/O library.

*Strings & Arrays*
 C stores strings in memory with one character in each byte, but also with a terminating, or ending character, at the end of each string. This special **null character**, or `\0`, is literally the number 0.
 In C, we can create arrays, or lists, comprised of elements of the same type of data.
 
*Cryptography*
Encrypted data, or ciphertext, is the scrambled version of plaintext, or the original, easily-readable data. To get from plaintext to ciphertext, and vice versa, we need to know the key, or some piece of information, like a number that indicates how many letters we need to shift each letter in our plaintext by.

**Lecture 3**

*Searching*

 - Linear search

```
for each element in array
    if element you're looking for
        return true
return false
```

 - Binary search
```
look at middle of sorted array
if element you're looking for
    return true
else if element is to left
    search left half of array
else if element is to right
    search right half of array
else
    return false
```

*Sorting*

 - Insertion sort
 ```
for i from 1 to n-1
    call 0'th through i-1'th elements the "sorted side"
    remove i'th element
    insert it into sorted side in order
```
 - Bubble sort
 ```
repeat until no swaps
    for i from 0 to n-2
        if i'th and i+1'th elements out of order
            swap them
```
 - Selection sort
 ```
for i from 0 to n-1
    find smallest element between i'th and n-1'th
    swap smallest with i'th element
```

*Running Time*

-   The notation for theoretical running time includes:
    
    -   _O_, worst-case running time, or upper bound
        
    -   Ω, best-case running time, or lower bound
        
    -   Θ, if both of those are the same

*Merge sort*
```
on input of n elements
    if n < 2
        return
    else
        sort left half of elements
        sort right half of elements
        merge sorted halves
```
**Lecture 4**

Recall that bytes in memory can be visualized as a grid, with each location having some numerical address indicating its position.
-   The heap, at top, is where memory for `malloc` comes from.
    
-   The stack, in the bottom, is used for functions. In fact, for our C programs, the very bottom of the stack contains a chunk of memory for our `main` function, such as any local variables or arguments.

 `char *s`, s is the pointer name.
 `char a`, a is the variable name.
 a has memory address and if we don't assign any value,there is random value in a.

Pointer in C programming https://www.youtube.com/watch?v=TFTpRjPcoUs

*Images*

The bit `1` to represent black and `0` for white, we can create an image with a grid of bits.
The first three bytes of a JPEG file are `0xff 0xd8 0xff`.
`0xff` is 255.
`0xd8` is 216.
