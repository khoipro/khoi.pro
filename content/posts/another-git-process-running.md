---
title: "Another git process seems to be running in this repository"
date: 2019-10-10T11:57:42+07:00
tags: [git,cpanel,repository]
---

I work with Git on cPanel (oh really? cPanel provides support for Git Version control from [version 72](https://documentation.cpanel.net/display/72Docs/Git+Version+Control)). Using a Terminal menu but it crashes and disconnected sometimes.

So I open up a new Terminal and try to run a git command, for example: `git status`.

It returns:

```bash
fatal: Unable to create '/home/<username>/public_html/.git/index.lock': File exists.

Another git process seems to be running in this repository, e.g.
an editor opened by 'git commit'. Please make sure all processes
are terminated then try again. If it still fails, a git process
may have crashed in this repository earlier:
remove the file manually to continue.
```

For a quick search, I found it's because the existing of file `.git/index.lock`. Certainly, you could have a second choice of finding a process and kill it, however it's better to unlock Git and do your homework!

So it's easy to resolve this problem by typing `rm -f .git/index.lock`.

Then you can resume your work in a current repository.