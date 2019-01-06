---
layout: post
title: How to Sysprep SQL Server 2012 Express
date: 2012-06-12 16:47
categories: 
tags: [sql, Uncategorized]
---

For some reason there's no "Advance" tab in the setup of SQL Server 2012 Express. To sysprep an installation, use the command line:<br><br><span>setup /action=PrepareImage</span><br><br><span>Then use the command line:</span><br><br><span>setup /action=CompleteImage</span><br>
to complete the installation.
