---
title: ubuntu ssh 连接
date: 2020-10-10 09:02:15
tags:
categories:
---

ssh
connect refused
sudo apt-get install openssh-server

root登录
/etc/ssh/sshd_config
PermitRootLogin yes
service ssh restart

修改root密码
sudo passwd