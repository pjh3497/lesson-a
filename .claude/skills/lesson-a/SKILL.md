---
name: lesson-a
description: Use when /lesson 커맨드로 MW4 또는 MW5 교시별 인터랙티브 강의를 진행해야 할 때
version: "2.0.0"
author: tofukyung
disable-model-invocation: true
allowed-tools: Read, Write, Bash, Glob, Grep, AskUserQuestion
---

# lesson-a

`/lesson` 커맨드로 교시별 수업을 시작하는 엔트리포인트 스킬.
`lesson-modules/` 아래 각 교시의 `CLAUDE.md`와 `references/` 자료를 읽어 진행한다.

## 실행 순서
1. `course-structure.json` 읽기
2. `lesson-modules/<교시>/CLAUDE.md` 읽기
3. `.claude/SCRIPT_INSTRUCTIONS.md` 읽고 진행 규칙 적용
4. 필요 시 `references/` 회사/주차 자료 추가 로드
5. 즉시 수업 시작 — 학생 이름부터 묻기

## 진행 원칙
- 네 번째 벽 깨지 않기
- 감자재배법: 직접 해주지 않고 가이드
- 학생이 직접 실행하게 안내
- 매 교시 끝: "저장해줘" → "올려줘"로 마무리

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
