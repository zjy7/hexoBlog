---
title: crossorigin
date: 2019-12-30 13:08:19
tags:
---

## crossorigin="anonymous"
从微信公众号文章，复制文本图片,至项目里的富文本编辑器内，图片不能显示。

查看DOM,发现图片img标签里有个crossorigin="anonymous",去掉改属性就能显示图片。

{% asset_img cross.jpg cross image %}

{% asset_img no-cross.png no-cross image %}

对比这两个请求头，crossorigin="anonymous"多了两行
Origin: http://XXX(项目地址)
TE: Trailers