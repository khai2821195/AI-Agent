---
title: Gemini
model: Gemini
tags:
  - 영역/AI_Agent
  - 유형/참고
  - AI
  - Gemini
  - 프롬프트
created: 2026-05-10
updated: 2026-05-13
type: concept
status: active
related:
  - "[[AI 프롬프트 인덱스]]"
  - "[[Gemini Code Assist - 프로젝트 설정]]"
  - "[[Gemini Global Memory]]"
---

# Gemini 프롬프트

Google Gemini 및 Gemini Code Assist 관련 프롬프트·설정 모음.

## 설정 노트
- [[Gemini Code Assist - 프로젝트 설정]] — 프로젝트 컨벤션 및 Instructions 설정
- [[Gemini Global Memory]] — 전역 사용자 선호도 및 컨텍스트

---

```dataview
TABLE WITHOUT ID
  file.link AS "프롬프트",
  project AS "프로젝트"
FROM "AI_Agent/AI 프롬프트/Gemini"
WHERE file.name != "Gemini"
SORT file.mtime DESC
```
