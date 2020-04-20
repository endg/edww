---
title: "Subproject commit -dirty"
description: 'Git diff: subproject is dirty'
keywords: ["Subproject", "dirty"]
date: 2020-04-03T16:01:23+08:00
lastmod: 2020-04-03T16:01:23+08:00
draft: false
tags: ["hugo"]
categories: ["Web"]
author: "dan"
slug: 'gitdirty'
# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
# comment: false
# toc: false

# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
#contentCopyright: '<a href="https://github.com/gohugoio/hugoBasicExample" rel="noopener" target="_blank">See origin</a>'
reward: false
# mathjax: true
---
keywords:Subproject

A.github中提示：Subproject commit 88bc8ad05dbf978eaae1ab6359a81acae4bfd034-dirty

B.git diff 提示 subproject dirty

> `https://stackoverflow.com/questions/4873980/git-diff-says-subproject-is-dirty`

尝试下面的方法中的一种

```
(1)git submodule foreach --recursive git checkout .

(2)git submodule update

(3)git diff --ignore-submodules
git status --ignore-submodules

(4)git config --global diff.ignoreSubmodules dirty
```

我使用了前两种方法都是合适的

