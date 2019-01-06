---
layout: post
title: Setting Up FTP with IIS 7.5/8
date: 2011-06-07 18:28
categories: 
tags: [ftp, iis, Uncategorized]
---

Things to check:

- Enable both sub-items under FTP (especially FTP Extensibility).

- Grant Network Service permission to IIS configuration files (through CMD, not PowerShell, otherwise will give "invalid parameter" error)

    - `ICACLS "%SystemDrive%WindowsSystem32inetsrvconfig" /grant "Network Service":R`

    - `ICACLS "%SystemDrive%WindowsSystem32inetsrvconfigadministration.config" /grant "Network Service":R`

    - `ICACLS "%SystemDrive%WindowsSystem32inetsrvconfigredirection.config" /grant "Network Service":R`