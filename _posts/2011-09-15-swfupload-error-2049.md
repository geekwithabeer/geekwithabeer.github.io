---
layout: post
title: SWFUpload Error #2049
date: 2011-09-15 15:41
categories: 
tags: [flash, security, swfupload, Uncategorized]
---

This is actually an issue I encountered a long time ago (back in 2009 when Syrupie first started using CDN). Recently Syrupie changed its CDN domain to s-syrupie and the issue came again.<br><br>
This issue is because the website and SWFUpload files reside on different domains, and cross-domain access violation occurs when the JavaScript on the website domain tries to access the swf files on the CDN domain.<br><br>
The solution is to add the CDN domain to crossdomain.xml in the root of the website.
