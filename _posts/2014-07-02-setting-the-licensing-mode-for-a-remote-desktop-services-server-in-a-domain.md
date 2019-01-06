---
layout: post
title: Setting the licensing mode for a Remote Desktop Services server in a domain
date: 2014-07-02 23:43
categories: 
tags: [Uncategorized]
---

For some reason, the UI in "Edit Deployment Properties" doesn't work. I had to use gpedit.msc.

Local Computer Policy -&gt; Computer Configuration -&gt; Administrative Templates -&gt; Windows Components -&gt; Remote Desktop Services -&gt; Remote Desktop Session Host -&gt; Licensing

"Use the specified RD license servers" = [servername]

"Set the Remote Desktop licensing mode" = Per User
