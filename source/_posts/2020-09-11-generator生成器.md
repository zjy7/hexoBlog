---
title: generator生成器
date: 2020-09-11 11:21:13
tags:
categories:
---
```javascript
function* fib(max) {
  var
    t,
    a = 0,
    b = 1,
    n = 1;
  while (n < max) {
    yield a;
    t = a + b;
    a = b;
    b = t;
    n ++;
  }
  return a;
}

fib(5); // fib {[[GeneratorStatus]]: "suspended", [[GeneratorReceiver]]: Window}

var f = fib(5);
f.next(); // {value: 0, done: false}
f.next(); // {value: 1, done: false}
f.next(); // {value: 1, done: false}
f.next(); // {value: 2, done: false}
f.next(); // {value: 3, done: true}
```