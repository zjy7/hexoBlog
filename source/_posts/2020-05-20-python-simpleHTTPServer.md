---
title: python simpleHTTPServer
date: 2020-05-20 10:23:10
tags:
categories:
- Code
---

## python -m SimpleHTTPServer [port]

### The SimpleHTTPServer module that comes with Python is a simple HTTP server that provides standard GET and HEAD request handlers.

```
POST on http:localhost:88
Status: 501 Unsupported method ('POST')
PUT on http:localhost:88
Status: 501 Unsupported method ('PUT')
```

## 另外
python 3.7版本，没有SimpleHTTPServer模块

python -m http.server 80