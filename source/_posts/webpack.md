---
title: webpack
date: 2021-04-12 22:29:40
tags: 构建工具
---

> https://webpack.wuhaolin.cn/

## 为什么需要构建工具
* 转换ES6语法
* 转换JSX
* CSS前缀补全/预处理器
* 压缩混淆
* 图片压缩


### loader 的作用
解析js不能识别的文件类型，如 css, image, font, vue, ts, jsx

### plugins 的作用
Plugin 是用来扩展 Webpack 功能的，通过在构建流程里注入钩子实现，它给 Webpack 带来了很大的灵活性。
* 用于bundle文件的优化
* 资源管理
* 环境变量注入


