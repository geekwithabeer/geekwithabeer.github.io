---
layout: post
title: "Resize Ubuntu VM disk"
date:   2019-01-06
categories: 
tags: ["hyper-v", "ubuntu"]
---

Tested on Ubuntu 18.04 VM with a GPT disk on Hyper-V.

1. Extend the VHD in Hyper-V

1. Extend the partition: 

    1. $ sudo parted
    
    1. print free
        It should show a warning:
            
            Warning: Not all of the space available to /dev/sda appears to be used, you can fix the GPT to use all of the space (anextra 167772160 blocks) or continue with the current setting?

    1. Let it fix it: `fix`
    
    1. Verify the free space is listed:

            Number Start    End     Size    File system     Name                    Flags
                   17.4kB   1049kB  1031kB  Free Space
                 1 1049kB   538MB   537MB   fat32           EFI System Partition    boot, esp
                 2 538MB    794MB   256MB   ext2
                 3 794MB    258GB   257GB   lvm
                   258GB    344GB   85.9GB  Free Space

    1. `quit`
    
    1. `sudo cfdisk`

        Select the device to resize, select **\[ Resize \]**, confirm the new size and hit Enter. Then select **\[ Write \]**, type yes. Finally select **\[ Quit \]**.

    1. Verify the new partition table: `$ sudo fdisk -l`

            Device      Start   End         Sectors     Size    Type
            /dev/sda1   2048    1050623     1048576     512M    EFI System
            /dev/sda2   1050624 1550335     499712      244M    Linux filesystem
            /dev/sda3   1550336 671088606   669538271   319.3G  Linux LVM

1. Resize the physical volume:  `$ sudo pvresize /dev/sda3`

1. Resize the logical volume: `sudo lvextend -l+100%FREE /dev/ubuntu-vg/root`

1. Get the name of the Filesystem: `df /`

1. Resize the filesystem: `sudo resize2fs /dev/mapper/ubuntu--vg-root`

1. Confirm the new size of the filesystem: `df /`
