---
layout: post
title: Launching Remote Desktop through a rdp:// hyperlink
date: 2015-08-24 04:14
categories: 
tags: [rdp, remote desktop, Uncategorized]
---

A very neat batch file will do the trick: [download](http://www.jjclements.co.uk/wp-content/uploads/2010/02/rdp.zip" target="_blank).

From [JJClements.co.uk](http://www.jjclements.co.uk/2010/02/21/rdp-hyperlink/" target="_blank).

If the download is not available, create a batch file using the code below:

    @echo off
    :menu
    echo RDP:// HyperLink - James Clements - james@jjclements.co.uk
    echo ----------------------------------------------------------
    echo.
    echo.
    echo 1. Install RDP Association
    echo 2. Uninstall RDP Association
    echo 3. Quit
    echo.
    set choice=
    set /p choice=[1,2,3]? 
    echo.
    if not '%choice%'=='' set choice=%choice:~0,1%
    if '%choice%'=='1' goto install
    if '%choice%'=='2' goto uninstall
    if '%choice%'=='3' goto quit
    echo.
    echo.
    echo "%choice%" is not a valid option - please try again
    echo.
    pause
    cls
    goto MENU

    :quit
    cls
    exit

    :uninstall
    if not exist "C:Windowsrdp-scheme.js" (
    cls
    echo RDP:// HyperLink - James Clements - james@jjclements.co.uk
    echo ----------------------------------------------------------
    echo.
    echo.
    echo RDP:// HyperLink not installed - nothing to remove
    echo.
    pause
    exit)

    del "C:Windowsrdp-scheme.js" /f
    reg delete "HKCRrdp" /f

    cls
    echo RDP:// HyperLink - James Clements - james@jjclements.co.uk
    echo ----------------------------------------------------------
    echo.
    echo.
    echo RDP:// HyperLink uninstalled successfully
    echo.
    pause
    exit

    :install
    if exist "C:Windowsrdp-scheme.js" (
    cls
    echo RDP:// HyperLink - James Clements - james@jjclements.co.uk
    echo ----------------------------------------------------------
    echo.
    echo.
    echo RDP:// HyperLink already installed - nothing to install
    echo.
    pause
    exit)

    echo var server=(WScript.Arguments(0))&gt;&gt;C:Windowsrdp-scheme.js
    echo var prefix='rdp://'&gt;&gt;C:Windowsrdp-scheme.js
    echo var app='C:\WINDOWS\system32\mstsc.exe'&gt;&gt;C:Windowsrdp-scheme.js
    echo server=server.replace(prefix, '')&gt;&gt;C:Windowsrdp-scheme.js
    echo server=server.replace('/', '')&gt;&gt;C:Windowsrdp-scheme.js
    echo var shell = new ActiveXObject("WScript.Shell")&gt;&gt;C:Windowsrdp-scheme.js
    echo shell.Exec(app + " /v:" + server)&gt;&gt;C:Windowsrdp-scheme.js

    reg add "HKCRrdp" /f /v "" /t REG_SZ /d "URL:Remote Desktop Connection"
    reg add "HKCRrdp" /f /v "URL Protocol" /t REG_SZ /d ""
    reg add "HKCRrdpDefaultIcon" /f /v "" /t REG_SZ /d "C:WINDOWSSystem32mstsc.exe"
    reg add "HKCRrdpshellopencommand" /f /v "" /t REG_SZ /d "wscript.exe C:WINDOWSrdp-scheme.js %%1"

    cls
    echo RDP:// HyperLink - James Clements - james@jjclements.co.uk
    echo ----------------------------------------------------------
    echo.
    echo.
    echo RDP:// HyperLink installed successfully
    echo.
    pause
    exit