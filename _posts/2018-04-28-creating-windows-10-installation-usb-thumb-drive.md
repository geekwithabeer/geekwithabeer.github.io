---
layout: post
title: Creating Windows 10 installation USB thumb drive
date: 2018-04-28 08:16
categories: 
tags: [Uncategorized, windows 10]
---

Starting with around Windows 10 1709, *install.wim* has become too big to fit under FAT32 required for EFI boot. Luckily, Windows 10 1709 also includes the capability of making multiple volumes in any USD thumb drives, not just those exposing as non-removable (such as SanDisk Ultra 16GB).

1. Open **PowerShell** as administrator, and start `diskpart`:
1. In **diskpart**, run the following (where * is the disk number of the USB disk):

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

1. In **PowerShell**, run the following (where **G:\** is where the Windows ISO is mounted):

	```powershell
 	mkdir P:\sources
 	robocopy G:\boot P:\boot /MIR
  	robocopy G:\efi P:\efi /MIR
 	robocopy G:\sources P:\sources boot.wim
  	robocopy G:\ P:\ bootmgr bootmgr.efi
  	robocopy G:\ I:\ /MIR
 	```
