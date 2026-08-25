# Hermes Agent 설정

tags: #AI_Agent #Hermes #Telegram #서버자동화
날짜: 2026-06-20

---

## 개요

NousResearch가 만든 오픈소스 자율 AI 에이전트.
Telegram으로 서버 명령 실행, n8n 트리거, LLM 대화를 통합 제어.

---

## 아키텍처

```
Telegram → Hermes Agent (systemd 서비스) → Gemini 3.1 Flash Lite
                                          ↘ bash 명령 실행
                                          ↘ n8n 워크플로우 트리거
```

---

## 설치 환경

- **서버**: math4u.co.kr (Rocky Linux 9 + Docker)
- **설치 경로**: `/home/Math4U/.hermes/`
- **실행 방식**: systemd user service (부팅 시 자동 시작)
- **LLM 프로바이더**: Google Gemini
- **모델**: `gemini-3.1-flash-lite`
- **터미널 백엔드**: Docker (격리 실행)
- **메시징 플랫폼**: Telegram

---

## 설정 파일 경로

| 파일 | 경로 |
|------|------|
| 환경변수 | `~/.hermes/.env` |
| 설정 | `~/.hermes/config.yaml` |
| 로그 | `~/.hermes/logs/` |
| 메모리 | `~/.hermes/memories/` |
| 스킬 | `~/.hermes/skills/` |

### .env 핵심 키
```
GOOGLE_API_KEY=...
TELEGRAM_BOT_TOKEN=...
```

---

## 주요 명령어

```bash
# 상태 확인
hermes gateway status

# 시작 / 중지 / 재시작
hermes gateway start
hermes gateway stop
hermes gateway restart

# 실시간 로그
journalctl --user -u hermes-gateway -f

# 설정 변경
hermes setup          # 전체 마법사
hermes setup model    # 모델/프로바이더 변경
hermes setup gateway  # Telegram 재설정
hermes config edit    # 직접 편집

# 진단
hermes doctor
```

---

## 설치 과정 요약

1. 공식 원라인 인스톨러 실행
   ```bash
   curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
   ```
2. `hermes setup` → Provider: Google Gemini / Model: gemini-3.1-flash-lite
3. Terminal backend: Docker
4. Platform: Telegram 선택
5. Web Search: DuckDuckGo (무료, API 키 불필요)
6. `hermes gateway install` → systemd 서비스 등록
7. `~/.hermes/.env`에 `GOOGLE_API_KEY` 수동 추가 후 restart

---

## 트러블슈팅

| 증상 | 원인 | 해결 |
|------|------|------|
| `RuntimeError: no API key` | .env에 키 누락 | `echo "GOOGLE_API_KEY=..." >> ~/.hermes/.env` 후 restart |
| `python-telegram-bot not installed` | 패키지 누락 | `/home/Math4U/.hermes/hermes-agent/venv/bin/pip install python-telegram-bot` |

---

## 참고 링크

- 공식 사이트: https://hermesagent.agency
- GitHub: https://github.com/NousResearch/hermes-agent
- 스킬 허브: https://agentskills.io
