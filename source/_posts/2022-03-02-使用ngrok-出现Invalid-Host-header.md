---
title: 使用ngrok 出现Invalid Host header
date: 2022-03-02 11:13:36
tags:
categories:
---

使用ngrok映射外网地址，访问时出现Invalid Host header错误

由于新版的webpack-dev-server出于安全考虑，默认检查hostname，如果hostname不是配置内的，将中断访问

解决方式：可以在项目根目录下的webpack.config.js中添加如下webpack-dev-server配置：

```javascript
    devServer: {
        disableHostCheck: true,
    }
```
