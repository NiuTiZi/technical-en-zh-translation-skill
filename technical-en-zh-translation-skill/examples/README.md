# 示例说明

- [`technical-source.md`](technical-source.md)：一段同时涉及 AI、身份安全和 Kubernetes 的英文文档。
- [`technical-translation.md`](technical-translation.md)：遵循本 Skill 的简体中文译文。代码块、命令、路径、配置 key 和 URL 保持不变。
- [`custom-glossaries/legal.md`](custom-glossaries/legal.md)：独立法律领域词库示例，展示语境限定和跨领域同词异义。

将下面的请求和 [`technical-source.md`](technical-source.md) 一起提供给支持 Skills 的助手，可观察领域词库如何按语境协作：

```text
使用 $technical-en-zh-translation-skill，将附件译成简体中文。
读者是负责部署 RAG 服务的后端和安全工程师。
保留 Markdown 结构、代码和技术标识符。
```

自定义词库示例：

```text
使用 $technical-en-zh-translation-skill，并参考 examples/custom-glossaries/legal.md。
把下面两句译成简体中文：

The consideration under this agreement is payable within 30 days.
Security considerations include credential rotation.
```

预期第一句中的 `consideration` 在该合同语境下译为“对价”；第二句的 `considerations` 是“考虑因素”。词库不是全局替换表，且 `credential` 按技术语境译为“凭证”。
