---
layout: default
title: Ivy
nav_order: 3
has_children: false
parent: Completion
permalink: /docs/modules/ivy
---

# Description

This module provides Ivy integration for a variety of Emacs commands, as
well as a unified interface for project search and replace, powered by
ag, rg, pt, git-grep & grep (whichever is available).

> I prefer ivy over ido for its flexibility. I prefer ivy over helm
> because it's lighter, simpler and faster in many cases.

## Module Flags

  - `+fuzzy` Enables the fuzzy method for ivy searches.
  - `+childframe` Causes Ivy to display in a floating child frame, above
    Emacs. **This requires GUI Emacs 26.1+**

## Plugins

  - [ivy](https://github.com/abo-abo/swiper)
  - [counsel](https://github.com/abo-abo/swiper)
  - [counsel-projectile](https://github.com/ericdanan/counsel-projectile)
  - [swiper](https://github.com/abo-abo/swiper)
  - [ivy-hydra](https://github.com/abo-abo/swiper)
  - [ivy-rich](https://github.com/yevgnen/ivy-rich)
  - [wgrep](https://github.com/mhayashi1120/Emacs-wgrep)
  - [amx](https://github.com/DarwinAwardWinner/amx)
  - [flx](https://github.com/lewang/flx)\* (`+fuzzy`)
  - [ivy-posframe](https://github.com/tumashu/ivy-posframe)\*
    (`+childframe`)

## Hacks

  - Functions with ivy/counsel equivalents have been globally remapped
    (like `find-file` =\> `counsel-find-file`). So a keybinding to
    `find-file` will invoke `counsel-find-file` instead.
  - `counsel-[arp]g`'s 3-character limit was reduced to 1 (mainly for
    the ex command)

# Prerequisites

This module optionally depends on one of:

  - [ripgrep](https://github.com/BurntSushi/ripgrep) (rg)
  - [the<sub>silversearcher</sub>](https://github.com/ggreer/the_silver_searcher)
    (ag)
  - [the<sub>platinumsearcher</sub>](https://github.com/monochromegane/the_platinum_searcher)
    (pt)

Ripgrep is recommended, but the order of its results aren't
deterministic and it doesn't support full PCRE (at the time of writing).
The<sub>silversearcher</sub> is a good alternative if either of these
