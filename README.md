# go-direx.el [![melpa badge][melpa-badge]][melpa-link] [![melpa stable badge][melpa-stable-badge]][melpa-stable-link]

## Introduction

You can view go code in a tree style viewer with `direx.el`.


## Screenshot

![go-direx1](image/go-direx1.png)


## Requirements

* [direx](https://github.com/m2ym/direx-el)
* [gotags](https://github.com/jstemmer/gotags)

You can install `direx` with package.el from MELPA.
And you can install `gotags` by `go get` as below.

```
% go get -u github.com/jstemmer/gotags
```


## Installation

`go-direx` is available on [MELPA](https://melpa.org/) and [MELPA stable](https://stable.melpa.org/)

You can install `go-direx` with the following command.

<kbd>M-x package-install [RET] go-direx [RET]</kbd>



## Setup

```lisp
(require 'go-direx) ;; Don't need to require, if you install by package.el
(define-key go-mode-map (kbd "C-c C-j") 'go-direx-pop-to-buffer)
```

### Working with [popwin](https://github.com/m2ym/popwin-el)

```lisp
(require 'popwin)
(setq display-buffer-function 'popwin:display-buffer)

(push '("^\*go-direx:" :regexp t :position left :width 0.4 :dedicated t :stick t)
      popwin:special-display-config)
```

#### Show buffer on right side

![go-direx2](image/go-direx-rightside.png)

```lisp
(push '("^\*go-direx:" :regexp t :position right :width 0.4 :dedicated t :stick t)
      popwin:special-display-config)
```

[melpa-link]: https://melpa.org/#/go-direx
[melpa-stable-link]: https://stable.melpa.org/#/go-direx
[melpa-badge]: https://melpa.org/packages/go-direx-badge.svg
[melpa-stable-badge]: https://stable.melpa.org/packages/go-direx-badge.svg
