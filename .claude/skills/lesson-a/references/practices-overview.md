---
disable-model-invocation: true
---

# 성우하이텍 AI 마스터 과정 — 강사 참조 자료

> **구조**: 실습 단위(Practice) 기반. 교시/주차 구분 없이 강사가 유연하게 배치.
> **원칙**: 풍부하게 준비하되, 진행 속도에 따라 Practice 단위로 유연 조절. "감자 재배법" 원칙.
> **기반**: CC101 Sec01, 05, 06, 08, 10, 12 / CMG Ch03-05 / chaei 1.1-1.3, 2.1-2.5

---

## 전체 Practice 맵

| # | Practice | 커맨드 | 핵심 산출물 | 선행 조건 |
|---|---------|--------|------------|----------|
| 01 | 설치와 연결 | `/start-practice-01` | 설치 성공 + 첫 응답 | 없음 |
| 02 | 플러그인 + 나를 알려주는 파일 | `/start-practice-02` | `student-profile.md` + 첫 push | P01 |
| 03 | 도구 탐색 | `/start-practice-03` | `my-installed-tools.md` | P02 |
| 04 | 부서별 데이터 분석 | `/start-practice-04` | 부서별 분석 결과 파일 | P03 |
| 05 | 결과 다듬기 + 저장 | `/start-practice-05` | 확장 결과 파일 + push | P04 |
| 06 | CLAUDE.md 규칙 설계 | `/start-practice-06` | Always/Ask/Never CLAUDE.md | P01~05 |
| 07 | 구조가 결과를 바꾼다 | `/start-practice-07` | A/B/C 비교 + /prompt 결과 | P06 |
| 08 | 부서별 통합 파이프라인 | `/start-practice-08` | 통합 분석 보고서 | P07 |
| 09 | 배포와 공유 | `/start-practice-09` | HTML 대시보드 + Vercel URL | P08 |

---

## 교시 배분 참고 (강사 재량)

아래는 2주 8교시 배분 예시입니다. 진행 속도에 따라 유연하게 조절합니다.

### 첫째 주 (4교시)

| 교시 | 시간 | 권장 Practice | 비고 |
|------|------|--------------|------|
| 1교시 | 08:00~08:45 | Practice 01 | 설치에 시간 여유를 충분히 |
| 2교시 | 09:00~09:45 | Practice 02 | 인터뷰+Git까지 완료 |
| 3교시 | 10:00~10:45 | Practice 03 + 04 | 도구 탐색 후 바로 부서 적용 |
| 4교시 | 11:00~11:45 | Practice 05 | 확장 + 마무리 |

### 둘째 주 (4교시)

| 교시 | 시간 | 권장 Practice | 비고 |
|------|------|--------------|------|
| 1교시 | 08:00~08:45 | Practice 06 | 복습 + CLAUDE.md 설계 |
| 2교시 | 09:00~09:45 | Practice 07 | 3층 비교 실험 + /prompt |
| 3교시 | 10:00~10:45 | Practice 08 | Plan 모드 + 멀티파일 |
| 4교시 | 11:00~11:45 | Practice 09 | HTML + Vercel 배포 |

---

## 공통 강사 원칙

### 감자재배법
AI가 직접 다 해주는 것이 아니라, 수강생이 직접 질문하고, 직접 결과를 확인하고, 직접 수정하고, 직접 저장하는 방식으로 배웁니다.

### 저장해줘 → 올려줘
매 실습 끝에 반드시 commit + push 루프를 확인합니다.

### VSCode Extension 환경 인식
- 수강생은 CLI가 아닌 **Claude Code VSCode extension v2.1+** 환경입니다.
- 터미널 명령보다 GUI 기반 안내를 우선합니다.
- 도구 실패 시 유연하게 대신 수행하는 폴백 경로를 두세요.
- 상세 규칙은 아래 "VSCode Extension 환경 표준 가이드" 참조.

### 자기 정체성
AI가 "나는 Claude입니다" 같은 자기 부정/혼란을 보이면, SCRIPT_INSTRUCTIONS의 자기 인식 지시문으로 돌아가세요.

---

## VSCode Extension 환경 표준 가이드

> **이 섹션은 강의 전체를 관통하는 환경 규칙입니다. 모든 Practice가 이 원칙을 따릅니다.**

### 전제 조건
- 수강생 PC: Windows 10/11, VSCode 1.98+, Claude Code extension v2.0 이상 (2026-04 기준 v2.1.92)
- CLI 터미널 접근 없음. `gh CLI` 미설치 상태 가정.
- 모든 조작은 VSCode 화면(사이드바 채팅창, 명령 팔레트, Source Control 패널)에서 완료 가능해야 함.

### 플러그인 설치 표준 경로 (3-Tier)

| 우선순위 | 방식 | 트리거 | 조건 |
|---------|------|--------|------|
| **A안 (권장)** | `/plugins` GUI의 Install 버튼 | 채팅창 `/plugins` → Discover 탭 | `.claude/settings.json`에 마켓플레이스 사전 등록 필요 |
| **B안 (폴백)** | 채팅창 슬래시 명령 | `/plugin marketplace add {repo}` + `/plugin install {name}@{marketplace}` | 네트워크 정상, URL 정확 |
| **C안 (최후)** | 강사 화면 공유 대신 실행 | 위 두 가지 모두 실패 | 강사가 원격 지원 |

**lesson-a 레포는 이미 A안 준비 완료**: `.claude/settings.json`에 `extraKnownMarketplaces`로 gptaku, tofukyung-plugins 사전 등록되어 있음. 수강생은 폴더만 열면 자동 인식.

### `/plugins` UI 4탭 구조
- **Discover** — 설치 가능한 플러그인 목록. Install 버튼으로 설치.
- **Installed** — 내 설치 목록 + 토글(on/off). 문제 시 가장 먼저 확인.
- **Marketplaces** — 등록된 마켓플레이스. `.claude/settings.json` 사전 등록분이 여기 표시됨.
- **Errors** — 로딩 오류. 비어 있으면 정상.

설치 후 반드시 `/reload-plugins` 실행 → Installed 탭에서 토글 ON 확인.

### GitHub 연동 표준 경로

수강생은 `gh CLI`를 설치하지 않습니다. 첫 push는 아래 경로로 진행:

```
1. 브라우저에서 GitHub 레포 생성 (Public, 이름만 입력)
2. HTTPS URL 복사
3. Claude Code 채팅창에 자연어 요청:
   "이 폴더를 git init 하고 [URL] 에 원격 연결, student-profile.md commit 해줘"
4. Claude가 git init / remote add / add / commit 실행
5. 채팅창에 "올려줘" 입력
6. Claude가 git push 실행 → VSCode Git Credential Manager가 인증 대화상자 자동 표시
7. "Sign in with your browser" → GitHub OAuth 승인 → VSCode 자동 복귀 → push 완료
8. 이후 재인증 불필요 (Windows Credential Manager 자동 저장)
```

### GitHub 폴백 체인
| 증상 | 폴백 |
|------|------|
| Claude의 `git push`에 인증 대화상자가 안 뜸 | Source Control 패널(Ctrl+Shift+G) → `...` → Push |
| 인증 반복 요청 | Windows 자격 증명 관리자에서 `git:https://github.com` 삭제 후 재시도 |
| "Repository not found" | 레포 Public 여부 재확인, URL 오타 점검 |
| Private 레포로 잘못 생성 | GitHub → Settings → Danger Zone → Public 전환 (Practice 02는 Public 전제) |

### 바르다-깃선생 플러그인 운영 원칙
- 오늘은 **Claude 자연어 경로가 주력**입니다. 바르다-깃선생은 **보조**로만 소개.
- 이유: VSCode extension에서 바르다-깃선생이 CLI에서 동작하는 것과 완전히 동일하게 작동하는지 미검증. Claude가 직접 Bash로 git 실행하는 경로가 가장 안정적.
- Practice 03 이후 여유 있을 때만 바르다-깃선생 재시도 가능.

### 외부 서비스 연동 (Vercel 등)
VSCode extension은 Vercel/Netlify 같은 외부 배포 서비스에 직접 연동하지 못합니다. 해당 단계는 **브라우저 작업**으로 분리하고, 강사가 사전에 시연을 준비하세요. (Practice 09 Step 3-2 참조)

### CLI 전용 기능 회피
아래 기능은 VSCode extension에서 **동작하지 않거나 제한적**이므로 강의에서 사용하지 마세요:
- `!` Bash 단축키 (채팅창에서 작동 안 함)
- Tab 자동완성
- `claude --plugin-dir` 로컬 개발 플래그
- `claude mcp add` CLI 커맨드 (강사 준비용으로는 사용 가능, 수강생 실습엔 부적합)

### 환경 점검 체크리스트 (Practice 01 종료 시점)
- [ ] VSCode 1.98+ 설치
- [ ] Claude Code extension v2.0+ 설치 (가능하면 v2.1.92+)
- [ ] claude.ai 로그인 완료
- [ ] 폴더 열었을 때 `.claude/settings.json`이 로드되어 `/plugins` Marketplaces 탭에 gptaku, tofukyung-plugins가 보임
- [ ] 첫 응답 수신 확인

---

## 부서별 데이터 파일 맵

| 그룹 | 폴더 | 주요 파일 |
|------|------|----------|
| A-RnD | `practice-data/A-RnD/` | `result.csv`, `battery_log.csv` |
| B-전략 | `practice-data/B-전략/` | `market_reports/Q1-2026.md`, `Q2-2026.md`, `kpi_data.csv` |
| C-제조 | `practice-data/C-제조/` | `defect_log.csv`, `production.csv`, `mold_history.csv` |
| D-경영 | `practice-data/D-경영/` | `budget_2026.csv`, `actual_Q1.csv`, `purchase_history.csv` |

---

## 트러블슈팅 공통

| 문제 | 해결 |
|------|------|
| 확장 안 보임 | VSCode 1.98+ 업데이트 후 재시작 |
| 로그인 브라우저 안 열림 | 팝업 차단 해제, claude.ai 직접 로그인 |
| 응답 없음 | Ctrl+N (새 대화), 또는 재로그인 |
| "구독 필요" 메시지 | Team 초대 미수락 → 이메일 확인 |
| `/plugins` 명령 안 됨 | 확장 최신 버전(v2.0+) 확인 + Developer: Reload Window |
| Marketplaces 탭 비어 있음 | `.claude/settings.json` 로드 실패 → Reload Window, 파일 존재 확인 |
| 플러그인 Install 버튼 먹통 | `/reload-plugins` → 그래도 안 되면 Reload Window |
| push 시 인증 대화상자 없음 | Source Control 패널(Ctrl+Shift+G) → `...` → Push로 폴백 |
| push 인증 반복 요청 | Windows 자격 증명 관리자 → `git:https://github.com` 삭제 → 재시도 |
| "Repository not found" | 레포 URL 오타 또는 Private로 잘못 생성 (Public으로 변경) |
| 설치 완전 실패 | Plan B: Desktop App 또는 claude.ai/code |

---

## 새 Practice 추가 시 템플릿

새 실습을 추가할 때는 아래 구조를 따릅니다:

```
lesson-modules/practice-XX-{설명}/
  CLAUDE.md     ← 실습 메인 문서
```

CLAUDE.md 필수 섹션:
- `## 역할` — 강사 역할 정의
- `## 실습 목표` — 이번 실습에서 달성할 것
- `## 산출물` — 수강생이 만들 파일/결과물
- `## 성공 기준` — 완료 판정 기준
- `## 선행 조건` — 이 실습 전에 완료해야 할 Practice
- `## 진행 순서` — Step 1, Step 2... (각 Step에 ACTION/USER/STOP)
- `## 트러블슈팅` — 예상 문제와 해결
- `## 체크리스트` — 완료 확인 항목

커맨드 파일: `.claude/commands/start-practice-XX.md`
```
---
description: Practice XX — {설명}
allowedTools: Read, Write, Bash, Glob, Grep, AskUserQuestion
---
Read("course-structure.json")
Read("student-profile.md")
Read("lesson-modules/practice-XX-{설명}/CLAUDE.md")
Read(".claude/SCRIPT_INSTRUCTIONS.md")
```
