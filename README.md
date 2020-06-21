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

Assuming that Make have been installed so can you now go the following [section](sub-sections/running-make.md) where Make will be taken for an initial test run.

## Compiling Hello World

Make is often used to compile C-programs. In this [section](sub-sections/compile-hello-world.md) is it explained how to compile a simple C-program by the use of Make and GCC.

## The Anatomy of a Makefile

A makefile will typically be based on a set of instructions known as rules, this [section](sub-section/anatomy-of-a-rule.md) discusses the syntax that is used for a rule.

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
