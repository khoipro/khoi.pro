---
title: "Load remote assets in WordPress local projects"
date: 2019-10-09T17:33:11+07:00
draft: true
tags: [wordpress,cdn,local,remote,proxy]
---

Recently when working with a few WordPress project which was published, I'm too lazy and don't want to download the copy of assets (around 3-4GB images) in `wp-content/uploads` folder.

So I tried to figure it out using another way: running WordPress filters and replace URLs to load direct from a remote URL.

## Benefits

### Good

- You don't need to wait to download a big asset.
- It's easy to make it working. My snippet works very smoothly. Just paste in inside your `functions.php` and replace your own remote domain name.

### Bad

- You shouldn't upload from a local environment. In case you really need to do that, try to upload a same file to both of remote and local environments (so shame).

## What did I do?

Don't worry, here is my snippet. Do you see a magic?

<script src="https://gist.github.com/khoipro/2468302fe8a948f8d2c0117387bae65c.js"></script>
