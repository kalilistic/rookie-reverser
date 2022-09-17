+++
date = "2022-09-17"
title = "learning c: objects, functions, and types"
+++


Slightly belated, but here is my second blog post on learning c. I'm not going to exhaustively list what I'm learning as I'm not sure a regurgitation of the source material will be that interesting. So instead, I'll share points of interest that stood out to me.

### Preprocessor Directives
The "Hello World" application has two preprocessor directives at the top.
{{< highlight c >}}
#include <stdio.h>
#include <stdlib.h>
{{< /highlight >}}
These behave in your code as if you've replaced them with the contents of the specified module. The stdio file contains I/O functions, and the stdlib contains general utility functions.

### Objects
What is an object? I never gave this idea much thought - just an instance of a class I've created. The definition of an object in the C standard (paraphrasing) is a region of data storage of which the contents can represent values. It is the variable that has a declared type that determines the kind of object the value represents.

### Pointers
I've had a little exposure to pointers, but I don't have significant experience with them. Pointers are addresses to the location of a function or object in memory.

### Pass By Value
C is a pass-by-value language which was a change. The argument you pass to a function is copied into a new variable. This contrasts with other languages that pass a reference to the function to the original variable. You can simulate pass-by-reference in C using pointers to update the original variable.

### Unary Operator
The & is the address-of operator, which generates a pointer to its operand. For example, &a generates a pointer to the variable a. In other words, &a generates an address that points to the memory location that contains an object or function.

### Dereferencing Operator
The * is the indirection operator, which is to retrieve the object located at a pointer's memory address. For example, the pointer *pa would return the object stored at the location in memory.

### Alignment
I found this topic to be more complex, and I might need to do some additional reading. I understand this relates to how data is stored in memory cells and how you handle extra space in the cell for smaller objects like chars. The CPU will add padding - but the exact specifics will differ between manufacturers/models. If needed, you can optimize data placement for performance or storage needs.

### Pointer Type
The pointer type is derived from the function or object type that it points to, called the reference type.

### Structs
A structure type contains sequentially allocated member objects. The objects in the struct have their own types, which can differ from one another. Structs are used for declaring a collection of related objects and are often used to simplify function arguments.

### Unions
Unions are similar to structs, except that the memory used by the member objects overlaps. They may contain objects at different times but never at once and are primarily used to save memory.

### volatile
This object qualification is used when the values stored in an object may change without the knowledge of the compiler. An example is reading from a real-time clock which will tick outside the program.

### restrict
This pointer qualification is used for optimization but may result in undefined behavior if used incorrectly.
