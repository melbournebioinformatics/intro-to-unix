---
title: Setup
---

Please follow the steps below **before** the scheduled workshop. If you encounter problems, contact
your own IT support with at least one week to spare.

For the live workshop you will be given an individual username, IP address and password to log in
to a remote [Nectar](https://cloud.nectar.org.au/) instance. No data needs to be downloaded for the
live delivery workshop — everything is already set up on the remote machine. The instructions below
cover the software you need locally, plus how to complete the workshop independently.

## Software Setup

::::::::::::::::: discussion

### Required software

You need a **terminal** to log in to the remote machine, and (optionally) a **file-transfer**
program for the last section.

- **macOS / Linux**: use the built-in `Terminal` app — no installation required.
- **Windows**: install a terminal emulator such as [PuTTY](https://www.putty.org/) (free and
  open-source).
- **File transfers (all platforms)**: install [FileZilla](https://filezilla-project.org/) for
  Section 8.

:::::::::::::::::::::::::::::

## Connecting to the remote machine

This workshop runs on a Nectar instance. Full, step-by-step login instructions (for both macOS and
Windows) are in the Melbourne Bioinformatics **Intro to the Nectar Cloud** lesson:

- [Logging on to a Nectar instance](https://melbournebioinformatics.github.io/nectar-instances/)

Your username, the instance IP address and your password will be provided at the start of the
workshop.

## Slides

The slides presented during this workshop are available here:
[PDF](files/unix_intro_slides.pdf) / [PPTX](files/unix_intro_slides.pptx).

## Completing the workshop independently

The remote machines are only provided for live workshop participants. You can still complete the
workshop on your own using the data provided.

Download the data: [unix-intro-data.zip](data/unix-intro-data.zip) (also available from
[Zenodo](https://zenodo.org/record/7349747)). Unzip it, then follow the OS-specific instructions
below before heading to the hands-on sections.

:::::::::::::::: spoiler

### macOS / Linux

Open the `Terminal` app. Change into the unzipped data directory, replacing `PATH_TO_DIRECTORY`
with its location (tip: drag the folder from Finder into the Terminal to paste its path):

```bash
cd PATH_TO_DIRECTORY
```

Confirm you are in the right place:

```bash
pwd
```

If the output ends in `/unix_intro_data`, you're ready — continue with the hands-on sections.

::::::::::::::::::::::::

:::::::::::::::: spoiler

### Windows

We will use [binder](https://mybinder.org/), which builds a live environment from a repository so
you can run Unix commands in your web browser.

[Launch the binder.](https://mybinder.org/v2/gh/melbournebioinformatics/training-infrastructure/HEAD)
Be patient — it can take a few minutes to set up. Once it has launched, select *Terminal* from the
bottom left-hand corner of the main page. You can now continue with the hands-on sections.

::::::::::::::::::::::::
