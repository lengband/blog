---
title: go
date: 2021-01-28 18:00:08
tags:
- go
---

# Go语言和其他语言的对比

## 一、Go语言设计初衷

1、设计Go语言是为了解决当时Google开发遇到的问题：

- 大量的C++代码，同时又引入了Java和Python
- 成千上万的工程师
- 数以万计行的代码
- 分布式的编译系统
- 数百万的服务器



2、Google开发中的痛点：

- 编译慢
- 失控的依赖
- 每个工程师只是用了一个语言里面的一部分
- 程序难以维护（可读性差、文档不清晰等）
- 更新的花费越来越长
- 交叉编译困难



3、如何解决当前的问题和痛点？

- Go希望成为互联网时代的C语言。多数系统级语言（包括Java和C#）的根本编程哲学来源于C++，将C++的面向对象进一步发扬光大。但是Go语言的设计者却有不同的看法，他们认为值得学习的是C语言。C语言经久不衰的根源是它足够简单。因此，Go语言也是足够简单。

- 所以，他们当时设计Go的目标是为了消除各种缓慢和笨重、改进各种低效和扩展性。Go是由那些开发大型系统的人设计的，同时也是为了这些人服务的；它是为了解决工程上的问题，不是为了研究语言设计；它还是为了让我们的编程变得更舒适和方便。
- 但是结合Google当时内部的一些现实情况，如很多工程师都是C系的，所以新设计的语言一定要易学习，最好是类似C的语言；20年没有出新的语言了，所以新设计的语言必须是现代化的（例如内置GC）等情况。最后根据实战经验，他们向着目标设计了Go这个语言。



4、Go语言的特色：

- 没有继承多态的面向对象
- 强一致类型
- interface不需要显式声明(Duck Typing)
- 没有异常处理(Error is value)
- 基于首字母的可访问特性
- 不用的import或者变量引起编译错误
- 完整而卓越的标准库包
- Go内置runtime（作用是性能监控、垃圾回收等）



## 二、Go语言的优势

1、学习曲线容易

​    Go语言语法简单，包含了类C语法。因为Go语言容易学习，所以一个普通的大学生花几个星期就能写出来可以上手的、高性能的应用。在国内大家都追求快，这也是为什么国内Go流行的原因之一。

​    ![go2](http://7xtcwd.com1.z0.glb.clouddn.com/go2.png)

> Go 语言的语法特性简直是太简单了，简单到你几乎玩不出什么花招，直来直去的，学习曲线很低，上手非常快。

2、效率：快速的编译时间，开发效率和运行效率高

​    开发过程中相较于 Java 和 C++呆滞的编译速度，Go 的快速编译时间是一个主要的效率优势。Go拥有接近C的运行效率和接近PHP的开发效率。

![](http://7xtcwd.com1.z0.glb.clouddn.com/golang2.png)



C 语言的理念是信任程序员，保持语言的小巧，不屏蔽底层且底层友好，关注语言的执行效率和性能。而 Python 的姿态是用尽量少的代码完成尽量多的事。于是我能够感觉到，Go 语言想要把 C 和 Python 统一起来，这是多棒的一件事啊。



![go3](http://7xtcwd.com1.z0.glb.clouddn.com/go3.png)



3、出身名门、血统纯正

​    之所以说Go出身名门，从Go语言的创造者就可见端倪，Go语言绝对血统纯正。其次Go语言出自Google公司，Google在业界的知名度和实力自然不用多说。Google公司聚集了一批牛人，在各种编程语言称雄争霸的局面下推出新的编程语言，自然有它的战略考虑。而且从Go语言的发展态势来看，Google对它这个新的宠儿还是很看重的，Go自然有一个良好的发展前途。

![](http://7xtcwd.com1.z0.glb.clouddn.com/qinerzi_meitu_1.jpg)

4、自由高效：组合的思想、无侵入式的接口

​    Go语言可以说是开发效率和运行效率二者的完美融合，天生的并发编程支持。Go语言支持当前所有的编程范式，包括过程式编程、面向对象编程、面向接口编程、函数式编程。程序员们可以各取所需、自由组合、想怎么玩就怎么玩。

​    

5、强大的标准库

​    这包括互联网应用、系统编程和网络编程。Go里面的标准库基本上已经是非常稳定了，特别是我这里提到的三个，网络层、系统层的库非常实用。**Go 语言的 lib 库麻雀虽小五脏俱全。**Go 语言的 lib 库中基本上有绝大多数常用的库，虽然有些库还不是很好，但我觉得不是问题，因为我相信在未来的发展中会把这些问题解决掉。



6、部署方便：二进制文件，Copy部署

​    这一点是很多人选择Go的最大理由，因为部署太方便了，所以现在也有很多人用Go开发运维程序。



4、简单的并发

**并行和异步编程几乎无痛点。**Go 语言的 Goroutine 和 Channel 这两个神器简直就是并发和异步编程的巨大福音。像 C、C++、Java、Python 和 JavaScript 这些语言的并发和异步方式太控制就比较复杂了，而且容易出错，而 Go 解决这个问题非常地优雅和流畅。这对于编程多年受尽并发和异步折磨的编程者来说，完全就是让人眼前一亮的感觉。Go 是一种非常高效的语言，高度支持并发性。Go是为大数据、微服务、并发而生的一种编程语言。

- Go 作为一门语言致力于使事情简单化。它并未引入很多新概念，而是聚焦于打造一门简单的语言，它使用起来异常快速并且简单。其唯一的创新之处是 goroutines 和通道。Goroutines 是 Go 面向线程的轻量级方法，而通道是 goroutines 之间通信的优先方式。

- 创建 Goroutines 的成本很低，只需几千个字节的额外内存，正由于此，才使得同时运行数百个甚至数千个 goroutines 成为可能。可以借助通道实现 goroutines 之间的通信。Goroutines 以及基于通道的并发性方法使其非常容易使用所有可用的 CPU 内核，并处理并发的 IO。相较于 Python/Java，在一个 goroutine 上运行一个函数需要最小的代码。



![](http://7xtcwd.com1.z0.glb.clouddn.com/golang1.png)



8、稳定性

​    Go拥有强大的编译检查、严格的编码规范和完整的软件生命周期工具，具有很强的稳定性，稳定压倒一切。那么为什么Go相比于其他程序会更稳定呢？这是因为Go提供了软件生命周期（开发、测试、部署、维护等等）的各个环节的工具，如go tool、gofmt、go test。





## 三、对比其他语言

Go的很多语言特性借鉴与它的三个祖先：C，Pascal和CSP。Go的语法、数据类型、控制流等继承于C，Go的包、面对对象等思想来源于Pascal分支，而Go最大的语言特色，基于管道通信的协程并发模型，则借鉴于CSP分支。

![go1](http://7xtcwd.com1.z0.glb.clouddn.com/go1.jpeg)





### Java

编译语言，速度适中（2.67s），目前的大型网站都是拿java写的，比如淘宝、京东等。主要特点是稳定，开源性好，具有自己的一套编写规范，开发效率适中，目前最主流的语言。

> 作为编程语言中的大腕。具有最大的知名度和用户群。无论风起云涌，我自巍然不动。他强任他强，清风拂山岗；他横由他横，明月照大江。



### c#

执行速度快（4.28），学习难度适中，开发速度适中。但是由于c#存在很多缺点，京东、携程等大型网站前身都是用c#开发的，但是现在都迁移到了java上。



### C/C++

现存编程语言中的老祖，其他语言皆由此而生。执行速度最快无人能及。但是写起来最为复杂，开发难度大。



### Javascript

编程语言中特立独行的傲娇美女。前端处理能力是其它语言无法比拟。发展中的js后端处理能力也是卓越不凡。前后端通吃，舍我其谁？



### Python

脚本语言，速度最慢（258s），代码简洁、学习进度短，开发速度快。豆瓣就是拿python写的。Python著名的服务器框架有django，flask。但是python在大型项目上不太稳定，因此有些用python的企业后来迁移到了java上。



### scala

编译语言，比python快十倍，和java差不多，但是学习进度慢，而且在实际编程中，如果对语言不够精通，很容易造成性能严重下降。，后来比如Yammer就从scala迁移到了java上。微服务框架有lagom等。



### Go

编程界的小鲜肉。高并发能力无人能及。即具有像Python一样的简洁代码、开发速度，又具有C语言一样的执行效率，优势突出。



## 四、最后

因为Go的语法和Erlang、Python类似，所以我们将这三门语言做个详细的对比。

相比于Python的40个特性，Go只有31个，可以说Go在语言设计上是相当克制的。比如，它没有隐式的数值转换，没有构造函数和析构函数，没有运算符重载，没有默认参数，也没有继承，没有泛型，没有异常，没有宏，没有函数修饰，更没有线程局部存储。

但是Go的特点也很鲜明，比如，它拥有协程、自动垃圾回收、包管理系统、一等公民的函数、栈空间管理等。

Go作为静态类型语言，保证了Go在运行效率、内存用量、类型安全都要强于Python和Erlang。

Go的数据类型也更加丰富，除了支持表、字典等复杂的数据结构，还支持指针和接口类型，这是Python和Erlang所没有的。特别是接口类型特别强大，它提供了管理类型系统的手段。而指针类型提供了管理内存的手段，这让Go进入底层软件开发提供了强有力的支持。

Go在面对对象的特性支持上做了很多反思和取舍，它没有类、虚函数、继承、泛型等特性。Go语言中面向对象编程的核心是组合和方法(function)。组合很类似于C语言的struct结构体的组合方式，方法类似于Java的接口(Interface)，但是使用方法上与对象更加解耦，减少了对对象内部的侵入。Erlang则不支持面对对象编程范式，相比而言，Python对面对对象范式的支持最为全面。

在函数式编程的特性支持上，Erlang作为函数式语言，支持最为全面。但是基本的函数式语言特性，如lambda、高阶函数、curry等，三种语言都支持。

控制流的特性支持上，三种语言都差不多。Erlang支持尾递归优化，这给它在函数式编程上带来便利。而Go在通过动态扩展协程栈的方式来支持深度递归调用。Python则在深度递归调用上经常被爆栈。

Go和Erlang的并发模型都来源于CSP，但是Erlang是基于actor和消息传递（mailbox）的并发实现，Go是基于goroutine和管道（channel）的并发实现。不管Erlang的actor还是Go的goroutine，都满足协程的特点：由编程语言实现和调度，切换在用户态完成，创建销毁开销很小。至于Python，其多线程的切换和调度是基于操作系统实现，而且因为GIL的大坑级存在，无法真正做到并行。

而且从笔者的并发编程体验上看，Erlang的函数式编程语法风格和其OTP behavior框架提供的晦涩的回调（callback）使用方法，对大部分的程序员，如C/C++和Java出身的程序员来说，有一定的入门门槛和挑战。而被称为“互联网时代的C”的Go，其类C的语法和控制流，以及面对对象的编程范式，编程体验则好很多。



# Go语言能做什么

## 一、我们为什么选择Go语言

选择Go语言的原因可能会有很多，关于Go语言的特性、优势等，我们在之前的文档中也已经介绍了很多了。但是最主要的原因，应该是基于以下两方面的考虑：

1. 执行性能

   缩短API的响应时长，解决批量请求访问超时的问题。在Uwork的业务场景下，一次API批量请求，往往会涉及对另外接口服务的多次调用，而在之前的PHP实现模式下，要做到并行调用是非常困难的，串行处理却不能从根本上提高处理性能。而GO语言不一样，通过协程可以方便的实现API的并行处理，达到处理效率的最大化。 依赖Golang的高性能HTTP Server，提升系统吞吐能力，由PHP的数百级别提升到数千里甚至过万级别。

2. 开发效率

   GO语言使用起来简单、代码描述效率高、编码规范统一、上手快。 通过少量的代码，即可实现框架的标准化，并以统一的规范快速构建API业务逻辑。 能快速的构建各种通用组件和公共类库，进一步提升开发效率，实现特定场景下的功能量产。

## 二、Go语言能做什么

Go 语言从发布 1.0 版本以来备受众多开发者关注并得到广泛使用，Go 语言的简单、高效、并发特性吸引了众多传统语言开发者的加入，而且人数越来越多。

鉴于Go语言的特点和设计的初衷，Go语言作为服务器编程语言，很适合处理日志、数据打包、虚拟机处理、文件系统、分布式系统、数据库代理等；网络编程方面，Go语言广泛应用于Web 应用、API应用、下载应用等；除此之外，Go语言还适用于内存数据库和云平台领域，目前国外很多云平台都是采用Go开发。

- 服务器编程，以前你如果使用C或者C++做的那些事情，用Go来做很合适，例如处理日志、数据打包、虚拟机处理、文件系统等。
- 分布式系统、数据库代理器、中间件等，例如Etcd。
- 网络编程，这一块目前应用最广，包括Web应用、API应用、下载应用，而且Go内置的net/http包基本上把我们平常用到的网络功能都实现了。
- 数据库操作
- 开发云平台，目前国外很多云平台在采用Go开发





## 三、国内外有哪些企业或项目使用Go语言

Go发布之后，很多公司特别是云计算公司开始用Go重构他们的基础架构，很多都是直接采用Go进行了开发，最近热火朝天的Docker就是采用Go开发的。

使用 Go 语言开发的开源项目非常多。早期的 Go 语言开源项目只是通过 Go 语言与传统项目进行C语言库绑定实现，例如 Qt、Sqlite 等；后期的很多项目都使用 Go 语言进行重新原生实现，这个过程相对于其他语言要简单一些，这也促成了大量使用 Go 语言原生开发项目的出现。



- 云计算基础设施领域

  代表项目：docker、kubernetes、etcd、[consul](http://tonybai.com/2015/07/06/implement-distributed-services-registery-and-discovery-by-consul/)、cloudflare CDN、七牛云存储等。

- 基础软件

  代表项目：[tidb](https://github.com/pingcap/tidb)、[influxdb](https://github.com/influxdata/influxdb)、[cockroachdb](https://github.com/cockroachdb/cockroach)等。

- 微服务

  代表项目：[go-kit](https://github.com/go-kit/kit)、[micro](https://github.com/micro/micro)、monzo bank的[typhon](https://github.com/monzo)、[bilibili](https://www.bilibili.com/)等。

- 互联网基础设施

  代表项目：[以太坊](https://github.com/ethereum/go-ethereum)、[hyperledger](https://github.com/hyperledger)等。

  

>采用Go的一些国外公司，如Google、Docker、Apple、Cloud Foundry、CloudFlare、Couchbase、CoreOS、Dropbox、MongoDB、AWS等公司；
>
>采用Go开发的国内企业：如阿里云CDN、百度、小米、七牛、PingCAP、华为、金山软件、猎豹移动、饿了么等公司。
>
>



### Docker

Docker 是一种操作系统层面的虚拟化技术，可以在操作系统和应用程序之间进行隔离，也可以称之为容器。Docker 可以在一台物理服务器上快速运行一个或多个实例。基于lxc的一个虚拟打包工具，能够实现PAAS平台的组建。例如，启动一个 CentOS 操作系统，并在其内部命令行执行指令后结束，整个过程就像自己在操作系统一样高效。

项目链接：

https://github.com/docker/docker





### go语言

Go 语言自己的早期源码使用C语言和汇编语言写成。从 Go 1.5 版本后，完全使用 Go 语言自身进行编写。Go 语言的源码对了解 Go 语言的底层调度有极大的参考意义，建议希望对 Go 语言有深入了解的读者读一读。

项目链接：

https://github.com/golang/go



### Kubernetes

Google 公司开发的构建于 Docker 之上的容器调度服务，用户可以通过 Kubernetes 集群进行云端容器集群管理。

项目链接：

https://github.com/kubernetes/kubernetes



### etcd

一款分布式、可靠的 KV 存储系统，可以快速进行云配置。

项目链接：

https://github.com/coreos/etcd



### beego

beego 是一个类似 Python的 Tornado 框架，采用了 RESTFul 的设计思路，使用 Go 语言编写的一个极轻量级、高可伸缩性和高性能的 Web 应用框架。

项目链接：

https://github.com/astaxie/beego



### martini

一款快速构建模块化的 Web 应用的 Web 框架。

项目链接：

https://github.com/go-martini/martini



### codis

国产的优秀分布式 Redis 解决方案。

项目链接：

https://github.com/CodisLabs/codis



### delve

Go语言

强大的调试器，被很多集成环境和编辑器整合。

项目链接：

https://github.com/derekparker/delve



### Facebook

Facebook也在用，为此他们还专门在Github上建立了一个开源组织facebookgo，大家可以通过https://github.com/facebookgo访问查看facebook开源的项目，比如著名的是平滑升级的grace。



### Uber





### 腾讯

腾讯作为国内的大公司，还是敢于尝试的，尤其是Docker容器化这一块，他们在15年已经做了docker万台规模的实践，具体可以参考http://www.infoq.com/cn/articles/tencent-millions-scale-docker-application-practice 。





### 百度

目前所知的百度的使用是在运维这边，是百度运维的一个BFE项目，负责前端流量的接入。他们的负责人在2016年有分享，大家可以看下这个 http://www.infoq.com/cn/presentations/application-of-golang-in-baidu-frontend 。

其次就是百度的消息系统。负责公司手百消息通讯系统服务器端开发及维护。

### 京东

京东云消息推送系统、云存储，以及京东商城等都有使用Go做开发。



### 小米

小米对Golang的支持，莫过于运维监控系统的开源，也就是 http://open-falcon.com/ 。

此外，小米互娱、小米商城、小米视频、小米生态链等团队都在使用Golang。



### 360

360对Golang的使用也不少，一个是开源的日志搜索系统Poseidon，托管在Github上，https://github.com/Qihoo360/poseidon.

还有360的推送团队也在使用，他们还写了篇博文在Golang的官方博客上 https://blog.golang.org/qihoo。





### 七牛云

七牛云用了近50万行代码，来实现整个产品。七牛云存储产品网址：http://qiniu.com/。上线时间：2011-9-1。应用范围：整个产品（包括基础服务、Web端、统计平台、各类小工具等等）Go代码行数占比：99.9%日 PV：保密



### 美团

美团后台流量支撑程序。应用范围：支撑主站后台流量（排序，推荐，搜索等），提供负载均衡，cache，容错，按条件分流，统计运行指标（qps，latency）等功能。



### 滴滴

基础服务平台。



###金山微看 

应用范围：服务接口，后台流程服务，消息系统，图片系统



### 搜狗

搜狗推送系统。Push系统中用于维持与客户端连接的部分。



### QOR - 模块化的电商系统 

- QOR官网: [QOR: E-commerce & CMS SDK written in Go](https://link.zhihu.com/?target=http%3A//getqor.com)
- github地址: qor/qor · GitHub
- 应用范围: 整个产品

### weico

产品名：weico 3.0， 服务端所有代码都是用Go实现。



### 仙侠道

- 产品网址：[仙侠道官网 - 心动游戏](仙侠道官网 - 心动游戏)
- 应用范围： 游戏服务端（通讯、逻辑、数据存储）



### 快玩游戏

- 网址：[快玩小游戏,单机游戏,网页游戏,快玩游戏,快玩游戏盒](快玩小游戏,单机游戏,网页游戏,快玩游戏,快玩游戏盒) 
- 应用范围：实时消息系统、用户认证、用户会话、统一统计接口



### 盛大云CDN

- 网址：盛大云计算
- 应用范围：CDN的调度系统、分发系统、监控系统、短域名服务，CDN内部开放平台、运营报表系统以及其他一些小工具等





### Bmob移动后端云服务平台

- 产品网址：Bmob移动后端云服务平台
- 应用范围：Restful API(使用Beego)、统计分析平台、常用服务如发邮件、队列异步处理、统计用户空间和接口请求



### 群策

- 网址：[群策 - 统一团队沟通，高效完成工作](群策 - 统一团队沟通，高效完成工作)
- 应用范围：全系统



### BiddingX DSP广告投放系统

- 网址：BiddingX_专业的DSP解决方案供应商
- 应用范围：竞价投放、曝光统计、点击跳转



### 街坊四邻

- 网址：首页 - 街坊四邻
- 应用范围：后台服务



### Leanote

- 网址：Leanote

### Bearychat

- 网址：BearyChat

### 宅豆

- 网址：宅豆网 - 自筑最美家，宅豆随你搭

### 白板- 设计图讨论工具

- 网址：白板

### 实验楼

- 网址：实验楼 - 第一家以实验为核心的IT在线教育平台



### 新浪微博

中间件和弹性调度用 Java 和 Go 编写，微博视频转码及存储服务用 Go 编写。



### 爱奇艺

VR 后台系统中间件，VR 端的 HTTP 接口。



### 猎豹移动

消息推送



### 网易

网易蜂巢容器公有云。



### 哔哩哔哩

弹幕



### 巨人网络

部分手机游戏的服务端。



### 今日头条





Nsq：Nsq 是由Go语言开发的高性能、高可用消息队列系统，性能非常高，每天能处理数十亿条的消息；

Packer:用来生成不同平台的镜像文件，例如VM、vbox、AWS等，作者是vagrant的作者

Skynet：分布式调度框架

Doozer：分布式同步工具，类似ZooKeeper

Heka：mazila开源的日志处理系统

Cbfs：couchbase开源的分布式文件系统

Tsuru：开源的PAAS平台，和SAE实现的功能一模一样

Groupcache：memcahe作者写的用于Google下载系统的缓存系统

God：类似redis的缓存系统，但是支持分布式和扩展性

Gor：网络流量抓包和重放工具



还有很多，比如阿里中间件、聚美优品、高升控股、探探、斗鱼直播、人人车、亚信、Udesk、方付通、招财猫、三一集团、美餐网等。一般的选择，都是选择用于自己公司合适的产品系统来做，比如消息推送的、监控的、容器的等，Golang特别适合做网络并发的服务，这是他的强项，所以也是被优先用于这些项目。Go语言作为一门大型项目开发语言，在很多大公司相继使用，甚至完全转向Go开发。



## 四、写在最后

当然，一个技术能不能发展起来，关键还要看三点。

- **有没有一个比较好的社区。**像 C、C++、Java、Python 和 JavaScript 的生态圈都是非常丰富和火爆的。尤其是有很多商业机构参与的社区那就更为人气爆棚了，比如 Linux 的社区。
- **有没有一个工业化的标准。**像 C、C++、Java 都是有标准化组织的。尤其是 Java，其在架构上还搞出了像 J2EE 这样的企业级标准。
- **有没有一个或多个杀手级应用。**C、C++ 和 Java 的杀手级应用不用多说了，就算是对于 PHP 这样还不能算是一个好的编程语言来说，因为是 Linux 时代的第一个杀手级解决方案 LAMP 中的关键技术，所以，也发展起来了。

上述的这三点是非常关键的，新的技术只需要占到其中一到两点就已经很不错了，何况有的技术，比如 Java，是三点全占到了，所以，Java 的发展是如此好。当然，除了上面这三点重要的，还有一些其它的影响因素，比如：

- **学习曲线是否低，上手是否快。**这点非常重要，C++ 在这点上越做越不好了。
- **有没有一个不错的提高开发效率的开发框架。**如：Java 的 Spring 框架，C++ 的 STL 等。
- **是否有一个或多个巨型的技术公司作为后盾。**如：Java 和 Linux 后面的 IBM、Sun……
- **有没有解决软件开发中的痛点。**如：Java 解决了 C 和 C++ 的内存管理问题。

用这些标尺来量一下 Go 语言，我们可以清楚地看到：

- Go 语言容易上手；
- Go 语言解决了并发编程和写底层应用开发效率的痛点；
- Go 语言有 Google 这个世界一流的技术公司在后面；
- Go 语言的杀手级应用是 Docker，而 Docker 的生态圈在这几年完全爆棚了。

所以，Go 语言的未来是不可限量的。当然，我个人觉得，Go 可能会吞食很多 C、C++、Java 的项目。不过，Go 语言所吞食主要的项目应该是中间层的项目，既不是非常底层也不会是业务层。

> 也就是说，Go 语言不会吞食底层到 C 和 C++ 那个级别的，也不会吞食到高层如 Java 业务层的项目。Go 语言能吞食的一定是 PaaS 上的项目，比如一些消息缓存中间件、服务发现、服务代理、控制系统、Agent、日志收集等等，没有复杂的业务场景，也到不了特别底层（如操作系统）的中间平台层的软件项目或工具。而 C 和 C++ 会被打到更底层，Java 会被打到更上层的业务层。

好了，我们再用上面的标尺来量一下 Go 语言的杀手级应用 Docker，你会发现基本是一样的。

- Docker 上手很容易。
- Docker 解决了运维中的环境问题以及服务调度的痛点。
- Docker 的生态圈中有大公司在后面助力。比如 Google。
- Docker 产出了工业界标准 OCI。
- Docker 的社区和生态圈已经出现像 Java 和 Linux 那样的态势。
- ……

所以，虽然几年前的 Docker ，当时的坑儿还很多，但是，相对于这些大的因素来说，那些小坑儿都不是问题。只是需要一些时间，这些小坑儿在未来 5-10 年就可以完全被填平了。

同样，我们可以看到 Kubernetes 作为服务和容器调度的关键技术一定会是最后的赢家。

最后，我还要说一下，为什么要早一点地进入这些新技术，而不是等待这些技术成熟了后再进入。原因有这么几个。

技术的发展过程非常重要。因为你可以清楚地看到了这种新技术的生态圈发展过程。让我们收获最大的并不是这些技术本身，而是一个技术的变迁和行业的发展。

从中，我们看到了非常具体的各种思潮和思路，这些东西比起 技术本身来说更有价值。因为，这不但让我们重新思考已经掌握的技术以及如何更好地解决已有的问题，而且还让我看到了未来。不但有了技术优势，而且这些知识还让我们的技术生涯多了很多的可能性。

这些关键新技术，可以让你拿到技术的先机。这些对一个需要技术领导力的个人或公司来说都是非常重要的。

一个公司或是个人能够占有技术先机，就会比其它公司或个人有更大的影响力。一旦未来行业需求引爆，那么这个公司或是个人的影响力就会形成一个比较大的护城河，并可以快速地产生经济利益。



Go的应用范围一直在扩大，云计算，微服务，区块链，哪里都有用Go写的重量级项目。docker/kubernetes生态圈，几百/千万行代码，基本统治了云原生应用市场。去年大热的区块链，以太坊的geth，比特币的btcd，闪电网络的lnd，都是Go语言开发。还是那句话，多看看各种语言的生态，或许都并没有你想象的那么不堪。。。Go语言设计上确实不够“先进”，但也是另一种“务实”。其实go不管在国内还是国外已经很受待见了，国外google用的很多，uber也在用，国内有著名的今日头条，每日千亿级的访问妥妥的。多少语言终其一生都没有这么大的应用场景。



# Go语言的前世今生

## 一、Golang语言的官网

首先我们登录Golang的官方网站：https://golang.org/

![guanwang2](http://7xtcwd.com1.z0.glb.clouddn.com/guanwang2.png)



> 因为Google和中国的关系，直接登录Golang的官网，需要翻墙。



当然你也可以登录Golang的国内网站：<https://golang.google.cn/>

![WX20190403-095602](http://7xtcwd.com1.z0.glb.clouddn.com/guanwang1.png)

## 二、下载



在Mac、Windows和Linux三个平台上都支持Golang。您可以从<https://golang.org/dl/>下载相应平台的安装包。

![xiazai1](http://7xtcwd.com1.z0.glb.clouddn.com/xiazai1.png)



该网站在国内不容易访问，所以可以访问中国对应的<https://golang.google.cn/dl/>或者是Go语言中文网

<https://www.studygolang.com/dl> 进行安装软件的下载。

![xiazai2](http://7xtcwd.com1.z0.glb.clouddn.com/xiazai2.png)



和

![xiazai3](http://7xtcwd.com1.z0.glb.clouddn.com/xiazai3.png)



目前最新的版本，是今年2月份发布的Go1.12。



Mac OS
从https://golang.org/dl/下载osx安装程序。双击启动安装。按照提示，这应该在/usr/local/go中安装了Golang，并且还会将文件夹/usr/local/go/bin添加到您的PATH环境变量中。

Windows
从https://golang.org/dl/下载MSI安装程序。双击启动安装并遵循提示。这将在位置c中安装Golang:\Go，并且还将添加目录c:\Go\bin到您的path环境变量。

Linux
从https://golang.org/dl/下载tar文件，并将其解压到/usr/local。将/usr/local/go/bin添加到PATH环境变量中。这应该安装在linux中。



```
开发工具包又分为安装版和压缩版。安装版是Mac和Windows特有的，他们的名字类似于：

- go1.12.1.darwin-amd64.pkg
- go1.12.1.windows-386.msi
- go1.12.1.windows-amd64.msi

安装版，顾名思义，双击打开会出现安装向导，让你选择安装的路径，帮你设置好环境比安康等信息，比较省事方便一些。

压缩版的就是一个压缩文件，可以解压得到里面的内容，他们的名字类似于：

- go1.12.1.darwin-amd64.tar.gz
- go1.12.1.linux-386.tar.gz
- go1.12.1.linux-amd64.tar.gz
- go1.12.1.windows-386.zip
- go1.12.1.windows-amd64.zip

压缩版我们下载后需要解压，然后自己移动到要存放的路径下，并且配置环境变量等信息，相比安装版来说，比较复杂一些，手动配置的比较多。

```





## 三、安装和配置环境变量

### 3.1 Linux系统安装和配置

Linux系统，我们以Ubuntu为例。

**第一步：下载安装**

到go的官网上下载go的安装包，自动下载到了下载目录。

打开终端，进入到下载目录，查看安装包：

```shell
ruby@hanru:~$ cd 下载
ruby@hanru:~/下载$ ls
```

![ubuntu1](http://7xtcwd.com1.z0.glb.clouddn.com/ubuntu1.png)



然后我们需要将压缩包解压，并拷贝到指定的目录下，所以在终端继续执行以下命令：

```shell
ruby@ubuntu:~/下载$ sudo tar -xzf go1.12.1.linux-amd64.tar.gz -C /usr/local
```

![ubuntu2](http://7xtcwd.com1.z0.glb.clouddn.com/ubuntu2.png)



> 输入sudo，表示使用管理员身份执行命令，需要输入密码

此时，就将从go官网https://golang.org/dl/上下载tar文件，解压到/usr/local目录下，该目录下会有一个go文件夹。

可以进入这个文件夹直接查看：

![ubuntu3](http://7xtcwd.com1.z0.glb.clouddn.com/ubuntu3.png)



也可以通过终端命令进行查看，输入以下命令：

```shell
ruby@hanru:~/下载$ cd /usr/local
ruby@hanru:/usr/local$ ls
```

![ubuntu4](http://7xtcwd.com1.z0.glb.clouddn.com/ubuntu4.png)



**第二步：配置环境变量**	

一：需要先安装vim。

直接在终端执行以下命令：

```shell
ruby@ubuntu:~$ sudo apt-get install vim
```

二：编辑$HOME/.profile文件

**A：先配置GOROOT，就是go的安装目录**

```shell
export GOROOT="/usr/local/go"
```



**B：然后配置GOPATH**

Gopath就是Go项目代码存放的位置。这个是我们自己定义的目录。就好比是其他IDE的Workspace。

​	对于Ubuntu系统，默认使用Home/go目录作为gopath。

​		该目录下有3个子目录：src，pkg，bin

> GO代码必须在工作空间内。工作空间是一个目录，其中包含三个子目录：
>
> ​	src ---- 里面每一个子目录，就是一个包。包内是Go的源码文件
>
> ​	pkg ---- 编译后生成的，包的目标文件
>
> ​	bin ---- 生成的可执行文件。



```shell
export GOPATH=$HOME/go
```



**C：GOBIN**

```shell
export GOBIN=$GOROOT/bin
```



**D：添加到PATH中**

我们需要将GOBIN添加到环境变量PATH中。可以通过vi直接将下面内容添加到$HOME/.profile中

```shell
export PATH=$PATH:$GOBIN
```





> 当然，你也可以将GO的bin目录直接配置到PATH中：
>
> ```shell
> export PATH=$GOROOT/bin:$PATH
> ```
> 
>相当于将上面的C和D步骤，写在一起





具体操作：


 1. 首先使用ls -a命令，查看home目录下是否有.profile文件。(以.开头的文件都是隐藏文件，使用-a命令查看)
2. 直接在终端中输入：vi $HOME/.profile
3. 输入i，切片到编辑模式，将以上内容复制到文件中，并保存退出。
>
> ​	点击esc键后，
>
> ​	:q!，强制退出不保存
>
> ​	:wq，保存并退出	



三：让配置文件立刻生效

使用source命令让配置文件生效

```shell
ruby@ubuntu:~$ source $HOME/.profile
```

四：测试安装

版本检测

```shell
ruby@ubuntu:~$ go version
```

检查go的配置信息

```shell
ruby@ubuntu:~$ go env
```



额外扩展：

```
vi命令后文件的保存

Linux中vi的英文全称为Visual Interface。

末行模式下执行以下操作。[命令模式下按下:就切换到末行模式下]
w
保存文件不退出vi

w file
文件另存到file中，不退出vi

w!
强制保存，不退出vi

wq
保持文件并退出

wq!
强制保存文件并退出

q
不保存文件退出vi

q!
不保存文件强制退出vi

e!
放弃所有修改，从上次保持的文件处在编辑
```



### 3.2 mac系统安装并配置

Mac分为压缩版和安装版，他们都是64位的。压缩版和Linux的大同小异，因为Mac和Linux都是基于Unix，终端这一块基本上是相同的。

**A：安装**

找到下载后的pkg安装包：一般情况下，下载后的文件都在下载目录下。

![anzhuang1](http://7xtcwd.com1.z0.glb.clouddn.com/anzhuang1.png)



双击pkg包，顺着指引，即可安装成功。 



在命令行输入 go version，获取到go的版本号，则代表安装成功。

**配置环境变量**

1、打开终端输入cd ~进入用户主目录; 
2、输入ls -all命令查看是否存在.bash_profile; 
3、存在既使用vim .bash_profile 打开文件; 
4、输入 i 进入vim编辑模式； 
5、输入下面代码： 

```shell
export GOROOT=/usr/local/go
export GOPATH=/Users/ruby/go
export GOBIN=$GOROOT/bin
export PATH=$PATH:$GOBIN
```

其中 GOPATH: 日常开发的根目录。GOBIN:是GOPATH下的bin目录。

6、点击ESC，并输入 :wq 保存并退出编辑。可输入vim .bash_profile 查看是否保存成功。

7、输入source ~/.bash_profile 完成对golang环境变量的配置，配置成功没有提示。 
8、输入go env 查看配置结果。



### 3.3 Windows

**A、安装**

安装步骤就不在多说什么了，一路下一步到底

**B、配置环境变量**

注意：如果是msi安装文件，Go语言的环境变量会自动设置好。

我的电脑——右键“属性”——“高级系统设置”——“环境变量”——“系统变量”

​	假设GO安装于C盘根目录

**新建：**

- GOROOT：Go安装路径（例：C:\Go）

- GOPATH：Go工程的路径（例：E:\go）。如果有多个，就以分号分隔添加

  ![winhuanjing1](http://7xtcwd.com1.z0.glb.clouddn.com/winhuanjing1.jpg)

**修改：**

- Path：在path中增加：C:\Go\bin;%GOPATH%\bin;

  > 需要把GOPATH中的可执行目录也配置到环境变量中, 否则你自行下载的第三方go工具就无法使用了

  

  ![winhuanjing2](http://7xtcwd.com1.z0.glb.clouddn.com/winhuanjing2.jpg)

  

> 1. 工作目录就是我们用来存放开发的源代码的地方，对应的也是Go里的GOPATH这个环境变量。这个环境变量指定之后，我们编译源代码等生成的文件都会放到这个目录下，GOPATH环境变量的配置参考上面的安装Go，配置到Windows下的系统变量里。
> 2. GOPATH之下主要包含三个目录: bin、pkg、src。bin目录主要存放可执行文件; pkg目录存放编译好的库文件, 主要是*.a文件; src目录下主要存放go的源文件





**C、查看是否安装配置成功**

使用快捷键win+R键，输入cmd，打开命令行提示符，在命令行中输入

```go
go env  # 查看得到go的配置信息
go version  # 查看go的版本号
```


# 第一个程序：HelloWorld

##  一、go项目工程结构

配置好工作目录后，就可以编码开发了，在这之前，我们看下go的通用项目结构，这里的结构主要是源代码相应地资源文件存放目录结构。

### 1.1 gopath目录

gopath目录就是我们存储我们所编写源代码的目录。该目录下往往要有3个子目录：src，bin，pkg。

> src ---- 里面每一个子目录，就是一个包。包内是Go的源码文件
>
> pkg ---- 编译后生成的，包的目标文件
>
> bin ---- 生成的可执行文件。



### 1.2 编写第一个程序

1.在HOME/go的目录下，(就是GOPATH目录里)，创建一个目录叫src，然后再该目录下创建一个文件夹叫hello，在该目录下创建一个文件叫helloworld.go，并双击打开，输入以下内容：

```go
package main

import "fmt"

func main() {
   fmt.Println("Hello, World!")
}
```

2.执行go程序

执行go程序由几种方式

方式一：使用go run命令

​	step1：打开终端：

​			window下使用快捷键win+R，输入cmd打开命令行提示符

​			linux下可以使用快捷键：ctrl+alt+T

​			mac下command+空格，输入termainl

​	step2：进入helloworld.go所在的目录

​	step3：输入go run helloworld.go命令并观察运行结果。

方式二：使用go build命令

​	step1：打开终端：在任意文件路径下，运行:
​			go install hello 

​		也可以进入项目(应用包)的路径，然后运行：
​			go install 

注意，在编译生成go程序的时，go实际上会去两个地方找程序包：
GOROOT下的src文件夹下，以及GOPATH下的src文件夹下。

在程序包里，自动找main包的main函数作为程序入口，然后进行编译。

​	step2：运行go程序
​		在/home/go/bin/下(如果之前没有bin目录则会自动创建)，会发现出现了一个hello的可执行文件，用如下命令运行:
​		./hello

​	

### 1.3 第一个程序的解释说明

#### 3.2.1 package

- 在同一个包下面的文件属于同一个工程文件，不用`import`包，可以直接使用
- 在同一个包下面的所有文件的package名，都是一样的
- 在同一个包下面的文件`package`名都建议设为是该目录名，但也可以不是

#### 3.2.2  import

import "fmt" 告诉 Go 编译器这个程序需要使用 fmt 包的函数，fmt 包实现了格式化 IO（输入/输出）的函数

可以是相对路径也可以是绝对路径，推荐使用绝对路径（起始于工程根目录）

1. 点操作
   我们有时候会看到如下的方式导入包

   ```go
   import(
   	. "fmt"
   ) 
   ```

   这个点操作的含义就是这个包导入之后在你调用这个包的函数时，你可以省略前缀的包名，也就是前面你调

   用的`fmt.Println("hello world")`可以省略的写成`Println("hello world")`

2. 别名操作
   别名操作顾名思义我们可以把包命名成另一个我们用起来容易记忆的名字

   ```go
   import(
   	f "fmt"
   ) 
   ```

   别名操作的话调用包函数时前缀变成了我们的前缀，即`f.Println("hello world")`

3. _操作
   这个操作经常是让很多人费解的一个操作符，请看下面这个import

   ```go
   import (
     "database/sql"
     _ "github.com/ziutek/mymysql/godrv"
   ) 
   ```

   _操作其实是引入该包，而不直接使用包里面的函数，而是调用了该包里面的init函数

#### 3.3.3 main

main(),是程序运行的入口。





### 1.4 包的说明

我们知道源代码都是存放在GOPATH的src目录下，那么多个多个项目的时候，怎么区分呢？答案是通过包，使用包来组织我们的项目目录结构。有过java开发的都知道，使用包进行组织代码，包以网站域名开头就不会有重复，比如千锋的网站是`http://www.mobiletrain.org`，我们就可以以`mobiletrain.org`的名字创建一个文件夹，我自己的go项目都放在这个文件夹里，这样就不会和其他人的项目冲突，包名也是唯一的。

如果有自己的域名，那也可以使用自己的域名。如果没有个人域名，现在流行的做法是使用你个人的github名，因为每个人的是唯一的，所以也不会有重复。

![package1](img8/package1.png)



如上，src目录下跟着一个个域名命名的文件夹。再以github.com文件夹为例，它里面又是以github用户名命名的文件夹，用于存储属于这个github用户编写的go源代码。




# Go的执行原理以及Go的命令

## 一、Go的源码文件

 Go 的源码文件分类：

![yuanmawenjian1](http://7xtcwd.com1.z0.glb.clouddn.com/yuanmawenjian1.png)

如上图，分为三类：

**1、命令源码文件：**

声明自己属于 main 代码包、包含无参数声明和结果声明的 main 函数。

命令源码文件被安装以后，GOPATH 如果只有一个工作区，那么相应的可执行文件会被存放当前工作区的 bin 文件夹下；如果有多个工作区，就会安装到 GOBIN 指向的目录下。

命令源码文件是 Go 程序的入口。

同一个代码包中最好也不要放多个命令源码文件。多个命令源码文件虽然可以分开单独 go run 运行起来，但是无法通过 go build 和 go install。



我们先打开上次课的hello目录，然后复制helloworld.go为helloworld2.go文件，并修改里面的内容：

```go
package main
import "fmt"
func main(){
	fmt.Println("我是第二个helloworld文件")
	fmt.Print("Go Go Go !!!")
}
```

hello目录下有两个go文件了，一个是helloworld.go，一个是helloworld2.go。先说明一下，在上述文件夹中放了两个命令源码文件，同时都声明自己属于 main 代码包。

![gomingling1](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling1.png)

打开终端，进入hello这个目录，也可以看到这两个文件：

```shell
localhost:~ ruby cd go/src/hello
localhost:hello ruby ls
helloworld.go	helloworld2.go
```

然后我们分别执行go run命令，可以看到两个go文件都可以被执行：

```shell
localhost:hello ruby$ go run helloworld.go
HelloWorld
Go Go Go !!!localhost:hello ruby$ go run helloworld2.go
我是第二个helloworld文件
Go Go Go !!!
```

![gomingling2](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling2.png)



接下来执行 go build 和 go install ，看看会发生什么：

```shell
localhost:hello ruby$ go build 
# hello
./helloworld2.go:3:6: main redeclared in this block
	previous declaration at ./helloworld.go:3:6
localhost:hello ruby$ go install
# hello
./helloworld2.go:3:6: main redeclared in this block
	previous declaration at ./helloworld.go:3:6
localhost:hello ruby$ 
```

运行效果图：

![gomingling3](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling3.png)



这也就证明了多个命令源码文件虽然可以分开单独 go run 运行起来，但是无法通过 go build 和 go install。

同理，如果命令源码文件和库源码文件也会出现这样的问题，库源码文件不能通过 go build 和 go install 这种常规的方法编译和安装。具体例子和上述类似，这里就不再贴代码了。

所以命令源码文件应该是被单独放在一个代码包中。

**2、库源码文件**

库源码文件就是不具备命令源码文件上述两个特征的源码文件。存在于某个代码包中的普通的源码文件。

库源码文件被安装后，相应的归档文件（.a 文件）会被存放到当前工作区的 pkg 的平台相关目录下。



**3、测试源码文件**

名称以 _test.go 为后缀的代码文件，并且必须包含 Test 或者 Benchmark 名称前缀的函数：

```go
func TestXXX( t *testing.T) {

}
```

名称以 Test 为名称前缀的函数，只能接受 *testing.T 的参数，这种测试函数是功能测试函数。

```go
func BenchmarkXXX( b *testing.B) {

}

```

名称以 Benchmark 为名称前缀的函数，只能接受 *testing.B 的参数，这种测试函数是性能测试函数。

现在答案就很明显了：

命令源码文件是可以单独运行的。可以使用 go run 命令直接运行，也可以通过 go build 或 go install 命令得到相应的可执行文件。所以命令源码文件是可以在机器的任何目录下运行的。

举个栗子：

比如平时我们在 LeetCode 上刷算法题，这时候写的就是一个程序，这就是命令源码文件，可以在电脑的任意一个文件夹新建一个 go 文件就可以开始刷题了，写完就可以运行，对比执行结果，答案对了就可以提交代码。

但是公司项目里面的代码就不能这样了，只能存放在 GOPATH 目录下。因为公司项目不可能只有命令源码文件的，肯定是包含库源码文件，甚至包含测试源码文件的。



## 二、Go的命令

目前Go的最新版1.12里面基本命令有以下17个。

我们可以打开终端输入：go help即可看到Go的这些命令以及简介。

```shell
	bug         start a bug report
	build       compile packages and dependencies
	clean       remove object files and cached files
	doc         show documentation for package or symbol
	env         print Go environment information
	fix         update packages to use new APIs
	fmt         gofmt (reformat) package sources
	generate    generate Go files by processing source
	get         download and install packages and dependencies
	install     compile and install packages and dependencies
	list        list packages or modules
	mod         module maintenance
	run         compile and run Go program
	test        test packages
	tool        run specified go tool
	version     print Go version
	vet         report likely mistakes in packages
```



其中和编译相关的有build、get、install、run这4个。接下来就依次看看这四个的作用。

在详细分析这4个命令之前，先罗列一下通用的命令标记，以下这些命令都可适用的：

| 名称  | 说明                                                         |
| ----- | ------------------------------------------------------------ |
| -a    | 用于强制重新编译所有涉及的 Go 语言代码包（包括 Go 语言标准库中的代码包），即使它们已经是最新的了。该标记可以让我们有机会通过改动底层的代码包做一些实验。 |
| -n    | 使命令仅打印其执行过程中用到的所有命令，而不去真正执行它们。如果不只想查看或者验证命令的执行过程，而不想改变任何东西，使用它正好合适。 |
| -race | 用于检测并报告指定 Go 语言程序中存在的数据竞争问题。当用 Go 语言编写并发程序的时候，这是很重要的检测手段之一。 |
| -v    | 用于打印命令执行过程中涉及的代码包。这一定包括我们指定的目标代码包，并且有时还会包括该代码包直接或间接依赖的那些代码包。这会让你知道哪些代码包被执行过了。 |
| -work | 用于打印命令执行时生成和使用的临时工作目录的名字，且命令执行完成后不删除它。这个目录下的文件可能会对你有用，也可以从侧面了解命令的执行过程。如果不添加此标记，那么临时工作目录会在命令执行完毕前删除。 |
| -x    | 使命令打印其执行过程中用到的所有命令，并同时执行它们。       |

### 1. go run

专门用来运行命令源码文件的命令，**注意，这个命令不是用来运行所有 Go 的源码文件的！**

go run 命令只能接受一个命令源码文件以及若干个库源码文件（必须同属于 main 包）作为文件参数，且**不能接受测试源码文件**。它在执行时会检查源码文件的类型。如果参数中有多个或者没有命令源码文件，那么 go run 命令就只会打印错误提示信息并退出，而不会继续执行。

这个命令具体干了些什么事情呢？来分析分析，我们先重新创建一个新文件：mytest.go，并加入以下代码：

```go
package main
import "fmt"
func main(){
	fmt.Println("HelloWorld")
	fmt.Println("你好，Go!!!")
}
```



执行go run 配合-n：

```shell
localhost:hello ruby$ go run -n mytest.go 

#
# command-line-arguments
#

mkdir -p $WORK/b001/
cat >$WORK/b001/importcfg << 'EOF' # internal
# import config
packagefile fmt=/usr/local/go/pkg/darwin_amd64/fmt.a
packagefile runtime=/usr/local/go/pkg/darwin_amd64/runtime.a
EOF
cd /Users/ruby/go/src/hello
/usr/local/go/pkg/tool/darwin_amd64/compile -o $WORK/b001/_pkg_.a -trimpath $WORK/b001 -p main -complete -buildid ieg41NOobNF0eqq3xgnP/ieg41NOobNF0eqq3xgnP -dwarf=false -goversion go1.12.1 -D _/Users/ruby/go/src/hello -importcfg $WORK/b001/importcfg -pack -c=4 ./mytest.go
/usr/local/go/pkg/tool/darwin_amd64/buildid -w $WORK/b001/_pkg_.a # internal
cat >$WORK/b001/importcfg.link << 'EOF' # internal
... # 此处省略
EOF
mkdir -p $WORK/b001/exe/
cd .
/usr/local/go/pkg/tool/darwin_amd64/link -o $WORK/b001/exe/mytest -importcfg $WORK/b001/importcfg.link -s -w -buildmode=exe -buildid=vpgT856LhbZPXp6WeHib/ieg41NOobNF0eqq3xgnP/ieg41NOobNF0eqq3xgnP/vpgT856LhbZPXp6WeHib -extld=clang $WORK/b001/_pkg_.a
$WORK/b001/exe/mytest
localhost:hello ruby$ 

```

运行效果图：

![gomingling4](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling4.gif)



这里可以看到创建了两个临时文件夹 b001 和 exe，先执行了 compile 命令，然后 link，生成了归档文件.a 和 最终可执行文件，最终的可执行文件放在 exe 文件夹里面。命令的最后一步就是执行了可执行文件。

总结一下如下图：

![gomingling5](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling5.jpg)



举个例子，生成的临时文件可以用`go run -work`看到，比如当前生成的临时文件夹是如下的路径：

```shell
localhost:hello ruby$ go run -work mytest.go 
WORK=/var/folders/kt/nlhsnpgn6lgd_q16f8j83sbh0000gn/T/go-build593750496
HelloWorld
你好，Go!!!
localhost:hello ruby$ 
```

我们进入：`/var/folders/kt/nlhsnpgn6lgd_q16f8j83sbh0000gn/T/go-build593750496`目录，可以看到如下目录结构：

![gomingling6](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling6.png)



可以看到，最终`go run`命令是生成了2个文件，一个是归档文件，一个是可执行文件。

go run 命令在第二次执行的时候，如果发现导入的代码包没有发生变化，那么 go run 不会再次编译这个导入的代码包。直接静态链接进来。

```shell
localhost:hello ruby$ go run -n mytest.go 
mkdir -p $WORK/b001/
cat >$WORK/b001/importcfg.link << 'EOF' # internal
packagefile command-line-arguments=/Users/ruby/Library/Caches/go-build/6b/6b9577027c8da20b0ae6da790267f558b3b71eea1feb44039fb933b35eaef6f9-d
packagefile fmt=/usr/local/go/pkg/darwin_amd64/fmt.a
...
EOF
mkdir -p $WORK/b001/exe/
cd .
/usr/local/go/pkg/tool/darwin_amd64/link -o $WORK/b001/exe/mytest -importcfg $WORK/b001/importcfg.link -s -w -buildmode=exe -buildid=goiqf_1cemqljgOYzSRA/ieg41NOobNF0eqq3xgnP/MVbHdxOky1BGK6Aq_4bM/goiqf_1cemqljgOYzSRA -extld=clang /Users/ruby/Library/Caches/go-build/6b/6b9577027c8da20b0ae6da790267f558b3b71eea1feb44039fb933b35eaef6f9-d
$WORK/b001/exe/mytest
localhost:hello ruby$ 

```



### 2. go build

go build 命令主要是用于测试编译。在包的编译过程中，若有必要，会同时编译与之相关联的包。

1. 如果是普通包，当你执行go build命令后，不会产生任何文件。
2. 如果是main包，当只执行go build命令后，会在当前目录下生成一个可执行文件。如果需要在$GOPATH/bin目录下生成相应的exe文件，需要执行go install 或者使用 go build -o 路径/可执行文件。
3. 如果某个文件夹下有多个文件，而你只想编译其中某一个文件，可以在 go build 之后加上文件名，例如 go build a.go；go build 命令默认会编译当前目录下的所有go文件。
4. 你也可以指定编译输出的文件名。比如，我们可以指定go build -o 可执行文件名，默认情况是你的package名(非main包)，或者是第一个源文件的文件名(main包)。
5. go build 会忽略目录下以”_”或者”.”开头的go文件。
6. 如果你的源代码针对不同的操作系统需要不同的处理，那么你可以根据不同的操作系统后缀来命名文件。



当代码包中有且仅有一个命令源码文件的时候，在文件夹所在目录中执行 go build 命令，会在该目录下生成一个与目录同名的可执行文件。

```shell
// 假设当前文件夹名叫 hello
localhost:hello ruby$ pwd
/Users/ruby/go/src/hello
localhost:hello ruby$ ls
helloworld.go
localhost:hello ruby$ go build
localhost:hello ruby$ ls
hello		helloworld.go
localhost:hello ruby$ 
```



于是在当前目录直接生成了以当前文件夹为名的可执行文件（ 在 Mac 平台下是 Unix executable 文件，在 Windows 平台下是 exe 文件）

![gomingling7](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling7.png)



但是这种情况下，如果使用 go install 命令，如果 GOPATH 里面只有一个工作区，就会在当前工作区的 bin 目录下生成相应的可执行文件。如果 GOPATH 下有多个工作区，则是在 GOBIN 下生成对应的可执行文件。

```shell
localhost:hello ruby$ go install
go install hello: open /usr/local/go/bin/hello: permission denied
localhost:hello ruby$ 
```



![gomingling8](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling8.png)



> 这个问题是因为它需要创建bin目录，然后把可刚才的可执行文件放进去，而目前我们在gopath下还没有bin目录，那么就需要先创建这个文件，而普通用户没有直接创建文件夹的权限，这个和Go语言的命令是没有关系的。我们可以加上sodu 来执行这个命令，表示使用管理员的身份执行，然后输入密码，那么就可以创建bin这个文件夹了。



再次执行：

```shell
localhost:hello ruby$ sudo go install
Password:
localhost:hello ruby$ 

```

执行完 go install 会发现可执行文件不见了！去哪里了呢？其实是被移动到了 bin 目录下了（如果 GOPATH 下有多个工作区，就会放在GOBIN 目录下）。

查看目录：

![gomingling9](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling9.png)





那 go build 和 go install 究竟干了些什么呢？

先来说说 go build。go build 用于编译我们指定的源码文件或代码包以及它们的依赖包。但是**注意如果用来编译非命令源码文件，即库源码文件，go build 执行完是不会产生任何结果的。这种情况下，go build 命令只是检查库源码文件的有效性，只会做检查性的编译，而不会输出任何结果文件。**

go build 编译命令源码文件，则会在该命令的执行目录中生成一个可执行文件，上面的例子也印证了这个过程。

go build 后面不追加目录路径的话，它就把当前目录作为代码包并进行编译。go build 命令后面如果跟了代码包导入路径作为参数，那么该代码包及其依赖都会被编译。

go build 命令究竟做了些什么呢？我们可以执行-n这个命令来查看：

```shell
localhost:hello ruby$ go build -n

#
# hello
#

mkdir -p $WORK/b001/
cat >$WORK/b001/importcfg << 'EOF' # internal
# import config
packagefile fmt=/usr/local/go/pkg/darwin_amd64/fmt.a
packagefile runtime=/usr/local/go/pkg/darwin_amd64/runtime.a
EOF
cd /Users/ruby/go/src/hello
/usr/local/go/pkg/tool/darwin_amd64/compile -o $WORK/b001/_pkg_.a -trimpath $WORK/b001 -p main -complete -buildid PXDetO1R1NhLFMK5QGUc/PXDetO1R1NhLFMK5QGUc -goversion go1.12.1 -D "" -importcfg $WORK/b001/importcfg -pack -c=4 ./helloworld.go
/usr/local/go/pkg/tool/darwin_amd64/buildid -w $WORK/b001/_pkg_.a # internal
cat >$WORK/b001/importcfg.link << 'EOF' # internal
packagefile hello=$WORK/b001/_pkg_.a
...
EOF
mkdir -p $WORK/b001/exe/
cd .
/usr/local/go/pkg/tool/darwin_amd64/link -o $WORK/b001/exe/a.out -importcfg $WORK/b001/importcfg.link -buildmode=exe -buildid=diTh1q6kcbGRIX3aj3mU/PXDetO1R1NhLFMK5QGUc/PXDetO1R1NhLFMK5QGUc/diTh1q6kcbGRIX3aj3mU -extld=clang $WORK/b001/_pkg_.a
/usr/local/go/pkg/tool/darwin_amd64/buildid -w $WORK/b001/exe/a.out # internal
mv $WORK/b001/exe/a.out hello
localhost:hello ruby$ 

```

可以看到，执行过程和 go run 大体相同，唯一不同的就是在最后一步，go run 是执行了可执行文件，但是 go build 命令，只是把库源码文件编译了一遍，然后把可执行文件移动到了当前目录的文件夹中。

总结一下如下图：

![gomingling10](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling10.jpg)



### 3. go install

go install 命令是用来编译并安装代码包或者源码文件的。

go install 命令在内部实际上分成了两步操作：第一步是生成结果文件(可执行文件或者.a包)，第二步会把编译好的结果移到` $GOPATH/pkg `或者​`$GOPATH/bin`。

可执行文件： 一般是 go install 带main函数的go文件产生的，有函数入口，所有可以直接运行。

.a应用包： 一般是 go install 不包含main函数的go文件产生的，没有函数入口，只能被调用。

go install 用于编译并安装指定的代码包及它们的依赖包。当指定的代码包的依赖包还没有被编译和安装时，该命令会先去处理依赖包。与 go build 命令一样，传给 go install 命令的代码包参数应该以导入路径的形式提供。并且，go build 命令的绝大多数标记也都可以用于
实际上，go install 命令只比 go build 命令多做了一件事，即：安装编译后的结果文件到指定目录。

安装代码包会在当前工作区的 pkg 的平台相关目录下生成归档文件（即 .a 文件）。
安装命令源码文件会在当前工作区的 bin 目录（如果 GOPATH 下有多个工作区，就会放在 GOBIN 目录下）生成可执行文件。

同样，go install 命令如果后面不追加任何参数，它会把当前目录作为代码包并安装。这和 go build 命令是完全一样的。

go install 命令后面如果跟了代码包导入路径作为参数，那么该代码包及其依赖都会被安装。

go install 命令后面如果跟了命令源码文件以及相关库源码文件作为参数的话，只有这些文件会被编译并安装。

go install 命令究竟做了些什么呢？

```shell
localhost:hello ruby$ go install -n

#
# hello
#

mkdir -p $WORK/b001/
cat >$WORK/b001/importcfg << 'EOF' # internal
# import config
packagefile fmt=/usr/local/go/pkg/darwin_amd64/fmt.a
packagefile runtime=/usr/local/go/pkg/darwin_amd64/runtime.a
EOF
cd /Users/ruby/go/src/hello
/usr/local/go/pkg/tool/darwin_amd64/compile -o $WORK/b001/_pkg_.a -trimpath $WORK/b001 -p main -complete -buildid E1CTs4eXkD5M28s_FQXT/E1CTs4eXkD5M28s_FQXT -goversion go1.12.1 -D "" -importcfg $WORK/b001/importcfg -pack -c=4 ./helloworld.go
/usr/local/go/pkg/tool/darwin_amd64/buildid -w $WORK/b001/_pkg_.a # internal
cat >$WORK/b001/importcfg.link << 'EOF' # internal
packagefile hello=$WORK/b001/_pkg_.a
packagefile fmt=/usr/local/go/pkg/darwin_amd64/fmt.a
...
EOF
mkdir -p $WORK/b001/exe/
cd .
/usr/local/go/pkg/tool/darwin_amd64/link -o $WORK/b001/exe/a.out -importcfg $WORK/b001/importcfg.link -buildmode=exe -buildid=FJ6kJTmN9rcWcwLhqfiQ/E1CTs4eXkD5M28s_FQXT/E1CTs4eXkD5M28s_FQXT/FJ6kJTmN9rcWcwLhqfiQ -extld=clang $WORK/b001/_pkg_.a
/usr/local/go/pkg/tool/darwin_amd64/buildid -w $WORK/b001/exe/a.out # internal
mkdir -p /usr/local/go/bin/
mv $WORK/b001/exe/a.out /usr/local/go/bin/hello
localhost:hello ruby$ 

```

前面几步依旧和 go run 、go build 完全一致，只是最后一步的差别，go install 会把命令源码文件安装到当前工作区的 bin 目录（如果 GOPATH 下有多个工作区，就会放在 GOBIN 目录下）。如果是库源码文件，就会被安装到当前工作区的 pkg 的平台相关目录下。



总结一下如下图：

![gomingling11](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling11.jpg)



在安装多个库源码文件时有可能遇到如下的问题：

```shell
localhost:hello ruby$  go install envir.go fpath.go ipath.go pnode.go util.go
go install: no install location for .go files listed on command line (GOBIN not set)
```

而且，在我们为环境变量 GOBIN 设置了正确的值之后，这个错误提示信息仍然会出现。这是因为，只有在安装命令源码文件的时候，命令程序才会将环境变量 GOBIN 的值作为结果文件的存放目录。而在安装库源码文件时，在命令程序内部的代表结果文件存放目录路径的那个变量不会被赋值。最后，命令程序会发现它依然是个无效的空值。所以，命令程序会同样返回一个关于“无安装位置”的错误。这就引出一个结论，我们只能使用安装代码包的方式来安装库源码文件，而不能在 go install 命令罗列并安装它们。另外，go install 命令目前无法接受标记`-o`以自定义结果文件的存放位置。这也从侧面说明了
 go install 命令不支持针对库源码文件的安装操作。



### 4. go get

go get 命令用于从远程代码仓库（比如 Github ）上下载并安装代码包。**注意，go get 命令会把当前的代码包下载到 $GOPATH 中的第一个工作区的 src 目录中，并安装。**

> 使用 go get 下载第三方包的时候，依旧会下载到 $GOPATH 的第一个工作空间，而非 vendor 目录。当前工作链中并没有真正意义上的包依赖管理，不过好在有不少第三方工具可选。

如果在 go get 下载过程中加入`-d` 标记，那么下载操作只会执行下载动作，而不执行安装动作。比如有些非常特殊的代码包在安装过程中需要有特殊的处理，所以我们需要先下载下来，所以就会用到`-d` 标记。

还有一个很有用的标记是`-u`标记，加上它可以利用网络来更新已有的代码包及其依赖包。如果已经下载过一个代码包，但是这个代码包又有更新了，那么这时候可以直接用`-u`标记来更新本地的对应的代码包。如果不加这个`-u`标记，执行 go get 一个已有的代码包，会发现命令什么都不执行。只有加了`-u`标记，命令会去执行 git pull 命令拉取最新的代码包的最新版本，下载并安装。

命令 go get 还有一个很值得称道的功能——智能下载。在使用它检出或更新代码包之后，它会寻找与本地已安装 Go 语言的版本号相对应的标签（tag）或分支（branch）。比如，本机安装 Go 语言的版本是1.x，那么 go get 命令会在该代码包的远程仓库中寻找名为 “go1” 的标签或者分支。如果找到指定的标签或者分支，则将本地代码包的版本切换到此标签或者分支。如果没有找到指定的标签或者分支，则将本地代码包的版本切换到主干的最新版本。

go get 常用的一些标记如下：

| 标记名称  | 标记描述                                                     |
| --------- | ------------------------------------------------------------ |
| -d        | 让命令程序只执行下载动作，而不执行安装动作。                 |
| -f        | 仅在使用`-u`标记时才有效。该标记会让命令程序忽略掉对已下载代码包的导入路径的检查。如果下载并安装的代码包所属的项目是你从别人那里 Fork 过来的，那么这样做就尤为重要了。 |
| -fix      | 让命令程序在下载代码包后先执行修正动作，而后再进行编译和安装。 |
| -insecure | 允许命令程序使用非安全的 scheme（如 HTTP ）去下载指定的代码包。如果你用的代码仓库（如公司内部的 Gitlab ）没有HTTPS 支持，可以添加此标记。请在确定安全的情况下使用它。 |
| -t        | 让命令程序同时下载并安装指定的代码包中的测试源码文件中依赖的代码包。 |
| -u        | 让命令利用网络来更新已有代码包及其依赖包。默认情况下，该命令只会从网络上下载本地不存在的代码包，而不会更新已有的代码包。 |

go get 命令究竟做了些什么呢？我们还是来打印一下每一步的执行过程。

```shell
localhost:hello ruby$ go get -x github.com/go-errors/errors
cd .
git clone https://github.com/go-errors/errors /Users/ruby/go/src/github.com/go-errors/errors
cd /Users/ruby/go/src/github.com/go-errors/errors
git submodule update --init --recursive
cd /Users/ruby/go/src/github.com/go-errors/errors
git show-ref
cd /Users/ruby/go/src/github.com/go-errors/errors
git submodule update --init --recursive
WORK=/var/folders/kt/nlhsnpgn6lgd_q16f8j83sbh0000gn/T/go-build188558329
localhost:hello ruby$ 
```

效果图：

![gomingling12](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling12.png)



这里可以很明显的看到，执行完 go get 命令以后，会调用 git clone 方法下载源码，并编译，最终会把库源码文件编译成归档文件安装到 pkg 对应的相关平台目录下。

![gomingling13](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling13.png)





总结一下如下图：

![gomingling14](http://7xtcwd.com1.z0.glb.clouddn.com/gomingling14.jpg)





### 5. 其他命令

**go clean**

go clean 命令是用来移除当前源码包里面编译生成的文件，这些文件包括

- _obj/ 旧的object目录，由Makefiles遗留
- _test/ 旧的test目录，由Makefiles遗留
- _testmain.go 旧的gotest文件，由Makefiles遗留
- test.out 旧的test记录，由Makefiles遗留
- build.out 旧的test记录，由Makefiles遗留
- *.[568ao] object文件，由Makefiles遗留
- DIR(.exe) 由 go build 产生
- DIR.test(.exe) 由 go test -c 产生
- MAINFILE(.exe) 由 go build MAINFILE.go产生



**go fmt**

go fmt 命令主要是用来帮你格式化所写好的代码文件。

比如我们写了一个格式很糟糕的 test.go 文件，我们只需要使用 fmt go test.go 命令，就可以让go帮我们格式化我们的代码文件。但是我们一般很少使用这个命令，因为我们的开发工具一般都带有保存时自动格式化功能，这个功能底层其实就是调用了 go fmt 命令而已。

使用go fmt命令，更多时候是用gofmt，而且需要参数-w，否则格式化结果不会写入文件。gofmt -w src，可以格式化整个项目。





**go test**

go test 命令，会自动读取源码目录下面名为*_test.go的文件，生成并运行测试用的可执行文件。默认的情况下，不需要任何的参数，它会自动把你源码包下面所有test文件测试完毕，当然你也可以带上参数，详情请参考go help testflag





**go doc**

go doc 命令其实就是一个很强大的文档工具。

如何查看相应package的文档呢？ 例如builtin包，那么执行go doc builtin；如果是http包，那么执行go doc net/http；查看某一个包里面的函数，那么执行go doc fmt Printf；也可以查看相应的代码，执行go doc -src fmt Printf；

```shell
# 查看net/http包
localhost:hello ruby$ go doc net/http
# 查看time包
localhost:hello ruby$ go doc time
# 查看某个包里的指定函数
localhost:hello ruby$ go doc fmt Printf
```



通过命令在命令行执行 go doc -http=:端口号，比如godoc -http=:8080。然后在浏览器中打开127.0.0.1:8080，你将会看到一个golang.org的本地copy版本，通过它你可以查询pkg文档等其它内容。如果你设置了GOPATH，在pkg分类下，不但会列出标准包的文档，还会列出你本地GOPATH中所有项目的相关文档，这对于经常被限制访问的用户来说是一个不错的选择。

```shell
localhost:hello ruby$ godoc -http=:9527
```





go fix 用来修复以前老版本的代码到新版本，例如go1之前老版本的代码转化到go1

go version 查看go当前的版本

go env 查看当前go的环境变量

go list 列出当前全部安装的package




# 编码规范

本规范旨在为日常Go项目开发提供一个代码的规范指导，方便团队形成一个统一的代码风格，提高代码的可读性，规范性和统一性。本规范将从命名规范，注释规范，代码风格和 Go 语言提供的常用的工具这几个方面做一个说明。该规范参考了 go 语言官方代码的风格制定。

## 一、 命名规范

命名是代码规范中很重要的一部分，统一的命名规则有利于提高的代码的可读性，好的命名仅仅通过命名就可以获取到足够多的信息。

Go在命名时以字母a到Z或a到Z或下划线开头，后面跟着零或更多的字母、下划线和数字(0到9)。Go不允许在命名时中使用@、$和%等标点符号。Go是一种区分大小写的编程语言。因此，Manpower和manpower是两个不同的命名。

> 1. 当命名（包括常量、变量、类型、函数名、结构字段等等）以一个大写字母开头，如：Group1，那么使用这种形式的标识符的对象就**可以被外部包的代码所使用**（客户端程序需要先导入这个包），这被称为导出（像面向对象语言中的 public）；
> 2. **命名如果以小写字母开头，则对包外是不可见的，但是他们在整个包的内部是可见并且可用的**（像面向对象语言中的 private ）



### 1、包命名：package

保持package的名字和目录保持一致，尽量采取有意义的包名，简短，有意义，尽量和标准库不要冲突。包名应该为**小写**单词，不要使用下划线或者混合大小写。

```go
package demo

package main
```



### 2、 文件命名

尽量采取有意义的文件名，简短，有意义，应该为**小写**单词，使用**下划线**分隔各个单词。

```go
my_test.go
```



### 3、 结构体命名
- 采用驼峰命名法，首字母根据访问控制大写或者小写

- struct 申明和初始化格式采用多行，例如下面：

```go
// 多行申明
type User struct{
    Username  string
    Email     string
}

// 多行初始化
u := User{
    Username: "astaxie",
    Email:    "astaxie@gmail.com",
}

```



### 4、 接口命名

- 命名规则基本和上面的结构体类型
- 单个函数的结构名以 “er” 作为后缀，例如 Reader , Writer 。

```go
type Reader interface {
        Read(p []byte) (n int, err error)
}

```



### 5、变量命名

- 和结构体类似，变量名称一般遵循驼峰法，首字母根据访问控制原则大写或者小写，但遇到特有名词时，需要遵循以下规则： 
  - 如果变量为私有，且特有名词为首个单词，则使用小写，如 apiClient
  - 其它情况都应当使用该名词原有的写法，如 APIClient、repoID、UserID
  - 错误示例：UrlArray，应该写成 urlArray 或者 URLArray
- 若变量类型为 bool 类型，则名称应以 Has, Is, Can 或 Allow 开头

```go
var isExist bool
var hasConflict bool
var canManage bool
var allowGitHook bool
```



### 6、常量命名

常量均需使用全部大写字母组成，并使用下划线分词

```go
const APP_VER = "1.0"
```


如果是枚举类型的常量，需要先创建相应类型：

```go
type Scheme string

const (
    HTTP  Scheme = "http"
    HTTPS Scheme = "https"
)

```



### 7、 关键字

下面的列表显示了Go中的保留字。这些保留字不能用作常量或变量或任何其他标识符名称。



![guanjianzi](http://7xtcwd.com1.z0.glb.clouddn.com/guanjianzi.jpg)



## 二、注释

Go提供C风格的`/* */`块注释和C ++风格的`//`行注释。行注释是常态；块注释主要显示为包注释，但在表达式中很有用或禁用大量代码。

- 单行注释是最常见的注释形式，你可以在任何地方使用以 // 开头的单行注释
- 多行注释也叫块注释，均已以 /* 开头，并以 */ 结尾，且不可以嵌套使用，多行注释一般用于包的文档描述或注释成块的代码片段

go 语言自带的 godoc 工具可以根据注释生成文档，生成可以自动生成对应的网站（ golang.org 就是使用 godoc 工具直接生成的），注释的质量决定了生成的文档的质量。每个包都应该有一个包注释，在package子句之前有一个块注释。对于多文件包，包注释只需要存在于一个文件中，任何一个都可以。包评论应该介绍包，并提供与整个包相关的信息。它将首先出现在`godoc`页面上，并应设置下面的详细文档。

详细的如何写注释可以
参考：<http://golang.org/doc/effective_go.html#commentary>



### 1、包注释

每个包都应该有一个包注释，一个位于package子句之前的块注释或行注释。包如果有多个go文件，只需要出现在一个go文件中（一般是和包同名的文件）即可。 包注释应该包含下面基本信息(请严格按照这个顺序，简介，创建人，创建时间）：

- 包的基本简介（包名，简介）
- 创建者，格式： 创建人： rtx 名
- 创建时间，格式：创建时间： yyyyMMdd

例如 util 包的注释示例如下

```go
// util 包， 该包包含了项目共用的一些常量，封装了项目中一些共用函数。
// 创建人： hanru
// 创建时间： 20190419
```



### 2、结构（接口）注释

每个自定义的结构体或者接口都应该有注释说明，该注释对结构进行简要介绍，放在结构体定义的前一行，格式为： 结构体名， 结构体说明。同时结构体内的每个成员变量都要有说明，该说明放在成员变量的后面（注意对齐），实例如下：

```go
// User ， 用户对象，定义了用户的基础信息
type User struct{
    Username  string // 用户名
    Email     string // 邮箱
}
```



### 3、函数（方法）注释

每个函数，或者方法（结构体或者接口下的函数称为方法）都应该有注释说明，函数的注释应该包括三个方面（严格按照此顺序撰写）：

- 简要说明，格式说明：以函数名开头，“，”分隔说明部分
- 参数列表：每行一个参数，参数名开头，“，”分隔说明部分
- 返回值： 每行一个返回值

示例如下：

```go
// NewtAttrModel ， 属性数据层操作类的工厂方法
// 参数：
//      ctx ： 上下文信息
// 返回值：
//      属性操作类指针
func NewAttrModel(ctx *common.Context) *AttrModel {
}
```



### 4、代码逻辑注释

对于一些关键位置的代码逻辑，或者局部较为复杂的逻辑，需要有相应的逻辑说明，方便其他开发者阅读该段代码，实例如下：

```go
// 从 Redis 中批量读取属性，对于没有读取到的 id ， 记录到一个数组里面，准备从 DB 中读取
xxxxx
xxxxxxx
xxxxxxx
```



### 5、注释风格

统一使用中文注释，对于中英文字符之间严格使用空格分隔， 这个不仅仅是中文和英文之间，英文和中文标点之间也都要使用空格分隔，例如：

```go
// 从 Redis 中批量读取属性，对于没有读取到的 id ， 记录到一个数组里面，准备从 DB 中读取
```


上面 Redis 、 id 、 DB 和其他中文字符之间都是用了空格分隔。 

* 建议全部使用单行注释
* 和代码的规范一样，单行注释不要过长，禁止超过 120 字符。



## 三、代码风格

### 1、缩进和折行

- 缩进直接使用 gofmt 工具格式化即可（gofmt 是使用 tab 缩进的）；
- 折行方面，一行最长不超过120个字符，超过的请使用换行展示，尽量保持格式优雅。

我们使用Goland开发工具，可以直接使用快捷键：ctrl+alt+L，即可。



### 2、语句的结尾

Go语言中是不需要类似于Java需要冒号结尾，默认一行就是一条数据

如果你打算将多个语句写在同一行，它们则必须使用 **;** 



### 3、括号和空格

括号和空格方面，也可以直接使用 gofmt 工具格式化（go 会强制左大括号不换行，换行会报语法错误），所有的运算符和操作数之间要留空格。

```go
// 正确的方式
if a > 0 {

} 

// 错误的方式
if a>0  // a ，0 和 > 之间应该空格
{       // 左大括号不可以换行，会报语法错误

}

```



### 4、import 规范

import在多行的情况下，goimports会自动帮你格式化，但是我们这里还是规范一下import的一些规范，如果你在一个文件里面引入了一个package，还是建议采用如下格式：

```go
import (
    "fmt"
)
```

如果你的包引入了三种类型的包，标准库包，程序内部包，第三方包，建议采用如下方式进行组织你的包：

```go
import (
    "encoding/json"
    "strings"

    "myproject/models"
    "myproject/controller"
    "myproject/utils"

    "github.com/astaxie/beego"
    "github.com/go-sql-driver/mysql"
)   
```

有顺序的引入包，不同的类型采用空格分离，第一种实标准库，第二是项目包，第三是第三方包。

在项目中不要使用相对路径引入包：

```go
// 这是不好的导入
import “../net”

// 这是正确的做法
import “github.com/repo/proj/src/net”
```

但是如果是引入本项目中的其他包，最好使用相对路径。

### 5、错误处理

- 错误处理的原则就是不能丢弃任何有返回err的调用，不要使用 _ 丢弃，必须全部处理。接收到错误，要么返回err，或者使用log记录下来
- 尽早return：一旦有错误发生，马上返回
- 尽量不要使用panic，除非你知道你在做什么
- 错误描述如果是英文必须为小写，不需要标点结尾
- 采用独立的错误流进行处理

```go
// 错误写法
if err != nil {
    // error handling
} else {
    // normal code
}

// 正确写法
if err != nil {
    // error handling
    return // or continue, etc.
}
// normal code

```



### 6、测试

单元测试文件名命名规范为 example_test.go
测试用例的函数名称必须以 Test 开头，例如：TestExample
每个重要的函数都要首先编写测试用例，测试用例和正规代码一起提交方便进行回归测试



## 四、常用工具

上面提到了很过规范， go 语言本身在代码规范性这方面也做了很多努力，很多限制都是强制语法要求，例如左大括号不换行，引用的包或者定义的变量不使用会报错，此外 go 还是提供了很多好用的工具帮助我们进行代码的规范，

**gofmt**
大部分的格式问题可以通过gofmt解决， gofmt 自动格式化代码，保证所有的 go 代码与官方推荐的格式保持一致，于是所有格式有关问题，都以 gofmt 的结果为准。

**goimport**
我们强烈建议使用 goimport ，该工具在 gofmt 的基础上增加了自动删除和引入包.

```shell
go get golang.org/x/tools/cmd/goimports
```

**go vet**
vet工具可以帮我们静态分析我们的源码存在的各种问题，例如多余的代码，提前return的逻辑，struct的tag是否符合标准等。

```shell
go get golang.org/x/tools/cmd/vet
```


使用如下：

```go
go vet .
```



# 基本语法——变量

## 一、变量的使用

### 1.1 什么是变量

变量是为存储特定类型的值而提供给内存位置的名称。在go中声明变量有多种语法。

所以变量的本质就是一小块内存，用于存储数据，在程序运行过程中数值可以改变



### 1.2 声明变量

var名称类型是声明单个变量的语法。

> 以字母或下划线开头，由一个或多个字母、数字、下划线组成

声明一个变量

第一种，指定变量类型，声明后若不赋值，使用默认值

```go
var name type
name = value
```

第二种，根据值自行判定变量类型(类型推断Type inference)

如果一个变量有一个初始值，Go将自动能够使用初始值来推断该变量的类型。因此，如果变量具有初始值，则可以省略变量声明中的类型。

```go
var name = value
```

第三种，省略var, 注意 :=左侧的变量不应该是已经声明过的(多个变量同时声明时，至少保证一个是新变量)，否则会导致编译错误(简短声明)



```go
name := value

// 例如
var a int = 10
var b = 10
c : = 10
```

> 这种方式它只能被用在函数体内，而不可以用于全局变量的声明与赋值

示例代码：

```go
package main
var a = "Hello"
var b string = "World"
var c bool

func main(){
    println(a, b, c)
}
```

运行结果：

```go
Hello World false
```

#### 多变量声明

第一种，以逗号分隔，声明与赋值分开，若不赋值，存在默认值

```go
var name1, name2, name3 type
name1, name2, name3 = v1, v2, v3
```

第二种，直接赋值，下面的变量类型可以是不同的类型

```go
var name1, name2, name3 = v1, v2, v3
```

第三种，集合类型

```go
var (
    name1 type1
    name2 type2
)
```

### 1.3 注意事项

如果在相同的代码块中，我们不可以再次对于相同名称的变量使用初始化声明，例如：a := 20 就是不被允许的，编译器会提示错误 no new variables on left side of :=，但是 a = 20 是可以的，因为这是给相同的变量赋予一个新的值。

如果你在定义变量 a 之前使用它，则会得到编译错误 undefined: a。如果你声明了一个局部变量却没有在相同的代码块中使用它，同样会得到编译错误，例如下面这个例子当中的变量 a：

```go
func main() {
   var a string = "abc"
   fmt.Println("hello, world")
}
```

尝试编译这段代码将得到错误 a declared and not used

此外，单纯地给 a 赋值也是不够的，这个值必须被使用，所以使用

在同一个作用域中，已存在同名的变量，则之后的声明初始化，则退化为赋值操作。但这个前提是，最少要有一个新的变量被定义，且在同一作用域，例如，下面的y就是新定义的变量

```go
package main

import (
	"fmt"
)

func main() {
	x := 140
	fmt.Println(&x)
	x, y := 200, "abc"
	fmt.Println(&x, x)
	fmt.Print(y)
}
```

运行结果：

```go
0xc04200a2b0
0xc04200a2b0 200
abc
```


# 基本语法——常量constant

## 一、常量的使用

### 1.1 常量声明

常量是一个简单值的标识符，在程序运行时，不会被修改的量。

```go
const identifier [type] = value
```

```go
显式类型定义： const b string = "abc"
隐式类型定义： const b = "abc"
```
```go
package main

import "fmt"

func main() {
   const LENGTH int = 10
   const WIDTH int = 5   
   var area int
   const a, b, c = 1, false, "str" //多重赋值

   area = LENGTH * WIDTH
   fmt.Printf("面积为 : %d", area)
   println()
   println(a, b, c)   
}
```
运行结果：

```go
面积为 : 50
1 false str
```

常量可以作为枚举，常量组

```go
const (
    Unknown = 0
    Female = 1
    Male = 2
)
```
常量组中如不指定类型和初始化值，则与上一行非空常量右值相同

```go
package main

import (
	"fmt"
)

func main() {
	const (
		x uint16 = 16
		y
		s = "abc"
		z
	)
	fmt.Printf("%T,%v\n", y, y)
	fmt.Printf("%T,%v\n", z, z)
}
```
运行结果：

```go
uint16,16
string,abc
```

常量的注意事项：

- 常量中的数据类型只可以是布尔型、数字型（整数型、浮点型和复数）和字符串型

- 不曾使用的常量，在编译的时候，是不会报错的

- 显示指定类型的时候，必须确保常量左右值类型一致，需要时可做显示类型转换。这与变量就不一样了，变量是可以是不同的类型值



### 1.2 iota

iota，特殊常量，可以认为是一个可以被编译器修改的常量

iota 可以被用作枚举值：

```go
const (
    a = iota
    b = iota
    c = iota
)
```
第一个 iota 等于 0，每当 iota 在新的一行被使用时，它的值都会自动加 1；所以 a=0, b=1, c=2 可以简写为如下形式：

```go
const (
    a = iota
    b
    c
)
```
**iota 用法**

```go
package main

import "fmt"

func main() {
    const (
            a = iota   //0
            b          //1
            c          //2
            d = "ha"   //独立值，iota += 1
            e          //"ha"   iota += 1
            f = 100    //iota +=1
            g          //100  iota +=1
            h = iota   //7,恢复计数
            i          //8
    )
    fmt.Println(a,b,c,d,e,f,g,h,i)
}
```
运行结果：

```
0 1 2 ha ha 100 100 7 8
```

如果中断iota自增，则必须显式恢复。且后续自增值按行序递增

自增默认是int类型，可以自行进行显示指定类型

数字常量不会分配存储空间，无须像变量那样通过内存寻址来取值，因此无法获取地址



# 基本语法——数据类型

## 一、基本数据类型

以下是go中可用的基本数据类型

![002shujuleixng](http://7xtcwd.com1.z0.glb.clouddn.com/002shujuleixng.jpg)



### 1.1 布尔型bool

布尔型的值只可以是常量 true 或者 false。一个简单的例子：var b bool = true

### 1.2 数值型

1、整数型

- int8
  有符号 8 位整型 (-128 到 127)
长度：8bit

- int16
  有符号 16 位整型 (-32768 到 32767)
- int32
  有符号 32 位整型 (-2147483648 到 2147483647)
- int64
  有符号 64 位整型 (-9223372036854775808 到 9223372036854775807)
- uint8
  无符号 8 位整型 (0 到 255)
8位都用于表示数值：

- uint16
  无符号 16 位整型 (0 到 65535)
- uint32
  无符号 32 位整型 (0 到 4294967295)
- uint64
  无符号 64 位整型 (0 到 18446744073709551615)
> int和uint:根据底层平台，表示32或64位整数。除非需要使用特定大小的整数，否则通常应该使用int来表示整数。
> 大小:32位系统32位，64位系统64位。
> 范围:-2147483648到2147483647的32位系统和-9223372036854775808到9223372036854775807的64位系统。

**2、浮点型**

- float32

  IEEE-754 32位浮点型数

- float64

  IEEE-754 64位浮点型数

- complex64

  32 位实数和虚数

- complex128

  64 位实数和虚数

**3、其他**

- byte

  类似 uint8

- rune

  类似 int32

- uint

  32 或 64 位

- int

  与 uint 一样大小

- uintptr

  无符号整型，用于存放一个指针

### 1.3 字符串型

字符串就是一串固定长度的字符连接起来的字符序列。Go的字符串是由单个字节连接起来的。Go语言的字符串的字节使用UTF-8编码标识Unicode文本

```go
	var str string
	str = "Hello World"
```



### 1.4 数据类型转换：Type Convert

语法格式：Type(Value)

常数：在有需要的时候，会自动转型

变量：需要手动转型	T(V)



注意点：兼容类型可以转换



## 二、 复合类型(派生类型)

1、指针类型（Pointer）
2、数组类型
3、结构化类型(struct)
4、Channel 类型
5、函数类型
6、切片类型
7、接口类型（interface）
8、Map 类型



# 基本数据——运算符

表达式：(a + b) * c

​	a,b,c叫做操作数

​	+，*，叫做运算符

## 一、运算符

###1.1  算术运算符

```go
+ - * / %(求余) ++ --
```

###1.2 关系运算符

```go
== != > < >= <=
```

###1.3 逻辑运算符

| 运算符 | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| &&     | 所谓逻辑与运算符。如果两个操作数都非零，则条件变为真         |
| \|\|   | 所谓的逻辑或操作。如果任何两个操作数是非零，则条件变为真     |
| !      | 所谓逻辑非运算符。使用反转操作数的逻辑状态。如果条件为真，那么逻辑非操后结果为假 |

###1.4 位运算符

| A    | B    | A&B  | A\|B | A^B  |
| ---- | ---- | ---- | ---- | ---- |
| 0    | 0    | 0    | 0    | 0    |
| 0    | 1    | 0    | 1    | 1    |
| 1    | 1    | 1    | 1    | 0    |
| 1    | 0    | 0    | 1    | 1    |

这里最难理解的就是^了，只要认为AB两者都相同的时候，为0，其他都为1

假设A为60，B为13

| 运算 | 描述                                                         | 示例                            |
| ---- | ------------------------------------------------------------ | ------------------------------- |
| &    | 二进制与操作副本位的结果，如果它存在于两个操作数             | (A & B) = 12, 也就是 0000 1100  |
| \|   | 二进制或操作副本，如果它存在一个操作数                       | (A \| B) = 61, 也就是 0011 1101 |
| ^    | 二进制异或操作副本，如果它被设置在一个操作数就是按位取非     | (A ^ B) = 49, 也就是 0011 0001  |
| &^   | 二进制位清空&^                                               | (A&^B)=48，也就是110000         |
| <<   | 二进制左移位运算符。左边的操作数的值向左移动由右操作数指定的位数 | A << 2 =240 也就是 1111 0000    |
| >>   | 二进制向右移位运算符。左边的操作数的值由右操作数指定的位数向右移动 | A >> 2 = 15 也就是 0000 1111    |

### 1.5 赋值运算符

| 运算符 | 描述                                                         | 示例                         |
| ------ | ------------------------------------------------------------ | ---------------------------- |
| =      | 简单的赋值操作符，分配值从右边的操作数左侧的操作数           | C = A + B 将分配A + B的值到C |
| +=     | 相加并赋值运算符，它增加了右操作数左操作数和分配结果左操作数 | C += A 相当于 C = C + A      |
| -=     | 减和赋值运算符，它减去右操作数从左侧的操作数和分配结果左操作数 | C -= A 相当于 C = C - A      |
| *=     | 乘法和赋值运算符，它乘以右边的操作数与左操作数和分配结果左操作数 | C *= A 相当于 C = C * A      |
| /=     | 除法赋值运算符，它把左操作数与右操作数和分配结果左操作数     | C /= A 相当于 C = C / A      |
| %=     | 模量和赋值运算符，它需要使用两个操作数的模量和分配结果左操作数 | C %= A 相当于 C = C % A      |
| <<=    | 左移位并赋值运算符                                           | C <<= 2 相同于 C = C << 2    |
| >>=    | 向右移位并赋值运算符                                         | C >>= 2 相同于 C = C >> 2    |
| &=     | 按位与赋值运算符                                             | C &= 2 相同于 C = C & 2      |
| ^=     | 按位异或并赋值运算符                                         | C ^= 2 相同于 C = C ^ 2      |
| \|=    | 按位或并赋值运算符                                           | C \|= 2 相同于 C = C \| 2    |

### 1.6优先级运算符优先级

有些运算符拥有较高的优先级，二元运算符的运算方向均是从左至右。下表列出了所有运算符以及它们的优先级，由上至下代表优先级由高到低：

| 优先级 | 运算符           |
| ------ | ---------------- |
| 7      | ~ ! ++ --        |
| 6      | * / % << >> & &^ |
| 5      | + -  ^           |
| 4      | == != < <= >= >  |
| 3      | <-               |
| 2      | &&               |
| 1      | \|\|             |

当然，你可以通过使用括号来临时提升某个表达式的整体运算优先级。




# 键盘输入和打印输出

## 一、打印输出

### 1.1 fmt包

fmt包实现了类似C语言printf和scanf的格式化I/O。格式化verb（'verb'）源自C语言但更简单。

详见官网fmt的API：https://golang.google.cn/pkg/fmt/

![fmtpackage](http://7xtcwd.com1.z0.glb.clouddn.com/fmtpackage.png)



### 1.2 导入包

```go
import "fmt"
```



### 1.3 常用打印函数

**打印：**

[func Print(a ...interface{}) (n int, err error)](https://golang.google.cn/pkg/fmt/#Print)

**格式化打印：**

[func Printf(format string, a ...interface{}) (n int, err error)](https://golang.google.cn/pkg/fmt/#Printf)

**打印后换行**

[func Println(a ...interface{}) (n int, err error)](https://golang.google.cn/pkg/fmt/#Println)



格式化打印中的常用占位符：

```
格式化打印占位符：
			%v,原样输出
			%T，打印类型
			%t,bool类型
			%s，字符串
			%f，浮点
			%d，10进制的整数
			%b，2进制的整数
			%o，8进制
			%x，%X，16进制
				%x：0-9，a-f
				%X：0-9，A-F
			%c，打印字符
			%p，打印地址
			。。。
```

示例代码：

```go
package main

import (
	"fmt"
)

func main() {
	a := 100           //int
	b := 3.14          //float64
	c := true          // bool
	d := "Hello World" //string
	e := `Ruby`        //string
	f := 'A'
	fmt.Printf("%T,%b\n", a, a)
	fmt.Printf("%T,%f\n", b, b)
	fmt.Printf("%T,%t\n", c, c)
	fmt.Printf("%T,%s\n", d, d)
	fmt.Printf("%T,%s\n", e, e)
	fmt.Printf("%T,%d,%c\n", f, f, f)
	fmt.Println("-----------------------")
	fmt.Printf("%v\n", a)
	fmt.Printf("%v\n", b)
	fmt.Printf("%v\n", c)
	fmt.Printf("%v\n", d)
	fmt.Printf("%v\n", e)
	fmt.Printf("%v\n", f)

}

```



运行结果：

![yunxing1](http://7xtcwd.com1.z0.glb.clouddn.com/yunxing1.png)



## 二、键盘输入

### 2.1 fmt包读取键盘输入

常用方法：

[func Scan(a ...interface{}) (n int, err error)](https://golang.google.cn/pkg/fmt/#Scan)

[func Scanf(format string, a ...interface{}) (n int, err error)](https://golang.google.cn/pkg/fmt/#Scanf)

[func Scanln(a ...interface{}) (n int, err error)](https://golang.google.cn/pkg/fmt/#Scanln)



```go
package main

import (
	"fmt"
)

func main() {
	var x int
	var y float64
	fmt.Println("请输入一个整数，一个浮点类型：")
	fmt.Scanln(&x,&y)//读取键盘的输入，通过操作地址，赋值给x和y   阻塞式
	fmt.Printf("x的数值：%d，y的数值：%f\n",x,y)

	fmt.Scanf("%d,%f",&x,&y)
	fmt.Printf("x:%d,y:%f\n",x,y)
}
```

运行结果：

![yunxing2](http://7xtcwd.com1.z0.glb.clouddn.com/yunxing2.png)



### 2.2 bufio包读取

https://golang.google.cn/pkg/bufio/



bufio包中都是IO操作的方法：

先创建Reader对象：

![bufio1](http://7xtcwd.com1.z0.glb.clouddn.com/bufio1.png)



然后就可以各种读取了：

![bufio2](http://7xtcwd.com1.z0.glb.clouddn.com/bufio2.png)



示例代码：

```go
package main

import (
	"fmt"
	"os"
	"bufio"
)

func main() {
	fmt.Println("请输入一个字符串：")
	reader := bufio.NewReader(os.Stdin)
	s1, _ := reader.ReadString('\n')
	fmt.Println("读到的数据：", s1)

}
```

运行效果：

![yunxing3](http://7xtcwd.com1.z0.glb.clouddn.com/yunxing3.png)



文章中的源代码：

https://github.com/rubyhan1314/go_foundation




# 条件语句

## If语句

语法格式：

```go
if 布尔表达式 {
   /* 在布尔表达式为 true 时执行 */
}
```

```go
if 布尔表达式 {
   /* 在布尔表达式为 true 时执行 */
} else {
  /* 在布尔表达式为 false 时执行 */
}
```

```go
if 布尔表达式1 {
   /* 在布尔表达式1为 true 时执行 */
} else if 布尔表达式2{
   /* 在布尔表达式1为 false ,布尔表达式2为true时执行 */
} else{
   /* 在上面两个布尔表达式都为false时，执行*/
}
```



示例代码：

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 10
 
   /* 使用 if 语句判断布尔表达式 */
   if a < 20 {
       /* 如果条件为 true 则执行以下语句 */
       fmt.Printf("a 小于 20\n" )
   }
   fmt.Printf("a 的值为 : %d\n", a)
}
```

如果其中包含一个可选的语句组件(在评估条件之前执行)，则还有一个变体。它的语法是

```go
if statement; condition {  
}

if condition{
    
    
}
```

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    if num := 10; num % 2 == 0 { //checks if number is even
        fmt.Println(num,"is even") 
    }  else {
        fmt.Println(num,"is odd")
    }
}
```

>需要注意的是，num的定义在if里，那么只能够在该if..else语句块中使用，否则编译器会报错的。







文章中的源代码：

https://github.com/rubyhan1314/go_foundation


## switch语句：“开关”

switch是一个条件语句，它计算表达式并将其与可能匹配的列表进行比较，并根据匹配执行代码块。它可以被认为是一种惯用的方式来写多个if else子句。

switch 语句用于基于不同条件执行不同动作，每一个 case 分支都是唯一的，从上直下逐一测试，直到匹配为止。
switch 语句执行的过程从上至下，直到找到匹配项，匹配项后面也不需要再加break。

而如果switch没有表达式，它会匹配true

Go里面switch默认相当于每个case最后带有break，匹配成功后不会自动向下执行其他case，而是跳出整个switch, 但是可以使用fallthrough强制执行后面的case代码。

变量 var1 可以是任何类型，而 val1 和 val2 则可以是同类型的任意值。类型不被局限于常量或整数，但必须是相同的类型；或者最终结果为相同类型的表达式。
您可以**同时测试多个可能符合条件的值，使用逗号分割它们**，例如：case val1, val2, val3。

```go
switch var1 {
    case val1:
        ...
    case val2:
        ...
    default:
        ...
}
```


示例代码：

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var grade string = "B"
   var marks int = 90

   switch marks {
      case 90: grade = "A"
      case 80: grade = "B"
      case 50,60,70 : grade = "C"  //case 后可以由多个数值
      default: grade = "D"  
   }

   switch {
      case grade == "A" :
         fmt.Printf("优秀!\n" )     
      case grade == "B", grade == "C" :
         fmt.Printf("良好\n" )      
      case grade == "D" :
         fmt.Printf("及格\n" )      
      case grade == "F":
         fmt.Printf("不及格\n" )
      default:
         fmt.Printf("差\n" );
   }
   fmt.Printf("你的等级是 %s\n", grade );      
}
```



## fallthrough

如需贯通后续的case，就添加fallthrough

```go
package main

import (
	"fmt"
)

type data [2]int

func main() {
	switch x := 5; x {
	default:
		fmt.Println(x)
	case 5:
		x += 10
		fmt.Println(x)
		fallthrough
	case 6:
		x += 20
		fmt.Println(x)

	}

}

```

运行结果：

```go
15
35
```



case中的表达式是可选的，可以省略。如果该表达式被省略，则被认为是switch true，并且每个case表达式都被计算为true，并执行相应的代码块。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    num := 75
    switch { // expression is omitted
    case num >= 0 && num <= 50:
        fmt.Println("num is greater than 0 and less than 50")
    case num >= 51 && num <= 100:
        fmt.Println("num is greater than 51 and less than 100")
    case num >= 101:
        fmt.Println("num is greater than 100")
    }

}
```



> switch的注意事项
>
> 1. case后的常量值不能重复
> 2. case后可以有多个常量值
> 3. fallthrough应该是某个case的最后一行。如果它出现在中间的某个地方，编译器就会抛出错误。

## Type Switch

switch 语句还可以被用于 type-switch 来判断某个 interface 变量中实际存储的变量类型。

```go
switch x.(type){
    case type:
       statement(s);      
    case type:
       statement(s); 
    /* 你可以定义任意个数的case */
    default: /* 可选 */
       statement(s);
}
```

```go
package main

import "fmt"

func main() {
   var x interface{}
     
   switch i := x.(type) {
      case nil:	  
         fmt.Printf(" x 的类型 :%T",i)                
      case int:	  
         fmt.Printf("x 是 int 型")                       
      case float64:
         fmt.Printf("x 是 float64 型")           
      case func(int) float64:
         fmt.Printf("x 是 func(int) 型")                      
      case bool, string:
         fmt.Printf("x 是 bool 或 string 型" )       
      default:
         fmt.Printf("未知型")     
   }   
}
```

运行结果：

```go
x 的类型 :<nil>
```



# 循环语句

循环语句表示条件满足，可以反复的执行某段代码。

for是唯一的循环语句。(Go没有while循环)

##2.1 For语句

语法结构：

```
for init; condition; post { }
```

> 初始化语句只执行一次。在初始化循环之后，将检查该条件。如果条件计算为true，那么{}中的循环体将被执行，然后是post语句。post语句将在循环的每次成功迭代之后执行。在执行post语句之后，该条件将被重新检查。如果它是正确的，循环将继续执行，否则循环终止。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    for i := 1; i <= 10; i++ {
        fmt.Printf(" %d",i)
    }
}
```

>在for循环中声明的变量仅在循环范围内可用。因此，i不能在外部访问循环。



**所有的三个组成部分，即初始化、条件和post都是可选的。**

```
for condition { }
```

效果与while相似

```
for { }
```

效果与for(;;) 一样

for 循环的 range 格式可以对 slice、map、数组、字符串等进行迭代循环

```
for key, value := range oldMap {
    newMap[key] = value
}
```

```go
package main

import "fmt"

func main() {

   var b int = 15
   var a int

   numbers := [6]int{1, 2, 3, 5} 

   /* for 循环 */
   for a := 0; a < 10; a++ {
      fmt.Printf("a 的值为: %d\n", a)
   }

   for a < b {
      a++
      fmt.Printf("a 的值为: %d\n", a)
      }

   for i,x:= range numbers {
      fmt.Printf("第 %d 位 x 的值 = %d\n", i,x)
   }   
}
```

运行结果：

```
a 的值为: 0
a 的值为: 1
a 的值为: 2
a 的值为: 3
a 的值为: 4
a 的值为: 5
a 的值为: 6
a 的值为: 7
a 的值为: 8
a 的值为: 9
a 的值为: 1
a 的值为: 2
a 的值为: 3
a 的值为: 4
a 的值为: 5
a 的值为: 6
a 的值为: 7
a 的值为: 8
a 的值为: 9
a 的值为: 10
a 的值为: 11
a 的值为: 12
a 的值为: 13
a 的值为: 14
a 的值为: 15
第 0 位 x 的值 = 1
第 1 位 x 的值 = 2
第 2 位 x 的值 = 3
第 3 位 x 的值 = 5
第 4 位 x 的值 = 0
第 5 位 x 的值 = 0
```



## 2.2 多层for循环

for循环中又有循环嵌套，就表示多层循环了。




# 跳出循环的语句

## 1、 break语句

break：跳出循环体。break语句用于在结束其正常执行之前突然终止for循环

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    for i := 1; i <= 10; i++ {
        if i > 5 {
            break //loop is terminated if i > 5
        }
        fmt.Printf("%d ", i)
    }
    fmt.Printf("\nline after for loop")
}
```

##  2、continue语句

continue：跳出一次循环。continue语句用于跳过for循环的当前迭代。在continue语句后面的for循环中的所有代码将不会在当前迭代中执行。循环将继续到下一个迭代。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    for i := 1; i <= 10; i++ {
        if i%2 == 0 {
            continue
        }
        fmt.Printf("%d ", i)
    }
}
```



# goto语句

goto：可以无条件地转移到过程中指定的行。

语法结构：

```go
goto label;
..
..
label: statement;
```



![goto1](http://7xtcwd.com1.z0.glb.clouddn.com/goto1.jpg)

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 10

   /* 循环 */
   LOOP: for a < 20 {
      if a == 15 {
         /* 跳过迭代 */
         a = a + 1
         goto LOOP
      }
      fmt.Printf("a的值为 : %d\n", a)
      a++     
   }  
}
```



统一错误处理
多处错误处理存在代码重复时是非常棘手的，例如：

```go
		err := firstCheckError()
    if err != nil {
        goto onExit
    }
    err = secondCheckError()
    if err != nil {
        goto onExit
    }
    fmt.Println("done")
    return
onExit:
    fmt.Println(err)
    exitProcess()



```


# 数组(Array)

## 1.1 什么是数组

Go 语言提供了数组类型的数据结构。
数组是具有相同唯一类型的一组已编号且长度固定的数据项序列，这种类型可以是任意的原始类型例如整形、字符串或者自定义类型。

数组元素可以通过索引（位置）来读取（或者修改），索引从0开始，第一个元素索引为 0，第二个索引为 1，以此类推。数组的下标取值范围是从0开始，到长度减1。

数组一旦定义后，大小不能更改。

## 1.2 数组的语法

**声明和初始化数组**

需要指明数组的大小和存储的数据类型。

```go
var variable_name [SIZE] variable_type
```

示例代码：

```go
var balance [10] float32
var balance = [5]float32{1000.0, 2.0, 3.4, 7.0, 50.0}
```

初始化数组中 {} 中的元素个数不能大于 [] 中的数字。
如果忽略 [] 中的数字不设置数组大小，Go 语言会根据元素的个数来设置数组的大小：

```go
var balance = []float32{1000.0, 2.0, 3.4, 7.0, 50.0}
```

```go
balance[4] = 50.0
```

数组的其他创建方式：

```go
  var a [4] float32 // 等价于：var arr2 = [4]float32{}
  fmt.Println(a) // [0 0 0 0]
  var b = [5] string{"ruby", "王二狗", "rose"}
  fmt.Println(b) // [ruby 王二狗 rose  ]
  var c = [5] int{'A', 'B', 'C', 'D', 'E'} // byte
  fmt.Println(c) // [65 66 67 68 69]
  d := [...] int{1,2,3,4,5}// 根据元素的个数，设置数组的大小
  fmt.Println(d)//[1 2 3 4 5]
  e := [5] int{4: 100} // [0 0 0 0 100]
  fmt.Println(e)
  f := [...] int{0: 1, 4: 1, 9: 1} // [1 0 0 0 1 0 0 0 0 1]
  fmt.Println(f)
```





**访问数组元素**

```go
float32 salary = balance[9]
```

示例代码：

```go
package main

import "fmt"

func main() {
   var n [10]int /* n 是一个长度为 10 的数组 */
   var i,j int

   /* 为数组 n 初始化元素 */         
   for i = 0; i < 10; i++ {
      n[i] = i + 100 /* 设置元素为 i + 100 */
   }

   /* 输出每个数组元素的值 */
   for j = 0; j < 10; j++ {
      fmt.Printf("Element[%d] = %d\n", j, n[j] )
   }
}
```

运行结果：

```go
Element[0] = 100
Element[1] = 101
Element[2] = 102
Element[3] = 103
Element[4] = 104
Element[5] = 105
Element[6] = 106
Element[7] = 107
Element[8] = 108
Element[9] = 109
```

**数组的长度**

通过将数组作为参数传递给len函数，可以获得数组的长度。

示例代码：

```go
package main

import "fmt"

func main() {  
    a := [...]float64{67.7, 89.8, 21, 78}
    fmt.Println("length of a is",len(a))

}
```

运行结果：

```
length of a is 4
```

您甚至可以忽略声明中数组的长度并将其替换为…让编译器为你找到长度。这是在下面的程序中完成的。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    a := [...]int{12, 78, 50} // ... makes the compiler determine the length
    fmt.Println(a)
}
```



遍历数组：

```go
package main

import "fmt"

func main() {  
    a := [...]float64{67.7, 89.8, 21, 78}
    for i := 0; i < len(a); i++ { //looping from 0 to the length of the array
        fmt.Printf("%d th element of a is %.2f\n", i, a[i])
    }
}
```



使用range遍历数组：

```go
package main

import "fmt"

func main() {  
    a := [...]float64{67.7, 89.8, 21, 78}
    sum := float64(0)
    for i, v := range a {//range returns both the index and value
        fmt.Printf("%d the element of a is %.2f\n", i, v)
        sum += v
    }
    fmt.Println("\nsum of all elements of a",sum)
}
```

如果您只需要值并希望忽略索引，那么可以通过使用_ blank标识符替换索引来实现这一点。

```go
for _, v := range a { //ignores index  
}
```



## 1.3 多维数组

Go 语言支持多维数组，以下为常用的多维数组声明语法方式：

```go
var variable_name [SIZE1][SIZE2]...[SIZEN] variable_type
```

```go
var threedim [5][10][4]int
```

三维数组

```go
a = [3][4]int{  
 {0, 1, 2, 3} ,   /*  第一行索引为 0 */
 {4, 5, 6, 7} ,   /*  第二行索引为 1 */
 {8, 9, 10, 11}   /*  第三行索引为 2 */
}
```

```go
int val = a[2][3]
```

## 1.4 数组是值类型

数组是值类型
Go中的数组是值类型，而不是引用类型。这意味着当它们被分配给一个新变量时，将把原始数组的副本分配给新变量。如果对新变量进行了更改，则不会在原始数组中反映。

```go
package main

import "fmt"

func main() {  
    a := [...]string{"USA", "China", "India", "Germany", "France"}
    b := a // a copy of a is assigned to b
    b[0] = "Singapore"
    fmt.Println("a is ", a)
    fmt.Println("b is ", b) 
}
```

运行结果：

```
a is [USA China India Germany France]  
b is [Singapore China India Germany France] 
```

数组的大小是类型的一部分。因此[5]int和[25]int是不同的类型。因此，数组不能被调整大小。不要担心这个限制，因为切片的存在是为了解决这个问题。

```go
package main

func main() {  
    a := [3]int{5, 78, 8}
    var b [5]int
    b = a //not possible since [3]int and [5]int are distinct types
}
```



# 切片(Slice)

## 1.1 什么是切片

Go 语言切片是对数组的抽象。
Go 数组的长度不可改变，在特定场景中这样的集合就不太适用，Go中提供了一种灵活，功能强悍的内置类型切片("动态数组"),与数组相比切片的长度是不固定的，可以追加元素，在追加时可能使切片的容量增大

切片是一种方便、灵活且强大的包装器。切片本身没有任何数据。它们只是对现有数组的引用。

切片与数组相比，不需要设定长度，在[]中不用设定值，相对来说比较自由

从概念上面来说slice像一个结构体，这个结构体包含了三个元素： 

1. 指针，指向数组中slice指定的开始位置
2. 长度，即slice的长度
3. 最大长度，也就是slice开始位置到数组的最后位置的长度

## 1.2 切片的语法

**定义切片**

```go
var identifier []type
```

切片不需要说明长度。
或使用make()函数来创建切片:

```go
var slice1 []type = make([]type, len)
也可以简写为
slice1 := make([]type, len)
```

```go
make([]T, length, capacity)
```

**初始化**

```go
s[0] = 1
s[1] = 2
s[2] = 3
```

```go
s :=[] int {1,2,3 } 
```

```go
s := arr[startIndex:endIndex] 
```

将arr中从下标startIndex到endIndex-1 下的元素创建为一个新的切片（**前闭后开**），长度为endIndex-startIndex

```go
s := arr[startIndex:] 
```

缺省endIndex时将表示一直到arr的最后一个元素

```go
s := arr[:endIndex] 
```

缺省startIndex时将表示从arr的第一个元素开始

```go
package main

import (  
    "fmt"
)

func main() {  
    a := [5]int{76, 77, 78, 79, 80}
    var b []int = a[1:4] //creates a slice from a[1] to a[3]
    fmt.Println(b)
}
```

## 1.3 修改切片

slice没有自己的任何数据。它只是底层数组的一个表示。对slice所做的任何修改都将反映在底层数组中。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    darr := [...]int{57, 89, 90, 82, 100, 78, 67, 69, 59}
    dslice := darr[2:5]
    fmt.Println("array before",darr)
    for i := range dslice {
        dslice[i]++
    }
    fmt.Println("array after",darr) 
}
```

运行结果：

```
array before [57 89 90 82 100 78 67 69 59]  
array after [57 89 91 83 101 78 67 69 59]  
```

当多个片共享相同的底层数组时，每个元素所做的更改将在数组中反映出来。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    numa := [3]int{78, 79 ,80}
    nums1 := numa[:] //creates a slice which contains all elements of the array
    nums2 := numa[:]
    fmt.Println("array before change 1",numa)
    nums1[0] = 100
    fmt.Println("array after modification to slice nums1", numa)
    nums2[1] = 101
    fmt.Println("array after modification to slice nums2", numa)
}
```

运行结果：

```
array before change 1 [78 79 80]  
array after modification to slice nums1 [100 79 80]  
array after modification to slice nums2 [100 101 80]  
```



## 1.4 len() 和 cap() 函数

切片的长度是切片中元素的数量。切片的容量是从创建切片的索引开始的底层数组中元素的数量。

切片是可索引的，并且可以由 len() 方法获取长度
切片提供了计算容量的方法 cap() 可以测量切片最长可以达到多少

```go
package main

import "fmt"

func main() {
   var numbers = make([]int,3,5)

   printSlice(numbers)
}

func printSlice(x []int){
   fmt.Printf("len=%d cap=%d slice=%v\n",len(x),cap(x),x)
}
```

运行结果

```go
len=3 cap=5 slice=[0 0 0]
```

**空切片**

一个切片在未初始化之前默认为 nil，长度为 0

```go
package main

import "fmt"

func main() {
   var numbers []int

   printSlice(numbers)

   if(numbers == nil){
      fmt.Printf("切片是空的")
   }
}

func printSlice(x []int){
   fmt.Printf("len=%d cap=%d slice=%v\n",len(x),cap(x),x)
}
```

运行结果

```go
len=0 cap=0 slice=[]
切片是空的
```

```go
package main

import "fmt"

func main() {
   /* 创建切片 */
   numbers := []int{0,1,2,3,4,5,6,7,8}   
   printSlice(numbers)

   /* 打印原始切片 */
   fmt.Println("numbers ==", numbers)

   /* 打印子切片从索引1(包含) 到索引4(不包含)*/
   fmt.Println("numbers[1:4] ==", numbers[1:4])

   /* 默认下限为 0*/
   fmt.Println("numbers[:3] ==", numbers[:3])

   /* 默认上限为 len(s)*/
   fmt.Println("numbers[4:] ==", numbers[4:])

   numbers1 := make([]int,0,5)
   printSlice(numbers1)

   /* 打印子切片从索引  0(包含) 到索引 2(不包含) */
   number2 := numbers[:2]
   printSlice(number2)

   /* 打印子切片从索引 2(包含) 到索引 5(不包含) */
   number3 := numbers[2:5]
   printSlice(number3)

}

func printSlice(x []int){
   fmt.Printf("len=%d cap=%d slice=%v\n",len(x),cap(x),x)
}
```

运行结果

```go
len=9 cap=9 slice=[0 1 2 3 4 5 6 7 8]
numbers == [0 1 2 3 4 5 6 7 8]
numbers[1:4] == [1 2 3]
numbers[:3] == [0 1 2]
numbers[4:] == [4 5 6 7 8]
len=0 cap=5 slice=[]
len=2 cap=9 slice=[0 1]
len=3 cap=7 slice=[2 3 4]
```

##1.5 append() 和 copy() 函数 

append 向slice里面追加一个或者多个元素，然后返回一个和slice一样类型的slice
copy 函数copy从源slice的src中复制元素到目标dst，并且返回复制的元素的个数

append函数会改变slice所引用的数组的内容，从而影响到引用同一数组的其它slice。 但当slice中没有剩
余空间（即(cap-len) == 0）时，此时将动态分配新的数组空间。返回的slice数组指针将指向这个空间，而原
数组的内容将保持不变；其它引用此数组的slice则不受影响

下面的代码描述了从拷贝切片的 copy 方法和向切片追加新元素的 append 方法

```go
package main

import "fmt"

func main() {
   var numbers []int
   printSlice(numbers)

   /* 允许追加空切片 */
   numbers = append(numbers, 0)
   printSlice(numbers)

   /* 向切片添加一个元素 */
   numbers = append(numbers, 1)
   printSlice(numbers)

   /* 同时添加多个元素 */
   numbers = append(numbers, 2,3,4)
   printSlice(numbers)

   /* 创建切片 numbers1 是之前切片的两倍容量*/
   numbers1 := make([]int, len(numbers), (cap(numbers))*2)

   /* 拷贝 numbers 的内容到 numbers1 */
   copy(numbers1,numbers)
   printSlice(numbers1)   
}

func printSlice(x []int){
   fmt.Printf("len=%d cap=%d slice=%v\n",len(x),cap(x),x)
}
```

运行结果

```go
len=0 cap=0 slice=[]
len=1 cap=2 slice=[0]
len=2 cap=2 slice=[0 1]
len=5 cap=8 slice=[0 1 2 3 4]
len=5 cap=12 slice=[0 1 2 3 4]
```

> numbers1与numbers两者不存在联系，numbers发生变化时，numbers1是不会随着变化的。也就是说copy方法是不会建立两个切片的联系的




# 集合(Map)

## 1.1 什么是Map

张三：13910101201

李四：13801010134





map是Go中的内置类型，它将一个值与一个键关联起来。可以使用相应的键检索值。

Map 是一种无序的键值对的集合。Map 最重要的一点是通过 key 来快速检索数据，key 类似于索引，指向数据的值
Map 是一种集合，所以我们可以像迭代数组和切片那样迭代它。不过，Map 是无序的，我们无法决定它的返回顺序，这是因为 Map 是使用 hash 表来实现的，也是引用类型

使用map过程中需要注意的几点： 

- map是无序的，每次打印出来的map都会不一样，它不能通过index获取，而必须通过key获取
- map的长度是不固定的，也就是和slice一样，也是一种引用类型
- 内置的len函数同样适用于map，返回map拥有的key的数量 
- map的key可以是所有可比较的类型，如布尔型、整数型、浮点型、复杂型、字符串型……也可以键。

## 1.2  Map的使用

### 1.2.1 使用make()创建map

可以使用内建函数 make 也可以使用 map 关键字来定义 Map:

```go
/* 声明变量，默认 map 是 nil */
var map_variable map[key_data_type]value_data_type

/* 使用 make 函数 */
map_variable = make(map[key_data_type]value_data_type)
```

```go
rating := map[string]float32 {"C":5, "Go":4.5, "Python":4.5, "C++":2 }
```

如果不初始化 map，那么就会创建一个 nil map。nil map 不能用来存放键值对

```go
package main

import "fmt"

func main() {
   var countryCapitalMap map[string]string
   /* 创建集合 */
   countryCapitalMap = make(map[string]string)
   
   /* map 插入 key-value 对，各个国家对应的首都 */
   countryCapitalMap["France"] = "Paris"
   countryCapitalMap["Italy"] = "Rome"
   countryCapitalMap["Japan"] = "Tokyo"
   countryCapitalMap["India"] = "New Delhi"
   
   /* 使用 key 输出 map 值 */
   for country := range countryCapitalMap {
      fmt.Println("Capital of",country,"is",countryCapitalMap[country])
   }
   
   /* 查看元素在集合中是否存在 */
   captial, ok := countryCapitalMap["United States"]
   /* 如果 ok 是 true, 则存在，否则不存在 */
   if(ok){
      fmt.Println("Capital of United States is", captial)  
   }else {
      fmt.Println("Capital of United States is not present") 
   }
}
```

运行结果：

```go
Capital of France is Paris
Capital of Italy is Rome
Capital of Japan is Tokyo
Capital of India is New Delhi
Capital of United States is not present
```

### 1.2.2 delete() 函数

delete(map, key) 函数用于删除集合的元素, 参数为 map 和其对应的 key。删除函数不返回任何值。

```go
package main

import "fmt"

func main() {   
   /* 创建 map */
   countryCapitalMap := map[string] string {"France":"Paris","Italy":"Rome","Japan":"Tokyo","India":"New Delhi"}
   
   fmt.Println("原始 map")   
   
   /* 打印 map */
   for country := range countryCapitalMap {
      fmt.Println("Capital of",country,"is",countryCapitalMap[country])
   }
   
   /* 删除元素 */
   delete(countryCapitalMap,"France");
   fmt.Println("Entry for France is deleted")  
   
   fmt.Println("删除元素后 map")   
   
   /* 打印 map */
   for country := range countryCapitalMap {
      fmt.Println("Capital of",country,"is",countryCapitalMap[country])
   }
}
```

运行结果：

```go
原始 map
Capital of France is Paris
Capital of Italy is Rome
Capital of Japan is Tokyo
Capital of India is New Delhi
Entry for France is deleted
删除元素后 map
Capital of Italy is Rome
Capital of Japan is Tokyo
Capital of India is New Delhi
```

### 1.2.3 ok-idiom

我们可以通过key获取map中对应的value值。语法为：

```go
map[key] 
```

但是当key如果不存在的时候，我们会得到该value值类型的默认值，比如string类型得到空字符串，int类型得到0。但是程序不会报错。

所以我们可以使用ok-idiom获取值，可知道key/value是否存在

```go
value, ok := map[key] 
```

示例代码：

```go
package main

import (
	"fmt"
)

func main() {
	m := make(map[string]int)
	m["a"] = 1
	x, ok := m["b"]
	fmt.Println(x, ok)
	x, ok = m["a"]
	fmt.Println(x, ok)
}

```

运行结果：

```go
0 false
1 true
```

### 1.2.4 map的长度

使用len函数可以确定map的长度。

```go
len(map)  // 可以得到map的长度
```

### 1.2.5 map是引用类型的

与切片相似，映射是引用类型。当将映射分配给一个新变量时，它们都指向相同的内部数据结构。因此，一个的变化会反映另一个。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    personSalary := map[string]int{
        "steve": 12000,
        "jamie": 15000,
    }
    personSalary["mike"] = 9000
    fmt.Println("Original person salary", personSalary)
    newPersonSalary := personSalary
    newPersonSalary["mike"] = 18000
    fmt.Println("Person salary changed", personSalary)

}
```

运行结果：

```
Original person salary map[steve:12000 jamie:15000 mike:9000]  
Person salary changed map[steve:12000 jamie:15000 mike:18000] 
```

>map不能使用==操作符进行比较。==只能用来检查map是否为空。否则会报错：invalid operation: map1 == map2 (map can only be comparedto nil)



# 字符串(string)

## 1.1 什么是string

Go中的字符串是一个字节的切片。可以通过将其内容封装在“”中来创建字符串。Go中的字符串是Unicode兼容的，并且是UTF-8编码的。

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    name := "Hello World"
    fmt.Println(name)
}
```



## 1.2  string的使用

### 1.2.1 访问字符串中的单个字节

```go
package main

import (  
    "fmt"
)

func main() {  
    name := "Hello World"
    for i:= 0; i < len(s); i++ {
        fmt.Printf("%d ", s[i])
    }
    fmt.Printf("\n")
    for i:= 0; i < len(s); i++ {
        fmt.Printf("%c ",s[i])
    }
}
```

运行结果：

72 101 108 108 111 32 87 111 114 108 100 
H e l l o   W o r l d 




# 函数

## 1.1 什么是函数

函数是执行特定任务的代码块。

## 1.2 函数的声明

go语言至少有一个main函数

语法格式：

```go
func funcName(parametername type1, parametername type2) (output1 type1, output2 type2) {
//这里是处理逻辑代码
//返回多个值
return value1, value2
}
```

- func：函数由 func 开始声明
- funcName：函数名称，函数名和参数列表一起构成了函数签名。
- parametername type：参数列表，参数就像一个占位符，当函数被调用时，你可以将值传递给参数，这个值被称为实际参数。参数列表指定的是参数类型、顺序、及参数个数。参数是可选的，也就是说函数也可以不包含参数。
- output1 type1, output2 type2：返回类型，函数返回一列值。return_types 是该列值的数据类型。有些功能不需要返回值，这种情况下 return_types 不是必须的。
- 上面返回值声明了两个变量output1和output2，如果你不想声明也可以，直接就两个类型。
- 如果只有一个返回值且不声明返回值变量，那么你可以省略包括返回值的括号（即一个返回值可以不声明返回类型）
- 函数体：函数定义的代码集合。

## 1.3 函数的使用

示例代码：

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 100
   var b int = 200
   var ret int

   /* 调用函数并返回最大值 */
   ret = max(a, b)

   fmt.Printf( "最大值是 : %d\n", ret )
}

/* 函数返回两个数的最大值 */
func max(num1, num2 int) int {
   /* 定义局部变量 */
   var result int

   if (num1 > num2) {
      result = num1
   } else {
      result = num2
   }
   return result 
}
```

运行结果：

```go
最大值是 : 200
```


## 函数的参数

## 1.1 参数的使用

形式参数：定义函数时，用于接收外部传入的数据，叫做形式参数，简称形参。

实际参数：调用函数时，传给形参的实际的数据，叫做实际参数，简称实参。

函数调用：

​	A：函数名称必须匹配

​	B：实参与形参必须一一对应：顺序，个数，类型

## 1.2 可变参

Go函数支持变参。接受变参的函数是有着不定数量的参数的。为了做到这点，首先需要定义函数使其接受变参：

```go
func myfunc(arg ...int) {}
```

`arg ...int`告诉Go这个函数接受不定数量的参数。注意，这些参数的类型全部是int。在函数体中，变量arg是一个int的slice：

```go
for _, n := range arg {
fmt.Printf("And the number is: %d\n", n)
}
```

## 1.3 参数传递

go语言函数的参数也是存在**值传递**和**引用传递**

函数运用场景

**值传递**

```go
package main

import (
   "fmt"
   "math"
)

func main(){
   /* 声明函数变量 */
   getSquareRoot := func(x float64) float64 {
      return math.Sqrt(x)
   }

   /* 使用函数 */
   fmt.Println(getSquareRoot(9))

}
```

**引用传递**

这就牵扯到了所谓的指针。我们知道，变量在内存中是存放于一定地址上的，修改变量实际是修改变量地址处的内
存。只有add1函数知道x变量所在的地址，才能修改x变量的值。所以我们需要将x所在地址&x传入函数，并将函数的参数的类型由int改为*int，即改为指针类型，才能在函数中修改x变量的值。此时参数仍然是按copy传递的，只是copy的是一个指针。请看下面的例子

```go
package main
import "fmt"
//简单的一个函数，实现了参数+1的操作
func add1(a *int) int { // 请注意，
*a = *a+1 // 修改了a的值
return *a // 返回新值
} f
unc main() {
x := 3
fmt.Println("x = ", x) // 应该输出 "x = 3"
x1 := add1(&x) // 调用 add1(&x) 传x的地址
fmt.Println("x+1 = ", x1) // 应该输出 "x+1 = 4"
fmt.Println("x = ", x) // 应该输出 "x = 4"
}
```

- 传指针使得多个函数能操作同一个对象。
- 传指针比较轻量级 (8bytes),只是传内存地址，我们可以用指针传递体积大的结构体。如果用参数值传递的话, 在每次copy上面就会花费相对较多的系统开销（内存和时间）。所以当你要传递大的结构体的时候，用指针是一个明智的选择。
- **Go语言中slice，map这三种类型的实现机制类似指针**，所以可以直接传递，而不用取地址后传递指针。（注：若函数需改变slice的长度，则仍需要取地址传递指针）



## 函数的返回值

## 1.1 什么是函数的返回值

一个函数被调用后，返回给调用处的执行结果，叫做函数的返回值。

调用处需要使用变量接收该结果

## 1.2 一个函数可以返回多个值

一个函数可以没有返回值，也可以有一个返回值，也可以有返回多个值。

```go
package main

import "fmt"

func swap(x, y string) (string, string) {
   return y, x
}

func main() {
   a, b := swap("Mahesh", "Kumar")
   fmt.Println(a, b)
}
```

```go
func SumAndProduct(A, B int) (add int, Multiplied int) {
add = A+B
Multiplied = A*B
return
}
```
## 1.3 空白标识符

_是Go中的空白标识符。它可以代替任何类型的任何值。让我们看看这个空白标识符的用法。

比如rectProps函数返回的结果是面积和周长，如果我们只要面积，不要周长，就可以使用空白标识符。

示例代码：

```go
package main

import (  
    "fmt"
)

func rectProps(length, width float64) (float64, float64) {  
    var area = length * width
    var perimeter = (length + width) * 2
    return area, perimeter
}
func main() {  
    area, _ := rectProps(10.8, 5.6) // perimeter is discarded
    fmt.Printf("Area %f ", area)
}
```



# defer


## 1.1 延迟是什么?

即延迟（defer）语句，延迟语句被用于执行一个函数调用，在这个函数之前，延迟语句返回。

## 1.2 延迟函数

你可以在函数中添加多个defer语句。当函数执行到最后时，这些defer语句会按照逆序执行，最后该函数返回。特别是当你在进行一些打开资源的操作时，遇到错误需要提前返回，在返回前你需要关闭相应的资源，不然很容易造成资源泄露等问题

- 如果有很多调用defer，那么defer是采用`后进先出`模式
- 在离开所在的方法时，执行（报错的时候也会执行）

```go
func ReadWrite() bool {
    file.Open("file")
    defer file.Close()
    if failureX {
          return false
    } i
    f failureY {
          return false
    } 
    return true
}
```

最后才执行`file.Close()`

示例代码：

```go
package main

import "fmt"

func main() {
	a := 1
	b := 2
	defer fmt.Println(b)
	fmt.Println(a)
}
```

运行结果：

```go
1
2
```

示例代码：

```go
package main

import (  
    "fmt"
)

func finished() {  
    fmt.Println("Finished finding largest")
}

func largest(nums []int) {  
    defer finished()    
    fmt.Println("Started finding largest")
    max := nums[0]
    for _, v := range nums {
        if v > max {
            max = v
        }
    }
    fmt.Println("Largest number in", nums, "is", max)
}

func main() {  
    nums := []int{78, 109, 2, 563, 300}
    largest(nums)
}
```

运行结果：

```
Started finding largest  
Largest number in [78 109 2 563 300] is 563  
Finished finding largest 
```

## 1.3 延迟方法

延迟并不仅仅局限于函数。延迟一个方法调用也是完全合法的。让我们编写一个小程序来测试这个。

示例代码：

```go
package main

import (  
    "fmt"
)


type person struct {  
    firstName string
    lastName string
}

func (p person) fullName() {  
    fmt.Printf("%s %s",p.firstName,p.lastName)
}

func main() {  
    p := person {
        firstName: "John",
        lastName: "Smith",
    }
    defer p.fullName()
    fmt.Printf("Welcome ")  
}
```

运行结果：

```
Welcome John Smith 
```

## 1.4 延迟参数

延迟函数的参数在执行延迟语句时被执行，而不是在执行实际的函数调用时执行。

让我们通过一个例子来理解这个问题。

示例代码：

```go
package main

import (  
    "fmt"
)

func printA(a int) {  
    fmt.Println("value of a in deferred function", a)
}
func main() {  
    a := 5
    defer printA(a)
    a = 10
    fmt.Println("value of a before deferred function call", a)

}
```

运行结果：

```
value of a before deferred function call 10  
value of a in deferred function 5 
```

## 1.5 堆栈的推迟

当一个函数有多个延迟调用时，它们被添加到一个堆栈中，并在Last In First Out（LIFO）后进先出的顺序中执行。

我们将编写一个小程序，它使用一堆defers打印一个字符串。示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    name := "Naveen"
    fmt.Printf("Orignal String: %s\n", string(name))
    fmt.Printf("Reversed String: ")
    for _, v := range []rune(name) {
        defer fmt.Printf("%c", v)
    }
}
```

运行结果：

```
Orignal String: Naveen  
Reversed String: neevaN 
```



## 1.6defer注意点

```
defer函数：
当外围函数中的语句正常执行完毕时，只有其中所有的延迟函数都执行完毕，外围函数才会真正的结束执行。
当执行外围函数中的return语句时，只有其中所有的延迟函数都执行完毕后，外围函数才会真正返回。
当外围函数中的代码引发运行恐慌时，只有其中所有的延迟函数都执行完毕后，该运行时恐慌才会真正被扩展至调用函数。
```



# 指针

## 1.1 指针的概念

指针是存储另一个变量的内存地址的变量。

我们都知道，变量是一种使用方便的占位符，用于引用计算机内存地址。

一个指针变量可以指向任何一个值的内存地址它指向那个值的内存地址。

 ![pointer1](http://7xtcwd.com1.z0.glb.clouddn.com/pointer1.png)

在上面的图中，变量b的值为156，存储在内存地址0x1040a124。变量a持有b的地址，现在a被认为指向b。

## 1.2 获取变量的地址

Go 语言的取地址符是 &，放到一个变量前使用就会返回相应变量的内存地址。

```go
package main

import "fmt"

func main() {
   var a int = 10   

   fmt.Printf("变量的地址: %x\n", &a  )
}
```

运行结果：

```go
变量的地址: 20818a220
```

## 1.3 声明指针

声明指针，*T是指针变量的类型，它指向T类型的值。

```go
var var_name *var-type
```

var-type 为指针类型，var_name 为指针变量名，* 号用于指定变量是作为一个指针。

```go
var ip *int        /* 指向整型*/
var fp *float32    /* 指向浮点型 */
```

示例代码：

```go
package main

import "fmt"

func main() {
   var a int= 20   /* 声明实际变量 */
   var ip *int        /* 声明指针变量 */

   ip = &a  /* 指针变量的存储地址 */

   fmt.Printf("a 变量的地址是: %x\n", &a  )

   /* 指针变量的存储地址 */
   fmt.Printf("ip 变量的存储地址: %x\n", ip )

   /* 使用指针访问值 */
   fmt.Printf("*ip 变量的值: %d\n", *ip )
}
```

运行结果：

```go
a 变量的地址是: 20818a220
ip 变量的存储地址: 20818a220
*ip 变量的值: 20
```

示例代码：

```go
package main

import "fmt"

type name int8
type first struct {
	a int
	b bool
	name
}

func main() {
	a := new(first)
	a.a = 1
	a.name = 11
	fmt.Println(a.b, a.a, a.name)
}
```

运行结果：

```go
false 1 11
```

> 未初始化的变量自动赋上初始值

```go
package main

import "fmt"

type name int8
type first struct {
	a int
	b bool
	name
}

func main() {
	var a = first{1, false, 2}
	var b *first = &a
	fmt.Println(a.b, a.a, a.name, &a, b.a, &b, (*b).a)
}
```

运行结果：

```go
false 1 2 &{1 false 2} 1 0xc042068018 1
```

> 获取指针地址在指针变量前加&的方式

## 1.4 空指针

**Go 空指针**
当一个指针被定义后没有分配到任何变量时，它的值为 nil。
nil 指针也称为空指针。
nil在概念上和其它语言的null、None、nil、NULL一样，都指代零值或空值。
一个指针变量通常缩写为 ptr。

空指针判断：

```go
if(ptr != nil)     /* ptr 不是空指针 */
if(ptr == nil)    /* ptr 是空指针 */
```

## 1.5 获取指针的值

获取一个指针意味着访问指针指向的变量的值。语法是：*a

示例代码：

```go
package main  
import (  
    "fmt"
)

func main() {  
    b := 255
    a := &b
    fmt.Println("address of b is", a)
    fmt.Println("value of b is", *a)
}
```

## 1.6 操作指针改变变量的数值

示例代码：

```go
package main

import (  
    "fmt"
)

func main() {  
    b := 255
    a := &b
    fmt.Println("address of b is", a)
    fmt.Println("value of b is", *a)
    *a++
    fmt.Println("new value of b is", b)
}
```

运行结果

```
address of b is 0x1040a124  
value of b is 255  
new value of b is 256  
```



## 1.7 使用指针传递函数的参数

示例代码

```go
package main

import (  
    "fmt"
)

func change(val *int) {  
    *val = 55
}
func main() {  
    a := 58
    fmt.Println("value of a before function call is",a)
    b := &a
    change(b)
    fmt.Println("value of a after function call is", a)
}
```

运行结果

```
value of a before function call is 58  
value of a after function call is 55  
```

**不要将一个指向数组的指针传递给函数。使用切片。**

假设我们想对函数内的数组进行一些修改，并且对调用者可以看到函数内的数组所做的更改。一种方法是将一个指向数组的指针传递给函数。

```go
package main

import (  
    "fmt"
)

func modify(arr *[3]int) {  
    (*arr)[0] = 90
}

func main() {  
    a := [3]int{89, 90, 91}
    modify(&a)
    fmt.Println(a)
}
```

运行结果

```
[90 90 91]
```

示例代码：

```go
package main

import (  
    "fmt"
)

func modify(arr *[3]int) {  
    arr[0] = 90
}

func main() {  
    a := [3]int{89, 90, 91}
    modify(&a)
    fmt.Println(a)
}
```

运行结果

```
[90 90 91]
```

**虽然将指针传递给一个数组作为函数的参数并对其进行修改，但这并不是实现这一目标的惯用方法。我们有切片。**

示例代码：

```go
package main

import (  
    "fmt"
)

func modify(sls []int) {  
    sls[0] = 90
}

func main() {  
    a := [3]int{89, 90, 91}
    modify(a[:])
    fmt.Println(a)
}
```

运行结果：

```
[90 90 91]
```



>Go不支持指针算法。
>
>package main
>
>func main() {  
>    b := [...]int{109, 110, 111}
>    p := &b
>    p++
>}
>
>nvalid operation: p++ (non-numeric type *[3]int)



**指针数组**

```go
package main

import "fmt"

const MAX int = 3

func main() {

   a := []int{10,100,200}
   var i int

   for i = 0; i < MAX; i++ {
      fmt.Printf("a[%d] = %d\n", i, a[i] )
   }
}
```

`结果`

```go
a[0] = 10
a[1] = 100
a[2] = 200
```

有一种情况，我们可能需要保存数组，这样我们就需要使用到指针。

```go
package main

import "fmt"

const MAX int = 3

func main() {
   a := []int{10,100,200}
   var i int
   var ptr [MAX]*int;

   for  i = 0; i < MAX; i++ {
      ptr[i] = &a[i] /* 整数地址赋值给指针数组 */
   }

   for  i = 0; i < MAX; i++ {
      fmt.Printf("a[%d] = %d\n", i,*ptr[i] )
   }
}
```

`结果`

```go
a[0] = 10
a[1] = 100
a[2] = 200
```

## 1.8 指针的指针

**指针的指针**

如果一个指针变量存放的又是另一个指针变量的地址，则称这个指针变量为指向指针的指针变量。

```go
var ptr **int;
```

```go
package main

import "fmt"

func main() {

   var a int
   var ptr *int
   var pptr **int

   a = 3000

   /* 指针 ptr 地址 */
   ptr = &a

   /* 指向指针 ptr 地址 */
   pptr = &ptr

   /* 获取 pptr 的值 */
   fmt.Printf("变量 a = %d\n", a )
   fmt.Printf("指针变量 *ptr = %d\n", *ptr )
   fmt.Printf("指向指针的指针变量 **pptr = %d\n", **pptr)
}
```

`结果`

```go
变量 a = 3000
指针变量 *ptr = 3000
指向指针的指针变量 **pptr = 3000
```

**指针作为函数参数**

```go
package main

import "fmt"

func main() {
   /* 定义局部变量 */
   var a int = 100
   var b int= 200

   fmt.Printf("交换前 a 的值 : %d\n", a )
   fmt.Printf("交换前 b 的值 : %d\n", b )

   /* 调用函数用于交换值
   * &a 指向 a 变量的地址
   * &b 指向 b 变量的地址
   */
   swap(&a, &b);

   fmt.Printf("交换后 a 的值 : %d\n", a )
   fmt.Printf("交换后 b 的值 : %d\n", b )
}

func swap(x *int, y *int) {
   var temp int
   temp = *x    /* 保存 x 地址的值 */
   *x = *y      /* 将 y 赋值给 x */
   *y = temp    /* 将 temp 赋值给 y */
}
```

`结果`

```go
交换前 a 的值 : 100
交换前 b 的值 : 200
交换后 a 的值 : 200
交换后 b 的值 : 100
```



# 结构体


## 1.1 什么是结构体

Go 语言中数组可以存储同一类型的数据，但在结构体中我们可以为不同项定义不同的数据类型。
结构体是由一系列具有相同类型或不同类型的数据构成的数据集合。

## 1.2 结构体的定义和初始化

```go
type struct_variable_type struct {
   member definition;
   member definition;
   ...
   member definition;
}
```

一旦定义了结构体类型，它就能用于变量的声明

```go
variable_name := structure_variable_type {value1, value2...valuen}
```

**初始化结构体**

```go
// 1.按照顺序提供初始化值
P := person{"Tom", 25}
// 2.通过field:value的方式初始化，这样可以任意顺序
P := person{age:24, name:"Tom"}
// 3.new方式,未设置初始值的，会赋予类型的默认初始值
p := new(person)
p.age=24
```

## 1.3 结构体的访问

访问结构体成员(访问结构的各个字段)

通过点.操作符用于访问结构的各个字段。

```go
package main

import "fmt"

type Books struct {
   title string
   author string
   subject string
   book_id int
}

func main() {
   var Book1 Books        /* 声明 Book1 为 Books 类型 */
   var Book2 Books        /* 声明 Book2 为 Books 类型 */

   /* book 1 描述 */
   Book1.title = "Go 语言"
   Book1.author = "www.runoob.com"
   Book1.subject = "Go 语言教程"
   Book1.book_id = 6495407

   /* book 2 描述 */
   Book2.title = "Python 教程"
   Book2.author = "www.runoob.com"
   Book2.subject = "Python 语言教程"
   Book2.book_id = 6495700

   /* 打印 Book1 信息 */
   fmt.Printf( "Book 1 title : %s\n", Book1.title)
   fmt.Printf( "Book 1 author : %s\n", Book1.author)
   fmt.Printf( "Book 1 subject : %s\n", Book1.subject)
   fmt.Printf( "Book 1 book_id : %d\n", Book1.book_id)

   /* 打印 Book2 信息 */
   fmt.Printf( "Book 2 title : %s\n", Book2.title)
   fmt.Printf( "Book 2 author : %s\n", Book2.author)
   fmt.Printf( "Book 2 subject : %s\n", Book2.subject)
   fmt.Printf( "Book 2 book_id : %d\n", Book2.book_id)
}
```

运行结果：

```go
Book 1 title : Go 语言
Book 1 author : www.runoob.com
Book 1 subject : Go 语言教程
Book 1 book_id : 6495407
Book 2 title : Python 教程
Book 2 author : www.runoob.com
Book 2 subject : Python 语言教程
Book 2 book_id : 6495700
```

## 1.4 结构体指针

指针指向一个结构体
也可以创建指向结构的指针。

**结构体指针**

```go
var struct_pointer *Books
```

以上定义的指针变量可以存储结构体变量的地址。查看结构体变量地址，可以将 & 符号放置于结构体变量前

```go
struct_pointer = &Book1;
```

使用结构体指针访问结构体成员，使用 "." 操作符

```go
struct_pointer.title;
```

```go
package main

import "fmt"

type Books struct {
   title string
   author string
   subject string
   book_id int
}

func main() {
   var Book1 Books        /* Declare Book1 of type Book */
   var Book2 Books        /* Declare Book2 of type Book */

   /* book 1 描述 */
   Book1.title = "Go 语言"
   Book1.author = "www.runoob.com"
   Book1.subject = "Go 语言教程"
   Book1.book_id = 6495407

   /* book 2 描述 */
   Book2.title = "Python 教程"
   Book2.author = "www.runoob.com"
   Book2.subject = "Python 语言教程"
   Book2.book_id = 6495700

   /* 打印 Book1 信息 */
   printBook(&Book1)

   /* 打印 Book2 信息 */
   printBook(&Book2)
}
func printBook( book *Books ) {
   fmt.Printf( "Book title : %s\n", book.title);
   fmt.Printf( "Book author : %s\n", book.author);
   fmt.Printf( "Book subject : %s\n", book.subject);
   fmt.Printf( "Book book_id : %d\n", book.book_id);
}
```

结构体实例化也可以是这样的

```go
package main

import "fmt"

type Books struct {
}

func (s Books) String() string {
	return "data"
}
func main() {
	fmt.Printf("%v\n", Books{})
}
```



## 1.5 结构体的匿名字段

**结构体的匿名字段**

可以用字段来创建结构，这些字段只包含一个没有字段名的类型。这些字段被称为匿名字段。

在类型中，使用不写字段名的方式，使用另一个类型

```go
type Human struct {
    name string
    age int
    weight int
} 
type Student struct {
    Human // 匿名字段，那么默认Student就包含了Human的所有字段
    speciality string
} 
func main() {
    // 我们初始化一个学生
    mark := Student{Human{"Mark", 25, 120}, "Computer Science"}
    // 我们访问相应的字段
    fmt.Println("His name is ", mark.name)
    fmt.Println("His age is ", mark.age)
    fmt.Println("His weight is ", mark.weight)
    fmt.Println("His speciality is ", mark.speciality)
    // 修改对应的备注信息
    mark.speciality = "AI"
    fmt.Println("Mark changed his speciality")
    fmt.Println("His speciality is ", mark.speciality)
    // 修改他的年龄信息
    fmt.Println("Mark become old")
    mark.age = 46
    fmt.Println("His age is", mark.age)
    // 修改他的体重信息
    fmt.Println("Mark is not an athlet anymore")
    mark.weight += 60
    fmt.Println("His weight is", mark.weight)
}
```

> 可以使用"."的方式进行调用匿名字段中的属性值
>
> 实际就是字段的继承
>
> 其中可以将匿名字段理解为字段名和字段类型都是同一个
>
> 基于上面的理解，所以可以`mark.Human = Human{"Marcus", 55, 220} `和`mark.Human.age -= 1`
>
> 若存在匿名字段中的字段与非匿名字段名字相同，则最外层的优先访问，就近原则

通过匿名访问和修改字段相当的有用，但是不仅仅是struct字段哦，所有的内置类型和自定义类型都是可以作为匿名字段的。



## 1.6 结构体嵌套

嵌套的结构体
一个结构体可能包含一个字段，而这个字段反过来就是一个结构体。这些结构被称为嵌套结构。

示例代码：

```go
package main

import (  
    "fmt"
)

type Address struct {  
    city, state string
}
type Person struct {  
    name string
    age int
    address Address
}

func main() {  
    var p Person
    p.name = "Naveen"
    p.age = 50
    p.address = Address {
        city: "Chicago",
        state: "Illinois",
    }
    fmt.Println("Name:", p.name)
    fmt.Println("Age:",p.age)
    fmt.Println("City:",p.address.city)
    fmt.Println("State:",p.address.state)
}
```



## 1.7 提升字段

在结构体中属于匿名结构体的字段称为提升字段，因为它们可以被访问，就好像它们属于拥有匿名结构字段的结构一样。理解这个定义是相当复杂的。

示例代码：

```go
package main

import (  
    "fmt"
)

type Address struct {  
    city, state string
}
type Person struct {  
    name string
    age  int
    address Address
}

func main() {  
    var p Person
    p.name = "Naveen"
    p.age = 50
    p.Address = Address{
        city:  "Chicago",
        state: "Illinois",
    }
    fmt.Println("Name:", p.name)
    fmt.Println("Age:", p.age)
    fmt.Println("City:", p.city) //city is promoted field
    fmt.Println("State:", p.state) //state is promoted field
}
```

运行结果

```
Name: Naveen  
Age: 50  
City: Chicago  
State: Illinois
```



## 1.8 导出结构体和字段

如果结构体类型以大写字母开头，那么它是一个导出类型，可以从其他包访问它。类似地，如果结构体的字段以大写开头，则可以从其他包访问它们。

示例代码：

1.在computer目录下，创建文件spec.go

```go
package computer

type Spec struct { //exported struct  
    Maker string //exported field
    model string //unexported field
    Price int //exported field
}
```

2.创建main.go 文件

```go
package main

import "structs/computer"  
import "fmt"

func main() {  
    var spec computer.Spec
    spec.Maker = "apple"
    spec.Price = 50000
    fmt.Println("Spec:", spec)
}
```

> 目录结构如下：
>
>     src  
>     	structs
>     		computer
>     			spec.go
>     		main.go



## 1.9 结构体比较

结构体是值类型，如果每个字段具有可比性，则是可比较的。如果它们对应的字段相等，则认为两个结构体变量是相等的。

示例代码：

```go
package main

import (  
    "fmt"
)

type name struct {  
    firstName string
    lastName string
}


func main() {  
    name1 := name{"Steve", "Jobs"}
    name2 := name{"Steve", "Jobs"}
    if name1 == name2 {
        fmt.Println("name1 and name2 are equal")
    } else {
        fmt.Println("name1 and name2 are not equal")
    }

    name3 := name{firstName:"Steve", lastName:"Jobs"}
    name4 := name{}
    name4.firstName = "Steve"
    if name3 == name4 {
        fmt.Println("name3 and name4 are equal")
    } else {
        fmt.Println("name3 and name4 are not equal")
    }
}
```

运行结果

```
name1 and name2 are equal  
name3 and name4 are not equal  
```

**如果结构变量包含的字段是不可比较的，那么结构变量是不可比较的**

示例代码：

```go
package main

import (  
    "fmt"
)

type image struct {  
    data map[int]int
}

func main() {  
    image1 := image{data: map[int]int{
        0: 155,
    }}
    image2 := image{data: map[int]int{
        0: 155,
    }}
    if image1 == image2 {
        fmt.Println("image1 and image2 are equal")
    }
}
```



## 2.0 结构体作为函数的参数

结构体作为函数参数使用

```go
ackage main

import "fmt"

type Books struct {
   title string
   author string
   subject string
   book_id int
}

func main() {
   var Book1 Books        /* 声明 Book1 为 Books 类型 */
   var Book2 Books        /* 声明 Book2 为 Books 类型 */

   /* book 1 描述 */
   Book1.title = "Go 语言"
   Book1.author = "www.runoob.com"
   Book1.subject = "Go 语言教程"
   Book1.book_id = 6495407

   /* book 2 描述 */
   Book2.title = "Python 教程"
   Book2.author = "www.runoob.com"
   Book2.subject = "Python 语言教程"
   Book2.book_id = 6495700

   /* 打印 Book1 信息 */
   printBook(Book1)

   /* 打印 Book2 信息 */
   printBook(Book2)
}

func printBook( book Books ) {
   fmt.Printf( "Book title : %s\n", book.title);
   fmt.Printf( "Book author : %s\n", book.author);
   fmt.Printf( "Book subject : %s\n", book.subject);
   fmt.Printf( "Book book_id : %d\n", book.book_id);
}
```

**make、new操作**

make用于内建类型（map、slice 和channel）的内存分配。new用于各种类型的内存分配
内建函数new本质上说跟其它语言中的同名函数功能一样：new(T)分配了零值填充的T类型的内存空间，并且返回其地址，即一个*T类型的值。用Go的术语说，它返回了一个指针，指向新分配的类型T的零值。有一点非常重要：new返回指针

内建函数make(T, args)与new(T)有着不同的功能，make只能创建slice、map和channel，并且返回一个有初始值(非零)的T类型，而不是*T。本质来讲，导致这三个类型有所不同的原因是指向数据结构的引用在使用前必须被初始化。例如，一个slice，是一个包含指向数据（内部array）的指针、长度和容量的三项描述符；在这些项目被初始化之前，slice为nil。对于slice、map和channel来说，make初始化了内部的数据结构，填充适当的值。

make返回初始化后的（非零）值。




# 方法


## 1.1 什么是方法

Go 语言中同时有函数和方法。一个方法就是一个包含了接受者的函数，接受者可以是命名类型或者结构体类型的一个值或者是一个指针。所有给定类型的方法属于该类型的方法集

方法只是一个函数，它带有一个特殊的接收器类型，它是在func关键字和方法名之间编写的。接收器可以是struct类型或非struct类型。接收方可以在方法内部访问。

## 1.2 方法的语法

定义方法的语法

```go
func (t Type) methodName(parameter list)(return list) {
  
}
func funcName(parameter list)(return list){
    
}
```

实例代码：

```go
package main

import (  
    "fmt"
)

type Employee struct {  
    name     string
    salary   int
    currency string
}

/*
 displaySalary() method has Employee as the receiver type
*/
func (e Employee) displaySalary() {  
    fmt.Printf("Salary of %s is %s%d", e.name, e.currency, e.salary)
}

func main() {  
    emp1 := Employee {
        name:     "Sam Adolf",
        salary:   5000,
        currency: "$",
    }
    emp1.displaySalary() //Calling displaySalary() method of Employee type
}
```

**可以定义相同的方法名**

示例代码：

```go
package main

import (
	"fmt"
	"math"
)

type Rectangle struct {
	width, height float64
}
type Circle struct {
	radius float64
}


func (r Rectangle) area() float64 {
	return r.width * r.height
}
//该 method 属于 Circle 类型对象中的方法
func (c Circle) area() float64 {
	return c.radius * c.radius * math.Pi
}
func main() {
	r1 := Rectangle{12, 2}
	r2 := Rectangle{9, 4}
	c1 := Circle{10}
	c2 := Circle{25}
	fmt.Println("Area of r1 is: ", r1.area())
	fmt.Println("Area of r2 is: ", r2.area())
	fmt.Println("Area of c1 is: ", c1.area())
	fmt.Println("Area of c2 is: ", c2.area())
}
```

运行结果

```
Area of r1 is:  24
Area of r2 is:  36
Area of c1 is:  314.1592653589793
Area of c2 is:  1963.4954084936207
```

- 虽然method的名字一模一样，但是如果接收者不一样，那么method就不一样
- method里面可以访问接收者的字段
- 调用method通过.访问，就像struct里面访问字段一样 

## 1.3 方法和函数

既然我们已经有了函数，为什么还要使用方法？

示例代码：

```go
package main

import (  
    "fmt"
)

type Employee struct {  
    name     string
    salary   int
    currency string
}

/*
 displaySalary() method converted to function with Employee as parameter
*/
func displaySalary(e Employee) {  
    fmt.Printf("Salary of %s is %s%d", e.name, e.currency, e.salary)
}

func main() {  
    emp1 := Employee{
        name:     "Sam Adolf",
        salary:   5000,
        currency: "$",
    }
    displaySalary(emp1)
}
```

>在上面的程序中，displaySalary方法被转换为一个函数，而Employee struct作为参数传递给它。这个程序也产生了相同的输出：Salary of Sam Adolf is $5000.。

为什么我们可以用函数来写相同的程序呢?有以下几个原因

1. Go不是一种纯粹面向对象的编程语言，它不支持类。因此，类型的方法是一种实现类似于类的行为的方法。
2. 相同名称的方法可以在不同的类型上定义，而具有相同名称的函数是不允许的。假设我们有一个正方形和圆形的结构。可以在正方形和圆形上定义一个名为Area的方法。这是在下面的程序中完成的。

## 1.4 变量作用域 

作用域为已声明标识符所表示的常量、类型、变量、函数或包在源代码中的作用范围。

Go 语言中变量可以在三个地方声明：

- 函数内定义的变量称为局部变量
- 函数外定义的变量称为全局变量
- 函数定义中的变量称为形式参数

**局部变量**

在函数体内声明的变量称之为局部变量，它们的作用域只在函数体内，参数和返回值变量也是局部变量。

**全局变量**

在函数体外声明的变量称之为全局变量，首字母大写全局变量可以在整个包甚至外部包（被导出后）使用。

```go
package main

import "fmt"

/* 声明全局变量 */
var g int

func main() {

   /* 声明局部变量 */
   var a, b int

   /* 初始化参数 */
   a = 10
   b = 20
   g = a + b

   fmt.Printf("结果： a = %d, b = %d and g = %d\n", a, b, g)
}
```

`结果`

```go
结果： a = 10, b = 20 and g = 30
```

**形式参数**

形式参数会作为函数的局部变量来使用

**指针作为接收者**

若不是以指针作为接收者，实际只是获取了一个copy，而不能真正改变接收者的中的数据

```go
func (b *Box) SetColor(c Color) {
	b.color = c
}
```

示例代码

```go
package main

import (
	"fmt"
)

type Rectangle struct {
	width, height int
}

func (r *Rectangle) setVal() {
	r.height = 20
}

func main() {
	p := Rectangle{1, 2}
	s := p
	p.setVal()
	fmt.Println(p.height, s.height)
}
```

结果

```go
20 2
```

如果没有那个*，则值就是`2 2`

## 1.5 method继承

method是可以继承的，如果匿名字段实现了一个method，那么包含这个匿名字段的struct也能调用该method

```go
package main

import "fmt"

type Human struct {
	name  string
	age   int
	phone string
}
type Student struct {
	Human  //匿名字段
	school string
}
type Employee struct {
	Human   //匿名字段
	company string
}

func (h *Human) SayHi() {
	fmt.Printf("Hi, I am %s you can call me on %s\n", h.name, h.phone)
}
func main() {
	mark := Student{Human{"Mark", 25, "222-222-YYYY"}, "MIT"}
	sam := Employee{Human{"Sam", 45, "111-888-XXXX"}, "Golang Inc"}
	mark.SayHi()
	sam.SayHi()
}
```

运行结果：

```go
Hi, I am Mark you can call me on 222-222-YYYY
Hi, I am Sam you can call me on 111-888-XXXX
```

## 1.6 method重写

```go
package main

import "fmt"

type Human struct {
	name  string
	age   int
	phone string
}
type Student struct {
	Human  //匿名字段
	school string
}
type Employee struct {
	Human   //匿名字段
	company string
}

//Human定义method
func (h *Human) SayHi() {
	fmt.Printf("Hi, I am %s you can call me on %s\n", h.name, h.phone)
}

//Employee的method重写Human的method
func (e *Employee) SayHi() {
	fmt.Printf("Hi, I am %s, I work at %s. Call me on %s\n", e.name,
		e.company, e.phone) //Yes you can split into 2 lines here.
}
func main() {
	mark := Student{Human{"Mark", 25, "222-222-YYYY"}, "MIT"}
	sam := Employee{Human{"Sam", 45, "111-888-XXXX"}, "Golang Inc"}
	mark.SayHi()
	sam.SayHi()
}
```

运行结果：

```go
Hi, I am Mark you can call me on 222-222-YYYY
Hi, I am Sam, I work at Golang Inc. Call me on 111-888-XXXX
```

- 方法是可以继承和重写的
- 存在继承关系时，按照就近原则，进行调用




# 接口


## 1.1 什么是接口?

面向对象世界中的接口的一般定义是“接口定义对象的行为”。它表示让指定对象应该做什么。实现这种行为的方法(实现细节)是针对对象的。

在Go中，接口是一组方法签名。当类型为接口中的所有方法提供定义时，它被称为实现接口。它与OOP非常相似。接口指定了类型应该具有的方法，类型决定了如何实现这些方法。

>  它把所有的具有共性的方法定义在一起，任何其他类型只要实现了这些方法就是实现了这个接口
>
>  接口定义了一组方法，如果某个对象实现了某个接口的所有方法，则此对象就实现了该接口。



## 1.2 接口的定义语法

定义接口

```go
/* 定义接口 */
type interface_name interface {
   method_name1 [return_type]
   method_name2 [return_type]
   method_name3 [return_type]
   ...
   method_namen [return_type]
}

/* 定义结构体 */
type struct_name struct {
   /* variables */
}

/* 实现接口方法 */
func (struct_name_variable struct_name) method_name1() [return_type] {
   /* 方法实现 */
}
...
func (struct_name_variable struct_name) method_namen() [return_type] {
   /* 方法实现*/
}
```

示例代码：

```go
package main

import (
    "fmt"
)

type Phone interface {
    call()
}

type NokiaPhone struct {
}

func (nokiaPhone NokiaPhone) call() {
    fmt.Println("I am Nokia, I can call you!")
}

type IPhone struct {
}

func (iPhone IPhone) call() {
    fmt.Println("I am iPhone, I can call you!")
}

func main() {
    var phone Phone

    phone = new(NokiaPhone)
    phone.call()

    phone = new(IPhone)
    phone.call()

}
```

运行结果：

```go
I am Nokia, I can call you!
I am iPhone, I can call you!
```

- interface可以被任意的对象实现
- 一个对象可以实现任意多个interface
- 任意的类型都实现了空interface(我们这样定义：interface{})，也就是包含0个method的interface

## 1.3 interface值



```go
package main

import "fmt"

type Human struct {
	name  string
	age   int
	phone string
}
type Student struct {
	Human  //匿名字段
	school string
	loan   float32
}
type Employee struct {
	Human   //匿名字段
	company string
	money   float32
} //Human实现Sayhi方法
func (h Human) SayHi() {
	fmt.Printf("Hi, I am %s you can call me on %s\n", h.name, h.phone)
} //Human实现Sing方法
func (h Human) Sing(lyrics string) {
	fmt.Println("La la la la...", lyrics)
} //Employee重写Human的SayHi方法
func (e Employee) SayHi() {
	fmt.Printf("Hi, I am %s, I work at %s. Call me on %s\n", e.name,
		e.company, e.phone) //Yes you can split into 2 lines here.
}

// Interface Men被Human,Student和Employee实现
// 因为这三个类型都实现了这两个方法
type Men interface {
	SayHi()
	Sing(lyrics string)
}

func main() {
	mike := Student{Human{"Mike", 25, "222-222-XXX"}, "MIT", 0.00}
	paul := Student{Human{"Paul", 26, "111-222-XXX"}, "Harvard", 100}
	sam := Employee{Human{"Sam", 36, "444-222-XXX"}, "Golang Inc.", 1000}
	Tom := Employee{Human{"Sam", 36, "444-222-XXX"}, "Things Ltd.", 5000}
	//定义Men类型的变量i
	var i Men
	//i能存储Student
	i = mike
	fmt.Println("This is Mike, a Student:")
	i.SayHi()
	i.Sing("November rain")
	//i也能存储Employee
	i = Tom
	fmt.Println("This is Tom, an Employee:")
	i.SayHi()
	i.Sing("Born to be wild")
	//定义了slice Men
	fmt.Println("Let's use a slice of Men and see what happens")
	x := make([]Men, 3)
	//T这三个都是不同类型的元素，但是他们实现了interface同一个接口
	x[0], x[1], x[2] = paul, sam, mike
	for _, value := range x {
		value.SayHi()
	}
}
```

运行结果：

```go
	This is Mike, a Student:
	Hi, I am Mike you can call me on 222-222-XXX
	La la la la... November rain
	This is Tom, an Employee:
	Hi, I am Sam, I work at Things Ltd.. Call me on 444-222-XXX
	La la la la... Born to be wild
	Let's use a slice of Men and see what happens
	Hi, I am Paul you can call me on 111-222-XXX
	Hi, I am Sam, I work at Golang Inc.. Call me on 444-222-XXX
	Hi, I am Mike you can call me on 222-222-XXX
```

那么interface里面到底能存什么值呢？如果我们定义了一个interface的变量，那么这个变量里面可以存实现这个interface的任意类型的对象。例如上面例子中，我们定义了一个Men interface类型的变量m，那么m里面可以存Human、Student或者Employee值

> 当然，使用指针的方式，也是可以的
>
> 但是，接口对象不能调用实现对象的属性

**interface函数参数**

interface的变量可以持有任意实现该interface类型的对象，这给我们编写函数(包括method)提供了一些额外的思考，我们是不是可以通过定义interface参数，让函数接受各种类型的参数

**嵌入interface**

```go
package main

import "fmt"

type Human interface {
	Len()
}
type Student interface {
	Human
}

type Test struct {
}

func (h *Test) Len() {
	fmt.Println("成功")
}
func main() {
	var s Student
	s = new(Test)
	s.Len()
}
```



示例代码：

```go
package test

import (
	"fmt"
)

type Controller struct {
	M int32
}

type Something interface {
	Get()
	Post()
}

func (c *Controller) Get() {
	fmt.Print("GET")
}

func (c *Controller) Post() {
	fmt.Print("POST")
}
```

```go
package main

import (
	"fmt"
	"test"
)

type T struct {
	test.Controller
}

func (t *T) Get() {
	//new(test.Controller).Get()
	fmt.Print("T")
}
func (t *T) Post() {
	fmt.Print("T")
}
func main() {
	var something test.Something
	something = new(T)
	var t T
	t.M = 1
	//	t.Controller.M = 1
	something.Get()
}
```



Controller实现了所有的Something接口方法，当结构体T中调用Controller结构体的时候，T就相当于Java中的继承，T继承了Controller，因此，T可以不用重写所有的Something接口中的方法，因为父构造器已经实现了接口。

如果Controller没有实现Something接口方法，则T要调用Something中方法，就要实现其所有方法。

如果`something = new(test.Controller)`则调用的是Controller中的Get方法。

T可以使用Controller结构体中定义的变量

#### 总结

接口对象不能调用接口实现对象的属性





































