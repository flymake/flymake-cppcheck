flymake-cppcheck.el
================

CppCheck for Emacs with flymake-mode.

To use [CppCheck](http://cppcheck.sourceforge.net/) with Emacs, you will need CppCheck installed.

You should be able to run

    $ cppcheck

and, you'll also need to install [flymake-easy](https://github.com/purcell/flymake-easy).

Usage
=====

You'll need to add the directory containing `flymake-cppcheck.el` to your `load-path`.

If not, also add to your config

    (add-to-list 'load-path "~/.emacs.d/path/to/flymake-cppcheck.el")

Add to your Emacs config
------------------------

    (require 'flymake-cppcheck)
    (add-hook 'c-mode-hook 'flymake-cppcheck-load)
    (add-hook 'c++-mode-hook 'flymake-cppcheck-load)

Enable messages
------------------------------------

By default only `error` messages are shown.
Through the command more checks can be enabled.

    (custom-set-variables
     '(flymake-cppcheck-enable "all"))

* `error`

  * Used when bugs are found.

* `warning`

  * Suggestions about defensive programming to prevent bugs.

* `style`

  * Stylistic issues related to code cleanup (unused functions, redundant code, constness, and such).

* `performance`

  * Suggestions for making the code faster. These suggestions are only based on common knowledge.
  * It is not certain you’ll get any measurable difference in speed by ﬁxing these messages.

* `portability`

  * Portability warnings. 64-bit portability. code might work different on different compilers. etc.

* `information`

  * Informational messages about checking problems.

cppcheck command location
----------------------

By default, the location of the `cppcheck` command is searched.

    (custom-set-variables
     '(flymake-cppcheck-command "/path/to/cppcheck"))

Where to create temporary copy
------------------------------

one of 'tempdir or 'inplace (default).

    (custom-set-variables
     '(flymake-cppcheck-location 'tempdir))
