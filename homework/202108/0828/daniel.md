## 解决问题

分库分表后, 如何存取数据, 使得后续有改动可以尽量少的影响到线上服务

# 简单模运算的问题

- 对数据中的键值和机器id进行简单模运算 , 然后将数据发送到不同节点
- 在节点发生变动的情况下, 大量的数据位置都发生变化, 需要进行数据迁移等处理, 影响线上应用

## 一致性 hash

- 数据被 hash 到一个 2^ 32 的hash 环空间上
- 不同server 节点也被平均的 hash 到环空间上
    - 每个server 负责一块空间
    - 如果单个 server 挂掉, 影响的也只是此server上的数据
    - 新加节点, 只有一小部分环空间需要重新映射, 对线上应用的影响可控