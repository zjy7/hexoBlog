---
title: websocket四种状态
date: 2020-05-21 09:43:25
tags:
categories:
- Code
---

### 通常在实例化一个websocket对象之后，客户端就会与服务器进行连接。但是连接的状态是不确定的，于是用readyState属性来进行标识。它有四个值，分别对应不同的状态：

- CONNECTING：值为0，表示正在连接；
- OPEN：值为1，表示连接成功，可以通信了；
- CLOSING：值为2，表示连接正在关闭；
- CLOSED：值为3，表示连接已经关闭，或者打开连接失败。