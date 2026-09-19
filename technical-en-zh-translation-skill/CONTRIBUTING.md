# 贡献指南

欢迎提交 Issue 或 Pull Request，改进翻译规则、已有词条、领域词库和示例。

## 提交范围

- 修正有明确语境证据的译法；在 PR 中说明原句、适用场景及修正理由。
- 新增领域词库时，从 [`references/domain-template.md`](references/domain-template.md) 复制结构，放在 `references/domains/<domain>.md`。只加入该领域高频、易误译或需要明确边界的词；避免堆积普通词典条目。
- 多义词分别列项，写清定义与排除语境。保留英文的术语也须解释理由。
- 尽量提供可公开使用、由你自己编写的短例句；不要粘贴受版权保护的整段原文或敏感资料。
- 若调整通用规则，请同时检查三个内置领域词库和 `examples/` 是否仍一致。

## 质量检查

1. 确认 `SKILL.md` 的 YAML frontmatter 包含 `name` 和 `description`，且所有相对链接有效。
2. 核对示例译文与原文：否定、条件、程度、数量和安全边界应保持一致；代码、命令、路径、标识符不能改变。
3. 对新增词条检查同一英文词在其他领域的不同含义；如可能冲突，在“适用语境/定义”栏写清边界。
4. 保持 Markdown 表格可读，并在 PR 描述中写明你验证的文档类型或例句。

建议使用简洁的 PR 标题，例如 `glossary: add biology terms` 或 `style: clarify token capitalization`。项目没有构建步骤；文档与示例的语义检查比机械匹配字词更重要。

提交内容按仓库的 [MIT License](LICENSE) 发布。参与讨论时请尊重不同地区和行业已有的合理术语习惯。
