---
layout: post
title:  "Git Reword Commit and Rebase"
date:   2020-03-18 +0800
categories: git
---
# Git Merge, Reword and Rebase

## Merge branch to master
```console
git checkout master
git pull origin master
git merge test
git push origin master
```

## Reword commit
```console
do something
git commit --amend
```
rewrite the last commit, before that you can do something like add some files forgot to track

## Rebase
```console
rebase -i HEAD~4
```
reword any of the last 4 commits of this blog  

```console
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
```

## Rebase on top of master
如果情况是这样的
```
       A---B---C feature
     /
D---E---F---G upstream/master
```
master开发者改了代码，那么如果你希望你的feature是基于G而不是E:
```
               A'--B'--C' feature
             /
D---E---F---G upstream/master
```
那么我们这么做
```console
# Point our `upstream` remote to the original fork
git remote add upstream https://github.com/thoughtbot/factory_girl.git

# Fetch latest commits from `upstream` (the original fork)
git fetch upstream

# Checkout our feature branch
git checkout feature

# Reapply it onto upstream's master
git rebase upstream/master

# Fix conflicts, then `git rebase --continue`, repeat until done
# Push to our fork
git push --force origin feature
```

[reference](https://thoughtbot.com/blog/git-interactive-rebase-squash-amend-rewriting-history)
