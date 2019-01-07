---
layout: post
title: disable-acrobat-contextual-menu
date: 2019/1/7
---

1. Open **Windows PowerShell**.

1. Navigate to _C:\Program Files (x86)\Adobe\Acrobat 2015\Acrobat Elements_ (it might differ depending on the version/edition of Acrobat you have).

1. Run the following commands:

    `regsvr32.exe /u ContextMenuShim64.dll`  
    `regsvr32.exe /u ContextMenu64.dll`  
    `regsvr32.exe /u ContextMenu.dll`  
