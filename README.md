# AI-Agent Organization & Guidelines (DCT Company)

> **카이(Kai, 김승현)** 대표님의 8인 C레벨 AI 임원진 및 에이전트 시스템 가이드라인과 프롬프트, 메모리를 관리하는 전용 저장소입니다.

---

## 👥 AI Executive Team (C-Level Board)

| 직책 / 이름 | 담당 영역 | 주요 역할 |
| :--- | :--- | :--- |
| **Jenna (제나)** | 총괄 / PM | 수석 비서 및 오케스트레이터, 게이트키퍼 통제 |
| **Kyle (카일)** | CEdO (교육) | 고등 수학 교육 전략 및 'Virtual Math-Master' 설계 |
| **Tony (토니)** | CTO (기술) | n8n, Supabase, 웹 앱 아키텍처 및 시스템 엔지니어링 |
| **Benjamin (벤자민)** | CLO (법무) | 법률 및 규정 검토 |
| **Neil (닐)** | CMO (마케팅) | 마케팅 및 브랜드 전략 |
| **Amy (에이미)** | Designer | UI/UX 디자인, 브랜드 가이드라인 및 웹 컴포넌트 디자인 |
| **Sheryl (셰릴)** | COO (운영) | 학원 및 회사 운영 관리 |
| **Linus (리누스)** | CDO / DevOps | Obsidian & GitHub 연동, 코드 및 문서 형상 관리 |

---

## 📂 Directory Structure

```text
AI-Agent/
├── AI Team Project/          # 자율화 AI 팀 관련 가이드 및 지식 베이스
├── AI 프롬프트/                # Claude, GPT, Gemini CLI 및 에이전트별 프롬프트
├── AI_Offices/               # 각 C레벨 임원진별 SOUL 및 메모리 디렉토리
└── README.md                 # 본 문서 (저장소 설명 및 운영 지침)
```

---

## ⚙️ Operational Guidelines for Linus (DevOps)

1. **원상 복구 및 독립성 유지**: 다른 서비스 레포지토리와 혼용하지 않고, AI 에이전트 관련 문서/설정 변경 시 본 `AI-Agent` 레포지토리에 독립적으로 관리합니다.
2. **README.md 유지보수 수칙**: 
   - 깃헙(GitHub)에 새로운 파일이나 디렉토리 구조 변경, 주요 정책 업데이트 등을 반영할 때는 **반드시 `README.md` 수정 필요성을 검토**합니다.
   - 프로젝트 구성이나 에이전트 역할에 변동이 있을 경우, 즉시 `README.md`를 최신 상태로 갱신한 뒤 커밋·푸시를 수행합니다.
