# Anatomy of a Rule

A makefile will hold a set of *rules* the syntax for writing a *rule* is explained in this section.

Below is a makefile already seen in a previous section. This makefile is so simple that it only holds a single rule and nothing else. We will use this makefile to explain the syntax for rules.

```make

```

There are typically three different parts in a rule.

First we have written hello-world-program before the colon. This part of the rule is known as the *target*. The target is often the name of something that will be generated. In this case so will an executable be generated.

The second part after the colon is known as the *prerequisites*. This part defines inputs that is used to generate the target. In this case so is the prerequisites the single source file hello-world.c.

Indented by a tab below the target-colon-prerequisite we finally have the third part that is known as a *recipe*. A recipe is an action that Make will carry out. In this case so is it a command to compile the hello-world application. This is just the same command that can be used directly in a terminal. There is a single recipe in this rule but a rule is not limited to hold a single recipe. Additional recipes can be added below and each recipe shall be intended using a tab.

There is no great benefit of using Make to compile this small dummy program. The benefits of using Make comes when building larger real-world applications that includes many files and libraries.