---
layout: default
title: E-Mail
nav_order: 3
has_children: true
parent: App
permalink: /docs/modules/app/email
---

# Email App

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Description

---

This module makes Emacs an email client, using mu4e.

> I want to live in Emacs, but as we all know, living is incomplete without email. So I prayed to the text editor gods and they (I) answered. Emacs+evil’s editing combined with org-mode for writing emails? Yes please.
> It uses mu4e to read my email, but depends on offlineimap (to sync my email via IMAP) and mu (to index my mail into a format mu4e can understand).

### Module Flags

---

* `+gmail` Enables gmail-specific configuration.

### Plugins

---

* [mu4e-maildirs-extension](https://github.com/agpchil/mu4e-maildirs-extension)


## Prerequisites
This module requires:

* Either `mbsync` (default) or `offlineimap` (to sync mail with)
* `mu` (to index your downloaded messages)

### MacOS

---

```bash
brew install mu --with-emacs
# And one of the following
brew install isync  # mbsync
brew install offlineimap
```


### Arch Linux

---

```bash
sudo pacman --noconfirm --needed -S mu
# And one of the following
sudo pacman -S isync  # mbsync
sudo pacman -S offlineimap
```


## Features

---

## Configuration

---

### offlineimap
This module uses `mbsync` by default. To change this, change `+email-backend`:

```emacs-lisp
(setq +email-backend 'offlineimap)
```

Then you must set up offlineimap and index your mail:

1. Write a` \~/.offlineimaprc`. Mine can be found in my dotfiles repository. It is configured to download mail to \~/.mail. I use unix pass to securely store my login credentials.
2. Download your email: `offlineimap -o` (may take a while)
3. Index it with mu: `mu index --maildir ~/.mail`

Then configure Emacs to use your email address:

```emacs-lisp
;; Each path is relative to `+email-mu4e-mail-path', which is ~/.mail by default
(set-email-account! "Lissner.net"
  '((mu4e-sent-folder       . "/Lissner.net/Sent Mail")
    (mu4e-drafts-folder     . "/Lissner.net/Drafts")
    (mu4e-trash-folder      . "/Lissner.net/Trash")
    (mu4e-refile-folder     . "/Lissner.net/All Mail")
    (smtpmail-smtp-user     . "henrik@lissner.net")
    (user-mail-address      . "henrik@lissner.net")
    (mu4e-compose-signature . "---\nHenrik Lissner"))
  t)
  ```
