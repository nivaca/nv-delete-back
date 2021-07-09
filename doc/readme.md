# Description

The package `nv-delete-back` replicates the backward delete behavior of modern text editors like oXygen XML or Sublime Text.

# Available commands

# `(nv-delete-back-all)`
Backward deletes either (i) all empty lines, or (ii) one whole word, or (iii) a single non-word character. (This replicates the behaviour of `Ctrl-Backspace` in oxYgen XML Editor.)

# `(nv-delete-back)`
Backward-deletes either (i) all spaces, (ii) one whole word, or (iii) a single non-word/non-space character. (This replicates the behaviour of `Ctrl-Backspace` in Sublime Text.)

# `(nv-delete-back-word &optional amount)`
Backward-deletes either (i) one whole word, or (ii) a single non-word character. If `amount` is supplied, the function will delete `amount` times of words or non-word characters. The function can also be called with a prefix. E.g. `C-u 5 M-x nv-delete-back-word` is equivalent to `(nv-delete-back-word 5)`.

# Compared to standard Emacs back-delete functions
## This is the standard behavior of `backward-kill-word`. Note how Emacs kills the word at the end of the previous line.

![backward-kill-word](/images/backward-kill-word.gif)

## This is the behavior of `nv-delete-back-all`. Note that the deletion stops at the last line containing text.

![nv-delete-back-all](/images/nv-delete-back-all.gif)

# Loading the package with `use-package`
```lisp
(use-package nv-delete-back
 :ensure t
 :bind
 ;; Suggested bindings
 (("C-<backspace>" . nv-delete-back-all)
   ("M-<backspace>" . nv-delete-back))
 )
```
