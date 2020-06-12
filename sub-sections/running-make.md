## Running Make

Make can be started by the following terminal command.

```console
> make
```

## Exercise 1

We will in this exercise intentionally make a mistake when running make to learn about the error message. Create a new empty folder somewhere on your computer, hint on how to achieve this below.

```console
> mkdir running-make


    Directory: C:\Temp


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       12/06/2020     13:46                running-make

```

Now enter the new folder and verify that it is empty by listing the contents.

```console
> cd running-make
> ls
>
```

Finally attempt run Make from inside the empty folder.

```console
> make
```

Expected output produced by Make is something like the following.

```console
make: *** No targets specified and no makefile found.  Stop.
```
