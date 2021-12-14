> 1.Spring + JTA  两阶段<br/>
> 2.消息总线<br/>
> 3.es<br/>
[原理](https://www.cnblogs.com/JimShi/p/11525360.html)<br/>
> 4.kafka<br/>
[kafka](https://blog.csdn.net/qq_28900249/article/details/90346599)<br/>
[常见面试](https://juejin.cn/post/6871499321506791437)
> 5.zookeeper<br/>
[zookeeper](https://www.cnblogs.com/felixzh/p/5869212.html)<br/>

> 6.CAP定理<br/>
  一致性(Consistency) ： 客户端知道一系列的操作都会同时发生(生效)<br/>
  可用性(Availability) ： 每个操作都必须以可预期的响应结束<br/>
  分区容错性(Partition tolerance) ： 即使出现单个组件无法可用,操作依然可以完成<br/>

> 7.BASE理论<br/>
在分布式系统中，我们往往追求的是可用性，它的重要程序比一致性要高，那么如何实现高可用性呢？ 前人已经给我们提出来了另外一个理论，就是BASE理论，它是用来对CAP定理进行进一步扩充的。BASE理论指的是：<br/>
Basically Available（基本可用）<br/>
Soft state（软状态）<br/>
Eventually consistent（最终一致性）<br/>

> 8.rabbitmq<br/>
[rabbitMq](https://blog.csdn.net/whoamiyang/article/details/54954780)<br/>
[死信队列](https://my.oschina.net/xiaominmin/blog/1810851)<br/>

> 9.多路复用<br/>
定义:IO多路复用是一种同步IO模型，实现一个线程可以监视多个文件句柄；一旦某个文件句柄就绪，就能够通知应用程序进行相应的读写操作；
没有文件句柄就绪时会阻塞应用程序，交出cpu。多路是指网络连接，复用指的是同一个线程<br/>
[epoll 水平触发（LT）与 边缘触发（ET）的区别？](https://www.cnblogs.com/heluan/p/9589086.html)

> 10、mq 的原理与应用场景，mq 是如何保证不丢消息的？<br/>
[原理](https://www.cnblogs.com/flyrock/p/8859203.html)<br/>
