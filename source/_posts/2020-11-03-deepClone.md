---
title: deepClone
date: 2020-11-03 14:35:11
tags:
categories:
---

```javascript
// 深拷贝
export const deepCopy = function (obj) {
  let str = '';
  let newobj = (obj && obj.constructor === Array) ? [] : {};
  if (typeof obj !== 'object') {
    return
  } else if (window.JSON) {
    // 系列化对象
    str = JSON.stringify(obj);
    // 还原
    newobj = JSON.parse(str);
  } else {
    for (let prop in obj) {
      if (obj.hasOwnProperty(prop)) {
        newobj[prop] = typeof obj[prop] === 'object' ? deepCopy(obj[prop]) : obj[prop]
      }
    }
  }
  return newobj;
};
```