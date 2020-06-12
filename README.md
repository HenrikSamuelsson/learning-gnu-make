# Learning GNU Make

By Henrik Samuelsson, version 0.1

## Background

Having worked as a developer writing C code for nearly a decade now and have still not learned GNU Make properly. Lets fix this now once and for all.

## About GNU Make

*GNU Make* is a tool that is useful when generating an executable program from the programs source files.

Note that GNU Make is by itself not a compiler but it is often used to invoke a compiler.

## About This Material

I am when starting out to write this material a beginner on GNU Make and basically learning in parallel while this is being written. So everything will for sure not be correct especially if you happen to read one of the early versions.

The material is written in a tutorial style way with exercises for the readers to attempt by themselves. Readers do not need to have any knowledge about GNU Make. Readers should have basic knowledge on terminal commands, also known as shell commands. Readers are also assumed to be somewhat proficient in the C programming language.

GNU Make will from now in this material be refereed to as just Make.

## Installation

Just like any other software so must Make be installed on the machine it is planned to be run on. Read [here](sub-sections/installation.md) for hints on how to get Make installed.

## Running Make

Assuming that Make have been installed so can you now go the following [subsection](subsections/running-make) where Make will be taken for an initial test run.



The content of a makefile is based around a type of instruction known as a *rule*. In the next section so will a makefile be constructed with a rule to compile a C program.

## Compiling Hello World

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

It can be compiled with GCC using the following instruction in a terminal.

```console
gcc -Wall hello-world.c -o hello-world
```

Lets now instead see how the program can be compiled using Make. We create a new file called makefile in the same folder that holds the source file hello-world.c. The content of the newly created makefile shall be:

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

The source code and makefile discussed in this section can be found in the folder [project-001-hello-world](projects/project-001-hello-world/).

## The Anatomy of a Makefile

A makefile will hold a set of *rules*, the first make file used in the previous section is so simple that it only holds a single rule and nothing else. There are commonly three different parts in a rule. Each of these three parts have a name that will be introduced in this section.

First we have written hello-world-program before the colon. This part of the rule is known as the *target*. The target is often the name of something that will be generated. In this case so will an executable be generated.

The second part after the colon is known as the *prerequisites*. This part defines inputs that is used to generate the target. In this case so is the prerequisites the single source file hello-world.c.

Indented by a tab below the target-colon-prerequisite we finally have the third part that is known as a *recipe*. A recipe is an action that **make** will carry out. In this case so is it a command to compile the hello-world application. This is just the same command that can be used directly in a terminal. There is a single recipe in this rule but a rule is not limited to hold a single recipe. Additional recipes can be added below and each recipe shall be intended using a tab.

There is no great benefit of using **make** to compile this small dummy program. The benefits of using **make** comes when building larger real-world applications that includes many files and libraries.

## Clean-up Recipe

A makefile can hold more than a single rule. We will in this section test with adding a rule that holds a recipe to clean up by erasing the generated executable.

First part of the makefile is identical to what we already have seen. We then introduce a new rule called clean. This will when invoked will execute a recipe to erase the generated executable.

```console
hello-world-program: hello-world.c
	gcc -Wall hello-world.c -o hello-world-program

clean:
	rm hello-world-program
```

So now we have two rules, the first rule is as before executed by entering the make command in console:

```console
make
```

Or alternatively to be more explicit, by the use of the following command that includes the target name:

```console
make hello-world-program
```

The new rule is executed using the newly introduced target name:

```console
make clean
```

Expected result is that if there was an executable present in the folder so is this erased after running the command make clean in the terminal. Should there currently not be file called hello-world-program in the folder of the makefile so will an message about not being able to remove the file be presented by the operating system.

The source code and makefile discussed in this section can be found in the folder [project-002-introduce-clean](projects/project-002-introduce-clean/).
