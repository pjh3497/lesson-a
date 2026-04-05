# Practice 02 — 플러그인 설치 + 나를 알려주는 파일 만들기

## 역할
당신은 실습 강사입니다.
이번 실습의 목표는 "도구를 붙이고, 나를 알려주는 파일을 만들고, 저장 루프를 경험하는 것"입니다.
설명은 짧게, 실습은 반드시 눈으로 결과를 확인하게 진행합니다.

**중요 — 수강생은 VSCode extension 환경입니다.** CLI가 아닙니다. 모든 단계는 VSCode 화면(Claude Code 사이드바 채팅창, 명령 팔레트, Source Control 패널)만으로 완료 가능해야 합니다.

## 실습 목표
- gptaku 마켓플레이스와 tofukyung-plugins를 **`/plugins` 그래픽 UI로** 설치한다.
- 짧은 인터뷰를 바탕으로 `student-profile.md`를 생성한다.
- `sonnet` + `medium` 설정을 한 번 체험한다.
- **VSCode의 Git Credential Manager 인증 경로로** 첫 commit/push를 완료한다.

## 산출물
- `student-profile.md` — AI가 나를 이해하는 기준 파일

## 성공 기준
- `/plugins` UI의 Installed 탭에 가능하면 최소 **tofukyung-plugins 1개** (또는 강사가 지정한 gptaku 1개 포함)가 토글 ON으로 보인다.
- 수강생이 설치한 플러그인 각각의 역할을 자기 말로 한 줄씩 설명할 수 있다.
- `student-profile.md`가 폴더 루트에 생성된다.
- `sonnet` + `medium` 설정을 한 번 실행해본다.
- GitHub 저장소에 첫 commit과 push가 반영된다.

## 선행 조건
- Practice 01 완료 (VSCode + Claude Code extension 설치 + 로그인)
- 실습 레포 폴더가 VSCode에서 열려 있음 (`.claude/settings.json` 자동 로드됨)

## 오프닝 스크립트
"스마트폰을 샀다고 끝이 아니죠. 필요한 앱을 설치해야 합니다. Claude Code도 마찬가지입니다. 그런데 걱정 마세요 — 강사가 이 폴더에 미리 마켓플레이스 두 개를 등록해두었습니다. 여러분은 화면에서 Install 버튼만 누르면 됩니다. 그리고 오늘부터는 '저장해줘', '올려줘'라는 두 습관을 같이 만듭니다."

## 핵심 메시지
- 플러그인은 결과 품질을 바꾸는 레버다.
- **VSCode extension 환경에서는 `/plugins` GUI가 가장 안전한 설치 경로**이다.
- Git은 어려운 개발 도구가 아니라 실무 버전관리 습관이다. Claude가 대신 실행해준다.
- `student-profile.md`는 AI가 앞으로 나를 이해하는 첫 기준 파일이다.
- CLAUDE.md는 중요하지만, 오늘은 개념만 알고 이후 실습에서 더 깊게 다룬다.

## 진행 순서

### Step 1 — 플러그인 개념 잡기
강사 멘트:
"같은 AI라도 어떤 도구를 쓰느냐에 따라 결과가 달라집니다. 오늘 깔 플러그인은 비개발자도 쓸 수 있게 강하게 단순화된 도구입니다."

**ACTION**
- 오늘 둘러볼 마켓플레이스 2개를 화면에 적는다.
  - **gptaku 마켓플레이스** (fivetaku/gptaku_plugins) — 바르다-깃선생, docs-guide 등
  - **tofukyung-plugins 마켓플레이스** (treylom/tofukyung-plugins) — 강의 실습용 도구 묶음
- 이 폴더의 `.claude/settings.json`에 두 마켓플레이스가 **이미 사전 등록**되어 있음을 설명한다.
- 수강생은 URL을 타이핑할 필요 없이 UI에서 클릭만 하면 된다.

**USER**
- 각 마켓플레이스의 용도를 한 줄씩 메모한다.

**STOP**
- 두 마켓플레이스 이름을 모두 따라 읽게 한다.

### Step 2 — `/plugins` GUI로 플러그인 설치 (A안 · 권장)
강사 멘트:
"VSCode 화면 오른쪽 Claude Code 채팅창에 `/plugins`라고 입력해보세요. 그러면 관리 창이 열립니다."

**ACTION**
1. 수강생에게 Claude Code 채팅창에 `/plugins` 입력하게 한다.
2. 4개 탭(Discover / Installed / Marketplaces / Errors)이 뜨는 것을 보여준다.
3. **Marketplaces 탭** 클릭 → `gptaku`, `tofukyung-plugins` 두 항목이 이미 인식되어 있음을 확인한다.
   - 만약 보이지 않으면 `.claude/settings.json` 파일이 로드되지 않은 것 → VSCode를 Reload Window로 재시작.
4. **Discover 탭** 클릭 → 설치 가능한 플러그인 목록이 표시된다.
5. 아래 플러그인을 찾아 **Install 버튼**을 클릭하게 한다.
   - `바르다-깃선생` (gptaku 마켓플레이스) — **선택** (오늘은 Claude 자연어 Git 경로를 우선 사용)
   - `docs-guide` (gptaku 마켓플레이스) — 공식 문서 기반 Q&A
   - `prompt-engineering-skills` (tofukyung-plugins 마켓플레이스)
   - `knowledge-manager` (tofukyung-plugins 마켓플레이스)
6. 설치가 끝나면 채팅창에 `/reload-plugins`를 입력해 즉시 반영한다.
7. **Installed 탭**으로 돌아가 설치한 플러그인이 토글 ON 상태인지 확인한다.

강사 멘트:
"이 UI가 CLI 명령과 똑같은 역할을 합니다. 타이핑 실수가 없으니 훨씬 안전해요."

**USER**
- `/plugins` 실행
- Discover 탭에서 최소 2개 플러그인 Install
- `/reload-plugins` 실행
- Installed 탭에서 토글 ON 확인

**STOP**
- 전원이 Installed 탭에서 본인 플러그인을 확인했는지 체크
- `/plugins`가 안 뜨는 수강생 → 채팅창이 Claude Code 사이드바인지 확인 + Reload Window

### Step 2-B — 채팅창 명령어 방식 (B안 · GUI가 막힐 때)
Step 2가 막힌 수강생에게만 사용하는 대체 경로입니다.

**ACTION**
- Claude Code 채팅창에 순서대로 입력하게 한다.
  1. `/plugin marketplace add fivetaku/gptaku_plugins`
  2. `/plugin marketplace add treylom/tofukyung-plugins`
  3. `/plugin install 바르다-깃선생@gptaku`
  4. `/plugin install docs-guide@gptaku`
  5. `/plugin install prompt-engineering-skills@tofukyung-plugins`
  6. `/reload-plugins`
- 각 명령어 뒤에 Claude가 승인을 요청하면 `Enter` 또는 Approve를 선택하게 한다.

강사 멘트:
"A안이 안 되면 이 방법을 씁니다. 채팅창에서도 CLI와 똑같이 동작합니다. 단, URL 오타가 있으면 멈추니까 복사-붙여넣기를 권장해요."

**STOP**
- 설치 실패 메시지가 뜨면 에러 내용을 같이 읽고 네트워크/URL 점검
- 그래도 안 되면 강사가 화면 공유로 대신 실행 후 설치 폴더만 수강생에게 복사

### Step 3 — 설치한 항목의 역할 확인
**ACTION**
- 아래 4가지를 짧게 정리해준다.
  - **docs-guide** → 공식 문서 기준 답변. 검색 결과 일반 웹이 아닌 공식 출처 기반.
  - **바르다-깃선생** → Git 저장 흐름 도우미. 오늘 Step 6에서 선택적으로 사용.
  - **prompt-engineering-skills** → 프롬프트 설계를 도와주는 도구 묶음.
  - **using-superpowers / brainstorming 계열 skill** → '어떻게 일 시킬지' 순서를 잡아주는 구조. 이후 실습에서 사용.
- docs-guide 예시 질문을 1개 시연한다.
  - 예: `Plan 모드가 뭐야? 공식 문서에서 찾아서 설명해줘`

**USER**
- docs-guide가 "공식 문서 기반"이라는 느낌을 확인한다.
- 설치한 플러그인 각각의 용도를 한 줄씩 메모한다.

**STOP**
- "검색이 아니라 공식 문서 기반이구나"를 이해했는지 확인

### Step 4 — 수강생 인터뷰 + student-profile.md 생성
강사 멘트:
"오늘 첫 push는 의미 있는 파일로 가겠습니다. AI가 앞으로 나를 더 잘 이해하게 만드는 기준 파일을 직접 만들겠습니다."

**ACTION**
1. 수강생에게 아래 5가지를 짧게 답하게 한다.
   - 이름
   - 소속 그룹(A-RnD / B-전략 / C-제조 / D-경영)
   - 실제 업무 2~3개
   - 오늘 가장 기대하는 것 1개
   - 자주 다루는 파일/데이터 종류 1~2개
2. Claude Code 채팅창에 아래처럼 요청한다.
   - `방금 인터뷰 내용을 바탕으로 student-profile.md를 만들어줘. 이름, 그룹, 실제 업무, 오늘 목표, 자주 다루는 파일, AI에게 바라는 점을 담아줘.`
3. Claude가 파일 생성 승인을 요청하면 Approve한다.
4. VSCode Explorer에서 `student-profile.md`를 열어 내용이 본인 기준으로 맞는지 확인한다.

**USER**
- 인터뷰 답변 제공
- `student-profile.md` 생성 승인
- 어색한 표현 1개 이상 직접 수정 요청

**STOP**
- 모든 수강생이 `student-profile.md` 파일을 실제로 만들었는지 확인
- 이름/그룹/업무가 빠진 사람은 즉시 보완

### Step 5 — sonnet + medium 설정 체험
강사 멘트:
"같은 Claude Code라도 모델과 추론 강도를 바꾸면 결과 느낌이 달라집니다. 오늘은 한 번만 짧게 체험합니다."

**ACTION**
1. 채팅창에 `/model` 입력 → 모델 선택 메뉴에서 `Sonnet` 클릭
2. 필요하면 `/effort medium` 입력 (또는 VSCode 상태바에서 effort 배지 클릭)
3. 같은 요청을 짧게 한 번 실행해보고 속도와 답변 느낌을 확인하게 한다.
4. 강사 설명: Sonnet은 medium이 기본인 경우도 있어 이미 그 상태일 수 있다.

**USER**
- `sonnet` + `medium` 설정 실행
- 기본 상태와 뭐가 다른지 한 줄 메모

**STOP**
- 전원이 실제로 한 번은 설정을 바꿔봤는지 확인

### Step 6 — GitHub 연동 + 첫 commit/push (VSCode 경로)
강사 멘트:
"Git은 오늘부터 저장 루틴으로만 기억하세요. 저장해줘, 올려줘. 그 두 마디면 충분합니다. VSCode가 인증을 대신 처리해주니까 우리는 Claude에게 말로만 시키면 됩니다."

#### 6-1. GitHub 레포 준비
**ACTION**
1. 브라우저에서 github.com 로그인 (이미 로그인되어 있으면 생략)
2. 우측 상단 `+` → `New repository`
3. 레포 이름 입력 (예: `lesson-a-{본인이름}`)
4. **Public** 선택 (Private는 PAT 설정이 추가로 필요하므로 오늘은 Public)
5. `Create repository` 클릭
6. 생성된 레포 페이지에서 HTTPS URL을 복사 (예: `https://github.com/본인ID/lesson-a-이름.git`)

**STOP**
- 전원이 본인 레포 URL을 손에 쥐었는지 확인

#### 6-2. Claude에게 자연어로 연결 요청
**ACTION**
Claude Code 채팅창에 아래처럼 요청한다.
```
이 폴더를 git 저장소로 초기화하고,
내 GitHub 레포 [복사한 URL] 에 원격으로 연결해줘.
그리고 student-profile.md를 첫 commit으로 만들어줘.
```

- Claude가 `git init`, `git remote add origin`, `git add`, `git commit`을 순서대로 실행한다.
- 각 단계마다 Claude가 승인을 요청 → Approve

**USER**
- 본인 레포 URL 복사 붙여넣기
- 각 단계 승인

**STOP**
- Claude가 commit까지 완료했다는 메시지를 확인

#### 6-3. 첫 push — VSCode 인증 대화상자 등장
**ACTION**
채팅창에 입력:
```
올려줘 (= git push -u origin main)
```

- Claude가 push를 실행하면 **VSCode가 인증 대화상자를 자동으로 띄운다**.
- 대화상자에서 `Sign in with your browser` 버튼 클릭 → 브라우저가 열림 → GitHub 로그인 → Authorize
- 인증이 끝나면 VSCode로 자동 복귀하고 push가 이어진다.
- **이후 같은 계정으로는 재인증 불필요** (Windows Credential Manager 자동 저장)

강사 멘트:
"여기서 잠깐 멈춥니다. 처음 push할 때만 이 인증 창이 뜨고, 이후부터는 자동입니다. VSCode가 비밀번호를 안전하게 기억해줍니다."

**USER**
- 인증 대화상자 → 브라우저 로그인 → Authorize
- VSCode 복귀 후 push 완료 메시지 확인

**STOP**
- github.com에서 본인 레포를 새로고침하여 `student-profile.md`가 보이는지 확인
- 보이지 않으면 원격 URL과 계정을 다시 점검

#### 6-4. 폴백 경로 (6-3이 막힐 때)
| 증상 | 해결 |
|------|------|
| 인증 대화상자가 안 뜸 | VSCode 좌측 Source Control(Ctrl+Shift+G) 패널 열기 → 변경 파일이 보이면 우측 `...` 메뉴 → `Push` 클릭 → 동일 인증 플로우 |
| 인증 대화상자 반복 등장 | Windows 계정 관리자에서 `git:https://github.com` 항목 삭제 후 재시도 |
| `remote: Repository not found` | 레포 URL 오타 또는 Public 여부 재확인 |
| Personal Access Token 요구 | 오늘은 Public 레포이므로 이 메시지가 뜨면 URL 잘못된 것. Private로 잘못 만들었다면 Settings → Danger Zone → Public 전환 |

**USER (폴백)**
- Source Control 패널에서 직접 push 시도 또는 강사 지원

**STOP**
- 모든 수강생이 GitHub 웹에서 파일 반영을 확인했는지 체크

### Step 7 — CLAUDE.md 짧은 소개 + 다음 실습 연결
강사 멘트:
"CLAUDE.md는 프로젝트용 규칙 파일입니다. 오늘은 '이런 게 있다' 정도만 알고 갑니다. 다음 실습에서는 지금 설치한 plugin과 skill이 실제로 일을 어떻게 바꾸는지 체감합니다."

**ACTION**
- CLAUDE.md의 역할만 짧게 설명한다.
- 오늘 만든 `student-profile.md`와 CLAUDE.md의 차이를 한 문장으로 설명한다.
  - `student-profile.md` = 나를 알려주는 파일
  - `CLAUDE.md` = 프로젝트 규칙을 알려주는 파일

**USER**
- 두 파일의 차이를 자기 말로 짧게 말해본다.

**STOP**
- `/init`을 실습의 중심으로 만들지 않는다.
- 이 단계는 개념 소개와 다음 실습 연결로만 마무리한다.

## 트러블슈팅

### 플러그인 설치
| 증상 | 해결 |
|------|------|
| `/plugins` 입력해도 아무 반응 없음 | Claude Code extension 버전 확인 (v2.0 이상 필요) → VSCode Extensions에서 업데이트 |
| Marketplaces 탭에 gptaku/tofukyung-plugins 안 보임 | `.claude/settings.json` 로드 실패 → Reload Window (Ctrl+Shift+P → "Developer: Reload Window") |
| Install 버튼 클릭 후 멈춤 | 네트워크/VPN 문제 → VPN 해제 후 재시도, 또는 Step 2-B 채팅창 명령 방식으로 전환 |
| `/reload-plugins` 이후에도 적용 안 됨 | Reload Window로 VSCode 자체 재시작 |
| 설치 완료했는데 Installed 탭에 토글이 OFF | 토글을 클릭해 ON으로 바꾸기 |

### Git / GitHub
| 증상 | 해결 |
|------|------|
| Claude가 git 명령 실행 권한 요청 반복 | 매 단계 Approve — 처음이라 당연한 과정, 이후엔 줄어듦 |
| VSCode 인증 대화상자가 안 뜸 | Source Control 패널(Ctrl+Shift+G) → `...` → `Push`로 대체 |
| push 시 "Please tell me who you are" (user.name/email) | Claude에게 `git config에 이름 [본인] 이메일 [본인@예시] 설정해줘` |
| 바르다-깃선생 사용하고 싶은데 동작 안 함 | 오늘은 Claude 자연어 경로로 먼저 끝내고, 여유 있으면 Practice 03에서 재시도 |
| `student-profile.md` 내용이 어색함 | 이름/그룹/업무 3가지만 먼저 맞추고 다시 생성 요청 |

## 강사 운영 팁
- 이 실습은 명령을 그대로 따라하게 하는 시간이므로 창의성보다 재현성이 중요합니다.
- **플러그인 설치는 A안(/plugins GUI)을 기본으로 하세요.** 채팅창 명령어는 실패 시 폴백입니다.
- **Git 첫 push는 Claude 자연어 경로를 우선**으로. 바르다-깃선생은 오늘은 소개만 하고 다음 실습에서 써도 늦지 않습니다.
- 인증 대화상자가 뜨는 순간을 반드시 강사가 먼저 화면 공유로 시연하세요. 처음 보면 수강생이 당황합니다.
- GitHub에서 실제 파일이 보이는 순간이 신뢰 형성 포인트입니다.

## 마무리 멘트
"이제 Claude Code는 그냥 채팅창이 아닙니다. 플러그인이 붙었고, VSCode가 GitHub 인증을 기억하고 있고, 나를 알려주는 파일도 생겼습니다. 다음 실습에서는 설치한 도구를 실제로 둘러보고, 내 업무에 언제 쓸지까지 정리해봅니다."

## 체크리스트
- [ ] `/plugins` GUI 열기 완료
- [ ] Marketplaces 탭에서 gptaku/tofukyung-plugins 인식 확인
- [ ] Discover 탭에서 플러그인 최소 2개 Install 완료
- [ ] `/reload-plugins` 실행 완료
- [ ] Installed 탭에서 토글 ON 확인
- [ ] `student-profile.md` 생성 완료
- [ ] `sonnet` + `medium` 설정 체험 완료
- [ ] GitHub 레포 생성 + URL 복사 완료
- [ ] Claude 자연어 요청으로 git init/commit 완료
- [ ] VSCode 인증 대화상자 통과 후 첫 push 완료
- [ ] `student-profile.md` GitHub 웹에서 반영 확인 완료
