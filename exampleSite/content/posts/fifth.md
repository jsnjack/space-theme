---
title: "Overwrite response body with mitmproxy 2"
date: 2018-08-02T20:46:47+02:00
tags: ["linux", "mitmproxy"]
---

Run python script with mitmproxy:
```bash
mitmproxy --ignore ws.sitesupport.net:443 -s script.py
```

Script example:
```python
from mitmproxy.script import concurrent

OLD = """var totalExpGems=0;"""
NEW = """var totalExpGems=0;debugger;"""


@concurrent
def response(flow):
    if "gem_finder" in flow.request.path:
        flow.response.headers["XX"] = "PATCHED"
        body = flow.response.content.decode("utf-8")
        if OLD in body:
            flow.response.content = body.replace(OLD, NEW).encode("utf-8")
            flow.response.headers["XXX"] = "PATCHED"
```
