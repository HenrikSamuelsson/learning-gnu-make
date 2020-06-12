# Installation

This section briefly discusses how to get Make installed on a machine. The installation process varies depending on the type of machine and what operation system the machine runs. The process also tend to change and evolve over time so it is hard to keep an updated guide for all type of machines. Hence so will only some more general hints be presented here.

Make is run from a terminal. Starting out in a terminal window is also a good way to check if Make is currently installed or not. Open up a terminal window on your machine and type the following command.

```console
> make -version
```

An example output from this command on a Windows PC is the following. It can bee seen that Make version 4.3 is available on this machine.

```console
> make -version
GNU Make 4.3
Built for x86_64-pc-cygwin
Copyright (C) 1988-2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
>
```

If not getting something similar to the result from above so will Make somehow need to be installed.

The general idea to get help with the installation is to just search online for:

Installing GNU Make on *(your operating system)*

Or try one of the ways described in the below subsections.

## Windows

There are various ways to get Make on a Windows machine although most of the ways will take a little effort.

On way to get access to Make in Windows is to use [Cygwin](https://cygwin.com/index.html), see this [question](https://stackoverflow.com/questions/17710209/how-to-run-make-from-cygwin-environment?rq=1) on Stack Overflow.

Another similar alternative to Cygwin is [Mingw-w64](http://mingw-w64.org/), see also this [question](https://stackoverflow.com/questions/42752721/mingw-64-ships-without-make-exe) on Stack Overflow.

On Windows there is also always the option to run a Linux on a virtual machine and do your development this way. It is however beyond the scope of this material to even try to suggest the best way to achieve this.

## Linux

It is generally simpler to get Make started under Linux compared to Windows.

Again so is a search engine your best friend but all that is needed is generally to enter one-liner in a terminal window.

For example if on Ubuntu try the following command that install make along with some other good to have tools:

```console
> sudo apt-get install build-essential
```

## MacOS

Have never really used an Apple computer and also not really sure if Make is relevant or not in this sphere so will refrain from even trying to help out on this environment.

## Exercises

### Exercise 1

Install GNU Make on your machine. Search online for instructions or follow the instructions from above.

### Exercise 2

Check what version of GNU Make you have installed on your machine by the use of the following terminal command.

```console
> make --version
```

### Exercise 3

Find out the version number of the latest released version of GNU Make and see how it compares to the version you have installed. Hint, search online for "GNU make changelog" or "GNU make ftp mirror list" and explore the hits.
