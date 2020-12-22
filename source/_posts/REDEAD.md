#### 2020 12 11 16 24 07 变为 2020年12月11日 16:24:07

substring 实现思路:
```javascript
function formatTime (timestr) {
  // console.time()
  const timeStart = +new Date()
  const year = timestr.substring(0, 4)
  const month = timestr.substring(4, 6)
  const date = timestr.substring(6, 8)
  const hour = timestr.substring(8, 10)
  const minute = timestr.substring(10, 12)
  const second = timestr.substring(12, 14)
  // console.log(+new Date - timeStart) // 0.005126953125 ms
  console.log(timeStart, +new Date())
  return `${year}年${month}月${date}日 ${hour}:${minute}:${second}`
}
formatTime('20201211162407')
```
正则 实现思路:
```javascript
function formatTime (timestr) {
  console.time()
  const reg = /(\d{4})(\d{2})(\d{2})(\d{2})(\d{2})(\d{2})/
  const ret = reg.exec(timestr)
  const [, year, month, date, hour, minte, second] = ret
  console.timeEnd() // 0.44091796875ms
  return `${year}年${month}月${date}日 ${hour}:${minute}:${second}`
}
formatTime('20201211162407')
```
结论：substring的执行速度高于正则


#### 浏览器的优化方式
> 这里指的是浏览器加在资源开始，不包含打包和构建相关

1.减少请求次数
  - 尽量合并图片、CSS、JS(将CSS和JS放到外部文件中,可以实现做缓存)
  - 小图片做base64~~~~
  - 使用强缓存或者是协商缓存
  - 使用字体图标 iconfont 代替图片图标
  - 开启 keep-alive

2.减少单次请求所花费的时间
  - 构建结果体积压缩
  - 删除冗余代码，利用类似Tree-Shaking的方式
  - 按需加载
  - 开启Gzip压缩
  - Cookie里面别塞那么多东西，因为每个请求都得带着他跑(可以把一部分数据放到本地，如localstorage)

3.使用CDN
4.把CSS放到顶部，把JS放到底部
5.避免使用CSS表达式
6.使用http2
7.减少重绘重排
8.使用事件委托
9.灵活使用 Web Workers处理纯数据
10.使用位操作
11.降低 CSS 选择器的复杂性(这里其实的优化空间不大，最慢和慢快的选择器性能差别很小)
 - 选择器越短越好，浏览器读取选择器，遵循的原则是从选择器的右边到左边读取 `#block .text p {`
 - 尽量使用高优先级的选择器，例如 ID 和类选择器
 - 避免使用通配符 *

12.如果没有兼容性的要求话，使用 flexbox 而不是较早的布局模型
13.事件的节流与防抖(scroll 事件，resize 事件、鼠标事件（比如 mousemove、mouseover 等）、键盘事件（keyup、keydown 等）都存在被频繁触发的风险)
14.服务端渲染(缺点:会增加服务器的负担)
15.预先解析资源，如在link标签里面设置属性 rel="dns-prefetch"/rel="preload"/rel="prefetch"