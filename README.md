# Undefined Behavior in C: Freeing Memory Not Allocated with malloc()

This repository demonstrates a common error in C programming: attempting to free memory that was not previously allocated using `malloc()`, `calloc()`, or `realloc()`. This often leads to undefined behavior, potentially causing program crashes or data corruption.

## The Bug

The `bug.c` file contains a simple program that allocates an integer variable `x` on the stack and attempts to free the memory using `free()`. This is incorrect behavior, as `free()` is intended for dynamically allocated memory from the heap.

## The Solution

The `bugSolution.c` file corrects this issue by removing the `free(ptr)` call.  Since `ptr` points to a variable allocated on the stack, it should not be freed.

## Compilation and Execution

To compile and run the examples:

1. Save the code in files named `bug.c` and `bugSolution.c`
2. Compile using a C compiler (like GCC):
   ```bash
   gcc bug.c -o bug
   gcc bugSolution.c -o bugSolution
   ```
3. Run the executables:
   ```bash
   ./bug
   ./bugSolution
   ```