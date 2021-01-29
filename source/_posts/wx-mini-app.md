---
title: wx-mini-app
date: 2021-01-19 09:16:05
tags:
- 微信小程序
categories:
- 小程序
---

### 微信小程序如何在组件内部使用外部样式？

1. 在对应组件里面的wxss文件import外部的wxss文件，如 
`@import "../../iconfont.wxss";`

2. 在对应组件里面的js文件添加属性 externalClasses 支持外部传递的样式类名
  parent：`<child iconfont="iconfont" icon-edit="icon-edit"></child>`
  child：`externalClasses: ['iconfont', 'icon-edit']`

3. 组件样式隔离 - 指定特殊的样式隔离选项 styleIsolation
    [styleIsolation](https://developers.weixin.qq.com/miniprogram/dev/framework/custom-component/wxml-wxss.html) 选项从基础库版本 2.6.5 开始支持。它支持以下取值：
    * isolated 表示启用样式隔离，在自定义组件内外，使用 class 指定的样式将不会相互影响（一般情况下的默认值）
    * apply-shared 表示页面 wxss 样式将影响到自定义组件，但自定义组件 wxss 中指定的样式不会影响页面；
    * shared 表示页面 wxss 样式将影响到自定义组件，自定义组件 wxss 中指定的样式也会影响页面和其他设置了 apply-shared 或 shared 的自定义组件。（这个选项在插件中不可用。）

