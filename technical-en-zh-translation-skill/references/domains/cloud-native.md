# 云原生领域词库

适用于容器、Kubernetes、微服务、云基础设施与可观测性文档。Kubernetes 资源类型和对象名称按原文保留。

| English term | 建议中文译法 | 适用语境/定义 | 备注 |
| --- | --- | --- | --- |
| workload | 工作负载 | 在平台上运行的应用或任务 | Kubernetes 对象名 `Workload` 若为专名则保留 |
| workload identity | 工作负载身份 | 供应用/任务访问资源的身份 | 与人工用户身份区分 |
| container | 容器 | 具有隔离运行环境的应用单元 | `container` 字段保留原样 |
| image | 镜像 | 容器运行所用的软件包映像 | 镜像名和 tag 保留原样 |
| registry | 镜像仓库 | 存储与分发容器镜像的服务 | Windows Registry 应译“注册表” |
| pod | Pod | Kubernetes 最小调度单元 | 资源类型名保留英文 |
| node | 节点 | 集群中承载工作负载的机器 | Kubernetes `Node` 类型保留英文 |
| namespace | 命名空间 | Kubernetes 资源隔离范围 | `metadata.namespace` 保留原样 |
| cluster | 集群 | 协同工作的计算或服务节点集合 | 产品专名保留英文 |
| service mesh | 服务网格 | 处理服务间通信的基础设施层 | 与 Kubernetes `Service` 区分 |
| ingress | 入站流量；Ingress | 进入集群的流量或 Kubernetes 资源 | 资源类型 `Ingress` 保留英文 |
| egress | 出站流量 | 离开工作负载或集群的流量 | 与 ingress 区分 |
| autoscaling | 自动扩缩容 | 根据负载调整资源规模 | 缩容不能漏译 |
| rollout | 滚动发布；部署过程 | 逐步推出新版本的过程 | 具体控制器和策略按上下文判断 |
| rollback | 回滚 | 恢复先前版本或状态 | 不等于重新部署任意版本 |
| reconciliation | 状态协调 | 控制器持续使实际状态接近期望状态 | 不等于一般“和解” |
| desired state | 期望状态 | 声明式系统指定的目标状态 | 与 actual state（实际状态）区分 |
| observability | 可观测性 | 借助指标、日志、追踪理解系统状态的能力 | 不等于单一监控指标 |
