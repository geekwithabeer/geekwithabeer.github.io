---
layout: post
title: Strong Name Verification on IIS
date: 2011-03-20 12:10
categories: 
tags: [.net, asp.net, iis, security, Uncategorized]
---

<span>For some reason I need to enable strong name verification skipping of a certainly assembly using sn.exe (sn -vr). It worked fined on my dev machine, but failed when I published the web application to the web server. I then ran a test app on the web server and the assembly loaded fine.</span><br><span><br></span><br><span>The reason turned out to be because IIS runs on 64-bit mode, and sn works with 32-bit registry. Duplicating the registry (from [HKEY_LOCAL_MACHINESOFTWAREMicrosoftStrongNameVerification*,*] to [HKEY_LOCAL_MACHINEWow6432NodeSOFTWAREMicrosoftStrongNameVerification*,*] solved it.</span>
