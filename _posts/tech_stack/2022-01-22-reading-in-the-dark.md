---
title: Reading in the Dark
category: Tools
tags: [emacs, books, dark, lamp]
---

### [2022-01-22 Sat 18:33] - 7936

Recently, I've taken a liking to working in the dark. 
This involves coding with a dark color scheme with the lights out and
if I'm following a hard-copy, switching on the lights kills the flow.

One could always switch to a light colored screen momentarily but that
also kills the flow. To be precise, exiting emacs in moments of
weakness kills the flow.

Hence, a state-ful background toggler to the rescue:
```elisp

(defun toggle-background ()
  (interactive)
  (defvar background-state 0)
  (defvar last-background nil)
  (cond ( (= background-state 0) (progn
				   (setq last-background (background-color-at-point))
				   (set-background-color "#ffffff")
				   (setq background-state 1)))
	( t (progn
	      (set-background-color last-background)
	      (setq background-state 0)))))

(general-define-key "C-c C-t C-b" #'toggle-background)

```

This allows one to quickly go light and back into darkness without
much of a context switch.

Emacs now works as a lamp.
