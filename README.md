# Learning GNU Make

Having worked as a developer writing C code for nearly a decade now and have still not learned GNU **make** properly. Lets fix this now once and for all.

GNU **make** is a tool that can be used for generation of an executable program from source files. I plan to use **make** when compiling C programs.

It should be noted that **make** is not by it self a compiler but will when it is executed commonly result in invocation of a compiler.

GNU **make** is executed by the use of the shell command:

```console
make
```

Execution of **make** requires a file called *makefile* that holds instructions for what shall be done. The makefile is typically written by the developers of a software during the development phase.

The content of a makefile is based around a type of instruction known as a *rule*. In the next section so will a makefile be constructed with a rule to compile a C program.

## Compiling Hello World

Assume that the following C source code have been written.

```C
/* hello-world.c */
#include <stdio.h>

int main (void)
{
  printf("Hello, world!\n");
  return 0;
}

```

It can be compiled with GCC using the following instruction in a terminal.

```console
gcc -Wall hello-world.c -o hello-world
```

Lets now instead see how the program can be compiled using **make**.
