---
layout: post
title: Disable WD IntelliPark on a Mac
date: 2010-08-04 16:36
categories: 
tags: [intellipark, mac, Uncategorized, wd, wdidle3]
---

On a Mac Pro (Early 2008) to be precise. But it should works on any other Intel-based Mac with an ATA CD drive.

1. Download a boot CD with WDIDLE3 (http://www.rapidspread.com/file.jsp?id=ya20rxh4zp) and stick it into your Mac.

2. Shutdown your Mac, unplug all the hard drives, and plug the hard drive you want to disable IntelliPark into the last (#4) SATA drive slot.

3. Boot up your Mac and press alt (option) to enter the boot device selection phase. Choose the CD icon with "Windows" on it.

4. Once it's booted, use wdidle3 /r to check the status of IntelliPark or wdidle3 /d to disable IntelliPark.

I always feel strange since the energy wasted on drives broken by IntelliPark will sure outweight the energy saved by it.
