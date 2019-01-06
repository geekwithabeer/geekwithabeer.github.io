---
layout: post
title: Could not load file or assembly error when deploying ASP.NET MVC 2 on IIS 7.5
date: 2010-08-16 09:41
categories: 
tags: [asp.net, iis, mvc, Uncategorized]
---

The solution is to deploy `System.Web.Mvc.dll` on the web server. Set `Copy Local` to `$True` for `System.Web.Mvc`in References.
