---
layout: post
title: Set up daily backup for Trello
date: 2018-08-30 22:57
categories: 
tags: [dropbox, trello, ubuntu, Uncategorized]
---

This is set up on an Ubuntu 18.04 server with [Trello Full Backup](https://github.com/jtpio/trello-full-backup" target="_blank" rel="noopener) and [Dropbox daemon](https://www.dropbox.com/install-linux).
 	
1. Install pip:`sudo apt-get install pythong3-pip`

1. Install Trello Full Backup: `pip install trello-full-backup`

1. Install Dropbox daemon, configure it and set it as a service: https://help.ubuntu.com/community/Dropbox (replace `user1 user2` in `/etc/init.d/dropbox` with the username of the Ubuntu user)

1. Create the Trello directory in Dropbox: `mkdir ~/Dropbox/Trello`

1. Create a shell script for Trello backup:

	`export TRELLO_API_KEY=YOUR-API-KEY`

	`export export TRELLO_TOKEN=YOUR-TRELLO-TOKEN`

	`~/.local/bin/trello-full-backup -d ~/Dropbox/Trello/ -i`

1. Set the script to run every day: `crontab -e` then add `0 * * * * /home/[username]/backup-trello.sh &gt;/dev/null 2&gt;&amp;1` to the crontab file