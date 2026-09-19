# Secure RAG deployment

The inference service uses a workload identity to retrieve documents from a private index. It must validate the access token issued by the identity provider before running retrieval.

An attacker may place a prompt injection in a retrieved page. Treat page text as untrusted input; do not let it override the system prompt. A detection rule can flag suspicious requests, but a flagged request is not necessarily a compromise.

In `config.yaml`, set `max_tokens` to `1024`. Preserve `request_id` and the original URL when investigating a possible false positive. Then run `kubectl apply -f config.yaml`.

```yaml
apiVersion: v1
metadata:
  name: rag-gateway
data:
  endpoint: "https://example.org/api"
  max_tokens: "1024"
```

For more information, see the [deployment guide](https://example.org/docs/deploy#setup).
