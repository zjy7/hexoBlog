---
title: vue2-3 migration(extend)
date: 2021-01-28 18:27:12
tags:
categories:
---

# vue3已不支持vue.extend api

# vue2 挂载自定义的组件

```javascript
import BusstationDetail from './BusstationDetail.vue'


// 找到节点并且挂载
let eldom = document.querySelector('#defaultwindow')
const BusstationDetailConstructor = Vue.extend(BusstationDetail)
// 生成一个组件实例
const instance = new BusstationDetailConstructor()
// 设置自定义属性
instance.item = item
instance.$mount(eldom)
```

# vue3 挂载自定义的组件

```javascript
import BusstationDetail from './BusstationDetail.vue'


// 找到节点并且挂载
let eldom = document.querySelector('#defaultwindow')
// 子组件 通过props属性 item 接收
const app = createApp(
BusstationDetail, {
    item: item
})
app.mount(eldom)
```
