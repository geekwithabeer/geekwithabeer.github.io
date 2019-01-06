---
layout: post
title: Timeout when Importing from SQL Server to SQL Azure
date: 2012-06-21 04:56
categories: 
tags: [azure, sql, ssis, Uncategorized]
---

When migrating large data (<span>varbinarymax</span>, for example) from SQL Server to SQL Azure using SQL Server Import and Export Wizard, it might throw an error message such as "An existing connection was forcibly closed by the remote host. The connection has exceeded the timeout settings."<br><br>
To solve this, turn on"Asynchronous processing" for the destination .NET SQL provider.
