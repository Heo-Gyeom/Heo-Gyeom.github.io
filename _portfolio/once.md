---
title: "GlobalNews AI — 멀티리전 DR 자동화 플랫폼"
excerpt: "카카오 화재 사태의 실패 원인 3가지를 AWS로 직접 해결한 DR 자동화 시스템<br/><img src='/images/500x300.png'>"
collection: portfolio
date: 2025-04-01
---

## 한 줄 요약

> GNews API로 수집한 해외 뉴스를 AWS Bedrock(Claude)이 번역·요약하는 서비스 위에,  
> **서울 리전 장애 시 도쿄 리전으로 자동 전환되는 멀티리전 DR 시스템**을 구현하고 수치로 검증했습니다.

---

## 프로젝트 개요

| | |
|---|---|
| **기간** | 2025.04 · 5주 |
| **팀** | 6인 (팀장) |
| **역할** | CI/CD 설계, 서비스 서빙, 데이터 정합성 검증, DR 시나리오 전체 |

### 왜 이 프로젝트인가

2022년 카카오 데이터센터 화재로 대규모 서비스 장애가 발생했고, 사후 분석에서 세 가지 구조적 원인이 드러났습니다.

| 카카오의 실패 원인 | 이 프로젝트의 해결 방식 |
|---|---|
| 수동 전환 의존 | AWS Step Functions로 Failover 오케스트레이션 **자동화** |
| 물리적 미분리 | 서울(Active) + 도쿄(Standby) **멀티리전 분리** |
| DR 사이클 미검증 | Aurora Managed Switchback으로 Failback까지 **전체 사이클 자동화 및 실측 검증** |

---

## 아키텍처

<!-- 아키텍처 이미지 추가 예정 -->
> 이미지를 `/images/once-architecture.png` 경로에 업로드하면 아래에 표시됩니다.

```
[사용자]
   ↓ Route 53 Health Check
[CloudFront]
   ↓ Origin Failover
[EKS — 서울 Active] ←── 장애 감지 ──→ [EKS — 도쿄 Standby]
   ↓                                         ↓
[Aurora PostgreSQL Global DB] ← 복제(RPO < 1초) →
   ↓
[Step Functions] → Failover 오케스트레이션
```

---

## 내가 기여한 부분

### 1. CI/CD 파이프라인 — 리전 장애에 독립적인 배포 구조

- **GitHub Actions를 CI 서버로 선택한 이유**: AWS 리전 장애 범위 밖에 배치해 서울 리전이 완전히 다운된 상황에서도 긴급 배포가 가능하도록 설계
- Source 레포 ↔ Manifest 레포를 분리하고 ArgoCD(GitOps)로 서울·도쿄 EKS에 일관된 배포 자동화

### 2. DR 시나리오 설계 및 실행

- Route 53 Health Check + CloudWatch 알람으로 서울 리전 장애 **자동 감지**
- Step Functions가 감지 즉시 Failover 오케스트레이션 실행 → **사람 개입 없이** 도쿄로 전환
- Aurora Global DB Managed Switchback으로 Failback 시에도 복제 관계 유지
- Failover → Failback 전체 DR 사이클을 코드로 관리하고 **반복 검증**

### 3. 데이터 정합성 검증

- Failover·Failback 전후 레코드 수 비교 + 해시 검증으로 데이터 무결성 **100% 수치 증명**
- AuroraGlobalDBReplicationLag 메트릭으로 RPO 실시간 측정

---

## 측정 결과

| 지표 | 목표 | 실측 |
|---|---|---|
| Failover RTO | < 5분 | **4분 23초** ✅ |
| Failback RTO | < 20분 | 측정값 기입 예정 |
| RPO | < 1초 | **< 1초** ✅ |
| 데이터 정합성 | 100% | **100%** ✅ |

---

## 트러블슈팅

### Failback 후 복제 방향이 역전되는 문제

**상황**: Aurora Global DB에서 Failover 후 도쿄가 Writer가 된 상태에서 Failback 시, Managed Switchback을 쓰지 않으면 복제 관계가 끊겨 데이터 불일치 위험 발생

**원인**: 일반적인 수동 Promote 방식은 복제 토폴로지를 재구성하지 않아 Failback 이후 서울이 단독 클러스터로 남음

**해결**: Aurora Global Database의 **Managed Switchback** API를 활용해 복제 관계를 유지한 채로 Writer 권한만 서울로 복귀. Failback 전후 해시 검증으로 정합성 확인

---

### Karpenter 노드 프로비저닝 지연으로 Failover 시 트래픽 급증 대응 실패

**상황**: 도쿄 Standby 클러스터에 최소 Pod만 유지했더니 Failover 시 스케일업 지연으로 초기 요청 실패율 급등

**해결**: 도쿄 클러스터에 최소 Pod 수를 상시 유지하도록 HPA 설정 조정. Karpenter NodePool에 warm 노드 1대 예약해 스케일업 대기 시간 제거

---

## 기술 스택

`AWS EKS` `Aurora PostgreSQL Global DB` `Route 53` `Step Functions` `CloudFront`  
`Terraform` `GitHub Actions` `ArgoCD` `Karpenter` `Prometheus` `Grafana` `CloudWatch`  
`AWS Bedrock (Claude)` `Spring Boot` `React`

---

## 링크

- [GitHub 소스 레포](#) ← 추가 예정
- [GitHub Manifest 레포](#) ← 추가 예정
