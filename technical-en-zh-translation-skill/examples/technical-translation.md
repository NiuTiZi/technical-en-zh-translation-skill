# 安全地部署 RAG 服务

推理服务使用工作负载身份从私有索引中检索文档。在执行检索前，它必须验证身份提供商签发的访问令牌。

攻击者可能在检索到的页面中植入提示词注入内容。应将页面文本视为不可信输入，不能让它覆盖系统提示词。检测规则可以标记可疑请求，但被标记的请求不一定意味着系统已失陷。

在 `config.yaml` 中，将 `max_tokens` 设为 `1024`。调查可能的误报时，保留 `request_id` 和原始 URL。然后运行 `kubectl apply -f config.yaml`。

```yaml
apiVersion: v1
metadata:
  name: rag-gateway
data:
  endpoint: "https://example.org/api"
  max_tokens: "1024"
```

详情请参阅[部署指南](https://example.org/docs/deploy#setup)。
