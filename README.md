# Dynamic-memory-allocation-using-C

What is dynamic memory allocation?

C Dynamic Memory Allocation can be defined as a procedure in which the size of a data structure (like Array) is changed during the runtime.
C provides some functions to achieve these tasks. There are 4 library functions provided by C defined under <stdlib.h> header file to facilitate dynamic memory allocation in C programming. They are: 

1] malloc() method
The “malloc” or “memory allocation” method in C is used to dynamically allocate a single large block of memory with the specified size. It returns a pointer of type void which can be cast into a pointer of any form. It doesn’t Initialize memory at execution time so that it has initialized each block with the default garbage value initially. 

Syntax: 
ptr = (cast-type*) malloc(byte-size)

For Example:
ptr = (int*) malloc(100 * sizeof(int));
Since the size of int is 4 bytes, this statement will allocate 400 bytes of memory. And, the pointer ptr holds the address of the first byte in the allocated memory.

2] calloc() method
“calloc” or “contiguous allocation” method in C is used to dynamically allocate the specified number of blocks of memory of the specified type. it is very much similar to malloc() but has two different points and these are:
- It initializes each block with a default value ‘0’.
- It has two parameters or arguments as compare to malloc().

Syntax: 
ptr = (cast-type*)calloc(n, element-size);
here, n is the no. of elements and element-size is the size of each element.

For Example: 
ptr = (float*) calloc(25, sizeof(float));
This statement allocates contiguous space in memory for 25 elements each with the size of the float.
 

3] realloc() method
“realloc” or “re-allocation” method in C is used to dynamically change the memory allocation of a previously allocated memory. In other words, if the memory previously allocated with the help of malloc or calloc is insufficient, realloc can be used to dynamically re-allocate memory. re-allocation of memory maintains the already present value and new blocks will be initialized with the default garbage value.

Syntax: 
ptr = realloc(ptr, newSize);
where ptr is reallocated with new size 'newSize'.

Key Differences between malloc() vs calloc()

malloc() function returns only starting address and does not make it zero, on the other hand, the calloc() function returns the starting address and makes it zero.
In malloc function, the number of arguments is 1, while in calloc function, the number of arguments is 2.
malloc() time efficiency is higher than calloc(), whereas malloc() is not secure as compared to calloc()
malloc does not initialize memory, whereas calloc performs memory initialization.
