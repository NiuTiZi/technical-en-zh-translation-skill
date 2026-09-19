# AI / LLM 领域词库

适用于机器学习、生成式 AI、模型服务与 Agent 文档。依语境选词；代码标识符保持原样。

| English term | 建议中文译法 | 适用语境/定义 | 备注 |
| --- | --- | --- | --- |
| inference | 推理 | 已训练模型生成预测或输出 | 不等于逻辑学一般“推断” |
| training | 训练 | 使用数据优化模型参数 | 与 inference 区分 |
| fine-tuning | 微调 | 在已有模型上继续训练以适配任务 | `fine_tuning` 字段不翻译 |
| embedding | 嵌入；向量嵌入 | 模型生成的向量表示 | 可按目标读者选择完整说法 |
| retrieval | 检索 | 从语料或索引中找出相关内容 | 不等于生成 |
| retrieval-augmented generation (RAG) | 检索增强生成（RAG） | 检索结果作为生成上下文的方法 | 首次出现可保留英文全称 |
| context window | 上下文窗口 | 模型一次可处理的上下文范围 | 不等于整个对话历史 |
| prompt | 提示词；Prompt | 输入给模型的指令或上下文 | 面向开发者可保留 `Prompt` |
| system prompt | 系统提示词 | 由系统角色提供的提示内容 | 不等于用户提示词 |
| token | Token；词元 | 模型分词及计费/上下文计量单位 | 与认证用访问令牌区分；按读者选用 |
| tokenizer | 分词器 | 将输入映射为 Token 的组件 | 具体实现未必按汉语词切分 |
| agent | Agent；智能体 | 可使用工具并执行多步骤任务的 AI 系统 | 不等于网络代理 `proxy` |
| tool call | 工具调用 | 模型或 Agent 调用外部工具 | API 标识符保持原样 |
| grounding | 依据外部信息生成；溯源约束 | 让输出基于给定资料或证据 | 具体译法随机制而变；避免笼统译“接地” |
| hallucination | 幻觉 | 模型输出缺乏事实依据或与证据不符 | 不应擅自推定所有错误均属幻觉 |
| temperature | 温度参数 | 控制采样随机性的参数 | `temperature` key 保留原样 |
| top-p sampling | Top-p 采样 | 按累计概率阈值选择候选 Token | `top_p` key 保留原样 |
| evaluation / eval | 评测；评估 | 对模型或应用表现进行测量 | `eval` 作为工具名或标识符时保留 |
