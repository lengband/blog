---
title: 你不知道的JS
date: 2020-11-29 16:59:46
tags:
- JS
categories:
- JS
---

## 多重for循环时，指定break到具体的循环层
```javascript
var arr1 = ['a', 'b', 'c']
var arr2= ['1', '2', '3']
outter: for (let i = 0; i < arr1.length; i++) {
  inner: for (let j = 0; j < arr2.length; j++) {
    if (arr2[j] === '2') {
      break outter;
    }
      console.log({ i: arr1[i], j: arr2[j] }); // { i: 'a', j: '1' }
  }
}
```
break 可以指定中断 outter或者inner，如果不声明label和指定label的话，默认是break outter