# 电商系统如何分库分表

分库分表可分为水平切分和垂直切分两种，垂直切分十分直观，把不同功能的业务分开就好。水平切分，一般有以下几种方式：1.设置一个数据库存储index与它实际存储的数据库的key-val pair； 2. 按index范围分表；
3. 按hash值分表。如果分表还是不能解决访问的压力的话，我们只能选择使用集群来解决这个问题。