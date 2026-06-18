---
title: 'Getting started'
teaching: 15
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions

- How do I connect to a Unix computer?
- How do I run a command and give it options?
- How do I find out what a command does?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Log in to a remote Unix machine.
- Run basic commands and modify their behaviour with flags.
- Read the manual page for a command.

::::::::::::::::::::::::::::::::::::::::::::::::

## Connecting to a Unix computer

Logging in connects your local computer (e.g. laptop) to a remote machine, and allows you to type
commands into the Unix prompt. The commands are run on the remote machine, and the results are
displayed on your local screen.

You will be allocated a training account for the duration of the workshop. Your username and
password will be supplied at the start of the workshop.

We connect to a remote computer so that everyone has an identical environment, regardless of the
specifications of your local computer. This is similar to how you would connect to a
high-performance computing (HPC) system such as [Spartan](https://dashboard.hpc.unimelb.edu.au/)
at The University of Melbourne.

::::::::::::::::::::::::::::::::::::: callout

### Connecting

Instructions for connecting to the remote machine (and for completing this workshop independently)
are on the [Setup](../learners/setup.md) page. Make sure you can log in before continuing.

::::::::::::::::::::::::::::::::::::::::::::::::

## Hands-on

::::::::::::::::::::::::::::::::::::: challenge

### 1.1 Run some commands

Once you've logged in, run the following commands and see what they do. Type each command in and
hit <kbd>Enter</kbd>. Once the previous command has completed, a new prompt indicates that it's
ready for the next command.

```bash
whoami
```

```bash
date
```

```bash
cal
```

:::::::::::::::::::::::: solution

### Solution

- `whoami`: displays your username (i.e. the person currently logged in).
- `date`: displays the current date and time.
- `cal`: displays a calendar.

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### 1.2 Try out some flags

Many Unix commands accept arguments (sometimes called flags) which enable or disable specific
features. For example, you can ask the `date` command to produce its output in a different format.

```bash
date -I
```

It is not uncommon for a command to accept many different arguments, and in most cases more than
one argument can be supplied at the same time. Arguments are separated by one or more space
characters and they are usually case sensitive.

```bash
cal -m january
```

```bash
cal -3
```

```bash
cal -3 -m january
```

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### 1.3 Consult the manual pages

If every Unix command has so many options, how do you find out what they are and what they do?
Thankfully, every Unix command has an associated *manual* that you can usually access by using the
`man` command.

Try accessing the manual pages for the commands we have used so far. Can you figure out what day of
the week your 100th birthday will be?

:::::::::::::::::::::::: solution

### Hint

The following command displays the manual page for the `cal` command.

```bash
man cal
```

When you are using the `man` command, use the up and down arrows to scroll, or press <kbd>q</kbd>
to quit. The `man` command is actually using another Unix program, a text viewer called `less`,
which we'll come to later on.

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

### binder users

If you are running this workshop in a binder, manual pages may not be accessible via the `man`
command. Try an internet search for your desired command followed by *manual unix* instead.

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Connect to a remote Unix machine with `ssh` (see Setup).
- Commands can be modified with flags, e.g. `cal -3`.
- `man <command>` opens the manual page; press <kbd>q</kbd> to quit.

::::::::::::::::::::::::::::::::::::::::::::::::
