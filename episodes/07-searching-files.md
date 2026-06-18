---
title: 'Searching files'
teaching: 10
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions

- How do I search within files for a pattern?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Search files for matching lines with `grep`.
- Use common `grep` options and simple regular expressions.

::::::::::::::::::::::::::::::::::::::::::::::::

In this section we'll cover how to search within files for matches to a given pattern.

## Grep for matches

We can use the command `grep` to search within files. You may also hear `grep` used as a verb; to
`grep` for the right line in a file.

The following examples show how you can use `grep`'s command-line options to:

- show lines that match a specified pattern
- ignore case when matching (*-i*)
- only match whole words (*-w*)
- show lines that don't match a pattern (*-v*)
- use wildcard characters and other patterns to allow for alternatives
- colour the matched text for easy visualisation (*--colour*)

Regular expressions (regex) are used to define search patterns. Some useful regex characters:

- **^** The beginning of a text line
- **$** The end of a text line
- **.** Any single character

The following command shows all of the lines in the file that contain the string CATCAT.

```bash
grep CATCAT sample_1.fastq
```

## Hands-on

::::::::::::::::::::::::::::::::::::: challenge

### 6.1 Extract ID lines

Each read in a FASTQ file has an associated sequence ID line. Identify which is the ID line from
the following `head` output.

```bash
head -n 12 sample_1.fastq
```

Use `grep` to print all of the ID lines from *sample_1.fastq*.

:::::::::::::::::::::::: solution

### Solution

```bash
grep ^@ sample_1.fastq
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### 6.2 Find matching entries

With a regular `grep` search, the line containing the matching term is printed. It can be useful to
also print lines before or after the matching lines. With *-B* (for before) and *-A* (for after),
you can specify the number of lines to display.

Display the full FASTQ entry for each sequence that contains the sequence CATCAT in
*sample_1.fastq*.

:::::::::::::::::::::::: solution

### Solution

```bash
grep -B 1 -A 2 CATCAT sample_1.fastq
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### 6.3 Search for a motif

Display the sequences in *sample_1.fastq* that contain the motif CATNNT where N is any nucleotide.

:::::::::::::::::::::::: solution

### Solution

```bash
grep CAT..T sample_1.fastq
```

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- `grep PATTERN FILE` prints lines matching a pattern.
- Options like `-i`, `-w`, `-v`, `-A` and `-B` refine what is matched and shown.
- Regular expression characters such as `^`, `$` and `.` make patterns flexible.

::::::::::::::::::::::::::::::::::::::::::::::::
