# lesson-a NAVIGATION

성우하이텍 AI 마스터 과정 실습 레포. Practice 기반 인터랙티브 강의 시스템. 수강생 환경은 Claude Code VSCode extension v2.0+.

---

## 이 문서의 목적

이 문서는 이 레포에 진입한 AI가
필요한 파일만 빠르게 읽고,
실습을 과도하게 스캔하지 않도록 돕는
최소 안내 문서입니다.

핵심 원칙은 단순합니다.

- 먼저 전체 규칙을 읽습니다.
- 지금 시작할 Practice 1개만 읽습니다.
- 수강생이 직접 지정한 파일만 추가로 읽습니다.
- 설계 문서나 템플릿 전체를 미리 훑지 않습니다.

---

## Minimum Context

### 가장 먼저 읽을 파일 3개

읽기 우선순위는 아래 순서를 따릅니다.

| 우선순위 | 파일 | 이유 |
|------|------|------|
| 1 | `CLAUDE.md` | 레포 전체 규칙, 수강생 역할, 실습 시작 방식 |
| 2 | `course-structure.json` | Practice 구성, 명령 이름, target_environment |
| 3 | `student-profile.md` | 수강생 개인화 정보. Practice 02 이후 생성되면 항상 활용 |

### 실습 진행 시 추가로 읽을 파일

아래 파일은 실습 시작 직전 또는 시작 시점에만 읽습니다.

| 파일 | 읽는 시점 | 이유 |
|------|----------|------|
| `.claude/SCRIPT_INSTRUCTIONS.md` | `start-practice` 진입 직후 | 진행 마커, 톤, 복습 원칙 확인 |
| `lesson-modules/practice-XX-*/CLAUDE.md` | 해당 Practice 시작 시 | 해당 실습 진행안 확인 |
| `.claude/commands/start-practice-XX.md` | 수강생이 해당 명령을 호출했을 때 | 시작 진입 규칙 확인 |

### 필요 시에만 읽는 파일

| 파일 또는 폴더 | 읽는 조건 |
|------|----------|
| `.claude/skills/lesson-a/SKILL.md` | 강사 스킬이 실제로 트리거되었을 때 |
| `.claude/skills/lesson-a/references/` | 강사 관점의 참조가 정말 필요할 때만 |
| `README.md` | 레포 소개나 온보딩 맥락이 추가로 필요할 때 |
| `organized/`, `reviews/` | 수강생이 기존 산출물을 다시 열어달라고 할 때 |

### 절대 로드하지 말 것

아래 항목은 강의 진행 중 기본적으로 읽지 않습니다.

| 금지 대상 | 금지 이유 | 예외 |
|------|------|------|
| `practice-data/` 전체 폴더 Glob 스캔 | 수강생 맥락 없이 데이터 전체를 미리 읽으면 과부하와 혼선 발생 | 수강생이 `@practice-data/...` 경로를 명시한 파일만 Read |
| `templates/` 전체 | 템플릿은 참조용이며 실습 시작 컨텍스트가 아님 | 수강생이 템플릿 적용을 직접 요청할 때 |
| `analysis/` 폴더 | 설계/리서치 문서이며 수강생용 기본 컨텍스트가 아님 | 강사가 특정 개념 설명을 위해 명시적으로 참조할 때 |
| 레포 전체 `**/*.md` 스캔 | 과도한 컨텍스트 로드의 대표 사례 | 금지 |

---

## 진입 순서

실습 요청을 받았을 때 기본 순서는 아래와 같습니다.

1. `CLAUDE.md`를 읽습니다.
2. `course-structure.json`를 읽습니다.
3. `student-profile.md`가 있으면 읽습니다.
4. 수강생이 호출한 `start-practice-XX`를 확인합니다.
5. `.claude/SCRIPT_INSTRUCTIONS.md`를 읽습니다.
6. 해당 Practice의 `lesson-modules/.../CLAUDE.md` 1개만 읽습니다.
7. 바로 실습을 시작합니다.

추가 파일은 수강생이 말한 것만 엽니다.

예:

- `@practice-data/C-제조/defect_log.csv`
- `my-weekly-check.md`
- `organized/strategy_review.md`

---

## 폴더 지도

| 경로 | 용도 | 로드 시점 |
|------|------|----------|
| `CLAUDE.md` | 레포 전체 규칙 | 진입 시 항상 |
| `course-structure.json` | 주차/Practice 구성 | 진입 시 항상 |
| `student-profile.md` | 수강생 개인화 | Practice 02 이후 항상 |
| `.claude/CLAUDE.md` | 프로젝트 추가 규칙 (있으면) | 존재할 때만 진입 시 |
| `.claude/SCRIPT_INSTRUCTIONS.md` | 진행 규칙 | `start-practice` 시 |
| `.claude/commands/start-practice-XX.md` | Practice 시작 커맨드 | 수강생이 해당 커맨드 호출 시 |
| `.claude/skills/lesson-a/SKILL.md` | 강사 스킬 정의 | 스킬 트리거 시 |
| `.claude/skills/lesson-a/references/` | 강사용 참조 | 필요 시 |
| `lesson-modules/practice-XX-*/CLAUDE.md` | Practice별 진행안 | 해당 `start-practice` 시 |
| `practice-data/{A-RnD,B-전략,C-제조,D-경영}/` | 부서별 실습 데이터 | `@경로` 명시 시만 |
| `templates/` | 산출물 템플릿 | 명시적 요청 시만 |
| `analysis/` | 설계 참조 문서 | 강의 중 로드 금지 |
| `organized/` | 정리 완료본 | 기존 결과 재사용 시 |
| `reviews/` | 피드백 메모 | 복습 또는 수정 요청 시 |

---

## 파일별 읽기 메모

### `CLAUDE.md`

- 수강생은 개발자가 아니라 제조업 실무자입니다.
- 핵심은 질문, 검토, 저장, 공유입니다.
- "저장해줘 → 올려줘" 루프를 매 교시 마무리로 봅니다.
- Practice 명령 표는 빠른 진입점입니다.

### `course-structure.json`

- 현재 Practice 목록과 모듈명을 확인합니다.
- `target_environment`를 반드시 반영합니다.
- CLI 가능 여부를 먼저 봅니다.
- 수강생 OS와 권장 버전을 확인합니다.

### `student-profile.md`

- 있으면 수강생 이름, 부서, 관심 업무를 적극 활용합니다.
- 없으면 profile을 없는 상태로 인정하고,
  Practice 03 이상에서는 먼저 생성 또는 보완 안내를 고려합니다.
- profile이 비어 있어도 수업은 멈추지 말고
  이름만 확인해 기본값으로 진행합니다.

### `.claude/SCRIPT_INSTRUCTIONS.md`

- 학생 이름을 먼저 묻습니다.
- 한 번에 한 단계씩 진행합니다.
- `ACTION`, `USER`, `STOP` 흐름을 유지합니다.
- 감자재배법 원칙을 지킵니다.

### Practice 모듈 문서

- 현재 Practice에 필요한 내용만 담겨 있습니다.
- 이전 Practice 전체를 다시 읽을 필요는 없습니다.
- 선행 조건은 확인하되,
  수강생이 일부를 건너뛰었다면 부드럽게 최소 보완 경로를 제안합니다.

---

## 자주 하는 실수

### 실수 1

❌ 수강생이 "실습해주세요"라고 하면
`Glob("**/*.md")`처럼 레포 전체 문서를 훑는다.

이 방식은 금지입니다.

올바른 접근:

- 어떤 Practice인지 먼저 확인합니다.
- `start-practice-XX` 커맨드로 진입합니다.
- 그 Practice 문서 1개만 읽고 시작합니다.

### 실수 2

❌ 부서별 데이터 파일을 미리 전부 읽는다.

이 방식은 금지입니다.

올바른 접근:

- 수강생이 `@practice-data/A-RnD/result.csv`처럼
  경로를 직접 적었을 때만 해당 파일을 읽습니다.
- 폴더 전체 탐색보다
  지정 파일 1개 또는 필요한 소수 파일만 읽습니다.

### 실수 3

❌ `student-profile.md`가 없는데
Practice 03 이상을 아무 설명 없이 진행한다.

올바른 접근:

- profile이 없음을 짧게 인지합니다.
- 가능하면 Practice 02 흐름으로 먼저 이어지게 합니다.
- 다만 강의 흐름상 바로 진행해야 하면
  이름과 부서만 확인해 임시로 진행합니다.

### 실수 4

❌ 수강생에게 CLI 명령, `gh auth`, 터미널 조작을 설명한다.

이 방식은 금지입니다.

올바른 접근:

- 수강생 환경은 VSCode extension 전제입니다.
- 모든 조작은 사이드바 채팅창, 명령 팔레트, Source Control 패널 기준으로 설명합니다.
- 명령어 예시가 필요해도
  채팅창에 그대로 붙여 넣을 자연어 중심으로 바꿉니다.

### 실수 5

❌ 강사용 참조 문서를 학생 기본 컨텍스트처럼 길게 불러온다.

이 방식은 금지입니다.

올바른 접근:

- 강사 참조는 정말 필요한 순간에만 일부 활용합니다.
- 학생에게는 지금 필요한 단계만 보여줍니다.

---

## Practice 순서

| # | 실습 | 커맨드 | 핵심 산출물 |
|---|------|--------|------------|
| 01 | 설치와 연결 | `/start-practice-01` | VSCode + Claude Code + 첫 응답 |
| 02 | 플러그인 + 프로필 | `/start-practice-02` | `student-profile.md` + 첫 push |
| 03 | 도구 탐색 | `/start-practice-03` | `my-installed-tools.md` |
| 04 | 부서별 데이터 분석 | `/start-practice-04` | 부서별 분석 결과 파일 |
| 05 | 결과 다듬기 + 저장 | `/start-practice-05` | 확장 결과 파일 + push |
| 06 | `CLAUDE.md` 규칙 설계 | `/start-practice-06` | Always/Ask/Never `CLAUDE.md` |
| 07 | 구조가 결과를 바꾼다 | `/start-practice-07` | A/B/C 비교 + `/prompt` 결과 |
| 08 | 실무 반복 파이프라인 | `/start-practice-08` | 부서별 루프 결과 + before/after |
| 09 | 하네스 + 나만의 스킬 + MW6 예고 | `/start-practice-09` | `my-weekly-check.md` + 스킬 1개 |
| SPARE | Vercel 배포 | `/start-practice-SPARE` | Vercel URL (시간 여유 시) |

---

## Practice 선택 가이드

| 상황 | 먼저 권할 Practice |
|------|------------------|
| 처음 들어온 수강생 | Practice 01 |
| 이름/부서/업무 맥락이 아직 없음 | Practice 02 |
| 설치된 도구 감각이 약함 | Practice 03 |
| 실제 데이터로 바로 해보고 싶음 | Practice 04 |
| 결과를 업무형 문서로 다듬고 싶음 | Practice 05 |
| 반복 규칙을 만들고 싶음 | Practice 06 |
| 구조 차이를 체험하고 싶음 | Practice 07 |
| 여러 파일을 묶어 흐름화하고 싶음 | Practice 08 |
| 링크로 공유하고 싶음 | Practice 09 |
| 반복 업무를 스킬 감각으로 정리하고 싶음 | Practice 10 |

---

## 수강생 환경 (CRITICAL)

- Claude Code VSCode extension v2.0+ 전제
- Windows 10/11 전제
- 터미널 없음
- `gh CLI` 미설치 가정
- 모든 조작은 VSCode 사이드바 채팅창, 명령 팔레트, Source Control 패널 기준
- 세부 기준은 `course-structure.json`의 `target_environment` 필드를 우선 참조

AI가 안내 중 환경을 헷갈리면
항상 이 섹션으로 돌아옵니다.

---

## 톤과 원칙

- 부드러운 권유형을 유지합니다.
- 감자재배법을 따릅니다.
- AI가 대신 끝내지 않고 수강생이 직접 시도하게 돕습니다.
- "저장해줘 → 올려줘" 루프를 유지합니다.
- 실습 시작 안내 박스는 Practice 01에만 1회 사용합니다.
- 복습 속도와 설명 깊이는 수강생별로 유동 조절합니다.

말투 예시:

- "이번에는 이 파일 하나만 같이 열어볼까요?"
- "먼저 이름과 부서를 기준으로 정리해보면 좋겠습니다."
- "바로 완벽하지 않아도 괜찮으니 한 번 실행해볼게요."

피해야 할 말투:

- "터미널에서 실행하세요"
- "`gh auth`를 하세요"
- "이건 그냥 제가 해둘게요"
- "전부 자동으로 처리됐습니다"

---

## 빠른 체크

실습을 시작하기 전에 아래 6개만 확인하면 충분합니다.

- 지금 Practice 번호가 무엇인가
- `CLAUDE.md`를 읽었는가
- `course-structure.json`를 읽었는가
- `student-profile.md`가 있는가
- 해당 Practice 모듈 1개만 읽었는가
- 불필요한 폴더 스캔을 하지 않았는가

이 문서의 목적은 많이 읽는 것이 아니라
덜 읽고도 정확히 시작하는 것입니다.
