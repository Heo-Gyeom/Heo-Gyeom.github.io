---
permalink: /
title: "허겸 | 포트폴리오"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

## 자기소개

> 안녕하세요, **허겸**입니다.
>
> 여기에 간단한 자기소개를 작성해주세요. 본인의 관심 분야, 목표, 강점 등을 담아보세요.

---

## 학력

| 기간 | 학교명 | 전공 | 학위 |
|------|--------|------|------|
| 20XX.03 ~ 20XX.02 | 학교 이름 | 전공 이름 | 학사 |

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

**데이터 파이프라인**
- **Kafka** — 3노드 브로커 클러스터 구성 및 고가용성 검증 / 토픽 단위 데이터 파이프라인 구축 (DB · Spark · ELK)
- **Airflow** — DAG 기반 외부 시스템 연동 및 알림 구성 / 일일 배치 수집 → S3 저장

**모니터링**
- **Grafana / Prometheus** — 사용자 만족도 기반 모델 재학습 트리거 구성 / Karpenter 스케일링 및 RDS Aurora 상태 모니터링
- **ELK** — 빌드 로그(ERROR · WARN · FATAL) 시각화 및 배포 위험도 지표 검토

**클라우드 / 인프라**
- **AWS (정적 배포)** — Route 53 · CloudFront · S3 프론트 배포, GitHub Actions 기반 S3 · ECR CI/CD 구성
- **AWS (EKS 멀티리전)** — 서울↔일본 리전 RDS Aurora 복제 환경에서 지연시간·유실률 검증
- **Terraform** — AWS 인프라 구성 구조 이해 및 리소스 배포 흐름·상태 관리 학습