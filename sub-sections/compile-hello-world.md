# Compiling a C-program with Make

Assume that the following C source code have been developed and is now to be compiled.

```C
/* hello-world.c */
#include <stdio.h>

int main (void)
{
  printf("Hello world!\n");
  return 0;
}

```

It can be compiled with GCC using the following instruction in a terminal. The command says that we shall run the GCC compiler and it shall compile the file hello-world.c for us, we also provide the instruction that the result of the compilation is to be placed in a file called hello-world.

```console
gcc hello-world.c -o hello-world
```

Lets now instead see how the program can be compiled using Make. We create a new file called makefile in the same folder that holds the source file hello-world.c. The content of the newly created makefile shall be:

```make
compile_hello-world: hello-world.c
	gcc hello-world.c -o hello-world-program
```

Note that the indentation shall be accomplished using a tab, not spaces.

After saving the makefile so shall we in the terminal run the *make* utility by the use of the command make. If everything is correct so should the output be:

```console
gcc hello-world.c -o hello-world-program
```

And there should afterwards be a fresh new version of the application hello-world-program that was just built when GCC was invoked by Make.

The source code and makefile discussed in this section can be found in the folder [project-001-hello-world](projects/project-001-hello-world/).
