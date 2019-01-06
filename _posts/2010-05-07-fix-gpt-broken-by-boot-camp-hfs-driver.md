---
layout: post
title: Fix GPT Broken by Boot Camp HFS Driver
date: 2010-05-07 11:57
categories: 
tags: [gpt, mac, Uncategorized]
---

Boot Camp's HFS driver breaks OS X partition quite frequently (especially when assigning drive letter to it). The cause is Windows/HFS driver will change OS X partition's partition type from "Apple HFS+" to "Microsoft Basic Data", causing it become unrecognizable by Mac's EFI. One fix is using [gpt_surgeon.py](http://steelpangolin.wordpress.com/2009/03/15/invalid-bs_jmpboot-in-boot-block-000000/). Another fix that runs Windows and without requiring Python is [GPT fdisk](http://sourceforge.net/projects/gptfdisk/).

GPT fdisk actually does a lot more than changing GPT partition type. But this feature saved the day.
