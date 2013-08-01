# go-direx.el

## Introduction
You can view go code in a tree style viewer with `direx.el`.


## Screenshot

![go-direx1](image/go-direx1.png)


## Dependency

* [direx](https://github.com/m2ym/direx-el)
* [gotags](https://github.com/jstemmer/gotags)

You can install `direx` with package.el from MELPA.
And you can install `gotags` by `go get` as below.

```
% go get -u github.com/nsf/gotags
```


## Setup

```elisp
(require 'go-direx) ;; Don't need to require, if you install by package.el
(define-key go-mode-map (kbd "C-c C-j") 'go-direx-pop-to-buffer)
```

### Working with [popwin](https://github.com/m2ym/popwin-el)

```elisp
(require 'popwin)
(defvar popwin:special-display-config-backup popwin:special-display-config)
(setq display-buffer-function 'popwin:display-buffer)

(push '(direx:direx-mode :position left :width 0.4 :dedicated t :stick t)
      popwin:special-display-config)
```

#### Show buffer on right side

![go-direx2](image/go-direx-rightside.png)

```elisp
(push '(direx:direx-mode :position right :width 0.4 :dedicated t :stick t)
      popwin:special-display-config)
```