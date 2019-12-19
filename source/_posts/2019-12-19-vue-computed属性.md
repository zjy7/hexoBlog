---
title: vue computed属性
date: 2019-12-19 14:30:43
tags:
---
用代码来解释一下vue官网文档的话。

### [**计算属性是基于它们的响应式依赖进行缓存的**](https://cn.vuejs.org/v2/guide/computed.html#%E8%AE%A1%E7%AE%97%E5%B1%9E%E6%80%A7-vs-%E4%BE%A6%E5%90%AC%E5%B1%9E%E6%80%A7)

只在相关响应式依赖发生改变时它们才会重新求值。
1. 只要bar的值没有发生变化，多次访问foo这个计算属性会立即返回之前的计算结果，而不必再次执行函数。
2. 当bar的值发生变化，同时又要访问foo的值，会执行函数。

```
export default{
  computed:{
    foo(){
      console.log(yeah)
      return this.bar+1
    }
  },
  data(){
    bar:0
  },
  methods:{
    addBar(){
      this.bar++ // no console yeah
    },
    displayFoo(){
      console.log(this.foo) // yeah
    }
  }
}
```