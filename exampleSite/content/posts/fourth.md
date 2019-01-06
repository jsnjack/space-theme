---
title: "Use mitmproxy with GNOME Web (Epiphany)"
date: 2018-08-28T20:46:47+02:00
tags: ["linux", "gnome", "epiphany", "ssl", "certs"]
---

To use mitmproxy with Epiphany you need to install CA certificate from mitmproxy. To do that, start mitmproxy and navigate to mitm.it. Download *.pem certificate (available under Other link). Install mitmproxy certificate with command:
```bash
sudo trust anchor mitmproxy-ca-cert.pem
```
With this command you can also install any custom certificate to use in Epiphany.
