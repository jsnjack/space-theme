---
title: "Monitor process with top"
date: 2018-09-02T20:46:47+02:00
tags: ["linux", "top"]
---

One liner to monitor a process with the name `/wshub`:
```bash
top -p "$(pgrep -f /wshub)"
```
