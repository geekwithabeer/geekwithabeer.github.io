---
layout: post
title: Set up PPTP VPN on OpenVZ VPS
date: 2018-02-20 03:11
categories: 
tags: [Uncategorized]
---

<h3>Enable TAP/TUN and PPP</h3>
TAP/TUN and PPP are usually disabled by default. Use the control panel (for example, SolusVM) to enable them.
<h3>Install pptpd and ufw</h3>
sudo apt-get install pptpd ufw

Set up ufw

sudo ufw allow from [ip-address-to-connect-from]

sudo vi /etc/ufw/before.rules

iptables -P FORWARD ACCEPT
iptables --table nat -A POSTROUTING -o venet0 -j MASQUERADE

Set up pptpd

&nbsp;
