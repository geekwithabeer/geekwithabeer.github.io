---
layout: post
title: Install LAN driver on Intel NUC running Windows Server 2012/2012 R2
date: 2015-07-06 10:39
categories: 
tags: [intel nuc, Uncategorized, windows server 2012, windows server 2012 r2]
---

The Ethernet chip on Intel NUC (I-218V) is not supported by Windows Server 2012/2012 R2, but it has a identical (?) twin I-218LM that is supported.
	
1. Install the driver that came with NUC. It will fail with an error saying no adapter found

1. Right click the network card in Device Manager and go to **Update Driver**

1. Click **Let me pick from a list of device drivers on my computer**

1. Select **Intel** (not **Intel Corporation**) under manufacturer and **Intel(R) Ethernet Connection I218-LM** from the list

Source: http://stackoverflow.com/questions/25031066/integrate-lan-drivers-for-windows-server-2012-r2-for-intel-nuc-with-mdt