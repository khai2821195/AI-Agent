---
title: Gemini Code Assist - 프로젝트 설정
tags:
  - 영역/AI_Agent
  - 유형/절차
created: 2026-05-10
updated: 2026-05-13
type: procedure
status: active
related:
  - "[[Gemini]]"
  - "[[AI 프롬프트 인덱스]]"
  - "[[지니 작업 지침]]"
---

# Gemini Code Assist - 프로젝트 설정

Gemini Code Assist의 **Project Instructions** 파일(`GEMINI.md`) 관련 설정 및 컨벤션 메모.

> [지니 보완] 원본은 Gemini Code Assist가 `C:\` 루트 프로젝트에 자동 생성한 빈 템플릿 파일임. 볼트 관련 컨벤션으로 내용을 보강하여 통합함.

---

## 개요

| 항목 | 내용 |
|------|------|
| 도구 | Google Gemini Code Assist (IDE 플러그인) |
| 설정 파일 | `GEMINI.md` (프로젝트 루트) |
| 생성일 | 2026-05-10 |
| 적용 범위 | C:\\ 루트 프로젝트 (로컬 개발 환경) |

---

## 프로젝트 컨벤션

> Gemini Code Assist에게 전달할 프로젝트 수준 지침을 여기에 기록합니다.

### 언어 및 커뮤니케이션
- 응답 언어: **한국어**
- 코드 주석: 한국어 가능, 변수명은 영어

### 코딩 스타일
- (프로젝트별 컨벤션 추가 예정)

### 도구 및 환경
- 주요 도구: n8n, Obsidian, Supabase, Notion
- 런타임: Node.js / Python
- 배포: Oracle Cloud (Docker)

---

## 관련 메모리 파일

| 파일 | 역할 |
|------|------|
| `GEMINI.md` | 팀 공유 프로젝트 컨벤션 (커밋 대상) |
| `GEMINI.md` (로컬) | 개인 로컬 설정 (커밋 제외) |
| Global Memory | 전역 사용자 선호도 |

---

## 참고

- [[Gemini]] — Gemini 프롬프트 허브
- [[AI 프롬프트 인덱스]] — 전체 AI 도구 프롬프트 인덱스
