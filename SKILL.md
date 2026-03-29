---
name: lesson-sungwoo
description: "/lesson 성우하이텍 마스터과정 {주차} — MW4-7 성우하이텍 전용 강의 콘텐츠"
version: "1.0.0"
author: tofukyung
disable-model-invocation: true
---

# lesson-sungwoo — 성우하이텍 AI 마스터 과정 강의 스킬

이 스킬은 `/lesson` core 엔진을 호출하되, 성우하이텍 전용 컨텍스트를 주입합니다.

## 호출 방법

```
/lesson [MW번호] [교시번호]
예시: /lesson MW4 전체
     /lesson MW4 1교시
     /lesson MW5 3교시
```

## 스킬 로드 순서 (경로 override)

> `/lesson` core 엔진의 Step 2는 `references/{COURSE_ID}/{WEEK_NUM}.md`를 찾지만,
> 이 스킬은 `references/sungwoo-hitech/MW{N}.md` 경로를 사용합니다.
> lesson-sungwoo가 직접 커리큘럼 파일을 로드한 뒤 core 엔진에 주입합니다.

1. `references/sungwoo-hitech/company-context.md` — 수강생/환경/데이터 컨텍스트
2. `references/sungwoo-hitech/MW{N}.md` — 해당 주차 교시별 상세 (**경로 override**)
3. `/lesson` core 엔진의 lesson-engine.md로 교시 진행 (Phase 2-3만 사용)

## 전체 MW 구조 요약

| 주차 | 주제 | 핵심 도구 |
|------|------|----------|
| MW4 | 첫걸음: 설치+GitHub+간단실습 | gptaku(바르다깃선생, docs-guide) |
| MW5 | 심화: CLAUDE.md+워크플로우+배포 | /prompt, show-me-the-prd |
| MW6 | 고도화: CE+Skills+확장 | 스킬러들의수다, /skills-upgrade |
| MW7 | 종합: 프로젝트+발표+수료 | 끼리끼리, 품앗이 |

## "감자 재배법" 원칙 (전체 관통)

> 절대 직접 해주지 않는다. 수강생이 스스로 할 수 있도록 가이드한다.

| 단계 | MW | 행동 |
|------|-----|------|
| 1단계 | MW4 | 이미 있는 것 쓰기 |
| 2단계 | MW5 | 나만의 규칙 만들기 |
| 3단계 | MW6 | 도구 생산자 되기 |
| 4단계 | MW7 | 재배한 감자로 요리 |

## 매 교시 클로징 필수 패턴

모든 교시 종료 시 반드시 포함:
```
"저장해줘" → commit 완료 확인
"올려줘"  → GitHub push 확인
```

## 참조 파일

- `references/sungwoo-hitech/company-context.md` — 수강생/환경/데이터
- `references/sungwoo-hitech/MW4.md` — MW4 4교시 상세 콘텐츠
- `references/sungwoo-hitech/MW5.md` — MW5 4교시 상세 콘텐츠
