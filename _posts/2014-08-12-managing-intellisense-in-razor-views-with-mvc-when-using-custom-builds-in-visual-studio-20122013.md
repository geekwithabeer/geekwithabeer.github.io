---
layout: post
title: Managing Intellisense in Razor Views with MVC when using custom builds in Visual Studio 2012/2013
date: 2014-08-12 13:24
categories: 
tags: [asp.net mvc, mvc, razor, Uncategorized, visual studio, visual studio 2012, visual studio 2013]
---

The root cause is that when the output directory is set to a directory other than bin, IntellisenseProvider can't find the DLL files.

A quick-n-dirty workaround is just set the output directory to default. For a comprehensive solution, see [http://www.dennisonpro.info/managing-intellisense-in-razor-views-with-mvc-5-using-custom-builds-in-visual-studio-2013/](http://www.dennisonpro.info/managing-intellisense-in-razor-views-with-mvc-5-using-custom-builds-in-visual-studio-2013/" target="_blank).
