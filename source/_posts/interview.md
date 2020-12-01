---
title: 前端面试灵魂之问
date: 2020-11-29 16:59:46
tags:
- JS
- OS
categories:
- JS
---

### 1、介绍下 Set、Map、WeakSet 和 WeakMap 的区别？
> https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/6

Set
成员唯一、无序且不重复
[value, value]，键值与键名是一致的（或者说只有键值，没有键名）
可以遍历，方法有：add、delete、has
WeakSet
成员都是对象
成员都是弱引用，可以被垃圾回收机制回收，可以用来保存DOM节点，不容易造成内存泄漏
不能遍历，方法有add、delete、has
Map
本质上是键值对的集合，类似集合
可以遍历，方法很多可以跟各种数据格式转换
WeakMap
只接受对象作为键名（null除外），不接受其他类型的值作为键名
键名是弱引用，键值可以是任意的，键名所指向的对象可以被垃圾回收，此时键名是无效的
不能遍历，方法有get、set、has、delete

### 2、介绍下深度优先遍历和广度优先遍历，如何实现？
> https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/9

```javascript
// 深度优先遍历 DFS(找到一个节点后，把它的后辈都找出来，最常用递归法。)
let deepTraversal1 = (node, nodeList = []) => {
  if (node !== null) {
    nodeList.push(node)
    let children = node.children
    for (let i = 0; i < children.length; i++) {
      deepTraversal1(children[i], nodeList)
    }
  }
  return nodeList
}
// 广度优先遍历 BFS(找到一个节点后，把他同级的兄弟节点都找出来放在前边，把孩子放到后边，最常用 while)
let widthTraversal2 = (node) => {
  let nodes = []
  let stack = []
  if (node) {
    stack.push(node)
    while (stack.length) {
      let item = stack.shift()
      let children = item.children
      nodes.push(item)
        // 队列，先进先出
        // nodes = [] stack = [parent]
        // nodes = [parent] stack = [child1,child2,child3]
        // nodes = [parent, child1] stack = [child2,child3,child1-1,child1-2]
        // nodes = [parent,child1,child2]
      for (let i = 0; i < children.length; i++) {
        stack.push(children[i])
      }
    }
  }
  return nodes
}
```

### 3、setTimeout、Promise、Async/Await 的区别？
其中settimeout的回调函数放到宏任务队列里，等到执行栈清空以后执行；
promise.then里的回调函数会放到相应宏任务的微任务队列里，等宏任务里面的同步代码执行完再执行；async函数表示函数里面可能会有异步方法，await后面跟一个表达式，async方法执行时，遇到await会立即执行表达式，然后把表达式后面的代码放到微任务队列里，让出执行栈让同步代码先执行。


### 4、实现new？
```javascript
var Dog = function(name) {
  this.name = name
}
Dog.prototype.bark = function() {
  console.log('wangwang')
}
var _new = function() {
  let constructor = Array.prototype.shift.call(arguments)
  let args = arguments
  const obj = new Object()
  obj.__proto__ = constructor.prototype
  constructor.call(obj, ...args)
  return obj
}
var simao = _new(Dog, 'simao')
simao.bark()
console.log(simao instanceof Dog) // true
```


### 5、简单讲解一下 http2 的多路复用？
HTTP2采用二进制格式传输，取代了HTTP1.x的文本格式，二进制格式解析更高效。
多路复用代替了HTTP1.x的序列和阻塞机制，所有的相同域名请求都通过同一个TCP连接并发完成。在HTTP1.x中，并发多个请求需要多个TCP连接，浏览器为了控制资源会有6-8个TCP连接都限制。

在 HTTP/2 中，有两个非常重要的概念，分别是帧（frame）和流（stream）。
帧代表着最小的数据单位，每个帧会标识出该帧属于哪个流，流也就是多个帧组成的数据流。
多路复用，就是在一个 TCP 连接中可以存在多条流。换句话说，也就是可以发送多个请求，对端可以通过帧中的标识知道属于哪个请求。通过这个技术，可以避免 HTTP 旧版本中的队头阻塞问题，极大的提高传输性能。

HTTP2中
1. 同域名下所有通信都在单个连接上完成，消除了因多个 TCP 连接而带来的延时和内存消耗。
2. 单个连接上可以并行交错的请求和响应，之间互不干扰


### 6、有以下 3 个判断数组的方法，请分别介绍它们之间的区别和优劣Object.prototype.toString.call() 、 instanceof 以及 Array.isArray()

> https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/23


### 7、介绍下重绘和回流（Repaint & Reflow），以及如何进行优化
> https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/24


### 8、介绍下观察者模式和订阅-发布模式的区别，各自适用于什么场景
> https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/25

**观察者模式**
```javascript
var subject = {
	observers: [],
	notify() {
		this.observers.forEach(observer =>{
			observer.update()
		})
	},
	attach (observer) {
		this.observers.push(observer)
	}
}
var observer = {
	update(){
		alert('updated')
	}
}
subject.attach(observer)
subject.notify()
```
**订阅发布模式**
```javascript
var publisher = {
	publish(pubsub) {
		pubsub.publish()
	}
}
var pubsub = {
	subscribes: [],
	publish() {
		this.subscribes.forEach(subscribe =>{
			subscribe.update();
		})
	},
	subscribe(sub) {
		this.subscribes.push(sub)
	}
}
var subscribe = {
	update() {
		console.log('update')
	},
        subscribe(pubsub) {
            pubsub.subscribe(this);
        }
}
subscribe.subscribe(pubsub)
publisher.publish(pubsub)
```
两种模式本质都是一样的，主要关键点都在于注册（添加到注册数组中）和触发（触发注册数组中的内容），只是订阅/发布模式对注册和触发进行了解耦。可以看到，使用订阅发布模式中发布者触发publish的时候，可以选择触发哪一些订阅者集合（因为publish参数传递了中间集合，可以定义多个pubsub集合），而观察者模式则只能触发所有的被观察对象。


