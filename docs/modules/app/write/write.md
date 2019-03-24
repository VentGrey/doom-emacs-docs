---
layout: default
title: Write
nav_order: 3
has_children: false
parent: App
permalink: /docs/modules/app/write
---

Adds word processing tools and the `+write-mode` minor mode, which
converts Emacs into a more comfortable writing environment.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Features

This module provides two module flags:

  - `+langtool` Enables language tool integration.
  - `+wordnut` Enables wordnet integration.

## `M-x +write-mode`

Write mode makes Emacs a more comfortable writing environment by:

  - Centering the buffer (with `visual-fill-column-mode`), ala
    distraction-free mode from other text editors.
  - Soft-wrapping long text lines with `visual-line-mode`.
  - Enabling `mixed-pitch-mode`, allowing fixed-width and variable-pitch
    fonts to co-exist in one buffer. For example, a monospace font for
    SRC blocks and Arial for everything else.
  - In org-mode:
      - Turns on `org-indent-mode`
      - Turns on `+org-pretty-mode`

## Language Tool `+langtool`

[Language Tool](https://www.languagetool.org/) is a polyglot proofreader
service that checks for grammar and stylistic issues in your writing.
This requires Java 1.8+.

> This requires Java 1.8+

### Commands

  - `langtool-check`
  - `langtool-correct-buffer`

## Wordnut `+wordnut`

Wordnut provides a searchable dictionary frontend for Emacs. This
requires `wordnet`, which should be available in your OS's package
manager.

### Commands

  - `wordnut-search`
  - `wordnut-lookup-curent-word`

## Synosaurus

Synosaurus provides a service for looking up synonyms. It requires an
internet connection.

### Commands

  - `synosaurus-lookup`
  - `synosaurus-choose-and-replace`

# Prerequisites

## Language Tool

Either download and deploy it from <https://languagetool.org/> or
install it through your OS package manager:

``` bash
# MacOS/Homebrew users:
brew install languagetool

# Arch Linux users:
sudo pacman -S languagetool
```

This module tries to guess the location of languagetool-commandline.jar.
If you get a warning that Doom `couldn't find
languagetool-commandline.jar`, you will need to find
langaugetool-commandline.jar and set `langtool-language-tool-jar` to its
path.

## Wordnut

This requires `wordnet` to be installed, which should be available
through your OS package manager:

``` bash
# MacOS/Homebrew users:
brew install wordnet

# Arch Linux users:
sudo pacaur -S wordnet  # on the AUR
```

# Configuration

## mixed-pitch-mode

To configure which faces are displayed with fixed-pitch fonts in
`mixed-pitch-mode`, look into `mixed-pitch-fixed-pitch-faces`.

# Appendix

## Minor modes

  - `+write-mode`
  - \~mixed-p
