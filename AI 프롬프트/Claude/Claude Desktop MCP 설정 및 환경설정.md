---
title: Claude Desktop MCP 설정 및 환경설정
tags:
  - 영역/사업
  - 유형/참고
created: 2026-05-15
updated: 2026-05-15
type: concept
status: active
related:
  - "[[Claude CLI 설정]]"
  - "[[n8n 허브]]"
  - "[[Gemini CLI 전역 MCP 설정 가이드]]"
---

# Claude Desktop MCP 설정 및 환경설정

Claude Desktop 앱에서 사용하는 MCP 서버 설정 및 사용자 환경설정 정보입니다.

## MCP 서버 설정 (mcpServers)

### 1. n8n-mcp
n8n 워크플로우를 Claude에서 직접 실행하고 제어하기 위한 서버 설정입니다.
- **API URL**: `https://n8n.math4u.co.kr`
- **Key 환경변수**: `N8N_API_KEY` (JWT 토큰 사용)

## 사용자 기본 설정 (preferences)
- **Persist Session**: 활성화 (세션 유지)
- **Scheduled Tasks**: 활성화 (예약 작업 사용)
- **Sidebar Mode**: Chat (채팅 모드)
- **Web Search**: 활성화 (웹 검색 사용)

## ⚠️ 보안 주의사항
> [지니 보완]
> `Claude Desktop Config.json` 파일 내에 `N8N_API_KEY`가 포함되어 있습니다. 
> 이 키는 `n8n.math4u.co.kr` 서버에 대한 강력한 권한을 부여하므로, 절대 외부로 유출되지 않도록 관리해야 합니다. 
> 설정 파일 원본은 `_Archive/raw-inbox/`에 안전하게 보관되어 있습니다.

---
**원본 데이터 보존**: `_Archive/raw-inbox/Claude Desktop Config_raw.json`
