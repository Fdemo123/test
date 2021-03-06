### 多线程
> 1.线程有几种状态？之间是如何切换的？<br/>
[见答案](https://blog.csdn.net/pange1991/article/details/53860651)<br/>


> 2.volatile 的作用（两点），volatile 的原理与应用场景。线程的可见性 和 防止指令重排<br/>
[见答案](https://www.cnblogs.com/chenssy/p/6379280.html)<br/>

> 3.线程安全是什么？如何做到线程安全？怎么判断一个类是不是线程安全？ <br/>
类要成为线程安全的，首先必须在单线程环境中有正确的行为。如果一个类实现正确(这是说它符合规格说明的另一种方式)，那么没有一种对这个类的对象的操作序列(读或者写公共字段以及调用公共方法)可以让对象处于无效状态，观察到对象处于无效状态、或者违反类的任何不可变量、前置条件或者后置条件的情况。此外，一个类要成为线程安全的，在被多个线程访问时，不管运行时环境执行这些线程有什么样的时序安排或者交错，它必须仍然有如上所述的正确行为，并且在调用的代码中没有任何额外的同步。其效果就是，在所有线程看来，对于线程安全对象的操作是以固定的、全局一致的顺序发生的。正确性与线程安全性之间的关系非常类似于在描述 ACID(原子性、一致性、独立性和持久性)事务时使用的一致性与独立性之间的关系：从特定线程的角度看，由不同线程所执行的对象操作是先后(虽然顺序不定)而不是并行执行的。<br/>

> 4.线程同步有几种方式？为何要使用同步？<br/>
[见答案](https://www.jianshu.com/p/f796f891c486)<br/>

> 5.threadlocal 的原理<br/>
[见答案](https://blog.csdn.net/xlgen157387/article/details/78297568)<br/>

> 6.synchronized 是如何实现的？<br/>
[见答案](https://blog.csdn.net/thousa_ho/article/details/77992743)<br/>

> 7.sleep 和wait 的区别<br/>
[见答案](https://blog.csdn.net/xyh269/article/details/52613507)<br/>
 
> 8.线程池有几种？各自的应用场景<br/>
[见答案](https://blog.csdn.net/WenJunZenDeQingRuXu/article/details/79488348)<br/>

> 9.线程池的原理，主要有几个参数？线程池满了怎么办？<br/>
[见答案](https://www.jianshu.com/p/edab547f2710)<br/>

> 10.Semaphore、countdownlatch、futureTask<br/>
[见答案](https://www.cnblogs.com/Eason-S/p/5763418.html?utm_source=itdadao&utm_medium=referral)<br/>

> 11.submit 和execute 的区别。<br/>
[见答案](https://www.jianshu.com/p/29610984f1dd)<br/>

> 12.Future 接口的几个主要方法<br/>
[见答案](https://blog.csdn.net/qq_38345606/article/details/82829400)<br/>

> 13.创建线程有几种方式<br/>
[见答案](https://blog.csdn.net/m0_37840000/article/details/79756932)<br/>

> 14.可重入锁是如何实现的<br/>
[见答案](https://www.cnblogs.com/gxyandwmm/p/9387833.html)<br/>
[见答案](https://blog.csdn.net/pb_yan/article/details/80502119)<br/>

> 15.线程池提交任务超过设置的最核心程数,并且队列也满了后，创建的小于超出核心线程数的那些线程会尝试去队列里面取任务，如果取不到 超过设定的keepAliveTime那么线程销毁<br/>
Executors.newFixedThreadPool(10)使用的是无界队列。因为LinkedBlockingQueue默认的最大任务数量是Integer.MAX_VALUE，非常大，近乎于可以理解为无限吧。<br/>
只要队列不满，就跟maximumPoolSize、keepAliveTime这些没关系了，因为不会创建超过corePoolSize数量的线程的。<br/>

> 16.LongAdder<br/>
[原理](https://www.cnblogs.com/myseries/p/12699433.html)<br/>

> 17.CAS<br/>
[原理](https://mp.weixin.qq.com/s/ZwIBesNycqtAaZj_OjvhxQ)<br/>

> 18.aqs<br/>
[原理](https://mp.weixin.qq.com/s?__biz=MzU0OTk3ODQ3Ng==&mid=2247484094&idx=1&sn=b337161f934b1c27ff1f059350ef5e65&chksm=fba6eabdccd163abc8978b65e155d79a133f20ee8a5bff79a33ed20a050c2bd576581db69fe6&mpshare=1&scene=1&srcid=0608yIcfsyrDG1NIBSsF58jq%23rd)<br/>

> 19.综合<br/>
[综合](https://github.com/minfei-miffy/Java-mianshi-note/blob/master/Java%E6%A0%B8%E5%BF%83%E9%9D%A2%E8%AF%95%E7%9F%A5%E8%AF%86%E9%9B%86%E2%80%94Java%E5%B9%B6%E5%8F%91%E7%BC%96%E7%A8%8B%E9%9D%A2%E8%AF%95%E9%A2%98.md)<br/>

> 20.公平与非公平<br/>
[原理](https://mp.weixin.qq.com/s?__biz=MzU0OTk3ODQ3Ng==&mid=2247484095&idx=1&sn=aa915ae16d0a550bbe7ae4b6fec99173&chksm=fba6eabcccd163aa2bc0e880d7d3929eee5ff834a73a6ccc3a53237537a4555ef7fd4d9e70d0&mpshare=1&scene=1&srcid=0608QNgPOxWhMZfdNvGvcoUW%23rd)<br/>

> 21.多线程一定快吗<br/>

> 22.在Java中CycliBarriar和CountdownLatch有什么区别？<br/>
CountDownLatch一般用于某个线程A等待若干个其他线程执行完任务之后，它才执行；<br/>
而CyclicBarrier一般用于一组线程互相等待至某个状态，然后这一组线程再同时执行；<br/>
另外，CountDownLatch是不能够重用的，而CyclicBarrier是可以重用的。<br/>

> 23.volatie 定义、指令重排、单例<br/>
(https://blog.csdn.net/u010255818/article/details/65633033)<br/>


> 24.volatile和synchronized的区别<br/>
volatile本质是在告诉jvm当前变量在寄存器（工作内存）中的值是不确定的，需要从主存中读取； synchronized则是锁定当前变量，只有当前线程可以访问该变量，其他线程被阻塞住。<br/>
volatile仅能使用在变量级别；synchronized则可以使用在变量、方法、和类级别的<br/>
volatile仅能实现变量的修改可见性，不能保证原子性；而synchronized则可以保证变量的修改可见性和原子性<br/>
volatile不会造成线程的阻塞；synchronized可能会造成线程的阻塞。<br/>
volatile标记的变量不会被编译器优化；synchronized标记的变量可以被编译器优化<br/>

> 25.Lock和synchronized的区别和使用<br/>
(https://www.cnblogs.com/baizhanshi/p/6419268.html)<br/>


> 26.Semaphore信号灯<br/>
(https://www.cnblogs.com/tonglin0325/p/6264634.html)<br/>

> 27.Threadlocal<br/>
(https://www.cnblogs.com/dolphin0520/p/3920407.html)<br/>
(https://www.cnblogs.com/xzwblog/p/7227509.html)<br/>

> 28.线程池参数<br/>
(https://www.cnblogs.com/jiangxiulian/p/7443983.html)<br/>

> 29.Future接口和Callable接口以及FeatureTask详解<br/>
(https://www.cnblogs.com/cuimiemie/p/6445154.html)<br/>

> 30.提高volatile并发效率<br/>
(https://blog.csdn.net/hyf_home/article/details/81673791#comments)<br/>

> 31.面试必问
(https://mp.weixin.qq.com/s/v3eClGAgC7iDW09MoDKiEA)

