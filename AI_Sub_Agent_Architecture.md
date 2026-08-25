# 🏢 DCT Biz 가상 AI 전문 조직(Sub-Agent) 아키텍처 기획서

> **작성일:** 2026-08-25  
> **총괄 디렉터:** 카이 (Kim Seung-hyun)  
> **오케스트레이터:** Aidan (Hermes Core)  
> **상위 시스템 연계:** AEGIS 시스템 및 Hermes 에이전트 네트워크

---

## 1. 기획 개요 및 목표

* **배경:** 단일 LLM 의존 시 발생하는 컨텍스트 오버헤드, 토큰 낭비, 복합 도메인(수학교육, 개발, 법무, 세무, 마케팅) 전문성 희석을 해결.
* **목표:**
  1. 실제 기업 조직과 동일한 **6인 전문 가상 직원(Sub-Agent) 체제** 구축.
  2. 필요에 따라 에이전트를 선별 소집하는 **동적 오케스트레이션(Dynamic Routing)** 구현.
  3. 에이전트별 **개별 작업실(Workspace) 및 장기 기억(RAG/Memory)**을 통한 업무 경험 자산화.

---

## 2. 조직 편제 및 모델 매핑 (6인 체제)

| 직원명 | 직무 및 포지션 | 담당 업무 | 탑재 추천 모델 | 작업실 경로 |
|---|---|---|---|---|
| **에이단 (Aidan)** | **PM / Orchestrator** | • 전사 회의 주재 및 아젠다 정리<br>• 태스크 분해 및 서브 에이전트 동적 호출<br>• 최종 산출물 검수 및 통합 보고 | `Gemini 3.7 Flash` | `/home/Cloud/Biz/AI_Offices/00_Aidan_PM/` |
| **카일 (Kyle)** | **Education Architect** | • 26년 고등수학 교수법 자산화<br>• AI Math4U 수식/커리큘럼/알고리즘 검증<br>• 교육 비즈니스 타당성 심층 감사 | `DeepSeek-R1` / `Kimi` | `/home/Cloud/Biz/AI_Offices/01_Kyle_Math/` |
| **레오 (Leo)** | **Full-stack Engineer** | • React, Node.js, Rocky Linux, Docker 엔지니어링<br>• Supabase DB 설계 및 SQL 쿼리 최적화<br>• n8n 워크플로우 자동화 구현 | `Qwen 2.5 Coder` / `Gemini 3.7 Flash` | `/home/Cloud/Biz/AI_Offices/02_Leo_Dev/` |
| **저스틴 (Justin)** | **Legal & Tax Lead** | • 학원/SaaS/판촉물 계약서 및 이용약관 검토<br>• 부가세/종소세/절세 전략 및 세무 감사<br>• AI 저작권 및 개인정보보호법 컴플라이언스 | `Kimi` / `Gemini 3.1 Pro` | `/home/Cloud/Biz/AI_Offices/03_Justin_Legal/` |
| **미아 (Mia)** | **Growth Marketer** | • 수학학원 브랜딩 및 네이버 블로그 SEO 원고<br>• B2B 세일즈 퍼널 및 전환 랜딩페이지 기획<br>• 유튜브/SNS 채널 맞춤형 카피라이팅 | `Gemini 3.7 Flash` | `/home/Cloud/Biz/AI_Offices/04_Mia_Marketing/` |
| **클로이 (Chloe)** | **Ops & QA Specialist** | • AEGIS UI/UX 흐름 및 엣지 케이스 테스트<br>• n8n 알림톡/보고서 전송 템플릿 검수<br>• 운영 매뉴얼 작성 및 단순 문서 요약 | `Gemini 3.1 Flash Lite` | `/home/Cloud/Biz/AI_Offices/05_Chloe_Ops/` |

---

## 3. 운영 아키텍처 및 작업 모드

### A. 회의 및 협업 모드 (Orchestrated Dynamic Delegation)
* 모든 안건에 6명을 상시 호출하지 않고, **안건 성격에 맞는 최소 인원(1~3명)**만 태스크포스(TF)로 소집.
* **시나리오 예시:**
  * **개발/수학 안건:** Aidan ➜ Kyle(수학) + Leo(개발) 호출
  * **마케팅 안건:** Aidan ➜ Mia(마케팅) 단독 호출
  * **릴리즈/법무 안건:** Aidan ➜ Justin(법무) + Chloe(QA) 호출

### B. 개별 작업실 1:1 업무 모드 (Direct Workspace Execution)
* 카이가 오케스트레이터를 거치지 않고 터미널에서 특정 직원의 프로필과 작업실 디렉터리를 직접 지정하여 1:1 지시.

---

## 4. 경험 누적(성장형 메모리) 파이프라인

1. **작업 일지 자동 기록:** 회의 종료 및 작업 완료 시 각 작업실 내 `Memory/` 폴더에 Decision Log 마크다운 자동 생성.
2. **컨텍스트 자동 주입:** 다음 작업 시작 시 Hermes가 해당 에이전트의 작업실 문서 및 과거 이력을 사전 로드하여 지식 누적.

---

## 5. 단계별 실행 로드맵 (Action Items)

- [ ] **Phase 1:** Rocky 서버 내 작업실 디렉터리 구조(`/home/Cloud/Biz/AI_Offices/...`) 생성
- [ ] **Phase 2:** Hermes 프로필 6종 설정 및 `SOUL.md` 페르소나 파일 배포
- [ ] **Phase 3:** 모델 API 매핑 및 프로필별 라우팅 테스트
- [ ] **Phase 4:** Aidan의 동적 서브 에이전트 호출 및 회의 주재 워크플로우 실증
