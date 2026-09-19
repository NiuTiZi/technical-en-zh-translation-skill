# Technical EN→ZH Translation Skill

将英文技术文档翻译成准确、术语一致、读起来自然的简体中文。内置计算机通用、AI/LLM、网络安全与云原生词库；法律、生物、金融等领域可按需添加。入口是 [`SKILL.md`](SKILL.md)，无需脚本或在线服务。

## 特点

- **语义优先**：先判断词在当前句子中的含义，再应用词库；不机械套词。
- **保护技术标识**：默认原样保留代码块、命令、路径、API 名称、JSON/YAML key、协议缩写等。
- **可扩展词库**：支持随请求附带词库、项目内词库，以及向仓库贡献通用领域词库。
- **保留文档结构**：尽量维持标题、列表、表格、链接、代码块和交叉引用。

## 项目结构

```text
technical-en-zh-translation-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── references/
│   ├── style-guide.md
│   ├── general-glossary.md
│   ├── domain-template.md
│   └── domains/
│       ├── ai-llm.md
│       ├── cybersecurity.md
│       └── cloud-native.md
└── examples/
    ├── README.md
    ├── technical-source.md
    ├── technical-translation.md
    └── custom-glossaries/
        └── legal.md
```

## 安装与使用

1. 下载本仓库或 ZIP，并将整个 `technical-en-zh-translation-skill` 文件夹放进你的 Skills 目录。例如，Codex 用户可放在 `~/.codex/skills/`；Windows 通常为 `%USERPROFILE%\.codex\skills\`。也可在支持 `SKILL.md` 的环境中按其说明安装。
2. 在支持 Skills 的会话里发出请求。需要显式调用时，可写 `$technical-en-zh-translation-skill`。

```text
使用 $technical-en-zh-translation-skill，把下列英文文档译成简体中文。
读者是后端工程师；保留 Markdown 结构和所有代码块。

[在这里粘贴英文原文]
```

安装后也可直接提供文件，并注明目标读者、期望语气、需要保留的格式和适用领域。默认仅输出译文；遇到会影响含义且无法可靠判断的歧义时，会附简短译者注。

## 自定义领域词库

推荐将个人或团队词库放在当前项目的 `.technical-en-zh/domains/`，例如 `.technical-en-zh/domains/legal.md`。也可以在请求中附上词库文件或其路径。若要随 Skill 分享新领域，请在 `references/domains/` 中添加文件并提交 Pull Request。文件名用小写英文及连字符，例如 `molecular-biology.md`。

每个词库按 [`references/domain-template.md`](references/domain-template.md) 的表格编写。**一行对应一个明确的词义和语境**；多义词使用多行，而不是用斜杠塞入多个候选译法。列包括英文术语、建议中文译法、适用语境/定义、备注。对不应翻译的名称，在中文译法栏写“保留英文”，并在备注中说明原因。请为易混淆词提供反例或排除语境。可参照 [`examples/custom-glossaries/legal.md`](examples/custom-glossaries/legal.md)。

使用时只读取与当前文档相关的词库。一个文档涉及多个行业时，可在请求里指定领域优先级，例如“这是一份医疗器械合同：法律术语优先于生物术语”。领域优先级只解决同一语境下同级词库的冲突，不得改变原文含义。

### 术语优先级与冲突处理

最高约束是**上下文正确性**与技术标识保护。对于确实匹配的词义，按下列顺序选择译法：

1. 本次请求明确指定的译法。
2. 本次提供的用户词库。
3. 项目 `.technical-en-zh/domains/` 中的词库。
4. Skill 自带的相关领域词库。
5. 通用词库。
6. 行业常见用法及一般翻译习惯。

若同级词库有冲突，先选定义和上下文最贴合的一项，再按用户指定的领域优先级处理。仍无法确定时保留英文，并以简短译者注说明歧义。若词库项与原文语义明显冲突，跳过该项；不要为了“统一术语”译错。

例如，`issue a token` 中的 `issue` 是“签发”，`GitHub issue` 应保留产品界面用语或按上下文译为“议题”；法律文书中的 `issue` 又可能是“争点”。词条必须说明适用语境。

## 翻译约定

详见 [`references/style-guide.md`](references/style-guide.md)。默认原样保留代码、命令、参数、路径、URL、IP、域名、标识符、产品名、协议缩写以及代码块中的内容。可翻译 Markdown 链接的显示文字，但链接目标不变。首次出现的重要专业词可写成“中文（English）”，后续按文档需要保持一致。

## 贡献与许可

欢迎改进译法、增加领域词库和补充真实语境示例。提交前请阅读 [`CONTRIBUTING.md`](CONTRIBUTING.md)。项目采用 [MIT License](LICENSE)。

## English quick start

Copy this folder into your agent's Skills directory. Invoke `$technical-en-zh-translation-skill` with English source text or a document, and state the audience and domain when useful. For custom terminology, attach a Markdown glossary or place one under the active project's `.technical-en-zh/domains/`. Contextual meaning takes priority over every glossary entry; code and technical identifiers remain unchanged by default.
