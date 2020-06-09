# Learning GNU Make

Having worked as a developer writing C code for nearly a decade now and have still not learned GNU **make** properly. Lets fix this now once and for all.

GNU **make** is a tool that can be used for generation of an executable program from source files. I personally plan to use **make** to compile C programs.

It should be noted that **make** is not by it self a compiler but it is commonly use to invoke a compiler.

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
  printf("Hello world!\n");
  return 0;
}

```

It can be compiled with GCC using the following instruction in a terminal.

```console
gcc -Wall hello-world.c -o hello-world
```

Lets now instead see how the program can be compiled using **make**. We create a new file called makefile in the same folder that holds the source file hello-world.c. The content of the newly created makefile shall be:

```make
hello-world-program: hello-world.c
	gcc -Wall hello-world.c -o hello-world-program
```

Note that the indentation shall be accomplished using a tab, not spaces.

After saving the makefile so shall we in the terminal run the *make* utility by the use of the command make. If everything is correct so should the output be:

```console
gcc -Wall hello-world.c -o hello-world-program
```

And there should afterwards be a fresh new version of the application hello-world-program that *make* just built.

There are three different parts in the makefile.

First we have hello-world-program before the colon, this part is known as the *target*. This parts is often the name of something that will be generated. In this case so is it an executable but it can also often be an object file.

The second part after the colon is known as the *prerequisite* and this is an input that is used to generate the target. In this case so is the prerequisite the single source file hello-world.c.

Indented by a tab below the target-colon-prerequisite we finally have the third part that is known as a *recipe*. A recipe is an action that **make** will carry out. In this case so is it a command to compile the hello-world application, and the command is the same that can be used directly in a terminal.

There is no great benefit of using **make** to compile this small dummy program. The benefits of using **make** comes when building larger real-world applications that includes many files and libraries.

The source code and makefile discussed in this section can be found in the folder [project-001-hello-world](projects/project-001-hello-world).
