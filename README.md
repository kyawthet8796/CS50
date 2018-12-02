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

**Lecture 5**

*Memory*

 1.  Text
   - The text area contains the binary code of our compiled program.
 2. Initialized and uninitialized data
   - refers to global variables for our program, depending on whether we’ve set initial values for them.
3. Heap
  - The heap has dynamically allocated memory, or memory allocated when the program is running.
4. Stack
  - The stack contains slices, or frames, of memory for functions and their local variables.
5. Environment variables
  - Environment variables, which we’ll see in web programming, are variables like usernames and passwords that we don’t want to store in the source code of our program, but still want access to via different mechanisms.

*Overflow*

 - StackOverflow
 - Heap overflow
 - Buffer overflow

*Stacks and Queues*

- Stacks(push & pop) or LIFO(Last In First Out)/FILO(First In Last Out) order
- Queue(enqueue & dequeue) or FIFO(First In First Out)

**Lecture 6**

*HTTP*
Websites are generally written not as binary, but in markup language.

 -   `GET` is a method that specifies we want to retrieve something.
    
 -   The `/` refers to the default page, or the homepage.
    
 -   `HTTP/1.1` indicates the the version of HTTP we want to use.
 -  `Host: www.facebook.com` indicates the website we want the server to return to us, since that same server might have many websites it is responsible for.


 -   200 OK
    
 -   301 Moved Permanently
    
 -   302 Found
    
 -   304 Not Modified
    
 -   401 Unauthorized
    
 -   403 Forbidden
    
    -   The requesting client doesn’t have the permissions to access a particular page.
        
    
 -   404 Not Found
    
 -   418 I’m a Teapot
    
    -   Actually an April Fool’s joke that stuck around.
        
    
 -   500 Internal Server Error
    
    -   The code on the web server itself had an error.

*Private Addresses*
- 10.#.#.#
- 172.16.#.# - 172.31.#.#
- 192.168.#.#

DHCP - automatically acquire an IP address from a DHCP server.

DNS, Domain Name System, that maps IP addresses to domain names, and vice versa.

Standard ports and protocols include:

-   22 SSH, secure shell, to run commands on another computer
    
-   53 DNS
    
-   80 HTTP, for visiting websites
    
-   443 HTTPS, for visiting secure websites
    
-   587 SMTP, for sending mail …

**Lecture 7**

*Dynamic Programming*
- is a type of algorithm that solves a problem by saving the results each time, and looking up the answer if it’s needed in the future.

*Rod Cutting*
There are different ways we can cut a rod of length 10, and we see that the total amount we can get is different depending on how we cut it.There are 2^_n_ - 1^ possibilties for a rod of length _n_.

*Network Routing*
Our own computers only go so far as to know about our local network and our access point, and only our ISP or school’s servers will participate in this route sharing process.

**Lecture 8**

*Python*
Python is interpreted. This means that we can run our program with one command like `python hello.py`.`Python` program is an interpreter that compiles our source code into something called bytecode. 

-   Python has familiar data types and features:
    
    -   `bool`
        
    -   `float`
        
    -   `int`
        
    -   `str`
        
    -   `…​`
-   We’ve also implemented some training wheels again, with functions in a library that we’ll call like this:
    
    -   `get_char`
        
    -   `get_float`
        
    -   `get_int`
        
    -   `get_string`
        
    -   …​
        
    
-   And there are even more types and features built into Python, like:
    
    -   `complex`
        
        -   complex numbers from mathematics
            
        
    -   `dict`
        
        -   a dictionary, like a hash table
            
        
    -   `list`
        
        -   like an array that automatically grows and shrinks
            
        
    -   `range`
        
    -   `set`
        
        -   a list with unique items, with operations like those of sets in mathematics
            
        
    -   `tuple`
        
        -   like structs, but without any specifications, like `(x, y)` to store two numbers
            
        
    -   …​

`//`, that divides two integers and returns an integer.
`/` symbol will divide two integers into a float if needed.
Comments in Python, will start with `#`.
`or` and `and` in Python instead of `||` and `&&`.
Python also doesn’t have a `do while` loop, so instead we use `while True`, and `break`, or stop the loop, `if n > 0`.
Python maximum for an integer is far larger than the maximum it is in C.

**Lecture 9**

*Web Programming*
To get data back from a server
```
GET / HTTP/1.1
Host: www.facebook.com
...
```
The server responds with a message
```
HTTP/1.1 200 OK
Content-Type: text/html
...
```
Python is a programming language that can be used for many purposes, but today we’ll use it to write a program that acts as web server, generating dynamic content.

**Lecture 10**

*Cookies*
A **cookie** (in this context) is a small piece of information unique to our login that a web server gives to our browser, that our browser can send back in the future, to verify who we are.Like a digital handstamp.
Our browser stores cookies for us and sends it back as part of an HTTP request in the headers.

Some of the headers in the reply from the server might look like this:

```
HTTP/1.1 200 OK
Content-Type: text/html
Set-Cookie: session=value
...
```

-   `session` is the key for the cookie, like a variable name, and `value` will be our unique handstamp, which might be a large random number that’s hard for others to guess.

Our browser, in future requests, will include that cookie in the headers:

```
GET / HTTP/1.1
Host: www.facebook.com
Cookie: session=value
...
```
HTTPS encrypts the messages between our browser and the receiving server, so someone along the network won’t be able to steal our cookies.
