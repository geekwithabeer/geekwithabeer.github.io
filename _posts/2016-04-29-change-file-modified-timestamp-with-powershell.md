---
layout: post
title: Change file modified timestamp with PowerShell
date: 2016-04-29 18:09
categories: 
tags: [Uncategorized]
---

To change one file:
`(Get-Item ".Pi.bin").LastWriteTime = "2015/3/14 9:26 AM"`

To change multiple files:
`Get-ChildItems -recurse | where { $_.LastWriteTime.Year -eq "2014" } | foreach { $_.LastWriteTime = "2015/3/14 9:26 AM" }`
