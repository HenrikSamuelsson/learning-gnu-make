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

Finally run Make from inside the empty folder.

```console
> make
```

Expected output produced by Make is something like the following.

```console
make: *** No targets specified and no makefile found.  Stop.
```

## The Makefile Concept

We saw in Exercise 1 above that make started but reported some issues. The first issue that we will fix is about the report of no makefile found.

A *makefile* is a file that Make expects to be present when run. The makefile holds instructions for what make shall do. The makefile is typically written by software developers in parallel with writing code for the software as a part of the development process.

## Exercise 2

Add an empty file called makefile in the empty folder from Exercise 1, for example by the use of the touch terminal command.

```console
> touch makefile
```

Then verify that the file is now present by listing the content of the folder with by the use of the terminal command ls.

```console
> ls


    Directory: C:\Temp\running-make


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        12/06/2020     16:55              0 makefile
```

We now have a makefile and it is now time to test to run Make again to see what happens.

```console
> make
```

Expected output this time is something like the following.

```console
make: *** No targets. Stop.
```

## The Target Concept

We saw in exercise 2 that the message about not finding a makefile went away since we added a file with the name makefile. However so is Make still confused because there where no targets.

A *target* is something that Make shall do. Our make file is totally empty so there is nothing for Make to do and this is what causes confusion for Make.

## Exercise 3

You will in the final exercise in this section add content to the makefile that conforms to the format that Make interprets as a target.

Open up the empty makefile in an editor and enter the following two lines.

```make
helloworld:
    $(info Hello world!)
```

**Important note:** The indentation of the second lines must be done using the tab character, so press the tab key to achieve the indentation. Also make sure that the editor used is not setup to automatically replace tabs with spaces.

Save the makefile and run Make again. Expected output is this time something like the following.

```console
Hello world!
make: 'helloworld' is up to date.
```

## Targets Briefly Explained

What was done in the last exercise was that a target named helloworld was added to the makefile. What should be done in this target is that a debug message with info level should be printed out by Make.

When me then executed Make so was the target found by Make in the makefile and Hello world! was in deed printed out in the terminal.

After the printout follows a new info message from Make that will be explained later on, but it shall basically be interpreted as there is at this point in time nothing more for Make to do with the helloworld target.
