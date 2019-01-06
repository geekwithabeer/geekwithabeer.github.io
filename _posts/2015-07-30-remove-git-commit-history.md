---
layout: post
title: Remove Git commit history
date: 2015-07-30 07:10
categories: 
tags: [git, Uncategorized]
---

Never really learn how to use `git rebase` to remove logs of certain commits, but to remove all commit history:

1. Checkout `git checkout --orphan latest_branch`

1. Add all the files `git add -A`

1. Commit the changes `git commit -am "removing history"`

1. Delete the branch `git branch -D master`

1. Rename the current branch to master `git branch -m master`

1. Finally, force update your repository `git push -f origin master`

Source: http://stackoverflow.com/a/26000395