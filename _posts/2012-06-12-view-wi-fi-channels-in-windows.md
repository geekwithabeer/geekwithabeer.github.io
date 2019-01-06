---
layout: post
title: View Wi-Fi Channels in Windows
date: 2012-06-12 16:48
categories: 
tags: [Uncategorized, Wi-Fi, wireless]
---

1. Open **Command Prompt**.
1. Type `netsh`.
1. Type `wlan`.
1. Type `show all`.

Sample output: 

    Interface name : Wireless Network Connection
    There are 10 networks currently visible.
    SSID 1 : Wi-Fi
        Network type            : Infrastructure
        Authentication          : WPA2-Personal
        Encryption              : CCMP
        BSSID 1                 : 00:64:bf:ab:67:c8
            Signal             : 99%
             Radio type         : 802.11g
             Channel            : 6
             Basic rates (Mbps) : 1 2 5.5 6 11 12 24
            Other rates (Mbps) : 9 18 36 48 54</span>