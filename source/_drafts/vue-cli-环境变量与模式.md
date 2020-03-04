---
title: vue cli 环境变量与模式
tags:
---
在项目中，也就是src中使用环境变量的话，必须以VUE_APP_开头。例如我们可以在main.js中直接输出：console.log(process.env.VUE_APP_SECRET)