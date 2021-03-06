---
title: Github Pages绑定域名
date: 2019-12-18 09:47:15
tags:
---

## 前提

以前在[西部数码](https://www.west.cn/)上购买过top的一级域名，且还没到期。

## Before
在我部署GitHub Pages前，这个域名我是设置了A记录指向了自己的vps主机。装了Nginx，反向代理到webpack打包后dist目录。
- 设置如下：
  - 主机名：www|@
  - 类型：A记录
  - 对应值：（vps IP地址）

## Now

现在由于折腾，想把域名指向自己的GitHub Pages。设置起来也很简单，主要分以下两步。
1. 修改域名解析
   - 主机名：www|@
   - 类型：CNAME
   - 对应值：zjy7.github.io
2. 添加Github Pages CNAME记录。
   - 到自己的GitHubPages仓库下。在Settings -> GitHub Pages -> Custom domain内填入自己的域名地址。
   - 保存后，就会在仓库根目录下看的新增的CNAME文件。参考GitHub文档[managing-a-custom-domain-for-your-github-pages-site](https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site)

## 遇到的坑
  通过Travis CI自动部署至GitHub Pages后，CNAME文件就没了。
  解决方案：**将CNAME文件放到source目录下**。
  
  部署后，发现仓库根目录下的确有CNAME文件。点击Settings后发现Custom domain也是正确的。但是访问zjy7.top失败。

  等待约5分钟后，还是不行。

  打开[西部数码](https://www.west.cn/)域名管理页查看。发现CNAME解析的状态已改为暂停。
  解决方案：**手动开启CNAME域名解析**。

  等待1分钟后，可以正常访问zjy7.top。

## Tips
  域名解析指向添加成功和修改成功，需等待各地dns刷新后解析方可生效。实测大概需要5分钟。