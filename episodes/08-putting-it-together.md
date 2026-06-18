---
title: 'Putting it all together'
teaching: 10
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions

- How do I combine commands?
- How do I save command output to a file?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Connect commands together with pipes (`|`).
- Redirect output to files with `>` and `>>`.

::::::::::::::::::::::::::::::::::::::::::::::::

In this section we will cover a few more advanced Unix concepts that allow us to bring together some
of the commands we have learned so far.

## Combine commands with pipes

One of the most powerful features of Unix is that you can send the output from one command directly
into the input of any other command.

We do this by using a pipe that is represented by the **|** character. Think of a pipe as a
connection between two Unix commands.

```bash
grep CAT..T sample_1.fastq | wc -l
```

The first part of the command is the same `grep` search from 6.3. The `grep` output is sent through
a pipe to `wc`, where the *-l* option counts the number of lines. So as a whole, this command
counts the number of sequences that contain a match to the motif CATNNT.

## Redirect output to a file

It can be very useful to direct output into a new file, rather than simply printing it to the
screen. This file redirection can be done with the **>** symbol.

```bash
whoami > user.txt
```

The command above sent the output of the `whoami` command to a file called user.txt. Notice that
there was no output on the screen. You can check the contents of user.txt with `less`.

::::::::::::::::::::::::::::::::::::: caution

### Warning

Be careful when using file redirection (**>**); it will overwrite any existing file of the same
name.

::::::::::::::::::::::::::::::::::::::::::::::::

We can also use the **>>** operator to append output to the end of an existing file.

```bash
date >> user.txt
```

You should see that your user.txt file now contains the output of the `date` command under the
original user line.

## Hands-on

::::::::::::::::::::::::::::::::::::: challenge

### 7.1 Use a pipe

Display the ID lines from the first 10 entries in *sample_1.fastq* using a pipe.

:::::::::::::::::::::::: solution

### Solution

```bash
grep ^@ sample_1.fastq | head
```

Or, alternatively:

```bash
head -n 40 sample_1.fastq | grep ^@
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### 7.2 Direct output to a file

Use your command from above but redirect the output to a file. Choose a sensible name for your file.

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### 7.3 Create a new FASTQ file

Create a new FASTQ file containing the final 3 reads in each of the three FASTQ files.

:::::::::::::::::::::::: solution

### Solution

```bash
tail -n 12 sample_1.fastq > new_sample.fastq
tail -n 12 sample_2.fastq >> new_sample.fastq
tail -n 12 sample_3.fastq >> new_sample.fastq
```

Or, alternatively:

```bash
tail -n 12 *.fastq | grep -v "^==>" | grep . > new_sample.fastq
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- A pipe (`|`) sends one command's output into another command's input.
- `>` redirects output to a file (overwriting it); `>>` appends to a file.

::::::::::::::::::::::::::::::::::::::::::::::::
