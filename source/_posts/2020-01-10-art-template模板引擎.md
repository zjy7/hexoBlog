---
title: art-template模板引擎
date: 2020-01-10 09:10:50
tags:
---

分享一个之前用过的模板引擎[art-template](https://aui.github.io/art-template/zh-cn/docs/)。解决的需求是要动态渲染地图上点位信息展示面板Popup、Tooltip。

### 渲染模板
```javascript
var template = require('art-template');
var html = template(__dirname + '/tpl-user.art', {
    user: {
        name: 'aui'
    }
});
```

### 核心方法
```javascript
// 基于模板名渲染模板
template(filename, data);
// 将模板源代码编译成函数
template.compile(source, options);
// 将模板源代码编译成函数并立刻执行
template.render(source, data, options);
```

### demo
```
template.helper("getAlarmType", function (alarm) {
  if(alarm){
    if(alarm[0]&&alarm[0].type=='offline'){
      return 'offline';
    }else{
      return 'alarmvalue';
    }
  }else{
    return 'normalvalue';
  }
});
```
```
const popupLabel = function (data){
    return  template.compile(
`
  <div class="event-box shadow gx-box">
  <table>
    {{if !haslabel}}
    <tr class="title {{alarm?(offline?'offline':'tralarm'):'trnormal'}} {{if !alarm&&(!sensors||sensors.length==0||hasdata)}}wtitle{{/if}}">
        <td class="name" colspan=3>
            <span>{{sname||name}}<span>
        </td>
    </tr>
    {{/if}}
    {{if !hasdata}}
      {{each sensors as s}}
        <tr class="{{s.alarm?'alarmpopup':'notalarm'}}">
            <td class="name">{{s.name}}</td>
            <td class="value {{getAlarmType(s.alarm)}}">{{s.val==null?'通讯中':s.val}}</td>
            <td class="unit {{getAlarmType(s.alarm)}}">{{s.unit}}</td>
        </tr>
      {{/each}}
    {{/if}}
  </table>
`
    )(data)
}
```

### 参考

[cnblog](https://www.cnblogs.com/jiqiyoudu/p/4588042.html)