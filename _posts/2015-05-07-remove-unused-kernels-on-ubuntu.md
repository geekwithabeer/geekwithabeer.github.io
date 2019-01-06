---
layout: post
title: Remove "unused" kernels on Ubuntu
date: 2015-05-07 15:49
categories: 
tags: [linux, ubuntu, Uncategorized]
---

From <a class="question-hyperlink" href="http://askubuntu.com/a/590841/156790" target="_blank">Why doesn't Ubuntu remove old kernels automatically?</a>,

`apt-get autoremove` will remove all kernels except for the latest one and the one used in the last successful boot.

If /boot is 100% full and apt-get can't run (showing error message 'disk is full'), use rm to remove the oldest kernel in /boot:
`cd /boot
sudo rm *-3.16.0-23-generic`
