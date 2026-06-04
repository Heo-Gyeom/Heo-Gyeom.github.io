---
permalink: /
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

> 안녕하세요, 포기하지 않는 엔지니어 **허겸**입니다..
> DB부터 인프라까지, 다양한 계층에서 가설을 세우고 원인을 추적하는 엔지니어로 성장하고 있습니다.
> 문제가 생기면 바로 결론을 내기보다, 단계별로 가설을 세우며 원인을 확인합니다.
> 하나의 계층만 보지 않고 다양한 관점에서 접근하며, 팀원들과 소통하면서 함께 정리해 가는 과정을 중요하게 생각합니다.

---

---

## 자격증

| 취득일 | 자격증명 | 발급기관 |
|--------|----------|----------|
| 2026.02.13 | AWS Certified Solutions Architect – Associate | Amazon Web Services |
| 2026.05.29 | Red Hat Certified System Administrator (RHCSA) | Red Hat |

---

## 교육 내역

| 기간 | 교육명 | 기관 |
|------|--------|------|
| 2024.04 ~ 2025.11 | AI 기술인력 양성 이어드림스쿨 | 중소벤처기업부 |
| 2025.06 ~ 2025.11 | 공공SI SW개발자 양성과정 | 한국소프트웨어산업협회 |
| 2025.12 ~ 2026.05 | 클라우드 DevOps 엔지니어 양성과정 | 청년취업사관학교 (SeSAC) |

---

## 활동 내역 및 수상

| 기간 | 활동명 / 수상명 | 기관 |
|------|----------------|------|
| 2025.11 | 공공SI SW개발자 양성과정 최종 프로젝트 장려상 | 한국소프트웨어산업협회 |
| 2026.05 | OpenStack 오픈소스 기여 (Upstream Merge) | 오픈소스 컨트리뷰션 아카데미 (OSSCA) |

---

## 기술 스택

**Cloud / Infrastructure**

**AWS**
- EKS 클러스터 기반 컨테이너 오케스트레이션 환경 구성 및 Karpenter 파드·노드 오토스케일링 적용
- Aurora Global DB 멀티리전(서울↔도쿄) 구성, 트래픽 집중 시 쓰기 지연·데이터 유실 검증

**Terraform**
- AWS 인프라 구성 구조 이해 및 리소스 배포 흐름·상태 관리 학습

**CI/CD**
- Route 53 · CloudFront · S3로 프론트엔드 정적 배포 구성
- GitHub Actions를 통해 프론트는 S3, 백엔드는 ECR로 빌드·배포 파이프라인 분리

---

**Data Pipeline**

**Kafka**
-  토픽·파티션·리플리케이션 학습, 3노드 브로커 클러스터 구성 및 장애 발생 시 고가용성 동작 확인
-  토픽 단위 데이터 분리로 DB 저장·Spark 분석·ELK 모니터링 파이프라인 구현, 컨슈머 그룹별 독립 구조 설계

**Airflow**
-  EC2 환경에 Airflow 구축, Python Operator 사용한 Sensor·Connection·Hook 기반 DAG 작성 및 Slack 알림 구성

---

**Monitoring**

**Grafana / Prometheus**
- MLOps 프로젝트에서 Elasticsearch 연동으로 사용자 만족도 실시간 모니터링 및 불만족 30% 초과 시 모델 재학습 트리거 구성
- EKS 환경의 Karpenter 스케일링 지표 대시보드 시각화 및 CloudWatch 연동으로 AWS 리소스·RDS Aurora 통합 모니터링