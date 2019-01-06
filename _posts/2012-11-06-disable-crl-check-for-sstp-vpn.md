---
layout: post
title: Disable CRL Check for SSTP VPN
date: 2012-11-06 12:47
categories: 
tags: [crl, sstp, Uncategorized, vpn]
---

At the client computer, create a DWORD value `NoCertRevocationCheck` under
`HKLM\System\CurrentControlSet\Services\Sstpsvc\Parameters`.

Value 1 = disable certificate revocation check.
