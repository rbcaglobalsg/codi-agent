---
name: korean-doc-generation
description: "한국어 문서 자동 생성 — README, API 문서, 아키텍처 문서, 사용자 가이드"
version: 1.0
language: ko
tags: [documentation, readme, api-docs]
---

# 한국어 문서 자동 생성

## 트리거
"문서 만들어줘", README, API 문서, "설명서", "문서화", documentation

## 문서 타입별 생성

### 1. README.md
```markdown
# 프로젝트명
한 줄 설명

## 설치
\```bash
npm install  # 또는 pip install
\```

## 사용법
\```bash
명령어 예시
\```

## 기능
- 기능 1
- 기능 2

## 라이선스
MIT
```

### 2. API 문서
- 엔드포인트 목록
- 요청/응답 예시
- 에러 코드
- 인증 방법

### 3. 아키텍처 문서
- 시스템 구조도
- 데이터 흐름
- 기술 스택
- 의존성 관계

### 4. 사용자 가이드
- 설치부터 실행까지
- 스크린샷 포함
- FAQ
- 문제 해결

## 원칙
- 한국어 우선, 기술 용어는 영어 병기
- 코드 예시는 실행 가능한 것만
- "할 수 있습니다" → "합니다" 직접 표현
- 불필요한 장식 금지, 핵심만
