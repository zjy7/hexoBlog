---
title: about jsessionid
tags:
---

### 第一次访问服务器的时候，后端会在Response Header里Set-Cookie，设置好jsessionId，之后的每次请求浏览器会在request Header里将这个cookie带上。

### 当用户访问服务器的时候会为每一个用户开启一个session，浏览器是怎么判断这个session到底是属于哪个用户呢？jsessionid的作用就体现出来了：jsessionid就是用来判断当前用户对应于哪个session。换句话说服务器识别session的方法是通过jsessionid来告诉服务器该客户端的session在内存的什么地方。