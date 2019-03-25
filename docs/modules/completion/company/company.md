---
layout: default
title: Company
nav_order: 3
has_children: false
parent: Completion
permalink: /docs/modules/company
---

# Description

This module provides code completion, powered by
[company-mode](https://github.com/company-mode/company-mode). It is
required for code completion in many of Doom's :lang modules.

<https://assets.doomemacs.org/completion/company/overlay.png>

## Module Flags

  - `+auto` Enables as-you-type completion.
  - `+childframe` Enables displaying completion candidates in a child
    frame, rather than an overlay or tooltip (among with other UI
    enhancements). **This requires GUI Emacs 26.1+.**

## Plugins

  - [company-mode](https://github.com/company-mode/company-mode)
  - [company-dict](https://github.com/hlissner/emacs-company-dict)
  - [company-prescient](https://github.com/raxod502/prescient.el)
  - [company-box](https://github.com/sebastiencs/company-box)

# Prerequisites

This module has no direct prerequisites.

However, some major modes may require additional setup for code
completion to work in them. Some major modes may have no completion
support at all. Check that major mode's module's documentation for
details.

# Features

## Code completion

Ccompletion must be triggered manually with the `C-SPC` key. If you want
as-you-type code completion, the `+auto` module flag will enable it.

| Keybind | Description                          |
| ------- | ------------------------------------ |
| `C-SPC` | Invoke code completion manually      |
| `C-n`   | Go to next candidate                 |
| `C-p`   | Go to previous candidate             |
| `C-j`   | (evil) Go to next candidate          |
| `C-k`   | (evil) Go to previous candidate      |
| `C-h`   | Display documentation (if available) |
| `C-u`   | Move to previous page of candidates  |
| `C-d`   | Move to next page of candidates      |
| `C-s`   | Filter candidates                    |
| `C-S-s` | Search candidates with helm/ivy      |
| `C-SPC` | Complete common                      |
| `TAB`   | Com                                  |
