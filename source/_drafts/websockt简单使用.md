---
title: websockt简单使用
tags:
---

### 前提
碰到个需求，项目中预警数量这个数值需要后端实时推送到前端展示。

引入websocket插件[websocket-heartbeat-js](!https://github.com/zimv/websocket-heartbeat-js)可以实现该功能。


### 安装引入WebsocketHeartbeatJs插件
```javascript
npm i websocket-heartbeat-js -S
```
```javascript
import WebsocketHeartbeatJs from 'websocket-heartbeat-js'
```

### 使用方法
```javascript
  const url = '' // 后端给的url地址
  _this.ws = new WebsocketHeartbeatJs({
    url: url,
    pingTimeout: 50000,
    pongTimeout: 10000,
    reconnectTimeout: 2000,
    pingMsg: 'heartbeat'
  })
  _this.ws.onopen = function () {
    console.log('open success')
  }
  _this.ws.onmessage = function (evt) {
    // 这里处理业务逻辑
  }
  // 窗口关闭时，断开websocket的链接
  _this.ws.onbeforeunload = function () {
    if (_this.ws) {
      try {
        _this.ws.close()
      } catch (error) {
      }
    }
  }
  _this.ws.onclose = function () {
    console.log('connect onclose')
  }
  _this.ws.onerror = () => {
    console.log('connect onerror')
  }
  _this.ws.onreconnect = (e) => {
    console.log('reconnecting...')
  }
```
