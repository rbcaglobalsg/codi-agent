# 코디(Codi) — 대화하며 성장하는 AI 코딩 동반자

> 처음이든, 고수든 — 코디와 함께 성장하세요.

코디는 **대화할수록 진화하는** AI 에이전트 OS입니다. 사용자와의 모든 대화에서 학습하고, 해결한 문제를 스킬로 저장하며, 점점 더 사용자에게 최적화됩니다.

Hermes Agent (MIT, Nous Research)를 기반으로 한국 개발자와 일반인을 위해 완전 한국어화했습니다.

## 핵심 특징

- 🧠 **대화할수록 진화** — 해결한 문제를 스킬로 자동 저장, 같은 질문은 두 번 다시 처음부터 안 함
- 🔑 **자기 API 키** — OpenRouter, OpenAI, Anthropic, DeepSeek, 로컬 모델. 특정 회사 종속 없음
- 🇰🇷 **완전 한국어** — 프롬프트, 에러, 설명, 도움말 전부 한국어. 기술 용어는 한국어+영어 병기
- 💬 **어디서나 대화** — 터미널, 카카오톡, 텔레그램, 디스코드, 슬랙. 같은 에이전트가 모든 플랫폼에서
- ⚡ **개발자 특화 스킬** — 코드 리뷰, 배포, 디버깅, TDD, CI/CD, 보안 감사
- 🎓 **초보자도 OK** — "코딩 배우고 싶어"부터 "배포 자동화해줘"까지 수준에 맞춰 적응

## 빠른 시작

### 직접 설치 (무료)

```bash
# 저장소 클론
git clone https://github.com/rbcaglobalsg/codi-agent.git
cd codi-agent

# 설치
pip install -e .

# API 키 설정
export OPENROUTER_API_KEY=sk-or-v1-xxxxx

# 실행
codi
```

### 클라우드 (준비 중)

가입만 하면 바로 사용. 서버 설정, API 키 관리 불필요.
카카오톡에서 바로 대화 시작.

## LLM 프로바이더 연결

자기 API 키를 사용 — 특정 회사에 종속되지 않습니다.

```yaml
# config.yaml
provider: openrouter          # 또는 openai, anthropic, deepseek, lmstudio
api_key: sk-or-v1-xxxxx      # 자기 API 키
model: anthropic/claude-sonnet-4  # 또는 gpt-4o, deepseek-chat 등
```

| 프로바이더 | 입문 | 추천 모델 | 비용 (1M 토큰) |
|---|---|---|---|
| OpenRouter | 가입 즉시 | 다중 모델 | 모델별 상이 |
| OpenAI | 널리 알려짐 | gpt-4o | $2.5 / $10 |
| Anthropic | 코딩 특화 | claude-sonnet-4 | $3 / $15 |
| DeepSeek | 최저가 | deepseek-chat | $0.14 / $0.28 |
| 로컬 (Ollama) | 무료 | 제한적 | 무료 (하드웨어 필요) |

## 한국 개발자 스킬

코디는 처음부터 한국 개발 환경에 맞춘 스킬을 내장합니다:

| 스킬 | 설명 |
|---|---|
| `korean-code-review` | 보안/성능/가독성 종합 코드 리뷰 |
| `korean-tdd` | RED-GREEN-REFACTOR 테스트 주도 개발 |
| `korean-deploy` | Docker, Kubernetes, 클라우드 배포 |
| `korean-debugging` | 4단계 체계적 디버깅 |
| `korean-beginner-guide` | 코딩 입문자 가이드 |
| `korean-api-key-setup` | LLM API 키 설정 |
| `korean-git-workflow` | Git/GitHub 워크플로우 |
| `korean-security-audit` | 보안 취약점 스캔 |
| `korean-doc-generation` | README, API 문서 자동 생성 |
| `korean-kakao-bot` | 카카오톡 채널 봇 연동 |
| `korean-cicd` | CI/CD 파이프라인 자동화 |

### 스킬 직접 만들기

```markdown
---
name: my-skill
description: "내 스킬 설명"
---

# 스킬 내용
여기에 절차를 적습니다. 코디가 이 스킬을 로드해서 실행합니다.
```

파일을 `skills/my-skill/SKILL.md`에 저장하면 자동으로 인식됩니다.

## 카카오톡 연동 (준비 중)

```
카카오톡 채널
    ↓ 웹훅
코디 서버 (FastAPI)
    ↓ 사용자별 세션
LLM (사용자 API 키)
    ↓ 스킬 저장/로드
사용자별 메모리 DB
```

사업자등록 후 카카오 비즈니스 채널을 통해 연동 가능합니다.

## 직접 설치 vs 클라우드

| 구분 | 직접 설치 (무료) | 클라우드 (유료) |
|---|---|---|
| 비용 | 무료 (LLM API 비용만) | 월 구독 + LLM 비용 |
| 서버 | 자기 서버 필요 | 불필요 |
| 설정 | 직접 | 자동 |
| 카카오톡 | 직접 구축 | 1클릭 연동 |
| 업데이트 | 직접 | 자동 |
| 지원 | 커뮤니티 | 우선 지원 |
| 스킬 | 직접 관리 | 마켓플레이스 |

## 라이선스

MIT License — Hermes Agent by Nous Research 기반.
자유롭게 사용, 수정, 배포 가능.

## 기여

스킬, 버그 리포트, 기능 제안 환영합니다.
