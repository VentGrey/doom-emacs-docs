---
layout: default
title: Doom Binaries
nav_order: 2
---

# Included executables
{: .no_toc }

Doom Emacs comes with a set of binaries to aid us in it's installation process
as well as maintaining our installation.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Doom

Develop
{: .label .label-purple}

This is the default doom binary.

A command line interface for managing Doom Emacs; including:

* Package management

* Diagnostics

* Unit Tests

* byte-compilation

This tool also makes it trivial to launch Emacs out of a different folder or
with a different private module.

* **Available commands**
  * `doom install`
  * `doom help update`
  * `doom compile :core lang/php lang/python`
  * `doom run`
  * `doom run -nw file.txt file2.el`
  * `doom run -p ~/.other.doom.d -e ~/.other.emacs.d .nw file.txt`
* **Format commands**
  * `-h` / `--h`  Help Command
  * `-d` / `--debug`  Turn on doom-debug-mode
  * `-e` / `--emacsd`   Use the emacs config at DIR
  * `-i` / `--insecure`  Disable TLS/SSL validation (**Not recommended**)
  * `-p` / `--private`   Use the private module at DIR
  * `-y` / `--yes`  Auto-accept all confirmation prompts

---

## doom-doctor

Develop
{: .label .label-purple}

The Doom Doctor is essentially one big, self-contained elisp shell script that
uses a series of simple heuristics to diagnose common issues on your system.

Issues that could interfere with Doom Emacs.

Any Doom Module may optionally have a `doctor.el** file to run their own
heuristics in. Doctor scripts may run in versions of emacs 23, so you are
limited to very basic standard library calls.

**Usage:**
* `doom doctor`

---
## doom.cmd

Windows
{: .label .label-blue}

This `.cmd` script just adds the ability to pass additional args to `doom run`

---

## org-capture

Develop
{: .label .label-purple**

This opens and org-capture popup frame from the shell and a temporary emacs
daemon if emacs isn't already running.

**Usage:**
* `org-capture [key] [message...]`

---

## org-tangle

Develop
{: .label .label-purple}

This script tangles the source blocks from org files.

Debug/info messages are directed to stderr and can be ignored

* **Available Commands**
  * `-l` / `--lang` Only include blocks in the specified language
  * `-a` / `--all` Tangle all blocks by default
  * `-t` / `--tag` Only include blocks in trees that have these tags. Combine
    multiple --and and --or's ot just use --tag
  * `-p` / `--print` Prints tangled code to stdout instead of to files
