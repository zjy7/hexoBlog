---
title: mac unzip Illegal byte sequence
date: 2020-02-21 09:22:17
tags:
---
## 问题
mac解压文件：
1. 直接双击，即命令行的 open，失败了，报错：
```
无法将"xxx.zip"解压到"xx"
(错误22 - 无效的参数)
```

2. 命令行unzip，失败，报错：
```
   unzip Interface.zip
Archive:  Interface.zip
checkdir error:  cannot create i-�++��+
                 Illegal byte sequence
```

## 解决
```
# 后面两个参数，xxx.zip是文件名， xx为解压后的文件夹名称
ditto -V -x -k --sequesterRsrc --rsrc xxx.ZIP xx
```