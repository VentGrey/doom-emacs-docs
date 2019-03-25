---
layout: default
title: Default
nav_order: 3
has_children: true
parent: Config
permalink: /docs/modules/config/default
---

This module provides a set of reasonable defaults, including:

  - A Spacemacs-esque keybinding scheme
  - Extra Ex commands for evil-mode users
  - A yasnippet snippets library tailored to Doom emacs
  - A configuration for (almost) universally repeating searches with `;`
    and `,`

> The defaults module is intended as a "reasonable-defaults" module, but
> also as a reference for your own private modules. You'll find [my
> private module in a separate
> repo](https://github.com/hlissner/doom-emacs-private).
> 
> Refer to the [Customization
> page](https://github.com/hlissner/doom-emacs/wiki/Customization) on
> the wiki for details on starting your own private module.

# Table of Contents <span class="tag" data-tag-name="TOC"><span class="smallcaps">TOC</span></span>

  - [Install](#install)
  - [Configuration](#configuration)
      - [Using another snippets
        library](#using-another-snippets-library)
      - [I'm not an evil user…](#im-not-an-evil-user)
  - [Appendix](#appendix)
      - [Commands](#commands)
      - [Hacks](#hacks)

# Install

This module has no external dependencies.

# Configuration

## Using another snippets library

Don't want to use provided one? Then add this to your private module,

``` commonlisp
;; in config/$USER/packages.el
(package! emacs-snippets :ignore t)

;; in config/$USER/config.el
(def-package-hook! emacs-snippets :disabled t)
(after! yasnippet
  (push "~/path/to/my/private/snippets" yas-snippet-dirs))
```

## I'm not an evil user…

That's fine. All evil configuration is ignored if `:feature evil` is
disabled.

# Appendix

## Commands

  - `+default/browse-project`
  - `+default/browse-templates`
  - `+default/find-in-templates`
  - `+default/browse-emacsd`
  - `+default/find-in-emacsd`
  - `+default/browse-notes`
  - `+default/find-in-notes`
  - `+default/find-in-snippets`

## Hacks

  - `epa-pinentry-mode` is set to `'loopback`, forcing gpg-agent to use
    the Emacs minibuffer when prompting for your passphrase. **Only
    works with GPG 2.1+\!**
