---
name: korean-deploy
description: "한국어 배포 가이드 — Docker, Kubernetes, AWS/GCP/Azure, Vercel/Netlify 배포 자동화"
version: 1.0
language: ko
tags: [deploy, devops, ci-cd]
---

# 한국어 배포 가이드

## 트리거
배포, deploy, "배포해줘", "올려줘", CI/CD, Docker, 쿠버네티스

## 절차

### 1. 배포 전 체크
- [ ] 환경변수 확인 (.env, secrets)
- [ ] 빌드 성공 확인
- [ ] 테스트 통과 확인
- [ ] 시크릿 노출 확인 (git history)
- [ ] 한국 시간 기준 배포 시간 선택 (트래픽 적은 시간)

### 2. 컨테이너화 (Docker)
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "main.py"]
```

### 3. CI/CD 파이프라인
- GitHub Actions: `.github/workflows/deploy.yml`
- 빌드 → 테스트 → 배포 자동화
- 한국 시간(Asia/Seoul) cron 설정

### 4. 플랫폼별 배포
- **Vercel/Netlify**: 프론트엔드, 정적 사이트
- **AWS/GCP/Azure**: 백엔드, 컨테이너
- **Cloudflare Pages**: 정적 + 엣지 함수
- **한국 클라우드**: 네이버 클라우드, 카카오 i 클라우드

### 5. 배포 후 검증
- 헬스체크 엔드포인트 확인
- 로그 에러 확인
- 모니터링 알림 설정

## 주의사항
- .env 파일은 절대 커밋하지 않음
- 배포 전 백업 필수
- 블루-그린 또는 카나리 배포 권장
