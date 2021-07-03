悲观锁和乐观锁
悲观锁
悲观锁认为每次自己修改数据的过程中，别人总是会同时对数据进行修改
常见的悲观锁有java中的synchronized关键字，被修饰的方法或代码块需要在进入方法或代码块执行的时候先获取synchronized
括号里的对象的monitor对象，然后才能进入到方法或代码块中进行执行，在这个过程中线程之间是排他的，只有一个线程执行完成
之后其他线程才能争夺monitor对象，拿到monitor对象的线程才能进入方法或代码块
mysql数据库的innodb存储引擎中也存在悲观锁，在一个事物中当查询语句是select ... for update 的时候，会给这条记录上排他写锁（行锁），
当其他事物对这条记录进行修改时需要等持有锁的事物把排他锁释放才能对这条事物进行修改

乐观锁
乐观锁认为每次自己修改数据的过程中，别人不会对数据进行修改
在java中Atomic原子类下面都是通过CAS实现的，CAS的更新过程是先读取要更新的值作为expectedValue，然后对这个值进行修改产生newValue，
然后使用CAS操作来修改这个值（再次读取这个值如果等于expectedValue就用newValue和expectedValue进行交换，整个CAS是jvm实现的是原子操作），
jdk1.9之前是在Unsafe包里实现的，Unsafe包可以直接操作内存，1.9开始使用Varhandler实现，具体实现原理不太清楚，，
java中AQS也是通过CAS实现的乐观锁。