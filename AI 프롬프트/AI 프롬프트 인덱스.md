---
type: concept
area: AI 프롬프트
updated: 2026-05-10
tags:
  - AI
  - 프롬프트
related:
  - "[[00. AI팀 소개 및 운영 가이드]]"
  - "[[지니 (Chief of Staff) 시스템 프롬프트]]"
  - "[[AI 프롬프트 인덱스]]"
---

# AI 프롬프트 관리

AI 모델별로 사용하는 프롬프트를 저장하고 관리하는 영역.

---

## 모델별 폴더

| 모델 | 폴더 | 용도 |
|------|------|------|
| Claude | [[Claude]] | Anthropic Claude 프롬프트 |
| GPT | [[GPT]] | OpenAI GPT 프롬프트 |
| Gemini | [[Gemini]] | Google Gemini 프롬프트 |

---

## AI 팀 에이전트

| 에이전트 | 파일 | 역할 |
|----------|------|------|
| Jemini | [[Jemini]] | 메인 오케스트레이터 |
| Planner | [[Planner]] | 시스템 설계 및 기획 |
| Coding Specialist | [[Coding_Specialist]] | 개발 전문가 |
| n8n Specialist | [[N8N_Specialist]] | 자동화 전문가 |
| Notion Specialist | [[Notion_Specialist]] | 데이터베이스 전문가 |
| Validator | [[Validator]] | 검증 및 보안 |

---

## 프롬프트 작성 규칙

- 파일명: `프로젝트명_용도.md`
- 효과 좋았던 프롬프트는 ⭐ 태그 추가

---

## 전체 프롬프트 목록

```dataview
TABLE WITHOUT ID
  file.link AS "프롬프트",
  project AS "프로젝트",
  tags AS "태그"
FROM "AI_Agent/AI 프롬프트"
WHERE file.name != "AI 프롬프트 인덱스"
SORT file.mtime DESC
```
