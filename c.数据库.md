###数据库

> 1.mysql 索 引 原 理 ？ 为 什 么 是 B+ 树 ？ 有 什 么 优 点 ？ <br/>
[见答案](https://blog.csdn.net/wohaqiyi/article/details/79503395)<br/>
[见答案](https://blog.csdn.net/bigtree_3721/article/details/73151472)<br/>

> 2.事务隔离级别有哪几种？mysql 默认的隔离级别是？脏读、幻读、不可重复读是什么情况？<br/>
[见答案](https://www.cnblogs.com/huanongying/p/7021555.html)<br/>
 
> 3.MVCC 原理<br/>
[见答案](https://blog.csdn.net/joy0921/article/details/80128857)<br/>
[京东](https://mp.weixin.qq.com/s/sEsZxlA6Zhb3UJIKskV5aA)<br/>

> 4.mysql 有哪几种锁？<br/>
[见答案](https://blog.csdn.net/soonfly/article/details/70238902)<br/>

> 5.mysql 的存储引擎有哪几种？区别和各自的适用场景。<br/>
[见答案](https://www.cnblogs.com/wcwen1990/p/6655416.html)<br/>

> 6.query cache 的配置<br/>
[见答案](https://www.cnblogs.com/JiangLe/p/5688266.html)<br/>
[见答案](https://www.jianshu.com/p/c5adfd764437)<br/>

> 7.ACID <br/>
[见答案](https://www.jianshu.com/p/0b245d972e23)<br/>

> 8.如何优化慢查询<br/>
[见答案]
<code>https://mp.weixin.qq.com/s?biz=MzA3MTUzOTcxOQ==&mid=2452965558&idx=1&sn=c3ee6be3e015c1c3cf0d046599c535b8&chksm=88ede5debf9a6cc8edad957885d885d0e13aa3b756c0cdcba1cdddecf4122410ef7a0c3fa7f4&scene=21#wechat_redirect</code><br/>

> 9.最左前缀匹配原则<br/>
[原理](https://www.kancloud.cn/kancloud/theory-of-mysql-index/41857)<br/>

> 10.综合<br/>
[综合](https://github.com/minfei-miffy/Java-mianshi-note/blob/master/Java%E6%A0%B8%E5%BF%83%E9%9D%A2%E8%AF%95%E7%9F%A5%E8%AF%86%E9%9B%86%E2%80%94MySQL%E9%9D%A2%E8%AF%95%E9%A2%98.md)<br/>
(https://mp.weixin.qq.com/s/nMJSog9k838xHVioK9NVyw)<br/>
(https://mp.weixin.qq.com/s/sUf43fvr3xDLzeh1KOSPaQ)<br/>

> 11.事务隔离级别<br/>
[死锁案例](http://blog.itpub.net/22664653/viewspace-2152274/)<br/>
上面的案例中出现死锁是由于不同会话对普通索引idx_c1和主键相互竞争导致循环等待而出现死锁的。生产过程中遇到高并发更新同一行的的时候可以考虑避免通过不同的索引进行更新，进而避免死锁。<br/>
1.read uncommitted（读未提交）<br/>
事务中对数据的修改即使未提交，对其他事务都是可见的，被称为脏读，性能不会比其他的好太多<br/>
2.read committed（读提交）<br/>
很多数据库的默认隔离级别，只能看见已提交事务的修改内容，也被称为不可重复读，因为重复读有可能会读到不同结果，解决脏读问题。<br/>
3.repeatable read（可重复读）<br/>
可以重复读，但不能解决幻读问题，当某个事务读取某个范围的数据，另外一个事务在该范围插入数据，再次读会有不同结果。<br/>
4.serializable(可串行化)<br/>
避免幻读，会在读取的每一行数据加上锁，只有在非常需要保证一致性的而且可以接受没有并发的情况下，才考虑该级别innodb解决死锁的方式：将持有最少行级排他锁的事务进行回滚<br/>

> 12.储存引擎的区别<br/>
如 Innodb 存储引擎的 B-Tree 索引实际使用的存储结构实际上是 B+Tree，也就是在 B-Tree 数据结构的基础上做了很小的改造，在每一个Leaf Node 上面出了存放索引键的相关信息之外，还存储了指向与该 Leaf Node 相邻的后一个 LeafNode 的指针信息（增加了顺序访问指针），这主要是为了加快检索多个相邻 Leaf Node 的效率考虑。
分库分表  执行计划<br/>
锁表<br/>
MySQL的innodb存储引擎支持行级锁，innodb的行锁是通过给索引项加锁实现的，这就意味着只有通过索引条件检索数据时，innodb才使用行锁，否则使用表锁。根据当前的数据更新语句（update jx_attach set complete=1,attach_size=63100 where cycore_file_id='56677142da502cd8907eb58f';），该条件字段cycore_file_id并没有添加索引，所以导致数据表被锁。<br/>

> 13.MVCC<br/>

> 14.聚集索引  全文索引<br/>

> 15.SQL慢查询的解决思路<br/>
(https://mp.weixin.qq.com/s?__biz=MzI3OTUwMjM4MA==&mid=2247483887&idx=1&sn=e04c1c4cd3915c5f7f7f0e0857a7b4a3&chksm=eb478aacdc3003babaa9900279a75e6cdf63394a8f9c6aa2776a44587db44265015f8ebe10ca)<br/>

> 16.mysql索引<br/>
B+Tree索引和Hash索引<br/>
1，不要滥用索引<br/>
①，索引提高查询速度，却会降低更新表的速度，因为更新表时，mysql不仅要更新数据，保存数据，还要更新索引，保存索引<br/>
②，索引会占用磁盘空间<br/>
2，索引不会包含含有NULL值的列<br/>
复合索引只要有一列含有NULL值,那么这一列对于此符合索引就是无效的，因此我们在设计数据库设计时不要让字段的默认值为NULL。<br/>
3，MySQL查询只是用一个索引<br/>
如果where字句中使用了索引的话，那么order by中的列是不会使用索引的<br/>
4，like<br/>
like '%aaa%'不会使用索引而like "aaa%"可以使用索引<br/>

> 17. redo log undolog


