---
name: korean-cicd
description: "한국어 CI/CD 파이프라인 — GitHub Actions, 빌드/테스트/배포 자동화"
version: 1.0
language: ko
tags: [ci-cd, automation, github-actions]
---

# 한국어 CI/CD 파이프라인

## 트리거
CI/CD, 파이프라인, 자동화, GitHub Actions, "배포 자동화", workflow

## 절차

### 1. GitHub Actions 워크플로우
```yaml
# .github/workflows/deploy.yml
name: 빌드 및 배포

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Python 설정
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - name: 의존성 설치
        run: pip install -r requirements.txt
      - name: 테스트 실행
        run: pytest -v --cov
  
  deploy:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - name: 배포
        run: |
          echo "배포 스크립트 실행"
```

### 2. 한국 시간 설정
```yaml
env:
  TZ: Asia/Seoul
```

### 3. 알림 연동
- Slack 웹훅
- Discord 웹훅
- 카카오톡 (제한적)
- 이메일 (SMTP)

### 4. 배포 전략
- **블루-그린**: 무중단 배포
- **카나리**: 점진적 배포 (5% → 50% → 100%)
- **롤백**: 자동 롤백 조건 설정

## 체크리스트
- [ ] 시크릿은 GitHub Secrets 사용
- [ ] 테스트 실패 시 배포 중단
- [ ] 빌드 캐시 사용 (속도 향상)
- [ ] 병렬 실행 (jobs 분리)
- [ ] 한국 시간 기준 cron: `0 9 * * *` (KST 18:00)
