---
title: "fedora: Install flashplayer in Firefox"
date: 2018-09-02T20:46:47+02:00
tags: ["fedora", "linux"]
---

I have flashplayer installed on my system from the official Adobe repository, but Firefox for some reason does not have flash plugin installed. You can check if your browser supports flash by navigating to this url

To make Firefox aware of flashplugin, try to create a symlink here:
```bash
cd http://isflashinstalled.com/ && ln -s /usr/lib64/flash-plugin/libflashplayer.so .
```

