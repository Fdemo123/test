> 1、redis 与 memcache 的区别<br/>
[原理](https://www.cnblogs.com/JavaBlackHole/p/7726195.html)<br/>

> 2 、 redis 与 memcached 内 存 分 别 是 如 何 回 收 的 ？ <br/>
[Redis](https://blog.csdn.net/tr1912/article/details/81267910) <br/>
[Memcached](https://www.cnblogs.com/leezhxing/p/3716332.html)<br/>

> 3、guava 的缓存是怎么实现的？<br/>
[1](https://crossoverjie.top/2018/06/13/guava/guava-cache/)<br/>
[2](https://blog.csdn.net/qq_18661793/article/details/81059226)<br/>

> 4、redis 与 memcache 的区别<br/>
[原理](https://www.cnblogs.com/JavaBlackHole/p/7726195.html)<br/>

> 5、redis 持久化策略，rdb 与 aof 的区别与应用场景<br/>
[原理](https://blog.csdn.net/m0_38110132/article/details/76906422)<br/>

> 6、memcached 的内存是如何分配的？一致性哈希原理<br/>
[原理](https://www.cnblogs.com/moyangvip/p/5259700.html)<br/>

> 7.【缓存穿透、缓存击穿、缓存雪崩、热点数据失效】问题的解决方案<br/>
[原理](https://mp.weixin.qq.com/s?__biz=MzU0OTk3ODQ3Ng==&mid=2247484884&idx=1&sn=ceb798b6e8ef0ee608a992385f7d8568&chksm=fba6edd7ccd164c155271811f7948b476955cab41b23f2333847b8c268b31cc9f3332c2e3926&mpshare=1&scene=1&srcid=0608pIX1L8Fja1H99IyorW2X%23rd)<br/>

> 8.redis 分布式锁和 zk 分布式锁的对比<br/>
redis 分布式锁，其实需要自己不断去尝试获取锁，比较消耗性能。<br/>
zk 分布式锁，获取不到锁，注册个监听器即可，不需要不断主动尝试获取锁，性能开销较小。<br/>
另外一点就是，如果是 redis 获取锁的那个客户端 出现 bug 挂了，那么只能等待超时时间之后才能释放锁；而 zk 的话，因为创建的是临时 znode，只要客户端挂了，znode 就没了，此时就自动释放锁。<br/>
redis 分布式锁大家没发现好麻烦吗？遍历上锁，计算时间等等......zk 的分布式锁语义清晰实现简单。所以先不分析太多的东西，就说这两点，我个人实践认为 zk 的分布式锁比 redis 的分布式锁牢靠、而且模型简单易用。<br/>

> 9.redis集群模式<br/>
[原理](https://mp.weixin.qq.com/s/_rxkA9AXlnkSU-l191GgrQ)<br/>
[面试总结](https://www.cnblogs.com/jiahaoJAVA/p/6244278.html)<br/>

> 10.分布式缓存<br/>
[原理](https://github.com/shishan100/Java-Interview-Advanced)<br/>

> 11.一致性哈希算法<br/>
[原理](https://www.zsythink.net/archives/1182)<br/>

> 12.分布式锁：
悲观锁：<br/>
expireMsecs 锁持有超时<br/>
timeoutMsecs 锁等待超时时间<br/>
循环，通过setnx设置锁，成功则获得锁，否则判断当前锁是否到期了（获取时间T1），没有到期则继续轮询，到期了就通过getset去获得旧T2，如果T1=T2则成功获得锁，不然就是被其他线程抢先了，继续轮询<br/>
乐观锁：<br/>
用watch一个key，开启事务multi，操作完执行exec 被人改了则失败。否则成功。<br/>
