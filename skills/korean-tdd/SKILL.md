---
name: korean-tdd
description: "한국어 TDD 가이드 — RED-GREEN-REFACTOR 순서, 테스트 코드부터 작성"
version: 1.0
language: ko
tags: [testing, tdd, quality]
---

# 한국어 TDD (테스트 주도 개발)

## 트리거
테스트 작성, TDD, "테스트 만들어줘", "TDD로 해줘", 테스트 코드

## 절차

### 1. RED — 실패하는 테스트 먼저
- 요구사항을 테스트로 표현
- 아직 구현이 없으므로 테스트는 실패해야 함
- 한국어 테스트명: `def test_주문_총액이_올바른지():`

### 2. GREEN — 최소 구현으로 통과
- 테스트를 통과하는 최소 코드 작성
- 과도한 추상화 금지
- "작동하는 코드"가 우선

### 3. REFACTOR — 개선
- 중복 제거
- 함수 분리
- 성능 개선
- 테스트는 여전히 통과해야 함

## 한국 특화
- pytest: `pytest -v --cov` (커버리지 포함)
- Django: `python manage.py test`
- Spring: `./gradlew test`
- 프론트엔드: `jest` 또는 `vitest`

## 주의사항
- 테스트 없는 코드는 레거시다
- Mock 남용 금지 — 실제 동작 검증 우선
- 테스트 커버리지 80% 이상 권장
