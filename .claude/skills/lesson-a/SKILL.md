---
name: lesson-a
description: Use when /lesson 커맨드로 MW4 또는 MW5 교시별 인터랙티브 강의를 진행해야 할 때
version: "2.0.0"
author: tofukyung
disable-model-invocation: true
allowed-tools: Read, Write, Bash, Glob, Grep, AskUserQuestion
---

# lesson-a

`/lesson` 커맨드로 교시별 수업을 시작할 때 사용하는 엔트리포인트 스킬입니다.
강의의 실제 내용은 `lesson-modules/` 아래 각 교시의 `CLAUDE.md`와 `references/` 자료를 읽어 진행합니다.

## 언제 쓰나
- MW4 또는 MW5 교시 수업을 바로 시작해야 할 때
- 교시별 목표, 실습, 멘트, STOP/ACTION 흐름을 불러와야 할 때
- 성우하이텍 맥락을 포함해 비개발자 대상 인터랙티브 수업을 진행해야 할 때

## 실행 원칙
1. 먼저 해당 교시 커맨드에서 `course-structure.json`을 읽습니다.
2. 이어서 해당 `lesson-modules/<교시>/CLAUDE.md`를 읽습니다.
3. `.claude/SCRIPT_INSTRUCTIONS.md`를 읽고 진행 규칙을 적용합니다.
4. 필요하면 `references/`의 회사/주차 자료를 추가로 읽어 맥락을 보강합니다.
5. 즉시 수업을 시작하고, 학생 이름부터 묻습니다.

## 진행 원칙
- 네 번째 벽을 깨지 않습니다.
- 감자재배법 원칙을 지킵니다.
- 학생이 직접 실행하게 안내합니다.
- 매 교시 끝에는 반드시 "저장해줘" 다음 "올려줘" 흐름으로 마무리합니다.

## references/ 구조
- `references/company-context.md` — 회사 배경, 수강생 환경, 실무 맥락
- `references/MW4.md` — MW4 4교시 상세 참고 자료
- `references/MW5.md` — MW5 4교시 상세 참고 자료

## 빠른 사용 흐름
- MW4 1교시: `/start-mw4-1`
- MW4 2교시: `/start-mw4-2`
- MW4 3교시: `/start-mw4-3`
- MW4 4교시: `/start-mw4-4`
- MW5 1교시: `/start-mw5-1`
- MW5 2교시: `/start-mw5-2`
- MW5 3교시: `/start-mw5-3`
- MW5 4교시: `/start-mw5-4`

## 참조 로드 규칙
주차별 상세 맥락이 필요하면 아래 파일을 우선 참조합니다.
- MW4 수업: `references/MW4.md`
- MW5 수업: `references/MW5.md`
- 공통 회사 맥락: `references/company-context.md`
