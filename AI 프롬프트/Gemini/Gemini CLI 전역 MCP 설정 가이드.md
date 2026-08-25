---
title: Gemini CLI 전역 MCP 설정 가이드
tags:
  - 영역/사업
  - 유형/절차
created: 2026-05-18
updated: 2026-05-18
type: procedure
status: active
related:
  - "[[Gemini Global Memory]]"
  - "[[n8n 허브]]"
  - "[[Claude CLI 설정]]"
---

# Gemini CLI 전역 MCP 설정 가이드

Gemini CLI에서 파일 시스템, Notion, n8n 등의 외부 도구와 연동하기 위한 전역 MCP(Model Context Protocol) 설정 방법입니다.

## 1. 설정 파일 경로
- **Windows**: `C:\Users\khai01\.gemini\settings.json`

## 2. 보안 주의사항 (중요)
> [!WARNING] 보안 알림
> 위 설정 파일에는 민감한 정보(토큰/API 키)가 포함되어 있습니다.
> 1. 이 파일을 공용 저장소(GitHub 등)에 절대 올리지 마세요.
> 2. 토큰 값이 노출된 경우, 즉시 해당 서비스(Notion, n8n, GitHub)에서 API 키를 재발급받으십시오.

## 3. 설정 내용 (`settings.json`)
```json
{
  "security": {
    "auth": {
      "selectedType": "gemini-api-key"
    }
  },
  "ui": {
    "theme": "Default"
  },
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "V:/Code",
        "V:/Biz",
        "V:/Obsidian",
        "V:/카이 김승현"
      ]
    },
    "notion": {
      "command": "npx",
      "args": [
        "-y",
        "@notionhq/notion-mcp-server"
      ],
      "env": {
        "NOTION_TOKEN": "REDACTED_NOTION_TOKEN"
      }
    },
    "n8n-mcp": {
      "command": "npx",
      "args": [
        "-y",
        "n8n-mcp"
      ],
      "env": {
        "MCP_MODE": "stdio",
        "LOG_LEVEL": "error",
        "DISABLE_CONSOLE_OUTPUT": "true",
        "N8N_API_URL": "https://n8n.math4u.co.kr",
        "N8N_API_KEY": "REDACTED_N8N_API_KEY"
      }
    },
    "github": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-github"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "REDACTED_GITHUB_TOKEN"
      }
    }
  },
  "ide": {
    "hasSeenNudge": true
  }
}
```
