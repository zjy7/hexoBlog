---
title: vue同时使用v-html filters
date: 2020-06-09 13:30:27
tags:
categories:
---
在定义的vue里的filter添加方法：


```
var appMain= new Vue({

      el: '#appMain',

      filters:{

        msg: function(msg) {

            return msg.replace(/\n/g, "<br>") ;

        }

      },

      data: {

        content: "XXXXX"

     }

})
```
然后页面上都可以直接用这个方法了:
```
<div id="appMain">

    <div  v-html="$options.filters.msg(content)"></div>

</div>
```