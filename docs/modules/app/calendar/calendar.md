---
layout: default
title: Calendar
nav_order: 3
has_children: false
parent: App
permalink: /docs/modules/app/calendar
---

# Calendar App

---

## Setup sync between google calendar and org file

---

* Checkout https://github.com/myuhe/org-gcal.el, put the following content in a file secret.el and set the variable `+calendar-org-gcal-secret-file` to the path of that file.

```emacs-lisp
(setq org-gcal-client-id "your-id-foo.apps.googleusercontent.com"
      org-gcal-client-secret "your-secret"
      org-gcal-file-alist '(("your-mail@gmail.com" .  "~/schedule.org")
                            ("another-mail@gmail.com" .  "~/task.org")))
```

## Doom faces

---

I'm using the following settings:

```emacs-lisp
;; calfw
(cfw:face-title              :foreground blue                     :bold bold :height 2.0 :inherit 'variable-pitch)
(cfw:face-header             :foreground (doom-blend blue bg 0.8) :bold bold)
(cfw:face-sunday             :foreground (doom-blend red bg 0.8)  :bold bold)
(cfw:face-saturday           :foreground (doom-blend red bg 0.8)  :bold bold)
(cfw:face-holiday            :foreground nil :background bg-alt   :bold bold)
(cfw:face-grid               :foreground vertical-bar)
(cfw:face-periods            :foreground yellow)
(cfw:face-toolbar            :foreground nil :background nil)
(cfw:face-toolbar-button-off :foreground base6                    :bold bold             :inherit 'variable-pitch)
(cfw:face-toolbar-button-on  :foreground blue                     :bold bold             :inherit 'variable-pitch)

(cfw:face-default-content    :foreground fg)
(cfw:face-day-title          :foreground fg                       :bold bold)
(cfw:face-today-title        :foreground bg  :background blue     :bold bold)
(cfw:face-default-day                                             :bold bold)
(cfw:face-today              :foreground nil :background nil      :bold bold)
(cfw:face-annotation         :foreground violet)
(cfw:face-disable            :foreground grey)
(cfw:face-select                             :background region)
```


## Adjust calendar to be included
---

Checkout example from https://github.com/kiwanami/emacs-calfw

```emacs-lisp
(defun my-open-calendar ()
  (interactive)
  (cfw:open-calendar-buffer
   :contents-sources
   (list
    (cfw:org-create-source "Green")  ; orgmode source
    (cfw:howm-create-source "Blue")  ; howm source
    (cfw:cal-create-source "Orange") ; diary source
    (cfw:ical-create-source "Moon" "~/moon.ics" "Gray")  ; ICS source1
    (cfw:ical-create-source "gcal" "https://..../basic.ics" "IndianRed") ; google calendar ICS
   ))) 
```

Specifically, if you want to adjust the org files to be included, use a let binding to set the org-agenda-files like below:

```emacs-lisp
;;;###autoload
(defun cfw:open-org-calendar-with-cal1 ()
  (interactive)
  (let ((org-agenda-files '("/path/to/org/" "/path/to/cal1.org")))
    (call-interactively '+calendar/open-calendar)))

;;;###autoload
(defun cfw:open-org-calendar-with-cal2 ()
  (interactive)
  (let ((org-agenda-files '("/path/to/org/" "/path/to/cal2.org")))
    (call-interactively '+calendar/open-calendar)))
```
