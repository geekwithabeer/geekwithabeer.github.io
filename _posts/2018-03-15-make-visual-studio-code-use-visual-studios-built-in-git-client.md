---
layout: post
title: Make Visual Studio Code use Visual Studio's built-in Git client
date: 2018-03-15 14:59
categories: 
tags: [git, Uncategorized, visual studio, visual studio code]
---

Visual Studio 2017 comes with a Git client, Git for Windows. However, as it is installed within Visual Studio 2017, Visual Studio Code is not aware of its existence and complains about the lack of a Git client.

To make VS Code use the Git client already exists in the system:

1. Add these two path variables:
	
	- `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\Git\mingw32\bin`
	
	- `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\Git\usr\bin`

1. In PowerShell, execute `git config --global credential.helper manager`

1. In VS Code, open User Settings (**Ctrl** + **,**). Change the value of **git.path** to **C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Enterprise\\Common7\\IDE\\CommonExtensions\\Microsoft\\TeamFoundation\\Team Explorer\\Git\\mingw32\\bin\\git.exe**.