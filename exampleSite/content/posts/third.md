---
title: "Firefox Quantum: No titlebar"
date: 2018-09-01T20:46:47+02:00
tags: ["linux", "firefox", "xnotitle", "mine"]
---

In "old" Firefox times I used to use HTitle extension. It removes useless titlebar in Firefox in GNOME 3. However, the extension was discontinued. Firefox starting version 56 does not support Legacy extension and new solution is needed.

I wrote a small application which hides titlebar of the maximized windows. xnotitle is written in Go. By default, every second it checks for a new window which contains "Mozilla Firefox" in the title and applies special style to disable the title bar when the window is maximized.

xnotitle can be used to hide title bar for any application. Specify window title to hide with -name argument. You can also adjust how often xnotitle is going to check for new windows.

To start using application, clone the repository and build the project:
```bash
git clone git@github.com:jsnjack/xnotitle.git
make build
```

You should have go installed.

After xnotitle is compiled, start it automatically with the system by creating ~/.config/autostart/xnotitle.desktop file with the following content:
```
[Desktop Entry]
Type=Application
Name=xnotitle
Comment=xnotitle hides title bar of the specified windows
Exec=/home/jsn/go/src/github.com/jsnjack/xnotitle/xnotitle
Terminal=false
```
I recommend also installing Close Window Button extension to add Close window button (as titlebar is gone and all window control buttons too)
