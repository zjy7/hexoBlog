---
title: 测试post_asset_folder
date: 2019-12-18 10:25:20
tags:
---
## 测试下hexo插入图片
步骤如下：
1. 将_config.yml文件中的配置项“post_asset_folder”设置为true
2. 使用hexo new post [测试post_asset_folder]命令创建新的文章时，在source/_post目录下就会出现一个文件和一个目录：
   - 测试post_asset_folder.md
   - 测试post_asset_folder目录
3. 将要插入的图片放置到[测试post_asset_folder]目录下
4. 在文章中使用以下的方式来插入图片即可：

```
{% asset_img noAccess.png This is an noAccess image %}
```
图片效果：
{% asset_img noAccess.png noAccess image %}

## 遇到的坑
使用以下方式也能插入图片

```
![noAccess](noAccess.png)
```

图片效果：
![noAccess](noAccess.png)

**这种方式插入的图片无法在首页中显示，只能在文章内容中显示。**

根据[官网文档](https://hexo.io/zh-cn/docs/asset-folders.html#%E7%9B%B8%E5%AF%B9%E8%B7%AF%E5%BE%84%E5%BC%95%E7%94%A8%E7%9A%84%E6%A0%87%E7%AD%BE%E6%8F%92%E4%BB%B6)描述，**通过常规的 markdown 语法和相对路径来引用图片和其它资源可能会导致它们在存档页或者主页上显示不正确。**