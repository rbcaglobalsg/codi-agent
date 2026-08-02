---
name: korean-api-key-setup
description: "한국어 LLM API 키 설정 가이드 — OpenRouter, OpenAI, Anthropic, 로컬 모델 연결"
version: 1.0
language: ko
tags: [setup, api, llm, configuration]
---

# LLM API 키 설정 가이드

## 트리거
API 키, setup, "모델 연결", "OpenRouter 설정", "OpenAI 키", API 연결, 프로바이더

## 지원 프로바이더

### OpenRouter (추천 — 다중 모델)
1. https://openrouter.ai 가입
2. API 키 발급 (Settings → Keys)
3. 설정:
```yaml
provider: openrouter
api_key: sk-or-v1-xxxxx
model: anthropic/claude-sonnet-4  # 또는 openai/gpt-4o 등
```

### OpenAI
```yaml
provider: openai
api_key: sk-xxxxx
model: gpt-4o
```

### Anthropic
```yaml
provider: anthropic
api_key: sk-ant-xxxxx
model: claude-sonnet-4
```

### DeepSeek (저비용)
```yaml
provider: deepseek
api_key: xxxx
model: deepseek-chat
```

### 로컬 모델 (Ollama/LM Studio)
```yaml
provider: lmstudio
base_url: http://localhost:1234/v1
model: local-model
```

## 비용 비교 (1M 토큰 기준)
| 프로바이더 | 모델 | 입력 | 출력 |
|---|---|---|---|
| OpenRouter | claude-sonnet-4 | $3 | $15 |
| OpenAI | gpt-4o | $2.5 | $10 |
| DeepSeek | deepseek-chat | $0.14 | $0.28 |
| 로컬 | (무료, 하드웨어 필요) | - | - |

## 주의사항
- API 키는 .env 파일에만 저장, git 커밋 금지
- .env가 .gitignore에 있는지 확인
- 키 노출 시 즉시 회수/재발급
- 한국 결제: OpenRouter/OpeAI 해외 카드 필요, DeepSeek 지원 확인
