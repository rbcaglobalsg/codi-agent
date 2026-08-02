---
name: korean-security-audit
description: "한국어 보안 감사 — 시크릿 노출, 인젝션, 인증/인가, 의존성 취약점 스캔"
version: 1.0
language: ko
tags: [security, audit, vulnerability]
---

# 한국어 보안 감사

## 트리거
보안, security, 취약점, "점검해줘", audit, 스캔, "안전한가"

## 점검 항목

### 1. 시크릿 노출
- 코드 내 하드코딩된 API 키/토큰/비밀번호
- git history에 노출된 시크릿
- .env 파일 .gitignore 등록 여부
- 로그에 시크릿 출력 여부

### 2. 인젝션
- SQL 인젝션 (파라미터화 쿼리 사용 여부)
- XSS (사용자 입력 검증/이스케이프)
- 커맨드 인젝션 (shell=True 사용)
- 경로 조작 (../ traversal)

### 3. 인증/인가
- 비밀번호 해시 (bcrypt/argon2)
- JWT 만료 시간
- 세션 관리
- 권한 체크 누락

### 4. 의존성
- `pip audit` / `npm audit` 실행
- 알려진 CVE 취약점 확인
- 오래된 패키지 버전

### 5. 한국 특화
- 개인정보보호법 준수 (개인정보 암호화)
- 정보통신망법 (로그인 정보 보호)
- ISMS-P 인증 필요 시 추가 점검

## 도구
```bash
# Python
pip install bandit && bandit -r .
pip install safety && safety check

# JavaScript
npm audit
npx eslint --plugin security

# 시크릿 스캔
trufflehog filesystem .
```

## 리포트
```
## 보안 감사 결과

### 🔴 심각 (즉시 수정)
- [위치] 내용

### 🟡 경고
- [위치] 내용

### 🟢 양호
- 확인된 항목

### 점수: X/100
```
