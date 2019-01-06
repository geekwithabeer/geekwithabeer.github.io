---
layout: post
title: Ubuntu 10.10 on Hyper-V
date: 2010-12-20 13:33
categories: 
tags: [hyper-v, linux, Uncategorized]
---

Ubuntu 10.04 includes drivers for Hyper-V donated by MSFT, but these early drivers lack features like heartbeat and integrated shutdown, and the network driver is somewhat unstable (I find it stable enough for use though). Ubutu 10.10 includes updated drivers that provide the same features as on Red Hat Linux.<br><br>
Depending on installtion options, Ubuntu might have <span>hv_vmbus</span>, <span>hv_netvsc</span> and <span>hv_utils</span> enabled But we still have to manually enable others:<br>
Add to <span>/etc/initramfs-tools/modules</span><br><blockquote><span>hv_vmbus</span><br><span>hv_storvsc</span><br><span>hv_blkvsc</span><br><span>hv_netvsc</span><br><span>hv_utils</span></blockquote>Then run <span>update-initramfs -u</span> and reboot it.
