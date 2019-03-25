---
layout: default
title: IRC
nav_order: 3
has_children: false
parent: App
permalink: /docs/modules/app/irc
---

# Table of Contents 

{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Description

---

This module turns adds an IRC client to Emacs with OS notifications.

## Module Flags

---

This module provides no flags.

## Plugins

---

  - [circe](https://github.com/jorgenschaefer/circe)
  - [circe-notifications](https://github.com/eqyiel/circe-notifications)

# Dependencies

---

This module requires `gnutls-cli` or `openssl` for secure connections.

# Prerequisites

---

This module has no direct prerequisites.

# Features

---

## An IRC Client in Emacs

---

To connect to IRC you can invoke the `=irc` function using `M-x` or your
own custom keybinding.

| command | description                               |
| ------- | ----------------------------------------- |
| `=irc`  | Connect to IRC and all configured servers |

When in a circe buffer these keybindings will be available.

| command                     | key       | description                                  |
| --------------------------- | --------- | -------------------------------------------- |
| `+irc/tracking-next-buffer` | `SPC m a` | Switch to the next active buffer             |
| `circe-command-JOIN`        | `SPC m j` | Join a channel                               |
| `+irc/send-message`         | `SPC m m` | Send a private message                       |
| `circe-command-NAMES`       | `SPC m n` | List the names of the current channel        |
| `circe-command-PART`        | `SPC m p` | Part the current channel                     |
| `+irc/quit`                 | `SPC m Q` | Kill the current circe session and workgroup |
| `circe-reconnect`           | `SPC m R` | Reconnect the current server                 |

# Configuration

---

Use `set-irc-server!` to configure IRC servers. Its second argument (a
plist) takes the same arguments as `circe-network-options`.

``` commonlisp
(set-irc-server! "chat.freenode.net"
  `(:tls t
    :nick "doom"
    :sasl-username "myusername"
    :sasl-password "mypassword"
    :channels ("#emacs")))
```

**It is a obviously a bad idea to store auth-details in plaintext,** so
here are some ways to avoid that:

## Pass: the unix password manager

---

[Pass](https://www.passwordstore.org/) is my tool of choice. I use it to
manage my passwords. If you activate the [:tools
password-store](../../../modules/tools/password-store/README.org) module
you get an elisp API through which to access your password store.

`set-irc-server!` accepts a plist can use functions instead of strings.
`+pass-get-user` an
