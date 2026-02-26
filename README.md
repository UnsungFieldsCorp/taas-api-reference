# UF Cloud API Reference

Public API reference documentation for the [UF Cloud](https://ufcloud.ai) platform.

## Contents

| File | Description |
|------|-------------|
| [api-reference.md](api-reference.md) | Complete API reference with request/response schemas and SDK examples |
| [libraries.md](libraries.md) | UF Cloud client library installation and usage guide |

## API Sections

| Section | Endpoints | Description |
|---------|-----------|-------------|
| Chat | `POST /openai/v1/chat/completions` | OpenAI-compatible chat completions |
| Responses | `POST /openai/v1/responses` | Response generation |
| Embeddings | `POST /openai/v1/embeddings` | Text embedding generation |
| Rerank | `POST /openai/v1/rerank` | Document reranking by relevance |
| Fine Tuning | `POST/GET /v1/fine-tuning/jobs` | Fine-tuning job management |
| Files | `POST/GET/DELETE /v1/files` | Training file upload and management |
| Batch | `POST/GET /v1/batch` | Batch job processing |
| Models | `GET /v1/models` | Model listing and retrieval |
| Images | `POST /openai/v1/images` | Image generation and manipulation |
| Audio | `POST /openai/v1/audio` | Audio transcription |
| Hardware | `GET /v1/hardware` | GPU hardware configurations and pricing |
| Dedicated Endpoints | `POST/GET/PATCH/DELETE /v1/endpoints` | Dedicated GPU endpoint lifecycle management |

## Client Libraries

| Language | Package | Install |
|----------|---------|---------|
| Python | [ufcloud-0.0.1-py3-none-any.whl](ufcloud-0.0.1-py3-none-any.whl) | `pip install ufcloud-0.0.1-py3-none-any.whl` |
| TypeScript | [ufcloud-0.0.1.tgz](ufcloud-0.0.1.tgz) | `npm install ufcloud-0.0.1.tgz` |

## Quick Start

```python
import os
from ufcloud import Ufcloud

client = Ufcloud(api_key=os.environ.get("UFCLOUD_API_KEY"))

response = client.chat.completions.create(
    model="openai/gpt-oss-120b",
    messages=[
        {"role": "user", "content": "Hello!"}
    ],
)
print(response.choices[0].message.content)
```

## Authentication

All API requests require a Bearer token in the `Authorization` header:

```
Authorization: Bearer <UFCLOUD_API_KEY>
```
