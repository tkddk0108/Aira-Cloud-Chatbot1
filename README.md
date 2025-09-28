# ☁️ Aira-1: 클라우드 퍼포먼스 최적화 프로젝트

> 기간: 2024.12.06 ~ 2025.01.15  
> 개인화 챗봇 서비스 **Aira**의 고가용성(High Availability) 및 확장성(Scalability) 아키텍처 구현 프로젝트

<img width="1429" height="1157" alt="image" src="https://github.com/user-attachments/assets/47428e29-816e-46b9-bf82-34e05a166a5b" />


---

## 🔧 프로젝트 개요

Aira-1은 OpenAI API 기반의 챗봇 서비스인 **Aira**를 AWS 환경에서 배포 및 운영하면서 **퍼포먼스를 최적화**하기 위해 수행한 클라우드 인프라 구축 프로젝트입니다.

- **목표**:  
  - EC2 중심 아키텍처에서의 고가용성 (HA), 트래픽 자동 확장 (ASG), 실시간 모니터링, 부하 테스트 등 도입
  - 최대 동시 접속 40명까지도 **안정적 성능 유지** 보장

---

## 🛠️ 주요 기술 스택 및 도구

| 항목 | 사용 기술 |
|------|-----------|
| 클라우드 인프라 | AWS EC2, ELB, Auto Scaling Group, S3, CodeDeploy |
| 백엔드 | FastAPI, OpenAI API 연동 |
| 프론트엔드 | HTML, CSS, JavaScript, Python 웹 연동 |
| 모니터링 | Prometheus (메트릭 수집), Grafana (시각화) |
| 부하 테스트 | Locust |
| 기타 | GitHub Actions, CloudWatch Logs |

---

## 🗂️ 아키텍처 구성

- **Region**: ap-northeast-2 (서울)
- **Subnet 구성**: 
  - Availability Zone 2a/2c 이중화
  - Public Subnet에 FE/BE 서버 분산
- **Auto Scaling Group**:
  - CPU 50% 초과 시 자동 인스턴스 증설
  - 80% 이하 유지 정책으로 자원 효율성 최적화
- **CI/CD**:
  - GitHub → S3 → CodeDeploy 자동 배포 파이프라인 구성

---

## 📊 성능 최적화 전략

- **Auto Scaling**: CPU 사용률에 따른 EC2 인스턴스 동적 증설
- **응답속도 개선**: 서버 과부하 시에도 70% 이상 응답속도 단축
- **부하 테스트**: Locust를 활용한 병목 구간 탐지 및 개선
- **실시간 모니터링**: Prometheus + Grafana로 시스템 상태 시각화 및 알림 구성

---

## ✅ 성과

- 최대 **40명 동시 접속** 환경에서도 안정적인 서비스 유지
- 트래픽 급증 시 자동 확장 및 복구 체계 검증 완료
- 백엔드/프론트엔드 분리 배포 구조로 유지보수 효율성 강화

---

## 📂 주요 역할 및 기여

| 구분 | 상세 내용 |
|------|-----------|
| 프론트엔드 개발 | HTML/CSS/JS로 UI 구성, Python 웹 서버 연동 |
| 백엔드 개발 | FastAPI 기반 OpenAI API 호출 로직 및 대화 히스토리 처리 |
| 모니터링 구축 | Prometheus로 메트릭 수집, Grafana로 대시보드 시각화 |
| 성능 테스트 | Locust로 병목 분석 및 리포트 기반 튜닝 |
| 문서 및 발표 자료 작성 | 전체 흐름 정리, PPT 발표 자료 및 보고서 작성 주도 |

---

## 🔗 관련 링크
- [📎 발표 자료 (Google Drive)](https://drive.google.com/file/d/1SdN00lI7PWEi2xb_oZ1uz0GM5x93x_4V/view?usp=drive_link)

---

## 📌 향후 개선 방향

- 서버리스(Fargate, Lambda)로의 전환 실험
- CloudFront CDN 적용을 통한 정적 리소스 최적화
- RDS 기반 DB 연결 및 세션 관리 강화

---

> 이 프로젝트는 AWS 기반 실무형 인프라 설계 및 운영 능력을 기르기 위한 핵심 사례로, 고가용성 아키텍처와 DevOps 체계를 직접 설계하고 테스트한 경험을 담고 있습니다.
