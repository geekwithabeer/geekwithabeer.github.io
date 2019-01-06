---
layout: post
title: Set Administrator password for new Windows Server 2012 Server Core installation
date: 2017-04-30 23:56
categories: 
tags: [server core, Uncategorized, windows server 2016]
---

So I have spent the last 2 hours figuring out how to get pass the **Enter new credentials for Administrator **screen on a newly installed Windows Server 2016 Server Core.

After entering the new password, the process just seemed to stuck and wouldn't let me confirm the password no matter how many times I have hit **Enter** on how many keyboards:

![Screenshot that shows the Logon UI](/media/set-administrator-password-for-new-windows-server-2012-server-core-installation/logon-ui.png)

Eventually I came across [this blog post](https://mikaelfalkvidd.com/category/windows) - you are supposed to hit the **down arrow key** to move the cursor to **Confirm password**. Who knew?

With text-based UI like this, Microsoft really should stick with GUI.
