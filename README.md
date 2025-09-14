# 인프라 템플릿

이 저장소는 백엔드와 프론트엔드를 연결하는 인프라 설정을 관리합니다.

## 구조
```
infra-template/
├── docker-compose.yml      # 전체 서비스 오케스트레이션
├── nginx/
│   └── conf.d/
│       └── default.conf    # nginx 프록시 설정
└── README.md
```

## 사용법

### 1. 이미지 빌드 (각 프로젝트에서)
```bash
# backend-template에서
docker build -t backend-template:latest .

# frontend-template에서
docker build -t frontend-template:latest .
```

### 2. 전체 서비스 실행
```bash
docker-compose up -d
```

## 접속 정보
- **메인 서비스**: http://localhost
- **프론트엔드 직접**: http://localhost:3000
- **백엔드 API 직접**: http://localhost:8080

## 라우팅 규칙
- `/api/*` → 백엔드 (Spring Boot)
- `/*` → 프론트엔드 (React/Vue 등)

## 환경별 배포
- `docker-compose.yml`: 로컬/개발 환경
- 운영 환경: Kubernetes, Docker Swarm 등으로 확장 가능# Inven_infra
