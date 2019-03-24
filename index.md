---
layout: default
title: Home
nav_order: 1
description: "An Emacs configuration for the stubborn martian vimmer"
permalink: /
---

# Doom Emacs Documentation
{: .fs-9 }

Doom emacs is a Gnu Emacs configuration layer created by Henrik Lissner
for the stubborn martian vimmers.

{: .fs-6 .fw-700 }

---

## Mantras
* **Gotta go fast**. Startup and runtime speed are high priorities; many expensive, heavy-handed features and packages have been fine-tuned to that end.
* **Hacker-friendly**. Doom caters to the command line denizen unafraid of writing a little (or a lot of) code to tailor their editor. It also inherits your shell configuration, warts 'n all, and expects frequent trips into the terminal to manage Doom with its bin/doom utility.
* **Opinionated, but not stubborn**. Doom has many opinions spread out across its 120+ modules designed to iron out idiosynchrosies and provide a better and more consistent baseline experience of Emacs and its plugins. However, they mustn't ever compromise your ability to change, rewrite or disable any or all of it, if you ask nicely.
* **Written to be read**. Doom's source ought to be self documenting and easy to grok. Modules should be syntactically sweet and concise, and backend logic should be explicit and abstraction-light. Where complexity arises, comments and documentation shouldn't be far away.


## Feature Highlight
* A fast, organized and opinionated Emacs configuration with a command line interface.
* A custom, declarative package management system that combines package.el, use-package and quelpa, allowing you to manage packages from the command line and install packages from sources other than ELPA.
* A popup management system (powered by shackle) that minimizes the presence and footprint of temporary and/or disposable buffers.
* A vim-like experience with evil-mode, including ports for several vim plugins, C-x omnicompletion and a slew of custom ex commands.
* Integration with editorconfig. Let someone else argue about tabs and spaces. (spaces, duh).
* Code completion for many languages, powered by company-mode (some languages may have external dependencies).
* Project-awareness powered by projectile, with tools and an API to navigate and manage projects and their files.
* Fast project search (and replace) utilities, powered by the_silver_searcher, ripgrep and wgrep, with integration for ivy (the default), helm and ido.
* Isolated and persistent workspaces powered by persp-mode. Also substitutes for vim tabs.
* Inline/live code evaluation (using quickrun), including REPLs for a variety of languages.


## Dependencies

Doom only supports Emacs >= 25.1, and is tested on Arch Linux 4.7+ and MacOS 10.11. YMMV on other platforms.
{: .fw-700}

## Quick start: Install using the `master` branch.

```bash
git clone https://github.com/hlissner/doom-emacs ~/.emacs.d
cd ~/.emacs.d
cp init.example.el init.el  # maybe edit init.el
make install
```

## Quick start: Install using the `develop` branch.

```bash
git clone https://github.com/hlissner/doom-emacs ~/.emacs.d
git checkout develop
cd ~/.emacs.d
cp init.example.el init.el  # maybe edit init.el
make install
```

> Don't forget to run make every time you modify init.el!

## Screenshots

![Doom-emacs](https://raw.githubusercontent.com/hlissner/doom-emacs/screenshots/main.png)

---

## Help this page!

This page is still in development and will continue to improve for you and
other doom users! Please consider helping us at our [main
repo](https://github.com/VentGrey/doom-emacs-docs)
or please help [Doom emacs](https://github.com/hlissner/doom-emacs) development!
