---
layout: post
title: Change ethX to ethY on Linux
date: 2010-12-20 13:05
categories: 
tags: [linux, Uncategorized]
---

The easiest way to do this is with udev.<br><br>
Edit <span>/etc/udev/rules.d/70-persistent-net.rules</span><br><br>
Find the line of the network interface you want to change<br><span>  SUBSYSTEM=="net", ACTION=="add", DRIVERS=="?*", ATTR{address}=="XX:XX:XX:XX:XX:XX", ATTR{dev_id}=="0x0", ATTR{type}=="1", KERNEL=="ethX", NAME="ethX"</span><br><br>
Then change from <span>ethX</span> to <span>ethY</span> (make sure ethY doesn't exist).
