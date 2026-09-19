# 通用技术词库

仅当“适用语境/定义”与原句匹配时使用。领域词库和用户词库可在相同词义下覆盖本表；词义不同则分别翻译。

| English term | 建议中文译法 | 适用语境/定义 | 备注 |
| --- | --- | --- | --- |
| authentication | 身份认证；认证 | 验证主体身份 | 不等于 authorization |
| authorization | 授权 | 决定主体可执行的操作 | 不等于 authentication |
| credential | 凭证 | 证明身份或访问资格的数据 | 不一律译为“密码” |
| access token | 访问令牌；Access Token | OAuth 等访问授权凭据 | `access_token` 字段保留原样 |
| endpoint | 端点 | API 或网络服务的访问入口 | 若指设备末端，按上下文调整 |
| request body | 请求体 | HTTP 请求正文 | 不等于 header |
| response body | 响应体 | HTTP 响应正文 | 不等于 header |
| payload | 载荷 | 协议、消息或数据承载内容 | HTTP 正文常可译“请求体/响应体”；安全攻击语境见领域词库 |
| dependency | 依赖项 | 软件包或系统组件之间的依赖关系 | 非软件语境可译“依赖关系” |
| deployment | 部署 | 将软件或配置投入目标环境 | 不等于 release（发布） |
| availability | 可用性 | 服务可访问、可运行的程度 | 不等于 reliability（可靠性） |
| reliability | 可靠性 | 系统按预期持续工作的能力 | 不等于 availability |
| throughput | 吞吐量 | 单位时间完成的请求或数据量 | 保留单位 |
| latency | 延迟 | 请求或操作的耗时 | 与 duration、timeout 区分 |
| timeout | 超时；超时时间 | 达到等待期限，或该期限本身 | 按词性和句意选择 |
| rate limit | 速率限制 | 限制单位时间内的请求量 | `rate_limit` 标识符保留原样 |
| issue | 签发 | `issue a token/certificate` | GitHub Issue、法律争点等不适用 |
| issue | 问题；议题 | 讨论事项或故障 | 产品界面名称 `Issue` 可保留英文 |
| encode | 编码 | 用规则表示数据 | 不等于 encrypt（加密） |
| encrypt | 加密 | 使用密码算法保护数据机密性 | 不等于 encode（编码） |
