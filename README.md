# Note

# I recommend that you use the [flycheck](https://github.com/flycheck/flycheck).

# Because, you can run the checker more than one. Of course, including `cppcheck`.


# flymake-cppcheck.el

Cppcheck for Emacs with flymake-mode.

To use [Cppcheck](http://cppcheck.sourceforge.net/) with Emacs, you will need Cppcheck installed.

You should be able to run

```sh
$ cppcheck
```

and, you'll also need to install [flymake-easy](https://github.com/purcell/flymake-easy).

# Usage

You'll need to add the directory containing `flymake-cppcheck.el` to your `load-path`.

If not, also add to your config

```lisp
(add-to-list 'load-path "~/.emacs.d/path/to/flymake-cppcheck.el")
```

## Add to your Emacs config

```lisp
(require 'flymake-cppcheck)
(add-hook 'c-mode-hook 'flymake-cppcheck-load)
(add-hook 'c++-mode-hook 'flymake-cppcheck-load)
```

## Enable messages

By default only `error` messages are shown.
Through the command more checks can be enabled.

```lisp
(custom-set-variables
 '(flymake-cppcheck-enable "all"))
```

multi:

```lisp
(custom-set-variables
 '(flymake-cppcheck-enable "warning,performance,information,style"))
```

* warning
* performance
* information
* style
* unusedFunction
* all

## cppcheck command location

By default, the location of the `cppcheck` command is searched.

```lisp
(custom-set-variables
 '(flymake-cppcheck-command "/path/to/cppcheck"))
```

## Where to create temporary copy

one of 'tempdir or 'inplace (default).

```lisp
(custom-set-variables
 '(flymake-cppcheck-location 'tempdir))
```

## For more informations

Please refer to [official document](http://cppcheck.sourceforge.net/manual.pdf).
