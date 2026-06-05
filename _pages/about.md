---
layout: archive
permalink: /
title: "원인을 계층 단위로 추적하는 인프라 엔지니어 허겸입니다."
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

한 계층에 머무르지 않고 시스템 전체를 보는 엔지니어로 성장하고 있습니다.

문제가 생기면 1단계별로 가설을 세워 원인을 좁혀가고,
팀원들과 소통하면서 함께 정리해 가는 과정을 중요하게 생각합니다.

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
| 2026.05 | [OpenStack 오픈소스 기여 — Upstream Merge ↗](https://review.opendev.org/c/openstack/openstacksdk/+/963982/8#message-b7c6c74e88490cc631c3c2667badfe5df80cc9dc) | 오픈소스 컨트리뷰션 아카데미 (OSSCA) |

---

## 기술 스택

### ☁ Cloud / Infrastructure

**AWS**
- EKS 클러스터 기반 컨테이너 오케스트레이션 환경 구성 및 Karpenter 파드·노드 오토스케일링 적용
- Aurora Global DB 멀티리전 구성, 트래픽 집중 시 쓰기 지연·데이터 유실 검증

**Terraform**
- AWS 인프라 구성 구조 이해 및 리소스 배포 흐름·상태 관리 학습

**CI/CD**
- Route 53 · CloudFront · S3로 프론트엔드 정적 배포 구성
- GitHub Actions를 통해 프론트는 S3, 백엔드는 ECR로 빌드·배포 파이프라인 분리

### ⚙ Data Pipeline

**Kafka**
- 토픽·파티션·리플리케이션 개념 학습 후 3-노드 클러스터로 구성해 장애 시 고가용성 동작 확인
- 토픽 단위로 데이터 형식을 분리해 중앙 허브 기능 구현, 컨슈머 그룹별 독립 구조 설계

**Airflow**
- EC2에 Airflow 구축, PythonOperator 기반으로 Sensor·Connection·Hook을 활용한 DAG 작성 및 Slack 알림 연동

### 📊 Monitoring

**Grafana / Prometheus**
- MLOps 프로젝트에서 Elasticsearch 연동으로 사용자 만족도 실시간 모니터링 및 불만족 30% 초과 시 모델 재학습 트리거 구성
- EKS 환경의 Karpenter 스케일링 지표 대시보드 시각화 및 CloudWatch 연동으로 AWS 리소스·RDS Aurora 통합 모니터링