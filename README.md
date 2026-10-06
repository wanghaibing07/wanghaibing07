# 小冰ovo

这里放我做过的 Linux 和 Kubernetes 运维实验、脚本和排障记录。目前在深圳找 Linux / 云平台运维相关岗位。

## Retail Reliability Lab

[项目仓库](https://github.com/wanghaibing07/retail-reliability-lab) · [项目概况](https://github.com/wanghaibing07/retail-reliability-lab/blob/main/docs/portfolio/plain-language-guide.md) · [架构图](https://github.com/wanghaibing07/retail-reliability-lab/blob/main/docs/portfolio/architecture.md)

在三台 VMware 虚拟机上部署 AWS 的电商样例，练习日常运维中会遇到的部署、监控和恢复问题。业务代码来自 AWS；我做的是部署配置、脚本、排障和实验记录。

几份具体记录：

- [镜像拉取异常](https://github.com/wanghaibing07/retail-reliability-lab/blob/main/docs/incidents/001-image-pull-failure/README.md)：检查 DNS、HTTPS 和容器运行时，对比串行与并发下载，最后把镜像预拉取单独做成部署前的步骤。
- [订单数据库恢复](https://github.com/wanghaibing07/retail-reliability-lab/blob/main/docs/backup/stage5-closeout.md)：恢复到隔离数据库，再由应用读回订单；迁移到持久存储后，重建 Pod 检查新旧订单是否还在。
- [发布失败演练](https://github.com/wanghaibing07/retail-reliability-lab/blob/main/docs/releases/stage6-closeout.md)：新实例因错误的就绪检查不能接流量，旧实例继续服务；撤销 Git 中的错误配置后恢复。
- [性能测试](https://github.com/wanghaibing07/retail-reliability-lab/blob/main/docs/performance/stage7-closeout.md)：只读浏览负载下，30 RPS 持续 300 秒已验证健康；45 RPS 多次出现超时或延迟突增，后段恢复，最大容量还没有确定。

部署和监控配置也在仓库中。这里记录的是本地实验结果，实际操作过程和限制都写在对应文档里。
