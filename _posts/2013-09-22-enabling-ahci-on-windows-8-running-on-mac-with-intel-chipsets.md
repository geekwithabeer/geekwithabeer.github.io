---
layout: post
title: Enabling AHCI on Windows 8 Running on Mac with Intel Chipsets
date: 2013-09-22 18:23
categories: 
tags: [ahci, mac, Uncategorized]
---

Tested on Mac Pro 3,1.

1. Locate this registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\storahci`, and change the value of ErrorControl (DWORD) from 3 to 0.

1. Locate this registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\storahci\StartOverride`, and change the value of 0 (DWORD) from 3 to 0 (create the DWORD if it doesn't exist).

1. Reboot into OS X. Run [ahci.sh](https://docs.google.com/file/d/0B-fqhdB2QCTMeXlEODczSE1pcm8/edit?usp=sharing) to modify the MBR.

1. Reboot into Windows. Install RST (the latest version that can be installed is [10.1.0.1008](https://docs.google.com/file/d/0B-fqhdB2QCTMZnpDSXMzbjJFeHM/edit?usp=sharing)).