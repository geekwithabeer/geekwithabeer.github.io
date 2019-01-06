---
layout: post
title: Creating Windows 10 installation USB thumb drive
date: 2018-04-28 08:16
categories: 
tags: [Uncategorized, windows 10]
---

Starting with around Windows 10 1709, *install.wim* has become too big to fit under FAT32 required for EFI boot. Luckily, Windows 10 1709 also includes the capability of making multiple volumes in any USD thumb drives, not just those exposing as non-removable (such as SanDisk Ultra 16GB).

1. In **PowerShell**, type (where * is the number of the USB disk):

	```powershell
	diskpart
	list disk
	select disk *
	clean
	create partition primary size=2048
	active
	format fs=FAT32 quick label="WinPE"
	assign letter=P
	create partition primary
	format fs=NTFS quick label="Images"
	assign letter=I
	exit
	```
	
1. In File Explorer, navigate to the root of the Windows ISO, and copy the *boot* and *efi* directories and the *bootmgr* and *bootmgr.efi* files to the *WinPE* volume.

1. Create a *sources* directory in the *WinPE* volume and copy *sources\boot.wim* from the Windows ISO to it.

1. Copy everything in the Windows ISO to the *Images* volume.