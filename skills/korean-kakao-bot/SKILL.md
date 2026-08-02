---
name: korean-kakao-bot
description: "카카오톡 채널 봇 연동 — 카카오 i 챗봇, 스킬 서버, 자동 응답 설정"
version: 1.0
language: ko
tags: [kakao, bot, integration]
---

# 카카오톡 채널 봇 연동

## 트리거
카카오, 카톡, kakao, 채널 봇, "카카오톡 연동", 챗봇

## 전제조건
- 사업자등록증 (카카오 비즈니스 채널 필요)
- 카카오 개발자 계정 (developers.kakao.com)

## 절차

### 1. 카카오 i 챨봇 설정
1. https://i.kakao.com 접속
2. 새 챗봇 생성
3. 시나리오 설계
4. 스킬 서버 URL 등록 (HTTPS 필수)

### 2. 스킬 서버 구현
```python
from fastapi import FastAPI, Request
import json

app = FastAPI()

@app.post("/chat")
async def chat(request: Request):
    body = await request.json()
    user_input = body["userRequest"]["utterance"]
    
    # 에이전트 호출
    response = call_agent(user_input)
    
    return {
        "version": "2.0",
        "template": {
            "outputs": [{"simpleText": {"text": response}}]
        }
    }
```

### 3. 카카오 채널 연결
1. 비즈니스 채널 생성
2. 챗봇을 채널에 연결
3. 친구 추가 링크 생성

### 4. 웹훅 설정
- HTTPS 엔드포인트 필수
- 응답 시간 5초 이내
- 실패 시 재시도 로직

## 주의사항
- 사업자등록 없이는 비즈니스 채널 불가
- 개인 채널은 챗봇 연동 제한
- 응답 시간 5초 제한 — 긴 작업은 비동기 처리
- 한국어 자연어 처리 필수
