---
layout: default
title: Lispy
nav_order: 3
has_children: true
parent: Config
permalink: /docs/modules/editor/lispy
---

This modules adds [lispy](https://github.com/noctuid/lispyville) key
functionality in Lisp languages.

This includes:

  - Common Lisp
  - Emacs Lisp
  - Scheme
  - Racket
  - [Hy](http://docs.hylang.org/en/stable/)
  - [LFE](http://lfe.io/)
  - Clojure

If evil is enabled, lispyville would also be activated for every mode
where lispy is active

The default key themes that are set are as follows:

``` commonlisp
(lispyville-set-key-theme
 '((operators normal)
    c-w
    (prettify insert)
    (atom-movement normal visual)
    slurp/barf-lispy
    (wrap normal insert)
    additional
    additional-insert
    (additional-wrap normal insert)
    (escape insert)))
```

See noctuid's
[README](https://github.com/noctuid/lispyville/blob/master/README.org)
for more info on specific keybindings (starting
[here](https://github.com/noctuid/lispyville#operators-key-theme)) of
each key theme. Think of `lispyville-set-key-theme` as adding
`parinfer-extensions` via `(setq parinfer-extensions '(blah blah
blah))`.
