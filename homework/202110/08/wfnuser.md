# Facebook全网宕机的解决办法
Facebook的robotron论文中提到 网络是高度需要人为介入配置的基础设施，自动化运维非常关键。
这次的事故也是源于意外的配置失误。一些可以优化的点如下：

审计平台 - 稳定性提升；经过更严苛的测试；能准确的自动发现错误的配置
运维侧 - 重要配置介入人工审核
园区基础设施 - 减少对外部网络服务的依赖

设计提升 - DNS 对 BGP 的健康监测和激进的下线机制可以调整；DNS自治号应该更多元

做得好的部分 应对恢复网络服务后的突发流量