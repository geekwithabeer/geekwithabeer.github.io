---
layout: post
title: Recursively Locating Zero Length Files
date: 2013-06-21 11:34
categories: 
tags: [powershell, Uncategorized]
---

Recently had some issue with a LUN on a QNAP NAS. After chkdsk, some files are recovered but the content is empty.<br><br>
I used the PowerShell command below to locate all those zero length files:<br><span>get-childitem -recurse *.* | where-object {$_.length -eq 0}</span>
