---
title: "배포맨 — CI/CD 통합 관리 시스템"
excerpt: "Jenkins·결재·일정 충돌 감지를 하나로 묶어 배포 운영 리스크를 줄인 플랫폼<br/><img src='/images/500x300.png'>"
collection: portfolio
date: 2025-02-01
---

## 한 줄 요약

> 배포 계획서 작성 → 복수 결재 → 일정 충돌 자동 감지 → Jenkins 실행 → 사후 보고까지,  
> **CI/CD 운영 전 과정을 하나의 플랫폼에서 관리**하는 시스템입니다.

---

## 프로젝트 개요

| | |
|---|---|
| **기간** | 2025.02 · 8주 |
| **팀** | 4인 (팀원) |
| **역할** | 담당 기능 기입 예정 |

### 왜 이 프로젝트인가

실제 운영 환경에서 배포 정보는 Jenkins 콘솔, 캘린더, 스프레드시트, 노션에 분산됩니다.  
이 파편화가 **일정 충돌, 승인 누락, 장애 대응 지연**으로 이어진다는 점에 주목했습니다.

| 현장의 문제 | 배포맨의 해결 |
|---|---|
| 운영 정보가 여러 도구에 분산 | 계획서·결재·빌드·로그·통계를 단일 플랫폼으로 통합 |
| 일정 충돌을 사람이 직접 체크 | 작업 금지 기간·기존 배포 일정과 충돌 자동 감지 |
| 배포 실패 원인 공유 어려움 | Gemini AI 기반 실패 로그 자동 분석 |

---

## 아키텍처

<!-- 아키텍처 이미지 추가 예정 -->
> 이미지를 `/images/baepooman-architecture.png` 경로에 업로드하면 아래에 표시됩니다.

```
[React Frontend — Vercel]
   ↓ REST API / SSE(실시간 로그)
[Spring Boot Backend — GCP VM]
   ↓                    ↓
[PostgreSQL]         [Redis] ← Jenkins 로그 캐싱 / 인증 토큰
   ↓
[Jenkins REST API] → 빌드 목록·파이프라인·콘솔 로그
```

---

## 내가 기여한 부분

> 담당 기능을 구체적으로 기입해주세요.  
> 아래는 팀 전체 기능 중 참고용 예시입니다.

### 예시 — Jenkins 실시간 로그 스트리밍

- Jenkins REST API를 폴링해 콘솔 로그를 SSE로 클라이언트에 스트리밍
- **지수 백오프(Exponential Backoff)** 적용으로 빌드 완료 시점까지 서버 부하 최소화
- Redis에 로그 캐싱 → 동일 로그 반복 조회 시 Jenkins 요청 없이 응답

---

## 트러블슈팅

> 본인이 직접 겪고 해결한 문제를 기입해주세요.  
> 형식: **상황 → 원인 → 해결** 순서로 작성하면 면접관이 읽기 쉽습니다.

### 예시 형식

**상황**: ~하는 과정에서 ~한 문제가 발생했습니다.

**원인**: ~이었습니다.

**해결**: ~으로 해결했습니다. (가능하면 수치 포함)

---

## 기술 스택

`Java 17` `Spring Boot` `Spring Security` `QueryDSL` `PostgreSQL` `Redis`  
`React` `TanStack Query` `Zustand` `Jenkins REST API` `Gemini API`  
`GCP` `Docker` `Vercel` `GitHub OAuth2` `JWT`

---

## 링크

- [GitHub 저장소](#) ← 추가 예정
- [시연 영상](#) ← 추가 예정
