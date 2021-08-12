# 垃圾回收机制GC, cms, G1,垃圾回收的算法
- https://zhuanlan.zhihu.com/p/59861022
- https://www.cnblogs.com/yanl55555/p/13366387.html

## 发展阶段
- 串行收集器，单线程，JDK 1.3 之前，收集时，其他线程暂停
- 并行收集器，吞吐量收集器，多线程，充分利用多核
- CMS 并发收集器， Minor GC暂行其他线程，多线程回收
- Full GC不暂停其他线程，用后台进程对老年代进行扫描
- G1 并发收集器，垃圾优先收集器，缩短超大堆时产生的停顿
