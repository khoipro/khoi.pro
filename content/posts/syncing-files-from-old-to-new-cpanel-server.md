---
title: "Syncing Files From Old to New cPanel Server"
date: 2019-10-10T12:09:25+07:00
draft: false
tags: [cpanel,migration,syncing,data,ssh,dns]
---

Working with multiple servers (mostly cPanel) is one of my daily tasks. And we should try a **smart way** to do that.

## The Case

I must sync a single website (which was added to a cPanel account) to a new dedicated cPanel account on another cPanel server.

**Positive**

- Both of two servers are using cPanel, so I can quick navigate to find what could be done.
- I have a root access or any jailed shell access on the new server.

**Negative**

- In the old server, this website isn't a main domain and was used as the Addon Domain only. So meaning we can't use any existing feature from cPanel.
- I don't have a root access in the old server.

## Doing it in the smart way

I found a DNS zone is a great way to start, because when running `wget` (download) command via terminal, it will take a look for DNS resolver to see which IP belongs to a domain.

**Change a DNS record of a domain to old IP address**

It's a small tip, but it could save your day!

Go to WHM (root), navigate to "Edit DNS Zone" menu, find your wanted domain and update "A" record to your old server ip.

For  example, it should be:

```bash
A - domain.com - <old_server_ip>
```

**Download time**

Quite easy, navigate back to your cPanel account's home folder and start download a compress file.

```bash
cd /home/<username>/public_html/
wget http://domain.com/wp-content/uploads.tar.bz2
```

It returns a great result with 13s download. It quite fast comparing with your tradition way: download a file and upload it back.

```bash
[root@sv2 wp-content]# wget http://khoi.pro/wp-content/uploads.tar.bz2
--2019-10-10 05:08:46--  http://khoi.pro/wp-content/uploads.tar.bz2
Resolving khoi.pro(khoi.pro)... 45.124.84.5
Connecting to khoi.pro(khoi.pro) |45.124.84.5|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 919117754 (877M) [application/x-bzip]
Saving to: ‘uploads.tar.bz2’
100%[======================================>] 919,117,754 67.3MB/s   in 13s
```

**Change DNS back to your domain**

If you already had your own file, remember to set DNS back for A record.
