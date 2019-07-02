---
layout: post
title: Set Network Location in Windows 8.1/Windows Server 2012 R2
date: 2014-08-12 13:17
categories: 
tags: [network location, Uncategorized, windows 8.1, windows server 2012 r2]
---

1. In Registry Editor, navigate to the location below: `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles`.

1. Double click/tap on the Profiles key in the left pane to expand it.

1. Click/tap on each long GUID number subkey, and look at its ProfileName string value in the right pane to see if it has the current network name.

1. When you find the correct ProfileName for your network name, double click/tap on the Category DWORD value in the same right pane to modify it.

1. Type in a new Value data number for the network location you want, and click/tap on OK (Public: 0, Private: 1, Domain: 2).

1. Reset the network adapter(s) if needed.
