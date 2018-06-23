---
layout: post
title: "Hail Hydra!"
date:  2018-06-23 10:47:12 -0600
categories: emacs tips tricks packages
comments: 
---
I'm a little late to the game on some of the developments in the Emacs world and don't like breaking my workflow if I don't have to. Even so, when I find a package that I find incedibly useful, adjustments are worth the effort. [Hydra](https://github.com/abo-abo/hydra) is one such package that I think all serious Emacs users will appreciate.

The basic idea of a Hydra is that it is a collection of related commands which are all accessible with a leader combination or key. But here's where it gets interesting - once the leader key is pressed, there is no need to press additional modifiers for functions which are within the scope of that Hydra.

How exactly does this work? Here's a simple example for when I need to change a numeric argument to a function:

``` emacs-lisp
(defhydra hydra-increment (global-map "C-c")
  ("n" universal-argument)
  ("u" increment-integer-at-point)
  ("e" decrement-integer-at-point)
  ("/" undo))
```

Notice that the leader combination is "C-c", and all following commands are dedicated to one kind of task, incrementing or decrementing an integer near the cursor. As long as you don't press a key that isn't listed in the body of the Hydra, you can do this any number of times. I also included a way to give a numeric argument to the increment operation for cases when you want to change an integer by some amount other than 1. There is no need to press "C-u" in advance this way. You can also quickly undo an operation without pressing Control.

Neat, but we can do better.

How about a way to manage your windows?

``` emacs-lisp
(defhydra hydra-window-manager (global-map "C-.")
  ("s" split-window-below)
  ("S" split-window-right)
  ("o" other-window)
  ("k" (other-window -1))
  ("n" other-window)
  ("p" (other-window -1))
  ("f" find-file-other-window)
  ("x" ido-find-file)
  ("l" list-buffers)
  ("g" execute-extended-command)
  ("m" notmuch)
  ("t" eshell)
  ("d" dired)
  ("c" calc)
  ("." delete-other-windows))
```

For cases when I want to perform a bunch of operations in multiple windows quickly, this unbelievably simple Hydra is up to the task. My most common applications for which I might want to split a window are available, and both horizontal and vertical window management are easy (and there is more than one way to navigate them without the use of vi-like keys). The reason "k" is used instead of "h" is because I'm currently using Colemak Mod-DH, which moves "k" into that position. And granted, I could add a few things for resizing windows and that sort of thing, but it's not something I often do.

Another thing I find myself doing frequently is moving around and deleting (not killing) text. The reason I delete rather than kill is because I use helm to manage my kill-ring and it is also clipboard-aware, making it something of a lispy clipboard manager in StumpWM. Killing text all the time only clutters the kill-ring up (which I don't like even though it is searchable), so this does the intended job nicely.

``` emacs-lisp
(defhydra hydra-motion-and-deletion (global-map "C-M-S-s-e")
  ("." mark-line)
  ("a" move-beginning-of-line)
  ("n" next-line)
  ("p" previous-line)
  ("f" forward-char)
  ("b" backward-char)
  ("M-f" forward-word)
  ("M-b" backward-word)
  ("e" move-end-of-line)
  ("k" delete-region)
  (">" end-of-buffer)
  ("<" beginning-of-buffer)
  ("/" undo))
```

I didn't draw any inspiration from [god-mode](https://github.com/chrisdone/god-mode) for this, but before I knew it, I realized this was looking more and more like a modal package for Emacs. Whoops! It's surprising that it took so few lines, though.

And lest you think I'm using a ridiculous key combination for that, it is actually a "Hyper" key in QMK that presses all those modifiers at once. I haven't decided on a good leader combo for this one, so this is my placeholder that didn't get in the way of any other binding.

<br />

As always, this is a work in progress that will be fine-tuned in time.

Experienced Hydra users will probably recognize that there are better ways to do what I presented here and that I'm only scratching the surface of what is possible. I'm aware that Hydras can be linked together, plaintext menus are possible, and that there are a host of other things not covered here. This was really meant to be a quick look to whet the appetite, as it surely did for me. :) 

For those not using Hydra, remember, it's only a package-install away!
