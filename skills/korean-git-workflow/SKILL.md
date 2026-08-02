---
name: korean-git-workflow
description: "한국어 Git/GitHub 워크플로우 — 커밋, 브랜치, PR, 머지, 충돌 해결"
version: 1.0
language: ko
tags: [git, github, version-control]
---

# 한국어 Git 워크플로우

## 트리거
git, 깃, 커밋, 브랜치, PR, 풀리퀘스트, 머지, 충돌, "올려줘"

## 기본 워크플로우

### 1. 브랜치 생성
```bash
git checkout -b feature/기능명
# 예: feature/login-api
```

### 2. 커밋 규칙
한국어 커밋 메시지 권장:
```
[타입] 간결한 설명

타입:
- feat: 새 기능
- fix: 버그 수정
- docs: 문서
- refactor: 리팩토링
- test: 테스트
- chore: 잡일

예: feat: 로그인 API 추가
예: fix: 결제 오류 수정 (#123)
```

### 3. PR (Pull Request)
```bash
git push origin feature/기능명
# GitHub에서 PR 생성
```

PR 템플릿:
```
## 변경 사항
- 무엇을 변경했는지

## 테스트
- 어떻게 테스트했는지

## 체크리스트
- [ ] 테스트 통과
- [ ] 코드 리뷰 반영
- [ ] 문서 업데이트
```

### 4. 충돌 해결
```bash
git fetch origin
git merge origin/main
# 충돌 파일 수정
git add .
git commit -m "fix: 충돌 해결"
```

### 5. 머지 후 정리
```bash
git checkout main
git pull origin main
git branch -d feature/기능명  # 로컬 브랜치 삭제
```

## 주의사항
- main 브랜치 직접 커밋 금지
- 커밋 전 git status 확인
- .env, node_modules 등은 .gitignore에 추가
- 한국 시간 기준: KST = UTC + 9
