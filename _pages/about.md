#---
#permalink: /
# title: "허겸 | 포트폴리오"
#author_profile: true
#redirect_from:
#  - /about/
#  - /about.html
#---

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

**Cloud / Infrastructure**

**AWS (정적 배포)**
- Route 53 · CloudFront · S3로 프론트엔드 정적 배포 구성
- GitHub Actions를 통해 프론트는 S3, 백엔드는 ECR로 빌드·배포 파이프라인 분리

**AWS (EKS 멀티리전)**
- EKS 클러스터 기반 컨테이너 오케스트레이션 환경 구성 및 Karpenter 파드·노드 오토스케일링 적용
- RDS Aurora 멀티리전(서울↔일본) 복제 환경에서 지연시간·유실률 검증 및 트래픽 시뮬레이션 테스트 진행

**Terraform**
- AWS 인프라 구성 구조 이해 및 리소스 배포 흐름·상태 관리 학습

---

**Data Pipeline**

**Kafka**
-  토픽·파티션·리플리케이션 학습, 3노드 브로커 클러스터 구성 및 장애 발생 시 고가용성 동작 확인
-  토픽 단위 데이터 분리로 DB 저장·Spark 분석·ELK 모니터링 파이프라인 구현, 컨슈머 그룹별 독립 구조 설계

**Airflow**
-  EC2 환경에 Airflow 구축, Python Operator 사용한 Sensor·Connection·Hook 기반 DAG 작성 및 Slack 알림 구성
-  일일 배치 수집 → S3 저장 구현, 이후 규모 검토 후 Crontab으로 경량화

---

**Monitoring**

**Grafana / Prometheus**
- MLOps 프로젝트에서 Elasticsearch 연동으로 사용자 만족도 실시간 모니터링 및 불만족 30% 초과 시 모델 재학습 트리거 구성
- EKS 환경의 Karpenter 스케일링 지표 대시보드 시각화 및 CloudWatch 연동으로 AWS 리소스·RDS Aurora 통합 모니터링

**ELK**
- 빌드 시 발생하는 ERROR · WARN · FATAL 로그를 Elasticsearch · Kibana로 시각화
- 배포 위험도 측정 지표 활용 검토 (프로젝트 방향과 맞지 않아 미적용)