# 수료 시험 B형 — 모범 답안 · 채점표 (채점자용)

> 라이브 실기 블록1·2의 클래스 이름: A형은 `Rune`, B형은 `Dusk` 접두사를 쓴다 (예: `ARuneCharacter`). 응시자가 다른 접두사를 써도 감점하지 않는다. 3부 포트폴리오 문항은 A·B형 공통이다.

> 문항 점수 = 부 배점 × 가중치 ÷ 부 안의 가중치 합. 채점표는 문항마다 10점 기준이며 환산 점수로 바꿔 합산한다.

## 1부 필기

### P1-001 (0.10점) — 목표: W00-01, W00-02, W00-31

**모범 답안**

(1) 5.8.2 설치 후 6개월 고정. 핫픽스는 버그만 고친 업데이트라 최고 번호가 안정적. Preview는 시험판. UE6로 바꾸면 변환·API 차이·빌드 대응에 시간 손실, 기준 버전이 흔들리고 포트폴리오는 안정 정식 버전이어야 함.
(2) 가: 최소·권장 모두 충족. 나: 최소 요구사항 충족. 권장 기준으로는 OS(권장 Windows 11)·VS(권장 VS 2026 18.0+)만 못 미치고 CPU·RAM·그래픽은 권장 충족. 다: 최소 미달 — Windows 10 21H2(22H2 이상 필요), VS 2022 17.12(17.14 이상 필요, 권장 2026 18.0+). 권장 미달 — 듀얼코어(권장 쿼드코어 2.5GHz), RAM 16GB(32GB), 그래픽 4GB(8GB).
(3) 가는 70GB로 100GB 기준 미달, 다는 HDD(SSD 권장). 준비: 100GB+ 여유(SSD) — 수십 GB 설치·캐시 / 전원 연결 — 몇 시간 소요.

**채점표 (10점)**

- [2] 5.8.2 설치 후 6개월 고정
- [2] 이유 2가지(핫픽스=버그 수정판 / Preview·UE6 미사용 이유, 각 1)
- [3] (2) 다 PC: OS 최소 미달 1, VS 최소 미달 1, CPU·RAM·그래픽 권장 미달 1(셋 다 맞으면 1, 둘이면 0.5). 나를 '최소 충족, OS·VS만 권장 미달'로 쓰면 정답. 가를 미달로 보거나 나를 최소 미달(설치 불가)로 판단하면 -0.5
- [1.5] 디스크 기준 문제: 가(70GB, 100GB 미만) 0.75, 다(HDD, SSD 권장) 0.75
- [1.5] 전원 연결과 이유

> 검토에서 고친 점: B형 채점표의 '가·나를 미달로 판단하면 -0.5'가 모호하다. 나 PC는 최소 요구사항은 충족하지만 권장(Windows 11·VS 2026)에는 못 미친다. 그래서 학생이 '나: OS·VS 권장 미달'이라고 맞게 써도 감점될 수 있다. 최소와 권장을 나눠 묻고 채점 기준을 분명히 했다.

> 작성 메모: 수치는 커리큘럼 작성일(2026-11) 기준, 시험 직전 공식 문서 확인 필요.

### P1-002 (0.10점) — 목표: W00-07, W00-10, W00-11, W00-12

**모범 답안**

① 런처=엔진 설치·버전 관리(유니티 허브 역할), 편집·컴파일·디버깅은 VS. 같은 VS에 C++ 게임 개발 워크로드 추가.
② 5.8.x 중 최고 번호(핫픽스=버그 수정판).
③ 켜야 함: 엔진 내부까지 콜스택 확인. 용량 증가는 감수.
④ C++ 게임 개발·C++ 데스크톱 개발·.NET 데스크톱 개발 + C++ profiling tools, C++ AddressSanitizer, Windows 11 SDK 10.0.26100+, Unreal Engine IDE support·Test Adapter.
⑤ MSVC 14.50. Installer '수정' → 개별 구성 요소에서 MSVC v14.50 추가 → 재빌드. 빠진 도구만 보강하면 됨.

**채점표 (10점)**

- [2] ① 런처 역할, VS 필요, 워크로드 추가
- [1] ② 최고 5.8.x와 이유
- [1.5] ③ 켜야 함+엔진 내부 콜스택 1, 용량 감수 0.5
- [3] ④ 워크로드 3개(각 0.5) + 구성 요소 3개 이상(각 0.5, 최대 1.5)
- [2.5] ⑤ MSVC 14.50 1, v14.50 추가 후 재빌드와 이유 1.5

> 작성 메모: 메뉴 이름 정확도는 채점하지 않음. .NET 워크로드가 필요한 이유는 요구하지 않음.

### P1-003 (0.19점) — 목표: W00-06, W00-08, W00-09, W01-07, C-33

**모범 답안**

(1) 빌드 생성물 커밋. Binaries, Intermediate, Saved, DerivedDataCache — 재생성되는 산출물·로그·캐시라 올리면 용량 폭증·충돌.
(2) Source, Config, Content, .uproject. 유니티 Assets·ProjectSettings는 커밋, Library·Temp는 안 함과 같다.
(3) 원본만 있으면 다시 빌드할 때 생성된다(.sln도 .uproject에서 재생성).
(4) 한글·공백 경로는 빌드 에러 원인 → C:\Projects 같은 짧은 영문 경로. OneDrive가 동기화하는 바탕화면·문서 폴더도 동기화 충돌로 피함.
(5) (가) Build.cs (나) Config/ (다) Content/ (라) Source/ (마) .uproject

**채점표 (10점)**

- [2.5] (1) 지적과 4개 폴더 1.5 + 이유 1
- [1.5] (2) 원본 4가지 1 + 유니티 대응 0.5
- [1] (3) 재빌드로 생성
- [2.5] (4) 한글·공백과 짧은 영문 경로 1.5 + OneDrive 폴더 회피·이유 1
- [2.5] (5) 각 0.5

> 작성 메모: .uproject는 '프로젝트를 여는 파일·VS 프로젝트 파일 재생성 기준' 수준이면 정답. .sln·.vs는 커리큘럼대로 생성물.

### P1-004 (0.29점) — 목표: W00-03, W00-04

**모범 답안**

① LC ② 재시작(생성자=기본값) ③ 재시작(헤더 UPROPERTY 기본값) ④ LC ⑤ 재시작(멤버·리플렉션·생성자) ⑥ LC
(7) 기준은 파일 종류가 아니라 바뀐 내용이다. 생성자는 기본값(CDO)을 정한다. 그런데 에디터에는 옛 생성자로 만든 CDO와 BP·레벨 인스턴스가 이미 있어서, 함수만 바꿔 끼우는 Live Coding으로는 안전하게 갱신되지 않는다. 헤더는 멤버 구성, UPROPERTY는 리플렉션 정보를 바꾸므로 마찬가지다. 헷갈리면 재시작.

**채점표 (10점)**

- [6] ①~⑥ 각 1(선택만 맞으면 0.5)
- [2] (7) 기준이 파일 종류가 아니라 바뀐 내용이라는 점 1 + 생성자=기본값(CDO)·헤더=멤버 구성·UPROPERTY=리플렉션 정보 중 2가지를 모양 변화로 설명 1('CDO' 용어 없이 '기본값'이라고 써도 인정)
- [1] (7) 이미 만들어진 CDO(기본값)·인스턴스는 옛 모양이라 안전하지 않다는 연결
- [1] 헷갈리면 재시작

> 검토에서 고친 점: B형 채점표만 (7)에서 '생성자=CDO' 용어를 요구한다. A형은 '멤버 구성·리플렉션·기본값'만 요구한다. 목표 W00-04의 표현도 '기본값'이라 두 형의 채점 난이도가 다르다. '기본값'이라고 써도 인정하도록 맞췄다.

> 작성 메모: Live Coding 재인스턴싱 등 엔진 옵션은 확인 필요. 커리큘럼 규칙(헤더·UPROPERTY·생성자 = 재시작) 기준 채점.

### P1-005 (0.29점) — 목표: W00-21, C-07, W01-45

**모범 답안**

(1) 현재 줄까지 불린 순서. 엔진 입력 → StartSprint(188) → SetMoveSpeed(210).
(2) StartSprint 경로로만 불리고 900은 정상 → 값이 아니라 되돌리는 경로가 안 불림. StopSprint 첫 줄에 중단점: 안 멈추면 뗄 때 입력(Completed)에 BindAction 연결 확인, 멈추면 SetMoveSpeed 호출·넘기는 값 확인.
(3) ArenaCharacter.h(24)부터(USpringArmComponent 선언 누락: 전방 선언/include). 이 헤더를 include한 모든 파일(.gen.cpp 포함)에서 반복되고 뒤 에러는 연쇄. 출력 창이 빌드 순서대로 원문을 보여 정확.
(4) 직접 좁히지 않음·시도한 것 없음·정답 코드 요구. 예: "증상: Shift를 떼도 달리기 속도 유지. 재현: Play→Shift 누름→뗌. 확인: SetMoveSpeed 중단점이 누를 때만 걸림(StartSprint, 900), 뗄 때 안 걸림. StopSprint 연결 의심, 다음 확인할 것 3개를 힌트로."

**채점표 (10점)**

- [2.5] (1) 의미 1 + 경로 1.5
- [2.5] (2) 되돌리는 경로가 안 불린다는 해석 1 + StopSprint 중단점·바인딩 확인 1.5
- [2.5] (3) h(24) 먼저 1, 연쇄 1, 출력 창 정확 0.5
- [2.5] (4) 문제점 1 + 재작성 1.5

> 작성 메모: 에러 원문은 단순화한 예시. 'IntelliSense 추정 오류' 언급은 가산 요소.

### P1-006 (0.19점) — 목표: W00-23, W00-24, C-34, C-35

**모범 답안**

(1) 바이너리는 매번 통째로 저장된다 → 60MB 버전 약 50개(약 3GB)가 히스토리에 쌓여 저장소와 Clone이 매우 커진다(텍스트는 바뀐 줄만 기록). LFS를 쓰면 저장소에는 포인터만 남고 실제 파일은 따로 보관돼 Clone·히스토리가 가볍다. (참고·채점 외: GitHub은 100MB가 넘는 파일을 LFS 없이 받지 않으므로 큰 에셋일수록 LFS가 필수다.)
(2) 바이너리는 병합할 수 없다 → 한 사람의 작업을 버려야 한다. .cpp는 줄 단위로 비교·병합할 수 있다.
(3) lock: 고치기 전에 잠가 '수정 중'을 표시하고, 다른 사람은 풀릴 때까지 기다린다. Perforce 체크아웃.
(4) 저장 10GiB·월 10GiB. 초과하면 업로드가 막힌다(일어남). 요금이 자동으로 청구되지는 않는다(안 일어남). 확인 위치는 GitHub 웹 Settings의 결제(Billing).

**채점표 (10점)**

- [2.5] (1) 통째 저장→크기 증가 1.5 + LFS 효과 1
- [2.5] (2) 병합 불가·작업 유실 1.5 + 텍스트 줄 단위 병합 1
- [2.5] (3) lock 1.5, 수정 전 시점 0.5, Perforce 0.5
- [2.5] (4) 한도 1, 차단/요금 없음 구분 1, 결제 설정 0.5

> 검토에서 고친 점: B형 상황(200MB .umap을 LFS 없이 운영)이 현실과 맞지 않는다. GitHub은 100MB가 넘는 파일을 LFS 없이 받지 않아서, 'LFS 없이 운영했다면 저장소·Clone에 주는 영향'이라는 전제가 성립하지 않는다. 파일 크기를 60MB로 낮추고 모범 답안의 수치를 맞췄다.

> 작성 메모: LFS 한도·초과 동작은 커리큘럼 기준, GitHub 정책 변경 가능(확인 필요). 확인 위치는 'GitHub 웹 결제(Billing) 설정'이면 정답.

### P1-007 (0.19점) — 목표: W00-27, W00-28, W00-29, W00-30, C-01

**모범 답안**

(1) (가) 코드를 읽는 AI: 파일 전체를 읽어야 함. (나) 채팅형: 개념 설명.
(2) AI가 읽는 프로젝트 규칙 파일. 5.4→UE 5.8, '바로 완성본'→힌트 먼저(코드는 요청할 때만), '짧게 코드만'→모든 줄 해설(C#과 비교), Epic C++ 코딩 표준 추가.
(3) ① 지킴·원칙2 ② 지킴·원칙3 ③ 지킴·원칙4 ④ 어김·원칙5: AI가 도운 것과 내가 검증·수정한 것을 구체적으로 ⑤ 어김·원칙1: 다시 묻고 이해해 TIL에 정리 후 커밋
(4) 민지 L1(W1~W8, AI가 쓰고 모든 줄 해설) 맞음. 준호 L2(W9~W20, 힌트만 받고 직접 작성, AI 리뷰 의견마다 채택/거절+이유) 틀림. 서연 L3(W17~W24, AI 없이 작성 후 검증) 맞음.

**채점표 (10점)**

- [2] (1) (가)(나) 각 1
- [2] (2) 용도 1 + 고칠 점 3개 이상 1(2개 0.5)
- [3] (3) 맞은 개수 5=3, 4=2.5, 3=2, 2=1, 1=0.5
- [3] (4) 학습자별 단계·규칙·구간·판정 각 1

> 작성 메모: CLAUDE.md 규칙은 W00 과제9 문구(UE 5.8·Epic 코딩 표준·힌트 먼저·모든 줄 해설) 기준. 부록 예시의 다른 규칙도 인정.

### P1-008 (0.10점) — 목표: W01-41, C-10, C-24, W21-01

**모범 답안**

(1) 30분 전에 요청·정답 코드 받음 → 30분 시도 후 힌트만. 풀이를 보고 풀었는데 끝 → 3일 뒤 AI 없이 재풀이. 이유: 정답만 보면 혼자 푸는 실력이 늘지 않음.
(2) 목적: AI 없이 구현·설명 가능한지 점검. ① W4=AFloatingItem 30분, ② W8=IInteractable+문 60분(서로 바뀜), ③ 90분, ④ W23·모의 코테 3회+질문 은행 녹음 답변.
(3) 직접 만들며 배울 기회가 줄어듦. 실험 기능이라 버전마다 동작이 다를 수 있음.
(4) W21 딥다이브 A: AI 에이전트가 에디터 기능을 호출해 웨이브 데이터 생성·레벨 배치 자동화. AI에 맡긴 것/사람이 검증한 것 문서화.

**채점표 (10점)**

- [3] (1) 30분·힌트만 1, 3일 뒤 재풀이 누락 1, 이유 1
- [3.5] (2) 목적 1 + ①② 교환 1, ③ 90분 0.5, ④ W23 0.5, 녹음 답변 0.5
- [1.5] (3) 이유 각 0.75
- [2] (4) W21 A·자동화 예 1 + 문서화 1

> 작성 메모: AI-Off ④는 분 단위 제한이 없어 '시간 제한'이면 정답.

### P1-009 (0.19점) — 목표: C-26, C-27, C-28, C-29

**모범 답안**

(1) ① 이슈 ② 마일스톤 ③ 브랜치(main은 본편, 새 기능은 feat/ 분기) ④ 커밋(`Commit to …`) ⑤ 푸시(`Push origin`, 처음이면 `Publish branch`) ⑥ 풀 리퀘스트(작업 보고서) ⑦ 머지(`Squash and merge`) ⑧ 태그 + 릴리즈. 저장소 = 프로젝트 파일과 변경 이력 전체. 내 PC와 GitHub에 하나씩 있다.
(2) 'Closes #14' 때문에 머지할 때 #14가 자동으로 닫힌다. M3 마일스톤의 달성률이 자동으로 올라가 '계획대로 해냈다'의 증거가 된다.
(3) 태그: 'v0.3.0'이라는 이름을 붙인 시점(버전 스냅샷). 릴리즈: GIF·변경 내역을 담아 공개한 발표 페이지(패치 노트).
(4) ① main이 항상 실행되는 본편이라는 보장이 깨진다. 미완성 코드가 본편에 바로 섞인다. ② PR이라는 작업 보고서(무엇을·왜·테스트·셀프 리뷰)가 사라진다. PR은 포트폴리오에서 가장 많이 읽히는 기록이다. 이슈 자동 닫기와 마일스톤으로 이어지던 '계획 → 실행' 연결도 끊긴다(셋 중 2개 이상이면 정답).

**채점표 (10점)**

- [4] ①~⑧ 용어 대응 + ④⑤ 버튼·⑦ Squash and merge + 저장소 정의 (틀린 항목당 -0.5)
- [2] Closes #14 자동 닫기와 마일스톤 달성률 자동 표시
- [2] 태그(이름 붙인 시점)와 릴리즈(발표 페이지)를 구분
- [2] PR을 생략할 때 잃는 것 2가지(main 보호, 작업 보고서·기록 연결)

> 검토에서 고친 점: A형은 저장소·커밋·푸시·브랜치·PR·머지·이슈·마일스톤·태그·릴리즈 정의, 버튼 2개, 혼자여도 PR을 거치는 이유 2개, Closes 동작, 태그/릴리즈 차이까지 15개 안팎의 요소를 요구한다. 그런데 '전체 6~8줄'로 제한해 응시자가 요소를 빠뜨리게 만든다. B형에는 분량 제한이 없어 두 형의 조건도 다르다. 분량은 채점하지 않는다고 밝히고 제한을 완화했다.

> 작성 메모: 근거: 6장 Git 5분 개념 표. 버튼 이름은 커리큘럼 표기(영문) 기준이며 버전에 따라 조금 다를 수 있어 채점 시 의미가 맞으면 인정.

### P1-010 (0.19점) — 목표: C-25, C-30, C-31, C-54

**모범 답안**

(1) 적 AI 코드를 main에 바로 커밋하는 것은 규칙 위반이다. 작업 브랜치(예: feat/enemy-ai)에 커밋 → Push → PR → Squash and merge로 올린다. Devlog를 브랜치 + PR로 올리는 것은 위반은 아니지만 필요 없는 수고다. 문서는 main에 바로 커밋해도 되고, 커리큘럼의 Devlog 올리기 절차도 main에 커밋한다. 규칙: 코드는 브랜치 + PR, 문서(TIL·Devlog·회고)는 main에 바로 커밋해도 된다.
(2)
- 커밋 메시지: 무엇을 바꿨나 한 줄. 작업이 끝날 때마다(하루 1~3회).
- PR 본문: 왜·어떻게·테스트 방법·GIF·AI 활용. 과제(기능)를 끝낸 날(오늘 학습 카드에 자동으로 나옴).
- 이슈: 할 일과 완료 조건. 작업 시작 전(선택).
- TIL: 오늘 배운 것을 내 말로, 매일.
- docs/ 문서: 트러블슈팅·설계 결정·엔진 노트·Devlog, 주 1~2편.
- 릴리즈 노트: 이번 버전에서 해낸 것. 릴리즈 주간(6회).
- README: 전체 요약 + 증거 링크. 월 1회 갱신.
예시:
- 이슈: '원거리 적 AI — 완료 조건: 시야 안 플레이어에게 사격, 벽 뒤에서는 감지 안 함'.
- 릴리즈 노트: '근접·원거리 적 AI 2종 추가(GIF)'.
- README: 핵심 구현 표에 '적 AI' 행 + PR·TS 링크.
(3) ① 문제 → 해결 → 트러블슈팅(TS). ② 선택 → 이유 → 설계 결정(ADR). ③ 원리 → 근거 → 엔진 소스 노트.
(4) ① 그날 남긴 기록은 커밋 시간으로 날짜가 증명되지만, 나중에 기억으로 재구성한 기록은 증거가 약하다. ② 형식은 도구가 채우고 내용은 내 말로 써야 한다. AI가 대신 쓴 글은 면접관이 알아보고, 내 이해의 증거가 되지 않는다. 구조: 마일스톤·이슈(계획) → PR(실행) → 릴리즈(성과).

**채점표 (10점)**

- [2] 적 AI 코드 main 커밋=위반 → 브랜치+PR로 1, Devlog PR은 위반 아님(main 바로 커밋 가능) 0.5, 규칙 진술 0.5. 'Devlog도 위반'으로만 쓰면 Devlog 0.5는 주지 않는다
- [3] 7곳의 내용·시점 2.5(틀리거나 빠진 곳당 -0.5, 최소 0) + 이슈·릴리즈 노트·README 예시 0.5
- [3] ①TS ②ADR ③엔진 노트 + 승격 기준
- [2] 몰아서·AI 대필의 약점 2가지 + 계획→실행→성과 구조

> 검토에서 고친 점: C-30(커밋 메시지·PR 본문·이슈·TIL·docs·릴리즈 노트·README 7곳)을 A형은 앞의 3곳만, B형은 뒤의 4곳만 시험해서 어느 형도 목표를 다 다루지 않는다. 또 B형은 'Devlog를 브랜치+PR로 올림'을 규칙 위반으로 채점한다. 하지만 커리큘럼 규칙은 '문서는 main에 바로 커밋해도 된다'(허용)여서, 위반은 코드를 main에 커밋한 것 하나뿐이다. 두 형 모두 7곳을 다루게 하고, B형 (1)의 판정 기준을 바로잡았다.

> 작성 메모: 근거: 6장 '왜 이 방식인가', '어디에 무엇을 남기나', '매주·매달(TIL 승격)'.

### P1-011 (0.19점) — 목표: C-58, C-59, C-60, C-61, C-64

**모범 답안**

① 커밋 직후 왼쪽 아래 `Undo` 버튼을 누른다. 커밋만 취소되고 파일 변경은 그대로 남으므로, 나머지 파일을 고친 뒤 다시 커밋하면 된다.
② 이미 Push했으므로 그대로 두는 게 안전하다. (Push 전이었다면 History → Amend Commit…)
③ `Current Branch` → `New Branch` → 이름 입력 → `Bring my changes to …`. 변경이 새 브랜치로 따라가고 main은 그대로 남는다.
④ GitHub 쪽에 이 PC에 없는 커밋이 있어서다. 위쪽 버튼이 `Pull origin`이면 먼저 받고, 그다음 `Push origin`.
⑤ 지우기 전에 `Current Repository`·`Current Branch`, `Changes`·`History` 탭을 스크린샷으로 찍어 멘토·AI에게 질문한다(보기만 하면 안전). Discard·브랜치 삭제는 확인받기 전에는 하지 않는다. (Binaries·Intermediate류라면 커밋하지 말고 .gitignore 위치를 확인하는 것도 가점.)
확인받는 버튼: `Discard All Changes…`(및 `Discard Changes…`), `Force push`, 브랜치 삭제. 공통 위험: 작업이 사라질 수 있고 되돌리기 어렵다.

**채점표 (10점)**

- [2] ① Undo(Push 전, 파일 변경은 유지)
- [1.5] ② 이미 Push했으면 그대로 둠 + Push 전이면 Amend라는 대비
- [2] ③ New Branch + Bring my changes to …
- [2] ④ Pull origin 먼저 → Push origin, 원인 설명
- [2.5] ⑤ 화면을 찍어 질문(안전) + 위험 버튼 3개와 공통 위험

> 검토에서 고친 점: A형은 C-59 가운데 '커밋 직후 `Undo`(파일 변경은 유지)'를 전혀 시험하지 않는다(B형에서만 나온다). A형에 Undo 상황 ⑥을 추가하고, '이미 Push했다면'을 ①·⑥ 모두에 걸었다. 채점표도 다시 배분했다.

> 작성 메모: 근거: 6장 '망했을 때' 표. 버튼명은 커리큘럼 영문 표기 기준이며 의미가 맞으면 인정.

### P1-012 (0.10점) — 목표: C-74, C-75

**모범 답안**

(1) Push를 하지 않아 GitHub에 브랜치와 커밋이 없기 때문이다. 순서는 ① Push(Push origin, 처음이면 Publish branch) → ② PR. PR 본문은 오늘 학습 카드에 자동으로 나오는 본문을 쓴다.
(2) 과제를 끝낸 날마다 Push → PR로 기록한다. 올릴 변경이 없는 날(영상만 본 날)은 카드의 '건너뛰기'를 고른다.
(3) 주간 Devlog: 이번 주 과제 결과, 일요일. 릴리즈: 릴리즈 노트 초안 + GitHub 웹에서 릴리즈를 만드는 순서, 릴리즈 주간(총 6회). 월간 회고: 진척도와 관문 체크 상태, 월말.
(4) 초안은 형식과 사실(과제 결과·체크 상태)만 채워 준다. 배운 것·막힌 것·Keep/Problem/Try는 내 말로 채워야 기록이 내 이해의 증거가 된다. 대신 쓴 기록은 면접관이 알아본다.

**채점표 (10점)**

- [3.5] Push 누락이 원인 + Push → PR 순서 + 카드 자동 PR 본문
- [2] 과제를 끝낸 날만 PR, 변경 없는 날은 건너뛰기
- [3] 알림 3종의 초안 내용과 올리는 시점, 릴리즈 6회
- [1.5] 초안을 내 말로 채워야 하는 이유

> 작성 메모: 근거: 6장 서문, 첫 PR 해 보기 1·3, 어디에 무엇을 남기나, 매주·매달. 카드·알림은 학습용 HTML 기능이므로 화면 위치가 아니라 순서·조건·채워지는 내용을 채점.

### P1-013 (0.29점) — 목표: W01-01, W01-02, W01-14, W13-09

**모범 답안**

(1) PlayerHealth.h(선언: 무엇이 있나) + .cpp(정의: 어떻게 동작하나).
(2) 다른 파일은 헤더만 include. .cpp 변경은 그 파일만, 헤더 변경은 include한 30개 모두 재컴파일. 분리로 구현 변경 시 범위가 줄어듦. C#은 컴파일러가 전체를 한 번에 봐서 불필요.
(3) include: 선언을 가져옴. pragma once: 한 번만 포함. 지우면 Inventory.cpp에서 Weapon.h가 두 번 포함돼 재정의 에러.
(4)(가) class AArenaCharacter; 전방 선언, include는 HealthBarComponent.cpp로. (나) 이 헤더를 include한 파일이 ArenaCharacter.h에 의존하지 않아 그 헤더 수정 시 재컴파일 수·빌드 시간 감소. 포인터로만 써서 정의 불필요.

**채점표 (10점)**

- [1.5] (1) 한 쌍 0.5 + 선언/정의 1
- [3] (2) 헤더만 include 1, 헤더 변경 시 전부 재컴파일 1, C# 이유 1
- [2] (3) include 0.5, pragma once 0.5, 재정의 에러 1
- [2] (4)(가) 전방 선언 1 + include를 .cpp로 1
- [1.5] (4)(나) 정의 불필요 0.75 + 재컴파일 감소 0.75

> 작성 메모: UPROPERTY TObjectPtr 멤버에 전방 선언 타입을 쓰는 것은 UE5의 일반 패턴.

### P1-014 (0.19점) — 목표: W01-03, W01-04, W01-32

**모범 답안**

(1) 1: 중복 포함 방지. 5: UHT 생성 리플렉션 헤더, 마지막 include. 6: 리플렉션 등록. 7: AActor public 상속 액터 클래스. 9: UHT 생성 코드 자리. 10 public=생성자(11), 12 protected=BeginPlay(13), 14 public=Tick·Frequency(15~17), 18 private=Mesh·StartLocation(19~21); 다음 지정자까지 적용(C#은 멤버마다). 13: 부모 BeginPlay 재정의 선언. 16~17: 에디터 수정 가능 float, 기본값 2. 19~20: 메시 컴포넌트 포인터, UPROPERTY로 GC 보호·에디터 표시. 22: 클래스 끝 세미콜론.
(2) AFloatingItem::AFloatingItem() / void AFloatingItem::BeginPlay(). :: 앞은 소속 클래스, 뒤는 그 클래스의 생성자(클래스와 같은 이름).
(3) class 앞 public 제거. 멤버 앞 private → private: 블록. } 뒤 ; 누락 → };

**채점표 (10점)**

- [5] (1) 10개 각 0.5
- [2] (2) 두 첫 줄 각 0.5 + :: 앞뒤 의미 1
- [3] (3) 3종류 각 1

> 작성 메모: 모듈 API 매크로는 커리큘럼 설명이 없어 코드에서 뺐다.

### P1-015 (0.29점) — 목표: W01-05, W01-06, W02-06, W11-01

**모범 답안**

(1) UCharacterMovementComponent 객체의 주소를 담는 포인터. nullptr은 아무것도 안 가리킴 → ->로 접근하면 크래시.
(2) Goal은 FVector 객체 자신이라 ., Mesh는 포인터라 ->. (*Mesh).SetWorldLocation(Goal); C#은 참조 타입도 .만.
(3) 4행: FollowTarget을 비워 두면 매 프레임 크래시. 13행: Picker가 캐릭터가 아니면 Cast가 nullptr.
(4) if (!IsValid(FollowTarget)) { return; }
AArenaCharacter* Hero = Cast<AArenaCharacter>(Picker);
if (Hero == nullptr) { return; }
UCharacterMovementComponent* Move = Hero->GetCharacterMovement();
if (Move) { Move->MaxWalkSpeed += BonusSpeed; }

**채점표 (10점)**

- [2] (1) 주소 담는 포인터 1 + nullptr 의미 1
- [3] (2) . 이유 0.5, -> 이유 1, (*Mesh). 0.5, C# 비교 1
- [3] (3) 4행·13행 각 1.5
- [2] (4) 두 곳 각 1

> 작성 메모: nullptr 비교·IsValid() 모두 인정. GetCharacterMovement 결과 검사 추가는 감점 없이 인정.

### P1-016 (0.19점) — 목표: W01-29, W01-30, W01-31

**모범 답안**

1: (가) NewLoc 앞에 ;가 없다 (나) 50행 끝 ; 누락. 문장이 다음 줄로 이어진 것으로 읽다가 NewLoc에서야 알아채 51행을 가리킴 (다) 50행 끝에 ;
2: (가) 클래스에 SetFloatRange(float) 하나짜리 멤버가 없다 (나) 선언은 매개변수 2개, 정의는 1개로 시그니처 불일치 (다) 선언과 정의를 똑같이.
3: (가) UGameplayStatics라는 클래스 선언을 못 찾음 (나) 선언한 헤더(Kismet/GameplayStatics.h)를 include하지 않음 (다) #include "Kismet/GameplayStatics.h" 추가.

**채점표 (10점)**

- [3] 에러 1: 해석 0.5, 50행 원인 1, 51행을 가리키는 이유 1, 수정 0.5
- [3.5] 에러 2: 해석 1, 매개변수 개수 불일치 1.5, 일치시키는 수정 1
- [3.5] 에러 3: 해석 1, 헤더 include 누락 1.5, include 추가 1

> 작성 메모: 에러 원문은 MSVC 메시지를 단순화한 예시. 헤더 이름을 정확히 몰라도 '선언한 헤더를 include'면 만점.

### P1-017 (0.19점) — 목표: W01-08, W01-09, W01-10

**모범 답안**

(1) ALever, UInventoryComponent, FWeaponStats, EEnemyState, IInteractable, bIsDead, TArray/TMap.
(2) ULeverActor → ALeverActor(AActor 파생은 A). IsDead → bIsDead(bool은 b). 엔진 빌드 도구(UHT)는 UCLASS 같은 리플렉션 클래스 이름의 접두사(A/U 등)를 검사해서, 맞지 않으면 빌드 에러를 낸다. bool의 b는 코딩 표준 규칙이라 빌드 에러는 나지 않고 셀프 리뷰에서 잡는다(학생이 b까지 빌드 에러라고 써도 이 문항에서는 감점하지 않음).
(3) UCLASS: 리플렉션 등록 표시, UHT가 보고 리플렉션 코드를 생성한다. GENERATED_BODY: 생성된 코드를 클래스 안에 끼워 넣는 자리. 지우면 엔진이 클래스를 몰라 UPROPERTY·에디터 노출·BP 상속·GC 보호가 동작하지 않는다(UHT·컴파일 단계에서 빌드 실패).
(4) BoxComponent.h를 generated.h 위로 올리고, generated.h를 마지막 include로 둔다. Lever.generated.h는 UHT가 생성한다.

**채점표 (10점)**

- [3.5] (1) 7개 각 0.5
- [2] (2) 틀린 2개(ULeverActor, IsDead) 수정과 이유 각 0.75 + UHT가 클래스 접두사를 검사해 틀리면 빌드 에러 0.5
- [2.5] (3) UCLASS 1 + GENERATED_BODY·지우면 안 되는 이유 1.5
- [2] (4) generated.h 마지막 1.5 + UHT 0.5

> 검토에서 고친 점: B형 모범 답안이 bool 멤버 IsDead까지 UHT가 접두사를 검사해 빌드 에러를 내는 것처럼 썼다. 이는 사실과 다르다. UHT는 UCLASS·USTRUCT 같은 리플렉션 타입 이름의 접두사를 검사하고, bool의 b는 코딩 표준일 뿐 빌드 에러가 나지 않는다. 모범 답안을 바로잡았다. 커리큘럼 서술이 일반적이므로 학생 답의 감점 기준은 두지 않았다.

> 작성 메모: 정확한 UHT 에러 문구와 generated.h를 마지막에 두는 이유는 요구하지 않음.

### P1-018 (0.19점) — 목표: W01-12, W01-13, W01-15

**모범 답안**

(1) X=600, 135도, Yaw.
(2) Velocity=초당 속도, Delta=이번 프레임 이동량, GetActorLocation()+Delta=새 위치.
(3) 24000cm·6000cm. 프레임레이트에 따라 속도가 달라짐. DeltaTime을 곱하면 1초 합이 항상 200cm.
(4) Update() + Time.deltaTime.
(5) C++ 부모가 로직과 UPROPERTY 수치, BP 자식 3개가 값만 다르게. 프리팹+프리팹 변형과 같음.

**채점표 (10점)**

- [2] (1) 600·135 1 + Yaw 1
- [2] (2) 세 FVector 의미
- [2] (3) 24000·6000 1 + 문제·해결 1
- [1] (4) Update+deltaTime
- [3] (5) 부모·자식 역할 2 + 프리팹 대응 1

> 작성 메모: FRotator 인자 순서는 (Pitch, Yaw, Roll). DeltaTime 변동으로 값이 근사가 되는 점은 감점 대상 아님.

### P1-019 (0.29점) — 목표: W02-01, W02-02, W02-07, W13-01, W23-06

**모범 답안**

(1) ① 40 ② 65 ③ 65 ④ 1(별칭이라 같은 주소) ⑤ 65 ⑥ 1(담긴 값이 Hp 주소).
(2) 포인터: 주소 변수라 대상 변경 가능·nullptr 가능·*로 역참조. 참조: 별칭이라 선언 시 초기화 필수·대상 변경 불가·null 없음.
(3) 값 전달이라 복사본만 바뀜. void SetToZero(int& Value) 또는 void SetToZero(int* Value) + *Value = 0;(호출 SetToZero(&Hp)).
(4) Hp·Ptr·Shield: 스택. *Shield: 힙. GScore: 데이터(전역) 영역. 스택: 자동 해제·빠름·크기 제한. 힙: new 할당, 직접 delete 또는 GC·스마트 포인터 관리, 느림.

**채점표 (10점)**

- [1.5] (1) 각 0.25
- [1.5] (2) 3가지 각 0.5
- [2] (3) 이유 0.5 + 두 방식 각 0.75
- [2] (4) 스택·힙 배치 1.5(하나 틀리면 -0.5) + 전역=데이터 0.5
- [3] (4) 스택/힙 차이 4요소 중 3개 이상 3, 2개 2, 1개 1

> 작성 메모: 메모리 구조는 커리큘럼에 'CS 기본: 메모리 구조'로만 있어 코드·데이터 영역은 0.5점만 배점, 스택·힙이 핵심.

### P1-020 (0.29점) — 목표: W02-03, W02-04, W02-05, W13-02

**모범 답안**

(1) 3개. 주소를 지역 변수 E만 들고 있다가 (가)에서 블록이 끝나 E가 사라져 delete 불가.
(2) nullptr이 된 건 Boss 변수뿐이고 Target은 여전히 해제된 주소를 가리킴 → 접근 시 크래시·오염.
(3) '7 1'. B는 값 복사라 별개, P는 A의 주소라 A를 바꿈. C#이면 모두 같은 객체라 7·7. C++은 복사하면 별개 객체이고 같은 객체를 가리키려면 *·&를 명시, C# 참조 타입 변수는 GC가 관리하는 포인터.
(4) 누수: 해제 안 한 메모리가 쌓임. 댕글링: 해제된 메모리를 가리켜 접근 시 크래시·오염.

**채점표 (10점)**

- [2] (1) 3개 1 + 이유 1
- [3] (2) Target이 해제된 주소를 가리킴 2 + 위험 1
- [3] (3) '7 1'과 이유 1, C#이면 7·7 1, 관점 1
- [2] (4) 각 1

> 작성 메모: 해제된 메모리 접근은 정의되지 않은 동작이라 '크래시 또는 메모리 오염'이면 정답.

### P1-021 (0.29점) — 목표: W03-01, W03-02, W03-03, W13-06

**모범 답안**

(1) Archer Move / Base Shout / ~Archer → ~Base. Move는 virtual이라 실제 객체 함수, Shout은 포인터 타입 기준(정적 바인딩). 소멸자가 virtual이라 자식→부모.
(2) virtual 함수가 있는 클래스는 함수 주소 표(vtable)를 갖고 객체는 자기 표를 가리킨다. 호출 때 표에서 찾아 FArcher::Move가 불림.
(3) ~Base만 출력, Arrows 누수. 부모 포인터로 자식을 delete할 때 자식 소멸자부터 불리게 하려면 virtual이어야 함.
(4) override 있으면 컴파일 에러. 없으면 새 함수 Mvoe가 생겨 E->Move()가 계속 부모 함수를 부르는 조용한 버그.
(5) final: 상속·재정의 금지. void Move() override final. class ALifecycleProbe : public AActor — AActor를 부모로 public 상속.

**채점표 (10점)**

- [2.5] (1) 출력 각 0.5 + 이유 1
- [2] (2) vtable 설명
- [2] (3) ~Base만·누수 1 + 이유 1
- [1.5] (4) 컴파일 에러 0.75 + 조용한 버그 0.75
- [2] (5) final 0.5, 선언 0.5, 상속 선언·의미 1

> 작성 메모: 가상 소멸자 없는 부모 포인터 delete는 정의되지 않은 동작, 일반적 결과(부모 소멸자만)를 정답으로. vtable은 개념 수준.

### P1-022 (0.19점) — 목표: W03-04, W03-05, W03-06

**모범 답안**

(1) Super::BeginPlay()는 부모 BeginPlay 호출(C# base.BeginPlay())로 컴포넌트 BeginPlay·BP Event BeginPlay를 처리. bDebugMode면 return이 Super보다 먼저 실행돼 건너뜀. Super를 첫 줄로 옮기고 그 뒤에 if (bDebugMode) {...; return;} SetupHUD();
(2) +1, +2, in, -2, +3, out, -3, -1. 생성자: 생성 시 초기화. 소멸자: B는 범위 끝, C는 delete, A는 main 끝에 정리.
(3) ② private라 자식도 불가, ④ protected라 외부 불가. ①③은 가능.
(4) public 누구나, protected 자신+자식, private 자신만. 보호할 상태를 숨기고 필요한 것만 공개.

**채점표 (10점)**

- [2.5] (1) Super 역할(base) 1, early return 원인 1, 수정 0.5
- [3] (2) 출력 순서 1.5(틀린 줄당 -0.5) + 시점·역할 1.5
- [2.25] (3) ②④ 각 0.75 + ①③ 가능 0.75
- [2.25] (4) 차이 1.5 + 이유 0.75

> 작성 메모: Super를 맨 앞에 두는 것은 관례이고 핵심은 Super가 반드시 실행되는 것. 소멸자는 순수 C++ 객체 기준.

### P1-023 (0.19점) — 목표: W04-01, W04-02, W04-03, W08-04, W18-02

**모범 답안**

(1) 원소 타입 int32 / 생성할 컴포넌트 타입 / 변환 목표 타입. 실패 시 nullptr.
(2) &: 복사 없이 참조, const: 수정 금지, C# in. & 없으면 호출마다 복사.
(3) 11행 FString 복사 → const FString& Name(또는 const auto&). 16행 FWeaponStats 복사 → for (const FWeaponStats& Stat : AllStats).
(4) 큰 구조체 값 전달로 호출마다 복사 → const FWeaponStats& Stats.
(5) int32 AddScore(int32 Score); 작은 값은 값 전달이 낫다.

**채점표 (10점)**

- [2] (1) 각 0.5 + nullptr 0.5
- [2.5] (2) & 0.75, const 0.75, in 0.5, 복사 0.5
- [2.5] (3) 추론 각 0.5 + 수정 각 0.75
- [1.5] (4) 지적 0.75 + 수정 0.75
- [1.5] (5) 수정 0.5 + 이유 1

> 작성 메모: auto*·const auto& 등 동등한 표기 인정.

### P1-024 (0.19점) — 목표: W05-01, W05-02, W05-03

**모범 답안**

(1) (가) = 0 (나) : public FPropBase, public IInteractTarget, public ISaveable. 순수 가상 함수, 추상 클래스.
(2) ① Pull ② 에러(FLever는 ISaveable을 상속하지 않음) ③ Saved ④ 에러(추상 클래스 생성 불가).
(3) 순수 가상 함수만 가진 클래스를 인터페이스로 쓰고 부모 클래스와 함께 다중 상속.
(4) 키워드 없음·순수 가상 클래스로 표현 / 다중 상속 / 멤버 변수·구현 가능 → SaveVersion 가능(C# interface는 인스턴스 필드 불가).

**채점표 (10점)**

- [2] (1) (가) 0.5, (나) 1, 명칭 0.5
- [3] (2) 각 0.75
- [2] (3) 순수 가상 클래스+다중 상속
- [3] (4) 차이 각 1(최대 2) + 멤버 변수 가능 1

> 작성 메모: C# 8+ 기본 구현 메서드가 있어 C# 쪽은 '인스턴스 필드 불가' 수준이면 정답.

### P1-025 (0.29점) — 목표: W05-04, W05-05, W05-06, W09-03

**모범 답안**

(1) 17(12+5). 함수를 저장했다가 나중에 호출 — C# Func<int,int,int> 변수와 같음.
(2) 현재 객체 포인터 this를 복사해 담아 멤버 접근. C++은 [ ]에 명시, C#은 자동 캡처·GC가 살려 둠.
(3) 콜백이 객체보다 늦게 불려 파괴된 this로 멤버 접근 → 크래시. 원시 this는 객체를 살리지도, 사라짐을 알리지도 못함.
(4) FStreamableDelegate::CreateUObject(this, &AWeaponSpawner::OnWeaponLoaded), CreateWeakLambda(this, ...), TWeakObjectPtr 캡처+IsValid. 예:
TWeakObjectPtr<AWeaponSpawner> WeakThis = this;
... CreateLambda([WeakThis]() { if (!WeakThis.IsValid()) { return; } WeakThis->SpawnLoadedWeapon(); })
(5) 타이머도 객체보다 오래 살아 나중에 람다를 실행하므로 그사이 파괴되면 this가 댕글링이 됨.

**채점표 (10점)**

- [2] (1) 17 0.5 + 개념·비교 1.5
- [2] (2) this 캡처 1 + C# 비교 1
- [2] (3) 크래시 1 + 콜백이 늦게 불린다 1
- [2] (4) 방법 2가지 1 + 코드 1
- [2] (5) 타이머도 객체보다 오래 살아 댕글링

> 작성 메모: 람다 타이머는 UObject에 묶이지 않아 파괴 시 자동 정리되지 않는다는 전제. 해법은 멤버 함수 바인딩(SetTimer(Handle, this, &Func,...)·CreateUObject·AddUObject), CreateWeakLambda, TWeakObjectPtr+IsValid 중 하나 이상. EndPlay의 ClearTimer는 가산.

### P1-026 (0.19점) — 목표: W06-01, W06-02, W13-08

**모범 답안**

(1) (가) const를 붙여야 함(조회 함수) → bool IsMoving() const. (나) 컴파일 에러(const 함수에서 Speed 변경) → 상태를 바꾸므로 const 제거. (다) 문제없음.
(2) 현재는 에러: const 참조에서 비const IsMoving 호출 불가. const 멤버 함수는 상태를 바꾸지 않는다는 약속이라 const 객체·참조에서도 호출 가능, 안에서 바꾸면 컴파일 에러.
(3) (1) CachedCharacter = Cast<AArenaCharacter>(TryGetPawnOwner()); (2) if (!IsValid(CachedCharacter)) { return; }
(4) Cast는 비용이 있는데 결과가 매 프레임 같음. 초기화 때 1회 캐싱하고 유효성만 확인.

**채점표 (10점)**

- [3.5] (1) 각 1 + (나) 수정 0.5
- [2] (2) 에러 판단 0.5 + 약속·이유 1.5
- [3] (3) (1) 1.5 + (2) 1.5
- [1.5] (4) 비용·결과 동일

> 작성 메모: 캐싱 멤버는 UPROPERTY TObjectPtr 또는 TWeakObjectPtr 인정. 에디터 미리보기에서 TryGetPawnOwner가 nullptr일 수 있어 업데이트에서 유효성 확인 필요.

### P1-027 (0.19점) — 목표: W08-01, W08-02, W08-03

**모범 답안**

(1) 틀렸다. struct의 기본 접근 지정자는 public이고 class가 private이다. 둘의 차이는 기본 접근 지정자(상속 기본값 포함)뿐이며 기능은 같다.
(2) 드롭 항목은 몇 개의 값만 묶은 가벼운 데이터라 GC가 추적할 객체일 필요가 없다. USTRUCT는 GC 대상이 아닌 값 타입이라 복사·배열 저장이 싸고 간단하다. UCLASS는 UObject라서 생성(NewObject)·GC 관리 비용이 있고, '객체'가 필요할 때 쓴다.
(3) 예시
UENUM(BlueprintType)
enum class EItemRarity : uint8 { Common, Rare, Legendary };

USTRUCT(BlueprintType)
struct FLootEntry
{
    GENERATED_BODY()
    UPROPERTY(EditAnywhere, BlueprintReadOnly) FName ItemName;
    UPROPERTY(EditAnywhere, BlueprintReadOnly) float DropChance = 0.1f;
    UPROPERTY(EditAnywhere, BlueprintReadOnly) EItemRarity Rarity = EItemRarity::Common;
};
핵심: UENUM/USTRUCT 매크로에 BlueprintType, E·F 접두사, GENERATED_BODY(), 멤버마다 UPROPERTY. enum은 구조체보다 먼저 선언한다(답안의 선언 순서는 감점하지 않음). uint8 기반은 블루프린트 노출 enum의 관례다. 커리큘럼에 명시되지 않았으므로 누락만으로는 감점하지 않는다.

**채점표 (10점)**

- [2] (1) 동료 말의 오류 지적: struct 기본 public, class 기본 private, 차이는 그것뿐
- [2] (2) USTRUCT가 맞는 이유: GC 대상이 아닌 가벼운 값 묶음, UCLASS는 UObject
- [3] (3) UENUM(BlueprintType), enum class, E 접두사로 선언(하나 빠질 때마다 -1, uint8 누락만으로는 감점 없음)
- [3] (3) USTRUCT(BlueprintType), F 접두사, GENERATED_BODY, UPROPERTY 멤버로 선언(하나 빠질 때마다 -1)

> 검토에서 고친 점: A형 (3)이 'enum class를 쓰는 이유(범위 제한·암묵 변환 없음)'를 정답 요건으로 요구하는데, 커리큘럼(W08 생존 문법, W02 리플렉션)에는 이 내용이 없다. 근거 없는 요건이다. 또 채점표는 'uint8 기반'을 배점 문구에 넣었는데 notes는 'uint8 누락으로 감점하지 않음'이라 해서 채점자가 헷갈린다. A형 enum 항목도 선언과 이유가 3점 한 줄로 묶여 있다. A형 (3)을 커리큘럼 근거가 있는 'UENUM을 빼면 무엇이 안 되나'로 바꿨다. 두 형 모두 uint8 처리와 선언 순서를 채점표·정답에 명시했다.

> 작성 메모: BlueprintType enum의 기반 타입이 uint8이어야 하는지는 UE 5.8에서 완화 여부 확인 필요 — 채점에서 uint8 누락만으로 감점하지 않는다(관례로만 안내).

### P1-028 (0.29점) — 목표: W09-01, W09-02, W13-07

**모범 답안**

(1) UWeaponData는 UObject라 수명을 GC가 관리한다. TSharedPtr의 참조 카운트는 GC가 모르므로 (UPROPERTY로 잡히지 않아) GC가 수거하면 댕글링이 되고, 카운트 0 시 TSharedPtr이 UObject를 delete하려 해 크래시 위험. 올바른 선언: UPROPERTY() TObjectPtr<UWeaponData> CurrentWeaponData; (관찰만 한다면 TWeakObjectPtr)
(2)(a) TWeakPtr<FSoundQueue>: 비UObject 객체를 참조 카운트 증가 없이 관찰, 사용 전 유효성 확인(살아 있으면 TSharedPtr로 얻어 사용). (b) TSharedRef<FGameOptions>: 공동 소유 + null 불가가 타입으로 보장.
(3) TUniquePtr↔unique_ptr: 소유자 하나, 소유자가 사라질 때 삭제, 복사 불가(이동만). TSharedPtr↔shared_ptr: 여러 소유자, 참조 카운트가 0이 될 때 마지막 소유자가 삭제. TWeakPtr↔weak_ptr: 소유하지 않음, 지우지 않으며 카운트도 올리지 않고 대상 생존 여부만 확인. UObject에는 이들 대신 GC와 연동되는 TObjectPtr/TWeakObjectPtr.

**채점표 (10점)**

- [3] (1) UObject는 GC 관리 → TSharedPtr 문제(댕글링/이중 해제) 설명과 UPROPERTY TObjectPtr 수정
- [3] (2) TWeakPtr, TSharedRef 선택과 이유 (각 1.5점)
- [4] (3) 세 쌍 대응과 '누가 지우는가' 기준 소유 방식 차이

> 작성 메모: TWeakPtr의 Pin() 등 구체 API명은 커리큘럼에 명시되지 않았으므로 요구하지 않는다(쓰면 가점 없이 인정).

### P1-029 (0.29점) — 목표: W09-28, W13-03, W13-04, W13-05

**모범 답안**

(1) 방은 유저를, 유저는 방을 shared로 서로 잡고 있어 순환 참조. 외부 참조가 사라져도 서로의 참조 카운트가 1 이상이라 0이 되지 않아 해제되지 않는다(누수). 소유 관계상 '방이 유저를 소유'하므로 FChatUser::CurrentRoom을 TWeakPtr<FChatRoom>로 바꿔 순환을 끊는다.
(2) 복사는 5만 개 원소를 새 메모리에 복제하지만, 이동은 배열 내부 버퍼의 소유권만 새 배열로 넘기고 원본을 빈 상태로 만든다(원소 복제 없음). SetPath(MoveTemp(PathPoints)); 이동 후 PathPoints는 빈 배열(Num() == 0)로 보고 다시 읽지 않는다.
(3) 소멸자에서 자원을 해제하는데 복사 대입·복사 생성자를 기본값으로 두면 포인터만 복사되어 두 객체가 같은 자원을 갖고, 하나가 해제한 자원을 다른 하나가 다시 해제(이중 해제)하거나 대입 전 자원이 누수된다. Rule of Three: 소멸자·복사 생성자·복사 대입 중 하나를 정의하면 나머지도 정의. Five: 이동 생성자·이동 대입 포함. Rule of Zero: 자원 관리를 TArray·TUniquePtr 같은 컨테이너·스마트 포인터에 맡겨 직접 정의를 하나도 하지 않는 것이 이상적.

**채점표 (10점)**

- [3] (1) 순환 참조로 카운트가 0이 안 되는 원리 + 소유하지 않는 쪽을 weak로
- [3] (2) 이동 원리(소유권만 이전) + MoveTemp 호출 + 원본 빈 상태
- [2] (3) 기본 복사로 이중 해제/누수 원인 + Three/Five 내용
- [2] (3) Rule of Zero 설명

> 작성 메모: 이동 후 원본 TArray가 빈 상태라는 것은 UE TArray 구현 기준. std::vector는 '유효하지만 미지정 상태'가 표준이므로 C++ 일반론으로 답해도 '다시 쓰지 않는다'면 인정.

### P1-030 (0.19점) — 목표: W10-02, W10-04, W12-02

**모범 답안**

(1) Combat을 protected로 옮긴다. protected는 자기와 자식 클래스만 접근 가능해 AArenaLootBox 같은 외부 클래스는 못 건드리고(컴파일 에러로 사고 차단), 자식은 그대로 사용. public은 누구나, private은 자식도 접근 불가. (외부가 읽어야 하면 const 게터를 public으로 제공)
(2) 0~3 숫자는 의미가 코드에 드러나지 않고, 4 같은 잘못된 값이 들어와도 컴파일러가 못 막는다. 
UENUM() enum class ERangedAIState : uint8 { Idle, KeepDistance, Fire, Cooldown };
void UpdateAI(ERangedAIState State) — switch로 상태별 처리. 상태 이름으로 설계·디버깅 가능.
(3) 예: void ResetForReuse(): bConsumed = false; HealAmount = 기본값(데이터에서 다시 읽기); 충돌·가시성 다시 켜기; 진행 중 타이머 정리. 풀에서 꺼낼 때(Activate 직전/직후) 매번 호출하고, 반환 시에는 충돌·가시성·Tick을 끈다. 재사용 시 BeginPlay·생성자가 다시 불리지 않으므로 그 초기화에 의존하면 안 된다.

**채점표 (10점)**

- [3] (1) protected 변경 + 세 접근 지정자 차이 설명
- [3] (2) int 상태의 문제 + enum class 선언 + 매개변수 타입 변경
- [3] (3) bConsumed·HealAmount·충돌/가시성 등 리셋 항목
- [1] (3) 꺼낼 때 매번 호출 + BeginPlay 재호출 안 됨 근거

> 작성 메모: UCLASS() 매크로는 지면상 생략했다고 문제에 명시하지 않았으나 채점 대상 아님.

### P1-031 (0.29점) — 목표: W11-02, W13-12, C-67

**모범 답안**

(1) ① 액터 클래스는 A 접두사: AArenaWeapon. ② enum은 E 접두사 + enum class(+UENUM): UENUM() enum class EWeaponKind : uint8 { Sword, Axe }; ③ 구조체는 F 접두사(+USTRUCT): FWeaponInfo, 멤버 이름은 파스칼 케이스 Damage/Ammo. ④ 헤더에서 .generated.h는 마지막 include여야 함 → Actor.h 아래로. ⑤ .cpp는 자기 헤더 ArenaWeapon.h를 먼저 include. ⑥ UObject 멤버 포인터는 UPROPERTY + TObjectPtr: UPROPERTY(VisibleAnywhere) TObjectPtr<UStaticMeshComponent> Mesh; (UPROPERTY가 없으면 GC가 참조를 몰라 위험) ⑦ GetAmmo는 const 멤버 함수: int32 GetAmmo() const. ⑧ bool은 b 접두사: bIsEquipped. ⑨ 하드코딩 30 → MaxAmmo 데이터.
(2) 예: HandleFireInput(), ConsumeAmmo(), PlayFireSound(), PerformHitTrace(). HUD 갱신은 OnAmmoChanged 델리게이트를 브로드캐스트하고 HUD가 구독한다. 탄약 계산·HUD 갱신·사운드는 이벤트(발사·재장전) 때만 하면 되므로 Tick에서 매 프레임 할 필요가 없다.
(3) 1점(미흡): 여러 책임을 진 120줄 거대 함수, 매직 넘버(30), 네이밍 위반, UPROPERTY 없는 UObject 포인터(GC 위험). 3점이 되려면 먼저 2점 조건(네이밍 준수, C++ 베이스 + BP 자식 구조)을 갖춰야 한다. 그다음 무기는 무기 로직만 맡기고 UI는 델리게이트로 분리(책임 분리), 수치는 UWeaponData 같은 DataAsset으로(데이터 분리), 모든 UObject 포인터는 UPROPERTY TObjectPtr로(GC 안전).

**채점표 (10점)**

- [5] (1) 위반 지적과 수정(1개당 1점, 최대 5점, 접두사·const·include 순서·TObjectPtr 중 3종 이상 포함해야 5점)
- [2] (2) 함수 분리·이름 + Tick에서 뺄 일 식별
- [1.5] (3) 1점 판정과 근거(거대 함수, 매직 넘버, 네이밍 위반, UPROPERTY 없는 포인터 중 2개 이상). 2점 이상으로 판정하면 0점
- [1.5] (3) 3점 조건(책임 분리·데이터 분리·GC 안전) 제시, 하나 빠질 때마다 -0.5

> 검토에서 고친 점: B형 (3)이 '2점→3점으로 올리려면'이라고 물어서, 지금 코드가 2점이라고 답을 흘린다. 모범 답안은 1점이라 문제 문구와 정답이 서로 맞지 않는다. A형과 같은 형식('몇 점인지 근거, 3점이 되려면')으로 고쳤다. 3점 배점도 판정과 조건으로 나눠 채점자가 판단할 수 있게 했다.

> 작성 메모: '.cpp는 자기 헤더를 먼저 include'와 '.generated.h는 헤더의 마지막 include'는 Epic 표준/UHT 규칙 기준. 커리큘럼은 'include 순서'만 명시하므로 둘 중 하나를 정확히 지적하면 include 항목 인정.

### P1-032 (0.29점) — 목표: W07-01, W07-02, W07-03, W07-04, W23-07

**모범 답안**

(1) 중복 금지 기록: TSet<AActor*>(HashSet), ID→정의: TMap<FName, FItemDef>(Dictionary), 순서 있는 로그: TArray(List).
(2) for (AActor* Item : NearbyItems) { if (IsValid(Item)) { UE_LOG(LogTemp, Log, TEXT("%s"), *Item->GetName()); } } — 루프 변수가 AActor*이고 멤버 접근에 -> 사용, 널/파괴 가능성을 검사.
(3) TArray::Contains는 선형 탐색 O(n)이라 매 프레임 최대 2,000번 비교. TSet은 해시 기반 평균 O(1)이라 개수와 거의 무관. 요소가 많고 검사가 잦으므로 TSet으로 바꾼다.
(4) 포인터 값(객체 주소)이 키. 같은 BP에서 나온 똑같은 포션이라도 서로 다른 객체(주소가 다름)이므로 2개 모두 들어간다. 같은 객체를 다시 넣을 때만 중복으로 걸러진다.
(5) 스택 push/pop O(1), 큐 push/pop O(1), 연결 리스트 k번째 찾기 O(n)(앞에서부터 따라감). TArray는 메모리가 연속이라 CPU 캐시 적중률이 높아 순회가 빠르다.

**채점표 (10점)**

- [2] (1) 컨테이너 선택과 C# 대응
- [2] (2) 범위 기반 for + 포인터 원소 다루기 + 유효성 검사
- [2] (3) O(n) vs 평균 O(1) 근거로 TSet 전환
- [2] (4) 주소(객체 정체성) 기준 → 2개 들어감
- [2] (5) 세 복잡도 + 캐시(연속 메모리) 이유

### P1-033 (0.19점) — 목표: W02-19, W02-20, W13-11, W18-03

**모범 답안**

(1) TArray<float> Damages; Damages.Add(12.5f); FString PlayerName = TEXT("Hero");
(2)(가) 둘 다 1001 (나) X 위험: 추가 중 용량 초과로 재할당·이동되어 Best가 댕글링. Y는 1100 확보로 재할당이 없어 주소 유지 (다) 확보 용량을 넘게 추가하면 무효 → 추가 후 다시 얻기.
(3) Num=원소 수, 용량=확보 칸, Slack=남는 칸. 한 칸씩 늘리면 매번 재할당·복사라 느려서 여유를 두고 크게 늘림.
(4) Add: 임시 객체를 만든 뒤 복사·이동. Emplace: 인자로 배열 안에서 바로 생성.
(5) Reserve(300)으로 미리 확보(배열을 멤버로 재사용도 인정).

**채점표 (10점)**

- [1] (1) 대응
- [3.5] (2) (가) 0.5, (나) X 위험 1 + Y 안전 1, (다) 1
- [2] (3) 차이 1 + 이유 1
- [1.5] (4) 차이
- [2] (5) Reserve 1 + 이유 1

> 작성 메모: 정확한 증가 공식은 요구하지 않음. 구조체는 학생이 만든 것으로 제시.

### P1-034 (0.29점) — 목표: W06-03, W06-07, W23-05

**모범 답안**

(1) 프로세스는 독립된 메모리 공간을 가져서 다른 프로세스가 직접 건드리지 못한다. 스레드는 한 프로세스 안에서 메모리를 공유하므로 동시에 접근할 수 있다(동기화 필요). 주요 스레드: 게임·렌더·RHI·태스크 워커 스레드.
(2) 게임 스레드: 게임 로직·UObject 상태 변경. 워커 스레드: 나눈 작업을 병렬로 처리.
(3) 아니다. ++는 읽기→더하기→쓰기 3단계라, 두 스레드가 동시에 읽고 쓰면 증가분이 사라진다. 동시 접근 중 하나 이상이 쓰기인 데이터 경쟁이라 결과가 2000보다 작거나 매번 다를 수 있다.
(4) ① A: 게임 스레드 UObject(캐릭터)를 읽는다. ② B: 미리 복사한 Velocity로만 계산하므로 안전하다. ③ 둘 다 부적절: 게임 객체 상태 변경은 캐릭터 코드에서 해야 하고, B에서는 금지다. ④ A: CMC(UObject)를 읽는다. ⑤ B: 복사본끼리 대입하므로 안전하다.
(5) 워커 스레드에서 실행되므로 게임 스레드 객체의 상태를 바꾸거나 스레드 안전하지 않은 UObject에 접근하지 않고 읽기만 한다. 방법: 게임 스레드에서 미리 복사해 둔 값 읽기, Property Access.

**채점표 (10점)**

- [2] (1) 메모리 차이 1.5 + 스레드 2개 0.5
- [1.5] (2) 각 0.75
- [2] (3) '아니다' 0.5 + 설명 1.5
- [2.5] (4) ①~⑤ 위치와 이유 각 0.5(②⑤는 원칙에 따라 B만 정답)
- [2] (5) 규칙 1 + 방법 2가지 1

> 검토에서 고친 점: B형 (4)의 ②(Speed = Velocity.Size2D())와 ⑤(bIsInAir = bCachedFalling)는 게임 스레드(A)에 둬도 문제없이 동작한다. 그래서 'B'라는 정답이 하나로 정해지지 않아, A를 쓴 학생의 감점 근거가 없다. '안전한 일은 B로 옮긴다'는 원칙을 문제에 넣어 정답을 하나로 만들었다.

> 작성 메모: NativeThreadSafeUpdateAnimation은 멀티스레드 애니메이션 업데이트가 켜져 있을 때 워커 스레드에서 실행(설정에 따라 다를 수 있음, 확인 필요). 커리큘럼 서술 기준 채점. Property Access 사용법 세부는 요구하지 않음.

### P1-035 (0.29점) — 목표: W02-08, W02-09, W02-10, W02-11

**모범 답안**

(1) 매크로는 엔진에 '이 타입·멤버를 등록하라'는 표시다. UHT가 빌드 전에 헤더를 읽고 리플렉션 코드(.generated.h, GENERATED_BODY 자리)를 만든다. 그래서 엔진이 클래스·변수·함수·구조체·열거형 목록을 안다. 예: 에디터 디테일 패널 표시, 블루프린트 노드 생성, GC의 참조 추적(UPROPERTY 포인터), 직렬화(값 저장·불러오기), 네트워크 복제·RPC.
(2) ① 두 창 모두 보기만 되고 Door 카테고리 아래에 보인다. 컴포넌트를 바꿔 끼울 수는 없다. BP 노드는 없다. ② 두 창 모두 편집 가능하다. 0.2를 입력하면 1.0으로 고정된다. BP 노드는 없다. ③ 두 창 모두 편집 가능하고 BP에 Get/Set 노드가 생긴다. ④ 어디에도 보이지 않고 BP에서 쓸 수 없으며 저장되지 않는다.
(3) 가=BlueprintReadWrite: 블루프린트에서 값을 읽고(Get) 쓸(Set) 수 있다. 나=VisibleAnywhere: 모든 디테일 창에 보이지만 고칠 수 없다. 다=Category: 이 변수를 묶을 분류 이름이고, Category=이름 형태로 쓴다.

**채점표 (10점)**

- [4] (1) UHT가 매크로를 읽어 리플렉션 코드를 만든다는 점과 엔진 시스템 3개의 사용 예를 정확히 씀(시스템당 1점)
- [3] (2) 표 4행이 정확함(각 0.75점, ② ClampMin 결과 포함)
- [3] (3) 주석 3개의 지정자와 내 말 번역이 맞음(각 1점)

> 작성 메모: (3)의 주석 문장은 ObjectMacros.h namespace UP 주석의 요지를 옮긴 것이다. 출제 전에 UE 5.8 원문과 표현을 맞춰 볼 것(확인 필요). ClampMin은 디테일 패널 입력만 막고 코드나 BP Set으로 넣은 값은 막지 않는다는 점은 정답 요건에서 뺐다(확인 필요).

### P1-036 (0.29점) — 목표: W02-12, W03-08, W03-09

**모범 답안**

(1) 가 NewObject: 액터가 아닌 일반 UObject를 런타임에 만든다. 나 CreateDefaultSubobject: 생성자 안에서 컴포넌트를 만든다. 다 SpawnActor: 월드에 놓이는 액터를 만든다.
(2) 액터는 NewObject로 만들지 않는다. 월드에 액터로 등록되고 배치되려면 SpawnActor를 써야 한다. 생성자는 CDO를 만들 때와 월드 배치 전에도 실행된다. 그때는 월드·플레이어가 없어 GetWorld()나 컨트롤러가 nullptr일 수 있다. 생성자에서는 컴포넌트와 기본값만 정하고, 플레이어 찾기는 BeginPlay로 옮긴다.
(3) 엔진은 클래스마다 기본값 견본 객체인 CDO를 만든다. CDO를 만들 때도 생성자가 실행되므로, Play 전 에디터를 켤 때 로그가 찍힌다. 새 문 인스턴스는 CDO의 값을 복사해서 시작한다. BP 기본값을 편집하는 것은 CDO를 고치는 것이다.

**채점표 (10점)**

- [3] (1) 세 상황 모두 맞게 고르고 이유가 맞음(각 1점)
- [4] (2) 액터는 SpawnActor로 만듦 + 생성자에서 월드 접근 불가 이유와 BeginPlay로 옮김
- [3] (3) 생성자가 CDO 생성 때 실행됨 + 새 인스턴스가 CDO 값을 복사해 시작함

> 작성 메모: 생성자는 CDO를 만들 때도 실행된다. 그래서 에디터를 켤 때 생성자 로그가 찍히는 현상을 근거로 들 수 있다.

### P1-037 (0.48점) — 목표: W02-13, W02-14, W02-15, W02-16

**모범 답안**

(1) 그림 예: [루트] → … → UWaveManager →(UPROPERTY Rules)→ UWaveRule들. UWaveReward는 어떤 UPROPERTY 연결선에도 매달려 있지 않다. 3문장: ① GC는 루트에서 닿을 수 있는 UObject만 살린다. ② 연결선은 리플렉션에 등록된 참조, 즉 UPROPERTY다(UPROPERTY 붙은 TArray 안의 포인터 포함). ③ 닿지 않는 객체는 GC 때 수거된다.
(2) PendingReward는 등록되지 않은 참조라 GC가 수거한다. 그러면 원시 포인터는 해제된 메모리를 가리키는 댕글링이 되고, Grant 호출 때 크래시나 메모리 오염이 생긴다. GC는 정해진 주기에 돌기 때문에 GC가 돈 뒤에만 터진다. 해제된 메모리가 우연히 남아 있으면 바로 안 터지기도 해서 '가끔'처럼 보인다.
(3) TObjectPtr은 UPROPERTY 원시 포인터 멤버를 대체하는 타입이다. 에디터 빌드에서 접근 추적·지연 로드 같은 기능을 더한다. 패키지 빌드에서는 원시 포인터와 같아 비용이 없다. GC 보호 자체는 UPROPERTY가 한다.
(4) TWeakObjectPtr로 소유하지 않고 관찰만 한다. 사용 전에 IsValid()로 확인한다. 적이 사라지면 false가 된다.

**채점표 (10점)**

- [3] (1) 루트→참조 그림(Rules 연결, PendingReward 미연결) + 도달성·UPROPERTY 연결선을 담은 3문장
- [3] (2) 미등록 참조 수거 → 댕글링 → 크래시·오염, GC 시점 때문에 '가끔'
- [2] (3) TObjectPtr 이유 2개 이상
- [2] (4) TWeakObjectPtr + IsValid

> 작성 메모: TObjectPtr 상단 주석의 정확한 문구는 UE 5.8 ObjectPtr.h로 확인할 것(확인 필요). 채점 요건은 '원시 포인터 멤버 대체, 에디터 빌드 추가 기능, 패키지 빌드에선 원시 포인터와 같음' 수준으로만 둔다. UPROPERTY 없이 TObjectPtr만 쓰면 GC 참조가 되지 않는다는 점은 가점 요소로만 쓴다.

### P1-038 (0.19점) — 목표: W02-21, W02-22

**모범 답안**

(1) [1](3초): Raw:alive Registered:alive. 아직 GC 전이다. [2](6초): Raw:gone Registered:alive. GC는 UPROPERTY로 등록된 참조만 따라간다. Registered는 살아남고, Raw가 가리키던 객체는 수거된다. TWeakObjectPtr은 생존을 붙잡지 않으므로 수거되면 IsValid()가 false다.
(2) 틀렸다. GC가 객체를 지워도 원시 포인터 Raw는 nullptr로 바뀌지 않는다. 값이 남은 채 해제된 메모리를 가리키는 댕글링이 된다. 그래서 nullptr 검사를 통과하고 GetName에서 크래시나 메모리 오염이 생길 수 있다. 관찰하려면 SeeRaw.IsValid() 같은 TWeakObjectPtr 검사를 써야 한다.
(3) Play 중 콘솔(` 키, 안 열리면 Output Log의 Cmd 칸)에 obj gc를 입력한다. 자동 GC 시점은 알 수 없다. 강제로 돌려야 원하는 순간에 수거 결과를 재현할 수 있다.

**채점표 (10점)**

- [3] (1) [1] 둘 다 alive, [2] Raw gone·Registered alive 예측
- [3] (1) 이유: UPROPERTY 참조만 GC가 따라감, Weak은 생존 연장 안 함
- [2] (2) nullptr 검사로 못 막음(댕글링) + Weak IsValid로 확인
- [2] (3) obj gc를 Play 중 콘솔에 입력 + 강제 실행 이유

> 작성 메모: 자동 GC 주기는 설정에 따라 다르다. 그래서 문제에 '그 사이 자동 GC는 돌지 않았다고 가정'을 넣었다. bool을 %d로 넘기면 1/0으로 찍힌다.

### P1-039 (0.19점) — 목표: W02-17, W02-18, W04-04

**모범 답안**

(1) 가 FText: 화면에 보이고 현지화되는 문자열이다. 나 FName: 바뀌지 않는 식별자다. 뼈·소켓 이름처럼 비교가 빠른 이름에 쓴다. 다 FString: 이어 붙이는 등 조작하는 가변 문자열이다.
(2) FName은 문자열을 직접 들고 있지 않고 이름 테이블 항목의 인덱스를 저장한다. 비교는 정수 번호 비교라 글자를 하나씩 비교하는 FString보다 훨씬 빠르다. 많은 객체가 자주 비교할수록 차이가 커진다. 대소문자를 구분하지 않으므로 결과는 true다.
(3) FString Slot = FString(TEXT("Slot_")) + PlayerName;
UE_LOG(LogArena, Log, TEXT("Saved"));
문자열 리터럴은 TEXT()로 감싼다.

**채점표 (10점)**

- [3] (1) 세 값의 타입 선택과 이유(각 1점)
- [3] (2) 이름 테이블 인덱스 저장 → 번호 비교라 빠름
- [1] (2) 대소문자 무시로 true
- [3] (3) 두 줄 모두 TEXT()로 감쌈(각 1.5점)

> 작성 메모: TEXT()를 쓰는 기술적 이유(TCHAR 문자 형식)는 커리큘럼에 없다. 그래서 관례를 지키는지만 채점한다.

### P1-040 (0.10점) — 목표: W01-11, W02-24

**모범 답안**

(1) ① LogCombat ② TEXT. Output Log에 'LogCombat: Error: Health below zero: -10.000000'처럼 빨간색(에러)으로 보인다. 소수 자릿수 표기는 감점하지 않는다.
(2) 헤더의 EXTERN은 선언일 뿐이라 실제 카테고리 정의가 없다. 빌드하면 링크 에러가 난다. .cpp 하나(예: CombatLog.cpp)에서 CombatLog.h를 include하고 DEFINE_LOG_CATEGORY(LogCombat);를 한 번 쓴다.
(3) LogCombat이 선언된 헤더를 include하지 않았다. 그래서 컴파일러가 LogCombat을 모른다는 컴파일 에러가 난다. WaveManager.cpp에 #include "CombatLog.h"를 추가한다.

**채점표 (10점)**

- [4] (1) ①② 정확 + 출력 모양(LogCombat·Error·빨간색)
- [4] (2) 정의 누락 → 링크 에러 + .cpp 한 곳에 DEFINE
- [2] (3) include 누락 → 컴파일 에러 + include 추가

> 작성 메모: '정의가 빠지면 링크 에러'는 용어집의 링크 에러 정의에서 끌어낼 수 있다. 에러 원문(LNK2001 등)은 요구하지 않는다. Output Log 줄 모양은 'LogArena: Warning: 내용'이다. Log 단계는 'LogTemp: 내용'으로 단계 이름이 빠진다(확인 필요). 그래서 단계 표시는 Warning·Error만 채점한다.

### P1-041 (0.39점) — 목표: W03-07, W03-14, W03-17, W03-18, W03-27

**모범 답안**

(1) 생성자(CDO 포함) → PostInitializeComponents → BeginPlay → Tick → EndPlay → (GC). 바로잡기: ① 생성자는 CDO 생성 때도·월드 배치 전에도 실행돼 월드가 없을 수 있다. 플레이어 찾기는 BeginPlay에서 한다. ② 시작 초기화는 Tick 첫 프레임이 아니라 BeginPlay에서 한다. Tick은 매 프레임 로직용이다.
(2) Awake ↔ 생성자·PostInitializeComponents, Start ↔ BeginPlay, Update ↔ Tick, OnDestroy ↔ EndPlay. 생성자는 CDO(기본값 견본)를 만들 때도 불리므로 Awake와 1:1이 아니다.
(3) PostInitializeComponents: 컴포넌트가 모두 초기화된 직후, 게임플레이 중에 불린다. BeginPlay: 그 액터의 플레이가 시작될 때 불린다. EndPlay: 액터가 레벨에서 제거될 때 불린다(Destroy, 레벨 전환, Play 종료 등).
(4) 콜스택에 AActor::DispatchBeginPlay → AActor::BeginPlay(내 BeginPlay의 Super 호출) 흐름이 보인다. 부모 AActor::BeginPlay 안에서 컴포넌트들의 BeginPlay와 블루프린트 Event BeginPlay가 호출된다. 나머지 요소: 유니티 대응표, 'Super를 빼먹으면?' 실험 결과.

**채점표 (10점)**

- [3] (1) 순서 정확 + 두 군데 바로잡기
- [2] (2) 대응표 + CDO 설명
- [2] (3) 세 함수 호출 시점
- [3] (4) DispatchBeginPlay→BeginPlay, 부모에서 컴포넌트·BP BeginPlay 호출, 노트 나머지 두 요소

> 작성 메모: 콜스택 중간 프레임(GameMode StartPlay, WorldSettings NotifyBeginPlay 등)의 정확한 이름은 요구하지 않는다(확인 필요). Actor.h 주석은 원문 인용 대신 내 말로 요지만 채점한다.

### P1-042 (0.29점) — 목표: W03-21, W03-26

**모범 답안**

(1) (a) → (c) → BP Ready → (e) → (b) → (d). Super::BeginPlay()가 먼저 실행되고, 블루프린트 Event BeginPlay는 그 안(부모 AActor::BeginPlay)에서 불린다. 그래서 'BP Ready'가 (e)보다 먼저 찍힌다. (a)는 CDO 생성·레벨 배치 때문에 Play 전에도 찍혀 있을 수 있다.
(2) Super::BeginPlay()를 부르지 않아 부모 AActor::BeginPlay의 처리가 실행되지 않았다. 그 처리가 바로 붙은 컴포넌트들의 BeginPlay 호출과 블루프린트 BeginPlay 이벤트 호출이다. 그래서 UFloatMotionComponent는 시작 준비를 못 해 움직이지 않고, BP Print도 불리지 않는다. (참고·채점 외: 부모 BeginPlay는 액터 Tick 등록도 하므로 (b)·(d)도 안 찍힐 수 있다.)

**채점표 (10점)**

- [3] (1) 생성자→PostInit→BeginPlay→Tick→EndPlay 순서
- [3] (1) BP Ready가 (e)보다 먼저인 이유(Super 안에서 BP 이벤트 호출)
- [4] (2) Super 누락 → 컴포넌트 BeginPlay·BP BeginPlay 미호출 설명

> 검토에서 고친 점: ① 두 형 모두 레벨에 놓은 것이 C++ 클래스인지 BP 자식인지 불분명하다. C++ 클래스를 놓으면 BP 로그가 아예 찍히지 않으므로 BP 자식을 놓았다고 명시했다. ② A형 (2)는 '위 결과에서 무엇이 사라지는지'를 묻고 정답을 'BP Begin만'이라고 했다. 하지만 부모 AActor::BeginPlay는 액터 Tick 등록과 '플레이 시작됨' 상태 표시도 한다. 그래서 실제로는 [P]·[K] 로그도 사라질 수 있어 정답이 틀릴 수 있다. 묻는 범위를 커리큘럼 근거(BP 이벤트·컴포넌트 BeginPlay)로 좁혔다.

> 작성 메모: Super::BeginPlay가 빠지면 엔진이 'BeginPlay를 전달하지 못했다'는 ensure 메시지를 띄울 수 있다. 액터 Tick 등록에도 영향이 있을 수 있다(둘 다 확인 필요). 그래서 정답 요건은 BP 이벤트와 컴포넌트 BeginPlay로 한정했다. 생성자 로그는 Play 전(CDO·배치)에도 찍히므로 '가장 먼저/Play 전에도'를 정답으로 인정한다.

### P1-043 (0.29점) — 목표: W03-10, W03-15, W03-19

**모범 답안**

(1) ① 몸통: UPrimitiveComponent(StaticMesh). 렌더·충돌이 필요하다. RootComponent로 둔다. ② 경첩: USceneComponent. 위치·회전 기준점이다. 몸통에 부착한다. ③ 뚜껑: UPrimitiveComponent(StaticMesh). 경첩에 부착하면 경첩을 돌릴 때 경첩 기준으로 열린다. ④ 보상 로직: UActorComponent. 위치가 필요 없다. 계층: 몸통(Root) → 경첩 → 뚜껑.
(2) 유니티: GameObject 하나에 보상 MonoBehaviour와 자식 GameObject(경첩, 뚜껑)를 붙인다. 언리얼: Actor 하나에 여러 Component를 붙인다. 보상 로직은 ActorComponent, 위치 계층은 SceneComponent 부착으로 만든다.
(3) 월드 = (-300,0,0) + (0,-40,60) + (0,40,0) = (-300,0,60). 밀고 난 뒤에도 상대 위치는 (0,40,0) 그대로다. 월드 위치는 (-300,500,60)이다. 자식은 부모 기준 상대 Transform을 갖는다. 월드 Transform은 부모 월드와 합성된 결과라 부모를 따라간다.

**채점표 (10점)**

- [4] (1) 네 부분의 컴포넌트 종류·이유 + Root·부착 계층
- [2] (2) GameObject+MonoBehaviour ↔ Actor+Component 대응
- [4] (3) 월드 (-300,0,60), 이동 뒤 상대 불변·월드 (-300,500,60), 상대/월드 설명

> 작성 메모: 회전·스케일이 없는 경우로 수치를 단순화했다. 부착 규칙 이름(KeepRelative 등)은 요구하지 않는다.

### P1-044 (0.29점) — 목표: W03-11, W05-16, W18-10

**모범 답안**

(1) 가: 타이머(0.1~0.5초 주기) 또는 TickInterval. 매 프레임 검사할 필요가 없다. 나: 타이머(2초 지연 1회 SetTimer). 지연 실행이다. 다: SetActorTickEnabled로 필요할 때만. 매 프레임 보간 회전이라 Tick이 필요하지만 조준 중에만 켠다('Tick 유지'를 고르고 조준 중에만 켠다고 쓰면 정답). 라: 델리게이트 이벤트. 상태가 바뀔 때만 알린다. 기준: 매 프레임 필요 없는 0.1~1초 주기 검사·지연 실행은 타이머, 매 프레임 보간·물리처럼 프레임 단위가 필요한 것만 Tick.
(2) 생성자: PrimaryActorTick.bCanEverTick = true(false면 켤 수 없음). 평소에는 꺼 둔다(BeginPlay에서 SetActorTickEnabled(false), 또는 생성자에서 PrimaryActorTick.bStartWithTickEnabled = false). 조준 시작에 SetActorTickEnabled(true), 조준 종료에 false.
(3) 대기 중인 포탑 60개의 Tick 호출과 트레이스 계산이 매 프레임 사라져 게임 스레드 비용이 크게 준다. 타이머 검사는 주기마다 한 번만 돈다.

**채점표 (10점)**

- [4] (1) 가~라 선택과 이유(각 1점, 다는 'SetActorTickEnabled로 필요할 때만' 또는 'Tick 유지+조준 중에만 켬' 인정)
- [2] (1) 타이머 vs Tick 기준 문장
- [2] (2) bCanEverTick=true 1(false로 쓰면 0) + 평소 끄고 조준 시작에 켜고 종료에 끔 1
- [2] (3) 다수 액터의 매 프레임 Tick 비용 감소 설명

> 검토에서 고친 점: (2)는 'bCanEverTick=true여야 나중에 SetActorTickEnabled로 켤 수 있다'를 정답으로 요구하고, false로 쓰면 감점한다(notes). 그런데 커리큘럼은 '기본은 bCanEverTick=false, 필요할 때만 SetActorTickEnabled'라고만 써 있어, 커리큘럼만 따른 학생은 반대로 답하게 된다(근거 없는 정답 요건). 그 사실을 문제에 참고로 넣었다. 또 (1)의 다는 보기 중 'SetActorTickEnabled로 필요할 때만'이 가장 맞는데 모범 답안이 'Tick 유지'라서 채점자가 헷갈릴 수 있어, 둘 다 인정하도록 고쳤다. bStartWithTickEnabled도 정답으로 넣었다.

> 작성 메모: bCanEverTick=false인 액터는 Tick 함수가 등록되지 않는다. 그래서 SetActorTickEnabled(true)로 켤 수 없다. '가끔 켜야 하는 액터'는 true로 두고 시작 때 꺼 둔다는 점을 정답에 넣었다. 학생이 bCanEverTick=false + SetActorTickEnabled(true)를 함께 쓰면 감점한다.

### P1-045 (0.29점) — 목표: W03-12, W03-13, W03-16, W03-20

**모범 답안**

(1) 가 PlayerState: 플레이어별 공개 정보. 나 GameMode: 규칙·승패 판정. 다 GameState: 모두가 알아야 할 게임 상태. 라 HUD: 그 플레이어 화면 UI. 마 PlayerController: 입력을 받아 Pawn을 조종한다. 바 Pawn/Character: 월드에서 움직이는 몸체.
(2) GameMode는 서버(리슨 서버 호스트)에만 있다. GameState는 모든 컴퓨터에 복제된다. 클라이언트에는 GameMode가 없어 읽을 수 없다(null). 남은 적 수는 GameState에 두어야 한다.
(3) 유니티는 GameManager 싱글턴을 직접 만들어 규칙·상태·UI를 몰았다. 언리얼은 엔진이 규칙(GameMode)과 공유 상태(GameState) 등으로 역할을 나눠 두었다. 멀티플레이에서 각 클래스가 존재하는 컴퓨터도 정해져 있다.
(4) 내 GameMode의 DefaultPawnClass가 AArenaCharacter(또는 BP 자식)로 지정됐는지 확인한다. PlayerControllerClass도 함께 본다. GameMode는 이 값으로 플레이어의 Pawn을 만든다. 레벨(프로젝트 설정 또는 World Settings)이 다른 GameMode를 쓰면 그 GameMode의 기본 Pawn이 나온다. 그래서 어떤 GameMode가 쓰이는지도 확인해야 한다. InitGame은 레벨 시작 때 GameMode가 가장 먼저 게임을 초기화하는 함수다.

**채점표 (10점)**

- [3] (1) 6개 배치와 역할 한 줄(각 0.5점)
- [3] (2) GameMode 서버 전용·GameState 복제 + 클라이언트에서 못 읽음
- [1] (3) GameManager ↔ 엔진이 나눠 둔 GameMode/GameState
- [3] (4) DefaultPawnClass(·PlayerControllerClass) 확인 + 사용 중인 GameMode 확인 이유 + InitGame 시점

> 작성 메모: InitGame은 GameMode가 레벨 로드 때(다른 액터 초기화 전) 가장 먼저 받는 초기화 함수라는 수준까지만 채점한다(세부 호출 순서는 확인 필요). PlayerController는 서버와 그 플레이어의 클라이언트에, HUD는 그 플레이어의 클라이언트에만 있다.

### P1-046 (0.19점) — 목표: W04-05, W04-06, W04-17, W04-18

**모범 답안**

(1) Capsule(충돌 몸통), SkeletalMesh(보이는 몸·애니메이션), CharacterMovementComponent(이동 처리. bOrientRotationToMovement가 여기 있어 증상과 관계 있음). SpringArm(카메라 붐), Camera(시점). 카메라 둘은 시점만 담당한다. 함수: GetCharacterMovement().
(2) 컨트롤러 회전은 마우스로 바라보는 방향, 캐릭터 회전은 몸이 향한 방향이다. 지금은 bUseControllerRotationYaw가 true라서 몸이 컨트롤러 Yaw를 그대로 따라간다. 평소: bUseControllerRotationYaw=false, bOrientRotationToMovement=true. 카메라만 돌고 몸은 이동 방향으로 돈다. 조준 중: bUseControllerRotationYaw=true, bOrientRotationToMovement=false. 몸이 카메라 정면을 향한다.
(3) CharacterController → CharacterMovementComponent. Action Map → InputMappingContext(IMC). 입력 하나하나(Action) → InputAction(IA).

**채점표 (10점)**

- [3] (1) 기본 3개 + 카메라 2개 + 증상 관계 + GetCharacterMovement
- [2] (2) 회전 구분과 원인(bUseControllerRotationYaw)
- [3] (2) 평소·조준 설정값(각 1.5점)
- [2] (3) CMC·IMC·IA 대응

> 작성 메모: bOrientRotationToMovement는 CharacterMovementComponent의 속성이다. bUseControllerRotationYaw는 Pawn의 속성이다. SpringArm의 컨트롤러 회전 사용 설정은 정답 요건에서 뺐다.

### P1-047 (0.29점) — 목표: W04-07, W04-08, W04-09, W04-10, W04-27

**모범 답안**

(1) IA: 입력 의미 하나. IMC: 키↔IA 매핑 묶음(상황별 세트). Trigger: 발동 조건(누름·길게 누름·탭 등). Modifier: 입력값 가공(데드존·반전·축 변환). ETriggerEvent: 바인딩 함수를 부를 단계(Started·Triggered·Completed 등). '내리기'는 탈것 IMC의 Shift 매핑(또는 IA_Dismount)에 '0.5초 이상 눌러야 발동'하는 Trigger(Hold, 0.5초)를 단다. Trigger 종류 이름(Hold)은 몰라도 된다.
(2) 상황별 입력 세트를 추가·제거해 컨텍스트를 바꾸고, 같은 키를 다른 의미로 재사용하기 위해서다. 탈 때 AddMappingContext(IMC_Mount, 더 높은 Priority), 내릴 때 RemoveMappingContext(IMC_Mount). 기본 IMC를 그대로 두면 IMC_Mount의 Priority를 더 높게 준다. Priority가 높은 매핑이 먼저 적용되고, 입력을 소비하면 낮은 IMC의 같은 키(점프)를 막는다. 마우스 시점은 기본 IMC에 남아 계속 동작한다.
(3) void F(), const FInputActionValue&를 받는 함수, const FInputActionInstance&를 받는 함수(그 밖에 함수 이름 바인딩). 박차는 누른 순간 한 번이므로 Started, 달리기 종료는 키를 뗀 순간이므로 Completed.
(4) Space → IMC_Mount(Priority 높음, Space→IA_Boost) → IA_Boost → Trigger(Pressed) → ETriggerEvent::Started → BindAction으로 연결한 AArenaCharacter::Boost().

**채점표 (10점)**

- [2.5] (1) 다섯 요소 역할(각 0.4) + 탈것 IMC의 Shift 매핑(또는 IA)에 '일정 시간 눌러야 발동하는 Trigger'를 단다 0.5(Hold라는 이름은 몰라도 정답)
- [3] (2) IMC 분리 이유 + Add/Remove + Priority 의미와 설정
- [2] (3) BindAction 함수 형태 2개 이상 + Started/Completed 이유
- [2.5] (4) 흐름도

> 검토에서 고친 점: B형 (1)은 0.5초 눌러야 발동하는 Hold 트리거의 이름·설정을 채점한다. 하지만 커리큘럼에서 Hold·Tap 트리거는 W04 '심화(선택)'에만 나오고, A형은 특정 트리거 종류를 요구하지 않는다. 그래서 두 형의 난이도가 다르고 근거도 약하다. 트리거 종류 이름을 몰라도 개념으로 답하면 정답이 되게 채점표를 고쳤다.

> 작성 메모: AddMappingContext의 Priority 주석 요지: 우선순위가 높은 매핑이 먼저 적용되고, 입력을 소비하면 낮은 쪽을 막는다(문구는 확인 필요). BindAction 오버로드는 '인자 없는 함수 / const FInputActionValue& / const FInputActionInstance&' 가운데 2개 이상이면 정답으로 본다.

### P1-048 (0.39점) — 목표: W04-11, W04-12, W04-13, W04-19

**모범 답안**

(1) 벡터 = (800,-600,0), 길이 = √(800²+600²) = 1000. 정규화 = (0.8,-0.6,0). 길이를 1로 맞춰야 내적이 순수하게 방향(cosθ)만 나타내기 때문이다.
(2) 내적 = 0×0.8 + 1×(-0.6) = -0.6. 음수라 사이각이 90°보다 크므로 뒤쪽이다. θ ≈ 127°다. -0.6 < cos45°(0.71)이므로 시야 밖이다. 정규화하지 않으면 -600이 된다.
(3) Z = Fx·Ty − Fy·Tx = 0×(-0.6) − 1×0.8 = -0.8 < 0이므로 왼쪽이다. 확인은 DrawDebugLine/DrawDebugString으로 판정 결과를 화면에 그려 실제 위치와 맞는지 본다. 좌표계에 따라 부호 해석이 달라질 수 있기 때문이다.
(4) FVector::DotProduct(Forward, Dir), FVector::CrossProduct(Forward, Dir). 연산자: Forward | Dir, Forward ^ Dir.

**채점표 (10점)**

- [2] (1) 벡터·길이 1000·정규화 (0.8,-0.6,0) + 정규화 이유
- [3] (2) 내적 -0.6 → 뒤·약 127°·시야 밖 + 근거
- [1] (2) 정규화 안 하면 -600
- [2] (3) Z=-0.8 → 왼쪽 + 디버그 드로잉 확인
- [2] (4) DotProduct/CrossProduct + | / ^

> 작성 메모: UE는 X 앞, Y 오른쪽, Z 위다. Forward × ToTarget의 Z가 양수면 오른쪽이다. 문제에 코사인 값 표를 줘서 계산기 없이 풀 수 있게 했다.

### P1-049 (0.19점) — 목표: W04-14, W04-15, W04-16, W23-08

**모범 답안**

(1) 오일러각(FRotator)을 축별로 따로 보간하면 회전 경로가 부자연스럽다. 특정 자세(위를 봄)에서는 두 축이 겹치는 짐벌락으로 회전이 튄다. 회전 연산은 FQuat로 바꿔 Slerp로 보간하고, 편집·표시만 FRotator로 한다. 이유: 짐벌락 회피, 자연스러운 Slerp 보간, 안정적인 회전 합성.
(2) 로컬 (200,0,50)을 Yaw 180° 돌리면 (-200,0,50)이다. 위치를 더하면 월드 (-200,300,50)이다. 로컬은 부모(액터) 기준 좌표, 월드는 레벨 기준 좌표다. 로컬→월드는 부모의 회전·이동(스케일)을 적용해 바꾸는 것이다.
(3) 언리얼에서 Y는 위가 아니라 오른쪽이다. 그래서 아이콘이 위가 아니라 옆(오른쪽)으로 5 움직인다. 위로 올리려면 Z를 써야 한다. UE: 왼손·Z-up·X-forward. 유니티: 왼손·Y-up·Z-forward.
(4) ① 정규화·길이 ② 내적=cosθ로 앞뒤·시야각 ③ 외적으로 좌우·법선 ④ 쿼터니언 회전(짐벌락·Slerp)과 로컬↔월드 Transform.

**채점표 (10점)**

- [3] (1) 원인(오일러각 보간·짐벌락) + FQuat Slerp로 변경 + 이유 3개
- [3] (2) 월드 (-200,300,50) + 로컬→월드 설명
- [2] (3) Y가 오른쪽이라 옆으로 감 + 좌표계 비교
- [2] (4) 요점 4개

> 작성 메모: UE 회전 방향은 Yaw가 +일수록 X축이 Y축 쪽으로 돈다고 보고 수치를 정했다. 스케일 1, Pitch·Roll 0이다. 유니티도 왼손 좌표계라는 점을 정답에 넣었다.

### P1-050 (0.29점) — 목표: W04-26, W06-15, W11-09

**모범 답안**

(1) ① Len. 벡터를 자기 길이로 나눠 길이 1로 정규화한다. 그래야 내적이 cosθ가 된다. ② > (>=도 인정). UE에서 Fwd × Dir의 Z가 양수면 오른쪽이다. CalculateDirection처럼 오른쪽을 +로 두려면 Z>0일 때 Deg를 그대로 둔다. | 는 내적(DotProduct), ^ 는 외적(CrossProduct)이다.
(2) P: 상대 (0,400) → 오른쪽 90°, +90 → HitRight, R. Q: 상대 (-300,-100) → 뒤쪽 왼편, 약 -162° → |Deg|≥120 → HitBack, L. S: 상대 (200,-200) → 앞쪽 왼편, -45 → |Deg|≤60 → HitFront, L.
(3) 크기는 같고 부호만 반대다. 그러니 좌우 부호 규약이 CalculateDirection과 반대로 구현됐다(② 연산자 오류). 이 상태에서 P는 -90이 되어 HitLeft가 재생된다(오른쪽에서 맞았는데 왼쪽 리액션).

**채점표 (10점)**

- [2] (1) ① Len과 정규화 의미 + | / ^ 의미
- [3] (1) ② > + Z 부호와 오른쪽 + 규약 근거
- [3] (2) P·Q·S 각도·몽타주·글자(각 1점)
- [2] (3) 부호 규약 반대 진단 + HitLeft 재생

> 작성 메모: CalculateDirection은 BaseRotation 정면 기준 Velocity 방향을 -180~180으로 돌려준다. 오른쪽이 +다(내부는 Right 벡터 내적 부호로 뒤집음). 문제에 이 규약을 적어 두었다. FMath::Acos 입력 범위 처리는 정답 요건에서 뺐다.

### P1-051 (0.29점) — 목표: W05-07, W05-08, W05-10, W05-19

**모범 답안**

(1) UPickupable: 리플렉션·블루프린트에 인터페이스를 알리는 빈 껍데기(UInterface 파생). IPickupable: 실제 C++ 가상 함수(OnPickedUp) 선언. 구현 클래스가 상속한다. 언리얼 리플렉션은 UObject 기반이라 U 클래스가 있어야 엔진·BP가 인터페이스를 알 수 있다. 그래서 두 개로 나뉜다. 상속: class ACTIONARENA_API APotionPickup : public AActor, public IPickupable
(2) BP에서 구현한 열쇠는 C++ IPickupable을 상속하지 않았다. 그래서 Cast<IPickupable>이 실패(nullptr)해 호출이 안 된다. 고친 코드:
if (Overlapped && Overlapped->Implements<UPickupable>()) { IPickupable::Execute_OnPickedUp(Overlapped, this); }
(3) C# interface 하나 ↔ 언리얼 UInterface + IInterface 쌍. 구현 확인은 Implements<UPickupable>(), 호출은 Execute_OnPickedUp으로 한다. 그래야 C++·BP 구현 모두 같은 방식으로 다룰 수 있다.

**채점표 (10점)**

- [4] (1) U·I 역할 + 리플렉션이 UObject 기반이라 분리 + 상속 줄
- [4] (2) BP 구현은 Cast 실패 이유 + Implements·Execute_ 코드
- [2] (3) C# interface ↔ UInterface+IInterface 대응

> 검토에서 고친 점: A형 상황이 기술적으로 틀렸다. BlueprintNativeEvent 인터페이스 함수를 I->Interact(this)처럼 직접 부르면, UHT가 만든 본문의 check('Do not directly call Event functions in Interfaces')에 걸려 C++ 문도 반응하지 않고 멈춘다. 그래서 '문은 반응하는데'라는 전제가 사실과 다르다. 호출은 Execute_로 바꾸고 막힌 곳이 Cast 검사뿐이 되게 고쳤다. 이렇게 하면 B형(Cast+직접 호출)과 코드 모양도 달라진다.

> 작성 메모: BlueprintNativeEvent 인터페이스 함수를 C++ 포인터로 직접 부르면 엔진이 막는다(확인 필요). 그래서 정답 요건은 커리큘럼 설명(BP 구현 액터는 Cast 실패, Execute_ 사용)으로 한정했다.

### P1-052 (0.39점) — 목표: W05-11, W05-12, W05-13, W05-14, W05-20

**모범 답안**

(1) 단일: 바인딩 1개. 멀티캐스트: 여러 개, Broadcast. 일반: C++ 전용·빠름·람다 가능. 다이나믹: 리플렉션 기반, BP 노출·직렬화 가능, UFUNCTION만, 느림. 스태미나 변화: BP 위젯이 듣고 듣는 쪽이 여럿이므로 다이나믹 멀티캐스트. 바닥남: C++ 내부 전용이므로 일반 델리게이트(듣는 쪽이 늘 수 있으면 일반 멀티캐스트, 하나뿐이면 단일도 인정).
(2) DECLARE_DYNAMIC_MULTICAST_DELEGATE_OneParam(FOnStaminaChanged, float, Current);
DECLARE_MULTICAST_DELEGATE(FOnStaminaDepleted); (또는 단일 DECLARE_DELEGATE(FOnStaminaDepleted);)
(3) Stamina->OnStaminaChanged.AddDynamic(this, &AArenaCharacter::StopSprint); StopSprint는 UFUNCTION()이어야 하고 매개변수 float가 맞아야 한다. Stamina->OnStaminaDepleted.AddUObject(this, &UFatigueBrain::OnDepleted); 해제: Stamina->OnStaminaChanged.RemoveAll(this); 람다는 일반 델리게이트에 AddLambda.
(4) 다이나믹은 리플렉션 기반이라 일반보다 느리고 UFUNCTION 바인딩이 필요하다. 그래서 BP 노출·직렬화가 필요할 때만 쓴다. C# event·Action ↔ 일반 멀티캐스트/단일 델리게이트, UnityEvent ↔ BP에 노출되는 다이나믹 멀티캐스트.

**채점표 (10점)**

- [3] (1) 4종 차이 + 두 이벤트의 종류 선택 이유
- [2] (2) 두 선언이 이름 규칙에 맞음
- [3] (3) AddDynamic+UFUNCTION·AddUObject·RemoveAll·AddLambda
- [2] (4) 다이나믹 비용 + C# 대응

> 검토에서 고친 점: A형 (3)은 (1)에서 고른 다이나믹 멀티캐스트(정답)에 람다를 '델리게이트 종류에 맞는 함수로' 바인딩하라고 한다. 그런데 다이나믹 델리게이트에는 람다를 붙일 수 없어서, 정답은 문제에 나오지 않은 두 번째 C++ 전용 델리게이트(OnHealthChangedNative)를 전제한다. 또 블루프린트 위젯이 C++로 RemoveAll(this)를 쓴다는 설정도 어색하다. 그 결과 B형보다 추론이 많이 필요하다. 두 번째 델리게이트를 문제에 명시하고, '람다를 왜 못 붙이나'를 직접 묻고, 해제 주체를 C++ 사운드 관리자로 바꿨다.

> 작성 메모: AddLambda로 붙인 람다는 RemoveAll(this)로 떼어지지 않는다(객체에 묶이지 않음). 커리큘럼에 없으므로 가점 요소로만 본다(확인 필요). 다이나믹 델리게이트의 BP 노출 지정자(BlueprintAssignable)는 요구하지 않는다.

### P1-053 (0.19점) — 목표: W05-18, W05-29

**모범 답안**

(1) 압력판은 '밟혔다'는 사실만 알린다. 누가(함정·문) 반응하는지 모른다. 함정·문이 스스로 구독한다. Broadcast는 구독된 함수들을 한꺼번에 부르고, 압력판 코드에는 받는 쪽 클래스가 없다.
(2) 가: 단순하고 흐름이 명확하다. 하지만 압력판이 함정·문 클래스를 알아 결합도가 높다. 대상 종류가 늘 때마다 수정해야 한다(조건 위반). 나: 압력판은 대상을 모른다. 대상 추가 시 압력판 수정이 없다. 대신 받는 쪽이 압력판을 알아야 하고 바인딩·해제 관리가 필요하며, 흐름 추적이 어렵다. 다: 압력판은 인터페이스만 안다. 인터페이스 작성 비용이 있고, 압력판이 대상 목록을 관리하며 파괴된 대상 검사가 필요하다.
(3) 예: 나를 고른다. 조건 충족, 대상 4개를 델리게이트 하나로 처리, 확장 시 압력판 수정 0줄이다. 주의: 파괴되는 함정은 EndPlay 등에서 RemoveAll(this)로 바인딩을 해제해 파괴된 객체가 호출되지 않게 한다. (다를 골랐다면 대상의 유효성(IsValid) 확인을 써야 한다)

**채점표 (10점)**

- [3] (1) 옵저버 패턴 설명 + Broadcast 연결
- [4.5] (2) 세 설계 장단점(각 1.5점)
- [2.5] (3) 선택과 근거 + 파괴된 대상 주의점

> 작성 메모: 고른 설계가 무엇이든 근거가 타당하면 정답이다. 모범 답안은 커리큘럼 과제(레버가 델리게이트로 문 여러 개와 연결, 레버는 문 클래스를 모름)를 따른다.

### P1-054 (0.19점) — 목표: W05-17, W05-21, W05-22

**모범 답안**

(1) BeginPlay 후 1초 뒤 첫 실행, 이후 0.25초마다 반복한다. 매번 적 위치에서 타깃 위치로 선을 쏴 처음 막는 액터가 타깃이면 bCanShoot = true다. 벽 등 다른 것이 먼저 막으면 false다. 타깃이 사라졌으면 검사하지 않는다.
(2) 타이머: InvokeRepeating("CheckLineOfSight", 1f, 0.25f) 또는 WaitForSeconds를 쓰는 코루틴 루프 → FTimerManager SetTimer. 트레이스: Physics.Raycast → LineTraceSingleByChannel.
(3) 구 Sweep은 두께가 있어 좁은 틈이나 모서리에 걸려 실제로는 보이는데 막힌 것으로 나오거나, 맞는 대상이 달라질 수 있다. 시야(사선)는 '눈에서 대상까지 직선이 뚫리는가'이므로 두께 없는 라인이 의미에 맞고 가볍다.
(4) GetWorldTimerManager().ClearTimer(AimTimer); (예: EndPlay·사망 처리에서). Target은 플레이어를 소유하지 않고 관찰만 하며, 사라지면 IsValid()가 false가 되도록 하기 위해서다.

**채점표 (10점)**

- [3] (1) 1초 지연 후 0.25초 반복 + 라인으로 사선 판정 흐름
- [3] (2) 코루틴/InvokeRepeating ↔ FTimerManager, Raycast ↔ LineTraceSingleByChannel
- [2] (3) 구 vs 라인 차이와 시야 판정에 라인이 맞는 이유
- [2] (4) ClearTimer + Weak 이유

> 작성 메모: 유니티의 SphereCast 대응은 커리큘럼에 없으므로 가점 요소로만 본다. SetTimer(핸들, 객체, 함수, 주기, 반복) 형태는 TimerManager.h 오버로드 기준이다.

### P1-055 (0.29점) — 목표: W06-04, W06-06, W06-08, W06-09

**모범 답안**

(1) EventGraph: 게임 값을 읽어 변수를 갱신하는 로직. AnimGraph: 변수로 상태 머신·블렌드를 평가해 포즈를 만드는 곳. 속도 계산은 값 갱신이므로 EventGraph(또는 C++ NativeUpdateAnimation)에서 한다. AnimGraph는 포즈 계산 전용이다.
(2) Initialize는 처음 한 번만 불려 Speed가 갱신되지 않는다(계속 처음 값). Initialize: Owner Cast 후 Character·CMC 포인터 캐싱. Update: 매 프레임 유효성 확인 후 Speed·bIsInAir 갱신.
(3) 375는 Walk(150)와 Run(450) 사이다. Run 약 75%, Walk 약 25%다(Run 쪽에 가까움). 블렌드스페이스는 속도·방향 값에 따라 인접한 샘플 애니메이션을 연속적으로 섞는다. 그래서 속도가 조금씩 변해도 걸음이 끊기지 않고 자연스럽다.
(4) 상태: Idle/Move(블렌드스페이스), JumpStart, Fall(Loop), Land. 룰: Idle/Move → JumpStart: bIsInAir. JumpStart → Fall: JumpStart 애니메이션이 거의 끝남. Fall → Land: !bIsInAir. Land → Idle/Move: Land가 거의 끝남(또는 이동 시작).

**채점표 (10점)**

- [2] (1) 두 그래프 역할 + ①이 맞지 않는 이유
- [3] (2) ② 문제 + Initialize/Update 바른 분담
- [2] (3) Run 쪽에 가깝게 약 3:1 + 블렌드스페이스 장점
- [3] (4) 상태와 트랜지션 룰

> 작성 메모: 블렌드스페이스 비율은 1D 선형 보간을 기준으로 계산했다(스무딩 설정 무시). 정확한 수치 대신 '어느 쪽에 가깝게 섞이는지'만 맞아도 부분 점수를 준다.

### P1-056 (0.19점) — 목표: W06-10, W06-11, W06-12, W06-16

**모범 답안**

(1) A: 애니메이션과 실제 이동이 따로 놀아 발이 미끄러지거나 거리가 어긋나기 쉽다. B: 애니메이션 루트 뼈의 이동을 캐릭터 실제 이동으로 써 거리·궤적이 애니메이션과 정확히 맞는다. 멀티플레이에서는 몽타주의 루트 모션만 안정적으로 지원되므로 구르기를 몽타주로 재생하고 'Montages Only'를 기본으로 둔다.
(2) Speed 파라미터 ↔ AnimBP 변수 Speed(AnimInstance가 갱신), Idle/Run 상태 ↔ 상태 머신 상태, 'Speed > 0.1' 트랜지션 ↔ 트랜지션 룰.
(3) 밀어 넣기(유니티): 세 스크립트가 모두 Animator를 알고 값을 넣는다. 갱신 시점은 명확하지만 결합도가 높고 갱신 지점이 흩어져 추적이 어렵다. 당겨오기(언리얼): AnimInstance가 NativeUpdateAnimation 한 곳에서 캐릭터·CMC·전투 상태를 읽는다. 게임 로직은 애니메이션을 모르고, 한 곳만 보면 된다. 대신 매 프레임 읽고 포인터 캐싱이 필요하다. 값 수집과 그래프 평가가 분리되므로 평가(심화: NativeThreadSafeUpdateAnimation)를 워커 스레드에서 병렬로 처리하기 쉽다.
(4) 유니티: [Move]·[Combat]·[Hit] --SetFloat/SetBool--> [Animator] → 포즈. 언리얼: [Character·CMC·CombatComponent] <--매 프레임 읽기-- [AnimInstance NativeUpdateAnimation] → 변수 → [AnimGraph] → 포즈.

**채점표 (10점)**

- [2.5] (1) A/B 차이 + 몽타주·Montages Only 이유
- [1.5] (2) 변수·상태·트랜지션 룰 대응
- [4] (3) 두 구조 비교 장단점 + 멀티스레드 유리한 이유
- [2] (4) 세 스크립트가 들어간 화살표 그림 2개

> 작성 메모: '몽타주 루트 모션만 네트워크에서 안정적으로 지원'은 커리큘럼 서술을 따른다. 멀티스레드 부분은 '값 수집과 애니 평가를 분리하면 워커 스레드에서 병렬로 갱신할 수 있다(NativeThreadSafeUpdateAnimation)' 수준까지만 요구한다.

### P1-057 (0.29점) — 목표: W07-05, W07-06, W07-07

**모범 답안**

(1) 몽타주는 CompositeSections 배열에 섹션별 이름·시작 위치·다음 섹션 연결 정보를 담는다. Slot은 몽타주가 재생되는 AnimGraph의 채널(예: DefaultSlot)로, AnimBP AnimGraph에 그 Slot 노드가 있어야 포즈에 반영되어 보인다.
(2) Start → Loop → Loop → … (누르는 동안 반복) → 떼는 순간 Release → 종료. (가) Start가 끝나면 Loop로 가도록 예약. (나) Loop가 끝나면 다시 Loop로 가도록 예약해 반복. (다) 떼는 즉시 Release 섹션으로 점프.
(3) SetNextSection은 '현재 섹션이 끝난 뒤'로 예약하므로, 뗀 순간이 아니라 진행 중인 Loop 한 바퀴가 끝나야 Release가 나와 입력이 늦게 반응하는 느낌이 든다. JumpToSection은 즉시 전환.
(4) 피격 몽타주에 의해 중단되므로 블렌드아웃이 시작될 때 HandleBlendingOut이 먼저, 몽타주가 완전히 끝날 때 HandleEnded가 나중에 불리며 둘 다 bInterrupted = true. 떼기 전에 끊겼으므로 OnChargeReleased가 정리를 못 했다. HandleEnded에서 bIsCharging=false와 차지 상태를 정리하지 않으면 '차지 중' 상태가 남아 이후 입력·이동이 꼬인다(종료 콜백이 안전장치). 핸들러는 AddDynamic용 UFUNCTION이어야 한다.

**채점표 (10점)**

- [2] (1) CompositeSections 구조·Slot 설명 + Slot 노드 필요
- [3] (2) 섹션 순서 + (가)(나)(다) 역할
- [2] (3) 예약은 현재 섹션 끝난 뒤라 반응 지연
- [3] (4) BlendingOut→Ended 순서, bInterrupted=true, 종료 콜백 정리의 중요성

> 작성 메모: Montage_IsPlaying, SetMovementEnabled, ClearChargeState는 설명을 붙였거나 학생 함수로 가정. OnMontageEnded/BlendingOut이 해당 AnimInstance의 모든 몽타주에 대해 브로드캐스트된다는 점은 UE 5.8 소스 기준으로 확인됨(AnimInstance.h).

### P1-058 (0.19점) — 목표: W07-08, W07-14, W07-15

**모범 답안**

(1) 무적 ON/OFF → AnimNotifyState: 유니티 OnStateEnter/OnStateExit처럼 구간의 시작(NotifyBegin)과 끝(NotifyEnd)을 받는다. 먼지 1회 → AnimNotify: 유니티 Animation Event처럼 애니메이션의 특정 시점에 한 번 불린다.
(2) NotifyState 1개가 낫다. 시작과 끝이 한 객체의 Begin/End 쌍으로 묶여 구간 의미가 분명하고, 길이를 타임라인에서 한 번에 조절하며, 끝 노티파이를 빠뜨리거나 순서가 꼬이는 실수가 줄어든다(무적 OFF를 놓치면 영구 무적 버그). 단, 몽타주 중단 시를 대비해 종료 콜백 정리도 둔다.
(3) AnimNotify: 한 시점 이벤트 — 발소리, 타격 이펙트·사운드 1회. AnimNotifyState: Begin → Tick → End 구간 — 히트 판정 활성 구간, 콤보 입력 구간(또는 무적 구간·무기 궤적).

**채점표 (10점)**

- [4] (1) 무적=NotifyState(Enter/Exit 대응), 먼지=Notify(Animation Event 대응)
- [3] (2) NotifyState가 나은 이유(Begin/End 쌍, 누락 위험 감소)
- [3] (3) 일반화된 차이 + 쓰임 각 2개

### P1-059 (0.29점) — 목표: W07-09, W07-11, W07-27

**모범 답안**

(1) 피격 몽타주가 공격 몽타주를 끊으면서 HitWindow 구간의 NotifyEnd가 정상 처리되지 않으면 판정 상태가 꼬인다. '켜진 채 남음' → 가만히 있어도 계속 판정. 반대로 판정 플래그·맞은 대상 집합 등의 상태가 정리되지 않은 채 남거나 다음 Begin이 기대대로 오지 않으면 이후 판정이 막혀 '못 맞힘'. 다른 상황: 메시가 화면 밖이라 애니메이션 틱이 생략되는 설정, 극단적 저프레임에서 시작/종료 처리가 꼬임, 블렌드아웃 경계.
(2) 몽타주 종료 콜백(OnMontageEnded, bInterrupted=true 포함)에서 판정 OFF, 맞은 대상 집합 비우기, 콤보 인덱스·입력 창 상태 리셋. 피격 처리 시작 시에도 공격 상태를 명시적으로 정리.
(3) 콤보 입력 윈도우: 다음 공격 입력을 받아 주는 구간으로, 그 안의 입력을 기억했다가 현재 동작 끝에서 다음 섹션으로 잇는 입력 버퍼링. 입력 큐 장점: 구간보다 조금 일찍 누른 입력도 저장했다가 처리해 씹힘이 줄고 반응이 관대해진다. 위험: 큐를 비우지 않으면 피격 후·사망 후 오래된 입력이 튀어나와 의도치 않은 공격이 나감 → 유효 시간·중단 시 비우기 필요.
(4) 공격 중 피격 후 다음 공격이 정상 판정, 몽타주 중단 후 판정 OFF, 윈도우 밖/오래된 입력 무시, t.MaxFPS 30에서 누락 없음, 한 스윙당 한 적 1회 타격.

**채점표 (10점)**

- [3] (1) 중단으로 End 처리 꼬임 → 두 증상 설명 + 다른 상황 2가지
- [2] (2) 종료 콜백에서 판정·집합·콤보 상태 정리
- [3] (3) 입력 윈도우 개념 + 입력 큐 장점과 위험
- [2] (4) 체크리스트 4개

> 작성 메모: 몽타주가 중단될 때 NotifyEnd가 반드시 호출되는지 여부는 엔진 버전·설정(브랜칭 포인트, 틱 옵션)에 따라 달라 정답 요건에서 '항상 안 불린다'로 단정하지 않는다 — 커리큘럼 표현('중단·블렌드아웃 경계에서 꼬일 수 있다') 수준이면 인정.

### P1-060 (0.29점) — 목표: W07-10, W07-12, W07-13, W07-16

**모범 답안**

(1) 독 장판: Overlap — 느리게 움직이고 '들어옴/나감' 이벤트로 충분, 설정이 간단. 무기: Sweep — 빠른 무기는 Overlap에서 프레임 사이 통과(터널링)할 수 있지만 Sweep은 이전→현재 위치를 연속 검사해 정확. 대신 직접 호출·관리 필요.
(2) Object Channel은 컴포넌트 자신의 종류(방패는 'Shield'), Trace Channel은 쿼리용 채널(무기 판정 'Weapon'). 각 컴포넌트는 채널별 Block/Overlap/Ignore 응답을 가진다. 방패: Weapon 채널에 Block(트레이스가 방패에서 멈춰 뒤의 몸까지 가지 않음), Pawn 채널에 Ignore(또는 Overlap — 이동을 막지 않음).
(3) ① ImpactPoint에 생성, ImpactNormal 방향으로 회전. ② 맞은 컴포넌트(FHitResult의 Component)가 방패 컴포넌트인지, 또는 BoneName이 몸의 뼈인지로 구분(맞은 액터는 GetActor()).
(4) 유니티는 레이어 쌍 표로 충돌 on/off. 언리얼은 '자기 종류(Object Channel)' + '상대 채널마다의 응답(Block/Overlap/Ignore)'으로 표현: 방패는 Weapon에 Block, Pawn에 Ignore. Overlap을 따로 둘 수 있어 표보다 세분화된다.

**채점표 (10점)**

- [3] (1) 장판=Overlap, 무기=Sweep 선택과 장단점 근거
- [3] (2) Object/Trace 차이 + 방패 응답(Weapon Block, Pawn Ignore)
- [2] (3) ImpactPoint·ImpactNormal + 컴포넌트/BoneName 구분
- [2] (4) Layer Matrix ↔ 채널+응답 대응

> 작성 메모: Trace 응답이 Block인지 Overlap인지는 사용하는 쿼리(Single/Multi, ByChannel)에 따라 결과가 달라지므로 '쿼리 방식에 맞게'를 인정한다.

### P1-061 (0.29점) — 목표: W07-32, W10-01, W10-03, W10-29

**모범 답안**

(1) 책임 분리: 전투는 컴포넌트가, 캐릭터는 이동·입력·조립을 맡는다. 플레이어 입력 콜백과 적 BT 태스크가 같은 CombatComponent를 호출하면 공격 로직이 한 곳에 있다. 그래서 버그 수정·밸런스 조정이 한 번에 적용되고 캐릭터 클래스가 거대해지지 않는다. 복사하면 수정할 때 두 곳을 고쳐야 하고 둘이 어긋난다.
(2) 부모(AArenaCharacterBase): HealthComponent·CombatComponent, 데미지 수신·체력 감소, 피격 몽타주 재생, 사망 공통 흐름. 자식: 플레이어는 화면 흔들림·입력 바인딩, 적은 BT/Blackboard 갱신.
(3) 예: 부모 protected에 void HandleHit(const FHitResult& Hit); (체력 감소 → 피격 몽타주 → OnHitSpecific(Hit))와 virtual void OnHitSpecific(const FHitResult& Hit) {}를 둔다. 플레이어는 virtual void OnHitSpecific(...) override;에서 화면을 흔든다. 적은 override에서 Blackboard '피격됨'을 갱신한다.
(4) 리팩터링 이유: 체력 감소·피격 몽타주·사망 처리가 부모 한 곳에만 있어 복사본(중복)이 사라진다. 플레이어와 적이 같은 데미지 파이프라인(ApplyDamage → TakeDamage → HealthComponent)을 쓰므로 버그 수정·밸런스 조정이 한 곳에서 끝난다. 차이(화면 흔들림 / BT 표시)는 가상 함수 재정의로만 드러난다.
Super 누락: 부모의 공통 처리(체력 감소·피격 몽타주)가 실행되지 않아 그 캐릭터만 체력이 안 줄거나 피격 반응이 없다. 공통 흐름 함수(HandleHit)를 부모에 비가상으로 두고 '다른 부분'만 빈 가상 훅(OnHitSpecific)으로 열어 두면, 자식은 훅만 재정의한다. Super를 부를 일 자체가 없으니 누락 위험이 줄어든다. 전체를 virtual로 둔다면 override에서 Super:: 호출이 필수다.

**채점표 (10점)**

- [2] (1) 컴포넌트 분리 이유(책임 분리·재사용·한 곳 수정)
- [3] (2) 부모/자식 구분이 적절함
- [3] (3) 공통 흐름 + 가상 훅 선언과 override 위치
- [1] (4) 리팩터링 이유(중복 제거·같은 데미지 파이프라인·한 곳에서 버그 수정 중 2개 이상)
- [1] (4) Super 누락 결과(공통 처리 미실행) + 비가상 공통 흐름·가상 훅 구조로 줄이는 방법

> 검토에서 고친 점: 설계표 covers의 W10-29(공통 베이스 클래스로 리팩터링하는 이유: 중복 제거, 같은 데미지 파이프라인, 차이는 가상 함수로만 재정의)를 A형은 (4)에서 묻는다. B형은 이 이유를 직접 묻지 않는다. B형 (1)은 컴포넌트 분리 이유이고 (4)는 Super 누락만 다룬다. B형 (4)에 리팩터링 이유를 보강하고 배점을 나눴다.

### P1-062 (0.39점) — 목표: W08-05, W08-06, W08-07, W08-09, W08-16

**모범 답안**

(1) 독 장판: ApplyDamage — 위치·방향이 필요 없는 일반 데미지. 폭발 화살: ApplyPointDamage — HitFromDirection과 FHitResult(ImpactPoint·BoneName)를 넘겨 받는 쪽이 지점·뼈별 리액션 가능. 예: UGameplayStatics::ApplyDamage(Victim, 5.f, nullptr, this, UDamageType_Poison::StaticClass()); (함정이라 가해 컨트롤러는 없음, 가해 액터는 장판 자신)
(2) 데미지 종류를 구분한다. 받는 쪽에서 DamageType이 독이면 독 저항 적용, 초록색 숫자·독 이펙트, 방어 무시 등 종류별 처리를 한다.
(3) ApplyDamage → (FDamageEvent 생성) → 대상 AActor::TakeDamage(가상) → Actor.cpp의 AActor::TakeDamage 구현에서 OnTakeAnyDamage 브로드캐스트 → 구독 중인 HealthComponent 핸들러가 Health 감소 → OnHealthChanged 브로드캐스트 → HUD 갱신.
(4) override 안에서 Super::TakeDamage(...) 호출이 빠졌다. 부모 구현이 OnTakeAnyDamage(포인트면 OnTakePointDamage도) 브로드캐스트를 하므로, 빼먹으면 HealthComponent가 이벤트를 못 받아 체력이 안 깎인다. 무적이면 0 반환, 아니면 return Super::TakeDamage(DamageAmount, DamageEvent, EventInstigator, DamageCauser);
(5) SendMessage는 문자열로 함수를 찾아 호출(오타·시그니처 불일치를 컴파일러가 못 잡음). 언리얼은 ApplyDamage/ApplyPointDamage → TakeDamage → 델리게이트의 타입 안전한 파이프라인이고 가해자·종류·히트 정보가 표준 형태로 전달된다.

**채점표 (10점)**

- [2.5] (1) 두 함수 선택과 이유 + ApplyDamage 호출 인자
- [1.5] (2) DamageType 활용(종류 구분)
- [2.5] (3) ApplyDamage→TakeDamage→OnTakeAnyDamage→HealthComponent 흐름 + Actor.cpp TakeDamage
- [2] (4) Super 누락과 이유, 수정
- [1.5] (5) SendMessage 대응과 차이

> 작성 메모: ApplyDamage/ApplyPointDamage가 BaseDamage 0일 때 호출 자체를 건너뛰는 등 세부 조건은 정답 요건에서 제외. 인자 순서는 GameplayStatics.h 기준(UE 5.8 확인 필요하나 오래 유지된 시그니처).

### P1-063 (0.29점) — 목표: W08-08, W08-10, W08-13

**모범 답안**

(1) 소유 액터의 OnTakeAnyDamage 델리게이트에 OnDamaged를 구독한다. 무기는 ApplyDamage/ApplyPointDamage만 호출하고, AActor::TakeDamage가 OnTakeAnyDamage를 브로드캐스트하면 구독자인 HealthComponent가 받는다(보내는 쪽은 받는 쪽을 모름). 의심: OnDamaged에 UFUNCTION()이 없거나 시그니처 불일치(AddDynamic 실패), 소유 액터가 TakeDamage를 override하며 Super를 호출하지 않아 브로드캐스트가 안 됨(또는 GetOwner가 기대와 다름).
(2) 체력이 음수로 내려가거나, 음수 데미지가 들어오면 MaxHealth를 넘어 회복됨 → Health = FMath::Clamp(Health - Damage, 0.f, MaxHealth); 또 체력 0 도달 시 사망 처리(State.Dead 추가, OnDeath 1회)가 없음 → if (Health <= 0.f) { 태그 추가; OnDeath.Broadcast(); }
(3) if (!WeaponTable) return 0.f; if (const FWeaponRow* Row = WeaponTable->FindRow<FWeaponRow>(WeaponId, TEXT("Lookup"))) { return Row->Damage; } return 0.f; FindRow: 행 이름(키)으로 한 행 조회. GetAllRows: 모든 행을 배열로 받아 순회(목록 UI, 합계, 조건 검색). 순회 시에도 R 널 검사.
(4) 상태가 'State.Dead', 'State.Stunned' 같은 계층형 이름표로 한 컨테이너에 모여 추가·제거·검사(HasTag)가 일관되고, 새 상태를 클래스에 bool을 추가하지 않고 태그 정의만으로 늘릴 수 있다. 여러 시스템(AI, UI, 입력 차단)이 같은 태그로 상태를 확인하며, 나중에 GAS의 태그 기반 조건으로 그대로 이어진다.

**채점표 (10점)**

- [3] (1) 구독 구조 설명 + 호출 안 될 때 의심 2가지(UFUNCTION/시그니처, Super 누락)
- [2] (2) Clamp 범위 + 사망 처리 누락 등 2가지 수정
- [3] (3) FindRow로 수정 + 널 검사 + 두 함수 용도
- [2] (4) GameplayTag 상태 표시의 장점

> 작성 메모: FGameplayTagContainer의 AddTag/HasTag와 FGameplayTag::RequestGameplayTag는 W08 'GameplayTags 첫 도입' 범위에서 문제에 직접 제시. FindRow의 bWarnIfRowMissing 기본 동작(경고 로그)은 채점 대상 아님.

### P1-064 (0.29점) — 목표: W08-11, W08-14, W08-15, W08-17

**모범 답안**

(1) ① DataTable: 같은 구조의 행이 100개, 스프레드시트·CSV 연동이 핵심. ② DataAsset(UPrimaryDataAsset): 객체 단위, 다른 에셋 참조, 상속·에디터 편집에 유리. ③ DataAsset 권장(커리큘럼 UCharacterStatData처럼 캐릭터 1개 = 에셋 1개, 에디터에서 개별 편집) — 같은 구조의 캐릭터가 많아 표로 관리할 거라면 DataTable도 근거가 있으면 인정.
(2) ScriptableObject ↔ UDataAsset/UPrimaryDataAsset(에디터에서 만드는 데이터 에셋). CSV 직접 파싱 ↔ DataTable: FTableRowBase 상속 행 구조체를 정의하면 에디터 임포트가 내장돼 파싱 코드가 필요 없고, 수정한 CSV를 재임포트하며, 코드에서는 FindRow/GetAllRows로 타입 있는 행을 조회한다.
(3) UPrimaryDataAsset은 GetPrimaryAssetId로 '타입 + 이름'(예: SkillData:DA_Fireball) 형태의 Primary Asset ID를 돌려준다. Asset Manager는 등록된 Primary Asset 타입을 스캔해 ID 목록을 알고, ID로 에셋을 찾고 로드·언로드를 관리한다. 그래서 'SkillData 타입의 ID 전부'를 조회해 목록을 만들 수 있고, 새 스킬은 에셋만 추가하면 코드 수정 없이 목록에 나타난다(Asset Manager에 타입 등록 필요).

**채점표 (10점)**

- [3] (1) 세 데이터 선택과 근거(③은 근거가 타당하면 인정)
- [3] (2) ScriptableObject·CSV 파싱 대응 + DataTable 임포트 내장
- [4] (3) Primary Asset ID·Asset Manager·GetPrimaryAssetId로 목록 조회 설명

> 작성 메모: UPrimaryDataAsset::GetPrimaryAssetId의 기본 구현이 타입을 '가장 가까운 네이티브 클래스 이름'으로 정하는 세부는 확인 필요 — 정답 요건은 '타입+이름 쌍의 ID를 돌려준다'까지만.

### P1-065 (0.19점) — 목표: W08-18, W08-24, W08-29

**모범 답안**

(1) ① DataTable: 같은 구조의 행 40개, 스프레드시트 협업. ② DataAsset(보스용 UPrimaryDataAsset): 몽타주·메시 등 에셋 참조, 객체 단위. ③ 웨이브 구성 데이터(DataTable 행 또는 게임 규칙 DataAsset) — 기획 조정 대상이라 데이터화가 타당. ④ 사망 연출 시간 — 캐릭터 스탯 DataAsset 또는 상수(근거 있으면 인정). ⑤ 로그 카테고리는 코드 영역이라 데이터화하지 않음. ⑥ UI 레이아웃 값은 위젯 BP(디자이너)에서 조정하는 편이 자연스러움(근거 있으면 인정).
(2) DataTable 행을 읽어 적에게 적용하는 지점(스폰 직후 스탯 적용 함수)에서 검증: 속도·체력이 0 이하이면 경고 로그(행 이름 포함) + 기본값 적용. 행을 못 찾으면(FindRow nullptr) 경고 후 기본값.
(3) docs/adr/ADR-0002-dataasset-vs-datatable.md. 선택지 표: DataAsset(장점: 에셋 참조·상속·개별 편집 / 단점: 수백 개 일괄 편집 불편) vs DataTable(장점: CSV·스프레드시트 일괄 편집 / 단점: 행마다 다른 구조·상속 어려움). 결과: 좋아진 점(코드 수정 없이 적·무기 추가), 감수한 비용(데이터 검증 코드·임포트 절차), 다시 볼 조건(데이터 종류가 늘어 Asset Manager 조회가 필요해질 때 등).
(4) 기획자가 빌드 없이 밸런스 수정, 프로그래머는 로직에 집중, 변경 이력이 데이터 단위로 분리돼 리뷰·되돌리기 쉬움, 테스트용 데이터 세트 교체가 쉬움.

**채점표 (10점)**

- [3] (1) 값 분류와 배치 타당성
- [2] (2) 적용 지점 검증 + 로그·기본값
- [3] (3) ADR 위치 + 선택지 표·결과 3요소
- [2] (4) 협업 이점 3가지 이상

### P1-066 (0.29점) — 목표: W09-06, W09-07, W09-15, W09-18

**모범 답안**

(1) NativeConstruct는 위젯이 화면에 붙어 구성될 때마다(AddToViewport할 때마다) 호출되고, NativeDestruct는 화면에서 제거될 때 호출된다. 구독만 하고 해제를 안 하니 다시 띄울 때마다 같은 함수가 또 구독돼 5개가 쌓였다. 수정: NativeDestruct에서 OnWaveChanged.RemoveDynamic(this, &UArenaPauseWidget::HandleWaveChanged)(또는 RemoveAll(this)) + Super::NativeDestruct(). 구독(Construct)과 해제(Destruct)를 짝으로.
(2) Tick·Property Binding은 값이 안 바뀌어도 매 프레임 평가되어, 위젯이 많아지면 게임 스레드 비용이 커진다. 웨이브는 수십 초에 한 번 바뀌므로 델리게이트로 바뀔 때만 갱신하는 게 맞다(버그는 구독 해제로 고치는 것이 정답).
(3) C++ 변수와 같은 이름·타입의 위젯을 BP 디자이너에서 찾아 자동 연결한다. 필수 바인딩이므로 디자이너에 WaveText가 없거나 타입이 다르면 위젯 BP 컴파일 에러.
(4) UMG. C++ 부모가 데이터 구독·갱신 로직을 담당하고, BP 자식(디자이너)이 배치·스타일을 담당해 프로그래머와 디자이너가 분리 작업한다(유니티는 Canvas 위 UGUI 컴포넌트에 스크립트를 붙이는 방식).

**채점표 (10점)**

- [3.5] (1) Construct가 재부착마다 호출 → 중복 구독 원인 + Destruct에서 해제
- [2.5] (2) 매 프레임 평가 비용 vs 이벤트 갱신
- [3] (3) BindWidget 자동 연결 + 없을 때 컴파일 에러
- [1] (4) UMG + C++ 부모/BP 레이아웃 의미

> 작성 메모: BindWidgetOptional 등은 커리큘럼 밖이므로 요구하지 않음. NativeOnInitialized(1회 초기화)도 요구하지 않는다.

### P1-067 (0.29점) — 목표: W09-09, W09-10, W09-16, W09-20

**모범 답안**

(1) 하드 참조는 참조한 쪽(던전 BP → 스포너)이 로드될 때 대상(보스 BP 클래스)도 함께 로드되고, 보스 BP가 참조하는 메시·머티리얼·텍스처까지 참조 체인을 따라 연쇄로 로드된다. 소프트 레퍼런스는 경로만 저장해 던전이 로드돼도 보스는 로드되지 않고, 필요할 때만 로드할 수 있다.
(2) UPROPERTY(EditAnywhere) TSoftClassPtr<AArenaEnemy> EnemyClass; UPROPERTY(EditAnywhere) TSoftObjectPtr<USoundBase> SpawnSound; — 몬스터는 스폰할 '클래스'라 TSoftClassPtr, 사운드는 에셋 '객체'라 TSoftObjectPtr.
(3) TSoftObjectPtr은 에셋 객체가 아니라 에셋 '경로'(FSoftObjectPath)를 저장한다. 로드하지 않았으면 Get()은 nullptr이고 엔진이 미리 들고 있지 않다. 직접 동기/비동기 로드해야 하고, 로드된 객체를 붙잡는 다른 참조가 없으면 다시 GC될 수 있다.
(4) UClass* BossClass = EnemyClass.LoadSynchronous(); (TSubclassOf로 받아 SpawnActor) — 유니티 Resources.Load에 대응. 로드가 끝날 때까지 게임 스레드가 멈춰 히치가 생긴다 → 미리 비동기 로드해 두는 편이 낫다.

**채점표 (10점)**

- [3] (1) 함께·연쇄 로드(참조 체인) + 소프트와 비교
- [3] (2) TSoftClassPtr/TSoftObjectPtr 선언과 구분 이유
- [2] (3) 경로 저장 근거로 오해 정정(Get nullptr, 직접 로드)
- [2] (4) LoadSynchronous + Resources.Load 대응 + 히치

> 작성 메모: TSoftObjectPtr 내부가 경로 + 약한 포인터 캐시(TPersistentObjectPtr)라는 세부는 가점 요소이며 필수 아님.

### P1-068 (0.29점) — 목표: W09-14, W09-17, W09-19, W09-38

**모범 답안**

(1) 요청: 경로 배열과 콜백으로 RequestAsyncLoad를 호출한다. ② 중복 요청이 쌓여 같은 로드·콜백이 여러 번 돈다(UI 중복 생성). 로딩 중: 비동기로 진행된다. ① 그 사이 위젯이 파괴될 수 있다. 완료 콜백: ① 매니저가 요청을 붙잡고 있어 콜백은 그대로 불리므로, 파괴된 위젯의 this에 접근하면 크래시가 난다. 표시: 텍스처를 이미지에 설정한다. ③ 핸들을 놓고 다른 참조가 없으면 GC될 수 있다. 위젯 이미지 브러시가 참조하는 아이콘은 유지되지만, 아직 표시하지 않은 아이콘은 사라질 수 있다.
(2) FStreamableHandle은 비동기 로드 요청 하나를 나타낸다. 진행·완료 여부 확인, 취소(CancelHandle)·해제(ReleaseHandle)에 쓰고, 유지되는 동안 로드된 에셋을 메모리에 붙잡아 둔다. 로딩 중에는 매니저가 요청을 붙잡고 있으므로 문제는 로드 완료 후에 생긴다. 핸들을 버리고 다른 참조도 없으면 로드된 텍스처가 GC된다. 그러면 나중에 Get()이 nullptr이 되거나, 아이콘을 다시 로드하느라 깜빡인다.
(3) ① TWeakObjectPtr<UArenaShopWidget> WeakThis(this)를 캡처하고, 콜백에서 IsValid를 확인한 뒤 사용한다. ② 객체 수명에 묶인 델리게이트로 콜백을 만든다. 예: FStreamableDelegate::CreateWeakLambda(this, [...]{...}) 또는 FStreamableDelegate::CreateUObject(this, &UArenaShopWidget::OnIconsLoaded). 객체가 사라지면 호출되지 않는다(W05의 AddUObject·CreateWeakLambda와 같은 원리). ③ NativeDestruct에서 보관한 핸들을 CancelHandle해 요청을 취소한다. ①~③ 중 2가지를 쓰면 정답이다. ②는 생성 함수 이름이 정확하지 않아도 '객체 수명에 묶인 바인딩'이라는 뜻이 맞으면 인정한다.
(4) Addressables.LoadAssetAsync(주소 기반 비동기 로드 + 핸들 Release) ↔ 소프트 레퍼런스 + StreamableManager.RequestAsyncLoad + FStreamableHandle. RequestAsyncLoad: StreamableManager.h의 FStreamableManager, 반환 타입 TSharedPtr<FStreamableHandle>(경로 1개/배열, 델리게이트/람다 오버로드). GetStreamableManager: AssetManager.h의 UAssetManager 정적 함수, 반환 타입 FStreamableManager&.

**채점표 (10점)**

- [3] (1) 4단계 + ①②③ 결과
- [2] (2) 핸들 역할 + 완료 후 미유지 시 GC
- [3] (3) 안전한 콜백 방법 2가지(약한 포인터 캡처 / 객체에 묶인 델리게이트(CreateWeakLambda·CreateUObject) / NativeDestruct에서 요청 취소 중 2개, 각 1.5점)
- [2] (4) Addressables 대응 + 헤더·클래스·반환 타입

> 검토에서 고친 점: 모범 답안에 기술 오류가 있다. A형 (2)의 '콜백 전까지는 핸들이 유일한 보호다'는 틀렸다. 로딩 중에는 StreamableManager가 요청을 내부에서 붙잡고 있어 반환값을 버려도 로드와 콜백은 진행된다. GC 위험은 로드 완료 후에 생긴다. 또 A형 (3) 수정 코드가 원시 포인터 Data를 캡처한 뒤 IsValid(Data)를 부르는데, 이미 파괴됐다면 댕글링 포인터 접근이라 안전하지 않다. B형 (3)은 커리큘럼(W05)이 가르친 CreateWeakLambda를 정답에서 빼고 커리큘럼 밖의 CreateUObject만 들었다. 두 형의 정답과 채점표를 바로잡았다.

> 작성 메모: RequestAsyncLoad의 정확한 오버로드 목록(델리게이트 타입, bManageActiveHandle 등)은 UE 5.8에서 변경 여부 확인 필요 — 정답 요건은 '경로(들)+콜백을 받고 TSharedPtr<FStreamableHandle>을 반환'까지. FStreamableDelegate::CreateUObject는 W05 델리게이트 바인딩 응용으로 인정.

### P1-069 (0.29점) — 목표: W10-05, W10-07, W10-08, W10-20

**모범 답안**

(1) AIController(두뇌)가 Pawn(몸)을 Possess해야 그 Pawn을 조종한다. 빙의 전이거나 빙의하지 못하면 컨트롤러가 움직일 Pawn이 없어 MoveToActor가 명령할 대상이 없다(BeginPlay 시점에 아직 빙의 전일 수 있음 — 배치/스폰된 적이 자동 빙의되는 설정도 확인).
(2) 원인: NavMeshBoundsVolume이 없거나 NavMesh가 생성되지 않음(뷰포트 P로 확인), 목표(Player)가 null이거나 NavMesh 밖에 있음, 빙의된 Pawn이 없음. 확인: MoveToActor 반환값(요청 결과)을 보거나, OnMoveCompleted(FAIRequestID, const FPathFollowingResult& Result)를 override해 Result로 성공/실패를 로그로 남긴다.
(3) void AArenaAIController::OnPossess(APawn* InPawn) { Super::OnPossess(InPawn); RunBehaviorTree(BehaviorTreeAsset); } — OnPossess는 Pawn을 실제로 조종하기 시작하는 시점이라 Pawn이 보장된다. 목표 추적은 BT의 MoveTo 태스크 + Blackboard 타깃으로 한다.
(4) 같은 점: NavMesh 위에서 경로를 찾아 목표로 이동시키는 명령이다. 다른 점: 유니티는 오브젝트에 붙은 에이전트 컴포넌트가 직접 이동한다. 언리얼은 Pawn을 빙의한 AIController가 MoveTo를 호출하면 Pawn의 이동 컴포넌트가 따라 움직이고, 완료를 OnMoveCompleted로 받는다.

**채점표 (10점)**

- [3] (1) 두뇌/몸·Possess 관계 + 미빙의 시 무효 이유
- [3] (2) 실패 원인 2가지(NavMesh 포함) + 결과 확인 방법(OnMoveCompleted 또는 반환값)
- [2] (3) OnPossess override에서 Super 호출 + RunBehaviorTree + 빙의 시점이라는 이유
- [2] (4) SetDestination ↔ MoveTo 같은 점·다른 점

> 검토에서 고친 점: 두 형의 (3)이 'OnPossess를 override해 RunBehaviorTree 호출'을 정답 요건으로 두는데, OnPossess는 커리큘럼 어디에도 나오지 않는다(W10은 Possess 개념, RunBehaviorTree만 다룸). 엔진 소스를 볼 수 없는 필기에서는 근거 없는 요건이다. 두 형 문제에 OnPossess 시그니처를 주고, 이유(빙의 시점)를 같은 수준으로 묻게 맞췄다.

> 작성 메모: AutoPossessAI(PlacedInWorld/Spawned) 설정명은 커리큘럼에 명시되지 않아 요구하지 않음. MoveToActor 반환 타입(EPathFollowingRequestResult)은 이름까지 요구하지 않는다.

### P1-070 (0.29점) — 목표: W10-09, W10-10, W10-11, W10-12, W10-27

**모범 답안**

(1) 예:
Root
└ Selector (Composite: 우선순위 왼쪽부터)
   ├ Sequence: 전투 [Decorator: TargetActor Is Set] [Service: 거리 갱신]
   │  ├ MoveTo TargetActor (Task: 추적)
   │  └ Attack (Task: 공격)
   ├ Sequence: 경보 대응 [Decorator: bAlarm == true]
   │  └ MoveTo AlarmLocation (Task)
   └ Sequence: 순찰
      ├ NextPatrolPoint (Task: 다음 지점을 Blackboard에)
      ├ MoveTo PatrolPoint (Task)
      └ Wait 2s (Task)
(왼쪽이 높은 우선순위: 전투 > 경보 > 순찰)
(2) 실행되지 않는다. Sequence는 자식이 순서대로 모두 성공해야 하고 하나라도 실패하면 즉시 중단·실패한다. 순찰 Sequence가 실패하면 상위 Selector는 다른 자식을 시도(우선순위 위가 모두 실패면 Selector 전체 실패 후 다음 틱에 다시 평가).
(3) Service. 브랜치가 활성인 동안 정해진 주기(Interval)로 반복 실행되어 정보를 갱신하는 노드다. Task는 한 번 실행되어 성공/실패로 끝나는 '행동' 노드라, 주기적 갱신을 하려면 흐름에 끼워 넣어 반복시켜야 해 추적 행동과 섞인다.
(4) Decorator: 노드·브랜치에 붙어 '실행해도 되는가' 조건을 건다(bAlarm, TargetActor, 쿨다운). Task: 말단에서 실제 행동을 수행한다(MoveTo, Attack, Wait).

**채점표 (10점)**

- [4] (1) 우선순위를 반영한 Selector 구조 + 노드 종류·역할 표기
- [2] (2) Wait 미실행 + Sequence/Selector 규칙 설명
- [2] (3) Service + Task로 만들면 어색한 이유
- [2] (4) Decorator=조건, Task=행동

> 검토에서 고친 점: A형 모범 BT 그림에 동작 결함이 있다. 전투 브랜치가 Sequence [MoveTo → 공격 Sequence(쿨다운 데코레이터)]라서, 1.5초 쿨다운 동안 공격 데코레이터가 실패하면 전투 Sequence 전체가 실패하고 Selector가 순찰로 넘어간다. 적이 플레이어 앞에서 쿨다운마다 순찰을 떠나게 되어 요구사항과 어긋난다. 모범 답안을 전투 안쪽 Selector 구조로 고치고, 채점표 (2)에 이 결함을 판정하는 기준을 넣었다.

> 작성 메모: 랜덤 순찰 지점을 구하는 노드는 기본 제공이 아니므로 커스텀 Task(또는 EQS)로 그린 답 모두 인정.

### P1-071 (0.39점) — 목표: W10-13, W10-14, W10-15, W10-16, W10-17

**모범 답안**

(1) (A) InProgress — 조준·발사가 끝날 때까지 시간이 걸리는 지연 태스크이므로 '진행 중'으로 BT를 대기시킨다. (B) FinishLatentTask — 발사가 끝나면 최종 결과를 BT에 통보. (C) 중단 정리: Enemy를 다시 얻어 Ranged->CancelAim(); Ranged->OnFireFinished.RemoveAll(this); — 중단돼도 조준이 계속되거나 나중에 HandleFired가 끝난 태스크에 결과를 보내는 것을 막는다. (D) Interval = 1.0f; — 서비스 실행 주기.
(2) ExecuteTask가 InProgress 반환 → 이 태스크가 실행 중 상태로 남고 BT는 다음 노드로 넘어가지 않음(그동안 서비스·데코레이터는 계속 동작) → 2초 뒤 발사 완료 시 OnFireFinished → HandleFired → FinishLatentTask(Succeeded) → 태스크 성공, 부모 composite 규칙에 따라 다음 노드 진행. (중간에 중단되면 AbortTask)
(3) Blackboard는 BT 노드들이 공유하는 데이터 저장소. 서비스가 1초마다 CoverLocation(Vector)을 쓰고, 이동 태스크가 같은 키를 GetValueAsVector로 읽어 목적지로 쓴다 — 노드끼리 직접 알지 않고 키를 통해 정보를 주고받는다(데코레이터도 키 값으로 조건 판단).
(4) Succeeded: 즉시 성공 완료. Failed: 즉시 실패 완료(Sequence면 중단, Selector면 다음 자식). InProgress: 아직 끝나지 않음, 나중에 FinishLatentTask로 결과 통보.

**채점표 (10점)**

- [4] (1) 빈칸 A~D (각 1점) — C는 취소+바인딩 해제 모두 있어야 1점
- [2] (2) InProgress 대기 → FinishLatentTask 흐름
- [2] (3) Blackboard 공유 저장소 역할(쓰기·읽기 예)
- [2] (4) 세 결과 값 의미

> 작성 메모: bCreateNodeInstance는 커리큘럼에 명시되지 않아 코드 주석으로 의미를 제공하고 채점하지 않는다(기본은 노드가 공유되어 멤버에 AI별 상태를 두면 안 된다는 점 — 가점 요소). SetValueAsFloat는 커리큘럼의 SetValueAsObject/GetValueAsVector와 같은 계열로 문제에 직접 제시.

### P1-072 (0.29점) — 목표: W10-18, W10-19, W10-21, W10-38

**모범 답안**

(1) ①의 Observer Aborts가 Self이므로 조건(TargetActor Is Set)이 거짓이 되는 즉시 ① 브랜치(공격 서브트리)가 중단되고 Selector가 다음 자식(② 탐색)을 평가한다. 반대 상황은 Self만으로는 낮은 우선순위(②)를 중단하지 않으므로 탐색이 끝나야 공격으로 돌아간다. Both(또는 Lower Priority 포함)로 바꾸면 조건이 참이 되는 순간 실행 중인 ②를 중단하고 ①로 전환. Self: 조건이 거짓이 되면 자기 서브트리 중단. Lower Priority: 조건이 참이 되면 자기보다 낮은 우선순위(오른쪽) 실행 브랜치 중단. Both: 둘 다.
(2) 기본 노드: 쿨다운(Cooldown 데코레이터), 탐색 지점 이동(MoveTo), 두리번 대기(Wait — 애니메이션이 필요하면 커스텀), 거리 유지 이동(MoveTo + 목표 위치 계산은 커스텀 또는 EQS). C++ 커스텀: 조준·발사 Task(풀 Subsystem·컴포넌트 연동, 2초 지연 → InProgress/FinishLatentTask, 중단 시 AbortTask 정리 필요), 거리·시야 갱신 Service(TickNode + Interval 0.5). 기준: 범용 이동·대기·조건은 기본 제공, 프로젝트 고유 시스템 연동·지연·정리가 필요한 것은 C++.
(3) BT: 조건 평가·우선순위 기반 의사결정 트리. StateTree: 상태 머신과 셀렉터를 합친 구조로 상태·전환을 명시, UE5에서 범용 로직용으로 확장 중. 기존 프로젝트에 BT가 많고 실무에선 둘 다 만날 수 있으므로 BT를 몰라도 된다는 말은 틀렸다.
(4) 유니티는 BT가 기본 기능이 아니어서 에셋 스토어 등 외부 도구에 의존한다. 언리얼은 BT·Blackboard·AIController가 엔진에 내장돼 별도 도입 없이 쓰고, C++ Task·Service 확장 지점이 표준화돼 있으며, BT 디버거로 실행 중인 노드·Blackboard 값을 실시간으로 볼 수 있다.

**채점표 (10점)**

- [4] (1) Self 동작 + 반대 상황 판단·수정(Both/Lower Priority) + 세 값 의미
- [3] (2) 기본/C++ 노드 구분과 이유
- [1.5] (3) BT vs StateTree 차이와 반박
- [1.5] (4) 엔진 내장 + 디버거 이점

> 작성 메모: Observer Aborts의 정확한 조건 변화 방향(Lower Priority는 조건이 '이 브랜치를 실행해야 하는 쪽'으로 바뀔 때)은 UE 공식 문서 기준. 커리큘럼은 '조건이 바뀌면 실행 중인 브랜치를 중단'까지 설명하므로, 세 값의 대상(자기 서브트리 / 낮은 우선순위 / 둘 다)만 정확하면 만점 처리.

### P1-073 (0.29점) — 목표: W11-05, W11-06, W11-12, W11-19

**모범 답안**

(1) 유니티: 주기적으로 Physics.OverlapSphere → 시야각 판정 → Raycast로 가림 확인 → 이전 목록과 비교해 들어옴/나감 판단을 직접 구현한다. Perception은 시야 반경·상실 반경·시야각·가림 트레이스, 감지/상실 이벤트, 팀 필터를 내장하고, 청각·피격 감지도 같은 틀로 제공한다.
(2) PerceptionComponent->OnTargetPerceptionUpdated.AddDynamic(this, &AArenaArcherController::OnTargetPerceived)로 바인딩하고, 함수는 UFUNCTION이어야 한다. 원인: 이 함수는 감지와 상실 때 모두 불리는데, 구분 없이 항상 타깃을 넣으므로 상실 때도 타깃이 남는다. 수정: Stimulus에 담긴 감지 성공 여부(Stimulus.WasSuccessfullySensed())가 true면 SetValueAsObject, false면 타깃 키를 비운다(ClearValue 또는 nullptr 설정). WasSuccessfullySensed라는 이름은 커리큘럼에 없으므로, 'Stimulus의 감지 성공 여부로 분기한다'고 쓰면 이름이 틀려도 인정한다.
(3) GetGenericTeamId로 얻은 팀 ID가 서로 다르면 적대(Hostile), 같으면 우호(Friendly)가 기본 규칙이다. 0과 1은 달라 적대이므로 '적만 감지'에 포함된다. 플레이어가 인터페이스를 구현하지 않으면 팀이 없어 '중립'으로 판정되고, '적만 감지' 설정에서는 걸러져 감지되지 않는다(중립 감지를 켜거나 인터페이스를 구현해야 함).
(4) Gameplay Debugger로 Perception 표시 → 시야 반경·각도 → 소속 감지 설정 → 자극 소스 등록 → 시야 트레이스를 막는 콜리전. 문제 ②는 5단계에서 잡힌다. 유리창 메시의 콜리전이 시야 트레이스 채널(보통 Visibility)을 Block하는지 확인하고, 보이게 할 의도라면 그 채널을 Ignore로 바꾼다.

**채점표 (10점)**

- [2] (1) 유니티 직접 구현 방식과 Perception 내장 기능 2가지 이상
- [3] (2) AddDynamic 바인딩·UFUNCTION, 상실 때도 호출된다는 원인, Stimulus의 감지 성공 여부로 분기(WasSuccessfullySensed라는 이름은 정확하지 않아도 인정)
- [3] (3) 팀 ID가 다르면 적대라 감지됨, 인터페이스가 없으면 중립이라 걸러짐
- [2] (4) 점검 5단계 순서와 문제 ②가 잡히는 단계(콜리전, 트레이스 채널 Block 확인)

> 검토에서 고친 점: 두 형 모두 감지와 상실을 FAIStimulus::WasSuccessfullySensed()로 구분하는 것을 정답 요건(3점 항목)으로 둔다. 그런데 커리큘럼에는 FAIStimulus도 WasSuccessfullySensed도 나오지 않는다. 또 B형은 핸들러 시그니처를 주는데 A형은 주지 않아 난이도가 다르다. A형에 시그니처를 주고, 두 형 채점표를 'Stimulus의 감지 성공 여부로 구분'이면 함수 이름이 틀려도 인정하도록 고쳤다.

> 작성 메모: OnTargetPerceptionUpdated 시그니처(AActor*, FAIStimulus)와 기본 태도 규칙(같은 팀 우호/다른 팀 적대/인터페이스 없음 중립)은 UE 5.8 GenericTeamAgentInterface.h 기준. 감지 대상 쪽 인터페이스를 Character와 PlayerController 중 어디에 구현해야 인식되는지는 정답 요건에서 뺐다(확인 필요). 시야 트레이스 채널이 Visibility라는 것도 프로젝트 설정에 따라 다를 수 있어 '보통'으로만 적었다.

### P1-074 (0.19점) — 목표: W11-11, W11-18, W11-20

**모범 답안**

(가) Visual Logger: 드물게 생기는 문제를 녹화해 두고 멈춘 시점 직전으로 되감아 판단 기록을 본다. (나) DrawDebug: DrawDebugLine/DrawDebugDirectionalArrow로 발사 방향을 월드에 그린다. (다) Gameplay Debugger: 지금 이 순간의 Perception 상태(감지 범위·감지 대상)를 오버레이로 본다. (라) 중단점(조건부 포함): 그 줄에서 멈춰 배열 값과 호출 스택을 본다.
(2) Gameplay Debugger는 현재 상태만 오버레이하고 지나간 상태는 남지 않는다. Visual Logger는 시간축으로 녹화해 과거 프레임의 로그·위치·도형을 되감아 비교할 수 있어, 재현이 어렵고 순간적으로 지나가는 AI 판단 버그의 근거(TS 문서 화면)를 남길 수 있다.
(3) 예: UE_VLOG(this, LogTemp, Log, TEXT("Dist to player: %.1f"), Dist);

**채점표 (10점)**

- [4] (1) 4개 상황의 도구 선택(가 VL, 나 DrawDebug, 다 GD, 라 중단점)과 이유, 상황당 1점
- [3] (2) VL은 시간축 녹화로 과거 프레임을 되감아 분석, GD는 현재만
- [3] (3) UE_VLOG 인자 순서와 float 형식 출력

> 작성 메모: UE_VLOG(LogOwner, CategoryName, Verbosity, Format, ...) 형식은 VisualLogger.h 기준. include(VisualLogger/VisualLogger.h)는 요구하지 않았다. 형식 지정자(%f/%.1f) 차이는 감점하지 않는다.

### P1-075 (0.29점) — 목표: W11-07, W11-14, W12-18

**모범 답안**

(1) (가) InitialSpeed (나) bRotationFollowsVelocity (다) true (라) false (마) Orb->Movement->Velocity = Muzzle.GetRotation().GetForwardVector() * Orb->Movement->InitialSpeed; (방향은 Orb->GetActorForwardVector()도 정답) (바) Dist < Stats.SafeDistance.
(2) SpawnActor로 새로 만들면 컴포넌트 초기화 때 InitialSpeed가 속도로 적용된다. Pop으로 꺼낸 것은 이미 만들어진 객체라 BeginPlay·초기화가 다시 불리지 않고, ReturnOrb에서 속도를 0으로 멈춘 상태가 그대로 남는다. 그래서 재사용 경로에서 속도를 직접 다시 넣는(리셋·활성화) 코드가 필요하다.
(3) 짤 필요 없다. ProjectileMovementComponent에 바운스와 호밍 옵션이 내장돼 있어 설정으로 해결한다.
(4) SafeDistance보다 가까우면 물러나 거리를 벌림, CastRange보다 멀면 사거리 조금 안쪽까지 접근, 그 사이면 멈춰서 시전. 즉 거리를 유지하며 발사한다.

**채점표 (10점)**

- [3.5] (1) 빈칸 6개(가 InitialSpeed, 나 bRotationFollowsVelocity, 다 true, 라 false, 마 Velocity=전방*InitialSpeed, 바 Dist<SafeDistance), (마)는 1점, 나머지 0.5점
- [3] (2) 새 스폰은 초기화 때 InitialSpeed 적용, 재사용은 BeginPlay·초기화가 다시 불리지 않아 정지 상태 유지
- [1.5] (3) 바운스·호밍이 PMC에 내장
- [2] (4) 거리 3구간(후퇴/접근/정지 후 시전) 설명

> 검토에서 고친 점: A형 (2)의 모범 답안 '처음 스폰된 화살은 (마) 없이도 정상 발사'가 주어진 코드에서는 틀리다. SpawnActor<AArenaArrow>(ArrowClass)는 원점·기본 회전으로 스폰되고, PMC는 컴포넌트 초기화 때 그 순간의 앞 방향(월드 +X)으로 InitialSpeed 속도를 정한다. 그 뒤 SetActorLocationAndRotation으로 돌려도 속도 방향은 Dir로 바뀌지 않는다. 또 이 화살은 중력 배율을 0으로 두지 않아, 재사용 화살은 '멈춰 있음'이 아니라 아래로 떨어질 수 있다. 의도한 정답이 성립하도록 스폰 코드에 위치·회전을 넘기고, 재사용 화살의 정답 범위를 넓혔다.

> 작성 메모: PMC는 바운스 없이 충돌로 멈추면 UpdatedComponent를 해제할 수 있어 재사용 때 SetUpdatedComponent 재설정이 필요할 수 있다(확인 필요). 정답 요건에서는 뺐고, 답안에 쓰면 가산 없이 인정만 한다. InitialSpeed가 초기화 시점에 Velocity로 적용된다는 설명은 ProjectileMovementComponent.h 주석 기준. 바운스·호밍 속성 이름은 요구하지 않는다(커리큘럼이 '내장돼 있다는 것만 확인'이라고 한정).

### P1-076 (0.19점) — 목표: W11-21, W12-24

**모범 답안**

(1) PMC는 속도·중력·바운스·호밍이 내장돼 있고, 충돌을 고려해 이동하며(직접 위치를 더하면 빠른 탄이 벽을 뚫거나 충돌 처리를 따로 짜야 함), 네트워크 보간도 제공한다. 직접 구현할 코드와 버그가 줄어든다. 무겁다는 주장도 측정 없이 판단하면 안 된다.
(2) 원인: 풀 재사용은 같은 액터를 다시 쓰는 것이라 BeginPlay가 다시 불리지 않는다. 첫 사용 뒤 바뀐 값이 그대로 남는다. 해결: 상태를 되돌리는 Reset/Activate 함수를 만들어 풀에서 꺼낼 때 명시적으로 호출한다(이펙트 켜기, 관통 횟수 초기화, 위치·속도 설정).
(3) 원인: 반환할 때 숨기기만 하고 충돌을 끄지 않아 보이지 않는 투사체가 여전히 맞는다. 꺼야 할 것: 충돌(안 끄면 버그 1), Tick·이동(안 끄면 쉬는 탄이 CPU를 쓰고 계속 움직임), 가시성(안 끄면 화면에 남음).

**채점표 (10점)**

- [3] (1) PMC 근거 3가지 이상
- [4] (2) BeginPlay 재호출 없음 + 명시적 Reset/Activate 설계
- [3] (3) 버그 1 원인(충돌 미해제)과 충돌·Tick·가시성 3가지의 문제

> 작성 메모: 커리큘럼 W11·W12 자가 점검 답을 근거로 했다. '충돌 고려 이동'은 PMC가 이동 경로를 스윕하며 충돌을 처리한다는 뜻으로 채점한다.

### P1-077 (0.19점) — 목표: W12-07, W12-19, W12-20

**모범 답안**

(1) 마법탄에만 풀 적용. 스폰 방식은 초당 40발 × 0.35ms ≈ 초당 14ms를 생성에 쓰고 웨이브 후반 프레임 시간이 목표 16.6ms를 넘는 20ms 안팎이었는데, 풀 방식에서 1회 0.02ms, 프레임 시간 15ms 안팎으로 목표 안에 들어왔다. 보스 연출은 1회 비용이 커도 스테이지당 1회, 컷신 중이라 영향이 적다 → 제외. 데칼은 빈도·비용이 작고 튐이 없다 → 제외.
(2) 풀은 측정으로 병목이 확인된 곳에만 적용한다. 1회 비용만 보면 보스 연출이 가장 크지만 실제 체감 비용은 '빈도 × 비용'과 발생 시점에 달려 있다. 측정 없이 고르면 병목이 아닌 곳에 리셋·상태 관리 복잡도만 더하고 실제 병목(투사체)은 그대로 남는다.
(3) 예시) 결정과 이유: 마법탄 투사체에만 UProjectilePoolSubsystem 풀을 적용한다. 5회 측정 중간값에서 스폰 방식은 1회 0.35ms·초당 40발로 웨이브 후반 프레임 시간이 20ms까지 올랐고, 풀 적용 뒤 15ms로 60fps 목표를 지켰다. 보스 연출·데칼은 빈도나 비용이 작아 제외. 결과: 좋아진 점-웨이브 후반 프레임 안정. 비용-리셋 함수·상태 관리 코드와 재사용 버그 위험. 다시 볼 조건-데칼 빈도가 크게 늘거나 새 측정에서 다른 생성 비용이 병목으로 보이면 재검토.

**채점표 (10점)**

- [4] (1) 마법탄만 풀 적용, 나머지 제외를 수치(빈도×비용, 프레임 시간, 발생 시점)로 근거
- [2] (2) 측정 후 결정 원칙과 1회 비용만 보는 판단의 오류
- [4] (3) ADR 결정과 이유에 측정 수치·조건 포함, 결과 3요소

> 작성 메모: 표의 수치는 시험용 가상 값이다. 측정 조건(반복 횟수, 중간값)을 ADR에 적으면 W18 원칙과도 이어지므로 (3)에서 긍정적으로 본다.

### P1-078 (0.29점) — 목표: W12-01, W12-06, W12-13, W12-15, W12-17

**모범 답안**

(1) 풀 → 직접 구현한 WorldSubsystem 풀: UnityEngine.Pool에 대응하지만 언리얼엔 기본 풀이 없어 직접 만든다. 월드와 함께 생기고 사라지므로 이전 레벨의 투사체를 들고 남을 일이 없다. 기록·설정 관리자 → GameInstance Subsystem: 싱글턴 GameManager + DontDestroyOnLoad에 대응하며, 게임 실행~종료 동안 살아 있고 레벨 전환에도 유지된다.
(2) static 싱글턴은 레벨이 바뀌어도 스스로 사라지지 않아 이미 파괴된 이전 월드의 객체를 가리키게 된다(수명을 직접 관리해야 함). Subsystem은 엔진이 정해진 수명에 맞춰 자동으로 만들고 정리하므로 이런 수명 불일치가 없다.
(3) Engine: 엔진 전체. Editor: 에디터 동안. GameInstance: 게임 실행~종료, 레벨 전환에도 유지. World: 월드 단위. LocalPlayer: 로컬 플레이어 단위.
(4) ShouldCreateSubsystem: 만들기 전에 불려 이 월드에 만들지 결정한다 → 게임 레벨에서만 true를 돌려주게 한다. Initialize: 생성 직후 초기화(풀 배열 준비, 미리 몇 개 생성). Deinitialize: 월드 정리 때 마무리(풀 비우기·참조 정리).

**채점표 (10점)**

- [3] (1) WorldSubsystem 풀·GameInstance Subsystem 대응, 유니티 대응과 수명 근거
- [2] (2) 크래시와 연결한 싱글턴 대비 Subsystem 이유
- [2.5] (3) 5종 수명
- [2.5] (4) ShouldCreateSubsystem으로 생성 여부 결정, Initialize·Deinitialize 시점과 예시

> 작성 메모: ShouldCreateSubsystem의 인자(UObject* Outer)나 월드 타입 판별 방법(DoesSupportWorldType 등)은 정답 요건에서 뺐다(확인 필요). 'Visual Studio Ctrl+T로 WorldSubsystem.h 찾기'는 메뉴 암기라 묻지 않고, 그 파일에서 읽는 함수의 역할로 평가한다.

### P1-079 (0.29점) — 목표: W12-03, W12-16, W12-23

**모범 답안**

(1) GameMode는 서버에만 존재한다. 클라이언트에는 GameMode가 없어 GetAuthGameMode가 null이므로 값을 읽지 못한다. 모든 플레이어가 봐야 하는 값은 모든 머신에 있고 복제되는 GameState에 두고 HUD는 GameState에서 읽어야 한다.
(2) GameState: (가) 남은 적 수, (나) 남은 초, (마) 현재 웨이브. GameMode: (다) 스폰 위치 선택, (라) 체력 배율 계산, (바) 단계 전환 함수(GameMode가 전환하고 그 결과 값은 GameState가 보관).
(3) 규칙·서버만 알아야 하는 것(스폰 로직, 난이도 계산)은 GameMode, 모든 플레이어가 봐야 하는 상태(현재 웨이브, 남은 적, 남은 시간)는 GameState.
(4) PlayerArray: 참여한 플레이어들의 PlayerState 목록. GameState에 있어 모든 머신에서 볼 수 있으므로 각 PlayerState의 이름을 꺼내 표시한다.

**채점표 (10점)**

- [3] (1) GameMode는 서버에만 있어 클라에서 null, GameState로 옮겨야 함
- [3] (2) 6개 분류, 항목당 0.5점
- [2] (3) 규칙/공유 상태 구분 기준
- [2] (4) PlayerArray와 그 의미(PlayerState 목록)

> 작성 메모: GetAuthGameMode가 클라이언트에서 null을 돌려준다는 점은 UE 5.8 기준 사실이다. GameState 값이 실제로 클라에 보이려면 W14의 복제 설정(Replicated)이 필요하지만 이 문항에서는 위치 판단만 채점한다.

### P1-080 (0.19점) — 목표: W12-08, W12-10, W12-14

**모범 답안**

(1) USaveGame은 UPROPERTY 멤버만 직렬화되어 저장된다. bInvertY에 UPROPERTY가 없어 저장되지 않아 기본값 false로 돌아온다. 수정: UPROPERTY() bool bInvertY = false;
(2) SaveGameToSlot은 직렬화·디스크 쓰기를 게임 스레드에서 동기로 하므로 호출할 때마다 히치가 생기고, 슬라이더를 끌 때 여러 번 불려 끊김이 이어진다. AsyncSaveGameToSlot으로 바꾸면 비동기로 처리되어 게임 스레드가 기다리지 않는다(저장 횟수를 줄이는 것, 예: 메뉴를 닫을 때 한 번 저장도 함께 하면 좋다).
(3) 둘 다 재실행 후에도 남는 기록·설정 저장용으로 대응된다. PlayerPrefs는 키-값으로 하나씩 저장한다. USaveGame은 UPROPERTY 멤버를 가진 저장용 클래스를 만들고, 객체를 슬롯 이름으로 통째로 저장·불러온다.

**채점표 (10점)**

- [4] (1) UPROPERTY만 직렬화된다는 원인과 수정
- [4] (2) 동기 저장의 히치 + AsyncSaveGameToSlot 비동기 처리
- [2] (3) PlayerPrefs 대응과 방식 차이

> 작성 메모: AsyncSaveGameToSlot도 직렬화 일부는 게임 스레드에서 할 수 있다는 세부 동작은 요구하지 않는다(확인 필요). 커리큘럼 W12 자가 점검 답 '직렬화와 디스크 쓰기를 게임 스레드에서 동기로 하면 히치'를 기준으로 채점한다.

### P1-081 (0.19점) — 목표: W13-22, W13-18, W13-19, W19-07

**모범 답안**

(1) 유니티 Build에 대응하는 작업은 Platforms → Windows → Package Project이고 쿠킹이 포함된다. 쿠킹은 맵이 참조하는 에셋(블루프린트 포함)을 불러 변환하므로, 에디터에서 열어 보지 않아 넘어갔던 블루프린트 컴파일 에러·깨진 참조가 이때 드러난다.
(2) BP_RangedEnemy의 'Call FireProjectile' 노드가 이름이 바뀌어 없어진 C++ 함수를 호출해 블루프린트 컴파일이 실패했고, 그래서 쿠킹이 실패했다. BP_RangedEnemy를 열어 노드를 FireAt 호출로 교체하고 컴파일·저장한 뒤 다시 패키징한다(C++ 이름 변경 뒤에는 그 함수를 쓰는 BP를 확인하는 습관).
(3) Saved/Logs와 Saved/Crashes.
(4) 문제가 난 함수: UProjectilePoolSubsystem::Acquire (31줄). 호출 경로: BehaviorTreeComponent → UBTTask_RangedAttack::ExecuteTask → AArenaRangedEnemy::FireAt(112줄) → Acquire. 작은 주소를 읽다 실패했으므로 null 포인터 멤버 접근 가능성이 크다. Acquire 31줄에서 쓰는 포인터(투사체 클래스가 지정되지 않음, SpawnActor 실패 결과, GetWorld 등)가 null인지, FireAt에서 얻은 Subsystem 포인터가 유효한지 확인하고 null 검사를 넣는다.

**채점표 (10점)**

- [2] (1) 패키징=쿠킹 포함, 쿠킹이 참조 에셋·BP를 실제 처리해 드러남
- [3] (2) 이름 바뀐 함수로 BP 컴파일 실패 → 쿠킹 실패, 노드 교체 조치
- [1.5] (3) Saved/Logs와 Saved/Crashes
- [3.5] (4) 원인 함수·BT 태스크에서 내려온 호출 경로, null 접근 추정과 확인할 것

> 작성 메모: 로그·콜스택 문구는 시험용으로 간략화한 것이며 실제 UE 5.8 출력 형식과 다를 수 있다(확인 필요). 패키징된 빌드의 Saved 폴더 실제 위치(패키지 폴더 안 또는 사용자 AppData)는 빌드 구성에 따라 달라 정답 요건에서 뺐다. 폴더 이름(Saved/Logs, Saved/Crashes)만 채점한다.

### P1-082 (0.39점) — 목표: W14-01, W14-02, W14-03, W15-13

**모범 답안**

(1) 상태 변경은 서버가 결정하고 클라이언트는 복제받은 결과를 보여 준다. 클라이언트는 요청만 한다.
(2) A 화면: 자기 PC 값만 줄어 잠깐 -50으로 보인다. B 화면·서버: 바뀌지 않는다. 서버 값이 다시 복제되면 A 화면도 서버 값으로 덮어써져 되돌아가 불일치가 생긴다. 클라가 적 체력을 바꿀 수 있으면 치트(즉사)에 취약하다.
(3) Dedicated Server: 화면·로컬 플레이어 없이 서버 역할만 한다. Listen Server는 호스트가 플레이하면서 서버 역할도 한다. 친구가 방장이 되면 Listen Server.
(4) 서버 PC: 전용 서버(Dedicated Server), A의 PC: 클라이언트(Client). NetMode는 현재 월드가 단독·리슨 서버·전용 서버·클라이언트 중 어떤 형태로 실행 중인지 나타낸다.
(5) A 입력 → Server RPC(공격 요청) → 서버가 판정하고 적 Health 변경 → 복제 → 각 클라 OnRep → 표시 갱신.

**채점표 (10점)**

- [2] (1) 서버 권위 모델 정의
- [3] (2) A만 잠깐 바뀜, 서버·B 미반영, 복제로 덮어씀, 치트 취약
- [2] (3) Dedicated 판단과 차이, 방장 구성은 Listen
- [2] (4) 서버 PC 전용 서버·A 클라이언트, NetMode의 의미
- [1] (5) Server RPC → 서버 변경 → 복제 흐름

> 작성 메모: NetMode 열거값 이름(NM_ListenServer 등)은 요구하지 않고 의미만 채점한다. '복제가 덮어쓴다'는 서버 값이 바뀌어 다시 복제될 때 일어나므로 '잠시 뒤(다음 복제 시)'로 표현했다.

### P1-083 (0.39점) — 목표: W14-04, W14-05, W14-06, W14-29

**모범 답안**

(1) (가) Authority (나) AutonomousProxy (다) SimulatedProxy (라) Authority (마) SimulatedProxy (바) SimulatedProxy.
(2) C1 화면의 C1 캐릭터는 AutonomousProxy로 C1이 직접 조종하는 사본이라 입력이 바로 반영된다. C2 화면의 C1 캐릭터는 SimulatedProxy로, 서버가 보낸 상태를 받아 보간해 보여 주므로 네트워크 지연만큼 늦고 부드럽게 따라온다.
(3) ① if (HasAuthority()) { 스태미나 차감 } — 상태 변경은 서버만(서버 권위). ② if (IsLocallyControlled()) { UI·카메라 } — 조종하는 사람의 화면에서만 실행. 전용 서버에는 로컬 플레이어가 없으므로 플레이어 캐릭터에 대해 IsLocallyControlled()가 false다.
(4) IsServer ↔ HasAuthority(), IsOwner ↔ IsLocallyControlled().

**채점표 (10점)**

- [3] (1) 역할 6칸, 칸당 0.5점
- [2] (2) AutonomousProxy(직접 조종 사본) vs SimulatedProxy(서버 상태 보간)로 지연 설명
- [3] (3) HasAuthority·IsLocallyControlled 분기와 이유, 전용 서버에서 false
- [2] (4) IsServer↔HasAuthority, IsOwner↔IsLocallyControlled

> 작성 메모: 서버 머신에서 원격 클라이언트 캐릭터의 GetRemoteRole()은 AutonomousProxy이지만 표는 GetLocalRole 기준이다. 클라에서 직접 스폰한 비복제 액터는 그 클라에서 HasAuthority가 true라는 예외는 다루지 않았다.

### P1-084 (0.39점) — 목표: W14-09, W14-11, W14-27, W14-30

**모범 답안**

(1) P1(서버): 'Disarm() on Server'만 찍힌다. P2: 아무 로그도 없다. 두 화면 모두 가시가 사라지지 않는다. 위험 1: 생성자에 bReplicates = true가 없어 이 액터가 복제되지 않으므로 P2에 값이 가지 않고 OnRep도 불리지 않는다. 위험 2: C++ OnRep은 서버에서 자동 호출되지 않아 호스트 화면도 갱신되지 않는다.
(2) 생성자에 bReplicates = true; 추가. Disarm()에서 bArmed = false; 다음에 OnRep_Armed(); 직접 호출. 블루프린트 RepNotify였다면 서버에서도 호출되므로 위험 2(호스트 화면 미갱신)는 생기지 않는다(복제 설정 누락 문제는 그대로).
(3) 클래스와 변수 이름으로 리플렉션에서 프로퍼티를 찾아, 그 프로퍼티를 복제 대상으로 OutLifetimeProps 배열에 등록하는 코드로 펼쳐진다. 이름 검사가 컴파일 시점에 이뤄지므로 bArmd처럼 없는 멤버 이름을 쓰면 컴파일 에러로 바로 알 수 있다.
(4) bReplicates, GetLifetimeReplicatedProps, HasAuthority, GetLocalRole. 유니티: NetworkVariable<bool>(값 변경 콜백 포함)이 UE 복제 프로퍼티에 대응한다.

**채점표 (10점)**

- [3] (1) 서버 로그만, 클라 로그 없음, 두 화면 모두 변화 없음 + 위험 2곳 지적
- [2.5] (2) bReplicates 추가, 서버 OnRep 직접 호출, BP RepNotify 차이
- [2.5] (3) 프로퍼티 찾아 OutLifetimeProps에 등록, 이름 오타는 컴파일 에러
- [2] (4) Actor.h 선언 4가지와 NetworkVariable 대응

> 작성 메모: DOREPLIFETIME의 실제 전개(GetReplicatedProperty, RegisterReplicatedLifetimeProperty 등 내부 함수 이름)는 엔진 버전에 따라 달라 정답 요건에서 뺐다(확인 필요). '프로퍼티를 이름으로 찾아(컴파일 시 이름 검사) OutLifetimeProps에 등록'까지만 채점한다. UE5에서 GetLifetimeReplicatedProps 헤더 선언을 UHT가 대신 만들어 주는지 여부도 다루지 않았다.

### P1-085 (0.39점) — 목표: W14-13, W14-14, W14-15, W14-28

**모범 답안**

(1) (가) Server RPC, Reliable: 상태를 바꾸는 중요한 요청. (나) NetMulticast, Unreliable: 잦은 일회성 연출. (다) Client RPC, Reliable: 소유 클라 한 명에게만 가는 중요한 알림. (라) NetMulticast, Unreliable: 잦은 연출, 일부 빠져도 무방.
(2) Reliable은 재전송·순서 보장 비용이 있어, 초당 수백 개를 보내면 대역폭과 버퍼가 포화되고 다른 중요한 RPC까지 밀리며 심하면 연결이 끊긴다. 연출은 Unreliable로 보낸다.
(3) Server RPC는 호출하는 클라이언트가 그 액터의 소유 연결(Owner 체인이 그 클라의 PlayerController)일 때만 실행되고 아니면 버려진다. 적은 서버가 소유하므로 P2의 호출이 버려진다. 고치기: P2가 소유한 캐릭터에 ServerAttack 같은 Server RPC를 두고, 서버가 판정한 뒤 서버에서 ApplyDamage로 적에게 데미지를 준다(판정을 서버에서 하는 것이 서버 권위에도 맞다).
(4) ServerRpc ↔ Server RPC, ClientRpc ↔ Client RPC(소유 클라 하나) 또는 NetMulticast(모두).

**채점표 (10점)**

- [4] (1) 4개 이벤트의 RPC 종류와 Reliable 선택, 항목당 1점
- [2] (2) Reliable 남발의 대역폭·버퍼 포화, 연결 끊김
- [3] (3) 오너십 규칙과 소유 캐릭터의 Server RPC를 거치는 수정
- [1] (4) ServerRpc/ClientRpc 대응

> 작성 메모: (1)의 연출 항목(라)은 RPC 없이 복제된 체력 변화(OnRep)를 보고 각 클라가 로컬로 재생해도 정답으로 인정한다. NGO의 ClientRpc는 기본적으로 모든 클라에게 가므로 Multicast에 가깝고 대상 지정 시 Client RPC에 가깝다는 세부는 확인 필요로 두고 둘 다 인정한다.

### P1-086 (0.39점) — 목표: W14-16, W14-22, W15-14, W15-15

**모범 답안**

(1) GameMode: 서버만. C1의 PlayerController: 서버 + C1. C1의 HUD: C1만. C1의 Pawn: 모두(서버·C1·C2). C2의 PlayerState: 모두. GameState: 모두. 보스 Pawn: 모두. 보스 AIController: 서버만.
(2) 분노 상태: 복제 프로퍼티 — 지속되는 상태라 늦게 온 클라도 최신 값을 받아야 한다(OnRep에서 눈 색 변경). 포효: Unreliable Multicast — 그 순간의 일회성 연출.
(3) Multicast만: C3는 지나간 이벤트를 못 받아 평상시 눈으로 보인다(불일치). 복제 프로퍼티: 접속 시 현재 값이 복제되어 빨간 눈으로 보인다. 상자 열림도 상태이므로 복제 프로퍼티로 보내야 C3에게 열린 상자로 보인다.
(4) AIController는 서버에만 존재하고 클라이언트에는 없다. C1이 보는 보스는 서버 상태를 받아 보간하는 Pawn 복제본(SimulatedProxy)이다. 클라에 필요한 AI 정보는 Pawn의 복제 프로퍼티로 보낸다.

**채점표 (10점)**

- [4] (1) 8개 객체의 존재 위치, 항목당 0.5점
- [2] (2) 상태=복제 프로퍼티, 일회성 연출=Unreliable Multicast와 이유
- [2] (3) 늦은 접속자 차이와 상자 열림 판단
- [2] (4) AIController는 서버에만, 클라는 SimulatedProxy만 봄

> 작성 메모: Listen Server에서 호스트 P1의 HUD는 P1 머신에 있다(P1이 그 머신의 로컬 플레이어). 커리큘럼 표의 'HUD=소유 클라만'을 기준으로 채점한다.

### P1-087 (0.39점) — 목표: W14-24, W14-26, W14-37, W15-16

**모범 답안**

(1) 예)
P2->>P2: 버튼 상호작용 입력(IsLocallyControlled)
P2->>P1: ServerUseButton(Button) [Server RPC, P2 소유 캐릭터를 통해]
P1->>P1: HasAuthority() 통과 → bCalled = true, 엘리베이터 이동 시작
P1->>P1: OnRep_Called() 직접 호출(호스트 화면)
P1-->>P2: bCalled 복제(엘리베이터 위치도 복제)
P2->>P2: OnRep_Called() 자동 호출 → 버튼 불빛 등 연출
(2) ① P2: 입력(P2) → ServerAttack RPC(P2→P1) → 몽타주는 서버에서 재생·동기화(오너 선재생 허용) → 노티파이 판정(P1) → ApplyDamage(P1) → 체력 복제 → 각 클라 OnRep → UI. ② P1: 입력(P1) → ServerAttack 호출은 서버에서 부르므로 네트워크를 타지 않고 P1에서 바로 실행 → 판정·ApplyDamage(P1) → 체력 값 변경, 호스트 UI는 서버에서 직접 갱신(OnRep 직접 호출 등), P2에는 복제 → OnRep → UI. 판정·데미지는 두 경우 모두 서버에서 한다(서버 권위).
(3) GameMode: 서버만 / PlayerController: 서버 + 소유 클라 / PlayerState: 모두 / GameState: 모두.

**채점표 (10점)**

- [3] (1) 시퀀스 순서(입력→Server RPC→서버 상태 변경→복제→OnRep)
- [2] (1) HasAuthority 위치와 호스트 OnRep 직접 호출 표시
- [3.5] (2) P2·P1 공격 시 단계별 실행 위치, 호스트의 Server RPC는 로컬 실행
- [1.5] (3) 클래스 존재 위치 4행

> 작성 메모: 서버에서 Server RPC를 호출하면 네트워크를 거치지 않고 서버에서 바로 실행된다(UE RPC 규칙). 몽타주 동기화 방식(Multicast vs 복제 상태)은 커리큘럼 W15 핵심 개념이지만 하나로 정하지 않았으므로 어느 방식이든 '다른 머신에서도 보이게 동기화'를 쓰면 인정한다. Mermaid 문법 오류는 감점하지 않는다.

### P1-088 (0.29점) — 목표: W14-20, W14-21, W14-23

**모범 답안**

(1) Mine->ServerWave(): 실행된다 — P2가 소유한 캐릭터(Owner 체인이 P2의 PlayerController)라서. P3Char->ServerWave(): 실행되지 않는다 — P3 소유 액터라 P2의 호출은 버려진다. 로그에 소유 연결이 없어 처리하지 않는다는 취지의 경고가 남는다. 고치기: P2 자신의 캐릭터(또는 PC)에 ServerWaveTo(ANetLabCharacter* Target) 같은 Server RPC를 만들고 서버가 대상 처리를 한다.
(2) P2: 왼쪽 2, 오른쪽 2(Unreliable이라 드물게 빠질 수 있음). P4: 왼쪽 2(접속 시 현재 RepPhase 복제 → OnRep), 오른쪽 1(지나간 Multicast는 받지 못함).
(3) P1(서버) 150, P2 0, P3(주인) 150, P4 0. COND_OwnerOnly는 소유 연결(P3)에게만 복제하므로 P2는 값을 받지 못한다. 팀원에게도 보여야 한다면 조건 없이(또는 다른 조건으로) 복제해야 한다.

**채점표 (10점)**

- [4] (1) 내 캐릭터 호출은 실행, P3 캐릭터 호출은 버려짐 + 이유 + 로그 + 수정
- [3] (2) P2·P4 표시판 4칸(P4 오른쪽 1이 핵심)
- [3] (3) P1 150, P2 0, P3 150, P4 0과 OwnerOnly가 맞지 않는 이유

> 작성 메모: 실패 로그의 정확한 문구는 버전에 따라 다르므로 '소유 연결이 없어 처리하지 않는다'는 의미만 채점한다(확인 필요). 서버(호스트)는 모든 액터의 실제 값을 가지므로 COND_OwnerOnly 변수도 서버에서는 설정 값이 보인다. 실험 2의 '서버에서는 직접 갱신' 조건은 C++ OnRep이 서버에서 자동 호출되지 않는 점을 피하려고 문제에 명시했다.

### P1-089 (0.29점) — 목표: W15-02, W15-03, W15-17

**모범 답안**

(1) Slam: 일회성 연출이므로 Unreliable NetMulticast. B가 Slam 이후에 들어오면 지나간 Slam은 볼 필요가 없다. Berserk: 지속 상태이므로 복제 변수 + OnRep. B가 들어와도 서버의 최신 값(광폭화 중)을 받아 붉은 연출을 바로 보여 준다.
(2) Slam을 상태로: 매번 상태 값을 바꾸고 되돌리는 처리가 필요하고, 값이 짧게 바뀌면 복제 사이에 묻혀 연출이 빠질 수 있다(일회성 이벤트에 맞지 않음). Berserk를 Multicast로: 늦게 들어온 B는 과거 이벤트를 받지 못해 광폭화 상태를 보지 못한다. Unreliable이면 손실 시 영구 불일치.
(3) 캐릭터 이동은 CharacterMovementComponent(CMC)가 클라이언트 예측까지 처리한다. 클라가 먼저 이동하고 서버가 검증해 틀리면 보정하며, 다른 클라에는 복제본으로 보여 준다. 직접 RPC로 위치를 보내면 중복 구현이고 끊김·대역폭 낭비가 생긴다.
(4) `CharacterMovementComponent.h`(Engine/Source/Runtime/Engine/Classes/GameFramework). FSavedMove_Character: 클라가 예측 실행한 이동을 저장해 서버 확인·보정 후 다시 쓰는 구조체. ClientAdjustPosition: 서버 판단에 따라 클라 위치를 보정하는 함수.

**채점표 (10점)**

- [3] Slam=Unreliable Multicast, Berserk=복제 상태, 늦은 접속을 근거로 설명
- [2] 반대로 골랐을 때의 문제 2개
- [2.5] CMC의 클라 예측·서버 검증·보정으로 반박
- [2.5] 헤더와 FSavedMove_Character·ClientAdjustPosition 역할

> 작성 메모: 근거: W14 자가 점검(NetMulticast vs 복제 프로퍼티), W15 핵심 개념·엔진 소스 읽기. FSavedMove_Character·ClientAdjustPosition은 커리큘럼상 '이름만 찾아두기'라 역할을 한 줄로 설명하면 만점. 내부 세부 동작(재시뮬레이션 단계 등)은 요구하지 않는다.

### P1-090 (0.29점) — 목표: W15-04, W15-05, W21-03

**모범 답안**

(1) 환경 설정: PIE 2인 Listen Server + 네트워크 에뮬레이션 지연 200ms(손실은 선택). 관찰: 호스트가 아닌 클라이언트 쪽에서 대시를 여러 번 눌러 반응 지연과 대시 중 위치 튐을 관찰하고 녹화한다. 기록: TS 문서(증상·재현 단계·가설과 검증·원인·해결)로 남긴다.
(2) 클라는 자기 속도(600)로 예측 이동하고 그 이동을 서버로 보낸다. 서버는 그 이동을 2000으로 다시 계산한다. 서버 쪽 위치가 클라보다 앞서므로, 서버가 클라 위치를 보정해 앞으로 당긴다(대시 동안 여러 번). 반응이 늦은 것은 RPC가 서버에 도착하고 보정 결과가 돌아올 때까지 지연만큼 걸리기 때문이다. 반대로 클라만 먼저 빨라지면 클라가 서버보다 앞서 나가 뒤로 되돌려진다. 공통 원인: 클라 예측에 쓰는 속도와 서버 검증에 쓰는 속도가 시점상 다르다.
(3) 권위는 지켜진다. 하지만 이동은 클라 예측을 전제로 동작하므로, 예측에 쓰는 값이 서버와 같은 시점에 같지 않으면 보정이 생긴다. 반응성도 지연만큼 나빠진다. 정석 해결: CMC 커스텀(SavedMove 플래그) 또는 GAS 같은 예측 가능한 구조(커리큘럼 표현). 채점자 참고: GAS 예측만으로는 CMC 이동 기록과 시점이 자동으로 맞춰지지 않으므로, 이동 속도 문제는 CMC 커스텀이 가장 직접적이다. 이 점을 덧붙이면 가점이고, 요구하지는 않는다.
(4) 대시·스프린트 여부를 이동 데이터(SavedMove)의 압축 플래그에 실어 보낸다. 클라는 즉시 예측하고, 서버는 그 이동을 계산할 때 같은 플래그로 같은 속도를 적용한다. 그래서 양쪽 계산이 같아져 보정이 거의 생기지 않는다. W15 러버밴딩 TS의 정석 해결을 실제로 구현하는 것이 딥다이브 C다.

**채점표 (10점)**

- [2] 환경 설정(2인 PIE + 지연, 클라 쪽 관찰) → 관찰 → TS 기록 절차
- [3] 서버만 빨라질 때 앞으로 보정되는 이유 2 + 반대 방식의 보정 방향(뒤로)과 공통 원인(시점상 속도 차이) 1
- [2.5] 서버 권위만으로는 부족한 이유 + 정석 해결 2가지
- [2.5] 압축 플래그로 양쪽이 같은 시점에 같은 속도를 쓰게 함 + W15 TS의 정석 해결

> 검토에서 고친 점: B형에는 세 가지 문제가 있다. ① '클라는 서버에서 복제돼 오는 값이 바뀌어야 빨라진다'는 전제가 틀렸다. MaxWalkSpeed는 기본으로 복제되지 않는다. ② 보정이 '대시가 끝날 무렵'에만 생긴다는 현상 묘사가 부정확하다. 실제로는 대시 동안 여러 번 생긴다. ③ 문항이 'A형의 클라만 먼저 빨라짐'이라고 다른 형을 직접 언급한다. B형만 받는 응시자는 A형을 볼 수 없다. 또 두 형의 정석 해결 'GAS 같은 예측 구조'는 커리큘럼 표현이라 인정하되, GAS 예측만으로는 CMC 이동 기록과 시점이 맞춰지지 않는다는 채점자 참고를 붙였다(요구 요건은 그대로).

> 작성 메모: 근거: W15 핵심 개념·과제5·자가 점검, W21 핵심 개념 C. 'GetCompressedFlags/UpdateFromCompressedFlags' 같은 함수 이름은 커리큘럼에 없으므로 요구하지 않음(쓰면 가점 없음, 감점도 없음).

### P1-091 (0.39점) — 목표: W16-03, W16-24, W16-28, W17-14

**모범 답안**

(1) ASC를 가운데 두고: GameplayAbility(GA_Cleanse) → ASC가 부여·활성화. GameplayEffect(GE_Poison) → ASC가 적용 → AttributeSet(Health·Mana) 값 변경. GameplayTags(State.Poisoned, Cooldown.Cleanse) → ASC가 보유, 어빌리티 조건과 GE 부여 태그에 사용.
(2) 독 피해: GE_Poison = Duration 5초 + Period 1초 + Health -4 Modifier, State.Poisoned 태그 부여. 회복 금지: 포션 어빌리티가 State.Poisoned 태그가 있으면 활성화 차단(태그 조건). 해독 스킬: GameplayAbility(GA_Cleanse)가 중독 GE·태그를 제거. 비용·쿨다운: Cost GE(Mana -10) + Cooldown GE(8초, Cooldown 태그), CommitAbility에서 적용.
(3) ASC는 어빌리티 부여·활성화와 GameplayEffect 적용을 담당하는 중심 컴포넌트다. 장판이 Health를 직접 깎으면 태그(중독 상태)·지속시간·해독 같은 다른 규칙과 연결되지 않고 복제·예측 구조도 우회한다. 장판은 ASC에 GE_Poison을 적용하기만 한다.
(4) 유니티: BuffManager에 버프 리스트, 코루틴으로 1초마다 체력 감소, 상태 bool로 포션 막기, 쿨다운 타이머를 직접 짰다. GAS는 대응 내장 기능이 없던 이것을 '스킬·버프·스탯을 엔진이 제공하는 프레임워크'로 대체한다. 지속시간·주기·태그 조건·비용·쿨다운을 데이터(GE·태그)로 설정한다.

**채점표 (10점)**

- [3] 5요소 그림과 각 요소의 역할
- [3] 독 피해·회복 금지·해독·비용/쿨다운 대응
- [2] ASC의 역할(부여·활성화, GE 적용)로 직접 수정 방식을 반박
- [2] 유니티 직접 구현 예시와 GAS 프레임워크 대체 비교

> 작성 메모: 근거: W16 핵심 개념·유니티 비교·DoD, W17 유니티 비교. 그림은 박스·화살표 수준이면 충분.

### P1-092 (0.39점) — 목표: W16-01, W16-07, W16-08

**모범 답안**

(1) ⓐ UArenaAttributeSet ⓑ GetStaminaAttribute() ⓒ GetIncomingDamageAttribute() ⓓ SetIncomingDamage(0.f)
(2) GetShieldAttribute(), GetShield(), SetShield(), InitShield(). 이 코드에서는 GetShield()·SetShield()가 쓰였다(ⓑⓒ에서는 Stamina·IncomingDamage의 GetXxxAttribute가 쓰임). 매크로 예시는 엔진 AttributeSet.h의 주석에 있고, 값은 FGameplayAttributeData로 저장된다.
(3) 첫 번째: Absorbed = min(40, 15) = 15 → Shield 0, 남은 데미지 25 → Health 35. 두 번째: Shield가 0이라 흡수 0 → 35 - 50 = -15 → Clamp → Health 0, Shield 0.
(4) Pre: Stamina 값이 바뀌기 직전에 0~MaxStamina로 제한해, 재생·소모 GE로 범위를 넘는 것을 막는다. Post: 데미지 반영 후 Health가 0 아래(또는 MaxHealth 위)로 가는 것을 막는다.
(5) ① 보호막·방어력 계산이 AttributeSet 한 곳에 모인다. 무기를 추가해도 계산을 복사하지 않고, 공식을 바꿀 때도 한 곳만 고친다. ② GE 실행 결과로 서버에서만 처리되고 결과가 복제된다. 클라가 각자 계산해 어긋나거나 조작될 위험이 없다.

**채점표 (10점)**

- [2] 빈칸 ⓐ~ⓓ (각 0.5)
- [2] 매크로가 만드는 함수 4개 + 사용된 것 1.5, 예시 위치 AttributeSet.h 주석 0.5
- [2] Shield 0·Health 35 → Health 0 계산
- [2] Pre/Post Clamp가 막는 상황 구분
- [2] 메타 속성 이유 2가지(계산 집중, 서버 처리)

> 검토에서 고친 점: W16-01은 'AttributeSet.h의 예시 주석과 FGameplayAttributeData를 참고해' 매크로를 읽는 목표다. A형은 매크로 예시가 어디에 있는지 묻지만, B형은 묻지 않아 목표의 엔진 소스 부분이 빠졌다. B형 (2)에 이 질문을 넣고 채점표에 반영했다.

> 작성 메모: 근거: W16 생존 문법(ATTRIBUTE_ACCESSORS), 핵심 개념, 자가 점검(메타 속성). 최근 엔진 버전에 ATTRIBUTE_ACCESSORS_BASIC 같은 기본 매크로가 AttributeSet.h에 추가됐다는 정보가 있으나 확인 필요라서 정답 요건에서 제외. PreAttributeChange가 Current 값 변경 직전에 불린다는 점까지 쓰면 가점(요구 아님).

### P1-093 (0.39점) — 목표: W16-09, W16-10, W16-14, W16-15

**모범 답안**

(1) GE_Poison: HasDuration(6초) + Periodic(2초). 주기마다 실행되며, 실행될 때마다 Base가 바뀐다. GE_Arrow: Instant, Base 영구 변경. GE_Focus: Infinite, 적용 중에만 Current 수정. GE_Slow: HasDuration(4초), 적용 중에만 Current 수정. enum 값은 헤더 표기(Instant / HasDuration / Infinite)가 정확하지만, 커리큘럼 표기 'Duration'으로 써도 인정한다.
(2) 3번 실행 → 100 - 30 = 70. Periodic 실행은 실행될 때마다 Instant처럼 Base를 바꾸므로 독이 끝나도 돌아오지 않는다. GE_Slow는 Current만 수정했으므로 끝나면 600으로 돌아온다.
(3) 대상 속성 = Health(또는 메타 속성 IncomingDamage), 연산 = 더하기(음수 값), 크기 = SetByCaller(태그로 코드에서 값 전달).
(4) ActivateAbility → CommitAbility(비용·쿨다운 확정) → 실패면 EndAbility 후 return, 성공이면 차지·발사 → 끝나면 EndAbility. GameplayAbility.h에서 시그니처와 주석을 직접 확인해, 어떤 순서로 불리고 무엇을 하는지의 근거로 삼는다.
(5) CommitAbility는 비용(Cost GE)과 쿨다운(Cooldown GE)을 실제로 적용하는 '확정' 단계다. 마나가 부족하면 비용을 적용할 수 없어 실패를 반환한다. 그러면 어빌리티는 발사하지 말고 EndAbility로 끝낸다.

**채점표 (10점)**

- [3] 4개 GE의 DurationType(HasDuration/Duration 모두 인정)·Periodic·Base/Current (항목당 0.75)
- [2] 독 결과 70과 복구되지 않는 이유(Periodic 실행=Base 변경), Slow 종료 후 600
- [1.5] Modifier 3요소(속성·연산·크기/SetByCaller)
- [2] Activate → Commit → End 흐름과 헤더 확인 이유
- [1.5] Commit의 확정 의미와 실패 처리

> 검토에서 고친 점: B형 GE_Poison(6초, 2초 주기)은 적용 즉시 실행(bExecutePeriodicEffectOnApplication) 기본값이 켜져 있으면 0·2·4·6초에 4번 실행되어 체력이 60이 된다. 모범 답안의 70(3번)과 맞지 않고, 이 설정은 커리큘럼에 없다. 실행 횟수를 문제에 명시해, 시험하려는 'Periodic 실행은 Base를 바꾼다'는 점만 보게 했다. 또 B형은 enum 값을 묻는데, 커리큘럼은 'Duration', 헤더는 'HasDuration'으로 표기한다. 둘 다 인정하도록 명시했다.

> 작성 메모: 근거: W16 핵심 개념(UGameplayEffect·UGameplayAbility), 엔진 소스 읽기(GameplayEffect.h, GameplayAbility.h), 자가 점검. EGameplayEffectDurationType의 실제 값 이름은 Instant / HasDuration / Infinite. ModifierOp의 세부 연산 이름은 UE5 중 변경 이력이 있어 확인 필요라서 요구하지 않음. 보통 TryActivate 단계에서 비용·쿨다운을 미리 검사해 활성화 자체가 거부될 수 있다는 점은 가점 사항.

### P1-094 (0.39점) — 목표: W16-18, W16-20, W16-21

**모범 답안**

(1) PossessedBy는 서버에서만 불리므로 클라에서는 ASC 초기화가 일어나지 않는다. 클라는 PlayerState가 복제되어 도착하는 OnRep_PlayerState에서도 초기화해야 한다(서버 PossessedBy + 클라 OnRep_PlayerState).
(2) Full: 모든 GE를 모든 클라에 복제. Mixed: GE는 소유 클라에만, 태그·큐는 모두에게. Minimal: GE 없이 태그·큐만. 모두 Full이면 잡몹 40마리의 GE까지 모든 클라에 복제돼 불필요한 트래픽이 생긴다. Full은 싱글·소규모용이다. 플레이어 = Mixed, 적 = Minimal.
(3) 적(AI·소모성 유닛)은 폰과 수명을 같이하는 Character에 두는 게 구조가 단순하고, 죽으면 함께 정리된다. AI는 PlayerState도 없다(일반적으로). 플레이어 PlayerState의 이점: 리스폰해도 속성·어빌리티 유지. 주의: PlayerState는 기본 복제 빈도가 낮아 올려야 할 수 있다.

**채점표 (10점)**

- [3] 원인(PossessedBy는 서버만) + OnRep_PlayerState 추가
- [4] 3모드 정의 + Full 남용 문제 + 플레이어 Mixed·적 Minimal
- [3] 적=Character 이유, 플레이어=PlayerState 이점·복제 빈도 주의

> 작성 메모: 근거: W16 핵심 개념(ASC 위치·Replication Mode·초기화 타이밍), 자가 점검. 초기화 때 호출하는 함수(InitAbilityActorInfo)는 커리큘럼에 이름이 없으므로 요구하지 않음. 'PlayerState 복제 빈도'를 올리는 구체 API도 요구하지 않음.

### P1-095 (0.29점) — 목표: W16-22, W16-23, W16-25, W17-13

**모범 답안**

(1) (A) GiveAbility: 어빌리티를 ASC에 부여하고 핸들 반환. (B) TryActivateAbility: 그 핸들의 어빌리티 발동 시도, 성공 여부 반환. (F) ApplyGameplayEffectSpecToSelf: 광폭화 GE 스펙을 자신에게 적용. 헤더: AbilitySystemComponent.h.
(2) 공격할 때마다 같은 어빌리티가 새로 부여되어 스펙이 계속 쌓인다(중복 부여, 메모리·관리 문제). 부여는 적 스폰 시 한 번, 서버(HasAuthority)에서 하고 핸들을 저장해 두었다가 BTTask에서는 TryActivateAbility만 부른다.
(3) ① 발동이 실패해도(쿨다운·비용·태그 조건) 성공으로 보고해 BT가 공격한 것처럼 진행한다. ② 성공해도 시전 몽타주가 끝나기 전에 BT가 다음 태스크로 넘어간다. 고치기: 반환값이 false면 Failed. 성공이면 InProgress를 반환하고 어빌리티 종료 시 FinishLatentTask로 통보(AbortTask도 처리).
(4) (D) 인스턴싱 정책: 실행할 때마다 새 인스턴스. (E) 네트워크 실행 정책: 로컬 예측(소유 클라가 먼저 실행하고 서버가 승인). 확인 위치: GameplayAbility.h. 적은 소유 클라가 없고 AI는 서버에만 있으므로 ServerOnly(또는 서버 주도 실행)가 의도에 맞다. 예측할 플레이어 입력이 없기 때문이다.
(5) 전부 읽지 않고, 앞부분과 ASC 구조처럼 내 프로젝트에 필요한 부분만 훑어 참고해 설계(ASC 위치·모드 등)에 반영한다.

**채점표 (10점)**

- [2.5] GiveAbility·TryActivateAbility·ApplyGameplayEffectSpecToSelf 역할 + 헤더
- [2] (A) 중복 부여 문제 + 스폰 시 서버에서 한 번 부여·핸들 저장
- [2.5] (B)(C) 문제 2가지 + Failed/InProgress·FinishLatentTask 수정
- [2] 인스턴싱·네트워크 실행 정책 의미, GameplayAbility.h, 적=ServerOnly 이유
- [1] 참고 자료를 필요한 부분만 훑어 반영

> 검토에서 고친 점: W16-23은 'GameplayAbility.h에서 인스턴싱·네트워크 실행 정책 설정을 찾아보는' 목표다. B형은 확인할 헤더를 묻지만, A형은 정책의 의미만 묻고 헤더는 묻지 않는다. A형 (3)에 헤더 질문을 넣고 채점표에 반영했다.

> 작성 메모: 근거: W16 엔진 소스 읽기(AbilitySystemComponent.h·GameplayAbility.h), 과제6(tranek/GASDocumentation·Lyra), W17 과제4, W10 BTTask(InProgress·FinishLatentTask). 코드 속 InitAbilityActorInfo·MakeOutgoingSpec·MakeEffectContext는 주어진 코드로만 읽히고 정답 요건이 아니다. 클라에서 GiveAbility를 부르면 실패하고 에러 로그가 남는다는 세부 동작은 확인 필요(요건은 '서버에서만 부여'까지). 인스턴싱 정책 NonInstanced는 UE 5.5 무렵부터 사용 중단(deprecated)으로 알려져 있으나 확인 필요라서 묻지 않음.

### P1-096 (0.39점) — 목표: W17-01, W17-15, W17-19

**모범 답안**

(1) 정의: AbilityTask는 어빌리티 안에서 몽타주 재생 대기·이벤트 대기·타깃 대기 같은 비동기 작업을 수행하는 단위다. 작업이 끝나거나 중단되면 완료·중단 델리게이트로 다음 로직에 흐름을 잇는다. 로그: A start → B tasks ready → (끝). C fire·D end는 찍히지 않는다. 태스크는 어빌리티 안의 작업이라 어빌리티가 살아 있어야 콜백이 온다. (X)에서 어빌리티를 바로 끝내면 태스크도 함께 정리되고(몽타주도 멈춤), 0.8초 이벤트를 받을 대상이 없어 발사가 안 된다.
(2) A start → B tasks ready → C fire(0.8초) → D end(블렌드아웃 시작 또는 완료 시점). EndAbility는 OnMontageEnd 콜백에서 불린다(어빌리티 종료를 콜백 쪽으로 옮김). D end가 블렌드아웃·완료로 두 번 불릴 수 있다고 쓰고, 첫 EndAbility 뒤에는 태스크가 정리된다고 설명하면 가점.
(3) 몽타주가 정상 완료·블렌드아웃되든, 피격으로 중단되든, 취소되든 반드시 EndAbility에 도달하게 하려고 4개를 모두 연결했다. 그러지 않으면 어빌리티가 활성 상태로 남아 다시 발동하지 못한다. true는 '이벤트를 한 번만 받고 끝(OnlyTriggerOnce)'이라는 뜻으로, 발사가 한 번만 일어나게 한다.
(4) AbilityTask_PlayMontageAndWait.h(완료·중단·블렌드아웃 델리게이트), AbilityTask_WaitGameplayEvent.h(이벤트 태그 대기 방식과 옵션), AbilitySystemBlueprintLibrary.h(SendGameplayEventToActor).

**채점표 (10점)**

- [1] AbilityTask 정의(어빌리티 안의 비동기 작업 단위 + 완료·중단 델리게이트로 흐름 연결)
- [2.5] 로그 A→B만 출력 예측 + 어빌리티 종료 시 태스크도 끝나 콜백이 오지 않는 이유
- [2.5] (X) 삭제 후 A→B→C→D 순서, 콜백에서 EndAbility
- [2] 델리게이트 4개 연결 이유 + 한 번만 받기 옵션
- [2] 헤더 3개 대응

> 검토에서 고친 점: W17-19는 AbilityTask가 '어빌리티 안에서 몽타주 대기·이벤트 대기·타깃 대기 같은 비동기 작업을 수행하고, 완료·중단 델리게이트로 흐름을 잇는 단위'임을 설명하는 목표다. A형은 정의를 직접 묻지만, B형은 묻지 않고 채점표에도 점수가 없다. B형 (1)에 정의를 넣고 채점표를 나눴다.

> 작성 메모: 근거: W17 생존 문법(AbilityTask 델리게이트), 엔진 소스 읽기 3개 헤더, 자가 점검. WaitGameplayEvent의 OnlyTriggerOnce 기본값 false는 확인 필요(A형 (2)에서 두 번 출력되는 근거). 어빌리티가 끝나면 태스크가 함께 정리되고 bStopWhenAbilityEnds 기본 true로 몽타주도 멈춘다는 점은 일반적인 동작이나, 채점은 '콜백이 오지 않는다' 수준이면 만점. InstancedPerActor 어빌리티가 이미 활성 상태면 재발동이 거부된다는 점은 정답 요건에 포함(엔진 동작), 단 재발동 옵션(bRetriggerInstancedAbility)은 요구하지 않음.

### P1-097 (0.29점) — 목표: W17-20, W17-21, W17-22, W15-11

**모범 답안**

(1) 정상이다. GameplayCue는 순수 연출(이펙트·사운드)을 게임 로직과 분리하는 장치이고, 연출이라 데디케이티드 서버에서는 실행되지 않는다. 사망 판정(State.Dead 태그 등)은 서버 로직에서 처리되고, 연출은 네트워크로 효율적으로 전달되어 클라에서 재생된다.
(2) 클라가 서버 승인 전에 예측 키를 붙여 대시를 먼저 실행한다. 서버가 같은 예측 키로 승인하면 유지된다. 서버가 거부하면(스태미나 부족) 클라가 예측으로 실행한 결과를 되돌린다. 지연을 체감에서 숨긴다.
(3) 비용: 학습 곡선, 보일러플레이트, 디버깅 난이도. 작은 게임엔 과할 수 있다는 점은 인정한다. ADR-0004에서 '클라 예측 직접 구현' vs 'GAS 예측'을 비교했다. 예측·승인·롤백을 직접 짜면 복잡하고 버그가 많아, 검증된 프레임워크를 쓰고 스킬·버프·스탯 구조까지 통일하려고 GAS를 택했다. 결과: 지연 200ms에서 W15(RPC) vs W17(GAS 예측) 반응성 비교 영상.
(4) `showdebug abilitysystem`으로 ASC가 가진 태그·적용 중인 GE·어빌리티 상태를 확인한다. ADR에 대안 비교·트레이드오프·결정 이유를 남겨 두었으므로 '왜 그렇게 했나'에 기억이 아니라 기록으로 답할 수 있다.

**채점표 (10점)**

- [2.5] Q1: 데디 서버 미실행이 정상 + 연출/로직 분리·효율 전달
- [2.5] Q2: 예측 키로 먼저 실행, 승인 유지, 거부 되돌림
- [3] Q3: 비용 3가지 + ADR-0004 선택지·결정 근거·비교 영상
- [2] showdebug abilitysystem 활용 + ADR이 주는 근거

> 작성 메모: 근거: W17 자가 점검(GameplayCue·로컬 예측·GAS 비용), W15 과제6(ADR-0004), 9장 ADR 템플릿. 예측 키 이름(FPredictionKey)은 요구하지 않음.

### P1-098 (0.29점) — 목표: W17-02, W17-11, W22-03

**모범 답안**

(1) ① 연결된 것(사망 델리게이트 → 리스폰, 체력바, AI 도망 판단, 복제)이 한꺼번에 끊겨 무엇 때문에 깨졌는지 찾기 어렵다. ② PR 하나가 커서 리뷰·되돌리기가 어렵고, 그동안 main이 실행 불가가 될 수 있다.
(2) 예: ① AttributeSet 추가(기존 유지, 빌드 확인) → ② 데미지를 GE → IncomingDamage → Health로(같은 수치 확인) → ③ 체력바를 속성 변경 델리게이트(GetGameplayAttributeValueChangeDelegate) 구독으로, 위젯 인터페이스 유지(UI 확인) → ④ 사망(State.Dead 태그 등)·리스폰, AI 판단이 새 값(속성)을 읽게 교체(시나리오 확인) → ⑤ 2인 확인 후 HealthComponent 제거. 단계별 PR.
(3) PIE 싱글, PIE 2인 Listen Server, 네트워크 에뮬레이션 지연 200ms(손실 포함 가능). 그 상태에서 데미지·사망·리스폰·UI·AI 도망 동작 확인(2인 10분 연속 무버그 같은 기준이면 가점).
(4) W5 델리게이트 컴포넌트(UI 결합 제거, PR/Devlog 링크) → W8 데이터·데미지 파이프라인(수치 하드코딩 제거, PR) → W15 네트워크 복제(2인 협동 서버 권위, TS 링크) → W17 GAS AttributeSet(예측·버프 통합, ADR-0004/PR·비교 영상).

**채점표 (10점)**

- [2] 한 번에 교체할 때의 위험 2가지(연결 단절·큰 PR/main 깨짐)
- [3.5] 단계적 계획과 단계별 완료 확인, 속성 델리게이트·위젯 인터페이스 유지
- [2] 검증 조건 3가지(싱글·2인·지연)
- [2.5] 체력 진화 행 4단계와 이유·근거 링크

> 작성 메모: 근거: W17 생존 문법(마이그레이션 순서)·과제2(UI는 속성 변경 델리게이트, W9 위젯 인터페이스 유지), 2장 '같은 기능의 진화', W22 과제2. 단계 수·세부 순서는 '안 깨고 단계적으로, 단계마다 검증'이라는 원리가 맞으면 다른 순서도 인정.

### P1-099 (0.29점) — 목표: W18-04, W18-06, W18-15, W18-16

**모범 답안**

(1) GPU. GPU 24.6ms가 Frame 25.0ms에 가장 가깝다. Game·Draw는 여유가 있다. 그 영역(GPU)을 Insights 등으로 상세 분석해 무엇이 무거운지 찾는다.
(2) 게임 스레드는 병목이 아니므로 BTService 주기·Tick을 줄여도 프레임은 거의 개선되지 않는다. AI 반응만 둔해지고 복잡도만 는다. 병목이 아닌 곳을 고치면 효과 없이 복잡도만 늘어나므로 측정으로 병목을 먼저 찾는다.
(3) ① 전원 연결 + Windows 전원 모드 '최고 성능'(배터리 모드는 수치가 흔들림) ② 같은 조건에서 여러 번 측정해 중간값 사용(한 번 측정은 신뢰 불가). 대표값: 중간값 24.9ms. 18.4처럼 튄 값에 평균이 흔들리지 않게 한다.
(4) Unity Profiler ↔ Unreal Insights. `Profiler.BeginSample("이름")` ↔ `TRACE_CPUPROFILER_EVENT_SCOPE(이름)`을 함수 안에 넣으면 Insights 트레이스에서 그 구간이 보인다.

**채점표 (10점)**

- [3] GPU 병목 판정 + 근거 + 상세 분석
- [2.5] 제안 효과 없음 예측 + 측정 먼저 이유
- [2.5] 측정 방식 개선 2가지 + 중간값 24.9와 이유
- [2] Profiler/BeginSample ↔ Insights/TRACE_CPUPROFILER_EVENT_SCOPE

> 작성 메모: 근거: W18 핵심 개념·측정 주의·유니티 비교·자가 점검. 프레임 시간은 대략 가장 느린 스레드에 맞춰진다는 커리큘럼 기준으로 채점.

### P1-100 (0.19점) — 목표: W18-08, W18-09, W18-17

**모범 답안**

① stat unit은 스레드별 시간만 보여 줄 뿐 메모리를 무엇이 차지하는지 알 수 없다. Memory Insights로 메모리 사용(할당·에셋별 크기, 시간에 따른 증가)을 분석해 해제되지 않는 대상을 찾는다.
② 서버 프레임이 정상이고 클라만 끊기면 네트워크(복제 트래픽) 문제일 수 있다. Networking Insights로 네트워크 트래픽을 분석해, 투사체 같은 액터의 복제량·패킷 크기 상위 항목을 확인한다.
(3) ⓐ DECLARE_CYCLE_STAT ⓑ TRACE_CPUPROFILER_EVENT_SCOPE ⓒ SCOPE_CYCLE_COUNTER. 헤더: TRACE_CPUPROFILER_EVENT_SCOPE는 CpuProfilerTrace.h(Core/Public/ProfilingDebugging), DECLARE_CYCLE_STAT·SCOPE_CYCLE_COUNTER는 Stats.h(Core/Public/Stats). 결과: TRACE는 Unreal Insights CPU 트레이스에서 구간으로, SCOPE_CYCLE_COUNTER는 stat 명령(해당 stat 그룹, 예: stat game)에서 수치로 확인.

**채점표 (10점)**

- [2.5] ① stat unit의 한계 + Memory Insights 용도
- [2.5] ② 네트워크 의심 근거 + Networking Insights 용도
- [3] 빈칸 ⓐⓑⓒ (각 1)
- [2] 헤더 2개 + 결과 확인 위치 구분

> 작성 메모: 근거: W18 핵심 개념(Insights 3종), 엔진 소스 읽기(CpuProfilerTrace.h, Stats.h), W15·W18 심화. SCOPE_CYCLE_COUNTER 통계가 Insights에도 표시되는지는 설정에 따라 달라 확인 필요라서 요건에서 제외. 요건은 'stat 명령으로 그룹 확인'.

### P1-101 (0.29점) — 목표: W18-12, W18-13, W18-14

**모범 답안**

(1) ① NetUpdateFrequency: 액터의 복제 검사 빈도. 많은 투사체의 검사·전송 횟수를 적정 수준으로 낮춘다. ② Dormancy: 변화 없는 액터를 복제 대상에서 휴면 처리해 서버 CPU와 대역폭을 아낀다. ③ Relevancy: 각 클라에게 관련 있는(가까운 등) 액터만 복제해 대상을 줄인다. B에게는 먼 북쪽 액터를 보내지 않는다.
(2) 모든 액터가 초당 1번만 검사되어 플레이어·적 움직임과 상태 변화가 늦고 끊겨 보인다. 액터마다 필요한 빈도가 다르므로 측정하며 액터별로 정해야 한다.
(3) 휴면 상태인 문(또는 레버)의 상태가 바뀔 때 휴면을 풀지(깨우지) 않아 변경이 복제되지 않았다. 상태를 바꾸는 순간 깨워야 한다. (서버에서 상태를 바꾸지 않았다 같은 권위 문제도 함께 의심하면 가점.)
(4) B에게 그 액터들이 관련 대상이 되어 복제가 시작되고, B 화면에 나타난다(최신 상태를 받음).

**채점표 (10점)**

- [6] ①②③ 대응과 각 원리 (각 2)
- [1.5] 일괄 1로 낮출 때의 문제
- [1.5] 휴면을 깨우지 않아 복제되지 않음
- [1] 관련 대상이 되면 복제 시작

> 작성 메모: 근거: W18 핵심 개념·자가 점검. Dormancy를 깨우는 API(FlushNetDormancy 등)나 Relevancy 세부 설정(NetCullDistanceSquared 등)은 커리큘럼에 없으므로 요구하지 않음. 쓰면 가점 없이 인정.

### P1-102 (0.19점) — 목표: W18-11, W18-23

**모범 답안**

(1) 화면 밖 적은 애니메이션 틱이 생략되거나 업데이트 빈도가 낮아졌다. 그래서 공격 몽타주의 노티파이 구간(판정 시작·끝)이 불리지 않거나 늦게 불려 Sweep 판정이 일어나지 않았다. 정면에서는 적이 화면에 보여 정상적으로 틱되므로 노티파이가 불린다. (참고: 리슨 서버라면 판정을 하는 서버, 즉 호스트 화면을 기준으로 같은 일이 생긴다. 쓰면 가점이고, 요구하지는 않는다.)
(2) 확인: 판정 노티파이에 로그·디버그 드로잉을 넣고 등진 상태와 정면 상태를 비교한다. 옵션을 끄면 재현되지 않는지도 확인한다. 고치는 방향: ① 공격 중(몽타주 재생 중)인 적이나 판정 노티파이가 있는 몽타주는 화면 밖에서도 틱되게 예외 처리한다. ② 가까운 적은 업데이트 비율을 낮추지 않고, 멀리 있는 적에만 적용한다.
(3) ① 거리·가시성에 따른 업데이트 빈도 낮추기(Update Rate Optimization): 먼 적의 애니메이션 계산 횟수를 줄인다. ② 화면 밖 애니메이션 틱 생략: 보이지 않는 적의 계산을 줄인다. ③ 불필요한 본·노드 정리: 매 업데이트마다 계산하는 양 자체를 줄인다.

**채점표 (10점)**

- [3.5] 원인(틱 생략·빈도 저하 → 노티파이 미발생 → 판정 누락) + 정면 정상 이유
- [3] 확인 방법 + 수정 방향 2가지
- [3.5] 방법 3가지와 각각 줄이는 것

> 검토에서 고친 점: 애니메이션 틱 생략으로 판정 노티파이가 빠지는지는, 판정을 실행하는 머신이 메시를 렌더링하는지에 달려 있다. 리슨 서버에서는 판정이 호스트에서 일어나므로 기준은 호스트 화면이다. A형 모범 답안의 예 '2인 협동에서 한 플레이어 화면 밖 적만'은 클라이언트 화면도 기준이 되는 것처럼 써 있어 부정확하다. B형의 '등지고 있으면'도 누구 화면 기준인지 정하지 않아, 클라이언트가 등을 돌린 경우로 읽으면 설명이 성립하지 않는다. A형 답안 예시를 고치고, B형 상황을 싱글 플레이 기준으로 한정했다.

> 작성 메모: 근거: W18 핵심 개념(업데이트 비율, 화면 밖 애니메이션 틱 옵션), 자가 점검. 실제 옵션 이름(VisibilityBasedAnimTickOption 등)은 커리큘럼에 없으므로 요구하지 않음. 렌더링이 없는 데디케이티드 서버에서의 가시성 판정 세부는 확인 필요라서 요건에서 제외.

### P1-103 (0.29점) — 목표: W19-06, W19-11

**모범 답안**

(1) Development: check 실패 → 크래시(콜스택 확인). Shipping: check는 기본적으로 식 자체가 제거되어 검사하지 않는다.
(2) ensure는 기본적으로 첫 1회만 보고한다 → 1번. 보고 후 계속 진행하고 Interval을 1로 보정해 게임이 이어진다.
(3) Development: (3)과 (4) 모두 SpawnEnemy를 실행 → 2마리. Shipping: (3)의 check 식이 제거되고 (4)의 verify는 평가 → 1마리. 빌드마다 게임 동작이 달라져 개발 중 테스트한 결과와 출시 빌드가 다르게 된다(Shipping에서만 나는 버그).
(4) `verify(SpawnEnemy(Row));` 한 줄만 남기거나, `const bool bSpawned = SpawnEnemy(Row); check(bSpawned);`(또는 ensure)처럼 부수효과를 매크로 밖으로 뺀다.
(5) AssertionMacros.h. 테스트: AutomationTest.h(IMPLEMENT_SIMPLE_AUTOMATION_TEST, EAutomationTestFlags). 치트: CheatManager.h.

**채점표 (10점)**

- [2] (1) Development 크래시 / Shipping 식 제거
- [1.5] (2) 1번 보고 + 계속 진행
- [2.5] (3) 2마리 vs 1마리 + 위험성
- [1.5] (4) 부수효과 분리 또는 verify로 수정
- [2.5] (5) AssertionMacros.h·AutomationTest.h·CheatManager.h

> 작성 메모: 근거: W19 핵심 개념·자가 점검·엔진 소스 읽기. ensure가 '실행마다 첫 1회만 보고'인지 '호출 지점마다'인지는 커리큘럼 표현('기본 첫 1회만') 기준으로 채점. ensureAlways는 커리큘럼에 없으므로 요구하지 않음.

### P1-104 (0.19점) — 목표: W19-03, W19-10, W19-14, W19-18

**모범 답안**

(1) 화살을 꺼내 적에게 부착하고 충돌 상태를 바꾼 뒤 반환하고, 다시 꺼낸다. 검증: ① 부착(따라다니기)이 해제됨 ② 충돌·Tick·가시성이 활성 상태로 리셋됨 ③ 속도·수명 등 상태가 초기화됨 ④ 새로 스폰하지 않고 재사용함. 재사용 시 BeginPlay가 다시 불리지 않으므로 Reset 함수를 검증하는 것이 핵심이다.
(2) 정상 → 기절 태그 부여(이동이 막히는지 검증) → 기절 해제(태그 제거) → 검증: State.Stunned 없음, 이동 입력 허용. 각 전이 직후에 검사한다.
(3) Simple Automation Test: IMPLEMENT_SIMPLE_AUTOMATION_TEST 매크로로 테스트 하나를 정의하고 RunTest 안에서 검사한다. Automation Spec: Simple과 함께 쓰이는 또 다른 작성 방식이다. 둘 다 Test Automation 창(또는 Session Frontend)에서 실행한다. Spec의 내부 문법(Describe/It 등)은 커리큘럼 밖이라 요구하지 않는다. 'Spec은 여러 케이스를 구조적으로 묶어 쓰기 좋다'고 덧붙이면 인정하되 가점은 없다.
(4) PlayMode ↔ Functional Test(월드에서 액터를 띄워 흐름 검증. W19 심화의 '적 스폰 → 처치 → 웨이브 종료' 통합 테스트). EditMode ↔ Automation Test(월드 없이 로직 검증).
(5) 개수보다 '무엇을 왜 테스트했는지'를 쓴다. 실제 버그를 재발 방지 테스트로 만든 것(TS의 재발 방지 칸과 연결)은 품질·회귀 방지를 생각하는 개발자라는 증거다.

**채점표 (10점)**

- [2.5] 버그 1 회귀 테스트(검증 3가지 이상)
- [2.5] 버그 2 태그 전이 테스트(순서·검증 시점)
- [1.5] 두 방식 이름(Simple Automation Test·Automation Spec) + IMPLEMENT_SIMPLE_AUTOMATION_TEST + 실행 위치(Test Automation 창 또는 Session Frontend) (각 0.5)
- [1.5] PlayMode↔Functional Test, EditMode↔Automation Test
- [2] 무엇을 왜 테스트했는지 설명 + 품질·회귀 방지 증거

> 검토에서 고친 점: 커리큘럼은 Automation Spec을 'Automation Test(`IMPLEMENT_SIMPLE_AUTOMATION_TEST`, Automation Spec)'라고 이름만 소개한다(W19-03: 또 다른 작성 방식임을 구분). 그런데 두 형 모두 '두 방식이 어떻게 다른가'를 묻고, 모범 답안에는 커리큘럼에 없는 구조 차이(시나리오 단위로 묶기)가 들어 있다. B형은 문제 상황에 'Spec=여러 케이스 묶기'라는 정답까지 깔려 있다. 두 형 모두 (3)을 커리큘럼 범위(두 방식의 이름, Simple 정의 매크로, 실행 위치)로 줄였다.

> 작성 메모: 근거: W19 핵심 개념·유니티 비교·과제1·자가 점검·심화(Functional Test), W12 풀링 주의점. Automation Spec의 Describe/It 문법은 요구하지 않음(쓰면 인정). 테스트 함수 이름(TestEqual 등)도 요구하지 않음.

### P1-105 (0.19점) — 목표: W20-08, W20-15

**모범 답안**

(1) Global Time Dilation은 월드 전체 시간을 바꾸므로 때리지 않은 다른 플레이어의 캐릭터도 멈칫한다. 또 서버 흐름(웨이브 타이머·AI·이동)까지 함께 느려져 게임 진행이 꼬인다.
(2) 맞은 액터와 때린 액터의 CustomTimeDilation만 아주 짧게 낮췄다가 원래대로 되돌린다. 강도·시간은 DataAsset으로 조절한다. 필요하면 카메라 셰이크와 피격 플래시로 손맛을 보강한다.
(3) 히트스톱은 연출이므로 판정 로직에는 영향이 없게 한다. 데미지·판정은 서버에서 정상 흐름대로 처리해야 상태 불일치나 판정 타이밍 차이가 생기지 않는다. 보이는 손맛과 게임 규칙을 분리한다.
(4) Time.timeScale 조작 ↔ CustomTimeDilation(액터별 시간 배율). Cinemachine Impulse ↔ Camera Shake(UCameraShakeBase).

**채점표 (10점)**

- [3] 두 리포트의 원인(전체 시간 → 다른 플레이어·서버 흐름)
- [2.5] CustomTimeDilation을 맞은·때린 액터만 짧게
- [2.5] 판정 로직에 영향 없음 원칙과 이유
- [2] timeScale↔CustomTimeDilation, Impulse↔Camera Shake

> 작성 메모: 근거: W20 핵심 개념·유니티 비교·자가 점검. Global Time Dilation을 바꾸는 함수 이름(SetGlobalTimeDilation)은 커리큘럼에 없으므로 요구하지 않음. CustomTimeDilation이 기본으로 복제되지 않는다는 점은 확인 필요라서 요건에서 제외.

### P1-106 (0.10점) — 목표: C-14, C-15, C-16, C-17

**모범 답안**

① 문제: 이해 없이 고친 코드를 받으면 설명 못 하는 코드를 커밋하게 된다. 고침(코드 해설 L1): C#/유니티 2개월·C++ 처음 + 한 줄씩 C#과 비교 + `&`(참조)·`const`·`->`·`::`·템플릿/매크로 의미 짚기 + 마지막에 이해 확인 질문 3개, 정답은 내가 답한 뒤.
② 문제: 모범 답안 암기는 꼬리 질문에 무너진다. 고침(자가 점검 공부): 배경 + 질문 원문 + 유니티/C# 비유 한 줄, 핵심 3~5줄(용어 풀어서), 직접 확인 방법 1가지, 확인 질문 1개(정답은 답한 뒤), 통째로 외우게 하지 말 것.
③ 문제: L2는 내가 쓰고 AI가 리뷰하는 단계인데 완성 코드를 받는다. 고침(힌트 모드): 정답 코드는 주지 말고 구현을 5단계로 쪼개 단계별 목표와 사용할 클래스·함수 이름만, 단계별 내 코드를 보여 주면 리뷰.
④ 문제: 정답 코드를 받으면 코테 실력이 늘지 않는다. 고침(코테 힌트): 문제 번호·제목, C++ + 정답 코드 금지 + 내 코드와 결과(시간 초과) + ① 놓친 조건 ② 의심되는 줄 ③ 반례 1개 순서로 힌트만.

**채점표 (10점)**

- [2.5] ① 문제 지적 + 코드 해설 프롬프트 요소
- [2.5] ② 문제 지적 + 자가 점검 공부 프롬프트 요소
- [2.5] ③ 문제 지적 + 힌트 모드 요소(5단계·이름만·리뷰)
- [2.5] ④ 문제 지적 + 코테 힌트 요소(순서 포함)

> 작성 메모: 근거: 4장 프롬프트 라이브러리(코드 해설 L1, 자가 점검 질문 공부, 힌트 모드 L2, 코테 힌트). 문장이 같을 필요 없고 필수 요소가 들어 있으면 만점. 1부는 AI 없이 보는 시험이므로 '프롬프트를 쓰는 능력'만 평가.

### P1-107 (0.19점) — 목표: C-06, C-18, C-19, C-20, C-21

**모범 답안**

① 함수 이름에 F12(정의로 이동)로 시그니처·주석을 직접 확인한다. 이 방식은 UE4 시절의 기존 입력 바인딩이고, 커리큘럼은 Enhanced Input(Input Action + BindAction(IA, ETriggerEvent...))을 쓴다. AI가 UE4 시절 API를 알려 준 사례로 TIL에 기록한다(면접 소재).
② 설치·설정 막힘: 과제 이름/환경(Windows 11) + 따라 하기 몇 번째 단계에서 멈췄는지 + 에러 메시지 원문과 스크린샷 + 원인 후보 3개를 가능성 순으로, 각각 확인 방법(메뉴는 한글·영어 병기, 버전마다 다른 건 '공식 문서 확인 필요' 표시).
③ 증상(적 사망 2번, 점수 2배) + 재현 단계 + 이미 확인한 것(같은 프레임 Die() 2회 로그) → 다음에 확인할 것 3개를 우선순위로. 규칙: 15분 룰. 먼저 15분 동안 로그·중단점·콜스택으로 직접 좁히고, '내가 시도한 것'과 함께 묻는다.
④ Epic C++ 코딩 표준 + UE 5.8 기준, 심각도 순. 항목: GC 안전성(UPROPERTY/TObjectPtr)·네트워크 권한·Tick 사용·하드 레퍼런스·네이밍·const. 정렬: ① UPROPERTY 없음(GC 안전성, 크래시 위험) → ② Tick에서 매 프레임 검색(성능) → ③ 네이밍 a1(가독성).
⑤ 'UE 5.8의 ACharacter::PossessedBy(또는 컨트롤러 Possess에서 시작)가 내부적으로 어떤 순서로 불리는지 파일명·함수명만 순서대로 짚어줘. 확실하지 않은 부분은 확인 필요로 표시해줘.' 이유: 엔진 소스를 직접 따라가며 확인해야 내 근거가 되고, AI가 지어낸 설명을 그대로 믿는 위험을 줄인다.

**채점표 (10점)**

- [2.5] ① F12 확인 + UE4 시절 API 인지 + TIL 기록
- [2] ② 설치 막힘 프롬프트 요소 4가지
- [2] ③ 디버깅 프롬프트 요소 + 15분 룰
- [2] ④ 리뷰 기준·항목 + 심각도 정렬
- [1.5] ⑤ 길잡이 프롬프트 + 이유

> 작성 메모: 근거: 4장 AI 페어 프로그래밍 5원칙 2, 프롬프트 라이브러리(설치·설정 막힘 / 에러 해석 / 디버깅 / 코드 리뷰 / 엔진 소스 길잡이). A형 ①의 함수는 일부러 지어낸 가짜 함수. B형 ①의 BindAction("Jump", IE_Pressed, ...)는 실제로 존재하는 UE4식 기존 입력 바인딩이며, 커리큘럼은 Enhanced Input을 사용.

### P1-108 (0.10점) — 목표: C-22, C-23, C-65, W03-28

**모범 답안**

가: 내 코드를 근거로 하지 않고, 질문 수·방식이 없으며, 채점·보충 조건이 없다. 고친 예: "너는 게임회사 UE 클라이언트 신입 면접관이야. 내 ALifecycleProbe 코드(첨부)를 보고 꼬리 질문 5개를 하나씩 해줘. 내가 답하면 채점하고 부족한 부분만 짧게 보충해줘."
나: '제일 좋은 것' 하나만 묻고 근거 비교가 없으며, 코드를 요구해 스스로 설계할 기회가 줄어든다. 고친 예: "상호작용 감지 설계 선택지(Tick·타이머·Overlap)를 장단점 표로 비교해줘. 6개월 포트폴리오 규모 전제로 추천 1개와 이유를 붙여줘. 코드는 쓰지 마."
다: AI가 빈 내용을 지어 넣으면 배우지 않은 것이 기록돼 TIL이 내 증거가 아니게 된다. 고친 예: "아래 메모의 문장은 바꾸지 말고 TIL 템플릿(키워드 / 배운 것 / 코드·실험 / 막힌 점 → 해결 / 다음 할 일) 칸에 배치만 해줘. 빈 칸은 채우지 말고 '비어 있음'으로 표시해줘."
기록: 질문 5개, 각 질문에 대한 내 답, 채점 결과(와 보충).

**채점표 (10점)**

- [3] 가: 문제(코드 근거·5개 하나씩·채점 보충 없음) + 고친 프롬프트
- [3] 나: 문제(비교·규모 전제·코드 금지 없음) + 고친 프롬프트
- [3] 다: 지어낸 내용 문제 + 문장 유지·템플릿·'비어 있음' 프롬프트
- [1] W3 기록 항목

> 작성 메모: 커리큘럼 4장 프롬프트 라이브러리(면접관 모드·설계 비교)와 6장 TIL 정리 프롬프트의 조건을 채점 기준으로 삼았다. 문장 표현은 달라도 조건이 모두 들어가면 만점이다.

### P1-109 (0.10점) — 목표: C-02, C-04, W01-28

**모범 답안**

(1) ① 모든 줄에 해설 주석을 달며 다시 쓴다 ② 설명 못 하는 WatchLoose 줄에서 멈추고, AI에게 묻거나 엔진 소스로 확인해 이해한다(소유하지 않고 관찰하는 약한 포인터, 사라지면 IsValid false) ③ 그 줄에도 해설 주석을 단다 ④ 모든 줄을 설명할 수 있게 되면 학습 로그 저장소에 커밋·Push한다. 설명 못 하는 줄이 남아 있으면 커밋하지 않는다.
(2) 예: // UPROPERTY로 등록한 UObject 포인터라 GC가 이 참조를 따라가 살려 둔다 // 이 액터를 Outer로 UGCLabItem 객체를 런타임에 새로 만든다 // LogArena 카테고리 Warning으로, 관찰 포인터가 아직 살아 있는지(1/0)를 출력.
(3) ① AI 없이 직접 작성한다 ② 동작을 확인한다 ③ 엣지 케이스·대안만 AI에게 묻는다. 전체 코드를 받으면 L3의 목적(AI 없이 쓰는 실력 증명, 면접·코테 대비)이 사라진다. 질문 예: '체력이 이미 최대일 때나 죽은 상태에서 먹으면 빠진 처리가 있나?', '회복을 즉시 대신 타이머로 나눠 주면 장단점은?'

**채점표 (10점)**

- [4] (1) L1 순서 + 모르는 줄 질문·이해 후 주석 + 학습 로그 커밋(설명 못 하면 커밋 안 함)
- [3] (2) 세 줄 해설이 정확함(각 1점)
- [3] (3) L3 순서 + 전체 코드 요청 금지 이유 + 질문 2개

> 작성 메모: 해설 주석은 내용이 맞으면 표현은 자유다.

### P1-110 (0.19점) — 목표: C-03, C-05, W11-03, W13-15

**모범 답안**

(1) ① 채택: 매 Tick 검색은 낭비, 한 번 캐시(UPROPERTY로 GC 안전). ② 채택: 포인터 유효성 검사 습관(W11 생존 문법). ③ 채택: 함수 이름 짓기, 의도를 드러내는 이름. ④ 거절: 언리얼은 Perception에 시야·가림·팀 필터·감지/상실 이벤트가 내장돼 있어 직접 구현은 중복이고 Tick 비용도 든다. ⑤ 거절: 엔진 소스에 없는 API, AI가 지어낸 함수일 수 있음 — 소스 확인 결과를 근거로 거절, AI가 틀린 사례로 기록(시야 반경은 Sight 감각 설정에서). ⑥ 채택: 매직 넘버 제거, 데이터 주도(W8 구조).
(2) 예: 'AI 리뷰 ④ Tick LineTrace 시야 — 거절. 이유: AI Perception이 시야·가림 트레이스·감지/상실 이벤트를 제공, Tick 추가는 비용·중복.' PR의 AI 활용 내역에 의견마다 채택/거절 + 이유를 남긴다.
(3) '설명 못 하는 코드는 커밋하지 않는다'(셀프 리뷰 체크리스트 1번). 커밋을 멈추고 → AI에게 그 줄을 다시 묻거나 소스·문서로 확인 → 이해한 내용을 TIL에 내 말로 정리 → 설명할 수 있게 된 뒤 체크리스트 체크 후 커밋.

**채점표 (10점)**

- [6] (1) 6개 판단(채택 ①②③⑥, 거절 ④⑤)과 이유, 항목당 1점
- [2] (2) PR에 의견별 채택/거절 + 이유 기록 형식
- [2] (3) 설명 못 하는 코드는 커밋 금지 → 다시 묻기 → TIL에 내 말로 → 커밋

> 작성 메모: ⑤의 '엔진에 선언이 없었다'는 문제에서 확인 결과로 주어진다. 응시자가 판단 근거로 '소스 확인 결과'를 쓰면 만점. 채택/거절이 모범과 달라도 근거가 커리큘럼 원칙에 맞으면 부분 점수(0.5)를 준다.

### P1-111 (0.10점) — 목표: C-08, C-09, W09-37

**모범 답안**

(1) '힌트 먼저, 코드는 마지막' 원칙과 L2(내가 먼저 쓰고 AI가 리뷰)를 어겼다. 다시 보낼 예: '웨이브 DataTable 기반 스포너를 만들 거야. 코드는 주지 말고 구현 단계와 각 단계에서 쓸 클래스·함수 이름, 주의점만 알려줘. 코드는 내가 쓸게, 완성되면 흐름 설명과 리뷰만 부탁해.' 받은 120줄은 복사하지 않고 내가 먼저 작성한 뒤 비교·리뷰용으로만 본다.
(2) 예: 사용 범위: 단계 설계 질문, 리뷰. 내가 검증·수정한 것: 리뷰 지적대로 FindRow 결과 null 검사 추가, 빈 행 데이터로 PIE 테스트. AI가 틀렸던 것: DataTable 함수 시그니처를 잘못 제시 → DataTable.h에서 확인 후 수정.

**채점표 (10점)**

- [2] (1) 힌트 먼저 원칙·L2 위반 지적과 받은 코드 처리
- [4] (1) 설계·단계·주의점 요청 + '코드는 내가 쓸게' 범위 제한 프롬프트
- [4] (2) AI 활용 내역 세 칸을 구체적으로 작성

> 작성 메모: 프롬프트 문장은 자유. '정답 코드 요청 없음'과 '범위 제한(흐름 설명·리뷰만)'이 모두 있어야 (1) 만점.

### P1-112 (0.10점) — 목표: C-66, C-67, C-68

**모범 답안**

기능 완성도 2점: 핵심 흐름은 동작하지만 예외·엣지 케이스(적 수 0 웨이브)를 처리하지 못한다. 데모 중 오류는 없었으므로 1점은 아니다. 보강: 빈 행·0·음수 데이터 검증과 처리(테스트로 고정).
코드 품질 1점: 거대 클래스(GameMode 2,000줄) + 하드코딩(체력·간격 숫자). 네이밍은 지켰지만 1점 기준에 해당한다. 보강: 책임을 컴포넌트·Subsystem으로 나누고 수치를 DataTable/DataAsset으로 옮김.
엔진 이해 2점: 동작 원리를 말로 설명. 소스·콜스택 근거가 없어 3점은 아니다. 보강: 엔진 소스(BeginPlay 호출 흐름)·콜스택 캡처를 근거로 엔진 노트 작성.
추가: 1점 항목(코드 품질)이 있으므로 다음 단계로 넘어가기 전에 그 항목부터 보강한다.

**채점표 (10점)**

- [3] 기능 완성도 2점 + 근거 + 보강
- [3.5] 코드 품질 1점 + 근거(거대 클래스·하드코딩) + 보강
- [2.5] 엔진 이해 2점 + 근거 + 보강
- [1] 1점 항목부터 보강 규칙

> 작성 메모: 근거: 7장 루브릭. 경계 사례는 근거가 루브릭 문구에 맞으면 ±1점까지 인정(채점자 재량).

### P1-113 (0.10점) — 목표: C-69, C-70, C-71, W12-21

**모범 답안**

(1) 문제 해결 기록 2점: TIL 메모만 있고 TS 템플릿으로 원인·해결을 쓰지 않음. 협업 습관 2점: 기능 단위 커밋은 했지만 이슈 ↔ PR 연결과 셀프 리뷰가 없어 3점 아님. AI 활용 4점: 직접 작성 후 리뷰·채택 근거에 더해 AI-Off 재구현 성공, AI 오류를 소스로 검증한 사례가 있음.
(2) 예: Keep: AI 제안을 엔진 소스로 검증하는 습관. Problem: 버그 기록이 메모뿐이라 면접 근거가 약함, 이슈 없는 PR. Try: 다음 버그부터 TS 템플릿으로 작성, PR 전에 이슈 만들고 연결 + 셀프 리뷰 체크. 6항목: 기능 완성도, 코드 품질, 엔진 이해, 문제 해결 기록, 협업 습관(Git), AI 활용.

**채점표 (10점)**

- [6] (1) 세 항목 점수(2·2·4점)와 루브릭 근거, 항목당 2점
- [2] (2) 기록에 근거한 Keep·Problem·Try
- [2] (2) 루브릭 6항목 이름

> 작성 메모: 루브릭 목표 평균(M3~M4 2.5~3점)과 '1점 항목이 있으면 그 항목부터 보강'은 가산 요소로만 본다. 점수가 모범과 1점 차이라도 루브릭 문구를 근거로 정확히 설명하면 해당 항목 1점을 준다.

### P1-114 (0.10점) — 목표: C-73, W08-35, W12-25, W16-26

**모범 답안**

(1) 각 단계 마지막 주차 아래의 관문 체크리스트를 산출물로 하나씩 확인해 모두 통과해야 다음 단계로 넘어간다. 빠진 항목은 먼저 보강한다.
(2) M2: 미통과 — '코드 변경 0줄로 무기 추가한 PR' 조건 위반(.h 변경이 있음, 데이터만으로 추가해야 함). M3: 미통과 — ADR 3건 중 2건(ADR-0003 풀링 결정 기록 누락 가능성). M4: 미통과 — AI-Off 챌린지 ③(90분) 기록 없음. 나머지 조건은 충족.

**채점표 (10점)**

- [2] (1) 관문 체크리스트 전부 통과해야 다음 단계, 산출물로 점검
- [2.5] (2) M2 미통과·무기 PR에 코드 변경
- [3] (2) M3 미통과·ADR 부족
- [2.5] (2) M4 미통과·AI-Off ③ 누락

> 작성 메모: 관문 조건은 커리큘럼 W08·W12·W16 관문 체크리스트 원문 기준이다. 메뉴 경로나 파일 위치는 묻지 않았다.

### P1-115 (0.10점) — 목표: C-72, W20-20, W24-03, W24-10

**모범 답안**

(1) (3+3+4+3+3+2)/6 = 18/6 = 3.0. M5~M6 목표 '3점 이상'을 충족한다. 1점 항목이 없으므로 '1점부터 보강' 규칙에 해당하지 않는다(가장 낮은 AI 활용 2는 개선 후보).
(2) 조건: 딥다이브 리포트 / 영상·README·PDF 완성 / 질문 은행 90% 답변 / 지원 10곳 + 매핑표 / v1.0.0 + 6개월 회고. 판정: 불통과. PDF 미완성(15~20쪽 필요), 질문 은행 85%(90% 미달), 6개월 회고가 숫자 없이 미완성.
(3) 커밋·PR·TS·ADR 개수(GitHub 저장소, docs/troubleshooting·docs/adr), 코테 문제 수(coding-test 폴더), 성능 개선 %(성능 리포트 전후 수치). docs/retro/6months.md에 작성.
(4) v0.4.0·v0.5.0 릴리즈 / 반응성 전후 비교 영상 / 성능 리포트 개선 3건 / 자동화 테스트 5개+ / 열린 버그 0 또는 Known Issues / 코테 누적 92문제.

**채점표 (10점)**

- [2.5] 평균 3.0 계산·목표 충족 + 1점 항목 판정
- [3.5] M6 조건 5개 + 불통과 판정과 미충족 3개
- [2] 회고 숫자 항목과 출처
- [2] M5 조건 6개

> 작성 메모: 근거: 7장 목표 평균, W20 M5 관문, W24 핵심 개념·과제4·M6 관문. 집계 출처(GitHub 등)는 합리적이면 인정.

### P1-116 (0.19점) — 목표: W21-02, W21-04, W21-05, W21-06

**모범 답안**

(1) 온라인·액션 게임 회사이므로 C(CMC 커스텀 이동 예측, FSavedMove 플래그). 기준: 온라인·액션 게임 회사 → C, 툴·파이프라인 조직 → D, AI 도입에 적극적인 회사 → A.
(2) D: Editor Utility Widget 또는 에디터 모듈로 기획자용 웨이브 편집기를 만든다. 연결 예: '팀의 반복 작업을 줄이는 도구를 만들어 본 경험'으로, 회사의 콘텐츠·데이터 작업 효율과 연결해 말한다(회사가 원하는 역량과 다르다는 점은 솔직히 인정).
(3) B는 재구현만이 아니라 BT 버전과 비교하는 것이 핵심이다. 비교 관점: 구조, 디버깅, 성능.
(4) E는 강의 요약이 아니라 엔진 소스를 근거로 분석하는 것이다. 대상: CMC 이동 예측·보정 흐름 또는 GC 흐름 중 하나를 골라 파일·함수·콜스택을 근거로 블로그 3편을 쓴다.

**채점표 (10점)**

- [3] C 추천 + 추천 기준 3가지
- [2] D 내용 + 연결 방법
- [2.5] B: 비교가 핵심 + 관점 3가지
- [2.5] E: 소스 근거 분석, 대상 2가지 중 선택, 3편

> 작성 메모: 근거: W21 핵심 개념 A~E, 유니티/C#에서 건너오기(추천). 추천 대응은 커리큘럼이 C·D·A만 명시하므로 B·E에 대해서는 이유가 합리적이면 인정.

### P1-117 (0.10점) — 목표: W21-07, W21-08, W21-09

**모범 답안**

(1) 예: ① BT 버전 기준 기록(구조 그림·디버깅 방식·성능 ms) — 완료: 기준표 ② StateTree로 근접 적 재구현 — 완료: 같은 행동(순찰·추적·공격) 동작 ③ 디버깅 비교(같은 버그를 두 버전에서 찾는 과정) — 완료: 스크린샷·기록 ④ 성능 비교(적 N마리 게임 스레드 ms, 같은 조건 반복 중간값) — 완료: 전후 표 ⑤ 리포트·블로그 — 완료: deepdive.md 머지.
(2) 문제 정의: BT로 만든 적 AI의 구조·디버깅·성능 한계를 StateTree와 비교하려 함. 접근: 같은 행동을 StateTree로 재구현, 같은 조건에서 비교. 결과(수치·영상): 구조 비교 그림, 디버깅 비교, 적 N마리 기준 ms 비교(예시 수치), 동작 영상. 한계와 다음 단계: 원거리 적 미적용, 샘플 수 제한 등.
(3) 제목 예: 'Behavior Tree vs StateTree — 같은 적 AI를 두 번 만들어 비교해 보니'. 덜어 낼 것: 이슈·작업 일지 세부. 더할 것: 독자용 배경 설명, 그림·GIF, 핵심 수치 표, 저장소·리포트 링크.

**채점표 (10점)**

- [4] 이슈 5개 이내 + 완료 조건(비교 관점 포함)
- [4] 4단계 재구성 + 빠진 결과 수치·영상·한계 보완
- [2] 블로그 재가공(제목, 덜고 더할 것)

> 작성 메모: 근거: W21 과제1~3, AI 프롬프트(5개 이슈 + 완료 기준). 이슈 구성은 예시이며 5개 이내·완료 조건이 명확하면 인정.

### P1-118 (0.19점) — 목표: W22-01, W22-05, W22-10, W23-03

**모범 답안**

(1) 문제: ① 너무 길다(2~3분 권장) ② 첫 10초 훅이 없다(메뉴로 시작) ③ 자막으로 기술명 표기·디버그 시각화가 없어 무슨 기술인지 알 수 없다. (공개 방식은 일부 공개 권장.) 순서: 훅 → 게임 루프 요약 → 기술 시연(자막, 판정 디버그·AI 디버거·지연 전후 비교) → 성능 수치·구조 다이어그램 → GitHub·연락처.
(2) 표지 / 자기소개(C#→UE 전환 스토리) / 프로젝트 개요 / 아키텍처 / 핵심 기술 4개(각 문제→설계→코드 발췌→결과) / 트러블슈팅 3건 / 성능 개선 전후 표 / 같은 기능의 진화 / 학습 방식(AI 원칙·AI-Off·6개월 숫자) / 엔진 소스 분석 요약. 코드는 전체가 아니라 핵심 발췌만. 국내 채용은 PDF 제출이 많다.
(3) 장르·기간·인원 → 핵심 기술 3개(데이터 주도 전투, 2인 협동+GAS 예측, 성능 개선 수치) → 가장 어려웠던 문제 한 줄 → 배운 점. 숫자와 링크로 말한다(열정 같은 형용사 대신 증거).
(4) 1분은 핵심 요약, 3분은 구조·어려웠던 문제 해결 과정·결과 수치를 더 깊게 다룬다. 질문 시간·상황에 맞춰 바로 말할 수 있게 미리 스크립트로 써서 연습한다.

**채점표 (10점)**

- [3] 영상 문제 3가지 + 구성안 순서
- [3] PDF 재구성 10항목+ + 코드 발췌 원칙 + PDF 이유
- [2.5] 1분 소개 재작성(순서·숫자·링크)
- [1.5] 1분/3분 차이와 스크립트 이유

> 작성 메모: 근거: W22 핵심 개념·과제1·과제3·자가 점검, 9장 시연 영상 구성·포트폴리오 PDF 구성, W23 과제4. 수치·링크는 가상 예시 허용.

### P1-119 (0.10점) — 목표: W24-01, W24-02, W24-05, W24-06, W22-08

**모범 답안**

(1) 1: '2인 협동 전환에서 생긴 버그 ○건을 TS로 기록하고 해결했습니다(TS 링크, 지연 200ms 비교 영상).' 2: 'GA_MeleeCombo·GA_Dash를 GAS로 구현하고, 직접 예측과 GAS 예측을 ADR-0004로 비교해 도입했습니다(PR·ADR 링크).' 3: '6개월간 매일 TIL·주간 Devlog로 전환 과정을 기록했습니다(학습 로그 저장소 링크).' 형용사 주장 대신 증거(PR·TS·영상·리포트)를 붙인다.
(2) 지원 회사 10곳 리스트, 공고 요구사항 ↔ 내 증거(링크) 매핑표가 빠졌다.
(3) 질문 원문 → 내가 한 답(못 함) → 부족했던 점 → 정리한 정답(변화 없는 액터를 복제 대상에서 휴면 처리해 서버 CPU·대역폭 절약) → 다음 행동(질문 은행에 추가, 말로 연습).
(4) 피드백 내용과 반영 방향을 기록(이슈·Devlog)하고 README를 30초 안에 읽히게 줄인다(핵심 표·링크 중심). 반영 PR로 무엇을 바꿨는지 남긴다.

**채점표 (10점)**

- [3] 문장 3개를 근거 링크가 붙은 문장으로 수정
- [2] 10곳 리스트·매핑표 누락 지적
- [2.5] 면접 복기 문서 형식
- [2.5] 피드백 반영과 기록

> 검토에서 고친 점: W24-01은 '지원 회사 10곳 리스트를 만들고 매핑표를 작성'하는 목표다. B형은 10곳 누락을 묻지만, A형은 매핑표만 시험한다. 10곳은 A형 답안에만 있고 문제와 채점표에는 없다. A형 (1)에 지원 리스트 규모와 매핑 단위를 넣고 채점표에 반영했다.

> 작성 메모: 근거: W24 핵심 개념·과제1·2·5·완료 기준, W22 과제5. 링크는 가상 예시 허용.

### P1-120 (0.10점) — 목표: W23-04, W23-09, W23-10

**모범 답안**

(1) 예: '2인 협동에서 스프린트 시 캐릭터가 뒤로 튕기는 러버밴딩 문제가 있었고, 지연 200ms PIE로 재현해 클라는 즉시 빨라지는데 서버는 RPC 도착 후 빨라져 서버가 위치를 보정함을 확인했습니다. 정석 해결(SavedMove 플래그 CMC 커스텀)을 TS에 기록하고 W21 딥다이브 C에서 구현했으며, 이후 이동 관련 값은 RPC로만 바꾸지 않는 것을 규칙으로 삼았습니다.' 틀: 문제 → 원인을 좁힌 방법 → 확인한 원인 → 해결 → 규칙화.
(2) 문제: AI 답안을 눈으로 외우면 내 말이 아니고 소리 내어 말해 본 적이 없어 막힌다. 고침(AI-Off): AI 없이 내가 답변 스크립트 작성 → 소리 내어 녹음 → 다시 들으며 수정(길이·결론 먼저·근거·막히는 곳).
(3) 문제: 답을 AI에게 받으면 AI 없는 실제 면접 연습이 되지 않는다. 규칙: AI 면접관 모드로 내 코드에 대한 꼬리 질문만 받고, 답은 AI 없이 내가 한다(채점·짧은 보충만 받음). 3회 진행한다.

**채점표 (10점)**

- [4] 30초 버전(틀 순서와 핵심 원인·해결·규칙)
- [3] 암기 방식 문제 + 작성→녹음→다시 듣고 수정
- [3] 리허설 문제 + 질문만 AI·답은 AI 없이 3회

> 작성 메모: 근거: W23 핵심 개념·과제1(AI-Off)·과제2, 9장 TS 템플릿 '면접 30초 버전', 4장 면접관 모드 프롬프트.

### P1-121 (0.19점) — 목표: W13-26, W23-01, W23-12

**모범 답안**

1. ->는 포인터가 가리키는 객체의 멤버에 접근((*Mesh).와 같음), .은 객체(또는 참조) 자신의 멤버에 접근한다. C#은 참조 타입도 .만 쓴다.
2. 스택은 함수 지역 변수 영역으로, 함수가 끝나면 자동 해제되고 빠르지만 크기 제한이 있다. 힙은 new 등으로 동적 할당하고, 수명을 직접(또는 GC·스마트 포인터가) 관리하며 상대적으로 느리다.
3. C++엔 interface 키워드가 없어 순수 가상 함수만 가진 클래스로 표현하고, 다중 상속으로 여러 개를 구현한다. 멤버 변수·구현도 가질 수 있다.
4. 그 함수가 객체 상태를 바꾸지 않는다는 약속이다. const 객체·const 참조에서도 호출할 수 있고, 값을 바꾸면 컴파일 에러가 난다.
5. 호출마다 복사 비용이 든다. const 참조로 넘긴다(작은 int·float는 값 전달이 낫다).
6. TSharedPtr은 UObject가 아닌 일반 C++ 객체의 참조 카운팅에 쓴다. UObject는 GC가 관리하므로 UPROPERTY TObjectPtr(또는 TWeakObjectPtr)을 쓴다.
7. 두 객체가 서로를 shared로 가리키면 참조 카운트가 0이 되지 않아 누수가 생긴다. 한쪽을 weak으로 바꿔 끊는다.
8. Class Default Object. 클래스마다 엔진이 만들어 두는 기본값 템플릿 객체다. 새 인스턴스는 CDO 값을 복사해 시작하고, BP 기본값 편집은 CDO를 수정하는 것이다.
9. 부모의 처리(컴포넌트 BeginPlay 호출, 블루프린트 BeginPlay 이벤트 등)가 실행되지 않아, BP 이벤트가 안 불리는 것 같은 미묘한 버그가 생긴다.
10. UHT(Unreal Header Tool)는 리플렉션 매크로(UCLASS·UPROPERTY 등)를 읽어 .generated.h 코드를 생성한다. UBT(Unreal Build Tool)는 .Build.cs·.Target.cs를 바탕으로 모듈 의존성과 빌드를 조율한다.

**채점표 (10점)**

- [5] 1~5번 문항, 각 1점(핵심어가 맞으면 1점, 절반이면 0.5점)
- [5] 6~10번 문항, 각 1점(핵심어가 맞으면 1점, 절반이면 0.5점)

> 검토에서 고친 점: 설계표 covers W23-01은 '질문 은행 전체(주차별 자가 점검 + 일반 질문)'인데, B형 10문항에는 일반 질문이 하나도 없다. A형은 10번 static이 일반 질문이다. 그래서 B형은 목표 일부를 시험하지 않고, 두 형의 구성(C++ 7 + UE 코어 2 + 일반 1 / C++ 7 + UE 코어 3)도 다르다. B형 10번을 질문 은행의 일반 질문 'UHT와 UBT'로 바꿔 구성을 맞췄다.

> 작성 메모: 두 형 모두 W1~W12 C++·UE 코어 자가 점검 질문(커리큘럼 8장 질문 은행에 연결된 문항)과 일반 질문(A형 10번 static)에서 뽑았다. 정답 기준은 각 주차 접힌 답이다. 9점 이상이면 W23 완료 기준('질문 은행 90% 이상')에 맞는 수준으로 본다. 0점·0.5점 문항은 채점자가 오답 노트 대상으로 표시하고, 응시자는 시험 뒤 '질문 / 내 답 / 틀린 이유 / 올바른 답' 형식으로 정리한다(W13 과제1 방식). 실제 운영에서 문항을 무작위로 뽑을 때도 A·B형 사이에 겹치는 문항이 없게 한다.

### P1-950 (0.19점) — 목표: W21-16

**모범 답안**

채점 기준(A~E 공통): ① 온라인·액션 회사 추천은 C. C면 네트워크 예측·러버밴딩 해결 역량으로, 다른 주제면 인정 후 전이 역량(측정 기반 검증, 소스 근거 분석, 도구로 팀 생산성 등)으로 연결한다. ② 이슈 분해(5개 이내)와 만든 것/분석한 것이 구체적이다. ③ 신뢰 근거: 같은 조건 여러 번 측정한 중간값, 지연 200ms 전후 비교 영상, 엔진 소스 파일·함수, 리포트·PR 링크 중 해당 항목을 구체적으로 든다. ④ AI 활용 범위(설계 질문·초안·리뷰 등)와 직접 검증(F12·소스·측정·테스트·AI가 틀렸던 사례)을 구분한다. ⑤ 아직 증명하지 못한 범위(예: 손실 조건, 확장 기능)를 솔직하게 말한다. 2분 안이고 '왜 했고 무엇을 증명했나'에 답한다.

**채점표 (10점)**

- [2] ① 고른 이유 + 온라인 액션 회사와의 연결(추천과 다르면 인정·전이 역량)
- [2] ② 이슈 분해와 해결한 문제·결과
- [2.5] ③ 결과의 신뢰 근거(반복 측정·전후 비교·소스)와 링크
- [1.5] ④ AI에 맡긴 것과 직접 검증한 것, 검증 방법
- [2] ⑤ 한계·다음 단계 + 2분 분량 준수

> 작성 메모: 근거: W21 자가 점검 질문(커리큘럼 수정으로 추가). 학생마다 고른 주제(A~E)가 다르므로 A~E 공통 채점 기준을 쓴다. 두 형은 '연결해야 할 회사 유형'과 '꼬리 질문 초점'을 다르게 해, 한 형의 답을 외워도 다른 형에 그대로 쓸 수 없게 했다. 실제 딥다이브 내용의 사실 여부는 3부 실기·구술과 대조할 것.

## 2부 코딩테스트

### P2-01 (0.36점) — 목표: W01-33, W01-35, W01-36, W01-37, W01-38, W01-39, W01-40, W04-33

**모범 답안**

[풀이]
1줄은 S / 60과 S % 60. 2줄은 (double)S / L을 cout << fixed; cout.precision(3);으로 출력한다(정수 나눗셈이면 .000, float면 2억대에서 틀림). 3줄은 N / 100, N / 10 % 10, N % 10. 4줄은 세 숫자 합을 3.0으로 나눠 같은 precision(3)으로 출력한다. 시간 복잡도 O(1).

[모범 코드]
#include <iostream>
using namespace std;

int main() {
    int s, l, n;
    cin >> s >> l >> n;
    cout << s / 60 << ' ' << s % 60 << '\n';
    cout << fixed;
    cout.precision(3);
    cout << (double)s / l << '\n';
    int a = n / 100, b = n / 10 % 10, c = n % 10;
    cout << a << ' ' << b << ' ' << c << '\n';
    cout << (a + b + c) / 3.0 << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 2줄을 s / l(정수 나눗셈)로 계산 → 1241.000
- float 사용 → 테스트 3에서 285714272.000
- 4줄을 (a + b + c) / 3(정수)로 → 0.333 대신 0.000
- S = 0, 0이 든 번호 100
- 1줄을 S / L로 착각(분·초 변환은 60 기준)

[채점 테스트]
테스트 1 입력
3725 3
246
기대 출력
62 5
1241.667
2 4 6
4.000

테스트 2 입력
0 1
100
기대 출력
0 0
0.000
1 0 0
0.333

테스트 3 입력
2000000000 7
999
기대 출력
33333333 20
285714285.714
9 9 9
9.000

**채점표 (10점)**

- [2] 채점 테스트 1(일반값) 출력 일치 — 4줄 중 맞은 줄마다 0.5점
- [3] 채점 테스트 2(작은 경계: S = 0, 0이 든 번호) 출력 일치 — 맞은 줄마다 0.75점
- [3] 채점 테스트 3(큰 경계: S = 20억, float·정수 나눗셈이면 틀림) 출력 일치 — 맞은 줄마다 0.75점
- [1] 파일 끝 주석에 직접 넣어 본 경계 입력 2개(최소 쪽·최대 쪽)와 VS 콘솔 출력이 적혀 있고, 그 출력이 실제 정답과 같음
- [1] 'P2-01-레이스-기록.cpp' 이름으로 제출 저장소에 커밋

> 작성 메모: A/B 차이: 나누는 수(P 변수 / 60 고정 + L), 자릿수 개수와 출력 순서(4자리 역순 / 3자리 정순), 소수 자릿수(4·2 / 3·3). 반올림이 애매한 값(…5로 끝나는 이진 정확값)은 MSVC와 gcc 결과가 갈릴 수 있어 예제·테스트에서 모두 피했다. W01-33의 'Ctrl+F5 예제 확인'은 직접 관찰할 수 없어 파일 끝 경계 입력 주석(W01-40)과 커밋 이름으로 간접 채점한다. W01-35(뼈대·cout)·W01-36(cin)은 테스트 통과에 포함된다.

### P2-02 (0.36점) — 목표: W02-25, W02-26, W02-27, W02-28

**모범 답안**

[풀이]
경보 단계는 >= 35 → >= 25 → >= 10 → >= 0 → 나머지 순서로 if / else if 사슬을 만든다(음수 구간이 마지막). 축제 연도는 y % 3 == 0 && (y % 10 != 0 || y % 8 == 0) — 괄호가 없으면 Y = 8처럼 3의 배수가 아닌데 8의 배수인 해를 YES로 잘못 판정한다. 시각은 (h*60 + m) - (a*60 + b)를 계산해 음수이면 1440을 더한다(a*60 + b ≤ 1439라 한 번이면 충분). 시간 복잡도 O(1).

[모범 코드]
#include <iostream>
using namespace std;

int main() {
    int temp, y, h, m, a, b;
    cin >> temp >> y >> h >> m >> a >> b;
    if (temp >= 35) cout << "HEAT" << '\n';
    else if (temp >= 25) cout << "WARM" << '\n';
    else if (temp >= 10) cout << "MILD" << '\n';
    else if (temp >= 0) cout << "COLD" << '\n';
    else cout << "FREEZE" << '\n';
    if (y % 3 == 0 && (y % 10 != 0 || y % 8 == 0)) cout << "YES" << '\n';
    else cout << "NO" << '\n';
    int t = (h * 60 + m) - (a * 60 + b);
    if (t < 0) t += 24 * 60;
    cout << t / 60 << ' ' << t % 60 << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 경계값 35·10·0에서 > 사용, 음수 기온을 COLD로 처리
- 괄호 없는 복합 조건(Y = 8)
- 시간과 분을 따로 빼서 분이 음수일 때 시를 안 내림
- 0시 0분에서 1분 전 → 23 59

[채점 테스트]
테스트 1 입력
10
2040
10 0 3 45
기대 출력
MILD
YES
6 15

테스트 2 입력
35
8
0 0 0 1
기대 출력
HEAT
NO
23 59

테스트 3 입력
0
24
0 10 23 59
기대 출력
COLD
YES
0 11

**채점표 (10점)**

- [3] 채점 테스트 1(경계 10, 연도 2040, 일반 시각) — 단계·연도·시각 줄마다 1점
- [3.5] 채점 테스트 2(경계 35, 괄호가 없으면 틀리는 연도 8, 0시 0분의 1분 전) — 단계 1점, 연도 1.5점, 시각 1점
- [3.5] 채점 테스트 3(경계 0, 연도 24, 23시간 59분 전 음수 보정) — 단계 1점, 연도 1점, 시각 1.5점

> 작성 메모: 두 형 모두 괄호를 빼면 오답이 되는 연도를 테스트 2에 넣었다(A: 7, B: 8 — 셋째 조건이 첫째 조건에 포함되지 않도록 설계). A는 분 단위 K, B는 'a시간 b분'을 분으로 바꾸는 단계가 하나 더 있지만 등급 구간이 A 4개 / B 5개(음수 포함)라 난이도를 맞췄다. W02-25(if/else if/else 비교)는 등급 판정 줄로 채점한다.

### P2-03 (0.36점) — 목표: W02-29, W03-29, W03-30, W03-31

**모범 답안**

[풀이]
T를 먼저 읽고 for (int k = 1; k <= T; ++k)로 탑마다 처리한다. 탑 하나는 바깥 for = 줄 번호 i, 안쪽 for 두 개 = '.' N−i개와 '*' 2i−1개를 찍는 이중 for다. 출력이 최대 110만 줄이므로 ios::sync_with_stdio(false); cin.tie(nullptr);와 '\n'을 쓴다(endl은 줄마다 버퍼를 비워 느리다). 시간 복잡도 O(ΣN²), 최대 약 1,600만 글자.

[모범 코드]
#include <iostream>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int t;
    cin >> t;
    for (int k = 1; k <= t; ++k) {
        int n;
        cin >> n;
        cout << '[' << k << ']' << '\n';
        for (int i = 1; i <= n; ++i) {
            for (int j = 0; j < n - i; ++j) cout << '.';
            for (int j = 0; j < 2 * i - 1; ++j) cout << '*';
            cout << '\n';
        }
    }
    return 0;
}

[놓치기 쉬운 경우]
- endl 사용 또는 동기화 해제 누락 → 테스트 3에서 시간 초과가 날 수 있고, 코드 확인 항목에서 감점
- '*' 개수를 2i+1이나 i로 계산
- 오른쪽에도 '.'을 채움(줄 끝 불일치)
- 탑 번호 줄 누락

[채점 테스트]
테스트 1 입력
3
4
1
2
기대 출력
[1]
...*
..***
.*****
*******
[2]
*
[3]
.*
***

테스트 2 입력
1
10
기대 출력
[1]
.........*
........***
.......*****
......*******
.....*********
....***********
...*************
..***************
.*****************
*******************

테스트 3 입력(생성)
첫 줄 100000, 이어서 10을 100,000줄.
기대 출력: k = 1 … 100000마다 '[k]' 한 줄과 테스트 2의 그림 10줄. 총 1,100,000줄(약 16.3MB). 1초 안에 끝나야 한다.

[코드 확인 항목]
(1) 첫 입출력보다 앞에 ios::sync_with_stdio(false);와 cin.tie(nullptr);가 둘 다 있다.
(2) 프로그램 어디에도 endl이 없고, 줄바꿈을 '\n'으로만 출력한다.
테스트 3의 1초 제한만으로는 채점 서버 성능에 따라 endl을 쓴 풀이도 통과할 수 있다. 그래서 W03-30(빠른 입출력)은 이 두 항목으로 따로 채점한다. 테스트 3은 대량 출력이 정확한지와 시간 안에 끝나는지만 본다.

**채점표 (10점)**

- [2.5] 채점 테스트 1(탑 3개, 번호 줄 포함) 출력 일치
- [2.5] 채점 테스트 2(최대 층수 N = 10) 출력 일치
- [3] 채점 테스트 3(T = 100,000, 출력 110만 줄)을 시간 제한 1초 안에 통과 — 시간 초과나 출력 불일치는 0점
- [1] 코드 확인: 첫 입출력보다 앞에 ios::sync_with_stdio(false);와 cin.tie(nullptr);를 둘 다 설정했다(하나라도 없으면 0점)
- [1] 코드 확인: 프로그램 어디에도 endl을 쓰지 않고 '\n'으로 줄을 바꿨다

> 검토에서 고친 점: W03-30(빠른 입출력)을 테스트 3의 1초 제한에만 맡겼다. endl을 쓴 풀이가 시간 초과가 나는지는 채점 서버 성능에 따라 달라서, 작성자도 '확인 필요'로 남겨 두었다. 서버가 빠르면 빠른 입출력을 쓰지 않아도 만점이 나와 목표가 평가되지 않는다. 문제에 채점 항목임을 밝히고, 설정 코드와 줄바꿈 방식을 코드 확인 2점으로 따로 채점하도록 바꿨다(테스트 배점 10→8).

> 작성 메모: 확인 필요: endl만 쓴 풀이가 테스트 3에서 실제로 시간 초과가 나는지는 채점 서버 입출력 성능에 따라 다르다. 채점 전에 endl 버전과 '\n' + 동기화 해제 버전을 같은 서버에서 재어 시간 제한(1초)이 둘을 가르는지 확인하고, 가르지 못하면 T 상한이나 시간 제한을 조정한다. A는 i개, B는 2i−1개로 안쪽 반복 횟수 식만 다르다.

### P2-04 (0.36점) — 목표: W03-32, W03-33, W04-32

**모범 답안**

[풀이]
한 줄에 c와 h가 함께 오므로 cin >> c[i] >> h[i]로 두 vector에 나눠 담는다. 최댓값·최솟값의 시작값은 h[0]으로 둔다(0으로 두면 모두 음수이거나 모두 양수일 때 틀림). 체크포인트 번호는 0부터 50,000까지이므로 bool seen[50001]로 처음 나온 번호만 센다. 출력은 최댓값이 먼저다. 시간 복잡도 O(N).

[모범 코드]
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

bool seen[50001];

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int n;
    cin >> n;
    vector<int> c(n), h(n);
    for (int i = 0; i < n; ++i) cin >> c[i] >> h[i];
    int hi = h[0], lo = h[0];
    for (int x : h) {
        hi = max(hi, x);
        lo = min(lo, x);
    }
    int kinds = 0;
    for (int x : c) {
        if (!seen[x]) {
            seen[x] = true;
            ++kinds;
        }
    }
    cout << hi << ' ' << lo << '\n' << kinds << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 시작값을 0으로 둠(테스트 1: 모두 음수, 테스트 2: 모두 양수)
- 번호 0을 빼고 1부터 셈, 배열 크기를 50000으로 잡아 번호 50,000에서 범위 초과(테스트 1)
- 출력 순서를 최솟값 먼저로 씀
- 입력을 저장하지 않고 받으면서 바로 계산(답이 맞아도 코드 확인 항목 0점)

[채점 테스트]
테스트 1 입력
5
10 -8
20 -3
10 -15
50000 -1000000000
20 -2
기대 출력
-2 -1000000000
3

테스트 2 입력
5
0 9
0 1000000000
0 7
0 3
0 11
기대 출력
1000000000 3
1

테스트 3 입력(생성)
N = 100000. i = 1 … 100000번째 줄에 c = (i − 1) % 25001, h = −i(i가 홀수) 또는 i(i가 짝수).
기대 출력
100000 -99999
25001

[코드 확인 항목]
c와 h를 vector<int>에 모두 저장한 뒤, 그 vector를 범위 기반 for나 인덱스로 순회해 최댓값·최솟값과 체크포인트 수를 구했는지 본다. 입력을 받으면서 바로 갱신하고 값을 저장하지 않았거나 일반 배열만 썼다면, 테스트를 통과했어도 이 항목은 0점이다.

**채점표 (10점)**

- [2.5] 채점 테스트 1(모두 음수, −10억 포함, 체크포인트 번호 50,000) — 1줄 1.5점, 2줄 1점
- [3] 채점 테스트 2(모두 양수, 10억 포함, 체크포인트 0만) — 1줄 1.5점, 2줄 1.5점
- [3.5] 채점 테스트 3(N = 100,000, 번호 0·25,000 포함, 시간 안) — 1줄 1.5점, 2줄 2점
- [1] 코드 확인: c와 h를 vector<int>에 모두 저장한 뒤 그 vector를 순회해 답을 구했다. 저장하지 않고 입력 중에 바로 계산했거나 일반 배열만 썼다면 0점.

> 검토에서 고친 점: W03-32(vector<int>에 저장하고 순회)를 채점하지 않았다. 문제에는 'vector에 저장한 뒤 처리' 조건이 있지만 채점표에는 없다. 최솟값·최댓값과 서로 다른 값의 개수는 입력을 받으면서 바로 계산할 수 있어서, vector를 전혀 쓰지 않아도 만점이 나온다. 그래서 조건을 채점 항목으로 밝히고 코드 확인 1점을 추가했다. B형은 '배열 크기 50000으로 번호 50,000에서 범위 초과'를 놓치기 쉬운 경우로 들면서도 그 번호가 나오는 테스트가 없었다. 테스트 1에 체크포인트 50,000을 넣어 A형(판매자 번호 100,000)과 맞췄다. 기대 출력은 그대로다.

> 작성 메모: 'vector에 저장' 조건은 테스트로 가려지지 않아 점수에 넣지 않았다(필요하면 코드 확인 감점 항목으로 추가 가능). A는 두 줄로 나뉜 배열 입력, B는 한 줄에 두 값이 섞인 입력에 0번 포함·최댓값 먼저 출력으로 바꿨다.

### P2-05 (0.36점) — 목표: W04-34, W04-35, W04-36, W05-34

**모범 답안**

[풀이]
S를 string으로 받는다(최대 100자리). 1은 s[s.size() − K](뒤에서 1번째가 s[s.size() − 1]). 2는 for (char c : s)로 c − '0'을 더한다. 3은 x = 1 … M을 to_string(x)로 바꿔 find("13") == string::npos인 수를 센다. 시간 복잡도 O(|S| + M × 자릿수).

[모범 코드]
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s;
    int k, m;
    cin >> s >> k >> m;
    cout << s[s.size() - k] << '\n';
    int sum = 0;
    for (char c : s) sum += c - '0';
    cout << sum << '\n';
    int cnt = 0;
    for (int x = 1; x <= m; ++x) {
        if (to_string(x).find("13") == string::npos) ++cnt;
    }
    cout << cnt << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- s[s.size() − K − 1] 또는 s[K − 1](앞에서 셈)
- S를 정수로 받음(100자리에서 실패), c를 그대로 더함
- '들어 있는' 수를 셈(반대 조건)
- 1부터가 아니라 0부터 셈

[채점 테스트]
테스트 1 입력
9876543210
10
1000
기대 출력
9
45
980

테스트 2 입력
(첫 줄: '1' 뒤에 '0' 98개, 마지막에 '1'을 이어 쓴 길이 100 문자열)
1
1000000
기대 출력
1
2
950599

테스트 3 입력
00000
3
1
기대 출력
0
0
1

**채점표 (10점)**

- [3] 채점 테스트 1(K = 길이, 즉 맨 앞 글자) — 글자·자릿수 합·개수 줄마다 1점
- [4] 채점 테스트 2(길이 100 문자열, M = 1,000,000) — 글자 1점, 자릿수 합 1.5점, 개수 1.5점
- [3] 채점 테스트 3(0만 있는 번호, M = 1) — 줄마다 1점

> 작성 메모: A는 앞에서 K번째·'77 포함' 개수, B는 뒤에서 K번째·'13 미포함' 개수로 인덱스 계산과 조건 방향을 바꿨다. 기대 출력 45739, 950599는 참조 구현으로 계산했다(채점 전 모범 코드로 한 번 더 생성 권장).

### P2-06 (0.71점) — 목표: W05-31, W05-32, W05-33, W05-35, W23-13

**모범 답안**

[풀이]
(1) 3중 for(i < j < k)로 모든 조합을 보며 DigitSum(b[i] + b[j] + b[k]) == S인 개수를 센다. O(N³).
(2) 9병 상자 개수 big을 P / 9부터 0까지 줄여 가며 P − 9·big이 5로 나누어떨어지는 첫 경우에 big + 나머지/5가 최소(9병 상자를 더 쓸수록 상자 수가 준다). 모든 경우를 다 보고 최솟값을 골라도 정답. 9병 상자를 P / 9개 쓰고 한 번만 확인하면 P = 10, 20처럼 틀린다. O(P).

[모범 코드]
#include <iostream>
#include <vector>
using namespace std;

int DigitSum(int x) {
    int s = 0;
    while (x > 0) {
        s += x % 10;
        x /= 10;
    }
    return s;
}

int main() {
    int n, target;
    cin >> n >> target;
    vector<int> b(n);
    for (auto& x : b) cin >> x;
    int p;
    cin >> p;
    int ways = 0;
    for (int i = 0; i < n; ++i)
        for (int j = i + 1; j < n; ++j)
            for (int k = j + 1; k < n; ++k)
                if (DigitSum(b[i] + b[j] + b[k]) == target) ++ways;
    cout << ways << '\n';
    int ans = -1;
    for (int big = p / 9; big >= 0; --big) {
        int rest = p - 9 * big;
        if (rest % 5 == 0) {
            ans = big + rest / 5;
            break;
        }
    }
    cout << ans << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 같은 카드를 두 번 고르거나 순서만 다른 조합을 중복으로 셈(i < j < k 아님)
- 한 번만 나누는 탐욕(P = 20에서 -1)
- 불가능할 때 0 출력

[채점 테스트]
테스트 1 입력
6 9
9 18 27 36 45 54
20
기대 출력
17
4

테스트 2 입력(생성)
N = 100, S = 20, b_i = (i × 991) % 100000 + 1 (i = 1 … 100, 즉 992 1983 2974 … 99101), P = 100000
기대 출력
8496
11112

테스트 3 입력
3 45
99999 99999 99999
1
기대 출력
1
-1

**채점표 (10점)**

- [3] 채점 테스트 1 — (1) 1.5점, (2) 1.5점(한 번만 나누는 탐욕이면 -1이 되는 P = 20)
- [3] 채점 테스트 2(N = 100, P = 100,000) — (1) 1.5점, (2) 1.5점
- [3] 채점 테스트 3(합 299,997, 담을 수 없는 P = 1) — (1) 1.5점, (2) 1.5점
- [1] 자릿수 합을 별도 함수로 분리해 3중 for 안에서 호출함(코드 확인)

> 작성 메모: A는 조합 중 최댓값, B는 조건을 만족하는 조합 개수로 바꿨고, 최소 개수 탐색은 A 7·4 / B 9·5로 숫자를 바꿨다(두 경우 모두 '큰 단위 개수를 바꿔 가며 전부 시도'가 필요하고 한 번만 나누는 탐욕은 테스트 1·2에서 틀린다). W23-13(모의고사형 완전탐색 Lv.1)은 같은 기법인 '모든 후보 대입'으로 대신 채점한다.

### P2-07 (0.71점) — 목표: W06-19, W06-20, W06-21, W06-22, W06-23, W06-24, W22-11

**모범 답안**

[풀이]
① pair는 첫 값부터 비교되므로 정렬 기준인 가격을 first에 둔 pair<int,int>(p, f)를 만들어 sort하고, 출력할 때 second(층) → first(가격) 순으로 쓴다.
② 람다 [](const string& a, const string& b){ if (a.size() != b.size()) return a.size() < b.size(); return a > b; }로 sort한 뒤 erase(unique(...), end())로 중복 제거.
③ 가격 복사본을 sort해 [N / 2].
④ 가격 vector의 [i−1, j) 구간을 복사해 greater<int>()로 내림차순 정렬 후 [k−1](또는 오름차순 정렬 후 [길이 − k]).
⑤ sort(W.begin(), W.end(), greater<char>()).
시간 복잡도 O(N log N).

[모범 코드]
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <functional>
using namespace std;

int main() {
    int n;
    cin >> n;
    vector<pair<int, int>> pf(n);
    vector<int> price(n);
    vector<string> names(n);
    for (int i = 0; i < n; ++i) {
        int f, p;
        cin >> names[i] >> f >> p;
        pf[i] = {p, f};
        price[i] = p;
    }
    int qi, qj, qk;
    cin >> qi >> qj >> qk;
    string tag;
    cin >> tag;

    sort(pf.begin(), pf.end());
    for (auto& x : pf) cout << x.second << ' ' << x.first << '\n';

    sort(names.begin(), names.end(), [](const string& a, const string& b) {
        if (a.size() != b.size()) return a.size() < b.size();
        return a > b;
    });
    names.erase(unique(names.begin(), names.end()), names.end());
    for (auto& s : names) cout << s << '\n';

    vector<int> sorted = price;
    sort(sorted.begin(), sorted.end());
    cout << sorted[n / 2] << '\n';

    vector<int> part(price.begin() + qi - 1, price.begin() + qj);
    sort(part.begin(), part.end(), greater<int>());
    cout << part[qk - 1] << '\n';

    sort(tag.begin(), tag.end(), greater<char>());
    cout << tag << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- pair를 (층, 가격)으로 만들어 층 기준으로 정렬됨
- 사전 역순을 a < b로 씀, unique 후 erase 누락
- ④를 k번째로 싼 가격으로 계산

[채점 테스트]
테스트 1 입력
7
bow 4 250
staff 1 900
ring 2 250
bow 1 80
orb 3 900
cape 2 10
gem 5 80
2 6 2
potion
기대 출력
2 10
1 80
5 80
2 250
4 250
1 900
3 900
orb
gem
bow
ring
cape
staff
250
900
tpooni

테스트 2 입력
9
zz 7 5
aa 7 1000000
zz 7 5
mm 7 1
aa 3 5
bb 1 5
mm 7 1000000
yy 2 1
bb 9 999
1 9 9
zyxzyx
기대 출력
2 1
7 1
1 5
3 5
7 5
7 5
9 999
7 1000000
7 1000000
zz
yy
mm
bb
aa
5
1
zzyyxx

테스트 3 입력
11
cab 10 7
abc 2 7
ba 10 3
abcd 2 9
cab 1 100
b 50 1
a 1 100
abc 2 7
zz 10 3
abce 1 99
c 50 9
3 9 4
qwertyasdf
기대 출력
50 1
10 3
10 3
2 7
2 7
10 7
2 9
50 9
1 99
1 100
1 100
c
b
a
zz
ba
cab
abc
abce
abcd
7
7
ywtsrqfeda

**채점표 (10점)**

- [2.5] ① (가격, 층) pair 정렬 후 '층 가격' 출력 — 테스트 3개 중 맞은 테스트마다 1/3
- [3] ② 람다 기준 정렬 + unique 중복 제거 — 테스트마다 1/3
- [1] ③ 정렬 후 중앙값 — 테스트마다 1/3
- [2.5] ④ 입력 순서 구간 i~j에서 k번째로 비싼 가격 — 테스트마다 1/3
- [1] ⑤ greater<char>() 내림차순 — 테스트마다 1/3

> 작성 메모: 설계표의 소문항(중앙값·내림차순·K번째 수)을 ③④⑤로 한 프로그램에 넣었다. ④는 W22-11(프로그래머스 K번째수)과 같은 기법을 백준형 입력으로 바꾼 것. A는 pair를 입력 순서 그대로, B는 순서를 뒤집어 만들어야 하고(가격 우선), 람다 기준·K번째 방향도 A와 반대로 바꿔 외운 코드로는 풀 수 없게 했다.

### P2-08 (0.71점) — 목표: W07-28, W07-29, W07-30, W07-31, W21-12

**모범 답안**

[풀이]
① vector<string> byNum(번호 → 이름)과 unordered_map<string,int> toNum(이름 → 번호)으로 양방향을 만들고, 문자열 질의는 toNum.count(s)로 존재부터 확인(평균 O(1)). 첫 글자가 숫자면 stoi(또는 c − '0' 누적)로 번호를 만든다.
② set<string>에 +는 insert, −는 erase. rbegin()부터 돌며 공백으로 이어 한 줄에 출력.
③ map<string,int> cnt: 주문은 ++, 배달 완료는 --, 값이 남은 메뉴가 답.
빠른 입출력 사용. 시간 복잡도 O((N + M + Q + K) log) 이하.

[모범 코드]
#include <iostream>
#include <string>
#include <vector>
#include <unordered_map>
#include <set>
#include <map>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int n, m, q;
    cin >> n >> m >> q;
    vector<string> byNum(n + 1);
    unordered_map<string, int> toNum;
    for (int i = 1; i <= n; ++i) {
        cin >> byNum[i];
        toNum[byNum[i]] = i;
    }
    set<string> bag;
    for (int i = 0; i < m; ++i) {
        string op, name;
        cin >> op >> name;
        if (op == "+") bag.insert(name);
        else bag.erase(name);
    }
    for (int i = 0; i < q; ++i) {
        string s;
        cin >> s;
        if (s[0] >= '0' && s[0] <= '9') cout << byNum[stoi(s)] << '\n';
        else if (toNum.count(s)) cout << toNum[s] << '\n';
        else cout << "UNKNOWN" << '\n';
    }
    if (bag.empty()) cout << "NOTHING";
    for (auto it = bag.rbegin(); it != bag.rend(); ++it) {
        if (it != bag.rbegin()) cout << ' ';
        cout << *it;
    }
    cout << '\n';
    int k;
    cin >> k;
    map<string, int> cnt;
    for (int i = 0; i < k; ++i) {
        string s;
        cin >> s;
        cnt[s]++;
    }
    for (int i = 0; i < k - 1; ++i) {
        string s;
        cin >> s;
        cnt[s]--;
    }
    for (auto& p : cnt) {
        if (p.second > 0) {
            cout << p.first << '\n';
            break;
        }
    }
    return 0;
}

[놓치기 쉬운 경우]
- 미등록 이름을 toNum[s]로 바로 조회 → 0 출력
- 이름 선형 검색 → 테스트 3 시간 초과
- ②를 줄마다 출력하거나 끝에 공백을 남김, 비었을 때 NOTHING 누락
- ③을 set으로 처리해 같은 메뉴 여러 건을 놓침

[채점 테스트]
테스트 1 입력
6 7 6
ruby
opal
jade
onyx
pearl
amber
+ jade
+ amber
+ ruby
- jade
+ onyx
+ jade
- amber
pearl
2
gold
6
onyx
4
6
tea
mocha
latte
tea
mocha
tea
mocha
tea
latte
tea
mocha
기대 출력
5
opal
UNKNOWN
amber
4
onyx
ruby onyx jade
tea

테스트 2 입력
5 5 6
x
y
z
xy
yx
+ yx
+ x
+ xy
+ z
+ y
1
xy
x1
5
z
zz
2
m
n
n
기대 출력
x
4
UNKNOWN
yx
3
UNKNOWN
z yx y xy x
m

테스트 3 입력(생성)
N = M = Q = K = 100000. 도감 i번 이름 = 'item' + i. 기록: '+ item1' … '+ item70000'(70000줄), 이어서 '- item1' … '- item30000'(30000줄). 질의 q = 1 … 100000: q가 짝수면 숫자 q, q % 4 == 1이면 'item' + q, q % 4 == 3이면 'zz' + q. 주문: m1 … m99999 다음에 m50505 한 번 더, 배달 완료: m1 … m99999.
기대 출력: 질의 100000줄(q 짝수 → itemq, q % 4 == 1 → q, q % 4 == 3 → UNKNOWN), 이어서 한 줄 'item70000 item69999 … item30001'(40000개), 마지막 줄 m50505. 1초 안.

**채점표 (10점)**

- [4] ① 질의 답(번호→이름, 이름→번호, 미등록 UNKNOWN) — 테스트 1·2 각 1점, 테스트 3(10만 건, 시간 안) 2점
- [3] ② 남은 인벤토리 사전 역순 한 줄(set + erase, NOTHING 처리) — 테스트마다 1점
- [3] ③ 배달되지 않은 메뉴(같은 메뉴 여러 건, map 개수 세기) — 테스트마다 1점

> 작성 메모: 설계표 summary의 '의상형 소문항'은 이 문항 covers에 의상(조합 수) 목표가 없어 넣지 않고, 완주하지 못한 선수형(③)만 넣었다 — 설계표 확인 필요. W07-28의 'TSet과 연결해 설명'은 설명 채점이 summary에 없어 2부에서는 count() 사용과 시간 통과로만 본다(설명은 1부에서). 숫자 질의 변환은 stoi나 c − '0' 누적 모두 인정.

### P2-09 (0.71점) — 목표: W08-30, W08-31, W08-32, W08-33, W08-34, W21-13

**모범 답안**

[풀이]
① deque<int>로 명령을 그대로 옮긴다(head → push_front, tail → push_back, cuthead → front + pop_front, cuttail → back + pop_back). 비었으면 0. 빠른 입출력 필요.
② stack<char>: '{' '<'는 push, '}' '>'는 스택이 비었거나 top()이 짝이 아니면 NO, 맞으면 pop, 그 밖의 글자는 무시. 끝에 스택이 비어야 YES.
③ queue<int>에 1 … R을 넣고, front를 꺼내 기록한 뒤 k[id]번 '앞에서 꺼내 뒤로 push'(큐가 비면 중단). 연산 수 ≤ 11R.
시간 복잡도 O(N + Σ문자열 길이 + R).

[모범 코드]
#include <iostream>
#include <string>
#include <vector>
#include <deque>
#include <stack>
#include <queue>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int n;
    cin >> n;
    deque<int> dq;
    while (n--) {
        string cmd;
        cin >> cmd;
        if (cmd == "head") { int x; cin >> x; dq.push_front(x); }
        else if (cmd == "tail") { int x; cin >> x; dq.push_back(x); }
        else if (cmd == "cuthead") {
            if (dq.empty()) cout << 0 << '\n';
            else { cout << dq.front() << '\n'; dq.pop_front(); }
        }
        else if (cmd == "cuttail") {
            if (dq.empty()) cout << 0 << '\n';
            else { cout << dq.back() << '\n'; dq.pop_back(); }
        }
        else if (cmd == "length") cout << dq.size() << '\n';
        else if (cmd == "first") cout << (dq.empty() ? 0 : dq.front()) << '\n';
        else if (cmd == "end") cout << (dq.empty() ? 0 : dq.back()) << '\n';
    }
    int b;
    cin >> b;
    while (b--) {
        string s;
        cin >> s;
        stack<char> st;
        bool ok = true;
        for (char ch : s) {
            if (ch == '{' || ch == '<') st.push(ch);
            else if (ch == '}' || ch == '>') {
                char want = (ch == '}') ? '{' : '<';
                if (st.empty() || st.top() != want) { ok = false; break; }
                st.pop();
            }
        }
        if (!st.empty()) ok = false;
        cout << (ok ? "YES" : "NO") << '\n';
    }
    int r;
    cin >> r;
    vector<int> k(r + 1);
    queue<int> q;
    for (int i = 1; i <= r; ++i) {
        cin >> k[i];
        q.push(i);
    }
    bool first = true;
    while (!q.empty()) {
        int id = q.front();
        q.pop();
        cout << (first ? "" : " ") << id;
        first = false;
        for (int t = 0; t < k[id] && !q.empty(); ++t) {
            q.push(q.front());
            q.pop();
        }
    }
    cout << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 빈 열차에서 front()/pop 호출
- 글자를 닫는 괄호로 취급해 스택을 pop
- 괄호 종류 무시('{<}>'를 YES로 판정)
- ③에서 연 상자를 다시 줄에 넣거나, 회전을 열기 전에 함

[채점 테스트]
테스트 1 입력
14
tail 4
tail 6
head 1
length
cuttail
first
head 9
cuthead
end
length
cuthead
cuthead
cuttail
length
6
{}<>
x{y<z}w>
<{}{}>
{{{}}}
<<>
}{
5
1 2 3 0 4
기대 출력
3
6
1
9
4
2
1
4
0
0
YES
NO
YES
YES
NO
NO
1 3 4 5 2

테스트 2 입력
8
cuthead
cuttail
first
end
length
head 1000000
cuttail
length
6
>
ab<>cd
{<>}<{}>
}<{
zzz
<<<<<<<<<<>>>>>>>>>>
3
10 10 10
기대 출력
0
0
0
0
0
1000000
0
NO
YES
YES
NO
YES
YES
1 2 3

테스트 3 입력(생성)
N = 500000: 'head 1' … 'head 250000' 다음에 'cuthead' 250000줄. B = 1, 문자열 'a{b}c'. R = 10000, k_i는 모두 10.
기대 출력: 250000부터 1까지 한 줄에 하나(250000줄), YES, 마지막 줄은 모범 코드로 생성한 10000개 순서(시작 '1 12 23 34 45 56 67 78 89 100 111 122 …', 끝 '… 7429 4052 2122 4012 6742'). 1초 안.

**채점표 (10점)**

- [4] ① 열차 명령 출력 — 테스트 1·2 각 1점, 테스트 3(50만 명령, 시간 안) 2점
- [3] ② 괄호 짝 판정(stack push·pop·top, 글자 무시) — 테스트마다 1점, 한 줄이라도 틀리면 그 테스트 0점
- [3] ③ 상자 연 순서(queue 회전 시뮬레이션) — 테스트마다 1점

> 작성 메모: W08-30(stack push·pop·top)은 괄호 종류를 top()으로 비교하는 ②로 채점한다. W08-32 queue의 front·pop은 ③, back에 해당하는 끝 확인은 ①의 last/end로 본다. ③은 설계표의 '기능개발·프로세스형 소문항'을 큐 회전 시뮬레이션(A: 라운드 로빈 수리, B: 숫자만큼 회전)으로 새로 만든 것이다. 빠른 입출력 채점 자체는 W03-30(P2-03) 몫이지만, ① 테스트 3은 빠른 입출력 없이는 시간 초과가 날 수 있다(서버 확인 필요).

### P2-10 (0.71점) — 목표: W09-31, W09-32, W09-33, W09-34, W09-35, W09-36

**모범 답안**

[풀이]
(1) 전역 string wall(4^N, '_')를 두고 Build(start, len, int& calls)를 재귀로 구현한다. ++calls를 하고, 길이가 1이면 '*'를 쓰고 return한다. 아니면 p = len / 4로 두고 start + p, start + 2p에 대해 재귀한다. 호출 수는 C(0) = 1, C(N) = 1 + 2·C(N−1)이므로 2^(N+1) − 1이다.
(2) Hanoi(K, 3, 1, 2): n−1개를 받침대 2로 옮기고, 1개를 3 → 1로 옮기고, n−1개를 2 → 1로 옮긴다.
(3) f(M) = 2·f(M−1) + 1을 long long으로 계산한다(1LL << M에서 1을 빼도 됨). M = 32 이상이면 2^M − 1이 int 최댓값 2,147,483,647을 넘어 오버플로가 난다.
시간 복잡도 O(4^N + 2^K + M).

[모범 코드]
#include <iostream>
#include <string>
using namespace std;

string wall;

void Build(int start, int len, int& calls) {
    ++calls;
    if (len == 1) {
        wall[start] = '*';
        return;
    }
    int p = len / 4;
    Build(start + p, p, calls);
    Build(start + 2 * p, p, calls);
}

void Hanoi(int n, int from, int to, int via) {
    if (n == 0) return;
    Hanoi(n - 1, from, via, to);
    cout << from << ' ' << to << '\n';
    Hanoi(n - 1, via, to, from);
}

long long MoveCount(int n) {
    if (n == 0) return 0;
    return 2 * MoveCount(n - 1) + 1;
}

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int n, k, m;
    cin >> n >> k >> m;
    int len = 1;
    for (int i = 0; i < n; ++i) len *= 4;
    wall = string(len, '_');
    int calls = 0;
    Build(0, len, calls);
    cout << wall << '\n' << calls << '\n';
    cout << MoveCount(k) << '\n';
    Hanoi(k, 3, 1, 2);
    cout << MoveCount(m) << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- calls를 값으로 넘김(2줄이 항상 1)
- 전역 카운터로 셈(2줄은 맞아도 코드 확인 항목 0점)
- 1·4번째 조각에 재귀(가운데가 아니라 바깥을 채움)
- 하노이 출발·도착을 1 → 3으로 씀
- (3)을 int로 계산(M = 32 이상에서 오버플로 → 테스트의 M = 33, 62에서 틀림)

[채점 테스트]
테스트 1 입력
2 3 12
기대 출력
_____**__**_____
7
7
3 1
3 2
1 2
3 1
2 3
2 1
3 1
4095

테스트 2 입력
8 1 33
기대 출력
1줄: 길이 65536 문자열('*' 256개, 앞 16384자는 모두 '_') — 모범 코드로 생성
511
1
3 1
8589934591

테스트 3 입력
3 14 62
기대 출력
_____________________**__**__________**__**_____________________
15
16383
(이동 16383줄 — 첫 줄 '3 2', 마지막 줄 '2 1', 모범 코드로 생성)
4611686018427387903

[코드 확인 항목]
Build가 호출 횟수를 int& 매개변수로 받아 누적하고, 그 횟수를 세는 전역 변수가 없는지 본다. 성벽 문자열(wall)은 전역이어도 된다. 전역 카운터로 셌다면 2줄이 맞아도 이 항목은 0점이다.

**채점표 (10점)**

- [2] 1줄 성벽 문자열(같은 모양으로 쪼개는 재귀) — 테스트마다 2/3점
- [1.5] 2줄 Build 호출 횟수 — 테스트마다 0.5점
- [0.5] 코드 확인: 호출 횟수를 int& 매개변수로 넘겨 누적했고, 그 횟수를 세는 전역 변수가 없다
- [3] 3줄 이동 횟수와 이동 순서 전체(하노이 분해) — 테스트마다 1점
- [3] 마지막 줄 M개 이동 횟수(long long) — 테스트마다 1점(M = 33, 62는 int면 틀림)

> 검토에서 고친 점: W09-34(참조 매개변수 int&로 재귀 호출 횟수 누적)를 출력으로는 구분할 수 없다. 전역 카운터로 세도 2줄이 맞으므로, 채점표의 '(int& 누적)' 괄호만으로는 채점자가 감점할지 정할 수 없다. 문제에 '호출 횟수는 참조 매개변수로 센다'는 조건을 넣고 코드 확인 0.5점을 분리했다(2줄 배점 2 → 1.5 + 0.5). B형 해설의 'M = 33 이상에서 int 오버플로'는 틀린 설명이다. 2^32 − 1 = 4,294,967,295가 이미 int 최댓값을 넘으므로 'M = 32 이상'으로 정정했다.

> 작성 메모: 칸토어(3등분)·하노이(1→3)를 그대로 외운 코드로는 풀리지 않게 A는 5등분·포탈 1→2, B는 4등분(가운데 둘)·받침대 3→1로 바꿨다. 호출 횟수는 문제에 정한 함수 규칙대로 셀 때만 정해지는 값이다. W09-33(두 갈래 호출 트리 추적)은 하노이 이동 순서 전체를 맞혀야 하는 3줄 항목으로 간접 채점한다. 하노이 깊이 최대 15라 스택 걱정 없음.

### P2-11 (1.07점) — 목표: W10-32, W10-33, W10-34, W10-36

**모범 답안**

[풀이]
캐릭터 코드를 vector<char>로 받아 sort한 뒤:
① 순열: 재귀 + bool used[]로 고르고 → 재귀 → 되돌리기.
② 조합: 시작 인덱스를 넘겨 i = start부터, 재귀는 Comb(i + 1).
③ 중복 수열: used 없이 매번 처음부터.
(2) op[4](+, −, ×, % 남은 개수)를 상태로 들고 다니는 백트래킹. %는 C++ % 그대로(음수 왼쪽 값이면 결과도 음수).

[모범 코드]
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int n, m, k;
vector<char> code, pick;
vector<int> a;
bool used[6];
int op[4];
int best = -1000000000, worst = 1000000000;

void Print() {
    for (int i = 0; i < m; ++i) cout << pick[i] << (i + 1 < m ? ' ' : '\n');
}

void Perm() {
    if ((int)pick.size() == m) { Print(); return; }
    for (int i = 0; i < n; ++i) {
        if (used[i]) continue;
        used[i] = true;
        pick.push_back(code[i]);
        Perm();
        pick.pop_back();
        used[i] = false;
    }
}

void Comb(int start) {
    if ((int)pick.size() == m) { Print(); return; }
    for (int i = start; i < n; ++i) {
        pick.push_back(code[i]);
        Comb(i + 1);
        pick.pop_back();
    }
}

void Rep() {
    if ((int)pick.size() == m) { Print(); return; }
    for (int i = 0; i < n; ++i) {
        pick.push_back(code[i]);
        Rep();
        pick.pop_back();
    }
}

void Calc(int idx, int val) {
    if (idx == k) {
        best = max(best, val);
        worst = min(worst, val);
        return;
    }
    for (int o = 0; o < 4; ++o) {
        if (op[o] == 0) continue;
        op[o]--;
        int b = a[idx], nv;
        if (o == 0) nv = val + b;
        else if (o == 1) nv = val - b;
        else if (o == 2) nv = val * b;
        else nv = val % b;
        Calc(idx + 1, nv);
        op[o]++;
    }
}

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    cin >> n >> m;
    code.resize(n);
    for (auto& c : code) cin >> c;
    sort(code.begin(), code.end());
    cin >> k;
    a.resize(k);
    for (auto& x : a) cin >> x;
    for (int i = 0; i < 4; ++i) cin >> op[i];
    Perm(); cout << "--" << '\n';
    Comb(0); cout << "--" << '\n';
    Rep(); cout << "--" << '\n';
    Calc(1, a[0]);
    cout << best << '\n' << worst << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 코드를 정렬하지 않음
- 되돌리기 누락, 조합에서 start + 1로 넘김
- 최댓값 시작값 0(결과가 모두 음수일 때)
- %를 '양수 나머지'로 고쳐 계산 → 테스트 3 최댓값이 2250으로 틀림

[채점 테스트]
테스트 1 입력
4 2
D A C B
4
9 4 6 5
1 1 0 1
기대 출력
① 12줄: A B / A C / A D / B A / B C / B D / C A / C B / C D / D A / D B / D C
--
② 6줄: A B / A C / A D / B C / B D / C D
--
③ 16줄: A A / A B / A C / A D / B A / … / D D
--
10
-4

테스트 2 입력
5 3
Q M X K T
6
8 3 9 2 7 4
1 1 1 2
기대 출력(모범 코드로 생성)
① 60줄(첫 줄 'K M Q', 끝 줄 'X T Q'), --, ② 10줄(K M Q / K M T / K M X / K Q T / K Q X / K T X / M Q T / M Q X / M T X / Q T X), --, ③ 125줄(첫 줄 'K K K', 끝 줄 'X X X'), --, 32, -28

테스트 3 입력
6 6
F A E B D C
11
100 1 2 3 4 5 6 7 8 9 10
3 3 2 2
기대 출력(모범 코드로 생성)
① 720줄(첫 줄 'A B C D E F', 끝 줄 'F E D C B A'), --, ② 1줄 'A B C D E F', --, ③ 46656줄(첫 줄 'A A A A A A', 끝 줄 'F F F F F F'), --, 2070, -1890

**채점표 (10점)**

- [2.5] ① 순열(visited 백트래킹) — 테스트 3개 중 맞은 테스트마다 1/3
- [2] ② 조합(시작 번호 매개변수) — 테스트마다 1/3
- [2] ③ 중복 수열(visited 없음) — 테스트마다 1/3
- [3.5] ④ 최댓값·최솟값(남은 연산자 개수를 상태로 들고 다니는 백트래킹) — 테스트마다 1/3, 두 값 모두 맞아야 인정

> 작성 메모: A는 정수 번호·÷, B는 문자 코드·%로 바꿨다. 테스트의 중간값 범위(±10억 이내)는 참조 구현으로 전수 확인했다. A 테스트 2는 ÷를 내림으로 구현하면 최댓값이 40 → 32로, B 테스트 3은 %를 양수 나머지로 구현하면 최댓값이 2070 → 2250으로 달라져 C++ 기본 연산을 그대로 써야 맞는다. 출력이 길어(최대 약 47,000줄) 큰 테스트의 기대 출력은 모범 코드로 생성한다.

### P2-12 (1.07점) — 목표: W11-24, W11-25, W11-26, W11-27, W11-28, W21-14

**모범 답안**

[풀이]
인접 리스트 vector<int> adj[1001]에 양방향으로 넣고 각 리스트를 sort(…, greater<int>())로 내림차순 정렬한다.
① 재귀 Dfs(u): od[u] = ++cnt → 인접 v 중 od[v] == 0이면 Dfs(v). 방문 순서 번호 배열 자체가 visited 역할.
② queue: ob[S] = ++cnt2로 시작, 꺼낸 역의 인접 역 중 ob == 0이면 번호를 매기고 push. 예제 1처럼 DFS(1 3 4 2)와 BFS(1 3 2 4)의 순서가 달라진다.
③ DFS에서 매긴 번호의 최댓값(cnt).
④ 미방문 역에서 탐색을 새로 시작할 때마다 + 1.
⑤ 재귀 Target(i, sum, minus): +c_i는 항상, −c_i는 minus < X일 때만 뻗는다(빼기 횟수를 상태로 들고 다님). 2^20 ≈ 100만 번.
시간 복잡도 O(N + E log E + 2^L).

[모범 코드]
#include <iostream>
#include <vector>
#include <queue>
#include <algorithm>
#include <functional>
using namespace std;

vector<int> adj[1001];
int od[1001], ob[1001], cntD = 0;
bool visC[1001];
int L, X, T, ways = 0;
vector<int> c;

void Dfs(int u) {
    od[u] = ++cntD;
    for (int v : adj[u])
        if (od[v] == 0) Dfs(v);
}

void Mark(int u) {
    visC[u] = true;
    for (int v : adj[u])
        if (!visC[v]) Mark(v);
}

void Target(int i, int sum, int minus) {
    if (i == L) {
        if (sum == T) ++ways;
        return;
    }
    Target(i + 1, sum + c[i], minus);
    if (minus < X) Target(i + 1, sum - c[i], minus + 1);
}

int main() {
    int n, e, s;
    cin >> n >> e >> s;
    for (int i = 0; i < e; ++i) {
        int u, v;
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    for (int i = 1; i <= n; ++i) sort(adj[i].begin(), adj[i].end(), greater<int>());

    Dfs(s);
    for (int i = 1; i <= n; ++i) cout << od[i] << (i < n ? ' ' : '\n');

    int cntB = 0;
    queue<int> q;
    ob[s] = ++cntB;
    q.push(s);
    while (!q.empty()) {
        int u = q.front();
        q.pop();
        for (int v : adj[u]) {
            if (ob[v] == 0) {
                ob[v] = ++cntB;
                q.push(v);
            }
        }
    }
    for (int i = 1; i <= n; ++i) cout << ob[i] << (i < n ? ' ' : '\n');

    cout << cntD << '\n';

    int comp = 0;
    for (int i = 1; i <= n; ++i) {
        if (!visC[i]) {
            ++comp;
            Mark(i);
        }
    }
    cout << comp << '\n';

    cin >> L >> X >> T;
    c.resize(L);
    for (auto& x : c) cin >> x;
    Target(0, 0, 0);
    cout << ways << '\n';
    return 0;
}

[놓치기 쉬운 경우]
- 오름차순 정렬(외운 코드 그대로) → ①② 모두 틀림
- 방문 순서 목록을 그대로 출력(역별 번호가 아니라)
- BFS에서 꺼낼 때 번호를 매김(순서는 같아도 중복 push 위험)
- ③에서 S를 빼먹음, ④에서 고립된 역 누락
- ⑤에서 빼기 횟수 제한을 무시(테스트 1·3에서 틀림)

[채점 테스트]
테스트 1 입력
8 8 3
3 8
3 1
1 5
5 8
8 2
2 6
4 7
1 3
4 2 0
4 1 2 3
기대 출력
4 5 1 0 3 6 0 2
3 5 1 0 4 6 0 2
6
2
2

테스트 2 입력
10 10 1
1 2
2 3
3 4
4 5
5 6
6 7
7 8
8 9
9 10
10 1
20 20 0
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
기대 출력
1 10 9 8 7 6 5 4 3 2
1 3 5 7 9 10 8 6 4 2
10
1
184756

테스트 3 입력
7 2 4
1 2
3 5
20 3 1000
10 20 30 40 50 60 70 80 90 100 110 120 130 140 150 160 170 180 190 200
기대 출력
0 0 0 1 0 0 0
0 0 0 1 0 0 0
1
5
2

**채점표 (10점)**

- [2.5] 1줄 DFS 역별 방문 번호(내림차순 인접 + 재귀) — 테스트 3개 중 맞은 테스트마다 1/3
- [2.5] 2줄 BFS 역별 방문 번호(queue) — 테스트마다 1/3
- [1] 3줄 출발역과 연결된 역 수(S 포함) — 테스트마다 1/3
- [1.5] 4줄 무리(연결 요소) 수 — 테스트마다 1/3
- [2.5] 5줄 빼기 횟수 제한이 있는 방법 수(재귀 탐색) — 테스트마다 1/3

> 작성 메모: A는 오름차순 방문·순서 목록 출력·S 제외·3갈래 타겟형, B는 내림차순 방문·역별 방문 번호 출력·S 포함·빼기 횟수 상태가 붙은 2갈래 타겟형으로 바꿨다. W11-28의 '방문 순서 차이 설명'은 2부에서 두 줄을 모두 맞히는 것으로 보고, 말로 하는 설명은 1부에서 채점한다. N ≤ 1,000이라 재귀 DFS 깊이가 VS 기본 스택(1MB)에서도 안전하다. 연결 요소 수(네트워크형)는 W11-27 목표의 확장으로 넣었다.

### P2-13 (1.07점) — 목표: W11-29, W12-28, W12-29, W12-31, W22-13

**모범 답안**

[풀이]
먼저 격자를 훑어 S와 E의 좌표를 찾는다.
① 방문하지 않은 '#'를 만날 때마다 개수를 1 늘리고, 그 칸에서 상하좌우 BFS/DFS로 이어진 '#'를 모두 방문 표시한다. 세는 대상이 나무라는 점에 주의한다.
② dist를 -1로 채우고 dist[S]=0으로 둔 뒤 BFS를 한다(dx[4], dy[4]). 다음 칸이 범위 안이고 '#'가 아니고 dist==-1이면 dist+1로 두고 push한다. 답은 dist[E] 그대로다(이동 횟수이므로 +1을 하지 않는다).
③ 같은 BFS를 나이트 8방향 배열로 돌리고 착지 칸만 검사한다. 답은 dist[E].

[시간 복잡도] O(RC) (③은 O(8RC)).

[놓치기 쉬운 경우]
- ①은 통로가 아니라 '#' 덩어리를 센다. 나무가 없으면 0이다.
- ②는 이동 횟수다. A형처럼 +1을 하면 오답이다.
- S와 E가 맞닿아 있으면 ②의 답은 1이다. 작은 지도에서는 나이트가 못 뛸 수 있다.
- 'S'와 'E' 칸도 지나갈 수 있는 칸으로 처리한다.
- BFS마다 dist를 새로 초기화하고, 배열에 접근하기 전에 범위를 검사한다.

[채점 테스트] (실제 입력에서는 ' / ' 자리가 줄바꿈이다)
T1 (S와 E가 이웃, 나이트 불가)
입력: 2 3 / SE# / ...
기대 출력: 1 / 1 / -1

T2 (숲 여러 개, 우회 경로)
입력:
5 6
S.#...
#.#.#.
..#.#.
.##.#.
....#E
기대 출력: 3 / 19 / 3

T3 (큰 지도, 시간 확인. 생성 규칙)
R=C=100이고 모든 칸이 '.'이다. 34번째 열은 1행만 빼고 모두 '#', 67번째 열은 100행만 빼고 모두 '#'이다. S는 (100,1), E는 (1,100)에 있다.
기대 출력: 2 / 396 / 66

**채점표 (10점)**

- [3] ① 숲('#' 덩어리) 개수가 T1·T2·T3에서 정답이다(테스트마다 1점). 시간 제한을 넘긴 테스트는 0점.
- [3.5] ② 썰매 최소 이동 횟수(갈 수 없으면 -1)가 정답이다. T1·T2 각 1점, T3 1.5점.
- [3.5] ③ 스쿠터(나이트) 최소 점프 횟수(갈 수 없으면 -1)가 정답이다. T1·T2 각 1점, T3 1.5점.

> 작성 메모: 2부-A, weight 3(권장 풀이 시간 약 14분). 출력 3줄을 줄 단위로 채점해 일부만 풀어도 부분 점수를 받는다. 이 문항은 백준 2667·1012·2178·7562와 프로그래머스 1844(게임 맵 최단거리)에서 쓰는 기법을 쓰지만 문장·데이터는 새로 만들었다(예제를 가져오지 않음). 모든 예제와 테스트의 기대 출력은 별도로 만든 참조 풀이로 계산하고 검증했다. 두 형의 차이: A형은 통로('1') 덩어리를 세고 ②를 칸 수(+1)로 답한다. B형은 나무('#') 덩어리를 세고 ②를 이동 횟수로 답한다. 시작점과 도착점 위치 방식도 다르다. 확인 필요 사항 없음.

### P2-14 (0.71점) — 목표: W12-30, W12-32

**모범 답안**

[풀이]
점검 1: 1차원 BFS다. dist[0..L]을 -1로 채우고 dist[N]=0으로 둔다. x를 꺼내 nx가 x-1, x+1, 2*x 중 하나이고 0 ≤ nx ≤ L이며 미방문이면 dist[x]+1로 두고 push한다. 답은 dist[K]다.
점검 2: 시작점이 여러 개인 BFS다. 모든 'P'를 dist=0으로 처음에 한꺼번에 push하고, 이웃이 'h'이며 미방문일 때만 퍼뜨린다. 끝난 뒤 'h' 중 미방문이 있으면 -1, 없으면 최댓값을 낸다('h'가 없으면 0).

[시간 복잡도] O(L) + O(RC).

[놓치기 쉬운 경우]
- 상한이 100,000으로 정해져 있지 않고 입력 L이다. 예제 1처럼 4→8→16→15(3초)는 16 > L이라 쓸 수 없어서 답이 4다. 상한을 무시하면 틀린다.
- 2×X 계산값을 배열 크기(L+1)와 먼저 비교한 뒤 접근한다.
- N ≥ K이면 N-K, N=K이면 0.
- 'x'는 전기가 통하지 않는다. 발전소끼리 떨어져 있어도 처음에 모두 큐에 넣는다.
- 'h'가 처음부터 없으면 0, 고립된 'h'가 있으면 -1.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1 (뒤로만 이동, 집 없음)
입력: 5 5 0 / 1 3 / xPx
기대 출력: 5 / 0

T2 (상한이 답을 바꾸는 경우)
입력:
99 25 99
4 5
Phhxh
xxhxh
hhhxh
hxhhh
기대 출력: 4 / 10 (상한을 무시하면 1번째 줄이 3이 되어 오답)

T3 (큰 입력. 생성 규칙)
첫 줄은 99999 2 99999, 둘째 줄은 500 500이다. 격자는 모두 'h'이고 (250,250) 칸만 'P'다.
기대 출력: 22 / 500

**채점표 (10점)**

- [5] 1번째 줄(범위 [0,L] 안의 +1·-1·×2 1차원 BFS)이 정답이다. T1 1점, T2 2점, T3 2점.
- [5] 2번째 줄(발전소 전체를 시작점으로 하는 BFS 복구 시간, 0/-1 처리 포함)이 정답이다. T1 1점, T2 2점, T3 2점. T3는 시간 제한 안에 끝나야 한다.

> 작성 메모: 2부-A, weight 2(권장 약 9분). 한 프로그램이 두 이벤트를 차례로 처리하고 답을 두 줄로 내므로 줄 단위로 부분 점수를 준다. 백준 1697·7576의 기법을 쓰지만 이야기와 데이터는 새로 만들었다. A형은 위치 상한이 100,000으로 정해져 있다. B형은 상한 L이 입력으로 주어지고, 상한 때문에 답이 달라지는 테스트(T2)를 넣었다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-15 (0.71점) — 목표: W13-29, W13-30, W13-31, W13-32, W24-07

**모범 답안**

[풀이]
1. C = Y - X로 두고, 주어진 순서(큰 것부터)로 cnt += C / B[i]; C %= B[i];를 한다. 근거는 배수 관계다. 큰 동전 1개를 작은 동전으로 바꾸면 개수가 늘기만 한다.
2. t를 오름차순으로 정렬한다. 대기 합에 '지금까지의 누적 합'을 먼저 더하고, 그다음 누적 합에 자기 시간을 더한다(자기 시간은 자기 대기에 들어가지 않는다). 근거: 앞사람의 시간은 뒤에 있는 모든 사람의 대기에 더해지므로 짧은 순서가 최선이다.
3. e = s + d를 계산해 (e, s)로 담고, e 오름차순, 같으면 s 오름차순으로 sort한다. s ≥ end이면 선택한다. 근거는 회의실 배정과 같다. 같은 e에서 s가 작은 것을 먼저 봐야 [3,4) 뒤의 [4,4)를 놓치지 않는다. s+d는 최대 20억이라 int에 들어간다.
4. 문자를 읽으며 num = num*10 + (c - '0')으로 수를 만든다. 앞자리 0은 이 계산에서 자연히 사라진다. 처음 '-'가 나온 뒤의 수는 모두 뺀다.
5. has 배열로 잃어버림(-1)과 여분(+1)을 반영한다. 번호가 작은 사람부터, has[i]==0이면 앞(i-1)의 여분을 먼저, 안 되면 뒤(i+1)의 여분을 빌린다.

[시간 복잡도] 정렬 O(P log P + Q log Q), 나머지는 선형이다.

[놓치기 쉬운 경우]
- 1번은 Y가 아니라 차액 Y-X다. 차액이 0이면 0이다.
- 2번은 A형(ATM형)과 달리 자기 시간을 빼야 한다. 손님이 1명이면 0이다.
- 3번에서 입력이 (시작, 길이)이므로 끝 시각을 직접 계산해야 한다. 끝 시각만으로 정렬하면 T2에서 6이 아니라 5가 나온다.
- 4번에서 '-0'처럼 0인 수도 정상 처리한다. 식을 '-' 기준으로만 나누면 앞자리 0이 있는 경우 등에서 실수하기 쉽다.
- 5번: 자기 여분을 쓰는 사람을 빌려주는 쪽으로 잘못 처리하면 예제 2가 5로 나온다.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1 (가장 작은 경우)
입력: 1 3 10 / 1 / 1 / 9 / 1 / 5 0 / 00042 / 3 1 1 / 3 / 3
기대 출력: 7 / 0 / 1 / 42 / 3

T2
입력:
5 2345 10000
5000 1000 100 20 1
6
8 3 3 10 1 5
7
5 0
2 3
5 0
3 1
4 1
5 2
7 0
100+050-020+030-0+10
7 3 3
1 5 7
2 5 6
기대 출력: 26 / 44 / 6 / 90 / 7

T3 (큰 입력. 생성 규칙)
동전은 512 256 128 64 32 16 8 4 2 1, X=1, Y=100000000이다. P=1000이고 t는 1000 999 … 1이다. Q=100000이고 i번째 이벤트(i=1..Q)는 '2(Q-i) 2'다. 식은 0001-2+3-4+5-6+7-8+9-10+11이다. n=30, L=10이며 잃어버린 사람은 21~30번, R=3이며 여분이 있는 사람은 20 21 30번이다.
기대 출력: 195320 / 166666500 / 100000 / -64 / 22

**채점표 (10점)**

- [1] 1번째 줄(최소 동전 수)이 T1~T3에서 맞은 비율만큼 점수를 준다(최대 1점).
- [1] 2번째 줄(포장 전 대기 시간 합의 최솟값)이 T1~T3에서 맞은 비율만큼 점수를 준다(최대 1점).
- [2] 3번째 줄(이벤트 최대 개수)이 T1~T3에서 맞은 비율만큼 점수를 준다(최대 2점). T3는 시간 제한 안에 끝나야 한다.
- [1.5] 4번째 줄(식의 최솟값)이 T1~T3에서 맞은 비율만큼 점수를 준다(최대 1.5점).
- [1.5] 5번째 줄(우산 대여, 체육복형)이 T1~T3에서 맞은 비율만큼 점수를 준다(최대 1.5점).
- [1] 주석 (a): 큰 동전부터 쓰는 것이 최선인 이유를 배수 관계로 설명했다.
- [1] 주석 (b): 2번의 정렬 기준(포장 시간이 짧은 순)과 근거를 적었다.
- [1] 주석 (c): 3번의 정렬 기준(끝 시각 = s+d 오름차순, 같으면 시작 시각 오름차순)과 근거를 적었다. 기준만 적고 근거가 없으면 0.5점.

> 작성 메모: 2부-A, weight 2. 하위 문제가 5개라 하나하나는 10줄 안팎으로 작게 만들었다(합쳐서 약 10~15분). 설계표 요약대로 정렬 기준과 그 근거를 주석으로 적는지를 3점 채점한다. 각 하위 문제가 덮는 목표는 다음과 같다. 1→W13-29(동전), 2→W13-30(ATM), 3→W13-31(회의실), 4→W13-32(잃어버린 괄호), 5→W24-07(체육복형). 백준 11047·11399·1931·1541과 프로그래머스 42862의 기법을 쓰지만 이야기·입력 형식·수치는 새로 만들었다. B형은 거스름돈(차액) 계산, '자기 차례 전까지의' 대기 시간, (시작, 길이) 형식, 앞자리 0이 붙은 식으로 바꿨다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-16 (1.07점) — 목표: W14-32, W14-33, W14-34, W14-35, W14-36, W24-08

**모범 답안**

[풀이]
1부분: sort한 뒤 binary_search로 판정하고, 결과를 공백으로 이어 한 줄에 출력한다(lo/hi/mid로 직접 구현해도 인정).
2부분(최댓값형): x를 정렬한다. 판정 함수 can(d)는 '첫 위치에 설치한 뒤, 마지막 설치 위치에서 d 이상 떨어진 첫 후보마다 설치해서 C개 이상 설치되는가'다. lo=1, hi=x[H-1]-x[0]으로 두고, 참이면 ans=mid, lo=mid+1, 거짓이면 hi=mid-1이다.
3부분(최솟값형): 판정 함수 ok(T)는 '앞에서부터 담다가, 더하면 T를 넘을 때 다음 날로 넘겨서 필요한 날 수가 D 이하인가'다. lo=max(p_i), hi=모든 p_i의 합(long long, 최대 10^14)으로 두고, 참이면 ans=mid, hi=mid-1, 거짓이면 lo=mid+1이다.

[시간 복잡도] 1부분 O((N+M) log N). 2부분 O(H log H + H log 10^9). 3부분 O(S log 10^14).

[놓치기 쉬운 경우]
- 2부분에서 위치를 정렬하지 않으면 판정이 틀린다(입력이 정렬되어 있지 않다).
- 3부분의 lo를 0이나 1로 두면, 한 스테이지가 T보다 긴 경우를 판정 함수가 처리하지 못해 오답이 난다. lo는 가장 긴 스테이지 시간이다(T2: D=S일 때 답은 최댓값 9).
- 3부분의 합과 답은 int를 넘는다(예제 2의 30억). 누적 변수와 lo, hi, mid는 long long이다.
- 1부분은 한 줄 출력이다. 줄마다 출력하면 형식 오류다.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1 (가장 작은 경우)
입력: 1 1 / -1000000000 / 1000000000 / 2 2 / 0 1 / 1 1 / 1000000000
기대 출력: 0 / 1 / 1000000000

T2 (중복, 정렬 안 된 위치, D=S)
입력:
6 5
5 -5 5 12 0 -12
-5 12 7 0 -12
7 3
30 2 17 9 25 40 11
6 6
5 9 2 8 4 7
기대 출력: 1 1 0 1 1 / 15 / 9

T3 (큰 입력. 생성 규칙)
N=M=100000이고 a_i = 3(i-1), q_j = j-1이다. H=200000, C=100000이고 x_i = 5000(i-1)이다. S=100000, D=3이고 모든 p_i = 1000000000이다.
기대 출력: 첫째 줄은 100000개 값이며 j번째 값은 (j-1)이 3의 배수면 1, 아니면 0이다. 둘째 줄 10000, 셋째 줄 33334000000000.

**채점표 (10점)**

- [3] 1부분(한 줄에 M개의 0/1)이 정답이다. T1 0.5점, T2 1점, T3 1.5점. T3는 시간 제한 안에 끝나야 한다.
- [3.5] 2부분(가장 가까운 두 방어탑 거리의 최댓값)이 정답이다. T1 0.5점, T2 1.5점, T3 1.5점.
- [3.5] 3부분(가장 긴 날 플레이 시간의 최솟값)이 정답이다. T1 0.5점, T2 1.5점, T3 1.5점.

> 작성 메모: 2부-A, weight 3(권장 약 14분). 세 부분이 덮는 목표는 다음과 같다. 1부분: W14-32 sort + binary_search(직접 구현해도 인정). 2·3부분: W14-33 lo/hi/mid 직접 구현, W14-35 판정 함수, W14-36 long long. 2부분: W14-34 '최댓값'형. 3부분: W24-08 '최솟값'형. A형 3부분은 입국심사형이다. B형 3부분은 같은 이분 탐색 Lv.3 유형인 '최대 합의 최소화'로 바꿔서, A형 코드를 외워도 그대로 쓸 수 없게 했다. 백준 1654·2110의 예제 수치는 쓰지 않았다. 기대 출력은 참조 풀이(큰 정수 연산)로 검증했다. 확인 필요 사항 없음.

### P2-17 (1.07점) — 목표: W15-18, W15-19, W15-20, W15-21, W15-22, W16-32

**모범 답안**

[풀이]
1. 카운터를 단 Stair를 실제로 호출한다(a ≤ 25이면 최대 약 147만 번). 또는 C(n)=1 (n ≤ 3), C(n)=1+C(n-1)+C(n-2)+C(n-3)으로 계산한다. ② 실행 횟수는 a ≥ 4이면 a-3, 아니면 0이다.
2. long long dp로 dp[i] = (dp[i-1] + dp[i-2] + dp[i-3]) % 1000000007을 매번 적용한다.
3. c일째에 새로 자라는 나무 수는 c-4일째에 있던 나무 수와 같다. 그래서 G(c) = G(c-1) + G(c-4)이고 G(1..4)=1이다. long long을 쓴다(G(70)부터 int를 넘는다).
4. cur = max(v_i, cur + v_i), best = max(best, cur)로 계산하고, 초기값은 첫 원소다.
5. d[1]=0이다. i=2..x에 대해 d[i]=d[i-1]+1로 두고, 짝수면 d[i/2]+1, 5의 배수면 d[i/5]+1과 비교해 최솟값을 넣는다.

[시간 복잡도] 2·5번 O(10^6), 3번 O(c), 4번 O(L).

[놓치기 쉬운 경우]
- 2번: 세 항 각각이 10^9 근처라 int로 합하면 30억이 되어 오버플로가 난다. long long을 쓰거나 두 항을 더할 때마다 나머지를 구한다.
- 3번은 int로 하면 c=70부터 틀린다(T2). 기저는 4개(1~4일)다.
- 4번은 모든 값이 음수일 때 가장 큰 음수가 답이다(예제 2).
- 5번에서 '나눌 수 있으면 나누기' 탐욕은 6(정답 2: 6→5→1), 26(정답 3: 26→25→5→1)에서 틀린다.
- 1번에서 a ≤ 3이면 ② 실행 횟수는 0이다.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1
입력: 3 / 1 / 5 / 1 / -1000 / 26
기대 출력: 1 0 / 1 / 2 / -1000 / 3

T2
입력: 25 / 1000000 / 70 / 10 / -3 6 -2 -5 7 1 -1 3 -12 8 / 1000000
기대 출력: 1468189 22 / 746580045 / 2489191330 / 10 / 12

T3 (큰 입력. 생성 규칙)
a=24, b=999999, c=100, L=100000이다. v_i는 i가 3의 배수면 -1000, 아니면 400이다. x=999999다.
기대 출력: 798238 21 / 71313044 / 39359646494758 / 800 / 24

**채점표 (10점)**

- [1.5] 1번째 줄(재귀 호출 횟수와 DP 반복 횟수)이 정답이다. T1·T2·T3 각 0.5점.
- [2] 2번째 줄(Stair(b) mod 1,000,000,007)이 정답이다. T1 0.5점, T2 0.75점, T3 0.75점.
- [2] 3번째 줄(나무 수열, long long)이 정답이다. T1 0.5점, T2 0.75점, T3 0.75점.
- [2] 4번째 줄(연속 구간 최대 합)이 정답이다. T1 0.5점, T2 0.75점, T3 0.75점.
- [2.5] 5번째 줄(÷5·÷2·-1 최소 연산 횟수)이 정답이다. T1 0.75점, T2 0.75점, T3 1점.

> 작성 메모: 2부-A, weight 3(권장 약 14분). 다섯 줄을 줄 단위로 채점한다. 각 줄이 덮는 목표는 다음과 같다. 1줄: W15-18(재귀와 DP의 호출 횟수 비교). 2줄: W15-19, W15-20(점화식과 나머지 연산). 3줄: W15-21(표에서 규칙을 찾아 점화식 세우기, long long). 4줄: W15-22(연속합). 5줄: W16-32(bottom-up 최소 연산). 수열은 파도반·피보나치가 아닌 a(n)=a(n-1)+a(n-3)(A형), g(n)=g(n-1)+g(n-4)(B형)이다. 최소 연산은 1463을 그대로 뒤집은 형태를 피해 연산 종류를 바꿨다. 탐욕이 실패하는 입력(A형 33, B형 26)을 T1에 넣었다. W15-18의 '설명'은 설계표 요약에 주석 요구가 없어서, 호출 횟수를 출력하는 것으로 채점한다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-18 (1.07점) — 목표: W16-29, W16-30, W16-31, W18-24, W18-25, W23-15

**모범 답안**

[풀이]
1. dp[i][c] = cost[i][c] + min(c가 아닌 색 c'에 대한 dp[i-1][c']), 색은 4개다. 답은 마지막 집의 4개 값 중 최솟값.
2. dp[i][j] = a[i][j] + max(위 왼쪽, 위 오른쪽)이고 양 끝은 한쪽만 쓴다. 답은 마지막 줄의 최댓값. 음수가 있으므로 최댓값의 초기값을 0으로 두면 안 된다.
3. (가) dp[i] = max(dp[i-2], dp[i-3] + s[i-1]) + s[i]이고 답은 dp[S]다. (나) dp[i] = max(dp[i-1], dp[i-2] + s[i], dp[i-3] + s[i-1] + s[i])다. 둘 다 dp[1]=s1, dp[2]=s1+s2.
4. dp[1][d]=1(d=1..9)로 두고, dp[len][d] = |d - e| ≥ 2인 모든 e에 대한 dp[len-1][e]의 합(매번 나머지 연산)이다. 답은 dp[L][0..9]의 합.

[시간 복잡도] O(16N + T² + S + 100L).

[놓치기 쉬운 경우]
- 2번: 음수 경로가 있으니 max의 초기값을 0으로 두면 T1(-8)과 예제 2(-100)가 틀린다.
- 1번: 색이 4개라 '다른 두 색 중 최소'로 고정해 둔 코드(3색용)는 틀린다.
- S=1, S=2일 때의 인덱스를 처리한다.
- (가)와 (나)의 차이(꼭대기 필수인지)는 예제 1의 64와 92처럼 답을 바꾼다.
- 4번: 9에서 다음 자리로 갈 수 있는 수는 0~7의 8개다. 경계 계산에 주의한다.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1 (가장 작은 경우, 음수 삼각형)
입력: 2 / 1 1 1 1 / 1 1 1 1 / 2 / -5 / -7 -3 / 1 / 777 / 1
기대 출력: 2 / -8 / 777 777 / 9

T2
입력:
5
6 2 9 4
3 8 1 7
2 9 6 1
8 4 3 5
1 7 9 2
5
-3
6 -8
-2 4 9
5 -7 -1 3
0 8 -6 2 -4
8
25 25 0 0 0 60 60 3
3
기대 출력: 8 / 14 / 113 170 / 463

T3 (큰 입력. 생성 규칙)
N=1000이고 집 i의 비용은 (i%7+1, 3i%11+1, 5i%13+1, 2i%5+1)이다. T=500이고 i번째 줄 j번째 값은 (i·j)%201 - 100이다. S=10000이고 s_k = 53k % 1000이다. L=100이다.
기대 출력: 2279 / 21466 / 3466896 3491640 / 457368683

**채점표 (10점)**

- [2.5] 1번째 줄(4색, 이웃 색 제약 최소 비용)이 정답이다. T1 0.5점, T2 1점, T3 1점.
- [2.5] 2번째 줄(음수를 포함한 삼각형 최대 경로 합)이 정답이다. T1 0.5점, T2 1점, T3 1점.
- [1.5] 3번째 줄 첫 값((가) 탑 층계, 계단형)이 정답이다. T1·T2·T3 각 0.5점.
- [1.5] 3번째 줄 둘째 값((나) 포션 진열대, 포도주형)이 정답이다. T1·T2·T3 각 0.5점.
- [2] 4번째 줄(dp[길이][마지막 숫자] 개수)이 정답이다. T1 0.5점, T2 0.5점, T3 1점.

> 작성 메모: 2부-A, weight 3(권장 약 14분). 각 줄이 덮는 목표는 다음과 같다. 1줄: W16-29. 2줄: W16-30, W23-15(정수 삼각형형). 3줄은 같은 배열로 두 규칙을 함께 묻는다. 첫 값은 W16-31(계단형), 둘째 값은 W18-25(포도주형, '이번 칸을 안 고르는 경우' 추가)다. 4줄: W18-24(dp[길이][마지막 숫자]). 백준 1932, 프로그래머스 43105, 2579·2156의 예제 수치는 쓰지 않았다. 두 규칙의 답이 서로 달라지는 배열을 예제와 T2에 넣었다. B형은 색이 4가지이고, 삼각형에 음수가 있으며, 자릿수 조건이 '차이가 2 이상'이다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-19 (1.07점) — 목표: W18-26, W18-27

**모범 답안**

[풀이]
1. dp[i]를 'i번째 원소로 끝나는 감소 부분 수열의 최대 길이'로 둔다. dp[i]=1로 시작해, j<i이고 a[j]>a[i]이면 dp[i]=max(dp[i], dp[j]+1)로 갱신한다. 답은 전체 dp의 최댓값이다.
2. 입력에서 '예산 B, 개수 M' 순서와 각 줄의 '데미지, 비용' 순서를 주의해 읽는다. 스킬마다 for (m = B; m >= c; m--) dp[m] = max(dp[m], dp[m - c] + d)를 한다. 답은 dp[B]다.
주석 모범: '마나를 큰 쪽부터 돌면 dp[m-c]는 아직 이번 스킬이 반영되지 않은 값이라, 스킬을 한 번만 쓴다. 작은 쪽부터 돌면 이번 스킬로 갱신한 값 위에 또 더해져 같은 스킬을 여러 번 쓰게 된다.'

[시간 복잡도] O(N²) + O(MB) = 최대 약 1,100만.

[놓치기 쉬운 경우]
- 부등호 방향(감소)과 '엄격히'(같은 값 불가)를 지킨다. 예제 1의 20, 20은 이어 붙일 수 없다.
- 입력 순서를 A형처럼 '개수 예산', '비용 가치'로 읽으면 전부 틀린다.
- 마나를 앞에서부터 갱신하면 T2가 200, T3가 116486으로 나온다.
- 비용이 예산보다 큰 스킬(T1)을 처리한다. 답은 전체 dp의 최댓값이다(dp[N-1]이 아님).

[채점 테스트] (' / ' 자리는 줄바꿈)
T1
입력: 1 / 1 / 1 1 / 1000 2
기대 출력: 1 / 0

T2
입력:
10
9 9 4 7 7 3 8 1 1 2
20 5
80 8
45 5
60 7
20 2
55 6
기대 출력: 4 / 185 (앞에서부터 갱신하면 200으로 오답)

T3 (큰 입력. 생성 규칙)
N=1000이고 a_i = (53i mod 1000) + 1이다. B=100000, M=100이고 스킬 i(1..100)는 d_i = 17i mod 1000, c_i = (991i mod 3000) + 500이다.
기대 출력: 26 / 34956

**채점표 (10점)**

- [4] 1번째 줄(엄격히 감소하는 부분 수열의 최대 길이)이 정답이다. T1 1점, T2 1.5점, T3 1.5점.
- [4] 2번째 줄(0/1 배낭 최대 데미지)이 정답이다. T1 1점, T2 1.5점, T3 1.5점.
- [2] 1차원 dp[마나]로 구현했고, 큰 쪽부터 갱신하는 이유(같은 스킬이 두 번 들어가지 않음)를 주석으로 정확히 적었다. 이유 없이 결론만 적으면 1점, 2차원 구현이면 0점.

> 작성 메모: 2부-A, weight 3(권장 약 14분). 설계표 요약대로 '무게를 뒤에서부터 갱신하는 이유'를 주석으로 쓰는지 2점 채점한다. T2와 T3는 무게를 앞에서부터 갱신하면 답이 달라지도록 만들었다(A형 T2: 180, T3: 55328 / B형 T2: 200, T3: 116486). 그래서 테스트만으로도 갱신 방향 오류를 잡아낸다. B형은 엄격히 감소하는 수열이고, 입력 순서가 '예산 개수', '데미지 비용'으로 A형과 반대라 코드를 그대로 옮기면 틀린다. 백준 11053·12865의 예제 수치는 쓰지 않았다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-20 (1.07점) — 목표: W17-23, W17-24, W17-25, W17-26

**모범 답안**

[풀이]
1부분: 비교 구조체를 쓴 priority_queue<int, vector<int>, Cmp>다. P는 전역 변수로 둔다.
struct Cmp { bool operator()(int a, int b) const { int da = abs(a - P), db = abs(b - P); if (da != db) return da > db; return a < b; } };
(차이가 작은 것이 top이고, 같으면 레벨이 큰 것이 top이다.) (차이, -레벨)을 greater로 담는 방식도 인정한다.
2부분: 단방향 인접 리스트와 greater<pair<int,int>>를 쓴 최소 힙으로 다익스트라를 돌린다. dist가 INF인 정점 수와, INF가 아닌 dist의 최댓값을 출력한다.
3부분: 0-1 BFS다. 비용 w는 g[nx][ny]==g[x][y]이면 0, 아니면 1이다. 0이면 deque push_front, 1이면 push_back한다. 다익스트라도 인정한다.

[시간 복잡도] O(Q log Q) + O((V+E) log E) + O(RC).

[놓치기 쉬운 경우]
- 동점일 때 레벨이 '높은' 쪽이 먼저다(예제 1에서 60이 40보다 먼저). 빈 대기열이면 0이다.
- 도로가 단방향이라 역방향 간선을 넣으면 안 된다(T2: 6번 거점은 도달 불가).
- 같은 도로가 중복이어도 다익스트라는 자연히 처리한다. E=0일 수 있다(T1).
- 3부분 비용은 '다음 칸이 현재 칸과 같은 색인지'로 정한다. '#'처럼 특정 문자로 정해지지 않는다.
- 한 줄에 Q개 값이 오고 출력이 많으므로 빠른 입출력을 쓴다.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1
입력: 1 1000 / 0 / 1 0 1 / 2 2 / AA / AA
기대 출력: 0 / 0 0 / 0

T2 (동점, 중복 도로, 단방향 함정)
입력:
10 100
100 99 101 0 0 0 98 102 0 0
6 9 1
1 2 5
1 2 2
2 3 2
3 1 1
3 4 6
4 5 3
2 5 20
5 2 1
6 1 1
4 4
ABBA
ABBA
BAAB
BBAA
기대 출력: 100 / 101 / 99 / 102 / 98 / 13 1 / 2

T3 (큰 입력. 생성 규칙)
Q=100000, P=500이다. 앞의 50000개 값은 i=1..50000에 대해 (i mod 1000)+1이고, 뒤의 50000개는 모두 0이다. 배송망은 V=20000, E=14999, S=1이고, 도로는 i에서 i+1(i=1..14999)로 가는 길이 1000짜리다. 격자는 100×100이고, 1부터 센 좌표 (i,j)의 색은 'A' + ((⌊(i-1)/10⌋ + ⌊(j-1)/10⌋) mod 3)이다.
기대 출력: 1부분 50000줄은 500이 50번, 501이 50번, 499가 50번, 502가 50번, 498이 50번, … 순서로 이어지고, 999가 50번, 1이 50번, 마지막으로 1000이 50번 나온다. 이어서 '14999000 5000', 마지막 줄 18.

**채점표 (10점)**

- [3] 1부분(기준 레벨에 가까운 순서의 커스텀 우선순위 큐 출력 전부)이 정답이다. T1 0.5점, T2 1점, T3 1.5점. T3는 시간 제한 안에 끝나야 한다.
- [4] 2부분(다익스트라로 구한 최댓값과 도달 불가 수)이 정답이다. T1 1점, T2 1.5점, T3 1.5점. 두 값 중 하나만 맞으면 그 테스트 점수의 절반.
- [3] 3부분(같은 색 0, 다른 색 1인 최소 비용)이 정답이다. T1 0.5점, T2 1점, T3 1.5점.

> 작성 메모: 2부-A, weight 3(권장 약 14분). 각 부분이 덮는 목표는 다음과 같다. 1부분(커스텀 우선순위): W17-24. 2부분(다익스트라, 최소 힙 greater): W17-25, W17-23. 3부분(비용 0/1 격자, deque 0-1 BFS 또는 다익스트라): W17-26. 백준 1927·11286·1753·13549와 기법은 같지만 우선순위 규칙, 출력 형식(거리 D 이하인 정점 수, 가장 먼 거리와 도달 불가 수), 0/1 비용 규칙(벽 부수기, 색이 바뀌는 칸)은 새로 만들었다. W17-23(greater 지정)은 출력으로는 직접 구분되지 않는다. 다익스트라 부분의 정답과 시간 제한(최대 힙으로 잘못 구현하면 오답이거나 느림)으로 간접 확인하고, 구술에서 확인하기를 권장한다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-21 (0.71점) — 목표: W20-16

**모범 답안**

[풀이]
sum[0]=0, sum[i]=sum[i-1]+a[i]로 누적 합을 만든다. 질의마다 x > y이면 swap하고, 답은 sum[y] - sum[x-1]이다. 빠른 입출력을 쓴다.

[시간 복잡도] O(N+Q).

[놓치기 쉬운 경우]
- x > y인 질의를 그대로 계산하면 음수나 엉뚱한 값이 나온다(예제 1의 '4 2').
- 합의 최댓값은 10만×1만 = 10억이라 int 범위(약 21억) 안이다.
- 질의마다 반복문으로 더하면 T3에서 시간 초과다.

[채점 테스트] (' / ' 자리는 줄바꿈)
T1
입력: 1 1 / 0 / 1 1
기대 출력: 0

T2
입력:
8 5
7 0 0 3 10000 1 0 9
8 1
5 5
6 2
3 4
2 7
기대 출력: 10020 / 10000 / 10004 / 3 / 10004

T3 (큰 입력. 생성 규칙)
N=Q=100000이고 모든 a_i = 10000이다. k번째 질의(k=1..Q)는 'N-k+1 k'다.
기대 출력: k번째 줄은 (|N+1-2k| + 1) × 10000이다. 첫 줄 1000000000, 50000번째와 50001번째 줄 20000, 마지막 줄 1000000000.

**채점표 (10점)**

- [2] T1(원소 1개) 정답.
- [4] T2(x > y 질의 포함) 모든 줄 정답.
- [4] T3(N=Q=10만) 모든 줄 정답이고 시간 제한 1초 안에 끝난다(질의마다 O(1)로 처리해야 통과).

> 작성 메모: 2부-A, weight 2(권장 약 9분). 단일 기법 문항이다. T3는 N=Q=10만이라 질의마다 직접 더하면(O(NQ)=약 50억) 시간 초과가 난다. 그래서 누적 합을 썼는지가 테스트 점수로 드러난다. A형은 질의가 (시작, 길이) 형식이고 값에 음수가 있다. B형은 질의 두 수의 순서가 뒤바뀔 수 있다(작은 쪽이 시작). 합의 범위는 두 형 모두 int 안이다. 백준 11659의 예제는 쓰지 않았다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-22 (1.43점) — 목표: W19-19, W19-20, W19-21, W19-22, W21-11

**모범 답안**

[풀이 1-가]
d를 0=북, 1=동, 2=남, 3=서로 두고 시작은 d=0이다. "L"이면 (d+3)%4, "R"이면 (d+1)%4, "U"이면 (d+2)%4다. "F k"는 s[0]=='F'로 구분하고 k = s[2]-'0'이다.
주사위 f[6](0=위, 1=북, 2=동, 3=남, 4=서, 5=아래)의 처음 값은 {1,5,3,2,4,6}이다. 굴리는 식은 A형과 같은 면 교환이다(동: f[0]=f[4]; f[4]=f[5]; f[5]=f[2]; f[2]=t 등).
몸통은 deque와 occupied 배열로 관리한다. 막히면 바깥 반복까지 끝내야 하므로 플래그나 함수 return을 쓴다. 이동이 성공하면 moves++. 굴린 뒤 f[0]==6이면 꼬리를 유지하고, 아니면 pop_back과 occupied 해제를 한다.
[풀이 1-나]
방향을 N=0, E=1, S=2, W=3으로 둔다. 조건은 (a[j]+2)%4==a[j+1]이다. 왼쪽 전파는 rot[j]=rot[j+1], 오른쪽 전파는 rot[j]=rot[j-1](같은 방향)이다. 전부 정한 뒤 동시에 적용한다.

[시간 복잡도] 1-가 O(총 이동 수), 1-나 O(ops × K).

[놓치기 쉬운 경우]
- 시작 위치는 왼쪽 아래, 시작 방향은 북쪽이다. 주사위 처음 값이 A형과 다르다(북 5, 남 2).
- 성장 조건은 '윗면'이 6일 때다(아랫면이 아니다).
- "F k" 도중에 막히면 게임 전체가 끝난다. 다음 명령을 계속 처리하면 틀린다(예 2, T2).
- 길이 2 이상에서 "U" 뒤에 앞으로 가면 꼬리와 충돌한다(T2).
- 1-나: 즉시 적용하면 예 2가 "ESWN"으로 틀린다.

[채점 테스트]
1-가
T1: board = ["...", "...", "..."], commands = ["F 1", "U", "F 1"] → [2, 1] (길이 1이면 뒤로 돌아 이동 가능)
T2: board = ["...", "...", "..."], commands = ["F 2", "U", "F 1", "R", "F 1"] → [2, 2] (길이 2에서 뒤로 돌아 꼬리와 충돌하면 끝)
T3: board = ["......", "..#...", "......", "......"], commands = ["R", "F 5", "L", "F 3", "L", "F 5", "U", "F 2"] → [13, 3]
1-나
T1: turrets = "NN", ops = [[2,1]] → "NE"
T2: turrets = "NSNSNS", ops = [[3,1]] → "EWEWEW" (즉시 적용하면 "NSESNS")
T3: turrets = "SNSNEW", ops = [[1,-1],[6,1],[2,1]] → "WEWEWE" (즉시 적용하면 "EESNEN")

**채점표 (10점)**

- [2] 1-가 T1 정답(반환 두 값 모두 맞으면 2점, 하나만 맞으면 1점).
- [2] 1-가 T2 정답(뒤로 돌기 뒤 꼬리 충돌과 게임 종료. 두 값 모두 2점, 하나만 1점).
- [2] 1-가 T3 정답(두 값 모두 2점, 하나만 1점).
- [1] 1-나 T1 정답.
- [1.5] 1-나 T2 정답(회전을 먼저 모두 정한 뒤 적용).
- [1.5] 1-나 T3 정답(명령 여러 개의 연쇄).

> 작성 메모: 2부-B 실전 세트 1/3, weight 4(세트 120분 중 권장 약 45분). 시뮬레이션 기법 네 가지를 한 함수에 억지로 섞으면 규칙이 지나치게 복잡해진다. 그래서 함수 두 개로 나눴다. 1-가는 방향 회전, 주사위 면 교환, deque 몸통(W19-19·20·21)을, 1-나는 연쇄 회전을 먼저 모두 정한 뒤 한 번에 적용하기(W19-22, 방향 회전 재사용)를 다룬다. W21-11(3문제 2시간 AI 없이)은 세트 시간 안에 제출한 것만 채점하는 운영 조건으로 확인한다. 2부-B 공통 규칙: 세트 시작부터 120분 안에 커밋된 풀이만 채점한다. 백준 14503·14499·3190·14891과 기법은 같지만, 보드 규칙, 점수 규칙(A형 바닥면 합, B형 윗면 6이면 성장), 연쇄 조건(A형 같은 방향이면 반대로 회전, B형 마주 보면 같은 방향으로 회전)은 새로 만들었다. '즉시 적용' 오답이 걸리는 테스트를 넣었다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-23 (1.07점) — 목표: W20-17, W21-11, W23-11

**모범 답안**

[풀이]
1. d를 INF(long long 권장)로 채우고 d[i][i]=0으로 둔다. 항로마다 d[from][to] = min(d[from][to], cost)를 한다. 단방향이므로 반대쪽은 넣지 않는다.
2. 플로이드: k를 가장 바깥에 두고 i, j 순서로 3중 for를 돈다.
3. c = 1..n마다 i ≠ c인 모든 i에 대해 d[c][i]와 d[i][c]가 둘 다 INF가 아니면 v = d[c][i] + d[i][c]이고, 그 최댓값이 평가값이다. 하나라도 INF이면 c는 후보가 아니다. 평가값이 더 작을 때만 갱신한다.

[시간 복잡도] O(n³).

[놓치기 쉬운 경우]
- 양방향으로 넣으면 예 2가 [-1, -1]이 아니게 된다.
- 중복 항로를 덮어쓰면 T1이 [1, 15], T2가 [2, 11]로 틀린다(작은 값이 먼저 나온다).
- k를 안쪽에 두면 T3가 [-1, -1]로 틀린다.
- INF를 더할 때 오버플로가 나지 않게 한다. 평가값은 '최댓값'이고 판정은 '최솟값'이라는 두 단계를 헷갈리지 않는다.

[채점 테스트]
T1: n = 2, routes = [[1,2,3],[2,1,8],[1,2,7]] → [1, 11]
T2: n = 3, routes = [[1,2,5],[2,1,5],[2,3,2],[3,2,2],[3,2,9]] → [2, 10]
T3 (생성 규칙): n = 100이다. q_i = (53·i) mod 101 (i=1..100, 순열)로 두고, i=1..99마다 [q_i, q_(i+1), 1000]과 [q_(i+1), q_i, 3000]을 넣는다. → [24, 200000]

**채점표 (10점)**

- [2] T1 정답(중복 항로. 반환 두 값 모두 맞으면 2점, 하나만 맞으면 1점).
- [3.5] T2 정답(중복 항로와 단방향 처리. 두 값 모두 3.5점, 하나만 1.75점).
- [4.5] T3 정답(k를 가장 바깥에 둔 플로이드. 두 값 모두 4.5점, 하나만 2.25점). 세트 제한 시간 안에 커밋된 제출만 채점한다.

> 작성 메모: 2부-B 실전 세트 2/3, weight 3(권장 약 35분). 핵심 목표는 W20-17(k를 가장 바깥에 둔 플로이드)이다. T3는 정점 번호를 섞은 사슬 그래프라, k를 안쪽에 두면 답이 [-1, -1]로 바뀐다. 그래서 순서 오류를 테스트가 잡는다. T2는 중복 간선 중 작은 값이 먼저 나와서, 단순히 덮어쓰면 틀린다. W21-11·W23-11(제한 시간 안에 AI 없이 응시하고 기록)은 세트 운영 조건(120분 안 커밋)으로 확인하며, 기록은 P2-24 채점표에서 1점으로 채점한다. 백준 11404, 프로그래머스 합승 택시 요금·순위와 기법은 같지만, '모임 장소 합 최소'(A형)와 '왕복 시간 최대값 최소인 수도'(B형)는 새로 만든 응용이다. 기대 출력은 참조 풀이로 검증했다. 확인 필요 사항 없음.

### P2-24 (1.43점) — 목표: W20-18, W20-19, W23-11, W23-12

**모범 답안**

[풀이]
1. 빈칸 좌표 목록 E, 불 좌표 목록, 보물 좌표를 만든다.
2. 백트래킹으로 E 중 k개 조합을 고른다(시작 인덱스를 넘기는 방식). 고른 칸을 임시로 '#'로 바꾼다.
3. 모든 F를 dist=0으로 큐에 넣고 BFS를 한다('#'만 막힘). 보물의 dist가 -1이면 blocked=true로 표시하고, 아니면 best = max(best, dist[T])로 갱신한다.
4. 원래대로 되돌린 뒤 다음 조합을 본다. 끝나면 blocked이면 -1, 아니면 best를 반환한다.

[시간 복잡도] 빈칸 최대 약 62개 → C(62,3) ≈ 3.8만 조합 × BFS 64칸 → 약 250만.

[놓치기 쉬운 경우]
- 벽을 '정확히 k개' 세운다. k보다 적게 세우는 경우는 볼 필요가 없지만, 조합의 크기는 k로 맞춘다.
- 조합마다 세운 벽을 되돌리지 않으면 다음 경우가 오염된다.
- 불은 처음부터 모든 F에서 동시에 퍼진다(다중 시작점). 하나에서만 출발하면 틀린다.
- 최댓값을 찾는 문제지만, 보물에 닿지 않는 경우가 하나라도 있으면 -1이 우선한다.
- 불이 보물 바로 옆에서 시작하면 벽으로 늦출 수 없다(T1은 1).

[채점 테스트]
T1: grid = ["FT", ".."], k = 1 → 1
T2: grid = ["F#......", ".#.###..", ".#.T.#..", ".###.#..", ".....#.F"], k = 1 → 12 (왼쪽 경로를 막으면 오른쪽 불이 12분에 도착)
T3: grid = ["F......F", "........", "..#..#..", "...T....", "..#.....", "........", ".#....#.", "F......."], k = 3 → 7

**채점표 (10점)**

- [2] T1 정답(늦출 수 없는 경우).
- [3] T2 정답(조합으로 경로를 막은 뒤 BFS 도착 시간의 최댓값).
- [4] T3 정답(8×8, 벽 3개 조합에 다중 시작점 BFS). 시간 제한 안에 끝나야 한다.
- [1] 세트 기록: '실전세트-기록.md'에 P2-22~24 각각의 해결 여부와 걸린 시간을 적어 세트 시간 안에 커밋했다.

> 작성 메모: 2부-B 실전 세트 3/3, weight 4(권장 약 40분). W20-18(브루트 포스와 BFS 조합)과 W20-19(조합 백트래킹 후 거리 계산으로 최적값 구하기)는 두 형 모두 '조합을 고르고 → 다중 시작점 BFS로 거리 계산 → 최적값'으로 시험한다. A형은 후보 중 k개를 골라 BFS 거리 합을 최소로 하고, B형은 빈칸 k개에 벽을 세워 불이 도착하는 시간을 최대로 한다. 백준 14502·15686·17142와 기법은 같지만 목표값과 규칙은 새로 만들었다. W23-11(시간 제한 모의 코테 기록)은 '실전세트-기록.md'(1점)로 채점한다. W23-12의 '3문제 중 2문제 이상 해결'은 세트 전체 결과로 판정한다. 권장 판정 기준은 P2-22~24 각 문항에서 7점 이상이면 '해결'로 보고, 3문항 중 2개 이상이면 W23-12 달성이다. 이 기준은 출제 측의 제안이므로 운영 측 확정이 필요하다. W23-12의 '질문 은행 90%' 부분은 1부·구술에서 채점하는 것으로 가정했다(확인 필요). 기대 출력은 참조 풀이로 검증했다.

## 3부-L 라이브 실기 (16.9점 · 720분)

- AI·인터넷 금지, 엔진 소스·공식 문서만 허용. 3블록 × 240분이고 블록마다 권장 시간 합은 200분 이하다(40분 여유).
- 블록1·2는 새 시험 프로젝트(A형 RuneArena·접두사 Rune, B형 DuskKeep·접두사 Dusk)에서, 블록3은 응시자 본인의 포트폴리오 저장소(UE5-ActionArena, 태그 exam-submit)를 채점자가 시험 PC에 Clone한 사본에서 한다. 채점자는 블록3 사본에 결함을 미리 심어 둔다.
- 과제마다 기능 브랜치 → PR → Squash merge로 올린다. PR 본문은 '무엇·왜, 테스트'면 충분하다(브랜치·커밋·PR 규칙은 3부-P의 P3-04·05에서 채점).
- 블록1에서 캐릭터(P3-10)를 끝내지 못했으면 블록2 시작 때 채점자가 주는 기준 커밋에서 시작할 수 있다. 이미 받은 블록1 점수는 바뀌지 않는다.

> **블록1 (240분 · 권장 합 200분)** — 새 시험 프로젝트: 세팅 · 저장소 · 디버깅 · AI-Off① · 프레임워크 · 캐릭터

### P3-01 (0.42점) — 목표: W00-13, W00-14, W00-15, W00-16, W00-17, W00-18, C-37

**모범 답안**

- StarterContent 없음. DefaultEngine.ini HardwareTargeting 값은 A형과 같다. 계기판 아이콘 → Scalability Low. Edit → Editor Preferences → Use Less CPU when in Background.
- VS 최종 상태는 A형과 같다(오류 목록 표시 해제, 외부 종속성 폴더 사용 안 함 True, 64비트 IntelliSense 켬).
- 감독관 준비(B): '외부 종속성 폴더 사용 안 함' False, '빌드가 오류와 함께 끝나면 항상 오류 목록 표시' 켬. 메모에 이 두 가지.
- 감독관 개입(B): 구성 DebugGame Editor, 시작 프로젝트 UE5. → Development Editor·Win64로 되돌리고, Games 아래 DuskKeep 우클릭 → 시작 프로젝트로 설정(굵게). 메모에 두 가지.
- 클래스: Tools → New C++ Class… → Actor → DuskBeacon. 채점자 앞에서 Ctrl+T → DuskBeacon.cpp.
- 에디터를 켠 채 VS로 빌드하면 Live Coding 활성 메시지로 빌드가 막힌다. 닫고 다시 빌드해 코드 에러를 기록하면 감점하지 않는다.
- 선언·정의 불일치 → 출력 창에 DuskBeacon.cpp(줄): error C2511 등 '오버로드된 멤버 함수를 클래스에서 찾을 수 없다' 취지. 되돌린 뒤 출력 창 끝의 빌드 시간을 기록한다.

**채점표 (10점)**

- [2] 경로·Blank·C++·Desktop·Scalable·StarterContent 없음: 모두 맞음(2) / 1개 틀림(1) / 2개 이상 틀림(0)
- [2] Scalability Low + Use Less CPU 켬: 둘(2) / 하나(1) / 없음(0)
- [2] VS 옵션 3개 최종 상태가 맞고 틀렸던 2개를 메모: 모두(2) / 메모 없음 또는 옵션 1개 틀림(1) / 옵션 2개 이상 틀림(0)
- [2] 개입 뒤 Development Editor·Win64·DuskKeep 굵게 복구 + 바뀐 2가지 메모 + DuskBeacon 생성과 Ctrl+T 시연: 모두(2) / 하나 빠짐(1) / 둘 이상 빠짐(0)
- [2] 첫 error 줄(파일·줄·시그니처 불일치)과 빌드 시간 기록: 둘(2) / 하나(1) / 없음(0)

> 검토에서 고친 점: B형만 VS 옵션이 1개 틀어져 있어 2개인 A형보다 쉽다. A형만 New C++ Class 메뉴를 알려 준다. Ctrl+T를 썼는지 나중에 확인할 방법이 없다. Desktop·Scalable 설정을 사후에 확인할 근거가 없다. 감독관이 언제 개입하는지 정해져 있지 않다. 채점표에 0점 기준이 없다. → B형도 옵션 2개를 틀어 둔다(외부 종속성 False, 오류 목록 표시 켬). 두 형의 문장 수준을 맞췄다. 화면 확인 때 Ctrl+T 시연을 넣었다. DefaultEngine.ini HardwareTargeting 확인을 추가했다(섹션 이름은 확인 필요). '프로젝트를 만들고 손 들기' 절차를 넣었다. 기준마다 2/1/0을 적었다.

> 작성 메모: 형별 이름: A=RuneArena/UE5-RuneArena/접두 Rune, B=DuskKeep/UE5-DuskKeep/접두 Dusk(라이브 블록1·2 공통, 블록3은 응시자 본인 저장소 사본). 감독관 사전 준비(두 형 모두 VS 옵션 2개를 틀어 둠): A는 '빌드가 오류와 함께 끝나면 항상 오류 목록 표시' 켬·'64비트 IntelliSense 사용' 끔, B는 '외부 종속성 폴더 사용 안 함' False·'빌드가 오류와 함께 끝나면 항상 오류 목록 표시' 켬. 개입 절차: 응시자가 프로젝트를 만들고 VS가 열리면 손을 들고, 감독관이 솔루션 설정을 바꾼다(A: 구성 Development·시작 프로젝트 UE5, B: 구성 DebugGame Editor·시작 프로젝트 UE5). VS 한국어 메뉴 표기는 버전(VS 2026/2022)에 따라 다를 수 있음(확인 필요). 저장소가 아직 없으므로 PR 없이 채점자 화면 확인(이때 Ctrl+T로 .cpp 열기 시연), 메모는 P3-02에서 docs/exam-log.md로 올린다. 권장 30분에는 프로젝트 첫 컴파일 대기(수 분)가 들어 있다.

### P3-02 (0.85점) — 목표: W00-08, W00-22, W01-18, W01-19, W01-20, W01-21, W01-46, C-32, C-33, C-38, C-39, C-40, C-41

**모범 답안**

- 감독관 준비(B): Email만 바꿈, *.fbx·*.wav 줄이 빠진 lfs-setup.txt, Content·Config 폴더에 desktop.ini·Thumbs.db.
- Options → Git 탭 Email이 계정과 다름 → 계정 Email로 Save(그대로면 커밋이 계정과 연결되지 않음). 메모에 Email.
- 빠진 줄: *.fbx·*.wav filter=lfs diff=lfs merge=lfs -text. 확장명 표시를 켜고 '.gitattributes.'(끝에 점 하나 더)로 바꾸는 요령. 위치는 .uproject와 같은 폴더.
- Add Local Repository… → create a repository → Git Ignore UnrealEngine → Initialize Git LFS.
- Changes에 Binaries·Intermediate·Saved·DerivedDataCache가 없어야 한다. 심어 둔 desktop.ini·Thumbs.db는 우클릭 → Ignore file(.gitignore에 줄 추가).
- Commit to main → Publish repository(Keep this code private 해제). 메시지는 문제에 준 것이며 채점하지 않는다. GitHub 웹 첫 커밋 작성자가 시험 계정으로 연결돼 보여야 한다.
- LFS 확인은 A형과 같다(블록1 끝 main의 .uasset이 'Stored with Git LFS').
- (a) 원본: Config·Content·.uproject / 생성물: Saved·Intermediate·.vs. 유니티 Assets·ProjectSettings(원본) ↔ Library·Temp(생성물). 다시 빌드하면 생기므로 올리면 용량·충돌만 생긴다.
- (b) wav를 Git LFS로 보냄(저장소엔 포인터) / 텍스트 줄바꿈 정규화.
- (c) 한글·공백 경로와 OneDrive 동기화는 빌드 에러·동기화 충돌의 원인.

**채점표 (10점)**

- [1] 틀린 Email을 찾아 고치고 메모(1) / 아님(0)
- [2] .gitattributes: 빠진 fbx·wav를 채운 4줄+text=auto, 최상위·이름 정확(2) / 줄 또는 위치·이름 중 하나 틀림(1) / 없음(0)
- [2] UnrealEngine .gitignore와 LFS 켜짐(블록1 끝 main의 .uasset이 LFS 표시): 둘(2) / 하나(1) / 없음(0)
- [2] main 첫 커밋에 생성물 없음, 심어 둔 윈도우 파일 2개를 Ignore file로 제외, 작성자가 계정과 연결(2) / 윈도우 파일 남음 또는 작성자 불일치(1) / 생성물 포함(0)
- [1] UE5-DuskKeep 공개(1) / 아님(0)
- [2] exam-log: 6개 분류·유니티 대응·안 올리는 이유·두 줄 뜻·경로 이유 모두 맞음(2) / 1~2개 틀림(1) / 3개 이상 틀림(0)

> 검토에서 고친 점: A형은 틀어진 설정이 없고 템플릿도 완전하다. 그래서 기준1·2가 거저 얻는 점수다. 또 단계마다 메뉴·템플릿 이름을 알려 줘 B형보다 쉽다. exam-log (a)도 B형만 6개 분류와 '안 올리는 이유'를 요구한다. Blank 프로젝트 첫 커밋에는 .uasset이 없어 '.uasset이 LFS로 표시'를 확인할 수 없다. → A형에 '*.umap'·'* text=auto' 누락과 Name·Email 변경을 심었다. 문장 수준과 exam-log (a) 요구를 B형과 맞췄다. LFS는 블록1이 끝난 뒤 main의 .uasset이 'Stored with Git LFS'로 보이는지로 확인한다. 작성자 연결 확인과 Name·Email을 바꾸는 방법을 notes에 넣었다.

> 작성 메모: 감독관 준비(A): 커리큘럼 템플릿에서 '*.umap' 줄과 '* text=auto' 줄을 뺀 lfs-setup.txt, Name·Email을 다른 사람 것(예: proctor / proctor@example.com)으로 바꿈, Content·Config에 Thumbs.db·desktop.ini를 심음. 감독관 준비(B): '*.fbx'·'*.wav' 줄을 뺀 lfs-setup.txt, Email만 바꿈, Content·Config에 desktop.ini·Thumbs.db를 심음. Name·Email은 Desktop Git 탭이나 git config --global로 바꾼다. 심는 파일은 숨김 속성 없이 둔다. 시험용 GitHub 계정 사용. 첫 커밋은 커리큘럼(W01)대로 main에 직접 한다. 커밋 메시지 규칙은 포트폴리오 P3-04에서 채점하므로 여기서는 메시지를 문제에 주고 채점하지 않는다. exam-log.md는 첫 커밋에 넣어도, Publish 뒤 PR로 올려도 같은 점수. Blank 프로젝트의 첫 커밋에는 .uasset·.umap이 없을 수 있으므로 LFS 동작은 블록1이 끝난 뒤 main의 .uasset으로 확인한다.

### P3-06 (0.85점) — 목표: W00-05, W00-19, W00-20, W01-11, W01-17, W03-22, C-06

**모범 답안**

- UE_LOG(LogTemp, Warning, TEXT("Beacon Lit")); 액터 2개라 두 번 멈춘다(F5로 계속). Output Log에 노란색(Warning).
- 흐름: 월드 플레이 시작 → 액터 시작 알림 → AActor::DispatchBeginPlay → ADuskBeacon::BeginPlay.
- Ctrl+Alt+F11. .cpp 함수 안만 바꿔 클래스 모양(헤더·UPROPERTY·생성자)이 그대로라서.
- Ctrl+T Actor.h(Engine/Source/Runtime/Engine/Classes/GameFramework), UE_LOG에서 F12 → LogMacros.h(Engine/Source/Runtime/Core/Public/Logging).
- 메모는 거짓: Actor.h 선언은 virtual void Tick(float DeltaSeconds).

**채점표 (10점)**

- [2] Warning 수준 UE_LOG 줄에서 두 번 멈추고 F5로 계속(2) / 한 번만 멈추거나 계속 못 함(1) / 없음(0)
- [2] 호출 스택으로 '월드 시작 → DispatchBeginPlay → 내 BeginPlay' 흐름 설명(2) / 일부만(1) / 없음(0)
- [2] 에디터를 켠 채 (LC) 문구 반영·Output Log 확인 + 재시작 불필요 이유: 둘 다(2) / 하나(1) / 없음(0)
- [2] 두 파일을 Ctrl+T·F12로 찾고 경로 설명: 둘(2) / 하나(1) / 없음(0)
- [2] 메모 거짓 판정 + float DeltaSeconds 선언과 파일 근거(2) / 판정만 맞고 근거 없음(1) / 틀림(0)

> 검토에서 고친 점: A형 기준5에 부분 점수가 없다. 기준1의 '진행 못 함 1'은 무엇이 부분인지 모호하다. 디버깅 기호 설치가 '확인 필요'로만 남아 있다. 기호가 없으면 호출 스택에 엔진 함수 이름이 안 보여 W03-22를 채점할 수 없다. → 모든 기준을 2/1/0으로 정의했다. 'Editor symbols for debugging'은 커리큘럼 W00 설치 단계대로 시험 PC 사전 준비로 확정했다. 기호를 처음 불러올 때 시간이 걸린다는 것도 notes에 적었다.

> 작성 메모: 시험 PC 사전 준비: 런처 엔진 Options에서 'Editor symbols for debugging'을 설치해 둔다(없으면 호출 스택에 엔진 함수 이름이 안 보인다). 디버거로 처음 띄울 때 기호 로딩에 1~2분 걸릴 수 있다. 콜스택 중간 프레임 이름은 버전·배치 방식에 따라 달라 '월드 시작 → DispatchBeginPlay → 내 BeginPlay' 흐름만 요구. 권장 15분 = 채점자 입회 시연 10분 + PR·merge 5분. 입회는 시연 1)~3)을 직접 보고, 4)와 스크린샷은 PR에서 확인.

### P3-07 (0.85점) — 목표: W01-12, W01-13, W01-16, W01-23, W01-24, C-11, W04-28

**모범 답안**

- .h: Mesh(VisibleAnywhere TObjectPtr), EditAnywhere float BobHeight = 25.f, BobSpeed = 3.f; FRotator RotationRate = FRotator(0.f, 60.f, 20.f); float PhaseOffset = 0.f; StartLocation, RunningTime.
- BeginPlay: StartLocation 저장.
- Tick: RunningTime += DeltaTime; L.Z = StartLocation.Z + BobHeight * FMath::Sin((RunningTime + PhaseOffset) * BobSpeed); SetActorLocation; AddActorLocalRotation(RotationRate * DeltaTime);
- FRotator(Pitch, Yaw, Roll) 순서 주의, ×DeltaTime으로 이번 프레임 각도.
- 세 개가 같은 높이·속도로 박자만 어긋나고, 세 번째는 반대 방향으로 돈다.

**채점표 (10점)**

- [2] 컴파일되는 ADuskLantern: 30분 안(2) / 31~40분(1) / 40분 넘음 또는 실패(0)
- [2] StaticMesh 루트 + 사인파 + PhaseOffset 반영: 모두(2) / 일부(1) / 없음(0)
- [2] RotationRate×DeltaTime 회전, 이동도 FPS 무관: 둘(2) / 하나(1) / 없음(0)
- [2] 조정값 4개 노출·기본값: 4개(2) / 2~3개(1) / 0~1개(0)
- [2] BP 3개 박자 어긋남·세 번째 반대 회전 + 일지: 둘(2) / 하나(1) / 없음(0)

> 검토에서 고친 점: A형 기준2·4에 부분 점수가 없다. B형은 Pitch가 0인데 '세 축 회전'이라고 적혀 있다. '세 번째는 Yaw −120'이 어느 값을 말하는지 모호하다. → 부분 점수를 넣었다. B형을 'RotationRate만큼 회전'과 '세 번째는 RotationRate Yaw −120'으로 고쳤다. 정답에 UE_PI(PI도 인정)를 적었다.

> 작성 메모: AI-Off ① 변형. 메시는 /Engine/BasicShapes를 BP에서 지정. 권장 40분 = C++ 작성·빌드 30분 + BP 배치·PR 10분. 시작·종료 시각은 감독관이 C++ 빌드 성공 시점까지 기록한다(응시자가 빌드 성공 때 손을 든다).

### P3-09 (0.42점) — 목표: W03-23, W03-24

**모범 답안**

- 부모: AGameModeBase(AGameMode도 인정) / APlayerController / ACharacter.
- Maps & Modes: Default GameMode = BP_DuskGameMode, Default Pawn Class = BP_DuskCharacter, Player Controller Class = BP_DuskPlayerController. 저장 위치는 A형과 같다.
- 원인(B): Window → World Settings → GameMode Override = GameModeBase. 맵 설정이 프로젝트 기본보다 우선 → None(또는 BP_DuskGameMode)으로 바꾸고 맵 저장.
- Outliner에 BP_DuskCharacter·BP_DuskPlayerController 인스턴스(이름 뒤 숫자는 달라도 됨).

**채점표 (10점)**

- [2] C++ 3개 알맞은 부모: 3개(2) / 2개(1) / 0~1개(0)
- [2] BP 자식 3개 폴더·이름 규칙: 모두(2) / 일부(1) / 없음(0)
- [2] 기본 GameMode·Pawn·PC 연결: 모두(2) / 일부(1) / 없음(0)
- [2] GameMode Override를 원인으로 찾아 고치고 원인·메뉴 기록(2) / 고쳤으나 기록 없음(1) / 못 고침(0)
- [2] Outliner 확인 + merge된 변경에 ini·BP·맵 수정 포함: 둘(2) / 하나(1) / 없음(0)

> 검토에서 고친 점: 난이도 차이가 있다. A형은 함정 없이 기본 맵만 지정하면 된다. B형은 GameMode Override 함정을 진단해야 한다. A형만 부모 클래스를 알려 준다. 기본 맵 지정은 covers 밖이다. 감독관 맵 준비 절차도 모호하다. → 두 형 모두 맵 GameMode Override 함정을 넣었다(A는 GameMode, B는 GameModeBase). 기본 맵 요구를 빼고 문장 수준을 맞췄다. 맵은 그 이름으로 저장해 두도록 준비 절차를 적었다. 채점표는 2/1/0으로 정리했다.

> 작성 메모: 감독관 준비: 같은 UE 5.8 버전의 다른 프로젝트에서 File → New Level → Basic으로 맵을 만들고 Window → World Settings → GameMode Override를 A형은 GameMode, B형은 GameModeBase로 바꾼 뒤 L_RuneTrial(A)·L_DuskTrial(B) 이름으로 저장해 시험 PC 바탕화면에 둔다(파일 이름만 바꾸지 말고 그 이름으로 저장). 응시자는 에디터를 닫은 채 Content/Rune/Maps(Content/Dusk/Maps)에 복사한다. 두 형 모두 같은 종류의 함정(맵 GameMode Override)이고 값만 다르다. 기본 맵(Default Maps) 지정은 covers 밖이라 요구하지 않는다.

### P3-10 (1.27점) — 목표: W04-20, W04-21, W04-22, W04-23, W04-24, W04-25

**모범 답안**

- 팩: + Add → Add Feature or Content Pack… → Third Person → Add to Project.
- USpringArmComponent(TargetArmLength 450, bUsePawnControlRotation true) + UCameraComponent(붐 끝에 부착), bUseControllerRotationYaw false, GetCharacterMovement()->bOrientRotationToMovement true.
- UPROPERTY(EditAnywhere) TObjectPtr<UInputAction> …, TObjectPtr<UInputMappingContext> ….
- BeginPlay: ULocalPlayer::GetSubsystem<UEnhancedInputLocalPlayerSubsystem>(PC->GetLocalPlayer())->AddMappingContext(IMC, 0); MaxWalkSpeed = WalkSpeed.
- SetupPlayerInputComponent: UEnhancedInputComponent로 Cast → BindAction(Triggered: 이동·시점 / Started·Completed: 점프·질주).
- UPROPERTY(EditAnywhere) float WalkSpeed = 400.f, SprintSpeed = 900.f; 위에 '// TODO(W8): 데이터 에셋으로 이전'(커리큘럼 W04 형식). TODO 표시와 '데이터 에셋으로 이전' 뜻이 있으면 괄호 안 표기가 달라도 인정.
- 질주 시작·끝 입력 때 SprintSpeed·WalkSpeed를 읽으므로 BP 값 600이 Play에 반영된다.

**채점표 (10점)**

- [1] 팩 추가, 마네킹 메시(1) / 아님(0)
- [2] 붐·카메라 C++ 생성, 길이 450, 카메라만 회전·캐릭터는 이동 방향: 모두(2) / 일부(1) / 없음(0)
- [1] IA 4개·IMC 지정 폴더·접두사, 키 매핑(1) / 아님(0)
- [2] UPROPERTY 에셋 + AddMappingContext + BindAction: 모두(2) / 일부(1) / 없음(0)
- [2] 이동·시점·점프 동작: 3개(2) / 1~2개(1) / 0개(0)
- [2] 400↔900 질주, 600 변경 반영, TODO(W8) 주석 또는 같은 뜻의 TODO: 3요소(2) / 1~2요소(1) / 없음(0)

> 검토에서 고친 점: A형은 IA 이름·키·API(로컬 플레이어 서브시스템, BindAction)·TODO 원문까지 준다. B형은 이를 직접 떠올려야 한다. B형만 채점자가 그 자리에서 600 반영을 확인하는데, 채점자가 기다려야 한다. P3-09를 못 끝낸 응시자는 진행할 방법이 없다. → 두 형을 같은 요구 수준으로 맞췄다(키는 사양으로 둘 다 제공). 600 반영은 두 형 모두 영상 끝 장면으로 확인한다. 팩에 따라 들어오는 예제 IA·IMC를 복제해도 인정한다. P3-09 미완성일 때 쓸 대체 지시를 notes에 넣었다.

> 작성 메모: 질주용 IA를 하나 더 만든다(IA 4개). Build.cs의 EnhancedInput 모듈 기본 포함 여부는 확인 필요(빠지면 추가). 마네킹은 Third Person 팩. 팩을 넣으면 예제 IA·IMC가 같이 들어올 수 있는데(버전마다 다름, 확인 필요), 복제·이름 변경해 지정 폴더에 두어도 인정. TODO 주석은 커리큘럼 W04 원문 '// TODO(W8): 데이터 에셋으로 이전'이 기준이다. TODO 표시와 '데이터 에셋으로 이전' 뜻이 있으면 괄호 안 표기가 달라도 인정. 600 반영은 영상으로 확인하므로 채점자가 자리에서 기다릴 필요가 없다. P3-09를 끝내지 못한 응시자도 캐릭터 C++ 클래스와 BP 자식이 있으면, 감독관 안내에 따라 레벨에 배치하고 Auto Possess Player = Player 0으로 시연해도 이 문항은 같은 점수.

> **블록2 (240분 · 권장 합 190분)** — 같은 시험 프로젝트: AI-Off② · AI-Off③ · 복제·RPC 실험

### P3-12 (1.69점) — 목표: W05-09, W05-15, W05-23, C-12, W08-25

**모범 답안**

- UINTERFACE(MinimalAPI, Blueprintable) + UFUNCTION(BlueprintNativeEvent, BlueprintCallable) Use·GetUsePrompt.
- 상자: Use_Implementation에서 토글, Lid->SetRelativeRotation(FRotator(bOpen ? -70.f : 0.f, 0.f, 0.f)).
- Implements<UDuskUsable>() → IDuskUsable::Execute_Use(Target, GetOwner()).
- 다이나믹 멀티캐스트 + BlueprintAssignable. SetTimer 0.2초 반복, EndPlay ClearTimer, Tick 끔.
- Scan: 시작점 = 소유 캐릭터 위치, 방향 = 카메라 전방 → SweepSingleByChannel(MakeSphere(40), 400cm, 소유자 제외) → 이전과 다를 때만 Broadcast. 카메라 위치에서 붐 길이(450)만큼 더 쏜 것도 인정.
- 근거 예: 시선 이동엔 0.2초 지연이 거의 안 보이고 매 프레임보다 싸다.

**채점표 (10점)**

- [2] 완성 시각: 60분 안(2) / 61~75분(1) / 75분 넘음 또는 미완성(0)
- [2] 두 함수 BlueprintNativeEvent, C++ 상자·BP 종 모두 Execute_로 동작: 둘(2) / 하나만(1) / 없음(0)
- [2] Tick 없음, 0.2초 반복 SetTimer, EndPlay에서 ClearTimer: 모두(2) / 일부(1) / 없음(0)
- [2] 캐릭터 앞 400cm·반지름 40 구 탐색, 바뀔 때만 BP에서도 받는 OnUseTargetChanged Broadcast(2) / 매번 Broadcast·다이나믹 아님·캐릭터 앞에 안 닿음 중 하나(1) / 없음(0)
- [2] F로 상자 토글·종 문구 출력 + 일지·근거: 둘(2) / 하나(1) / 없음(0)

> 검토에서 고친 점: 3인칭이라 카메라가 캐릭터 뒤 350/450cm에 있다. '카메라 앞 250/400cm' 트레이스는 캐릭터 뒤에서 끝나 대상을 못 잡는다. B형 문제에는 타이머 해제 요구가 없는데 채점표는 ClearTimer를 요구한다. A형만 BlueprintNativeEvent·반복 타이머·SphereTrace 같은 기술 이름을 준다. 근거 1줄도 B형만 요구한다. → 탐색 시작점을 '캐릭터 위치, 카메라가 보는 방향'으로 바꿨다(카메라에서 붐 길이만큼 더 쏘아도 인정). 두 형 모두 '끝날 때 주기 실행 정지'와 근거 1줄을 요구한다. 문장 수준을 맞추고 기준 4의 부분 점수 조건을 구체화했다.

> 작성 메모: AI-Off ② 변형: 60분에 인터페이스+감지 컴포넌트+문(상자) 1개. 나머지 대상(픽업·레버)과 레버-문 연동은 포트폴리오 P3-13에서 본다. 3인칭이라 카메라가 캐릭터 뒤 350(B형 450)cm에 있다. 카메라 위치에서 250(400)cm만 쏘면 캐릭터 뒤에서 끝나 아무것도 못 잡으므로 탐색 시작점을 캐릭터 위치로 정했다(카메라 위치에서 붐 길이만큼 더 길게 쏘아도 인정). SweepSingleByChannel·SphereTrace(KismetSystemLibrary) 모두 정답. E(F)용 Input Action은 블록1에서 만든 IMC에 추가한다. 시작·종료 시각은 감독관이 기록. A·B 문제 문장은 같은 수준(기술 이름을 주지 않음)으로 맞췄다.

### P3-14 (1.69점) — 목표: W05-26, W08-21, W08-22, W07-23, W13-27, C-13

**모범 답안**

- 구조는 A형과 같다(데미지 이벤트 AddDynamic → Clamp → Broadcast → 0이면 OnDeath 1회, 다이나믹 멀티캐스트 + BlueprintAssignable).
- 공격: 카메라 위치·방향으로 LineTrace(붐보다 길게, 자신 제외) → ApplyPointDamage(대상, 30, 방향, Hit, Controller, this, UDamageType::StaticClass()).
- 함정: UBoxComponent 겹침 시작에 SetTimer(1초 반복)로 ApplyPointDamage/ApplyDamage 20, 겹침 끝·사망 시 ClearTimer.
- 사망(플레이어): State.Dead, DisableInput, 래그돌/몽타주, 5초 Destroy(SetLifeSpan 인정).
- 체력바: OnHealthChanged 바인딩. 속성 바인딩(Bind)은 인정 안 함.
- 계산: 30×5 = 150, 20×4 = 80(첫 틱 시점에 따라 3~4초).

**채점표 (10점)**

- [2] 완성 시각: 90분 안(2) / 91~110분(1) / 110분 넘음 또는 미완성(0)
- [2] Clamp·BP에서도 받는 다이나믹 델리게이트 2개·OnDeath 1회: 모두(2) / 일부(1) / 없음(0)
- [2] 공격·함정 모두 엔진 데미지 함수 → 데미지 이벤트 경로, 벗어나거나 사망하면 함정 타이머 해제: 모두(2) / 컴포넌트 직접 호출·해제 없음 등 일부(1) / 없음(0)
- [2] 플레이어 사망 4요소: 4개(2) / 2~3개(1) / 0~1개(0)
- [2] 델리게이트로만 갱신되는 허수아비 체력바, 5타·함정 사망 영상, 일지: 모두(2) / 일부(1) / 없음(0)

> 검토에서 고친 점: '사망 4요소'가 플레이어 것인지 샌드백 것인지 모호하다. A형 체력바도 누구 것인지 정해져 있지 않다. A형만 API 이름을 준다. B형만 타이머와 해제를 쓰는 함정이 있어 분량이 더 많다. UMG 속성 바인딩을 인정할지 정해져 있지 않다. 3인칭 트레이스 길이 안내도 없다. → 사망 4요소는 플레이어, 체력바는 두 형 모두 더미 것으로 정했다. A형 K를 '누르는 동안 0.5초마다 15'(타이머·해제)로 바꿔 B형 함정과 같은 구조로 만들었다. 문장 수준을 맞췄다. 속성 바인딩은 불인정으로 하고, 트레이스는 붐보다 길게 쏘도록 정답에 적었다.

> 작성 메모: AI-Off ③ 변형(90분). State.Dead는 Project Settings → GameplayTags에 추가(Build.cs에 GameplayTags 모듈). 래그돌·몽타주 택1. 5초 제거는 SetTimer·SetLifeSpan 모두 인정. 공격·K용 Input Action은 블록1 IMC에 추가한다. 시작·종료 시각은 감독관이 기록. 두 형 분량을 맞추려고 A형 K는 '누르는 동안 0.5초마다 15'(타이머 + 해제)로 B형 함정(겹친 동안 1초마다 20)과 같은 구조로 했다. 사망 4요소는 플레이어에만 요구하고, 체력바는 두 형 모두 더미(샌드백·허수아비) 것이다. 3인칭이라 공격 트레이스는 붐 길이보다 길게 쏘아야 한다. UMG 속성 바인딩(Percent 옆 Bind)은 매 프레임 호출이라 '델리게이트로만 갱신'으로 인정하지 않는다.

### P3-25 (1.69점) — 목표: W14-07, W14-08, W14-10, W14-12, W14-17, W14-18, W14-19

**모범 답안**

- bReplicates = true, DOREPLIFETIME(ADuskNetChest, LidStage), DOREPLIFETIME_CONDITION(ADuskCharacter, GoldPouch, COND_OwnerOnly). #include "Net/UnrealNetwork.h".
- 서버에서 LidStage를 올린 뒤 OnRep_LidStage()를 직접 호출(C++ OnRep은 서버 자동 호출 안 됨).
- 상자는 클라 소유가 아니므로 캐릭터의 UFUNCTION(Server, Reliable) ServerPryChest(ADuskNetChest* Chest)에서 단계를 올린다. 2가 되면 GoldPouch += 50 후 UFUNCTION(Client, Reliable) ClientShowLoot, UFUNCTION(NetMulticast, Unreliable) 반짝임 함수(상자·캐릭터 어느 쪽에 두어도 됨). 손실 5%에서 Unreliable 연출이 가끔 빠질 수 있다(감점 안 함).
- P3-12 사용 시스템을 쓰면 상자의 Use_Implementation(클라에서 실행)에서 User를 ADuskCharacter로 Cast해 ServerPryChest(this)를 부른다. 새 입력을 만들어도 같은 점수.
- 다른 플레이어 화면에는 GoldPouch가 복제되지 않아야 한다(COND_OwnerOnly).
- 실행 위치·설정 위치는 A형과 같다(Server = 서버, Client = 소유 클라, Multicast = 서버 + 모든 클라, OnRep = 값을 받은 클라·서버는 직접 호출 때만).

**채점표 (10점)**

- [2] bReplicates, DOREPLIFETIME과 COND_OwnerOnly 등록이 코드에 있음(2) / 하나 빠짐(1) / 없음(0)
- [2] OnRep으로 두 창 모두 단계별 각도가 맞음(호스트 포함), 서버만 값 변경(2) / 한쪽 창만(1) / 없음(0)
- [3] Server·Client·Multicast RPC가 소유 캐릭터 경유로 동작, GoldPouch는 서버에서만 증가, '+50'이 연 사람 창에만(3) / 1~2종만 맞음(1~2) / 없음(0)
- [2] 2인 Listen Server·지연 150ms·손실 5% 설정 캡처와 각도·'+50' 장면이 나온 영상(2) / 하나만(1) / 없음(0)
- [1] 실행 위치 표 4줄이 정답과 일치(1) / 틀림(0)

> 검토에서 고친 점: A형만 열쇠 픽업(새 액터·오버랩 권한 처리)과 잠김/열림 두 경로가 있어 B형보다 분량이 크다. 40분 안에 하기 어렵다. Starter Content를 껐으므로 효과음·반짝임 에셋이 없을 수 있다. 영상을 mp4로만 받는다. B형은 영상 요구가 모호하다. → A형을 '토글 문 + OpenCount(COND_OwnerOnly) + ClientShowOpenCount + Multicast 연출'로 바꿨다. B형과 같은 구성이다(복제 변수 2·RPC 3·OnRep 1). 효과음·반짝임은 화면 메시지·디버그 드로잉으로 대신해도 된다. 영상은 mp4 또는 GIF로 받는다. 영상에 들어가야 할 장면을 두 형 모두 구체적으로 적었다.

> 작성 메모: 블록2 마지막 문항(P3-14까지 merge된 main에서 시작). 블록2 권장 합 60+90+40 = 190분. A형은 열쇠 픽업(새 액터·오버랩 권한 처리)과 잠김/열림 두 경로가 있어 B형보다 분량이 컸으므로, '토글 문 + OpenCount'로 바꿔 B형(3단 상자 + GoldPouch)과 구성을 맞췄다(복제 변수 2개·RPC 3종·OnRep 1개). 클래스 이름은 형 접두사(Rune/Dusk) 기준이며 같은 역할이면 이름이 달라도 인정. Starter Content가 없으므로 효과음·반짝임은 화면 메시지·DrawDebugSphere로 대신해도 같은 점수. 네트워크 에뮬레이션 칸 이름은 버전마다 조금 다르다(지연·손실 값만 확인). 앞 과제의 체력바 위젯을 원격 플레이어용으로도 만들면 2인 PIE에서 위젯 생성 에러가 날 수 있다(IsLocallyControlled·IsLocalController 확인으로 해결). 이 문항 채점과 무관하지만 고치는 시간은 권장 시간에 포함된다. 녹화는 시험 PC의 ScreenToGif 등으로 두 창을 한 영역에 담는다.

> **블록3 (240분 · 권장 합 200분)** — 본인 포트폴리오 저장소 사본: Git 사고 · 셀프 리뷰 · 테스트·치트 · 프로파일링 · 패키징 · TS

### P3-41 (0.85점) — 목표: C-58, C-59, C-60, C-61, C-62, C-63

**모범 답안**

- ①: 보기만 하면 안전하다. 질문 글 예: '브랜치 exam/tmp(GitHub에 있음, Push origin 버튼에 ↑2), History 위쪽에 올리지 않은 커밋 2개, Changes에 바뀐 파일 2개(TESTING.md, DefaultGame.ini). main으로 가려면 어떻게 하나?'
- ②: Push origin → 'Newer commits on remote' → Fetch → Pull origin → 충돌 창. 자동 Fetch로 처음부터 Pull origin이 보이면 바로 눌러도 같은 점수. TESTING.md는 편집기에서 <<<<<<< ~ >>>>>>> 구간을 정리해 첫 줄 '# 테스트 안내 (시험용 사본)', 둘째 줄 '블록3 갱신'으로 저장. 캐릭터 스탯 DataAsset(.uasset)은 origin 쪽 파일 선택(메뉴 예: 'Use the modified file from origin/main', 버전에 따라 이름이 다르다). → Continue merge(또는 Commit merge) → Push origin. 채점자 확인: TESTING.md에 마커 없음·두 줄, 에디터에서 MaxHealth 120.
- ③: Current Branch → New Branch → 이름(예: chore/character-base-comment) → Create Branch(물으면 Bring my changes to …) → 커밋 → Publish branch → PR → Squash and merge → main에서 Pull origin. 코드 파일 변경이라 main 직접 커밋 대상이 아니다.
- ④: 커밋하지 않는다. 숨긴 항목·파일 확장명을 켜고 찾으면 .gitignore가 Source 폴더 안에 있다. 프로젝트 최상위로 옮긴다(커리큘럼 템플릿으로 새로 만들어도 내용이 같으면 인정). 하위 폴더의 .gitignore 규칙은 그 폴더 아래에만 적용돼 최상위 Binaries·Intermediate를 막지 못한다. Changes가 정상으로 돌아온 화면을 캡처한다.
- ⑤: 상관없는 파일 → 커밋 직후 왼쪽 아래 Undo(파일 변경은 남고 커밋만 취소) → memo.txt 체크 해제 → md만 다시 커밋. 오타 → History → 맨 위 커밋 우클릭 → Amend Commit…(Push 전만). 이미 Push했다면 그대로 두고 다음 커밋으로 고친다(Force push가 필요하고 다른 Clone과 꼬여 위험하다).
- Force push나 Discard All을 쓰면 해당 항목 0점.

**채점표 (10점)**

- [1] ① 버튼 조작 없이 두 화면 캡처, 브랜치·바뀐 파일·Push 안 한 커밋을 모두 맞게 적은 질문 글(1) / 일부 틀림(0.5) / 없음·버튼 조작(0)
- [2] ② Push 거절(또는 Pull origin 표시) → Pull origin → Push origin 성공(2) / 채점자 도움으로 성공(1) / Force push·실패(0)
- [2.5] ② TESTING.md 마커 정리·지시대로 두 줄, DataAsset origin 쪽 선택 후 Continue merge(2.5) / 둘 중 하나만(1) / 실패(0)
- [1.5] ③ 커밋 전에 새 브랜치로 옮겨 그 브랜치에서 커밋·PR(1.5) / main에 커밋한 뒤 수습(0.5) / 없음(0)
- [1.5] ④ 생성물 미커밋, 숨긴 항목·확장명을 켜고 .gitignore를 최상위로 복구하고 하위 폴더에서는 왜 안 되는지 한 줄, Changes 정상 캡처(1.5) / 커밋하지 않았지만 복구 못 함(0.5) / 생성물 커밋(0)
- [1.5] ⑤ Undo 후 md만 재커밋, Amend Commit…로 메시지 수정, Push 후 그대로 두는 이유 셋 다(1.5) / 둘만(0.5) / 하나 이하·Force push(0)

> 검토에서 고친 점: git-incidents.md를 처음부터 저장소 안 docs/exam에 쓰게 했다. 그러면 ① 캡처의 Changes 화면에 이 파일이 섞이고, ③에서 Bring my changes로 새 브랜치에 같이 끌려가 채점 상황이 오염된다. → 메모·캡처는 ⑤ 전까지 저장소 밖 C:\ExamNotes에 모았다가 ⑤에서 docs/exam/으로 옮겨 커밋하게 했다. / A형 ⑤ (나)에서는 (가)에서 md를 이미 커밋해 버려 'md만 다시 커밋'할 변경이 남지 않는다. Undo 시나리오가 성립하지 않는다. → (나)에서 md에 'Push 후 대처' 한 줄을 더한 다음 scratch.txt와 함께 커밋 → Undo → md만 재커밋하도록 순서를 고쳤다. / A형 ③(Project Settings 수정)만 에디터를 다시 열어야 한다. B형 ③(헤더 주석)보다 몇 분 더 걸린다. → A형 ③은 Config/DefaultGame.ini를 메모장으로 고쳐도 되게 했다(Project Settings Description과 같은 값). / GitHub Desktop은 자동으로 Fetch하므로 'Push 거절' 안내 없이 처음부터 Pull origin이 보일 수 있다. 이때 채점이 갈린다. 새 브랜치를 만들 때 Bring my changes를 묻지 않는 경우도 있다. → 두 경로 모두 같은 점수로 답안과 채점표에 넣었다. 묻지 않고 변경이 따라오면 그대로 인정한다. / 공통 준비가 응시자 GitHub 계정에 Write 권한을 주라고 했다. 하지만 시험 PC의 GitHub Desktop은 블록1·2에서 쓴 시험용 계정으로 로그인돼 있다. 에디터 시작·PIE에서 결함이 드러나는지 보는 리허설도 없었고, .uasset(LFS) 충돌이 Desktop에서 '한쪽 고르기'로 뜨는지 확인하는 절차도 없었다. → Write 권한을 시험용 계정에 주게 바꿨다. 공통 준비에 리허설 단계(에디터 시작 Error 없음, 쿠킹 실패, 증상 확인, .uasset 충돌 UI)와 대체안을 넣었다. / ⑤의 부분 점수가 '0.5~1' 범위로 돼 있어 채점자마다 다르게 줄 수 있다. → '셋 다 1.5 / 둘만 0.5 / 하나 이하 0'으로 고정했다. / 블록3 제목 형식이 블록1·2('[3부-L 라이브·블록N·A형] 제목 (권장 N분)')와 달랐다. 블록 시간 배분도 문항별 현실 소요와 맞지 않았다(P3-31·32·36은 부족, P3-33은 범위가 과다). → 6문항 제목을 블록1·2 형식으로 맞췄다. 시간을 P3-41 25 + P3-33 20 + P3-31 35 + P3-32 35 + P3-34 40 + P3-36 45 = 200분으로 다시 나누고, 합계를 공통 준비 노트에 적었다.

> 작성 메모: [블록3 공통 준비 — P3-41·33·31·32·34·36 모두 이 절차를 따른다]
1) 시험 7일 전 받은 UE5-ActionArena의 exam-submit 태그를 채점자 PC에 Clone(LFS 포함)해 Development Editor로 빌드하고 PIE·패키징이 되는지 본다. 안 되면 시험 전에 응시자에게 알린다.
2) 각 문항 notes의 결함을 형에 맞게 심는다. 대상은 커리큘럼이 모두에게 만들게 한 클래스·데이터다(이름이 달라도 같은 역할이면 그것). 결함마다 '파일·줄(또는 에셋)·원래 값·바꾼 값·확인한 증상'을 채점자 시트에 적는다.
3) 리허설(채점자 PC, 결함을 모두 심은 상태): ① 에디터 시작 Output Log와 게임 맵 PIE에 결함 관련 Error가 없다(있으면 그 결함이 블록3 첫 문항에서 드러난다). ② P3-34 쿠킹 결함으로 Package Project가 실제로 실패하고, 첫 Error 줄 원문을 시트에 적는다. ③ 각 문항의 증상이 문항·카드 문구대로 나온다. ④ P3-41 ②의 .uasset 충돌이 GitHub Desktop에서 '한쪽 파일 고르기'로 뜬다(확인 필요). 뜨지 않으면 ②에서 .uasset 부분을 빼고, 3행의 .uasset 점수는 채점자 앞 구술(어느 쪽을 어떻게 고르는지)로 본다.
4) 결과를 이력 없는 커밋 1개(메시지 exam: base)로 시험 기관 계정의 비공개 저장소(예: exam-<수험번호>-arena) main에 올린다(LFS 객체 포함, 확인 필요). History로 결함 위치가 드러나지 않게 하려는 것이다. 응시자의 원래 저장소와 태그는 건드리지 않는다(포트폴리오 심사는 원래 저장소로). 시험 PC의 GitHub Desktop은 블록1·2에서 쓴 시험용 GitHub 계정으로 로그인돼 있으므로 그 계정에 Write 권한을 준다. 블록3의 인터넷은 GitHub 제출용으로만 허용한다.
5) 시험 PC: 먼저 깨끗한 exam-submit 상태를 C:\Projects\<원래 폴더 이름>에 Clone해 빌드하고, 에디터를 한 번 열고, Development·Shipping 패키징을 한 번씩 해 컴파일 결과와 DDC를 데운다. 그다음 같은 폴더의 원격을 시험용 저장소로 바꾸고 로컬 main을 그 main(결함 포함)에 맞춘다(채점자는 명령어 사용 가능). 패키징 출력 폴더, Saved/Logs·Saved/Crashes, %LOCALAPPDATA%\<프로젝트 이름>을 지우고 Development Editor로 다시 빌드한다. GitHub Desktop에 저장소를 추가하고 에디터는 닫아 둔다.
6) 기능이 포트폴리오에 아예 없으면(과제 미완) 결함 대신 그 하위 과제를 블록3 안에서 최소 형태로 만들게 하고 채점표는 그대로 쓴다. 응시자가 다른 문항의 결함을 먼저 고쳤으면 그 PR에 위치·이유가 있을 때 해당 문항 기준에서 인정한다.
7) 모든 결함은 응시자 본인 코드·데이터에 심는다. 형별로 내용은 다르게, 종류와 수는 같게 맞춘다. 블록3 권장 합: P3-41 25 + P3-33 20 + P3-31 35 + P3-32 35 + P3-34 40 + P3-36 45 = 200분.
[P3-41 준비] 각 상황은 그 차례에 채점자가 만든다.
① A형: 로컬 전용 브랜치 exam/warmup(Publish 안 함)에 커밋 1개(TESTING.md 1줄), 커밋 안 한 변경 1개(README 1줄). B형: 브랜치 exam/tmp(Publish함)에 Push 안 한 커밋 2개, 커밋 안 한 변경 2개(TESTING.md·Config/DefaultGame.ini 각 1줄). 끝나면 채점자가 main으로 돌아가 변경 버리기·브랜치 삭제를 한다.
② 채점자 PC 사본(시험용 저장소 main)에서 A형: README 첫 줄 끝에 ' (시험용 사본)'을 붙이고 기본 무기 DataAsset(W8 UWeaponData)의 데미지 배율을 1.5로 저장. B형: TESTING.md 첫 줄을 '# 테스트 안내 (시험용 사본)'으로, 캐릭터 스탯 DataAsset(W8 UCharacterStatData)의 MaxHealth를 120으로 저장. 시험 PC가 ①을 마친 뒤, 응시자가 ②를 시작하기 전에 커밋·Push한다. 시험 PC가 자동 Fetch해 처음부터 Pull origin이 보여도 된다. README 첫 줄이 제목 줄이 아니면 쓸 줄을 정해 알려 준다. TESTING.md가 없으면(W19 미완) README의 다른 줄로, 해당 DataAsset이 없으면 응시자의 다른 DataAsset으로 바꾼다.
③ 지시만 한다. B형 클래스가 없으면 응시자 캐릭터 C++ 헤더 아무것이나.
④ A형: .gitignore를 .gitignore.bak으로 이름만 바꾼다. B형: Source 폴더 안으로 옮긴다. 둘 다 커밋하지 않는다. Changes 목록이 뜨는 데 시간이 걸릴 수 있다.
⑤ 직전에 프로젝트 최상위에 scratch.txt(B형 memo.txt)를 만든다.
응시자는 GitHub Desktop만 쓴다. 메모·캡처는 저장소 밖(C:\ExamNotes)에 모았다가 ⑤에서 docs/exam/으로 옮긴다(저장소 안에 먼저 만들면 ①의 Changes 화면에 섞이고 ③에서 새 브랜치로 같이 끌려간다). Force push나 Discard All을 쓰면 해당 항목 0점. 이 문항에서 채점자 지시로 main에 직접 한 커밋은 다른 문항에서 감점하지 않는다.

### P3-33 (0.85점) — 목표: W13-10, W13-13, W13-14, C-05

**모범 답안**

- 심은 결함(채점자 시트와 대조):
① UArenaHUDWidget 헤더: class UProgressBar; class UTextBlock;를 지우고 #include "Components/ProgressBar.h"·"Components/TextBlock.h"를 넣었다 → 전방 선언 복구, include는 .cpp로. BindWidget용 TObjectPtr 멤버는 전방 선언만으로 선언할 수 있다.
② UProjectilePoolSubsystem: 풀 배열(TArray<TObjectPtr<…>>)의 UPROPERTY()를 지웠다 → 복구. 등록되지 않은 배열은 GC가 모르므로, 투사체가 파괴·수거되면 해제된 메모리를 가리키는 댕글링이 남을 수 있다.
③ UArenaHUDWidget: NativeTick 오버라이드에서 매 프레임 체력을 읽어 SetPercent → NativeTick을 지우고 속성 변경 델리게이트(W17)로만 갱신.
④ 풀의 조회 함수(예: GetAvailableCount) const 삭제 → 복구.
⑤ Build.cs: 쓰지 않는 "MovieScene"·"LevelSequence" 추가 → 삭제. 확인 방법·남긴 모듈·Public/Private 기준은 A형과 같다.
- 카드 정답: 1 'HUD 위젯 헤더의 컴포넌트 include는 전방 선언으로' 채택 / 2 '전방 선언하면 런타임이 느려진다' 거절(컴파일 의존성 문제일 뿐 실행 속도와 무관) / 3 '풀 배열에 UPROPERTY가 없다' 채택 / 4 'UPROPERTY는 BP·디테일 패널에 보일 때만 필요하다' 거절(GC 추적·직렬화·복제에도 필요) / 5 '체력바는 NativeTick에서 매 프레임 갱신해야 정확하다' 거절(이벤트 기반, W9 Tick·Binding 0개) / 6 'Build.cs에 쓰지 않는 모듈이 있다' 채택.
- C-05 해설은 A형과 같다.

**채점표 (10점)**

- [2] 헤더 include를 전방 선언으로 바꾸고 include를 .cpp로 옮김, 빌드 통과(2) / 일부만이나 빌드 실패(1) / 없음(0)
- [2] Build.cs 심은 모듈 2개 삭제·빌드 통과, 삭제 근거(검색)와 고른 모듈의 쓰는 곳(2) / 하나만이나 근거 없음(1) / 없음(0)
- [2] UPROPERTY·Tick(이벤트로)·const 3종 수정, PR에 파일·줄·이유(2) / 1~2종(1) / 없음(0)
- [2] 카드 6장 모두 맞게 채택/거절하고 이유(2) / 오판 1장이나 이유 빠짐(1) / 오판 2장 이상·없음(0)
- [2] 고른 2줄을 1분 안에 설명, 셀프 체크, 엔진 소스 확인 TIL 1건(2) / 1줄만 설명했거나 TIL 없음(1) / 설명 실패(0)

> 검토에서 고친 점: 20분에 결함 7개 수정, 카드 8장 판단, 남긴 모듈마다 근거 쓰기, Build.cs 변경으로 인한 모듈 전체 재빌드(2~4분), 구술과 TIL까지 하라고 했다. 실제로는 35분 이상 걸린다. → 값 복사 결함을 빼서 결함을 6개로 줄였다. 카드는 6장(맞음 3·틀림 3)으로 줄였다. 남긴 모듈 근거는 채점자가 고른 1개만 쓰게 했다. / A형 UPROPERTY 결함을 '무기 DataAsset 포인터'에 심으라고 했다. 이 멤버가 BP 기본값으로 넣는 것이면 UPROPERTY를 지우는 순간 BP 값이 사라진다. 로드한 에셋만 가리키는 멤버면 GC에 수거돼 P3-31·32·36에서 크래시가 날 수 있다. → 다른 곳에서도 붙잡고 있는 객체(소유 캐릭터·AnimInstance·레벨에 있는 액터)를 가리키는 런타임 캐시 포인터에만 심게 했다. 형마다 범위를 클래스 2개·코드 결함 4개로 맞췄다(B형 BTService는 범위에서 뺌). / 카드 행은 오판 1장일 때 몇 점인지 정해져 있지 않다. 구술 행의 부분 기준도 모호하다. TIL을 main에 직접 커밋하라 했는데, 기능 브랜치에서 작업하는 중이라 브랜치를 바꿔야 한다. → 카드 행을 '오판 0 → 2 / 오판 1이나 이유 빠짐 → 1 / 오판 2 이상 → 0'으로, 구술 행을 '1줄만 설명했거나 TIL 없음 → 1'로 정했다. TIL은 같은 PR에 넣어도 되게 했다.

> 작성 메모: [준비] 공통 준비는 P3-41 notes. 리뷰 범위(형별 클래스 2개와 Build.cs)에 결함 6개(include 1, UPROPERTY 1, Tick 1, const 1, Build.cs 모듈 2)를 심고 위치를 채점자 시트에 적는다. A형 범위: UCombatComponent(W7)·UInteractionComponent(W5). B형 범위: HUD 위젯 C++ 부모(W9 UArenaHUDWidget)·UProjectilePoolSubsystem(W12). 이름이 다르면 같은 역할 클래스로 바꾸고 시작 때 범위를 알려 준다. 모두 빌드·PIE가 돼야 한다. UPROPERTY는 런타임에 채우는 캐시 포인터 중 다른 곳에서도 붙잡고 있는 객체(소유 캐릭터·AnimInstance·레벨에 있는 액터)를 가리키는 멤버에서만 지운다. EditAnywhere·EditDefaultsOnly처럼 BP에서 값을 넣는 멤버에서 지우면 BP 값이 사라지고, 로드한 에셋만 가리키는 멤버에서 지우면 GC 수거로 다른 문항에서 크래시가 날 수 있다. const는 const 함수에서 부르지 않는 조회 함수에서 지운다. 알맞은 멤버·함수가 범위에 없으면 같은 역할의 다른 파일에 심고 그 파일을 범위에 넣어 알려 준다. 리뷰 카드 6장(형별, 맞는 의견 3·틀린 의견 3)을 인쇄한다. 시험은 AI 없이 치르므로 'AI 리뷰 의견'은 이 카드로 대신한다. const 결함은 카드에 없다(응시자가 직접 찾는다). 2줄 설명은 채점자가 응시자 diff에서 전방 선언 1줄과 UPROPERTY 또는 Tick 1줄을 고른다. Build.cs '남긴 모듈'은 채점자가 하나 고른다(예: AIModule 또는 GameplayAbilities). 20분에 맞추려고 값 복사 인자 결함을 빼고 카드를 6장으로 줄였다(Build.cs를 바꾸면 모듈 전체를 다시 빌드해 2~4분 걸린다). 다른 문항 결함(P3-31·32·34·36)과 위치가 겹치지 않는다. 시험 TIL은 docs/exam/til-block3.md(같은 PR에 넣어도 된다).

### P3-31 (1.27점) — 목표: W19-01, W19-02, W19-04, W19-05, W19-12, W19-13, W19-16, W19-17

**모범 답안**

- 심은 결함(채점자 시트와 대조): (가) 데미지 순수 함수에서 크리티컬 배율을 두 번 곱한다 → 치명 결과가 배율의 제곱만큼 커진다. (나) 기본 장착이 아닌 무기 DataAsset의 필수 필드(예: 소켓 이름·콤보 몽타주) 비움 → 필수 필드 규칙.
- 새 테스트 예: IMPLEMENT_SIMPLE_AUTOMATION_TEST(FArenaDamageCritOnceTest, "Arena.Damage.CritOnce", EAutomationTestFlags::EditorContext | EAutomationTestFlags::ProductFilter); RunTest에서 TestEqual(TEXT("crit once"), ComputeDamage(B, D, true), 기대값)을 두 경우로 확인하고 return true. 배율을 방어력 전에 곱하는지 뒤에 곱하는지는 응시자 공식대로(채점자가 미리 계산). '일반 결과 × 배율'과 같지 않을 수 있으니 공식에서 직접 계산한 값이면 정답.
- RefillHealth: UFUNCTION(Exec) void RefillHealth(); GetWorld()->GetGameState()->PlayerArray의 PlayerState마다 UAbilitySystemBlueprintLibrary::GetAbilitySystemComponent(PS)(또는 내 PlayerState의 getter)로 ASC를 얻고 ASC->SetNumericAttributeBase(UArenaAttributeSet::GetHealthAttribute(), ASC->GetNumericAttribute(UArenaAttributeSet::GetMaxHealthAttribute())), Stamina도 같게(또는 최대값으로 덮어쓰는 Instant GE). HUD는 속성 변경 델리게이트(W17)로 바뀌어야 한다.
- 진단 순서, 기존 테스트가 먼저 잡은 경우, 순수 함수 기준, 검증 테스트(실제 에셋 오류 0개, LoadObject), 기존 치트(God의 GE 데미지 차단, 못 막으면 Known Issues), Shipping에서 치트 매니저 없음, TESTING.md·Known Issues, 먼저 고친 경우의 인정은 A형과 같다.

**채점표 (10점)**

- [2.5] Test Automation 창에서 전체 실행·실패 캡처, 심은 결함 2개를 테스트 실패로 드러내 원인을 짚고 고침(2.5) / 1개(1) / 없음(0)
- [2.5] 새 테스트 CritOnce(매크로·플래그)가 월드 없이 데미지 함수만 불러 2경우 확인, 고치기 전 실패 → 후 통과(기존 테스트가 먼저 잡았으면 통과만), PR에 게임 코드 호출 위치(2.5) / 1경우만이거나 실패→통과·호출 위치 중 하나 빠짐(1) / 없음(0)
- [1.5] 검증 함수가 따로 있고 웨이브 DataTable·무기 DataAsset 검증 테스트가 실제 에셋을 통과(1.5) / 둘 중 하나만(0.5) / 없음(0)
- [2] 새 치트 RefillHealth로 체력·스태미나와 HUD가 차는 시연 + 기존 God·SkipWave·SpawnEnemy 5 실행(2) / 새 치트만이나 기존만(1) / 없음(0)
- [1.5] TESTING.md에 새 테스트·실행 방법·전부 통과 캡처, README Known Issues(없으면 '없음')(1.5) / 하나만(0.5) / 없음(0)

> 검토에서 고친 점: 30분에 결함 3개 진단, 순수 함수 분리 리팩터, 새 테스트, 새 치트, 기존 치트 시연, 문서를 모두 하라고 했다. 에디터를 닫고 빌드하는 시간까지 넣으면 50분 안팎이다. → 결함을 2개(계산 1·데이터 1)로 줄이고 시간을 35분으로 늘렸다. W19-01은 새 테스트가 월드 없이 함수를 부르는 것과 PR의 '게임 코드 호출 위치' 1줄로 확인한다. 새 테스트와 새 치트를 한 번에 빌드하라는 팁을 넣었다. / B형 CritOnce는 '일반 결과 × 배율'을 기대값으로 삼는다. 방어력 전에 배율을 곱하는 공식에서는 맞는 코드도 이 테스트에 실패한다. A형 DefenseFloor는 크리티컬 경우의 경계 조건(방어력 ≥ 기본 데미지 × 배율)이 빠져 있다. → 두 형 모두 기대값을 '내 공식으로 손 계산한 값'으로 바꾸고, A형 경계 조건을 적었다. 기존 테스트가 먼저 잡았으면 새 테스트는 통과만 보여도 되게 했다. / 채점표가 '기존 God가 GAS 데미지까지 막는지'를 조건으로 걸었다. 이는 심은 결함이 아니라 포트폴리오 품질 문제인데, 고치느라 시간이 샐 수 있다. → God가 GE 데미지를 못 막으면 원인 한 줄을 Known Issues에 적는 것으로 인정한다.

> 작성 메모: [준비] 공통 준비는 P3-41 notes. 형별 결함 2개(데미지 계산 1, 데이터 1)를 심는다. A형: (가) 데미지 순수 함수(W19, 방어력·크리티컬)의 하한 처리(예: FMath::Max(1, …))를 지운다. 하한이 없는 공식이면 방어력 차감을 더하기로 바꾼다. (나) 웨이브 DataTable(W12) 마지막 행의 적 수를 -2로. B형: (가) 크리티컬 배율을 두 번 곱하게 바꾼다. (나) 기본 장착이 아닌 무기 DataAsset(W8)의 필수 필드 하나(응시자 검증 규칙이 검사하는 것, 예: 콤보 몽타주·소켓 이름)를 비운다. 시험 전에 응시자의 기존 테스트로 어느 결함이 잡히는지 채점자 시트에 적는다(못 잡는 결함은 응시자가 테스트·규칙을 더해야 해 시간이 더 든다). 응시자 공식으로 새 테스트 기대값을 미리 계산해 둔다(배율을 방어력 전에 곱하는지 뒤에 곱하는지 확인). 기존 치트·테스트를 보여 주는 것만으로는 점수가 거의 없고, 결함 진단·새 테스트·새 치트가 라이브 작업이다. 대체 지시: 데미지 계산이 순수 함수로 분리돼 있지 않으면 계산 코드에 같은 결함을 심고 응시자는 이번에 순수 함수로 뺀다. 치트 매니저가 없으면 UCheatManager 상속 클래스와 PlayerController 연결(CheatClass)부터 한다. 검증 함수·테스트가 없으면 이번에 만든다. 함수·에셋 이름은 같은 역할이면 인정. 새 치트는 P3-36 네트워크 결함과 섞이지 않게 PIE 1인 기준으로 본다. 기존 God가 GAS 데미지를 못 막으면(bCanBeDamaged만 바꾸는 경우) 원인 한 줄을 Known Issues에 적으면 4행을 인정한다. 35분에 맞추려고 결함을 3개에서 2개로 줄였다(다른 데이터 종류는 3행의 실제 에셋 통과로 본다). 새 테스트 파일을 더하거나 헤더를 바꾸면 에디터를 닫고 빌드해야 하므로, 새 테스트와 새 치트를 한 번에 써서 한 번만 빌드하는 것이 빠르다. UE 5.5 이후 EAutomationTestFlags 표기가 일부 바뀌었으니 확인 필요.

### P3-32 (1.27점) — 목표: W18-01, W18-05, W18-06, W18-07, W18-15, W18-18, W18-19, W18-20, W18-22

**모범 답안**

- 심은 결함(채점자 시트): AArenaGameMode(또는 웨이브 관리 클래스) Tick에서 매 프레임 TActorIterator로 적마다 SphereOverlapActors(반경 3000)를 부르고 결과를 버린다. 고치기: 쓰이지 않는 코드를 지우고 Tick을 끈다(생성자를 바꿨으면 에디터를 닫고 빌드). 꼭 필요하면 웨이브 타이머(W12)에서 가끔 계산.
- 병목 판정, stat net, 트레이스 기록과 Timers 검색, 측정 방법은 A형과 같다.
- 매크로 예: TRACE_CPUPROFILER_EVENT_SCOPE(ArenaGameMode_Tick); DECLARE_STATS_GROUP(TEXT("ArenaExam"), STATGROUP_ArenaExam, STATCAT_Advanced); DECLARE_CYCLE_STAT(TEXT("GameMode Tick"), STAT_ArenaGameModeTick, STATGROUP_ArenaExam); SCOPE_CYCLE_COUNTER(STAT_ArenaGameModeTick); 콘솔 stat ArenaExam.
- 상위 3개 표 예: GameMode Tick(심은 결함, 안에서 물리 Overlap 쿼리), CharacterMovement, 애니메이션 업데이트 — 각 ms와 캡처.

**채점표 (10점)**

- [1.5] (노트북이면 전원 연결)·'최고 성능' 캡처, 스트레스 맵에서 치트로 적 50→100·투사체 100 즉시 소환(1.5) / 수량 부족이나 치트 없이 배치(0.5) / 없음(0)
- [2] stat unit·fps·game 캡처와 Game/Draw/GPU 병목 판정 근거가 맞음, 2인 PIE stat net 캡처(2) / 근거 부족이나 stat net 없음(1) / 없음(0)
- [2] Insights 캡처에서 W18 내 스코프 1개 이상 식별, 게임 스레드 상위 3개 표(이름·ms)(2) / 하나만(1) / 없음(0)
- [2] 의심 함수에 새 TRACE 스코프 + SCOPE_CYCLE_COUNTER(stat 그룹)를 넣어 확인하고 심은 결함을 정확히 짚음(2) / 매크로만이나 결함만(1) / 없음(0)
- [2.5] 고친 뒤 같은 조건 전후 각 3회와 중간값 표(차이가 측정 오차보다 큼), 성능 리포트 절 추가(2.5) / 1회 측정이나 표·리포트 미흡(1) / 없음(0)

> 검토에서 고친 점: B형 결함을 투사체 Tick에 심었다. 투사체는 금방 풀로 돌아가 Tick이 꺼지므로 '소환 10초 뒤' 측정에서는 비용이 사라진다. 부하도 적 120·투사체 200으로 A형(100·100)과 달랐다. → B형을 GameMode(웨이브 관리 클래스) Tick에서 적마다 Overlap하는 결함으로 바꿨다. 적 수에 비례하는 같은 종류다. 수량은 A형과 같게 했다. / 30분 안에 트레이스·빌드 각 2번, 전후 6회 측정, 2인 PIE까지 하기는 어렵다. 데스크톱 시험 PC에서는 '전원 연결' 캡처를 할 수 없다. → 시간을 35분으로 늘리고, 같은 PIE 세션에서 10초 간격으로 3회 읽어도 인정한다. 전원 연결은 '노트북이면'으로 바꿨다.

> 작성 메모: [준비] 공통 준비는 P3-41 notes. A형: 적 클래스(W10 AArenaEnemy 또는 같은 역할)에서 Tick을 켜고(생성자 PrimaryActorTick.bCanEverTick·bStartWithTickEnabled = true, BP 자식에서 꺼져 있으면 BeginPlay에서 SetActorTickEnabled(true)), Tick에서 매 프레임 UKismetSystemLibrary::SphereOverlapActors(반경 3000, Pawn)를 부르고 결과를 버린다('주변 아군 수 세기' 주석). B형: AArenaGameMode(W3, 웨이브를 다른 클래스가 관리하면 그 클래스)에서 Tick을 켜고 매 프레임 TActorIterator<AArenaEnemy>로 적마다 같은 SphereOverlapActors(반경 3000, Pawn)를 부르고 결과를 버린다('적 밀집도 계산' 주석). 두 형 모두 '불필요한 매 프레임 쿼리, 적 수에 비례'라 난이도와 부하가 같다. 이전 B형의 투사체 Tick 결함은 투사체가 금방 풀로 돌아가 Tick이 꺼져 '소환 10초 뒤' 측정에서 비용이 사라지고 수량(적 120·투사체 200)도 A형과 달라 바꿨다. 결함은 응시자의 W18 스코프 밖(새 Tick 함수)에 둔다. 시험 PC에서 적 100마리 기준 stat unit Game이 3ms 이상 늘었는지 확인하고, 모자라면 반경을 늘린다. P3-33 Tick 결함(A InteractionComponent, B HUD)과 위치가 겹치지 않는다. 대체 지시: 스트레스 맵·소환 치트가 없으면(W18 미완) 빈 맵에 바닥·NavMesh를 깔고 SpawnEnemy로 대신한다. 투사체 소환 치트가 없으면 원거리 적(W11)을 섞어 소환한다. W18 스코프가 없으면 3행의 '기존 스코프' 부분은 0점이고 4행은 그대로 본다. 시간 때문에 Top 3는 찾기만 하고 개선은 1건으로 줄였고, 측정은 같은 PIE 세션 10초 간격 3회도 인정한다(트레이스 2번·빌드 2번·2인 PIE가 있어 30분은 부족해 35분). 데스크톱 시험 PC는 전원 모드 화면만 본다. stat namedevents로 Insights에 액터 이름이 보이는지 시험 PC에서 미리 확인한다(확인 필요).

### P3-34 (1.27점) — 목표: W13-16, W13-17, W13-18, W13-19, W13-20, W19-15

**모범 답안**

- 심은 결함(채점자 시트): (1) 메뉴 맵 Level Blueprint의 BeginPlay 노드가 이름이 바뀐 C++ 함수(AArenaPlayerController::GetMenuHint → GetMenuHintText)를 부른다. 에디터·게임 맵 PIE에서는 메뉴 맵이 로드되지 않아 안 보이고, 쿠킹이 메뉴 맵을 불러올 때 BP 컴파일 Error(예: 'LogBlueprint: Error: … L_MainMenu … Could not find a function named "GetMenuHint" …', 문구는 버전마다 다르다)가 나며 패키징이 실패한다. 고치기: 메뉴 맵을 열고 Level Blueprint(툴바 Blueprints → Open Level Blueprint)에서 ERROR 노드를 지우거나 다시 연결 → Compile → 맵 저장 → 다시 패키징. (2) Game Default Map이 게임(전투) 맵으로 바뀌어 메뉴를 건너뛴다 → 원래 시작 맵(보통 W12 메인 메뉴)으로.
- 로그 읽기(첫 Error부터, 요약 줄만 보지 않기), Maps & Modes 의미, 다른 폴더 실행 이유, 먼저 고친 경우의 인정(2행 최대 1.5)은 A형과 같다.
- 위치: Development는 <실행 폴더>\<프로젝트>\Saved, Shipping은 설치된 게임으로 취급돼 %LOCALAPPDATA%\<프로젝트>\Saved. Shipping은 기본적으로 로그 파일이 없어 에러 확인은 Development 로그로 한다. 실행 폴더의 Saved만 보고 '비어 있음'이라 하면 부분 점수.

**채점표 (10점)**

- [1.5] Maps & Modes에서 바뀐 값을 찾아 고침(전후 캡처), Shipping 빌드가 의도한 맵으로 시작(1.5) / 캡처만이거나 시작 맵이 틀림(0.5) / 없음(0)
- [2.5] 첫 쿠킹 Error 줄 원문과 원인(BP·함수)을 짚고 BP를 고쳐 다시 패키징(먼저 고쳤으면 최대 1.5)(2.5) / 원인 추측만(1) / 없음(0)
- [2] Binary Configuration으로 Shipping·Development 패키징 성공(2) / 하나만(1) / 없음(0)
- [2] 다른 폴더에서 Shipping 10분 실행, 사용자 폴더 Saved\Crashes 비어 있음 캡처(경로 보임)(2) / 10분 미만이나 엉뚱한 폴더 확인(1) / 없음(0)
- [2] Development 빌드 3분 이상 실행 후 Saved\Logs Error 0 캡처(또는 남은 에러의 원인 기록)(2) / 로그 위치만(1) / 없음(0)

> 검토에서 고친 점: 쿠킹 결함을 GameMode·PlayerController 생성자의 ConstructorHelpers::FObjectFinder로 심었다. 에디터는 시작할 때 모든 C++ 클래스의 CDO를 만들므로 'CDO Constructor … Failed to find' Error(경고 창 포함)가 블록3 첫 문항(P3-41에서 에디터를 열 때)에 바로 드러난다. 그러면 쿠킹 로그 읽기(W13-18)를 시험하지 못하고, 노트도 '먼저 고쳐도 인정'으로 이를 덮고 있었다. → 메뉴 맵에서만 로드되는 BP(A 메인 메뉴 위젯, B 메뉴 맵 Level Blueprint)가 이름이 바뀐 C++ 함수를 부르게 해, 쿠킹 때만 BP 컴파일 Error가 나게 했다. 리허설 항목(에디터 시작·PIE에서 안 보이는지, 메뉴 맵이 쿠킹 대상인지, 실제로 실패하는지)과 대체 결함(L_NetLab BP, 마지막으로 WITH_EDITOR 전용 멤버 호출)을 적었다. 먼저 고친 경우는 2행 최대 1.5로 낮췄다. / 패키징 3번(실패 1 + 성공 2)에 Shipping 10분과 Development 5분을 더하면 40분이 빠듯하다. A형은 Development 로그 확인이 4)에 섞여 순서도 엉켜 있었다. → Development 실행을 3분으로 줄이고, 다른 패키징을 기다리는 동안 하도록 단계 순서를 정리했다(A: Shipping 패키징 중 Development 실행, B: Development 패키징 중 Shipping 10분).

> 작성 메모: [준비] 공통 준비는 P3-41 notes(깨끗한 상태로 Development·Shipping 패키징을 한 번 해 컴파일 결과·DDC를 데운 뒤 결함 main으로 바꾸고 출력 폴더·Saved/Logs·Saved/Crashes·%LOCALAPPDATA%\<프로젝트 이름>을 지운다). 포트폴리오 게임은 시험 프로젝트보다 커서 데우기가 없으면 40분 안에 패키징 세 번(실패 1 + 성공 2)이 어렵다.
쿠킹 결함은 에디터 시작·게임 맵 PIE에서는 드러나지 않고 쿠킹 때만 Error가 나야 한다. 생성자의 ConstructorHelpers::FObjectFinder 결함은 에디터가 시작할 때 C++ 클래스 CDO를 만들며 'CDO Constructor … Failed to find' Error(경고 창이 뜰 수 있다)를 내므로 P3-41에서 에디터를 열자마자 드러난다. 그래서 쓰지 않는다.
A형: (1) 응시자 C++ 클래스(W12 세이브·GameInstance 쪽, 없으면 아무 UCLASS)에 UFUNCTION(BlueprintCallable, Category="Exam") static FText GetMenuHint();를 더해 빌드 → 메인 메뉴 위젯 BP(W12)의 Construct에 그 노드를 연결해 Compile·Save → C++ 이름을 GetMenuHintText로 바꿔 빌드하고 그 BP는 다시 열지 않는다. (2) Config/DefaultEngine.ini [/Script/EngineSettings.GameMapsSettings]의 GameDefaultMap을 스트레스 맵(W18)으로.
B형: (1) 같은 방법으로 AArenaPlayerController(W3)에 함수를 더하고, 메뉴 맵(W12)의 Level Blueprint BeginPlay에 노드를 연결한 뒤 이름을 바꾼다. (2) GameDefaultMap을 게임(전투) 맵으로 바꿔 메뉴를 건너뛰게 한다(원래 시작 맵이 게임 맵이면 스트레스 맵으로).
리허설로 확인한다(확인 필요): 쿠킹 로그에 그 BP의 컴파일 Error(예: 'Could not find a function named …')가 남고 패키징이 실패하는지, 메뉴 맵이 쿠킹 대상인지(Project Settings → Packaging의 맵 목록이 비었거나 메뉴 맵이 들어 있음). 그 BP가 Editor Startup Map·게임 맵·GameInstance에서 참조돼 에디터 시작이나 PIE에 로드되면 메뉴 맵에서만 쓰는 다른 BP를 고른다. 메뉴 맵이 없으면(W12 미완) W14 L_NetLab 맵의 BP를 쓴다(쿠킹 대상인지 확인). BP 에러로 쿠킹이 실패하지 않으면 마지막 대체로 게임 코드에서 WITH_EDITOR 전용 멤버(예: AActor::GetActorLabel)를 #if WITH_EDITOR 없이 부르게 한다(에디터 빌드는 되고 패키징의 게임 빌드 단계에서 실패, 2행은 '첫 Error 줄' 기준으로 같게 채점).
패키징 전에 BP 에러를 먼저 찾아 고쳤으면 PR에 위치·이유가 있을 때 2행은 최대 1.5. Shipping 데스크톱 빌드는 설치된 게임으로 취급돼(FApp::IsInstalled) Saved가 %LOCALAPPDATA%\<프로젝트>\Saved에 생기고, Shipping은 기본적으로 로그 파일을 남기지 않는다 — 둘 다 시험 PC에서 미리 확인한다(확인 필요). 다른 문항의 런타임 결함(P3-36)이 남아 있어 Development 로그에 에러가 남으면 5행은 '원인 기록'도 인정한다.

### P3-36 (1.69점) — 목표: W02-23, W02-30, W07-24, W11-17, W14-25, W15-10, C-54

**모범 답안**

- 심은 결함(채점자 시트): 카드 1 — 플레이어 캐릭터 OnRep_PlayerState의 ASC->InitAbilityActorInfo(클라 쪽 초기화) 호출 삭제. 카드 2 — 판정 함수의 '이번 휘두르기에 이미 맞힌 대상' 확인(TSet) 삭제 → 히트 윈도우 동안 프레임마다 같은 대상을 다시 맞힘.
- 카드 1 진단 예: 가설 ① 클라에 어빌리티가 부여되지 않았다(서버 로그에서 GiveAbility 정상 → 기각) ② 입력 바인딩 문제(로그 → 클라 입력 함수는 불림 → 기각) ③ 클라 ASC의 액터 정보가 초기화되지 않았다(클라 중단점: OnRep_PlayerState는 불리지만 Init 호출 없음, 콜스택 캡처, showdebug abilitysystem에 아바타 정보 없음 → 채택). 해결: OnRep_PlayerState에서 InitAbilityActorInfo(PS, this) 복구. 재발 방지: 'ASC 초기화는 서버 PossessedBy + 클라 OnRep_PlayerState 둘 다(W16)' 체크리스트와 2인 PIE 테스트 항목.
- 카드 2 진단 예: 가설 ① BT가 공격 태스크를 두 번 실행한다(Visual Logger BT 기록 → 공격 1회 → 기각) ② GE가 두 번 적용된다(로그 → 적용 위치는 판정 콜백 한 곳 → 원인 아님) ③ 대상당 1회 처리가 빠졌다(DrawDebug와 '프레임·대상' 히트 로그 → 같은 대상이 여러 프레임에 기록, t.MaxFPS를 바꾸면 횟수도 바뀜 → 채택). 해결: TSet 확인 복구, 윈도우 시작 때 Reset. 재발 방지: 히트 로그로 '휘두르기당 대상별 1회'를 확인하는 테스트·PR 체크리스트, 저프레임 확인.
- 도달성 3줄 예, 30초 버전 형식, 채점 핵심, 힌트 카드 규칙은 A형과 같다.

**채점표 (10점)**

- [2.5] TS-1(네트워크): 재현·원인 확인·수정, NetMode 로그와 (콜스택 또는 showdebug abilitysystem 캡처) 근거, 7칸(2.5) / 칸 누락 1~2개나 근거 하나 빠짐(1) / 없음(0)
- [2] TS-2(판정): 재현·수정, DrawDebug·프레임별 히트 로그 근거, 'BT 두 번 실행' 가설 행(Visual Logger 캡처), 7칸(2) / 칸이나 근거 누락(1) / 없음(0)
- [2] 두 TS의 가설·검증 표가 3행 이상(기각 가설 포함)이고 근거가 원인을 증명(2) / 한 TS만이거나 근거 약함(1) / 없음(0)
- [1.5] 재발 방지가 구체적 장치(테스트·체크리스트·규칙)이고 30초 버전을 채점자 앞에서 말함(1.5) / 하나만(0.5) / 없음(0)
- [1] 도달성 부록 3줄이 정확(루트 → UPROPERTY 참조 추적 → 도달 불가 수거 → 댕글링)(1) / 일부만 맞음(0.5) / 없음·틀림(0)
- [1] TIL ↔ TS 양방향 링크(1) / 한쪽만(0.5) / 없음(0)

> 검토에서 고친 점: A형 카드 1 결함(OnRep 안의 Broadcast 삭제)은 서버가 값을 바꿀 때 OnRep을 직접 부르는 흔한 구조에서 서버 화면도 깨뜨린다. 그러면 카드 문구('서버 화면은 정상')와 맞지 않는다. → ReplicatedUsing을 Replicated로 바꾸는 결함을 기본으로 했다(OnRep 함수와 서버 알림은 그대로 둔다). OnRep이 없으면 DOREPLIFETIME을 지우는 대체안을 적었다. / 45분에 버그 2개 진단·수정, PR 2개, TS 2건(7칸), TIL, 부록, 구술을 모두 하라고 했다. PR 2개는 '과제마다 PR 1개' 규칙보다 많고 시간도 모자란다. 근거 요구 '로그와 콜스택(두 창 캡처로 대신)'은 무엇을 대신하는지 모호하다. 힌트 카드 15분이 카드 전체 기준인지 카드마다인지도 불분명하다. → 두 수정과 TS·TIL을 PR 하나로 묶고, 칸마다 1~3줄이면 되게 했다. 근거는 'NetMode 로그 + (콜스택 또는 두 창/showdebug 캡처)'로, 힌트 카드는 카드마다 15분으로 정했다. / 도달성 행은 0/완료 두 단계뿐이다. W07-24·W11-17의 coverage는 한 형에서 TS 전체로 시험하는 것처럼 적혀 있었지만, 실제로는 가설 1행으로만 확인된다. → 도달성 행에 부분 점수(0.5)를 넣었다. coverage에는 형별로 무엇이 TS 전체이고 무엇이 가설 행인지 사실대로 적고, 가설 행에 근거 캡처를 채점 조건으로 넣었다.

> 작성 메모: [준비] 공통 준비는 P3-41 notes. 형별 런타임 결함 2개를 심고, 카드 문구의 증상이 2인 PIE·1인 PIE에서 그대로 나오는지 리허설한다.
A형 카드 1(네트워크): GameState(W12·W15)의 웨이브 번호나 남은 적 수 UPROPERTY에서 ReplicatedUsing=OnRep_…를 Replicated로 바꾼다(OnRep 함수와 서버 쪽 알림 코드는 그대로 둔다 → 서버 화면은 정상, 클라 HUD만 멈춘다). 이전 안(OnRep 안의 Broadcast 삭제)은 서버가 값을 바꿀 때 OnRep을 직접 부르는 흔한 구조에서 서버 화면도 깨져 카드 문구와 달라 바꿨다. GameState에 OnRep이 없으면 그 값의 DOREPLIFETIME 줄을 지운다.
A형 카드 2(AI): UBTService_UpdateTargetDistance(W10)가 거리를 쓰는 Blackboard 키를 다른 키로 바꾼다(FName 오타나 BT 에셋 서비스 노드의 키 선택 변경). 거리 키가 기본값 0에 머물러 '사거리 안' 조건이 항상 참이 된다. 사거리 판단을 다른 방식으로 하면 그 판단이 항상 '사거리 안'이 되게 같은 역할의 한 줄을 바꾼다.
B형 카드 1(네트워크): 플레이어 캐릭터 OnRep_PlayerState의 ASC->InitAbilityActorInfo(클라 쪽 초기화) 호출을 지운다(W16, 서버 PossessedBy 쪽은 그대로). ASC 위치가 다르면 클라 쪽 초기화 호출을 지운다.
B형 카드 2(판정): 판정 함수(W7 Sweep, W17 GA에서 재사용)에서 '이번 휘두르기에 이미 맞힌 대상' 확인(TSet Contains/Add 또는 AddUnique)을 지워, 히트 윈도우 동안 같은 대상이 프레임마다 다시 맞게 한다.
증상이 카드와 다르게 나오면 카드 문구를 실제 증상에 맞춘다. 카드 2장과 힌트 카드(원인 파일 이름)를 인쇄한다. 버그를 채점자가 심으므로 모든 응시자가 실제로 겪는다. 응시자가 다른 문항 중에 이 결함을 먼저 고쳤다면 그 PR로 TS를 쓰게 하고 감점하지 않는다. A형은 AI·네트워크, B형은 판정·네트워크로 나누고, 각 형의 TS-2에 다른 분야 가설 1행(근거 캡처 포함)을 넣게 했다. W02-23(도달성)은 두 버그가 GC와 무관해도 부록 3줄로 확인한다. 45분에 맞추려고 두 수정과 TS·TIL을 PR 하나로 묶었고(과제마다 PR 1개 규칙), 칸마다 1~3줄이면 되게 했다. 힌트 카드는 카드마다 15분 기준이다. 시험 TIL은 docs/exam/til-block3.md.

## 3부-P 포트폴리오 심사 (33.1점 · 시험 전 제출 + 구술 40분)

- 시험 7일 전, 게임 저장소 UE5-ActionArena(태그 exam-submit)와 학습 로그 저장소 unreal-study-log 링크를 낸다. 채점자는 시험 전에 이슈·PR·커밋 이력, docs, README, 릴리즈, GIF·영상, Shipping zip을 심사한다.
- 아래 항목은 미리 공개하는 심사 기준이다(A·B형 공통). 클래스·파일 이름은 커리큘럼 이름 기준이며, 같은 역할이면 이름이 달라도 인정한다.
- 진위 규칙: 구술(P3-42)에서 채점자가 심사 항목 3개를 골라 핵심 코드·결정을 설명하게 한다. 설명하지 못한 항목은 그 항목 점수의 50%만 인정한다. 커리큘럼 AI 레벨 안의 AI 활용은 감점하지 않는다. PR 'AI 활용' 칸이 사실과 달라 보이면 그 항목을 구술 후보로 먼저 고른다.

### P3-03 (0.42점) — 목표: W00-25, C-36, W01-22, W01-26, C-42, C-43, C-55

**모범 답안**

- 여는 순서(약 10분): ① unreal-study-log → Commits ② 게임 저장소 Issues → Labels ③ Issues → Milestones(Open·Closed 탭) ④ Projects 탭 ⑤ Pull requests(is:pr is:merged)에서 W01 PR 전부와 표본 기능 PR 10개 ⑥ Milestones에서 마일스톤마다 이슈 목록(Oldest 순).
- ① W1 시작 전 주(W00)의 커밋(빌드 시간 기록 TIL 등)이 있고, 그 뒤 'docs(til): …'처럼 직접 쓴 메시지의 커밋이 이어지면 로컬 Clone을 쓴 것이다. 커밋이 대부분 웹 기본 메시지('Add files via upload', 'Create …', 'Update …')면 로컬 Clone 증거가 약하다(1점). HTML 카드가 만든 기록 하나 이상(TIL의 '# 📅 날짜 | 주제'와 '> WNN Day n' 줄, PR 본문의 '- 주차: WNN · …' 줄, Devlog 초안의 '근거(PR·커밋 링크)' 표)이 있으면 커리큘럼 HTML을 브라우저로 연 증거다. 하나도 없으면 ①은 1점까지.
- ③ W1 시작일은 docs/devlog/W01.md 제목의 날짜 범위로 정한다(HTML 초안이면 '(12/07(월) ~ 12/13(일))'처럼 들어 있다). 없으면 게임 저장소 첫 커밋이 있는 주의 월요일. 마감일 = W1 월요일 + 27·55·83·111·139·167일(= W04·W08·W12·W16·W20·W24의 일요일). 예: W1이 2026-12-07(월)이면 M1 2027-01-03, M2 01-31, M3 02-28, M4 03-28, M5 04-25, M6 05-23. 버퍼(최대 2주)로 옮긴 마감일은 1~2주 뒤 일요일이고 회고나 Devlog에 버퍼 사용이 적혀 있으면 인정.
- ④ PR 오른쪽 Development에 연결 이슈가 있고, 이슈 타임라인에 'closed this as completed in #N'이 있으면 자동 닫힘이다. Milestone은 PR 오른쪽 칸(없으면 연결 이슈의 칸)을 본다. W01 PR은 머지 뒤 채운 것도 인정한다: 'added this to the M1 milestone' 기록, 머지 뒤 본문에 적은 #N(이슈 타임라인에 'mentioned this'), 손으로 닫은 이슈. 표본 기능 PR은 Closes #N 자동 닫힘과 마일스톤이 둘 다 있어야 1개로 센다.
- ⑤ 마일스톤을 하나씩 열어 이슈 생성일을 본다. 통과 단계: 과제 이슈가 서로 다른 3주 이상에 나뉘어 생김, 지난 단계라면 열린 과제 이슈가 없고 마일스톤이 Closed 탭에 있음. 이슈를 PR 머지 뒤 몇 분 만에 만들고 바로 닫은 것(사후 기록)이 그 단계 이슈의 절반 이상이면 불통과. M6은 열려 있어도 된다. 남은 할 일·Known Issues 버그가 열려 있는 것은 정상.
- 만점 예: W00부터 Desktop 커밋이 이어지고 TIL이 HTML 카드 형식, 라벨 4종 + Board, 마감일 6개 정확, W01 PR 3개 모두 연결(1개는 머지 뒤 M1 추가), 표본 9/10, 6단계 모두 통과. 부분 예: Board 없음(② 1점), M5·M6 마감일이 토요일(③ 1점), W01 PR에 마일스톤 없음(④ 1점), M4·M5 이슈를 PR 머지 뒤 한꺼번에 만들어 닫음(⑤ 4단계 통과 1점).
- 구술 질문(의심될 때, P3-42에서 뽑혔을 때): '학습 로그 저장소를 어느 경로에 Clone했고, GitHub Desktop에서 그 폴더를 탐색기로 여는 메뉴는?'(C:\Projects\unreal-study-log, Repository → Show in Explorer) / 'M3 마감일은 어떻게 정했나? Closes #N은 언제 이슈를 닫나?'(M3 = W09~W12, W12의 일요일. PR이 main에 머지될 때 닫힌다).

**채점표 (10점)**

- [2] ① unreal-study-log에 W00 커밋이 있고 그 뒤 Desktop에서 직접 쓴 메시지의 커밋이 이어지며, HTML 카드가 만든 기록이 있음(2) / W01부터만 있거나, 웹 업로드 메시지가 절반 이상이거나, HTML 카드 기록이 없음(1) / 커밋 없음(0)
- [2] ② 라벨 feat·bug·docs·perf와 Projects Board(둘 다 2 / 하나 1 / 없음 0)
- [2] ③ M1~M6 마감일이 각 단계 마지막 주 일요일, 버퍼로 옮긴 것은 기록이 있으면 인정(6개 2 / 4~5개 1 / 3개 이하 0)
- [2] ④ W01 PR 전부에 이슈 연결과 M1(머지 뒤 채운 것 인정), 표본 기능 PR 10개 중 Closes #N 자동 닫힘과 마일스톤이 함께 있는 PR(W01 전부 + 8개 이상 2 / W01 일부 누락이거나 5~7개 1 / 4개 이하 0)
- [2] ⑤ 통과 단계 수: 과제 이슈가 서로 다른 3주 이상에 나뉘어 생기고 사후 기록이 절반 미만, 지난 단계는 열린 과제 이슈 없이 마일스톤 Closed, M6은 열려 있어도 됨(6단계 2 / 4~5단계 1 / 3단계 이하 0)

> 검토에서 고친 점: ④가 W01 PR 전부에 'Closes #N 자동 닫힘'을 요구한다. 커리큘럼은 W01 첫 PR의 이슈를 '이슈 먼저 (선택)'으로 두고, W01 과제6(PR 흐름 점검)은 머지가 끝난 뒤 '빠진 것 채우기'라서 자동 닫힘이 원래 불가능할 수 있다. → W01 PR은 이슈 연결과 M1만 보고, 머지 뒤 채운 기록(added this to the M1 milestone, #N 언급, 손으로 닫은 이슈)도 인정했다. 자동 닫힘은 표본 기능 PR에서만 본다. / ④ 표본 기준(10개 중 9개)이 너무 높다. HTML PR 카드의 이슈 번호 칸은 '없으면 비움'이고, 커리큘럼 '어디에 무엇을 남기나' 표도 이슈를 '(선택)'으로 둔다. → 표본 기준을 8개 이상이면 2점, 5~7개면 1점으로 낮췄다. / ⑤ 기준('일부 주 빠짐', '몰아서 생성', '방치')이 주관적이라 0/부분/완료를 판정하기 어렵다. → 단계(마일스톤)마다 통과 여부를 본다. 통과 조건은 이슈가 서로 다른 3주 이상에 나뉘어 생김, 사후 기록이 절반 미만, 지난 단계는 열린 과제 이슈 없이 Closed. 6단계면 2점, 4~5단계면 1점, 3단계 이하는 0점. / C-36의 '커리큘럼 HTML을 Chrome/Edge로 연다'는 coverage에만 있고 채점표 기준에는 없다. → ① 2점 조건에 'HTML 카드가 만든 기록(TIL 📅 머리글, PR 본문의 - 주차: WNN 줄, Devlog 초안)'을 넣었다. 하나도 없으면 ①은 1점까지다. / ③ '일정을 옮겼다면 이유를 회고에 적는다'가 커리큘럼에 없는 일반 요구처럼 읽힌다. 마감일 판정 근거도 흐리다. → 버퍼(최대 2주)로 옮긴 경우에만 기록이 있으면 인정하도록 바꿨다. 마감일 판정은 Devlog W01 제목의 날짜 범위와 W04·W08…의 일요일을 기준으로 적었다.

> 작성 메모: 배점 50×1÷118 ≈ 0.42점. 심사 약 10분. 표본 기능 PR 10개 = P3-05 표본 8개 + 2개(P3-04 표본과 겹쳐도 된다). 이슈·PR·마일스톤은 exam-submit 태그에 묶이지 않으므로 제출일(시험 7일 전) 뒤에 만들거나 고친 것은 타임라인 시각으로 걸러 보지 않는다. W01 첫 PR의 이슈는 커리큘럼에서 '이슈 먼저 (선택)'이고, W01 과제6(PR 흐름 점검)은 머지가 끝난 뒤 '빠진 것 채우기'라서 W01 PR에는 자동 닫힘을 요구하지 않는다. HTML PR 카드의 이슈 번호 칸이 '없으면 비움'이라 표본 기준은 10개 중 8개로 둔다. 마감일은 학생별 실제 W1 시작일로 채점한다. 이름이 커리큘럼과 달라도 같은 역할이면 인정. P3-42 진위 확인에 뽑히면 answer_key의 구술 질문을 쓰고, 설명하지 못하면 이 문항 점수의 50%만 준다.

### P3-04 (1.27점) — 목표: W01-42, W01-43, C-44, C-45, W01-25, W01-34

**모범 답안**

- 여는 순서(약 12분): ① 머지된 PR 목록(is:pr is:merged)에서 단계마다 2개, 표본 12개 ② PR 머리글의 브랜치 이름('merged N commits into main from feat/…')과 Commits 탭 ③ 표본 3개는 Commits 탭 첫 커밋을 열어 '1 parent' 옆 해시 ④ Code 탭에서 Source·Content·Config 폴더를 열고 오른쪽 위 History ⑤ unreal-study-log → ue5-til 폴더 History, 게임 저장소 docs/devlog 폴더 History.
- ① type 접두사 + 기능 이름이면 통과. 'patch-1', 'test', 'my-branch', 날짜뿐인 이름은 불통과.
- ② 표본 PR의 Commits 탭과 main 문서 커밋에서 20개를 본다. type이 맞고 요약이 무엇을 바꿨는지 말하면 통과(왜까지 있으면 더 좋다). 'docs(til): …', 'docs(devlog): W05 주간 기록' 같은 HTML 카드 메시지, scope가 없는 'chore: UE 5.8 프로젝트 생성'도 통과. 'update', 'fix', 'wip', 'asdf', 'Add files via upload'는 불통과.
- ③ Squash 커밋은 GitHub의 main에만 생긴다. 머지 뒤 Pull하지 않은 로컬 main에서 New Branch를 만들면 직전 Squash 커밋이 없는 옛 main에서 갈라진다. 표본 PR 3개의 첫 커밋 parent가 '그 첫 커밋 시각 전에 머지된 마지막 PR의 Squash 커밋'이거나 그 뒤의 main 커밋이면 통과. Desktop 버전에 따라 새 브랜치를 origin/main 기준으로 만들 수도 있으므로(확인 필요) 이 기준은 '최신이면 통과'로만 쓴다. main 커밋 목록에서 'Merge branch 'main' of https://github.com/…' 커밋을 센다. Pull 없이 main에 문서를 커밋하고 Push가 막혀 생긴 흔적이다.
- ④ 폴더 History는 그 폴더를 바꾼 커밋만 보여 준다. 제목 끝에 (#N)이 없는 커밋이 PR 없이 들어간 코드 커밋이다. Content/·Config/도 같다. W01 첫 커밋(chore: UE 5.8 프로젝트 생성)은 뺀다.
- ⑤ ue5-til 파일 수를 세고, History 날짜에서 몰아 올린 날(하루에 TIL 7개 이상)을 찾는다. Devlog는 W01~W24 파일 중 커밋 날짜가 그 주 일요일 ±3일 안인 것만 센다(주는 HTML 초안 제목의 날짜 범위로 정한다).
- 만점 예: 브랜치 12/12, 커밋 19/20, parent 3/3, Merge branch 커밋 1개, 직접 코드 커밋 0, TIL 130개·제때 Devlog 23편·몰아 올린 날 0. 부분 예: M1 기간 커밋이 'update'뿐(② 1점), 표본 parent 2/3(③ 1점), M3 TIL 10개를 한 날에 올림(⑤ 1점).
- 구술 질문(의심될 때): '새 기능 브랜치를 만들기 직전 GitHub Desktop에서 무엇을 누르나? 안 하면 어떤 일이 생기나?'(main → Fetch origin → Pull origin → New Branch. 안 하면 직전 Squash 커밋이 없는 옛 main에서 갈라져 충돌·누락) / 'main에서 커밋 전에 작업을 시작해 버렸다면? 머지 뒤 로컬 브랜치는 어떻게 정리하나?'(New Branch → 'Bring my changes to …'. main으로 돌아와 Pull origin → Branch → Delete…).

**채점표 (10점)**

- [2] ① 표본 PR 12개의 브랜치 이름이 'type/기능'(11개 이상 2 / 8~10개 1 / 7개 이하 0)
- [2] ② 커밋 표본 20개가 '<type>(<scope>): 무엇을' 형식이고 무엇을 바꿨는지 알 수 있음, scope 생략은 통과(18개 이상 2 / 12~17개 1 / 11개 이하 0)
- [2] ③ 표본 PR 3개의 첫 커밋 parent가 그 시각의 최신 main(3개 2 / 2개 1 / 1개 이하 0). main에 'Merge branch 'main' of …' 커밋이 4개 이상이면 한 단계 낮춤
- [2] ④ Source/·Content/·Config/를 바꾼 main 커밋 중 PR 없이(제목 끝 (#N) 없음) 들어간 것, W01 첫 커밋 제외(0개 2 / 1~2개 1 / 3개 이상 0)
- [2] ⑤ TIL 100개 이상·제때 올린 Devlog 20편 이상·몰아 올린 날 0일(2) / TIL 50개 이상·Devlog 12편 이상·몰아 올린 날 2일 이하(1) / 그 아래(0). 몰아 올린 날 = 하루에 TIL 7개 이상, 제때 = 그 주 일요일 ±3일

> 검토에서 고친 점: ③의 'Merge branch 흔적이 거의 없음/잦음'이 주관적이다. 'parent가 최신 main'인지 무엇을 기준으로 판정하는지도 흐리다. 또 '머지 뒤 Pull 안 하면 반드시 옛 main에서 갈라진다'는 GitHub Desktop 동작은 확실하지 않다. → parent 기준을 '첫 커밋 시각 전에 머지된 마지막 PR의 Squash 커밋 또는 그 뒤 커밋'으로 정했다. Merge branch 커밋이 4개 이상이면 한 단계 낮춘다. Desktop의 새 브랜치 기준은 '(확인 필요)'로 표시하고, 이 기준은 '최신이면 통과'로만 쓴다고 적었다. / ④는 main 커밋 중 (#N)이 없는 것을 모두 열어 보게 해 비효율적이다. 문서 커밋만 수십 개다. → Source·Content·Config 폴더의 History에서 (#N)이 없는 커밋만 찾도록 바꿨다. / ⑤ 등급 사이에 빈칸과 겹침이 있다(예: TIL 120개인데 몰아 올린 날 3일이면 판정 불가). '몰아 올린 날'과 '제때'의 정의도 없다. → 등급을 2점(TIL 100+, 제때 Devlog 20+, 몰아 0일), 1점(TIL 50+, Devlog 12+, 몰아 2일 이하), 0점(그 아래)으로 정했다. 몰아 올린 날은 하루 TIL 7개 이상, 제때는 그 주 일요일 ±3일로 정의했다. / ② 채점표는 '무엇을, 왜'를 요구하는데 answer_key는 '되도록 왜'라서 서로 맞지 않는다. HTML 카드 기본 메시지에는 '왜'가 없다. → 기준을 '<type>(<scope>): 무엇을' 형식과 무엇을 바꿨는지 알 수 있는지로 맞췄다. 왜는 가산 요소다.

> 작성 메모: 배점 50×3÷118 ≈ 1.27점. 심사 약 12분. 표본 PR 12개 = P3-05 표본 8개 + 4개(단계마다 2개). Squash merge라 브랜치 커밋은 PR의 Commits 탭에만 남는다(원격 브랜치를 지워도 PR 페이지에서 보인다). 이슈·PR은 exam-submit 태그에 묶이지 않으므로 제출일 뒤 기록은 보지 않는다. 원격 선행 커밋 대응·main에서 시작한 변경 옮기기는 라이브 P3-41에서, 이 문항은 6개월 이력으로 본다. 브랜치 이름은 커리큘럼 이름 기준, 같은 역할이면 다른 이름도 인정. P3-42 진위 확인에 뽑히면 구술 질문 2개를 쓰고, 설명하지 못하면 이 문항 점수의 50%만 준다.

### P3-05 (1.69점) — 목표: W01-25, W01-27, W01-44, C-27, C-46, C-47, C-48

**모범 답안**

- 여는 순서(약 16분, PR당 2분): 표본 8개마다 Conversation(본문·GIF·머지 방식·브랜치 삭제) → Files changed(셀프 코멘트).
- ① 안내 문구('(무엇을 만들었고 왜 이렇게 했는지 — 내 말로)', '- 재현 단계: (1. … 2. …)')가 그대로면 빈칸이다. 재현 단계는 번호 붙은 확인 순서(예: 'BP_FloatingItem 3개 배치 → Play → 높이·속도가 다른지'). W14 이후 PR(표본의 W15·W17·W20)은 'PIE 2인 Listen Server + 지연 200ms' 줄이 체크되어 있어야 한다. 변경 사항은 무엇을/왜 아래 목록이어도 된다. 셀프 리뷰 체크가 전부 빈 상자면 그 칸은 빈칸.
- ② 화면 변화가 없는 리팩터링·문서 PR은 빼고 센다. 본문에서 재생되는지 본다.
- ③ 같은 주 Devlog의 'AI 활용 회고', TIL, 학습 로그 ai-off/ 기록과 맞춰 본다. 구체적 = 사용 범위와 '내가 검증·수정한 것'에 실제 내용(API·함수 이름, 엔진 소스·공식 문서로 확인한 것, 고친 줄)이 있음. W1~W8(L1)은 'AI 초안 + 모든 줄 해설·검증', W9~W20(L2)은 '내가 작성 + AI 리뷰 의견의 채택/거절 이유', W17~(L3)은 'AI 없이 작성 + AI로 검증'이 자연스럽다. AI를 안 썼으면 '사용 안 함'도 구체적인 답이다. PR은 '사용 안 함'인데 다른 기록에 같은 코드를 AI가 짰다고 적혀 있으면 ③은 0점. 레벨을 넘은 사용도 사실대로 적었으면 깎지 않고 구술 질문 후보로 메모한다.
- ④ 줄 코멘트는 Conversation 탭에도 파일 줄과 함께 보인다. '좋음', 'LGTM'처럼 이유가 없으면 불통과.
- ⑤ PR에 'merged commit … into main'과 'deleted the … branch'가 있고, main에는 PR당 커밋 1개(제목 끝 (#N))가 있다. 'Merge pull request #N from …' 커밋이면 Squash가 아니다.
- ⑥ 기대 답 네 가지: main은 항상 실행되는 본편이고 새 기능은 feat/ 분기, PR은 무엇을·왜·테스트를 남기는 작업 보고서(포트폴리오에서 가장 많이 읽힘), Squash and merge는 커밋을 하나로 묶어 main 이력을 정리, 혼자여도 main을 깨지 않고 근거를 남기려고 PR을 거친다.
- 만점 예: 8개 모두 칸·재현 단계, 기능 PR GIF 6/6, AI 칸 7/8 구체적이고 Devlog와 맞음, 셀프 코멘트 7/8, 모두 Squash·브랜치 삭제, W01 Devlog에 이유. 부분 예: W01·W04 PR은 칸이 비고 W07부터 채움(① 6개 1점), GIF 3/6(② 1점), L2 PR에 채택/거절 이유 없이 '리뷰'만 적음(③ 1점).
- 구술 질문(의심될 때): '이 PR(채점자가 고른 1개)에서 셀프 코멘트를 단 줄은 왜 그렇게 짰나?' / '혼자인데 왜 PR을 거치고, 왜 Squash and merge를 골랐나?'

**채점표 (10점)**

- [2] ① 표본 8개 중 본문 칸이 내 말로 채워진 PR: 무엇을/왜, 번호 붙은 재현 단계, W14 이후는 2인 PIE 줄 체크, 셀프 리뷰 체크 표시(7개 이상 2 / 4~6개 1 / 3개 이하 0)
- [2] ② 화면이 바뀌는 표본 PR의 GIF·영상(빠진 것 1개 이하 2 / 절반 이상 있음 1 / 절반 미만 0)
- [2] ③ AI 활용 칸이 구체적인 PR(사용 범위·검증한 것, L2부터 채택/거절 이유, 안 썼으면 '사용 안 함')(6개 이상 2 / 3~5개 1 / 2개 이하 0). 다른 기록과 모순 1건이면 0
- [2] ④ '왜'를 말하는 줄 셀프 코멘트(W01 PR 포함 8개 중 6개 이상 2 / 3~5개 1 / 2개 이하 0)
- [1] ⑤ Squash and merge와 원격 브랜치 삭제(8개 모두 1 / 5~7개 0.5 / 4개 이하 0)
- [1] ⑥ 브랜치·PR·Squash의 의미와 혼자여도 PR을 거치는 이유를 기록이나 구술로 설명(네 가지 1 / 일부 0.5 / 없음 0)

> 검토에서 고친 점: ① 본문 칸 기준에 Closes #N이 들어 있다. 같은 결함을 P3-03 ④와 이중으로 감점하고, 이슈는 커리큘럼상 선택이다. → ①에서 Closes #N을 빼고 이슈 연결은 P3-03 ④에서만 채점한다고 적었다. / 표본 정의(W01 + M1 1 + M2 2 + M3 2 + M4 1 + M5 2)를 세면 9개라서 '8개'와 맞지 않는다. evidence_weeks에도 M3 주차(W10~W12)가 없다. → 표본 8개를 주차로 못박았다(W01·W04·W07·W08·W10~W12 중 1·W15·W17·W20). evidence_weeks에 W10·W12를 넣었다. / ② '모두'여야 만점이라 GIF 하나만 빠져도 1점이 된다. 성실한 수료생도 감점된다. → 빠진 것이 1개 이하면 2점으로 바꿨다. / ③ AI 활용 칸 기준에 개수가 없어 '구체적/형식적'을 주관적으로 판정하게 된다. → 표본 8개 중 구체적인 PR 수(6개 이상 2점, 3~5개 1점)로 판정한다. '구체적'은 API 이름, 확인한 소스, 고친 줄 같은 실제 내용으로 정의했다. 다른 기록과 모순이 1건이라도 있으면 0점이다. / ⑤ '일부 0.5'의 범위가 정해져 있지 않다. → 8개 모두면 1점, 5~7개면 0.5점, 4개 이하면 0점으로 정했다.

> 작성 메모: 배점 50×4÷118 ≈ 1.69점. 심사 약 16분(PR당 2분). 표본 8개는 P3-03·P3-04 표본에 그대로 쓴다. 포트폴리오 PR은 그 주 AI 레벨(L1 W1~W8, L2 W9~W20, L3 W17~)대로 쓴 것이 정상이고, 사실대로 적었는지만 본다. 레벨을 넘은 사용도 사실대로 적었으면 감점하지 않는다. 이슈 연결(Closes #N)은 P3-03 ④에서 채점하므로 여기서는 보지 않는다(이중 감점 방지). ⑥은 기록에 없으면 P3-42 구술 때 1분 질문으로 확인한다(진위 확인 3문항과 별개). 진위 확인에 뽑히면 셀프 코멘트 줄 설명을 시키고, 설명하지 못하면 이 문항 점수의 50%만 준다. 이슈·PR은 태그에 묶이지 않으므로 제출일 뒤 본문 수정('edited' 기록)은 보지 않는다.

### P3-08 (0.85점) — 목표: W03-25, W03-11

**모범 답안**

[여는 곳·순서]
1. GitHub PR 검색: is:pr is:merged head:refactor/float-motion-component. 없으면 W03 기간 PR을 제목과 Files changed로 찾는다. 본문·GIF·테스트 방법·AI 활용 칸을 본다.
2. exam-submit 코드: git grep -n -e bCanEverTick -e bStartWithTickEnabled -e SetComponentTickEnabled -e SetComponentTickInterval -e Activate -- Source. 컴포넌트 .h/.cpp와 AFloatingItem .h/.cpp를 연다. 컴포넌트를 붙인 다른 BP는 에디터 Reference Viewer로 찾는다.
3. 설명 위치: PR 본문 → docs/devlog/W03.md → unreal-study-log/ue5-til(W03 기간) → docs/adr/ADR-0001-interaction-detection.md → 컴포넌트 코드 주석 순서로 찾는다.
4. 타이머 대체 사용처: W05 UInteractionComponent의 SetTimer(0.1초).
[정답 예]
- 생성자: PrimaryComponentTick.bCanEverTick = true; PrimaryComponentTick.bStartWithTickEnabled = false;
- 켜기/끄기: SetComponentTickEnabled(true/false)를 부르는 함수(예: StartFloating/StopFloating)가 있다. 또는 옵션(예: bFloatOnStart)이 켜져 있을 때만 BeginPlay에서 켠다. Activate()/Deactivate()로 켜고 끄는 것도 정답이다(UActorComponent::Activate·Deactivate가 SetComponentTickEnabled를 부른다. ActorComponent.cpp에서 확인). 단, bAutoActivate만 false로 두고 bStartWithTickEnabled를 그대로 두면 시작부터 Tick이 돌 수 있으니(확인 필요) 시작 상태는 테스트 방법 기록이나 구술로 확인한다.
- TickComponent: GetOwner()->SetActorLocation / AddActorLocalRotation(또는 SetActorLocationAndRotation). 소유 액터 클래스를 include하거나 Cast하지 않는다.
- AFloatingItem: PrimaryActorTick.bCanEverTick = false이고 Tick override가 없다.
- 4가지: bCanEverTick 기본 false, 필요할 때만 켜기(SetActorTickEnabled/SetComponentTickEnabled), TickInterval로 주기 낮추기, 타이머·델리게이트로 대체.
[만점 예] 위 코드가 있다. PR GIF에서 BP_FloatingItem과 메시만 있는 다른 BP가 함께 떠다닌다. 테스트 방법에 'TickComponent 중단점이 Start 호출 뒤에만 걸림'이 있다. TIL이나 ADR-0001에 4가지와 W05 타이머 사용처가 있다.
[부분 예]
- AFloatingItem에서 Tick 함수는 지웠지만 bCanEverTick = true가 남아 있다 → 기준1 1.
- 컴포넌트가 Cast<AFloatingItem>을 쓴다. 또는 GIF·다른 BP가 없고 채점자 에디터 확인도 실패한다 → 기준2 1.
- 컴포넌트는 있지만 bStartWithTickEnabled가 기본값(켜짐) 그대로이고 켜고 끄는 경로가 없다 → 기준3 0.
- 기본은 꺼져 있지만 BeginPlay에서 조건 없이 켠다 → 기준3 1.
- PR에 GIF는 있지만 Tick 확인 방법이 없다 → 기준4 1.
- 4가지 중 2~3개만 적었거나, 4가지를 적었지만 저장소 사용처가 없다 → 기준5 1.
[구술 질문(의심될 때)]
- 이 컴포넌트의 Tick이 처음 켜지는 줄을 짚어 주세요. bCanEverTick과 bStartWithTickEnabled는 어떻게 다른가요? (bCanEverTick이 false면 Tick 함수가 등록되지 않아 나중에 켤 수 없다. bStartWithTickEnabled는 시작 상태만 정한다)
- TickInterval을 0.25초로 하면 움직임이 어떻게 보이나요? (1초에 4번만 갱신돼 뚝뚝 끊긴다. DeltaTime이 약 0.25로 들어오므로 위치 계산 자체는 맞다)

**채점표 (10점)**

- [2] 로직을 컴포넌트로 옮김, AFloatingItem에 떠다니기 Tick 코드 없음 + bCanEverTick false(2/Tick 코드나 bCanEverTick true가 남음 1/컴포넌트 없음 0)
- [2] GetOwner만 쓰고(소유 액터 include·Cast 없음) 다른 액터에서도 동작: GIF·다른 BP·채점자 에디터 확인 중 하나(2/Cast 사용 또는 다른 액터 동작 확인 안 됨 1/동작 안 함 0)
- [2] 컴포넌트 Tick 기본 꺼짐 + 켜고 끄는 경로가 코드에 있음(2/기본 꺼짐이지만 BeginPlay에서 조건 없이 켬 1/기본 켜짐·경로 없음 0)
- [2] W03 PR(또는 Devlog W03)에 동작 GIF + Tick이 필요할 때만 도는지 확인한 방법(2/하나만 1/둘 다 없음 0)
- [2] Tick 비용 줄이는 방법 4가지 설명 + 저장소 사용처 1곳 이상(2/2~3가지 또는 사용처 없음 1/1가지 이하 0)

> 검토에서 고친 점: W03-11의 첫 방법(액터 bCanEverTick 기본 false)이 채점표에 없었다. answer_key는 'bCanEverTick false이거나 Tick override 없음'이라 Tick override만 지우고 bCanEverTick true가 남아도 만점이었다. → 기준1에 'AFloatingItem bCanEverTick false'를 넣었다. Tick 코드나 bCanEverTick true가 남으면 1점으로 정했고, coverage에 W03-11 → 기준1을 더했다. / 기준2가 '서로 다른 액터 2개 이상이 떠다니는 GIF'를 요구했다. 커리큘럼은 '어떤 액터에 붙여도 동작'만 요구하고 그런 GIF를 만들게 하지 않는다. → GIF, 다른 BP·맵 배치, 채점자의 에디터 확인(큐브 액터에 붙여 Play) 중 하나로 인정하게 바꿨다. 0/1/2 판정 조건도 적었다. / 'bAutoActivate = false + Activate()/Deactivate()도 정답'은 오해를 부를 수 있다. bStartWithTickEnabled가 기본값이면 활성화 전에도 Tick이 돌 수 있다. → Activate/Deactivate가 SetComponentTickEnabled를 부르는 것은 그대로 두고, 시작 상태는 bStartWithTickEnabled로 정해진다고 적었다. 확실하지 않은 동작에는 '(확인 필요)'를 붙였다. / notes에 'L1 주차인데 전부 직접 작성이면 구술 대상으로 먼저 고른다'가 있었다. L1 방식(AI 초안 → 학생 해설)에서도 학생이 다시 타이핑하므로, 이 기준은 정직한 학생을 의심하게 만든다. → '칸이 비어 있거나 실제 코드와 맞지 않아 보이면 구술 후보로 고른다(감점 없음)'로 바꿨다. W04 AI-Off ① AFloatingItem은 채점 대상이 아니라는 메모와, 설명 위치로 코드 주석(L1 해설 주석)을 더했다. / 채점 기준 여러 개에 0점 조건이 없었고, 기준5는 '저장소 사용처'를 빠뜨렸을 때 몇 점인지 정하지 않았다. → 모든 기준을 2/1/0으로 나눴다. 기준5는 '2~3가지 또는 사용처 없음 1, 1가지 이하 0'으로 정했다.

> 작성 메모: 채점자 준비: exam-submit 태그를 블록3용과 다른 폴더에 클론해 둔다(결함을 심지 않은 사본). 문항 점수 = 50×2÷118 ≈ 0.85점이고, 채점표 점수÷10을 곱한다. 진위: 구술(P3-42)에서 이 항목이 뽑혔는데 설명하지 못하면 이 문항 점수의 50%만 인정한다. AI: W03은 AI 레벨 L1(AI 초안 → 학생이 모든 줄에 해설 주석)이라 AI가 초안을 썼어도 감점하지 않는다. PR 'AI 활용 내역'이 정직한지만 본다. 칸이 비어 있거나 실제 코드와 맞지 않아 보이면 이 항목을 구술 후보로 고른다(그 자체로 감점하지 않는다). 컴포넌트 이름이 바뀌었거나 다른 액터에서만 쓰여도 같은 역할이면 인정한다. W04 AI-Off ①에서 다시 쓴 AFloatingItem(Tick 사용)이 따로 있으면 채점 대상이 아니다. W03 리팩터링 PR이 바꾼 클래스를 본다. TickInterval은 커리큘럼 과제가 코드로 요구하지 않으므로 코드에 없어도 감점하지 않고 기준5 설명으로 확인한다. 컴포넌트용 Tick 함수(SetComponentTickEnabled·SetComponentTickInterval)와 PrimaryComponentTick은 ActorComponent.h에 있다. 기준2에서 GIF나 다른 BP가 없으면 채점자가 에디터에서 큐브 액터에 컴포넌트를 붙이고, 코드에 있는 켜는 경로(옵션·함수)로 Play해 확인한다(5분 이내).

### P3-11 (1.27점) — 목표: W06-05, W06-13, W06-14, W06-17

**모범 답안**

[여는 곳·순서]
1. PR 검색: is:pr is:merged head:feat/anim-instance. GIF·캡처·AI 활용 칸을 본다.
2. exam-submit 코드: git grep -n -e NativeInitializeAnimation -e NativeUpdateAnimation -e NativeThreadSafeUpdateAnimation -e TryGetPawnOwner -- Source.
3. 에디터(결함을 심지 않은 사본, 외부 에셋을 넣은 뒤): 플레이어 BP의 Mesh 컴포넌트 → Details의 Anim Class → 그 ABP 열기 → 툴바 Class Settings → Parent Class → AnimGraph(블렌드스페이스·상태 머신·전이 규칙) → Event Graph 순서로 본다.
4. Shipping zip 실행(GIF가 없거나 흐릴 때): 걷기 → 질주(Shift) → 점프 → 착지.
[정답 예]
- .h: UPROPERTY(BlueprintReadOnly) Speed·Direction·bIsInAir·bIsAccelerating. UPROPERTY(Transient) TObjectPtr<ACharacter> Character와 TObjectPtr<UCharacterMovementComponent> Movement(TWeakObjectPtr도 인정).
- NativeInitializeAnimation: Super 호출 → Character = Cast<ACharacter>(TryGetPawnOwner()); if (Character) Movement = Character->GetCharacterMovement();
- NativeUpdateAnimation: Super → 유효성만 확인(비어 있을 때만 다시 얻는 것은 허용) → Speed = Movement->Velocity.Size2D() 또는 Character->GetVelocity().Size2D(); bIsInAir = Movement->IsFalling(); bIsAccelerating = Movement->GetCurrentAcceleration().Size() > 0.f; Direction = UKismetAnimationLibrary::CalculateDirection(Velocity, Character->GetActorRotation())(Build.cs에 AnimGraphRuntime) 또는 W4 내적·외적 계산.
- UAnimInstance에는 GetVelocity()가 없다(AActor의 함수이고, CMC는 Velocity 멤버를 가진다). GetCurrentAcceleration()은 CMC 멤버다.
- 상태 머신: 지상(로코모션) → 점프 시작 → 낙하 → 착지 → 지상. 전이 규칙에 bIsInAir 같은 C++ 변수를 쓴다. 상태 이름·개수가 달라도 지상·공중·착지 흐름이면 인정한다.
[만점 예] 위 코드와 에셋이 있고, GIF나 Shipping 실행에서 T포즈·튐 없이 이어진다.
[부분 예]
- ABP 부모는 UArenaAnimInstance지만 플레이어 메시에는 다른 ABP(예: 템플릿 기본 ABP)가 지정돼 있다 → 기준1 1.
- Direction 변수는 있지만 갱신하지 않는다 → 기준2 1.
- NativeUpdateAnimation에서 매 프레임 Cast<ACharacter>(TryGetPawnOwner())를 한다 → 기준3 1.
- ABP Event Graph에 Blueprint Update Animation → Cast To 노드가 남아 있다 → 기준3 1.
- 블렌드스페이스만 있고 점프 상태 머신이 없다, 또는 전이 규칙이 C++ 변수 대신 BP에서 따로 구한 값을 쓴다 → 기준4 1.
- GIF나 Shipping에서 착지 때 포즈 튐·T포즈가 1곳 있다 → 기준5 1.
[구술 질문(의심될 때)]
- Character·CMC를 매 프레임 Cast하지 않고 초기화 때 캐싱한 이유는? 초기화 때 Pawn이 아직 없으면 어떻게 되나요? (TryGetPawnOwner가 nullptr을 돌려준다. Update에서 비어 있을 때만 다시 얻는다)
- 기본 이동 설정(bOrientRotationToMovement 켜짐)에서 Direction이 거의 0인 이유는? (몸이 이동 방향으로 돌아 정면과 속도 방향이 같다. 도는 순간에만 값이 생긴다)

**채점표 (10점)**

- [2] 부모가 UArenaAnimInstance인 ABP를 플레이어 메시가 씀(Class Settings 확인)(2/부모는 맞지만 플레이어가 다른 ABP를 씀 1/부모가 기본 AnimInstance 0)
- [2] 변수 4개를 맞는 값으로 갱신(Speed·Direction 계산·IsFalling·가속)(4개 2, 2~3개 1, 1개 이하 0)
- [2] 초기화 때 TryGetPawnOwner로 Character·CMC 캐싱 + 이벤트 그래프 매 프레임 Cast 0(2/하나만 1/둘 다 아님 0)
- [2] AnimGraph에 블렌드스페이스 + 점프 상태 머신, 전이에 C++ 변수 사용(2/하나가 없거나 전이에 C++ 변수 안 씀 1/둘 다 없음 0)
- [2] GIF 또는 Shipping zip에서 걷기→달리기→점프→착지가 T포즈·포즈 튐 없이 이어짐(2/튐·T포즈 1곳 1/둘 다 확인 불가 0)

> 검토에서 고친 점: Shipping zip의 근거 주차를 W19라고 했다. 커리큘럼에서 Release에 Shipping zip을 첨부하라는 과제는 W13(v0.3.0)뿐이다. 기준5의 'GIF와 Shipping'은 둘 다 필요한지 하나만 있으면 되는지도 애매했다. → evidence_weeks를 W06·W13으로 바꿨다. 기준5는 'GIF 또는 Shipping zip'으로 정하고, 'T포즈·포즈 튐'처럼 눈으로 확인할 수 있는 조건으로 판정하게 했다. / 외부 에셋(Content/ThirdParty)은 커리큘럼 규칙상 .gitignore된다. 그래서 채점자가 클론한 사본에서는 ABP·블렌드스페이스가 깨져 보일 수 있는데, 이 준비 절차가 없었다. → notes와 answer_key에 'README 안내대로 외부 에셋을 미리 넣어 둔다'를 추가했다. question에는 README에 받는 방법을 적으라는 항목을 넣었다. / 기준1에 부분 점수 조건이 없었다. 기준4의 '하나 1'은 세 조건 중 무엇을 말하는지 애매했다. Speed를 Size2D로만 인정하는 것은 커리큘럼에 없는 요구였다. Direction은 기본 설정에서 거의 0이라 값으로 판정할 수 없다. → 기준1에 '부모는 맞지만 플레이어가 다른 ABP 사용 1'을 넣었다. 기준4의 부분 조건을 구체적으로 적었다. Size()도 인정하고, Direction은 계산 코드로 판정한다고 notes에 적었다.

> 작성 메모: 채점자 준비: 결함을 심지 않은 exam-submit 사본을 UE 5.8로 열어 둔다. ABP는 바이너리 에셋이라 에디터에서 확인한다. README에 외부 에셋(Content/ThirdParty 등 .gitignore한 폴더) 받는 방법이 있으면 미리 넣어 둔다. 넣지 않으면 애니메이션이 빠져 ABP가 깨져 보일 수 있다. Release에 첨부된 Shipping zip(W13 v0.3.0부터, 가장 최근 것)을 받아 다른 폴더에 풀어 둔다. 문항 점수 = 50×3÷118 ≈ 1.27점. 진위: 구술(P3-42)에서 뽑혔는데 설명하지 못하면 이 문항 점수의 50%만 인정한다. AI: W06은 AI 레벨 L1이라 AI 초안 사용은 감점하지 않는다. PR 'AI 활용 내역'이 정직한지만 본다. W17 이후 ABP를 적과 함께 쓰거나 GAS 태그 변수를 더했어도, 변수 4개와 캐싱 구조가 남아 있으면 인정한다. 심화로 NativeThreadSafeUpdateAnimation에 계산을 옮겼어도 인정한다. 기본 이동 설정(bOrientRotationToMovement)에서는 Direction이 거의 0인 것이 정상이므로, Direction은 값이 아니라 계산 코드로 판정한다. Speed는 Size2D를 권장하지만 커리큘럼이 정하지 않았으므로 Size()도 인정한다. CalculateDirection 비교(과제3)와 엔진 노트 03은 참고 자료이고 채점하지 않는다.

### P3-13 (1.27점) — 목표: W05-24, W05-25, W05-28

**모범 답안**

[여는 곳·순서]
1. PR 검색: is:pr is:merged head:feat/interaction-system(과제마다 PR을 열었다면 인터페이스·컴포넌트·대상 3종 PR이 따로 있다). GIF·본문·AI 활용 칸을 본다.
2. exam-submit 코드: git grep -n -e BlueprintNativeEvent -e Execute_Interact -e Implements -- Source. 인터페이스·컴포넌트·대상 3종을 연다. 레버 .h/.cpp에서 문 클래스 이름을 검색한다(git grep -n Door -- <레버 파일>). BP로 만든 대상은 에디터에서 그 BP의 Class Settings → Interfaces와 그래프를 본다.
3. 0줄 확인: git log --oneline --stat -- <Interaction 폴더>로 대상 파일이 추가된 스쿼시 커밋을 찾는다. git show --stat <커밋>에 InteractionComponent 파일이 없는지 본다. 커밋으로 확인할 수 없으면 PR 본문과 docs/devlog/W05.md의 기록을 본다.
4. 맵: GIF가 없거나 흐리면 에디터에서 레버 1개·문 2개가 있는 맵을 열어 Play로 확인한다.
[정답 예]
- 인터페이스: UINTERFACE(MinimalAPI, Blueprintable) UInteractable. IInteractable에 UFUNCTION(BlueprintNativeEvent, BlueprintCallable) void Interact(AActor* Interactor);와 FText GetInteractionText();
- 매개변수 이름을 Instigator로 하면 구현 액터에서 AActor::Instigator를 가려(shadowing) 경고나 빌드 오류가 날 수 있다. 다른 이름이면 된다.
- 컴포넌트: Target->Implements<UInteractable>()로 확인한 뒤 IInteractable::Execute_Interact(Target, GetOwner()). 대상 클래스를 include하거나 Cast하지 않는다.
- 레버: DECLARE_DYNAMIC_MULTICAST_DELEGATE_OneParam(FOnLeverToggled, bool, bIsOn); UPROPERTY(BlueprintAssignable) FOnLeverToggled OnLeverToggled; Interact_Implementation에서 토글한 뒤 Broadcast. 일반 멀티캐스트 델리게이트, BP의 Event Dispatcher도 정답.
- 문: UPROPERTY(EditAnywhere) TObjectPtr<ALever> LinkedLever → BeginPlay에서 AddDynamic(UFUNCTION 핸들러). 레벨 BP 바인딩이나 연결 담당 액터도 정답. 문이 레버를 아는 것은 괜찮다(듣는 쪽이다).
- 픽업: Interact에서 획득 처리(로그 등) 후 Destroy.
- C++ 대상(.h/.cpp)을 추가한 커밋에 컴포넌트 파일이 없는 것이 가장 좋은 증거다. BP 전용 대상은 원래 C++ 변경이 없으므로 그것만으로는 기준5 1.
- W15 이후 네트워크(Server RPC 등) 때문에 컴포넌트를 고친 커밋은 '대상 추가'가 아니므로 0줄 판단과 상관없다.
[만점 예] 위 구조가 있고, C++ 대상 추가 커밋에 컴포넌트 파일이 없으며, GIF에 대상 3종과 레버 1개·문 2개가 모두 보인다.
[부분 예]
- 대상이 2종뿐이다 → 기준1 1.
- GIF·에디터에서 대상 1~2종만 동작한다 → 기준2 1.
- 레버가 대상 배열을 들고 인터페이스 함수로 직접 부른다(문 클래스는 모르지만 델리게이트가 아님) → 기준3 1. 레버가 문 헤더를 include해 직접 부른다 → 기준3 0.
- 문 1개만 연결돼 있다 → 기준4 1.
- 컴포넌트 구조는 맞지만 0줄을 보여 주는 커밋·기록이 없다 → 기준5 1. 컴포넌트에 Cast<ADoor> 같은 대상별 분기가 있다 → 기준5 0.
[구술 질문(의심될 때)]
- 새 대상 '보물상자'를 추가하려면 어떤 파일을 만들고, 어떤 파일은 건드리지 않나요? 왜 그런가요?
- 블루프린트에서만 인터페이스를 구현한 대상에 Cast<IInteractable>을 쓰면 어떻게 되나요? (Cast가 실패한다. Implements<UInteractable>()와 Execute_Interact를 쓴다)

**채점표 (10점)**

- [2] IInteractable(BlueprintNativeEvent) + C++·BP로 구현한 대상 3종(3종 2, 2종 1, 1종 이하 0)
- [2] 대상 3종이 동작함: PR·Devlog W05 GIF, 없으면 에디터 Play(3종 2, 1~2종 1, 확인 불가 0)
- [2] 레버가 문을 모르고 델리게이트 Broadcast, 문이나 레벨 BP가 구독(2/델리게이트 없이 인터페이스로 직접 호출 1/레버가 문 include·직접 호출 0)
- [2] 레버 1개로 문 2개가 열고 닫힘: GIF, 없으면 에디터 Play(2/문 1개만 1/확인 불가 0)
- [2] 컴포넌트는 인터페이스만 사용 + 대상 추가 커밋에 컴포넌트 변경 0 또는 확인 기록(2/구조만 맞음 1/대상별 분기 있음 0)

> 검토에서 고친 점: 정답 예의 Interact(AActor* Instigator)는 구현 액터에서 AActor::Instigator를 가려(shadowing) 경고나 빌드 오류가 날 수 있다. → 매개변수 이름을 Interactor로 바꾸고 이유를 한 줄로 적었다. / 커리큘럼은 BlueprintNativeEvent로 'C++·BP 모두 구현 가능하게'를 요구하는데, 기준1은 '코드'만 인정했다. GIF 기준에는 대체 확인 방법과 0점 조건이 없었다. → BP로 구현한 대상도 인정하고 BP 확인 경로를 더했다. GIF가 없으면 에디터 Play로 확인할 수 있게 했고, 모든 기준을 2/1/0으로 나눴다.

> 작성 메모: 채점자 준비: 결함을 심지 않은 exam-submit 사본과 PR 목록을 연다. 상호작용 대상은 아레나 맵이나 Shipping 빌드에 없을 수 있다. 그래서 GIF와 에디터 테스트 맵으로 확인한다. 문항 점수 = 50×3÷118 ≈ 1.27점. 진위: 구술(P3-42)에서 뽑혔는데 설명하지 못하면 이 문항 점수의 50%만 인정한다. AI: W05는 AI 레벨 L1이라 AI 초안은 감점하지 않는다. PR 'AI 활용 내역'이 정직한지만 본다. 커리큘럼이 BlueprintNativeEvent로 'C++·BP 모두 구현 가능하게'를 요구하므로 BP로 구현한 대상도 인정한다. 같은 인터페이스와 문을 AI 없이 다시 만드는 AI-Off ②는 라이브 P3-12에서 따로 채점한다. 여기서는 W05 저장소 결과만 본다.

### P3-15 (1.27점) — 목표: W09-05, W09-08, W09-21, W09-22, W20-06

**모범 답안**

[여는 곳·순서]
1. PR 검색: head:feat/hud(W09), head:feat/game-feel(W20). GIF·본문·AI 활용 칸을 본다(W09는 L2라 AI 리뷰 의견마다 채택/거절 + 이유가 있다).
2. exam-submit 코드: git grep -n -e BindWidget -e BindWidgetAnim -e NativeTick -e CreateWidget -e AddToViewport -e PlayAnimation -- Source. 위젯과 PC(또는 HUD) .cpp에서 델리게이트 구독 줄을 찾는다.
3. 에디터(결함을 심지 않은 사본): HUD WBP 열기 → Graph 탭 Class Settings → Parent Class를 본다. Graph에 실행 핀이 연결된 Event Tick이 없는지 본다. Designer에서 체력 바·스태미나 바·텍스트를 골라 Details의 Percent·Text 옆 Bind 드롭다운에 바인딩이 없는지, My Blueprint 함수 목록에 바인딩용 Get 함수가 없는지 본다. Animations 패널에서 UI 애니메이션을 찾고, 어떤 이벤트가 재생하는지 본다.
4. Shipping zip: 적에게 맞아 체력 바가 줄고 UI 애니메이션이 재생되는지, 대시(W16 GA_Dash)를 쓰면 스태미나 바가 줄었다 다시 차는지 본다. 상호작용 프롬프트는 Shipping 맵에 대상이 없을 수 있으므로 W09 GIF나 에디터 Play로 본다.
[정답 예]
- UPROPERTY(meta=(BindWidget)) TObjectPtr<UProgressBar> HealthBar, StaminaBar; TObjectPtr<UTextBlock> PromptText. WBP 위젯 이름·타입이 같아야 컴파일된다.
- PC BeginPlay: if (IsLocalController() && HUDWidgetClass) { HUDWidget = CreateWidget<UArenaHUDWidget>(this, HUDWidgetClass); HUDWidget->AddToViewport(); } HUDWidget은 UPROPERTY. AHUD 자식에서 GetOwningPlayerController()로 만들어도 정답.
- 구독: OnHealthChanged.AddDynamic(위젯, UFUNCTION) → SetPercent. W16·W17 이후 ASC->GetGameplayAttributeValueChangeDelegate(UArenaAttributeSet::GetHealthAttribute()).AddUObject(...)도 정답(스태미나도 같은 방식). 프롬프트: OnFocusChanged → Execute_GetInteractionText → SetText, 대상이 없으면 SetVisibility(Collapsed).
- UI 애니메이션: UPROPERTY(Transient, meta=(BindWidgetAnim)) TObjectPtr<UWidgetAnimation> HitFlash; 체력 감소 이벤트에서 PlayAnimation(HitFlash). BP 이벤트에서 Play Animation 노드로 재생해도 정답.
- 새 WBP에 기본으로 생기는 회색(비활성) Event Tick 노드는 감점하지 않는다. 실행 핀이 연결된 Event Tick만 센다.
[만점 예] BindWidget 3개, PC의 생성·보관, 모든 갱신이 델리게이트, Tick·Binding 0, Shipping에서 피격 때 체력 바 번쩍임 애니메이션과 대시 후 스태미나 변화가 보인다.
[부분 예]
- BindWidget이 체력 바 하나뿐이다 → 기준1 1.
- 캐릭터 BP나 레벨 BP에서 위젯을 만들거나, PC가 만들지만 포인터를 보관하지 않는다 → 기준2 1.
- 체력은 델리게이트, 스태미나는 Property Binding이다 → 기준3 1, 기준4 1.
- 프롬프트가 없거나 Tick으로 대상을 검사한다 → 기준3 1.
- UI 애니메이션 에셋은 있지만 어떤 이벤트도 재생하지 않는다 → 기준5 1. Tick으로 색을 바꾸는 방식은 UI 애니메이션으로 보지 않는다.
[구술 질문(의심될 때)]
- 데미지를 받은 뒤 HUD 체력 바가 바뀌기까지 호출 순서를 말해 보세요. (데미지 → 체력 변경 → 델리게이트 Broadcast → 위젯 함수 → SetPercent)
- PC에서 위젯을 만들 때 IsLocalController를 확인하는 이유는? (리슨 서버에는 다른 플레이어의 PC도 있어서, 그 PC로는 위젯을 만들면 안 된다) Property Binding이나 Tick으로 갱신하면 무엇이 문제인가요? (값이 안 바뀌어도 매 프레임 평가된다)

**채점표 (10점)**

- [2] C++ 부모 + BindWidget 3개(체력·스태미나·프롬프트), WBP 부모 지정(3개 2, 1~2개 1, C++ 부모 없음 0)
- [2] PC 또는 AHUD가 생성·AddToViewport·UPROPERTY 보관(2/다른 곳에서 생성하거나 보관 안 함 1/HUD 없음 0)
- [2] 체력·스태미나·프롬프트 모두 델리게이트 구독으로 갱신, 바뀌는 모습이 GIF·Shipping에서 보임(2/1~2개만 델리게이트이거나 동작 확인 불가 1/델리게이트 갱신 없음 0)
- [2] HUD 위젯에 NativeTick·연결된 Event Tick·Property Binding 0(코드·WBP 확인)(2/1곳 1/2곳 이상 0)
- [2] UMG 애니메이션 1개 이상이 이벤트로 재생, GIF·Shipping·에디터 Play 중 한 곳에서 확인(2/에셋만 있고 재생 이벤트 없음 1/없음 0)

> 검토에서 고친 점: Shipping 확인 절차에 '질주하면 스태미나가 주는지'가 있었다. 커리큘럼에서 스태미나는 W16 대시(GE_Dash_Cost)가 쓰고 질주는 쓰지 않는다. 또 W09에는 스태미나 값이 아직 없어서 W09 GIF로는 스태미나 갱신을 보일 수 없다. → '대시를 쓰면 스태미나 바가 줄었다 다시 참'으로 고쳤다. 스태미나는 W16 이후 GIF·Shipping으로 확인하고 W09 GIF에서는 감점하지 않는다고 적었다. evidence_weeks에 W16·W17을 더했다. / UI 애니메이션(W20-06)은 W20 핵심 개념에만 있고 필수 과제에는 없다. 그런데도 W20 PR·v0.5.0 GIF를 근거로 요구했다. 또 question은 'Shipping에서도 보인다'를 필수처럼 썼지만 채점표는 '또는'이었다. → 프로젝트 안 어느 위젯의 UMG 애니메이션이든 인정하고, GIF·Shipping·에디터 Play 중 한 곳에서 확인하면 되게 했다. question과 채점표 표현을 맞췄다. / 기준2의 '(로컬 확인)'은 W09-08 범위 밖인데 점수에 들어가는지 애매했다. 기준4는 범위(메뉴·팝업 위젯 포함 여부)가 정해지지 않았다. 기준3의 '일부만 1'도 애매했다. → 로컬 확인은 구술 질문으로만 쓰고 점수에서 뺐다. 기준4는 HUD 위젯만 보도록 범위를 정했다. 기준3은 '1~2개만 델리게이트이거나 동작 확인 불가 1, 델리게이트 갱신 없음 0'으로 정했다.

> 작성 메모: 채점자 준비: 결함을 심지 않은 exam-submit 사본을 에디터로 열어 HUD WBP를 확인하고, 최근 Release의 Shipping zip을 풀어 둔다. 문항 점수 = 50×3÷118 ≈ 1.27점. 진위: 구술(P3-42)에서 뽑혔는데 설명하지 못하면 이 문항 점수의 50%만 인정한다. AI: W09는 L2, W20은 L2~L3이라 AI 리뷰·검증을 쓴 것은 감점하지 않는다. PR 'AI 활용 내역'이 정직한지만 본다. HUD는 W12(메뉴), W15(복제), W16·W17(GAS)에서 바뀐다. 그래서 코드는 exam-submit 결과로 보고, W09 PR은 처음 구조를 확인하는 데 쓴다. 스태미나는 W16 AttributeSet(GE_Dash_Cost·GE_StaminaRegen)에서 처음 실제 값이 생긴다. 질주(Shift)는 스태미나를 쓰지 않는다. 그래서 W09 GIF에서 스태미나 바가 움직이지 않아도 감점하지 않고, 스태미나는 대시 이후 GIF·Shipping으로 본다. 기준4는 HUD(레이아웃 WBP, C++ 부모, HUD 안 자식 위젯)만 본다. 메뉴·데미지 숫자 팝업 위젯은 보지 않는다. IsLocalController 확인은 좋은 습관이지만 W09-08 범위 밖이라 점수에 넣지 않는다(구술 질문으로만 쓴다). UI 애니메이션은 W20 핵심 개념에만 있고 필수 과제 체크박스에는 없다. 그래서 위치·PR 이름을 묻지 않고 프로젝트 안 어느 위젯이든 인정한다(HUD 피격 번쩍임, W09 심화 데미지 숫자 팝업, W12 메뉴·웨이브 알림 등). 심사 항목에 미리 공개되므로 하나도 없으면 기준5는 0이다.

### P3-16 (1.69점) — 목표: W07-17, W07-18, W07-26, W20-07

**모범 답안**

[여는 곳·순서]
1) Pull requests → Closed에서 W07 콤보 PR(feat/combo-system 또는 같은 역할) → Files changed.
- 콤보: 공격 입력 → 공격 중이 아니면 Montage_Play. 윈도우가 열려 있고 아직 예약이 없을 때만 예약(Montage_SetNextSection, 또는 플래그 + 윈도우 끝에 Montage_JumpToSection). 섹션 3개.
- 윈도우 밖 입력: 윈도우 플래그가 꺼져 있으면 바로 return(로그를 남기면 더 좋다).
- 초기화: OnMontageEnded(또는 OnMontageBlendingOut) 콜백에서 콤보 번호·예약·윈도우 플래그를 되돌린다.
- 로직이 캐릭터가 아니라 컴포넌트에 있는지. W10 UBTTask_MeleeAttack이 이 컴포넌트를 재사용하면 분리 효과가 보인다(가점 없음).
2) NotifyState(.h/.cpp가 콤보 PR이나 feat/weapon-sweep PR에): NotifyBegin/NotifyEnd 오버라이드(시그니처는 AnimNotifyState.h 기준). MeshComp->GetOwner()에서 컴포넌트를 찾아 윈도우·판정을 켜고 끈다.
3) 밖 입력 무시 기록: 재현 단계(예: 윈도우 전 연타 → 1타에서 끝, 윈도우 안 입력 → 다음 타)와 결과. GIF만으로는 누른 입력이 안 보이므로 글로 적은 단계·결과가 있어야 한다. 로그·화면 표시가 GIF에 보이면 더 분명하다.
4) W20 기록: 바꾼 내용(예: 윈도우 시작을 앞당김, 길이 0.2→0.35초)과 이유(예: 플레이테스트 2차 '연타가 끊긴다'). PR Files changed에 몽타주 .uasset만 바뀌어 있어도 본문 설명으로 판단한다.
[부분 점수 예시]
- 콤보 로직이 캐릭터 클래스에 있거나 2단까지만 → 기준1 1점.
- 윈도우 검사는 있지만 몽타주 종료·중단 초기화가 없음(또는 반대) → 기준2 1점. 언제 눌러도 예약되고 초기화도 없음 → 0점.
- C++ NotifyState가 하나뿐(다른 하나는 BP이거나 없음) → 기준3 1점. 둘 다 BP → 0점.
- GIF는 있으나 '밖 입력 무시' 재현 단계·결과 글이 없음(또는 글만 있고 GIF 없음) → 기준4 1점.
- W20 기록에 바꾼 내용·이유 중 하나만 있음(예: '윈도우를 늘렸다'뿐) → 기준5 1점. W20 기록이 어디에도 없으면 0점.
[구술 질문]
- 윈도우 밖에서 누른 입력은 코드 어디에서 버려지나? 몽타주가 중간에 끊기면 상태는 어디서 초기화되나?
- 윈도우를 짧게·길게 했을 때 플레이 느낌이 어떻게 달랐나? 그래서 왜 그 값을 골랐나?

**채점표 (10점)**

- [2] UCombatComponent(같은 역할)에 로직, 섹션 기반 3단 콤보(2/캐릭터에 로직 또는 2단 1)
- [2] 윈도우 안 입력만 예약 + 종료·중단 시 초기화 코드(2/하나 1)
- [2] C++ NotifyState 2개(ComboWindow·HitWindow) Begin/End 토글(2/C++ 1개 1, C++ 없음 0)
- [2] 밖 입력 무시 재현 단계·결과 글(PR 테스트 방법·TS-002·Devlog W07) + 콤보 GIF(2/하나 1)
- [2] W20 윈도우 조정 내용과 이유 기록(W20 PR·Devlog·v0.5.0·M5 회고)(2/하나 1, 없음 0)

> 검토에서 고친 점: AI 레벨 설명이 커리큘럼과 다름('L1 = AI가 설명·학생이 타이핑'). 커리큘럼은 L1 = AI 초안 → 모든 줄 해설 주석, M2(W05~W08) = L1~L2, M5(W17~W20) = L2~L3. → notes의 AI 활용 문장을 커리큘럼 표현으로 바꿈(W07 L1~L2, W20 L2~L3). / 구술 후보 표시 기준 '칸이 코드 수준과 어긋나면'이 주관적. → '칸이 비었거나 같은 주 Devlog AI 활용 회고와 어긋나면'으로 바꿔 관찰 가능하게 함(5문항 공통). / 기준4가 PR '테스트 방법'만 증거로 인정하고 GIF로 '밖 입력 무시'를 보라고 함. GIF에는 누른 입력이 안 보여 판정할 수 없음. → 재현 단계·결과 글(PR 테스트 방법·TS-002·Devlog W07 중 한 곳) + 콤보 GIF로 기준을 나눔. 글이 없으면 1점. / 기준5가 W20 PR·Devlog의 '전/후 값'을 요구함. 콤보 윈도우 튜닝은 W20 핵심 개념일 뿐 정해진 산출물이 없어 커리큘럼보다 엄격함. → 바꾼 내용(값이나 노티파이 위치)과 이유를 W20 PR·Devlog W20·v0.5.0 릴리즈 노트·M5 회고 중 어디에 적었든 인정함. / 기준3 부분 점수가 'BP로만 만듦 → 1점'이라 C++ 작성 목표(W07-18)와 맞지 않음. HitWindow가 feat/weapon-sweep PR에 있을 수 있는 점도 빠짐. → C++ 2개 2점, 1개 1점, 0개 0점. 증거 위치에 feat/weapon-sweep PR을 추가함.

> 작성 메모: - 문항 점수 50×4÷118 ≈ 1.69점. 심사 약 10분.
- 증거 위치: W07 PR(커리큘럼 브랜치 feat/combo-system, NotifyState는 feat/weapon-sweep PR에 있을 수도 있음), docs/troubleshooting/TS-002-*.md, docs/devlog/W07.md, W20 PR(feat/game-feel 또는 플레이테스트 2차 반영 PR), docs/devlog/W20.md, v0.5.0 릴리즈(전/후 GIF), docs/retro/M5.md. 브랜치·클래스 이름이 달라도 같은 역할이면 인정.
- W17(refactor/combat-to-gas)에서 GA_MeleeCombo로 옮겨 exam-submit 코드가 달라졌어도 감점하지 않는다. 기준1~3은 W07 PR diff로 채점한다.
- 노티파이 위치는 몽타주 .uasset이라 diff에 값이 안 보인다. 확인이 필요하면 exam-submit을 따로 Clone한 사본에서 몽타주를 연다(블록3용 결함 심은 사본은 쓰지 않는다).
- 콤보 윈도우 튜닝은 W20 핵심 개념('입력 반응성 튜닝(콤보 윈도우)')이고 따로 정한 산출물이 없다. 그래서 W20의 PR·Devlog·릴리즈 노트·M5 회고 중 어디에 적었든 인정한다. 숫자 대신 '노티파이를 몇 프레임 앞당김'처럼 적어도 된다.
- AI 활용: W07은 M2 구간 L1~L2(새 개념은 AI 초안 → 모든 줄 해설 주석 달아 다시 작성, 반복 패턴은 내가 먼저 작성), W20은 L2~L3. 이 범위 안의 AI 활용은 감점하지 않는다. PR 'AI 활용 내역' 칸은 정직한지만 본다. 칸이 비었거나 같은 주 Devlog 'AI 활용 회고'와 어긋나면 P3-42 구술 후보로 표시한다(이 문항에서 감점하지 않음).
- 진위: P3-42 구술에서 이 문항이 뽑혀 핵심 코드·결정을 설명하지 못하면 이 문항 점수의 50%만 인정한다.
- 보조로 Shipping zip에서 연타해 볼 수 있다. 채점은 PR·GIF·문서 기준.

### P3-17 (1.69점) — 목표: W07-19, W07-20, W07-21, W07-22, W07-25

**모범 답안**

[여는 곳·순서]
1) W07 판정 PR(feat/weapon-sweep 또는 같은 역할) → Files changed.
- 판정 시작(HitWindow Begin): 맞은 목록 비우기, 소켓 위치를 '이전 위치'로 저장. 목록을 판정 끝(End)에서 비워도 인정.
- 판정 중 매 프레임(Tick 또는 NotifyTick): GetSocketLocation(시작·끝, 사이 점 포함 가능) → 점마다 이전 → 현재로 SweepMultiByChannel(SweepSingle·SphereTraceMulti도 인정) → 이전 = 현재.
- TSet<AActor*>(TObjectPtr·TWeakObjectPtr 키도 인정): Contains가 false일 때만 Add + 데미지.
- DrawDebugLine·DrawDebugSphere 등으로 경로·ImpactPoint 표시. bool UPROPERTY나 콘솔 변수로 켜고 끄면 좋다.
2) Weapon 채널: Config/DefaultEngine.ini의 [/Script/Engine.CollisionProfile] 아래 +DefaultChannelResponses=(Channel=ECC_GameTraceChannel1,…,Name="Weapon") 같은 줄. 프리셋을 만들었다면 +Profiles=(Name=…) 줄도 같은 diff에 있다. Trace·Object 채널 어느 쪽이든 인정. 코드가 그 ECC_GameTraceChannelN(또는 그것을 가리키는 상수)로 Sweep하는지 함께 본다.
3) 30FPS 영상: 화면의 stat fps(약 30)나 콘솔 입력 장면, 또는 본문의 측정 조건 't.MaxFPS 30'. 디버그 선이 끊김 없이 이어지고 스윙마다 맞은 대상이 표시·로그되는지.
[부분 점수 예시]
- 현재 프레임의 시작~끝 소켓만 한 줄로 트레이스(프레임 사이 경로 없음) → 기준1 1점. Overlap 콜리전 이벤트만 씀 → 0점.
- TArray::Contains로 중복 검사, 또는 스윙마다 목록을 비우지 않음 → 기준2 1점.
- DrawDebug 코드는 있으나 영상·GIF에 안 보임 → 기준3 1점.
- ini 변경이 PR이 아닌 main 직접 커밋에만 있음, 또는 채널은 만들었지만 코드가 ECC_Visibility 등 다른 채널로 Sweep → 기준4 1점. ini에 채널이 없으면 0점.
- 영상은 있으나 30FPS 조건이 안 보이거나 누락 장면이 1~2번 → 기준5 1점.
[구술 질문]
- 현재 위치만 Sweep하면 30FPS에서 왜 판정이 새나? 이전 위치는 언제 저장하고 갱신하나?
- TSet은 언제 비우나? 비우지 않으면 어떤 버그가 생기나? (보조: Object Channel과 Trace Channel의 차이는?)

**채점표 (10점)**

- [2] 소켓 2개 이전→현재 위치 Sweep 코드(2/현재 위치만 1)
- [2] TSet으로 스윙당 대상별 1회, 스윙마다 비움(2/TArray 또는 비우지 않음 1)
- [2] DrawDebug로 경로·히트 지점 표시, 영상·GIF에 보임(2/코드만 1)
- [2] Weapon 채널(만든 프리셋 포함)이 PR diff의 DefaultEngine.ini에 있고 코드가 그 채널로 Sweep(2/PR 밖 커밋만 또는 다른 채널 사용 1)
- [2] t.MaxFPS 30 디버그 영상, 누락 없음(2/조건 안 보임 또는 누락 1~2번 1)

> 검토에서 고친 점: W07-22 목표의 '(및 프리셋)'을 확인하는 기준이 없음. 코드가 실제로 Weapon 채널을 쓰는지도 확인하지 않음. → 기준4: 만든 프리셋의 +Profiles 줄을 같은 PR diff에서 확인하고, 코드가 그 채널로 Sweep하는지 봄. 필수 과제는 채널 추가뿐이라 프리셋이 없어도 감점하지 않는다고 notes에 적음. / TSet을 '판정 시작 때' 비울 때만 인정함. 판정 끝에서 비워도 맞는 구현임. → '스윙마다 비움'으로 바꿔 시작·끝 둘 다 인정함.

> 작성 메모: - 문항 점수 50×4÷118 ≈ 1.69점. 심사 약 10분.
- 증거 위치: W07 PR(커리큘럼 브랜치 feat/weapon-sweep), W07 산출물 '30FPS 판정 검증 영상', docs/devlog/W07.md, docs/troubleshooting/TS-002-*.md(보조), v0.2.0 릴리즈 45초 영상(디버그 판정 ON, W08). 이름이 달라도 같은 역할이면 인정.
- W15(서버 판정)·W17(GA_MeleeCombo가 W7 판정 재사용) 이후 코드 위치가 바뀌어도 W07 PR diff로 채점한다.
- 프리셋: 커리큘럼 필수 과제는 'Weapon 채널 추가 → PR에서 ini diff 확인'이다. 프리셋을 만들었으면 그 줄도 같은 PR diff에서 확인한다. 채널 기본 응답만으로 동작해 프리셋이 없어도 감점하지 않는다.
- 채널 응답(Block/Overlap)에 따른 Multi Sweep 결과 차이는 커리큘럼 범위 밖이라 채점하지 않는다.
- AI 활용: W07은 M2 구간 L1~L2(새 개념은 AI 초안 → 모든 줄 해설 주석 달아 다시 작성, 반복 패턴은 내가 먼저 작성). 이 범위 안의 AI 활용은 감점하지 않는다. PR 'AI 활용 내역' 칸은 정직한지만 본다. 칸이 비었거나 같은 주 Devlog 'AI 활용 회고'와 어긋나면 P3-42 구술 후보로 표시한다(이 문항에서 감점하지 않음).
- 진위: P3-42 구술에서 이 문항이 뽑혀 핵심 코드·결정을 설명하지 못하면 이 문항 점수의 50%만 인정한다.

### P3-18 (0.85점) — 목표: W11-08, W11-09, W04-26

**모범 답안**

[여는 곳·순서]
1) W04 PR(feat/direction-debug 또는 같은 역할) → Files changed의 디버그 액터.
- To = (대상 − 플레이어).GetSafeNormal2D(), F = 플레이어 Forward. Dot = FVector::DotProduct(F, To) → 양수 앞·음수 뒤. CrossZ = FVector::CrossProduct(F, To).Z → UE(Z-up, X 앞·Y 오른쪽)에서 양수 오른쪽·음수 왼쪽.
- 각도: Acos(Dot)를 도(degree)로 바꾸고 CrossZ 부호를 붙인다(Atan2 방식도 인정).
- DrawDebugLine(플레이어→대상)과 DrawDebugString(방향 이름·각도).
2) W04 영상·v0.1.0 GIF: 대상 주위를 돌 때 앞/뒤/좌/우 표시와 각도가 실제 위치와 맞는지. 좌우가 뒤바뀌지 않았는지.
3) W11 PR(feat/hit-reaction): 피격 처리(TakeDamage·OnTakePointDamage 등)에서 공격자 위치로 방향을 구하는 식이 W4와 같은 내적·외적 식인지(W4 함수 호출, 공용 유틸, 같은 식을 옮겨 씀 모두 인정). 방향별 몽타주 4개 중 선택.
4) 경직: 일정 시간 이동·공격을 막음(입력 무시 플래그, 적은 BT·Blackboard 플래그 등) + 타이머로 해제. 넉백: LaunchCharacter 등으로 공격자 반대 방향.
5) GIF: 네 방향에서 맞을 때 다른 리액션, 경직 중 멈춤, 밀려남.
[부분 점수 예시]
- 디버그 액터가 앞/뒤만 표시하고 좌/우·각도가 없음 → 기준1 1점.
- 영상에서 두세 방향만 확인되거나 좌우가 뒤바뀌어 표시됨 → 기준2 1점.
- W11에서 UKismetAnimationLibrary::CalculateDirection 등 내적·외적이 아닌 방식만 씀, 또는 2~3방향만 선택 → 기준3 1점.
- GIF에서 2~3방향만 보임 → 기준4 1점.
- GIF에 넉백은 보이나 경직이 안 보임(또는 반대) → 기준5 1점.
- 참고: CMC DisableMovement(MOVE_None)로 경직을 만들면 대기 중인 LaunchCharacter 속도가 지워져 넉백이 사라질 수 있다. GIF에서 넉백이 실제로 보이면 방식은 묻지 않는다.
[구술 질문]
- 내적과 외적은 각각 무엇을 알려 주나? 외적 Z가 양수면 왜 오른쪽인가?
- 피격 방향 계산을 W4 코드와 어떻게 나눠 썼나? 경직 중에도 넉백이 적용되게 하려고 어떻게 처리했나?

**채점표 (10점)**

- [2] 디버그 액터: 내적 앞뒤·외적 Z 좌우·각도를 DrawDebugLine·String으로(2/일부 1)
- [2] W04 영상·v0.1.0 GIF에서 네 방향·각도가 맞음(2/2~3방향 또는 좌우 뒤바뀜 1)
- [2] 피격 방향을 W4 내적·외적 계산으로 판정, 네 방향 몽타주 선택 코드(2/다른 방식 또는 2~3방향 1)
- [2] 방향별 리액션 GIF·영상(4방향 2, 2~3방향 1)
- [2] 경직·넉백 코드와 GIF(2/하나 1)

> 검토에서 고친 점: 기준3에서 W4 식을 옮겨 쓰면 1점. 목표(W11-09)는 'W4 내적/외적으로 판정'이라 같은 식을 쓰면 충족함. 커리큘럼보다 엄격함. → W4 함수 호출·공용 유틸·같은 식 옮겨 쓰기를 모두 인정함. 내적·외적이 아닌 방식(CalculateDirection 등)만 썼거나 2~3방향이면 1점.

> 작성 메모: - 문항 점수 50×2÷118 ≈ 0.85점. 심사 약 8분.
- 증거 위치: W04 PR(커리큘럼 브랜치 feat/direction-debug), W04 산출물 '방향 판정 디버그 영상', v0.1.0 릴리즈 20초 GIF, W11 PR(feat/hit-reaction), docs/devlog/W11.md. 이름이 달라도 같은 역할이면 인정.
- 팩에 히트 리액션 애니메이션이 부족하면 이름이 다른 몽타주 4개 + 로그·화면 표시로 방향 선택을 보여도 인정한다.
- 커리큘럼은 'W4 내적/외적으로' 판정하라고 한다. W4 함수 호출, 공용 유틸로 옮김, 같은 식을 옮겨 씀 모두 인정한다.
- W15·W17 이후 피격 연출이 Multicast나 GameplayCue로 옮겨졌어도 방향 판정 식이 같으면 인정. 기준3은 W11 PR diff로 채점한다.
- AI 활용: W04는 L1(AI 초안 → 모든 줄 해설 주석 달아 다시 작성), W11은 L2(내가 작성 → AI 리뷰, 의견마다 채택/거절 + 이유를 PR에). 이 범위 안의 AI 활용은 감점하지 않는다. PR 'AI 활용 내역' 칸은 정직한지만 본다. 칸이 비었거나 같은 주 Devlog 'AI 활용 회고'와 어긋나면 P3-42 구술 후보로 표시한다(이 문항에서 감점하지 않음).
- 진위: P3-42 구술에서 이 문항이 뽑혀 핵심 코드·결정을 설명하지 못하면 이 문항 점수의 50%만 인정한다.

### P3-19 (1.27점) — 목표: W08-12, W08-19, W08-20, W08-23, W08-28, W11-15

**모범 답안**

[여는 곳·순서]
1) W08 PR(feat/data-assets 또는 같은 역할) → Files changed.
- UCharacterStatData : UPrimaryDataAsset의 4값 → 캐릭터 BeginPlay(또는 PossessedBy·초기화 함수)에서 CMC MaxWalkSpeed·JumpZVelocity, 스프린트 속도, 체력 MaxHealth에 적용.
- 'TODO(W8)' 주석과 W4 스프린트 속도 상수(UPROPERTY 기본값 등)가 지워졌는지 diff의 빨간 줄로 본다. exam-submit 사본에서 'TODO(W8)'를 검색하면 0건이어야 한다.
2) UWeaponData 필드를 판정(소켓 이름·반경), 데미지(배율), 콤보(몽타주), 장착(메시) 코드가 읽는지. 같은 값이 .cpp 상수로 남아 있지 않은지. 무기 DataAsset 2개(예: DA_Sword·DA_Axe).
3) feat/second-weapon-data-only PR → Files changed: .uasset(필요하면 Config)만 있고 .h/.cpp 0개. 본문 GIF에서 두 번째 무기로 타격.
4) 적 스탯: USTRUCT(BlueprintType) 행 구조체 : FTableRowBase, DataTable 에셋(Files changed의 .uasset), 적이 FindRow로 읽는 코드. 재임포트 흔적(예: 'Grunt MaxHealth 120→150 수정 후 Reimport').
5) W11 PR(feat/ranged-enemy): 원거리 적 스탯이 W8과 같은 행 구조체의 DataTable 새 행인지(같은 테이블 권장, 같은 구조체의 새 테이블도 인정). 구조체에 필드 1~2개를 더한 것은 인정. 투사체 등 AI 코드 변경은 있어도 된다.
[부분 점수 예시]
- StatData 4값 중 일부만 적용(예: JumpZVelocity 미적용), 또는 TODO(W8)·스프린트 상수가 남음 → 기준1 1점.
- WeaponData에 필드는 있지만 판정이 소켓 이름·반경을 코드 상수로 씀, 또는 무기 DataAsset이 1개뿐 → 기준2 1점.
- 두 번째 무기 PR에 .h/.cpp가 1개라도 있으면 기준3 0점. .h/.cpp 0개지만 동작 GIF가 없으면 1점.
- DataTable·행 구조체·FindRow는 있으나 재임포트 흔적이 어디에도 없음 → 기준4 1점. DataTable 없이 코드·DataAsset으로만 적 스탯 → 0점.
- 원거리 적 스탯을 새 행 구조체로 따로 만듦 → 기준5 1점. 코드 상수 → 0점.
[구술 질문]
- DataAsset과 DataTable을 어떤 기준으로 나눴나? (ADR-0002 내용과 비교)
- 두 번째 무기 PR이 코드 0줄로 가능했던 이유는? CSV를 고친 뒤 에디터에서 무엇을 해야 값이 바뀌나?

**채점표 (10점)**

- [2] UCharacterStatData 4값을 초기화 때 적용, W4 TODO(W8)·스프린트 상수 제거(2/일부 값만 또는 TODO 남음 1)
- [2] UWeaponData 5항목을 판정·데미지·콤보·장착 코드가 읽고 해당 상수 없음, 무기 DataAsset 2종(2/일부 1)
- [2] second-weapon PR .h/.cpp 0개 + 동작 GIF(2/GIF 없음 1, .h/.cpp 있음 0)
- [2] 적 스탯 DataTable: 행 구조체·CSV 임포트·FindRow + 재임포트 흔적(2/흔적 없음 1, DataTable 없음 0)
- [2] W11 원거리 적 스탯을 W8 행 구조체의 DataTable 행으로 정의(2/새 행 구조체 1, 코드 상수 0)

> 검토에서 고친 점: 기준1이 'PR 본문의 옮긴 매직 넘버 목록'을 요구함. 커리큘럼 산출물이 아님. → 목록 요구를 없애고 W4 TODO(W8)·스프린트 상수 제거와 StatData 적용으로 판정함. 목록은 '있으면 확인이 쉽다'로만 둠. / 재임포트 기록을 PR 본문·Devlog만 인정함. 커리큘럼은 이 흐름을 '체험'으로만 요구함. 기준5가 W08-23과 W11-15를 묶어 '하나 1'이라 판정이 모호함. → TIL·CSV 커밋 이력도 흔적으로 인정함. 기준을 StatData+TODO / WeaponData / 0줄 PR / DataTable+재임포트 / 원거리 적 행으로 다시 나눔.

> 작성 메모: - 문항 점수 50×3÷118 ≈ 1.27점. 심사 약 10분.
- 증거 위치: W08 PR(커리큘럼 브랜치 feat/data-assets·feat/second-weapon-data-only), docs/devlog/W08.md, unreal-study-log ue5-til/의 W08 TIL, docs/adr/ADR-0002-dataasset-vs-datatable.md(구술 참고, 이 문항에서 채점 안 함), v0.2.0 릴리즈, W11 PR(feat/ranged-enemy). 이름이 달라도 같은 역할이면 인정.
- 매직 넘버 '목록'은 커리큘럼 산출물이 아니다. 목록이 없어도 코드에서 수치가 빠졌으면 기준1·2 만점. PR '변경 사항'에 적혀 있으면 확인이 빨라진다.
- CSV 재임포트는 커리큘럼이 '체험'으로만 요구한다. PR 본문·Devlog W08·TIL 한 줄·저장소 CSV 원본의 커밋 이력 중 하나면 흔적으로 인정한다.
- W08 DoD가 '무기 추가 PR diff에 .h/.cpp 없음'이므로 기준3은 엄격히 본다.
- W17 이후 체력이 AttributeSet으로, W09 이후 무기 메시·몽타주가 TSoftObjectPtr로 바뀌어도 정상. 기준1~4는 W08 PR diff로 채점한다.
- DataTable 행 값 확인이 필요하면 exam-submit을 따로 Clone한 사본에서 연다(블록3용 결함 심은 사본은 쓰지 않는다).
- AI 활용: W08은 M2 구간 L1~L2(새 개념은 AI 초안 → 모든 줄 해설 주석 달아 다시 작성, 반복 패턴은 내가 먼저 작성), W11은 L2(내가 작성 → AI 리뷰, 의견마다 채택/거절 + 이유를 PR에). W08 AI 프롬프트로 매직 넘버 표를 받았다고 적혀 있어도 감점하지 않는다. PR 'AI 활용 내역' 칸은 정직한지만 본다. 칸이 비었거나 같은 주 Devlog 'AI 활용 회고'와 어긋나면 P3-42 구술 후보로 표시한다(이 문항에서 감점하지 않음).
- 진위: P3-42 구술에서 이 문항이 뽑혀 핵심 코드·결정을 설명하지 못하면 이 문항 점수의 50%만 인정한다.

### P3-20 (1.27점) — 목표: W09-04, W09-11, W09-12, W09-13, W09-23, W09-24, W09-25, W09-26

**모범 답안**

[여는 곳·순서]
1) W09 PR(perf/soft-weapon-refs 또는 같은 역할) → Files changed의 UWeaponData 헤더: TObjectPtr<UStaticMesh>·TObjectPtr<UAnimMontage>(또는 원시 포인터) → TSoftObjectPtr<UStaticMesh>·TSoftObjectPtr<UAnimMontage>.
2) 교체 함수: ToSoftObjectPath()로 경로를 모아 UAssetManager::GetStreamableManager().RequestAsyncLoad(경로, 콜백). 콜백에서 .Get()으로 꺼내 SetStaticMesh 등으로 장착. 교체 경로에 LoadSynchronous가 섞여 있지 않은지.
3) 콜백: TWeakObjectPtr<캐릭터> WeakThis(this)를 람다에 캡처 → if (!WeakThis.IsValid()) return; 뒤에 접근. FStreamableDelegate::CreateWeakLambda(this, …)도 인정.
4) docs/perf/01-soft-reference.md: 측정 조건(대상 BP, Memory Size·Disk Size 중 무엇), Size Map 전/후 스크린샷, 수치(예: 캐릭터 BP 몇 MB → 몇 MB). 감소 폭이 작아도 스크린샷과 수치가 있으면 완료.
5) 참조 근거: Reference Viewer 캡처, 또는 '캐릭터 BP → WeaponData → 메시·몽타주' 참조 체인 설명. 히치: 교체 GIF·영상 + 어떻게 확인했는지(stat unit·stat fps 관찰, 여러 번 교체 등)와 결과 한 줄.
[부분 점수 예시]
- 메시만 소프트로 바꾸고 몽타주는 하드 참조 → 기준1 1점.
- RequestAsyncLoad는 있지만 교체 경로에 LoadSynchronous가 섞이거나 콜백 밖에서 장착 → 기준2 1점. 동기 로드만 → 0점.
- 약한 포인터를 캡처했지만 IsValid 확인 없이 바로 접근 → 기준3 1점. 람다 없이 FStreamableDelegate::CreateUObject로 멤버 함수 바인딩 → 1점(UObject 바인딩은 객체가 없으면 호출되지 않아 안전하지만, 목표인 '람다 + 약한 포인터 확인'이 보이지 않음). 람다에 원시 this만 캡처하고 확인 없음 → 0점.
- 스크린샷과 수치 중 하나만 있음 → 기준4 1점.
- 참조 근거와 히치 확인 기록 중 하나만 있음 → 기준5 1점. GIF만 있고 확인 방법·결과 글이 없으면 히치 쪽은 인정하지 않는다.
[구술 질문]
- 콜백이 불릴 때 캐릭터가 이미 파괴됐다면? 약한 포인터 대신 this를 캡처하면 무슨 일이 생기나?
- Reference Viewer와 Size Map은 각각 무엇을 보여 주나? 하드 참조가 메모리를 키우는 이유는? (보조: 핸들을 들고 있지 않고 다른 참조도 없으면 로드한 에셋은 어떻게 될 수 있나?)

**채점표 (10점)**

- [2] UWeaponData 메시·몽타주 TSoftObjectPtr 전환 diff(2/하나만 1)
- [2] 교체 시 RequestAsyncLoad → 완료 콜백에서 장착(2/동기 로드 혼용·콜백 밖 장착 1, 동기 로드만 0)
- [2] 람다에 약한 포인터 캡처 + 유효성 확인 뒤 접근(2/확인 없음·CreateUObject 1, 원시 this 0)
- [2] 성능 노트: 캐릭터 BP Size Map 전/후 스크린샷 + 감소 수치(2/하나 1)
- [2] 참조 관계 근거(Reference Viewer·참조 체인 설명) + 교체 히치 확인 기록(GIF + 방법·결과)(2/하나 1)

> 검토에서 고친 점: 기준5가 'stat unit 등 지표를 켠 GIF'를 요구함. 커리큘럼에 없는 산출물임. → 교체 GIF + 확인 방법·결과 글(PR 테스트 방법이나 성능 노트)로 바꿈. / 기준4가 Size Map 외에 Reference Viewer 캡처까지 요구함. 성능 노트의 필수 내용은 Size Map 전/후 스크린샷 + 수치뿐임. → 기준4는 Size Map 스크린샷·수치만 봄. Reference Viewer 근거는 기준5로 옮기고 참조 체인 글 설명·W09 TIL도 인정함. 구술 질문에 Reference Viewer를 추가함. / CreateUObject 바인딩을 1점 처리하면서 이유가 없음. 채점자가 이 방식이 안전하지 않다고 오해할 수 있음. 핸들 메모의 '컴포넌트가 참조하면 GC 안 됨'도 몽타주에는 맞지 않을 수 있음. → UObject 바인딩은 안전하지만 목표 패턴(람다 + 약한 포인터)이 안 보여 1점이라고 적음. 몽타주를 소프트 포인터로만 들고 있으면 GC될 수 있다는 점을 구술 보조로 고침.

> 작성 메모: - 문항 점수 50×3÷118 ≈ 1.27점. 심사 약 10분.
- 증거 위치: W09 PR(커리큘럼 브랜치 perf/soft-weapon-refs), docs/perf/01-soft-reference.md, docs/devlog/W09.md, unreal-study-log ue5-til/의 W09 TIL. 이름이 달라도 같은 역할이면 인정.
- 커리큘럼 성능 노트의 필수 내용은 'Size Map 전/후 스크린샷 + 수치'다. Reference Viewer 캡처는 필수가 아니므로 참조 체인을 글로 설명했어도 기준5의 참조 쪽을 인정한다.
- 히치는 W09 DoD('무기 교체 시 멈칫이 없다')다. stat unit 화면 녹화는 요구하지 않는다. 교체 GIF + 어떻게 확인했는지 적은 글이면 된다.
- Size Map 감소 폭은 팩 에셋 크기에 따라 작을 수 있다. '줄어든 수치를 근거와 함께 기록했는가'를 본다.
- FStreamableHandle 보관은 채점하지 않는다. 장착 뒤 메시 컴포넌트 등의 UPROPERTY가 에셋을 하드 참조하면 GC되지 않는다. 몽타주를 소프트 포인터로만 들고 있다가 나중에 .Get()하면 GC 뒤 null일 수 있다 — 구술 보조 질문으로만 쓴다.
- AI 활용: W09는 L2(내가 작성 → AI 리뷰, 의견마다 채택/거절 + 이유를 PR에). 이 범위 안의 AI 활용은 감점하지 않는다. PR 'AI 활용 내역' 칸은 정직한지만 본다. 칸이 비었거나 같은 주 Devlog 'AI 활용 회고'와 어긋나면 P3-42 구술 후보로 표시한다(이 문항에서 감점하지 않음).
- 진위: P3-42 구술에서 이 문항이 뽑혀 핵심 코드·결정을 설명하지 못하면 이 문항 점수의 50%만 인정한다.
- 보조로 Shipping zip에서 무기 교체를 여러 번 해 볼 수 있다. 채점은 PR·노트 기준.

### P3-21 (1.27점) — 목표: W10-22, W10-23, W10-28

**모범 답안**

[여는 곳·순서]
1. PR 검색: is:pr is:merged head:refactor/character-base. 다이어그램·테스트 방법·GIF·AI 활용 칸을 본다(L2라 AI 리뷰 의견마다 채택/거절 + 이유가 있다).
2. 처음 구조는 W10 PR의 Files changed로, 지금 구조는 exam-submit 코드로 본다: git grep -n -e AArenaCharacterBase -e HandleDeath -e "Super::" -- Source. 베이스 .h/.cpp와 파생 클래스의 override 함수, Super:: 호출을 본다.
3. 데미지 경로: git grep -n -e TakeDamage -e OnTakeAnyDamage -e ApplyPointDamage -e PostGameplayEffectExecute -- Source로 데미지를 받는 곳이 플레이어·적 공용 한 곳인지 본다.
4. 한 곳 수정: git log --oneline -- <HealthComponent·AttributeSet·베이스 경로>로 W10 이후 커밋을 찾고 git show --stat <커밋>으로 Files changed를 본다. 그 PR 본문, docs/devlog/W10.md·W15.md, docs/troubleshooting/에서 양쪽 적용 기록을 찾는다.
5. Shipping zip(GIF로 확인되지 않을 때): 적을 처치하고, 일부러 맞아 플레이어가 죽어 게임오버가 되는지 본다.
[정답 예]
- 베이스: protected UPROPERTY(VisibleAnywhere) TObjectPtr<UHealthComponent> HealthComponent; TObjectPtr<UCombatComponent> CombatComponent; 생성자에서 CreateDefaultSubobject. BeginPlay에서 OnDeath 구독 → virtual void HandleDeath()(State.Dead 태그·래그돌·타이머 Destroy는 공통).
- 플레이어: HandleDeath override → Super::HandleDeath() 후 입력 차단 등. 적: Super 후 AI 정지(예: AAIController의 BrainComponent->StopLogic) 등.
- 데미지: 판정 → ApplyPointDamage → HealthComponent(또는 베이스) 한 곳. W17 이후에는 GE_Damage → AttributeSet PostGameplayEffectExecute 한 곳.
- W17 이후 ASC 초기화(플레이어는 PlayerState, 적은 Character)는 갈라져도 된다. 데미지 적용과 사망 처리가 공통이면 된다.
- 다이어그램 예: Before = 플레이어·샌드백(W7 테스트 더미)이 각자 컴포넌트·사망 코드를 가짐 / After = AArenaCharacterBase ← 플레이어, AArenaEnemy(컴포넌트·가상 함수 표시).
- W15 'HealthComponent 복제 + OnRep' PR은 Files changed가 HealthComponent(와 UI) 쪽뿐이면 한 곳 수정 사례로 인정한다. 플레이어·적 체력이 모두 복제되는 GIF·테스트 방법이 있으면 더 좋다.
[만점 예] 베이스·override·Super 구조, Before/After 다이어그램, 양쪽 피격·사망 GIF(또는 Shipping 확인), 데미지는 AttributeSet 한 곳, W15 복제 PR에서 HealthComponent 파일만 바뀌었다.
[부분 예]
- 적이 사망 처리 코드를 따로 복사해 가진다 → 기준1 1.
- override에서 Super 호출을 빠뜨렸거나, 베이스에 IsPlayerControlled() 분기로 플레이어 전용 처리를 넣었다 → 기준2 1.
- 다이어그램이 After만 있다 → 기준3 1.
- 적 사망만 확인되고 플레이어 피격·사망은 어디서도 확인되지 않는다 → 기준4 1.
- 데미지 처리는 한 곳이지만 한 곳 수정 사례(기록·공통 파일만 바꾼 PR)가 없다 → 기준5 1. 플레이어와 적이 TakeDamage를 따로 override해 각자 체력을 깎는다 → 기준5 0.
[구술 질문(의심될 때)]
- 데미지 계산 버그가 나면 어느 파일·함수를 고치나요? 그러면 왜 플레이어와 적이 함께 고쳐지나요?
- 플레이어만 다르게 처리하는 것은 무엇이고 어떻게 나눴나요? Super를 빼면 어떻게 되나요? (부모의 공통 사망 처리가 실행되지 않는다)

**채점표 (10점)**

- [2] 베이스에 체력·전투 컴포넌트(W17 이후 ASC 연결)와 사망 처리, 플레이어·적 상속, 사망 처리 중복 없음(2/중복 남음 1/베이스 없음 0)
- [2] 차이는 virtual override + Super 호출로 나눔(2/Super 누락 또는 베이스에 플레이어 전용 분기 1/차이를 복사한 코드로 나눔 0)
- [2] W10 PR 본문에 Before/After 클래스 다이어그램(상속·컴포넌트)(2/한쪽만 1/없음 0)
- [2] 플레이어·적이 같은 경로로 피격·사망: W10 PR·Devlog GIF 또는 Shipping(2/한쪽만 확인 1/확인 불가 0)
- [2] 데미지 처리가 공용 한 곳 + 한 곳 수정이 양쪽에 적용된 사례(확인 기록 또는 공통 파일만 바꾼 PR)(2/한 곳이지만 사례 없음 1/플레이어·적이 따로 처리 0)

> 검토에서 고친 점: 만점 예가 'W17 AttributeSet 교체 PR에서 공통 파일만 바뀜'이었다. 하지만 ASC가 플레이어는 PlayerState, 적은 Character에 있으므로(ADR-0005) 그 PR은 반드시 양쪽 파일을 바꾼다. 실제로 나올 수 없는 사례다. → W17 PR은 한 곳 수정 사례로 쓰지 않는다고 적었다. 사례는 W15 HealthComponent 복제 PR처럼 공통 파일만 바꾼 PR로 바꿨고, ASC 초기화가 갈라진 것은 정상이라고 적었다. / 기준4가 리팩터링 PR의 GIF에서 플레이어 피격·사망을 요구했다. W10 Day 2 리팩터링 때는 적 AI가 아직 공격하지 않아서 보일 수 없을 수 있다. → 같은 주 PR·Devlog W10 GIF나 Shipping zip(W12 게임오버)으로도 인정하게 했다. evidence_weeks에 W13을 더했다. / 기준5는 커리큘럼이 만들게 하지 않는 '양쪽 적용 기록' 글에 의존했다. W10-28의 '같은 데미지 파이프라인'을 코드로 확인하는 조건도 없었다. 또 W17 이후에는 HealthComponent가 없을 수 있어 기준1을 그대로 적용할 수 없었다. → 기준5를 '데미지 처리가 공용 한 곳(코드로 확인) + 한 곳 수정 사례(확인 기록 또는 공통 파일만 바꾼 PR)'로 바꾸고, 데미지 경로를 찾는 git grep을 더했다. 기준1은 W17 이후 ASC 연결도 인정한다. 모든 기준을 2/1/0으로 나눴다.

> 작성 메모: 채점자 준비: 결함을 심지 않은 exam-submit 사본, PR 목록, git log, 최근 Release의 Shipping zip(W13 v0.3.0부터)을 준비한다. 문항 점수 = 50×3÷118 ≈ 1.27점. 진위: 구술(P3-42)에서 뽑혔는데 설명하지 못하면 이 문항 점수의 50%만 인정한다. AI: W10은 AI 레벨 L2(학생이 작성, AI가 리뷰)라 AI 리뷰를 쓴 것은 감점하지 않는다. PR 'AI 활용 내역'이 정직한지만 본다. 플레이어 클래스는 W03의 AArenaCharacter 이름을 그대로 써도 되고 AArenaPlayerCharacter로 바꿨어도 인정한다. 원거리 적(W11)이 AArenaEnemy를 상속해도 인정한다. W17에 체력이 AttributeSet으로 옮겨진 것은 커리큘럼 과제이므로 감점하지 않는다. W17 이후 ASC는 플레이어 PlayerState, 적 Character에 있으므로(ADR-0005) ASC 초기화 코드가 갈라진 것은 정상이다. 그래서 W17 AttributeSet 교체 PR은 기준5의 '공통 파일만 바꾼 PR' 예로 쓰지 않는다. W10 리팩터링 PR(Day 2) 때는 적이 아직 공격하지 않을 수 있으므로, 플레이어 피격·사망은 같은 주 PR·Devlog W10이나 Shipping zip(W12 게임오버)으로 확인해도 된다.

### P3-22 (1.69점) — 목표: W10-06, W10-24, W10-25, W10-26, W10-37

**모범 답안**

여는 순서
1) GitHub → Pull requests → Closed에서 is:pr is:merged head:feat/melee-enemy-ai(또는 M3 마일스톤)로 W10 PR을 연다. GIF·캡처, 테스트 칸, AI 활용 칸을 본다. W10은 L2라 '내가 작성, AI 리뷰 채택/거절 + 이유'가 기대된다. AI 사용은 감점하지 않는다. 칸이 비었거나 코드와 안 맞으면 P3-42 진위 확인 후보로 적어 둔다.
2) Files changed → BTTask_MeleeAttack.cpp: ExecuteTask(OwnerComp, NodeMemory)에서 AIController → Pawn → CombatComponent로 공격을 시작하고, 몽타주 종료 알림(컴포넌트 델리게이트, AnimInstance OnMontageEnded, Montage_SetEndDelegate 등)을 연결한 뒤 EBTNodeResult::InProgress를 반환하는지. 종료 콜백에서 FinishLatentTask(OwnerComp, EBTNodeResult::Succeeded). AbortTask는 연결 해제(또는 몽타주 정지) 뒤 Aborted. 폰·컴포넌트가 없으면 Failed.
3) exam-submit 코드: W17 과제 '적 공격도 GA로'에서 태스크가 어빌리티 활성화(TryActivateAbility 계열)로 바뀌었을 수 있다. 그때는 어빌리티 종료 알림(예: ASC의 OnAbilityEnded, 이름 확인 필요)을 받은 뒤 FinishLatentTask를 부르는지 본다. W10 diff와 현재 코드 중 하나라도 지연 태스크 흐름이 맞으면 인정.
4) BTService_UpdateTargetDistance: 생성자에서 Interval 설정, TickNode에서 BB의 타깃 → 거리 계산 → SetValueAsFloat. 타깃이 없으면 건너뛴다.
5) 에셋·맵: 04-behavior-tree.md 그림과 PR·W10 Devlog·TIL 캡처로 BT 구조(서비스 위치 포함), BB 키, P 키 화면을 먼저 본다. 캡처로 확인이 안 되는 것만 에디터에서 본다. 블록3 사본을 결함을 심기 전에 빌드해 열고(약 5분) ① 게임 맵의 NavMeshBoundsVolume 선택 → 뷰포트에서 P → 적이 다니는 바닥이 초록인지 ② BB 에셋의 키 목록(추적 대상 Object, 순찰 지점 Vector 등) ③ BT 에셋의 Blackboard 지정과 서비스 위치를 본다. 아무것도 저장하지 않고 닫은 뒤 git status가 깨끗한지 확인한다.
6) 최신 Release의 Shipping zip을 실행해 1분 관찰(혼자 시작할 수 없으면 v0.3.0 zip): 적이 돌아다니다 플레이어를 보면 쫓아와 공격하고 잠깐 쉰다. W11 이후라 '보면 추적'이 정상이다.
만점 예: GIF에 4단계가 차례로 보이고, 태스크가 InProgress → 몽타주 종료 → FinishLatentTask, AbortTask까지 있으며, 맵·BB·BT가 캡처나 에디터에서 확인된다.
부분 예: 몽타주 재생 직후 Succeeded 반환(공격 중에 다음 노드로 넘어감) → 기준4 1점. AbortTask만 없음 → 기준4 2점. 서비스 코드는 있으나 BT에 안 붙음 → 기준5 0.5점. 아레나 바닥 일부에 NavMesh가 없어 적이 못 감 → 기준1 0.5점. 캡처가 없고 사본도 빌드되지 않아 BB 키를 볼 수 없음 → 기준2 1점.
참고(감점 아님): BT 노드는 기본적으로 인스턴스를 만들지 않고 여러 AI가 같은 노드를 공유한다. OwnerComp를 멤버에 저장하면 적이 여럿일 때 섞인다(bCreateNodeInstance = true나 NodeMemory로 피함). 꼬리 질문 소재로만 쓴다.
구술 질문(진위 확인)
- 'ExecuteTask가 InProgress를 돌려준 뒤 이 태스크는 누가, 언제 끝내나요? 공격 중에 플레이어가 사거리를 벗어나면 어떻게 되나요?'(몽타주 종료 콜백의 FinishLatentTask / 거리 데코레이터의 Observer Aborts가 Self·Both면 브랜치가 중단되어 AbortTask가 불림)
- '내 BT에서 Selector와 Sequence를 어디에 왜 놓았고, BB 키는 무엇을 두었는지 엔진 노트의 그림으로 설명해 보세요.'

**채점표 (10점)**

- [1.5] NavMesh: 게임 맵에 NavMeshBoundsVolume이 있고, P 키 화면(응시자 캡처 또는 채점자가 사본에서 확인)에서 적이 다니는 바닥이 초록(1.5) / 볼륨은 있으나 아레나 바닥 일부가 빠져 적이 못 가는 곳이 있거나, 맵을 볼 수 없어 순찰 GIF로만 확인(0.5) / 볼륨 없음(0)
- [2] BT·BB 에셋과 연결: BT·BB 에셋이 있고, BB에 BT가 쓰는 키(추적 대상·순찰 지점 등)가 있으며, BT의 Blackboard 지정이 그 BB임(엔진 노트·PR 캡처·사본 중 한 곳에서 확인)(2) / 에셋은 있으나 키나 BT 연결 중 하나를 확인할 수 없음(1) / 에셋 없음(0)
- [2] BT 동작: PR GIF(또는 Shipping zip)에서 순찰 → 추적 → 사거리 안 공격 → 쿨다운이 차례로 보임(2) / 한 단계가 안 보임(1) / 동작 증거 없음(0)
- [3] UBTTask_MeleeAttack: PR diff나 현재 코드에 CombatComponent(W17 이후는 어빌리티) 재사용, InProgress 반환, 몽타주(어빌리티) 종료 콜백에서 FinishLatentTask, AbortTask 처리가 있음(3) / AbortTask만 빠짐(2) / 공격을 시작하고 바로 Succeeded 반환(1) / 태스크 없음(0)
- [1.5] UBTService_UpdateTargetDistance: Interval 설정, TickNode에서 타깃 거리 계산 → BB 값 갱신, BT에 붙어 있음(1.5) / 코드는 있으나 BT에 붙지 않음(0.5) / 없음(0)

> 검토에서 고친 점: 커리큘럼 W10은 P 키 NavMesh 화면 캡처나 BB 키 목록을 산출물로 요구하지 않는데, 캡처가 없으면 기준1을 0.5점으로, 엔진 노트에 키 목록이 없으면 기준2를 1점으로 깎았다. 기준2는 1부 범위인 엔진 노트 04 작성(W10-27)에 점수를 주고 있어, covers인 W10-37(BB 키 정의·BT 연결)을 직접 보지 않았다. → 캡처가 없으면 채점자가 블록3 사본을 결함 심기 전에 열어 P 키 화면·BB 키·BT의 Blackboard 지정을 직접 확인하게 했다(저장 없이 닫고 git status 확인). 이 경우 감점하지 않는다. 기준2는 BB 키와 BT 연결로 바꿨다. / 구술 질문의 '사거리를 벗어나면 AbortTask가 불린다'는 데코레이터의 Observer Aborts 설정에 따라 달라진다. 또 최신 Shipping zip을 혼자 시작할 수 없는 경우의 처리가 없었다. → 모범 답에 'Observer Aborts가 Self·Both면'이라는 조건을 넣었다. 최신 zip을 혼자 시작할 수 없으면 v0.3.0 zip을 쓰도록 했다.

> 작성 메모: 문항 점수 1.69점(50×4÷118). 채점표 1점 = 0.169점. 시험 7일 전 제출된 exam-submit 태그로 시험 전에 심사한다. 진위: P3-42 구술에서 이 문항이 뽑혀 태스크의 지연 흐름이나 BT 구조를 설명하지 못하면 이 문항 점수의 50%만 인정한다. W10은 AI 레벨 L2이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. 커리큘럼은 P 키 화면·BT 그래프·BB 키 캡처를 따로 요구하지 않는다. 캡처가 없어도 감점하지 말고 채점자가 에디터에서 직접 본다. 에디터 확인 절차: 블록3 사본을 결함을 심기 전에 빌드해 열고, 아무것도 저장하지 않고 닫은 뒤 git status가 깨끗한지 확인한다(같은 태그를 다른 폴더에 따로 Clone해도 된다). BT·BB·맵 .uasset은 GitHub에서 LFS 파일로 존재만 보인다. W17 과제 '적 공격도 GA로'에서 BTTask가 어빌리티를 켜도록 바뀌는 것은 정상 진화이므로 W10 PR diff를 먼저 본다. 공통 베이스 리팩터링(AArenaCharacterBase)과 클래스 다이어그램은 P3-21, 엔진 노트 04 작성(W10-27)·RunBehaviorTree·Selector/Sequence·Observer Aborts 설명은 1부에서 채점한다. 브랜치·문서 이름은 커리큘럼 예시라 같은 역할이면 이름이 달라도 인정한다.

### P3-23 (1.27점) — 목표: W11-04, W11-10, W11-13, W11-16

**모범 답안**

여는 순서
1) exam-submit 코드(예: Source/ActionArena/AI/): UAIPerceptionComponent 생성, UAISenseConfig_Sight(SightRadius, LoseSightRadius, PeripheralVisionAngleDegrees, DetectionByAffiliation)와 UAISenseConfig_Damage를 ConfigureSense로 등록, 주 감각은 Sight. BP에서 설정했으면 PR 캡처나 블록3 사본(결함을 심기 전, 저장하지 않고 닫기)으로 본다. Hearing은 UAISenseConfig_Hearing 코드가 있거나, W11 TIL·디버깅 도구 노트에 Hearing 설정과 소리를 내는 쪽(ReportNoiseEvent 등)이 정리돼 있으면 인정.
2) Damage 감각은 피해를 줄 때 UAISense_Damage::ReportDamageEvent를 불러야 자극이 생긴다(AISense_Damage.h). 저장소에서 ReportDamageEvent를 검색한다. W17 GAS 이전 뒤 AttributeSet 쪽으로 옮겨졌어도 인정.
3) PR feat/ai-perception → Files changed: OnTargetPerceptionUpdated를 AddDynamic(UFUNCTION 필요)으로 연결, Stimulus.WasSuccessfullySensed()가 true면 SetValueAsObject(추적 대상), false면 ClearValue(또는 마지막 위치를 순찰 지점에 저장). W10에서 BeginPlay 등에 넣은 '타깃 = 플레이어 고정' 줄이 삭제(빨간 줄)로 보여야 한다. 팀 인터페이스가 없으면 모두 중립이라 중립 감지를 켜야 감지된다.
4) 동작: PR GIF에서 감지 → 추적 → 놓침 → 순찰 복귀. GIF가 없거나 짧으면 P3-24에서 Shipping zip을 실행할 때 적 시야에 들어갔다가 멀리 달아나 본다.
5) Gameplay Debugger 화면: Perception 카테고리(시야 범위·감지 대상)와 BehaviorTree 카테고리(실행 중 노드·BB 값)가 보이는지. W22 시연 영상의 'AI 디버거(Perception · BT)' 장면도 인정.
6) TS-003: '4. 원인'의 근거가 Visual Logger 화면 캡처인지 본다. 타임라인의 과거 시점을 짚어 '이때 AI가 이 위치에서 이렇게 판단했다'고 쓰면 완료. 코드에 UE_VLOG 기록이 있으면 근거가 더 확실하다(필수 아님). TS 문서 전체 품질은 여기서 보지 않는다.
AI 활용 칸: W11은 L2. AI 사용은 감점하지 않는다. 칸이 비었거나 코드와 안 맞으면 P3-42 진위 확인 후보로 적어 둔다.
만점 예: 감각 설정·Damage 보고·감지/상실 BB 갱신·고정 코드 삭제가 diff에 있고, 두 카테고리가 보이는 디버거 화면, Visual Logger 캡처의 시점을 짚어 원인을 쓴 TS-003이 있다.
부분 예: Hearing이 코드·TIL 어디에도 없음 → 기준1 1.5점. Damage 감각 설정은 있으나 ReportDamageEvent 호출이 없어 등 뒤 피격에 반응하지 않음 → 기준1 1점. W10 고정 코드가 남아 놓쳐도 계속 추적(②·③ 빠짐) → 기준2 1점. TS-003에 Visual Logger 캡처만 붙이고 '로그를 보고 고쳤다'만 적음 → 기준4 1.5점.
구술 질문(진위 확인)
- '적이 플레이어를 못 볼 때 무엇부터 확인하나요?'(Gameplay Debugger → 반경·각도 → 소속 감지(팀이 없으면 중립) → 자극 소스 → 시야를 막는 콜리전)
- 'TS-003 버그는 왜 Gameplay Debugger가 아니라 Visual Logger로 찾았나요? 타임라인의 어느 시점을 보고 원인을 알았나요?'(지금 순간의 오버레이 vs 시간축 녹화를 되감아 과거 프레임 분석)

**채점표 (10점)**

- [2] 감각 설정: Sight·Damage 설정과 피해를 줄 때 ReportDamageEvent 호출이 있고, Hearing이 코드나 W11 TIL·노트로 확인됨(2) / Hearing 확인만 안 됨(1.5) / Sight만 있거나 ReportDamageEvent 호출이 없음(1) / Perception 없음(0)
- [3] 감지·상실 → BB: ① OnTargetPerceptionUpdated에서 감지 시 BB 설정·상실 시 비움 ② W10 '플레이어 고정' 코드 삭제(diff) ③ GIF나 Shipping zip에서 감지 → 추적 → 놓침 → 순찰 복귀. 셋 다(3) / 하나 빠짐(2) / 둘 빠짐(1) / Perception 처리 없음(0)
- [2] Gameplay Debugger: ' 키 화면(캡처나 W22 시연 영상)에 Perception(시야 범위·감지 대상)과 BT 상태(실행 중 노드·BB 값)가 함께 보임(2) / 한 카테고리만 보임(1) / 없음(0)
- [3] Visual Logger 근거: TS-003 '원인' 칸에 Visual Logger 화면 캡처가 있고, 캡처의 시점과 그때 AI의 판단(로그 줄)·위치를 짚어 원인을 설명함(3) / 캡처는 있으나 어느 시점에서 무엇을 봤는지 글이 없음(1.5) / Visual Logger 근거 없음(0)

> 검토에서 고친 점: 기준4에 covers 밖의 디버깅 도구 비교 노트(W11-18, 1부 범위)가 점수로 걸려 있었다. 부분 점수 기준 '근거 설명이 약하거나(1~2)'는 주관적이다. 기준2의 부분 점수 '1~2'도 판정 기준이 없었다. → 비교 노트를 채점에서 뺐다. 기준4는 'Visual Logger 캡처 + 캡처 시점·판단·위치를 짚은 글(3) / 캡처만(1.5)'으로 바꿨다. 기준2는 세 요소(감지·상실 처리, 고정 코드 삭제, GIF) 가운데 빠진 개수로 3/2/1/0을 준다. / W11 과제는 Hearing을 요구하지 않는데, Hearing 증거가 없을 때 몇 점인지 정해져 있지 않았다. notes에는 원거리 적이 P3-18·P3-19에서 채점된다고 잘못 적혀 있었다(W11-14는 1부). Shipping에 Gameplay Debugger가 없다는 안내도 빠져 있었다. → Hearing만 빠지면 1.5점으로 정했다. 교차 참조는 비교 노트·UE_VLOG·원거리 적 구현은 1부, 피격 리액션은 P3-18, 적 스탯 DT는 P3-19, TS 작성(W11-17)은 P3-36으로 고쳤다. Shipping zip으로는 디버거를 확인하지 않는다고 적었다.

> 작성 메모: 문항 점수 1.27점(50×3÷118). 채점표 1점 = 0.127점. 진위: P3-42 구술에서 이 문항이 뽑혀 감지 처리 코드나 TS-003의 근거를 설명하지 못하면 이 문항 점수의 50%만 인정한다. W11은 L2이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. W11 과제는 '시야 + 피격'만 요구하므로 Hearing은 코드에 없어도 W11 TIL·노트 정리로 인정하고, 그것도 없으면 0.5점만 깎는다. Visual Logger 녹화 파일 제출은 요구하지 않는다(커리큘럼 산출물은 TS 문서의 캡처). Gameplay Debugger 화면은 W22 시연 영상(부록 구성안의 'AI 디버거(Perception · BT)' 장면)으로도 인정한다. Shipping 빌드에는 Gameplay Debugger가 빠져 있으므로 zip으로 확인하지 않는다. 디버깅 도구 비교 노트(W11-18)·UE_VLOG 코드(W11-11)·원거리 적 구현(W11-14)은 1부, 피격 방향 리액션은 P3-18, 원거리 적 스탯 DataTable은 P3-19, TS-003 문서 작성(W11-17)은 P3-36에서 채점하고, 여기서는 Visual Logger로 과거 프레임을 분석해 원인을 찾았는지만 본다.

### P3-24 (1.27점) — 목표: W12-04, W12-05, W12-09, W12-11, W12-12, W12-22

**모범 답안**

여는 순서
1) 코드(예: Source/ActionArena/Game/): UENUM enum class EArenaPhase 4상태. GameMode에 전환 함수(예: SetPhase)가 있고, GameState가 CurrentPhase·CurrentWave·RemainingEnemies를 보관하는지(W15 이후는 Replicated). 전환 로직이 GameState에 있거나 값이 GameMode에만 있으면 1점.
2) 웨이브: USTRUCT 행 구조체(FTableRowBase 상속, 적 클래스·수·간격). 스포너가 FindRow나 GetAllRows로 현재 웨이브 행을 읽고 타이머로 간격을 두고 스폰하는지. DT 값은 GitHub에서 안 보이므로 PR 캡처나 CSV(있으면)로 보고, 없으면 블록3 사본에서 DT를 연다.
3) SaveGame: 저장 필드가 UPROPERTY인지, DoesSaveGameExist → LoadGameFromSlot → Cast(없을 때만 CreateSaveGameObject) → 최고 기록은 더 클 때만 갱신 → SaveGameToSlot 또는 AsyncSaveGameToSlot. 흔한 실수: 불러오기 전에 새 객체로 덮어써 기록이 0이 된다.
4) UI·전환: 위젯 클래스(예: Source/ActionArena/UI/, C++ 부모 없이 WBP만 있어도 인정)와 UGameplayStatics::OpenLevel 호출(BP Open Level 노드도 인정). W15 이후 OpenLevel에 listen 옵션을 붙였거나 ServerTravel을 써도 인정. 일시정지는 SetGamePaused와 입력 모드 전환.
5) 검증 기록: PR 테스트 칸, W12 Devlog 목표 vs 결과 표, v0.3.0 90초 영상 중 한 곳에 3회 루프와 재실행 후 기록 유지 결과가 있는지.
6) Shipping zip 실행(약 10분): 최신 Release(v1.0.0, 없으면 그 전 최신) zip을 풀어 exe 실행 → 혼자 시작(메뉴에 호스트/참가가 있으면 호스트) → 웨이브 진행(남은 적 감소 → 휴식 → 다음 웨이브) → 가만히 있어 게임오버 → 메뉴 → 종료 → exe 다시 실행 → 최고 기록 확인(메뉴나 다음 게임오버 화면). 2인이 있어야 시작되는 구조면 v0.3.0 zip으로 같은 순서를 밟는다. 3회 루프는 기록으로 보고 직접은 1회면 된다. Shipping에는 보통 치트가 빠져 있으니 치트로 줄이지 않는다.
AI 활용 칸: W12는 L2. AI 사용은 감점하지 않는다. 칸이 비었거나 코드와 안 맞으면 P3-42 진위 확인 후보로 적어 둔다.
만점 예: 코드 요소가 모두 있고, PR·Devlog·영상 중 한 곳에 3회 루프 결과가 있으며, Shipping에서 재실행 후에도 기록이 남는다.
부분 예: Shipping 재실행 후 기록이 0 → 기준5 1점(코드가 불러오기 전에 덮어쓰면 기준3도 1점). 메뉴로 돌아온 뒤 입력이 먹통 → 기준4 1점. 웨이브 수·간격 일부가 코드 상수 → 기준2 1점. 두 zip 모두 실행되지 않음 → 기준4·5는 GIF와 기록으로만 보고 각각 최대 1점.
구술 질문(진위 확인)
- '웨이브 번호와 남은 적 수를 GameMode가 아니라 GameState에 둔 이유는?'(GameMode는 서버에만 있고, 모두가 봐야 하는 상태는 GameState)
- '최고 기록을 불러와 갱신하고 저장하는 순서를 말해 보세요. 어디서 틀리면 기록이 초기화되나요?'

**채점표 (10점)**

- [2] EArenaPhase: 4상태 enum class, GameMode가 전환하고 GameState가 보관하는 코드(2) / 전환과 보관이 한 클래스에 몰림(1) / 없음(0)
- [2] 웨이브 DataTable: 행 구조체(적 종류·수·간격)와 DT 에셋이 있고 스포너가 표를 읽어 스폰(2) / 표는 있으나 수·간격 일부가 코드 상수(1) / 표 미사용(0)
- [2] SaveGame: USaveGame 자식의 최고 웨이브 UPROPERTY, 불러오기 → 더 클 때만 갱신 → 저장 코드(2) / 저장만 있거나 불러오기 전에 덮어씀(1) / 없음(0)
- [2] 메뉴·일시정지·게임오버 UI와 OpenLevel: 위젯 3종과 전환 코드(BP 포함)가 있고, PR GIF나 Shipping zip에서 메뉴 → 게임 → 일시정지 → 게임오버 → 메뉴가 동작(2) / 위젯 하나가 빠지거나 전환 뒤 입력 먹통(1) / 없음(0)
- [2] 루프 검증: PR 테스트 칸·W12 Devlog·v0.3.0 영상 중 한 곳에 3회 연속 루프와 재실행 후 기록 유지 결과가 있고, 채점자의 Shipping zip(최신 또는 v0.3.0) 확인에서 루프 1회 + exe 재실행 후 기록이 남음(2) / 기록이나 Shipping 확인 중 하나만(1) / 없음(0)

> 검토에서 고친 점: 최신 Shipping zip을 '혼자(호스트 1인) 시작'할 수 있어야 한다는 요구는 커리큘럼에 없다. 2인 전용 구조라면 기준4·5가 최대 1점으로 깎였다. DT 값 PR 캡처도 커리큘럼 산출물이 아니다. 위젯과 OpenLevel은 C++만 전제했고, 3회 루프 기록 위치에서 v0.3.0 90초 영상이 빠져 있었다. → 최신 빌드를 혼자 시작할 수 없으면 W13 산출물인 v0.3.0 Shipping zip으로 확인하고 감점하지 않는다. DT 값은 캡처가 없으면 사본에서 확인한다. WBP와 BP Open Level 노드도 인정한다. 루프 기록은 PR·Devlog·v0.3.0 영상 중 한 곳이면 된다. 교차 참조(풀링·ADR-0003은 1부, M3 회고는 P3-40)도 고쳤다.

> 작성 메모: 문항 점수 1.27점(50×3÷118). 채점표 1점 = 0.127점. 진위: P3-42 구술에서 이 문항이 뽑혀 GameMode/GameState 분리나 저장 순서를 설명하지 못하면 이 문항 점수의 50%만 인정한다. W12는 L2이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. 채점자는 시험 전에 Shipping zip을 실행한다(약 10분). 커리큘럼은 W13에 v0.3.0 '싱글플레이 MVP' Shipping zip을 Release에 첨부하게 하므로, 최신 빌드가 2인 전용이라 혼자 시작할 수 없어도 v0.3.0 zip으로 보고 감점하지 않는다. 두 zip 모두 없거나 실행되지 않으면 기준4·5는 PR GIF와 기록으로만 판단하고 각각 최대 1점. DT 값 캡처는 커리큘럼이 요구하지 않으므로, 없으면 블록3 사본을 결함을 심기 전에 열어 본다(저장하지 않고 닫은 뒤 git status 확인). 패키징 절차는 P3-34, 풀링·ADR-0003·AsyncSave 설명은 1부, M3 회고는 P3-40에서 채점한다. 2인 전환(W15) 뒤 메뉴에 호스트/참가 버튼이 생기거나 OpenLevel에 listen 옵션이 붙은 것은 정상이다.

### P3-26 (1.69점) — 목표: W15-01, W15-06, W15-07, W15-08, W15-09, W15-12, W14-31, W17-18

**모범 답안**

여는 순서
1) PR feat/coop-combat → Files changed: UFUNCTION(Server, Reliable) ServerAttack, 서버(HasAuthority)에서만 판정·데미지, UFUNCTION(NetMulticast, Unreliable) 피격 연출. 클라에서도 데미지를 적용하면 2번 깎인다. 현재 코드는 W17 GA_MeleeCombo로 바뀌었을 수 있으니 PR diff로 판단한다.
2) PR feat/replicated-health: 컴포넌트 생성자의 SetIsReplicatedByDefault(true), Health의 ReplicatedUsing=OnRep_Health, GetLifetimeReplicatedProps의 DOREPLIFETIME. C++ OnRep은 서버에서 자동 호출되지 않으므로 서버(리슨 호스트)에서 값을 바꾼 뒤 델리게이트를 직접 브로드캐스트하는지 본다. W9 HUD 위젯(예: UArenaHUDWidget, WBP) 파일이 Files changed에 없거나, 바뀐 줄이 구독 대상(바인딩)뿐이면 'W9 구조 재사용' 완료. W17에서 AttributeSet으로 바뀐 것은 정상.
3) 서버 전용·GameState: 스포너·웨이브 진행에 HasAuthority 확인이 있거나 GameMode 안에서만 실행되는지(GameMode·AIController는 서버에만 있다). GameState에 DOREPLIFETIME(웨이브, 남은 적), OnRep → 델리게이트 → HUD. PR GIF나 200ms 영상에서 두 창의 HUD 값이 같은지.
4) 리스폰: 서버에서 사망 처리 → 타이머 → GameMode RestartPlayer(또는 관전 카메라로 SetViewTarget). 리스폰 뒤 HUD가 새 폰을 다시 구독해 갱신되는지 GIF나 영상으로 본다(W17 이후 ASC가 PlayerState에 있으면 다시 구독하지 않아도 된다).
5) W14-31: Closed PR 중 W14 이후 네트워크 PR 3개(예: feat/netlab, feat/coop-combat, feat/replicated-waves)를 골라 테스트 칸 체크, 셀프 체크 칸, 실행 위치 표시(예: // [서버] 주석, PR 변경 사항의 '서버에서 실행')를 본다.
6) 영상·기록: 200ms 영상은 두 창이 한 화면에 보이고 체력·웨이브·남은 적이 같은지 본다. 반응 지연은 허용, 값이 다르면 불일치. 10분 기록은 영상(전체 또는 YouTube 일부 공개) 또는 W17 Devlog·릴리즈 노트에 조건(2인, 200ms)·시간·결과가 적혀 있으면 인정. README 비교 영상은 있는지만 본다.
AI 활용 칸: W14~W15는 L2. AI 사용은 감점하지 않는다. 칸이 비었거나 코드와 안 맞으면 P3-42 진위 확인 후보로 적어 둔다.
만점 예: 세 PR diff의 RPC·복제·권한 분기가 맞고, 네트워크 PR 3개 모두 테스트·셀프 체크·실행 위치를 갖췄으며, 200ms 일치 영상·10분 기록·README 비교 영상이 있다.
부분 예: 데미지를 클라에서도 적용(2배) → 기준1 1점. 피격 연출 Multicast가 Reliable → 기준1 1.5점. 호스트 HUD만 안 갱신(서버 쪽 브로드캐스트 누락) → 기준2 1점. PR 체크박스는 다 있으나 실행 위치 표시가 없음 → 기준5 1점. 10분 기록 없이 200ms 영상과 비교 영상만 → 기준6 1점.
구술 질문(진위 확인)
- '클라이언트가 공격 키를 누르면 어떤 함수가 어느 머신에서 차례로 실행되나요?'(클라 입력 → Server RPC → 서버 판정·데미지 → 복제·Multicast 연출)
- '리슨 서버 호스트의 HUD는 OnRep이 자동으로 안 불리는데 어떻게 갱신했나요?'

**채점표 (10점)**

- [2] 공격 RPC(feat/coop-combat diff): Server RPC → 서버에서만 판정·데미지 → Unreliable Multicast 연출(2) / 흐름은 맞으나 Multicast가 Reliable(1.5) / 데미지가 클라에서도 적용되거나 연출이 서버 화면에만 나옴(1) / Server RPC 없음(0)
- [2] 체력 복제 → UI(feat/replicated-health diff): SetIsReplicatedByDefault, ReplicatedUsing OnRep → 델리게이트, 서버 쪽 직접 브로드캐스트가 있고, Files changed에 W9 HUD 위젯 파일이 없거나 구독 대상만 바뀜(2) / 호스트나 클라 한쪽 HUD만 갱신되거나, 위젯이 Tick·Binding으로 체력을 읽게 바뀜(1) / 체력 복제 없음(0)
- [2] 서버 전용 스폰·AI와 GameState 복제: 권한 분기 코드, 웨이브·남은 적 DOREPLIFETIME + OnRep → HUD, GIF·영상에서 두 HUD 값 일치(2) / 권한 분기와 GameState 복제 중 하나만(1) / 없음(0)
- [1] 사망 → 리스폰(또는 관전): 서버 쪽 처리 코드와 리스폰 뒤 HUD 갱신이 보이는 GIF·영상(1) / 코드만 있거나 리스폰 뒤 HUD 멈춤(0.5) / 없음(0)
- [1.5] W14 이후 PR 규칙: 고른 네트워크 PR 3개 모두 테스트 'PIE 2인 Listen Server + 지연 200ms'와 셀프 체크 '서버/클라 실행 위치 확인'이 체크되고, 실행 위치가 코드 주석이나 PR 본문에 적힘(1.5) / 체크는 모두 있으나 실행 위치 표시 없음(1) / 3개 중 일부 PR만 체크(0.5) / 없음(0)
- [1.5] 검증 영상·기록: ① 지연 200ms 2인 상태 일치 영상 ② 10분 연속 무버그 기록(영상 또는 조건·시간·결과 글) ③ README의 RPC vs GAS 비교 영상. 있는 것 하나당 0.5(최대 1.5) / 하나도 없음(0)

> 검토에서 고친 점: 기준2의 'W9 HUD 위젯은 거의 그대로'는 주관적이다. 기준5·6의 부분 점수가 '0.5~1' 범위로만 적혀 있어 판정할 수 없었다. Multicast가 Reliable인 흔한 경우의 점수도 정해져 있지 않았다. notes에는 ADR-0004가 'P3-36 등'에서 채점된다고 잘못 적혀 있었다(W15-11은 1부). → 기준2는 'Files changed에 위젯 파일이 없거나 구독 대상만 바뀜'으로 바꿨다. 기준5는 1.5/1/0.5/0으로 단계를 정했다. 기준6은 세 증거 하나당 0.5점이다. Reliable Multicast는 1.5점이다. 교차 참조를 고치고, PR이 없는 기능은 커밋 diff로 보고 기준5는 PR이 있는 작업에서 고르도록 했다. W17 이후 ASC가 PlayerState에 있으면 리스폰 뒤 다시 구독하지 않아도 된다고 적었다.

> 작성 메모: 문항 점수 1.69점(50×4÷118). 채점표 1점 = 0.169점. 진위: P3-42 구술에서 이 문항이 뽑혀 공격 RPC 흐름이나 호스트 HUD 갱신 방법을 설명하지 못하면 이 문항 점수의 50%만 인정한다. W14~W16은 L2이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. W17 '전투 이전'으로 ServerAttack·HealthComponent가 GAS로 바뀌는 것은 정상 진화이므로, 현재 코드에 없어도 감점하지 않고 W15 PR diff로 본다(Squash merge여도 PR 페이지에 diff가 남는다). PR 없이 커밋만 있는 기능은 그 커밋 diff로 보고, 기준5는 PR이 있는 네트워크 작업 중에서 3개를 고른다(3개가 안 되면 0.5). 10분 기록은 GAS 전환 뒤에 다시 찍거나 쓴 것도 인정한다. TS-005·006(W15-10)은 P3-36, ADR-0004(W15-11)와 몽타주 동기화·러버밴딩 설명은 1부, README 비교 영상의 품질·설명(W17-16)은 P3-38에서 채점하므로 여기서는 비교 영상이 있는지만 본다. NetLab 실험(W14)은 P3-25 라이브 문항이다. 브랜치 이름은 커리큘럼 예시라 같은 역할이면 달라도 인정한다.

### P3-27 (1.69점) — 목표: W16-02, W16-04, W16-05, W16-06, W16-17, W16-19

**모범 답안**

여는 순서
1) .uproject(텍스트 파일)의 Plugins 배열에 GameplayAbilities가 Enabled: true인지. 목록에 없으면 블록3 사본을 결함을 심기 전에 열어 Edit → Plugins에서 켜져 있는지 본다(UE 5.8 기본값 확인 필요, 저장하지 않고 닫은 뒤 git status 확인). Source/ActionArena/ActionArena.Build.cs의 PublicDependencyModuleNames(또는 Private)에 세 모듈이 있는지.
2) ASC: UArenaAbilitySystemComponent(UAbilitySystemComponent 상속) 클래스가 있고, PlayerState와 적 Character가 CreateDefaultSubobject로 이 클래스를 만드는지(SetIsReplicated, 플레이어 Mixed·적 Minimal Replication Mode면 더 좋음, 감점 없음). 초기화: 플레이어는 서버 PossessedBy와 클라 OnRep_PlayerState에서 InitAbilityActorInfo(PlayerState, 캐릭터). 적은 BeginPlay나 PossessedBy에서 InitAbilityActorInfo(this, this).
3) IAbilitySystemInterface: 적 Character, 그리고 PlayerState나 플레이어 캐릭터 중 하나 이상이 GetAbilitySystemComponent() const override를 구현하는지. 플레이어 캐릭터가 PlayerState의 ASC를 돌려주면 W17의 SendGameplayEventToActor(캐릭터)와 적이 플레이어에게 GE를 적용하는 코드가 ASC를 찾을 수 있다. 캐릭터 쪽이 없어도 W17 기능이 동작하면 감점하지 않고 꼬리 질문 소재로 쓴다.
4) AttributeSet: FGameplayAttributeData 5개와 접근자 매크로. PreAttributeChange에서 Health 0~MaxHealth, Stamina 0~MaxStamina. Instant·Periodic GE는 Base 값을 바꾸므로 PostGameplayEffectExecute(또는 PreAttributeBaseChange)에서도 Clamp해야 완료. PostGameplayEffectExecute에서 IncomingDamage를 읽어 0으로 되돌린 뒤 Health에 반영하는지. 2인용이면 속성 복제(DOREPLIFETIME_CONDITION_NOTIFY + GAMEPLAYATTRIBUTE_REPNOTIFY)도 보인다.
5) gas-tags.md: 4계층과 태그별 한 줄 용도. 실제 태그 정의(Config/DefaultGameplayTags.ini나 C++ 네이티브 태그)와 문서의 태그 3개를 골라 대조한다.
6) ADR-0005: 템플릿 칸(맥락·선택지 표·결정과 이유·결과). 핵심 이유는 PlayerState는 리스폰 뒤에도 속성·어빌리티가 유지되고, Character는 폰과 수명이 같아 단순하다는 것.
AI 활용 칸: W16은 L2. AI 사용은 감점하지 않는다. 칸이 비었거나 코드와 안 맞으면 P3-42 진위 확인 후보로 적어 둔다.
만점 예: 위 6가지가 모두 있고, Clamp가 두 곳에 있으며, 태그 문서와 실제 태그가 일치한다.
부분 예: 엔진 기본 UAbilitySystemComponent를 그대로 씀 → 기준2 1점. 클라 초기화(OnRep_PlayerState) 누락 → 기준2 1점. 적만 인터페이스를 구현 → 기준3 0.5점. Clamp가 PreAttributeChange에만 있음 → 기준4 1.5점. 태그 문서에 계층만 있고 용도가 없음 → 기준5 0.5점.
구술 질문(진위 확인)
- 'ASC를 PlayerState에 두면 초기화를 왜 PossessedBy와 OnRep_PlayerState 두 곳에서 하나요?'(서버는 빙의 시점, 클라는 PlayerState 복제가 도착한 시점)
- 'IncomingDamage 메타 속성을 왜 쓰고, 그 계산은 어느 머신에서 하나요?'(데미지 계산을 한 곳에 모음, 서버)

**채점표 (10점)**

- [1.5] 플러그인·모듈: GameplayAbilities 플러그인이 켜져 있고(.uproject 또는 Plugins 창), Build.cs에 GameplayAbilities·GameplayTags·GameplayTasks(1.5) / 모듈 일부 누락(0.5) / 없음(0)
- [2] ASC 클래스와 배치: UArenaAbilitySystemComponent를 PlayerState(플레이어)와 적 Character가 만들고, 플레이어는 서버 PossessedBy·클라 OnRep_PlayerState, 적은 BeginPlay나 PossessedBy에서 InitAbilityActorInfo(2) / 엔진 기본 ASC 사용, 클라 초기화 누락, 플레이어 ASC가 Character에 있음 중 하나(1) / 둘 이상 해당하거나 ASC 없음(0)
- [1.5] IAbilitySystemInterface: 적 Character와 플레이어 쪽(PlayerState 또는 플레이어 캐릭터 중 하나 이상)이 GetAbilitySystemComponent()로 ASC를 돌려줌(1.5) / 적이나 플레이어 한쪽만(0.5) / 없음(0)
- [2.5] UArenaAttributeSet: 속성 5개, Health·Stamina Clamp가 PreAttributeChange와 PostGameplayEffectExecute(또는 PreAttributeBaseChange) 양쪽에 있고, IncomingDamage를 읽어 0으로 되돌린 뒤 Health에 반영(2.5) / Clamp가 한 곳뿐이거나 IncomingDamage 미사용 중 하나(1.5) / 둘 다 해당하거나 Clamp 없음(1) / 속성 클래스 없음(0)
- [1.5] docs/gas-tags.md: 4계층과 태그별 한 줄 용도가 있고 고른 태그 3개가 실제 정의와 맞음(1.5) / 문서는 갖췄으나 실제 태그와 다른 것이 있음(1) / 계층 일부만이거나 용도 없음(0.5) / 없음(0)
- [1] ADR-0005: 템플릿 칸(맥락·선택지·결정과 이유·결과)이 있고 플레이어 PlayerState·적 Character의 이유가 적힘(1) / 칸 일부만(0.5) / 없음(0)

> 검토에서 고친 점: 기준3은 'PlayerState와 적'이 구현해야만 완료로 봤다. 그래서 플레이어 캐릭터에 IAbilitySystemInterface를 구현한 설계는 '한쪽만(0.5)'으로 깎일 수 있었다. 이 설계는 흔하고 W17 SendGameplayEventToActor(캐릭터)에 필요하다. 기준4 부분 '1~1.5', 기준5의 실제 태그 불일치, 기준2의 0점 조건, 플러그인이 .uproject에 없을 때의 판정도 정해져 있지 않았다. → 기준3은 '적과 플레이어 쪽(PlayerState나 캐릭터 중 하나 이상)'을 완료로 본다. 기준4는 2.5/1.5/1/0, 기준5는 1.5/1/0.5/0, 기준2는 '하나 해당(1) / 둘 이상(0)'으로 정했다. 플러그인이 .uproject에 없으면 사본의 Plugins 창에서 확인한다(UE 5.8 기본값은 확인 필요).

> 작성 메모: 문항 점수 1.69점(50×4÷118). 채점표 1점 = 0.169점. 진위: P3-42 구술에서 이 문항이 뽑혀 ASC 위치와 초기화 시점, IncomingDamage 처리를 설명하지 못하면 이 문항 점수의 50%만 인정한다. W16은 L2이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. Clamp 두 곳(PreAttributeChange·PostGameplayEffectExecute)은 W16 핵심 개념과 W16-07에 있는 범위라 요구한다. IAbilitySystemInterface는 커리큘럼이 구현 위치를 정하지 않으므로 PlayerState와 플레이어 캐릭터 중 어느 쪽에 구현했든 인정한다. 접근자 매크로는 AttributeSet.h 주석을 보고 직접 정의했든 엔진 제공 매크로든 인정한다. PlayerState 복제 빈도 조정과 Replication Mode는 권장이라 감점하지 않는다. GE·GA_Dash는 P3-28, GA_MeleeCombo·속성 델리게이트 UI는 P3-29, 매크로·Replication Mode·초기화 타이밍 설명은 1부에서 채점한다. 커뮤니티 GAS 문서 학습과 M4 회고는 이 문항 대상이 아니다. 코드는 대부분 현재 코드(exam-submit)에서 그대로 확인할 수 있고, 바뀐 이유가 궁금하면 feat/gas-setup PR diff를 본다.

### P3-28 (1.69점) — 목표: W16-11, W16-12, W16-13, W16-16, W16-27

**모범 답안**

여는 순서
1) GE 설정: PR feat/ga-dash(와 feat/gas-setup)의 캡처를 먼저 보고, 없으면 블록3 사본을 결함을 심기 전에 열어 GE 에셋을 본다. GE_Damage: Duration Policy Instant, Modifier 대상 IncomingDamage(또는 Health), Magnitude는 Set By Caller + 데이터 태그. GE_StaminaRegen: Infinite + Period + Stamina 증가. GE_Dash_Cost: Instant, Stamina 감소. GE_Dash_Cooldown: Has Duration + Cooldown.* 태그 부여(UE 5.3 이후는 GE 컴포넌트로 태그를 준다. 메뉴 이름 예: Grant Tags to Target Actor(확인 필요)). C++로 만든 GE면 생성자 코드로 본다.
2) 코드 검색: SetSetByCallerMagnitude 또는 AssignTagSetByCallerMagnitude. W17 GA_MeleeCombo 안에 있어도 인정. GE_StaminaRegen은 서버에서 ApplyGameplayEffectToSelf(또는 시작 GE 목록)로 적용하는지. 회복은 GIF의 HUD 스태미나 바나 Shipping zip에서 대시 뒤 다시 차오르는지로 본다. 최대치를 넘는지(Clamp)는 P3-27에서만 본다.
3) GA_Dash: Cost Gameplay Effect Class·Cooldown Gameplay Effect Class에 두 GE가 지정됐는지(C++ 생성자 또는 BP 클래스 디폴트). ActivateAbility에서 CommitAbility가 실패하면 EndAbility(취소), 성공하면 이동(LaunchCharacter 등) 뒤 EndAbility. Activation Blocked Tags에 공격 중 태그(예: State.Attacking).
4) 공격 중 태그를 실제로 붙이는 곳(W16 공격 코드의 AddLooseGameplayTag, W17 GA_MeleeCombo의 Activation Owned Tags 등)이 있어야 차단이 의미가 있다. Shipping zip에서 공격 도중 대시 키를 눌러 막히는지 보면 더 확실하다(선택).
5) 2인 검증: PR 테스트 칸 체크와, 2인 PIE GIF에서 클라 창의 대시·스태미나 감소·쿨다운 중 재사용 불가. 호스트 창도 보이면 좋다(필수 아님). 반응 지연은 허용.
참고(감점 아님): 공격 중 태그를 서버에서만 루즈 태그로 붙이면 클라 예측 발동이 서버에서 거부돼 대시가 잠깐 되돌아갈 수 있다. 꼬리 질문 소재로만 쓴다.
AI 활용 칸: W16은 L2. AI 사용은 감점하지 않는다. 칸이 비었거나 코드와 안 맞으면 P3-42 진위 확인 후보로 적어 둔다.
만점 예: GE 4종 설정, SetByCaller 코드, GA_Dash의 CommitAbility·차단 태그·태그를 붙이는 곳, 2인 PIE GIF가 모두 있다.
부분 예: GE_Damage가 고정 Magnitude → 기준1 1점. 쿨다운 GE만 연결되고 비용 없음 → 기준3 1점. 차단 태그는 넣었지만 공격 중 태그를 붙이는 곳이 없음 → 기준4 1점. 2인 GIF에 호스트 대시만 보임 → 기준5 1.5점. 싱글 PIE GIF만 → 기준5 1점.
구술 질문(진위 확인)
- 'CommitAbility는 무엇을 하고, 실패하면 GA_Dash는 어떻게 끝나나요?'(비용·쿨다운을 실제로 적용하는 확정 단계, 실패하면 EndAbility로 취소)
- 'GE_Damage 같은 Instant GE와 GE_StaminaRegen 같은 Infinite·Periodic GE는 속성 값을 어떻게 다르게 바꾸나요?'(Instant는 Base를 영구 변경, Periodic은 주기마다 실행되어 Base 변경, 주기 없는 Duration·Infinite Modifier는 적용 중에만 Current 변경)

**채점표 (10점)**

- [2] GE_Damage: Instant + SetByCaller 설정(캡처·C++·사본)과 SetByCaller로 값을 넣는 코드(2) / 고정 Magnitude이거나 값을 넣는 코드 없음(1) / GE_Damage 없음(0)
- [1.5] GE_StaminaRegen: Infinite·Period 설정, 시작할 때 적용하는 코드, GIF·HUD나 Shipping zip에서 스태미나가 다시 차오름(1.5) / 셋 중 하나를 확인할 수 없음(1) / 없음(0)
- [2] Cost·Cooldown: GE_Dash_Cost(Stamina 감소)와 GE_Dash_Cooldown(Has Duration + Cooldown 태그)이 GA_Dash에 연결되고 ActivateAbility에서 CommitAbility 호출(2) / 비용이나 쿨다운 하나만 연결(1) / 없음(0)
- [2] 공격 중 차단: GA_Dash 발동 차단 태그에 공격 중 태그가 있고, 공격할 때 그 태그를 붙이는 코드·GE·GA 설정이 있음(2) / 차단 태그만 있고 붙이는 곳 없음(1) / 없음(0)
- [2.5] 2인 PIE 검증: PR 테스트 칸 '2인 Listen Server + 지연 200ms' 체크, 2인 PIE GIF(PR 또는 W16 Devlog)에서 클라 쪽 플레이어의 대시 → 스태미나 감소 → 쿨다운 중 재사용 불가가 보임(2.5) / 2인 GIF가 호스트 대시만 보이거나 비용·쿨다운 중 하나가 안 보임(1.5) / 싱글 PIE GIF만(1) / 없음(0)

> 검토에서 고친 점: 기준2의 '회복이 최대치에서 멈춤'은 P3-27의 Clamp 기준과 겹쳐 두 번 감점된다. 스태미나 바로는 초과를 관찰하기도 어렵다. 기준5는 두 플레이어 모두의 GIF와 Devlog까지 요구해 커리큘럼 DoD('2인 PIE에서 비용·쿨다운과 함께 동작')보다 높았다. GE 설정 캡처는 커리큘럼 산출물이 아닌데, 캡처가 없으면 부분 점수를 줄 수 있었다. → 기준2는 설정·적용 코드·회복이 보이는지만 보고, Clamp는 P3-27에서만 채점한다. 기준5는 2인 PIE에서 클라 쪽 동작과 PR 테스트 체크가 보이면 완료(2.5)다. 호스트만 보이면 1.5, 싱글이면 1이고, Devlog는 GIF를 둘 수 있는 다른 위치로만 쓴다. 캡처가 없으면 사본에서 확인하고, 사본이 빌드되지 않을 때만 부분 점수를 준다.

> 작성 메모: 문항 점수 1.69점(50×4÷118). 채점표 1점 = 0.169점. 진위: P3-42 구술에서 이 문항이 뽑혀 CommitAbility와 GE 종류의 차이를 설명하지 못하면 이 문항 점수의 50%만 인정한다. W16은 L2이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. GE·GA가 BP 에셋이면 GitHub에서 설정이 안 보인다. 커리큘럼은 설정 캡처를 요구하지 않으므로, 캡처가 없으면 채점자가 블록3 사본을 결함을 심기 전에 열어 확인하고 감점하지 않는다(저장하지 않고 닫은 뒤 git status 확인). 사본이 빌드되지 않아 확인할 수 없을 때만 해당 기준을 부분 점수로 본다. 수치(대시 거리, 비용, 쿨다운 시간)는 학생마다 달라도 된다. UE 5.3 이후 GE의 부여 태그는 GE 컴포넌트로 설정하며 메뉴 이름은 확인이 필요하다. 스태미나가 최대치에서 멈추는지(Clamp)는 P3-27에서만 채점해 중복 감점하지 않는다. W16 DoD는 '대시가 2인 PIE에서 비용·쿨다운과 함께 동작'이므로 2인 PIE에서 클라이언트 쪽 동작이 보이면 완료로 보고, 두 플레이어 모두의 GIF나 Devlog 기록을 따로 요구하지 않는다. GA_MeleeCombo는 P3-29, CommitAbility·GE 종류 설명(W16-09·14·15)은 1부에서 채점한다.

### P3-29 (1.69점) — 목표: W17-03, W17-04, W17-05, W17-06, W17-07, W17-09, W17-10, W17-12

**모범 답안**

기준 시점은 exam-submit 태그다. 아래 순서로 연다.
1) PR: 목록에서 `is:pr head:refactor/combat-to-gas`로 찾는다(없으면 제목으로). 본문, 영상, AI 활용 칸, Files changed를 본다.
2) GA(예: Source/ActionArena/AbilitySystem/Abilities/GA_MeleeCombo.cpp, BP면 PR 캡처)
- 생성자나 클래스 기본값: NetExecutionPolicy = EGameplayAbilityNetExecutionPolicy::LocalPredicted.
- ActivateAbility: CommitAbility → UAbilityTask_PlayMontageAndWait::CreatePlayMontageAndWaitProxy → OnCompleted·OnBlendOut·OnInterrupted를 EndAbility로 연결(OnCancelled도 연결하면 좋다) → ReadyForActivation.
- UAbilityTask_WaitGameplayEvent::WaitGameplayEvent(this, 타격 태그) → EventReceived 핸들러.
3) AnimNotify(C++·BP 모두 인정, W7 HitWindow NotifyState 시작에서 보내도 인정): UAbilitySystemBlueprintLibrary::SendGameplayEventToActor(MeshComp->GetOwner(), 태그, Payload). 캐릭터가 IAbilitySystemInterface로 ASC를 돌려줘야 이벤트가 도착한다.
4) 핸들러: UCombatComponent의 기존 판정 함수(Sweep·TSet)를 호출한다. MakeOutgoingGameplayEffectSpec(GE_Damage) → SetSetByCallerMagnitude(SetByCaller 태그, 값) → 대상 ASC에 적용. 값은 이벤트 크기든 무기 데이터든 인정. 서버 적용 근거: HasAuthority 분기, 또는 PR·Devlog·TIL·주석의 설명, 또는 2인 테스트에서 한 번만 깎인 기록.
5) State.Dead: Clone에서 'State.Dead'와 네이티브 태그 변수 이름(예: TAG_State_Dead)을 전체 검색(VS Ctrl+Shift+F 또는 git grep). 붙이는 곳(PostGameplayEffectExecute나 사망 처리, GE 부여 권장)과 쓰는 곳(ActivationBlockedTags, 입력 처리, AI 정지, 사망 연출)을 본다. 쓰는 곳은 1곳이면 충분하다.
6) HUD: PR Files changed에서 UArenaHUDWidget 표시 함수 선언과 WBP 에셋이 바뀌지 않았는지 본다. 구독은 ASC->GetGameplayAttributeValueChangeDelegate(...GetHealthAttribute()).AddUObject(...) → FOnAttributeChangeData.NewValue → 기존 표시 함수. W9에서 위젯이 HealthComponent를 직접 구독했다면 구독 대상만 바꾼 수정은 '유지'로 본다.
7) 영상: README 핵심 섹션(또는 PR)의 지연 200ms 비교 영상에서 W17 쪽은 클라가 누르자마자 몽타주가 시작되는지.
- 만점 예: 1~7이 모두 확인된다.
- 부분 예: OnCompleted만 연결(기준1 0.5). 이벤트 없이 노티파이가 판정 함수를 직접 부름(기준2 1). Sweep을 GA 안에 새로 복사(기준3 1), 복사 + 고정 데미지(기준3 0.5). State.Dead를 붙이기만 하고 쓰는 곳 없음(기준4 0.5). LocalPredicted 설정만 있고 비교 영상 없음(기준5 0.5). HUD 위젯 표시 함수·구조를 새로 짬(기준6 1), Tick·Binding으로 속성을 읽음(기준6 0).
- 구술 질문: ① '노티파이는 클라와 서버 양쪽에서 올 수 있는데, 데미지가 두 번 들어가지 않게 어디서 막았나?' ② 'OnInterrupted에서 EndAbility를 부르지 않으면 무슨 일이 생기나?'

**채점표 (10점)**

- [1.5] GA_MeleeCombo의 PlayMontageAndWait와 완료·블렌드아웃·중단 델리게이트 → EndAbility(1.5) / 1~2개만 연결(0.5) / 없음(0)
- [2] AnimNotify가 SendGameplayEventToActor로 Event.Montage.Hit 전송, GA가 WaitGameplayEvent로 받아 판정 실행(2) / 한쪽만이거나 이벤트 없이 노티파이가 판정을 직접 호출(1) / 없음(0)
- [2] 핸들러가 W7 UCombatComponent 판정 함수를 다시 호출하고, GE_Damage 스펙에 SetByCaller로 값을 넣어 서버에서 대상에 적용(HasAuthority나 기록된 근거)(2) / 판정 복사, 고정 데미지, 서버 적용 근거 없음 중 하나(1) / 둘 이상(0.5) / 없음(0)
- [1.5] State.Dead를 붙이는 코드(ASC 권장)와 이 태그로 사망을 판단해 처리하는 곳 1곳 이상(1.5) / 붙이기만 하고 쓰는 곳 없음(0.5) / 없음(0)
- [1] LocalPredicted 설정과 지연 200ms 비교 영상에서 클라 입력 즉시 몽타주 시작(1) / 설정만 있고 영상 없음(0.5) / 없음(0)
- [2] HUD가 속성 변경 델리게이트로 갱신(HealthComponent 의존 제거)되고 PR diff에서 W9 위젯 표시 함수·WBP 유지(2) / 갱신은 되지만 위젯 표시 함수·구조를 새로 짬(1) / 없음이나 Tick·Binding으로 읽음(0)

> 검토에서 고친 점: 기준4가 State.Dead를 '쓰는 곳 2곳 이상' 요구. W17-07은 '판단·처리'만 요구해 커리큘럼보다 높다. → 부여 코드 + 판단·처리하는 곳 1곳 이상으로 낮춤. / 기준1이 취소 델리게이트까지 4개를 요구. W17-03은 완료·중단·블렌드아웃 3개. → 3개 연결을 만점으로, 취소는 권장으로 바꿈. / 기준3이 '서버 확인 없음'을 코드의 HasAuthority로만 판단. 다른 방식으로 서버 적용을 보장한 학생도 깎인다. 부분 점수도 2단계뿐. → HasAuthority, PR·Devlog·TIL·주석 설명, 2인 테스트 기록 중 하나를 근거로 인정. 결함 수에 따라 1/0.5로 나눔. / AnimNotify만 인정. W7 판정이 HitWindow NotifyState 기반이라, 재사용(W17-12)하면 NotifyState 시작에서 이벤트를 보내는 학생이 깎일 수 있다. → HitWindow NotifyState 시작에서 보내는 방식도 인정한다고 적음. / 만점 예에 'PR에 2인·200ms 테스트'를 넣어 P3-05(PR 규칙)와 겹친다. GA가 BP일 때 확인 방법이 없다. State.Dead 검색이 네이티브 태그 변수 이름을 놓친다. → PR 규칙은 P3-05로 넘김. BP면 PR 캡처나 블록3 사본으로 확인. TAG_State_Dead 같은 변수 이름도 검색.

> 작성 메모: 문항 점수 1.69점(50×4÷118). 채점표 1점 = 0.169점. 심사 약 15분. 기준 시점은 exam-submit 태그다. GitHub 웹이나 exam-submit의 깨끗한 Clone(블록3용 결함을 심기 전)에서 본다. 진위: P3-42 구술에서 이 문항이 뽑혀 몽타주 → 이벤트 → 판정 → GE 적용 흐름을 설명하지 못하면 이 문항 점수의 50%만 인정한다. 커리큘럼 이름(GA_MeleeCombo, UCombatComponent, UArenaHUDWidget, UArenaAttributeSet, Event.Montage.Hit)이 기준이고, 같은 역할이면 다른 이름도 인정한다. GA가 BP면 그래프 캡처를 PR에서 보고, 캡처가 없으면 블록3용 사본에서 에디터로 확인한다(선택). W7 HitWindow NotifyState 시작에서 이벤트를 보내 CombatComponent의 Sweep 창을 여는 방식도 W7 재사용으로 인정한다. 서버 적용은 HasAuthority 분기가 없어도, PR·Devlog·TIL·주석의 설명이나 2인 테스트에서 데미지가 한 번만 들어간 기록이 있으면 인정한다. State.Dead 루즈 태그 복제 API는 버전마다 달라 (확인 필요). GE로 붙이든 서버·클라 각각 붙이든 인정한다. 다른 문항과 나눔: 적 공격 GA(W17 과제4)는 P3-22, PR 본문 규칙(2인·200ms 테스트 칸)은 P3-05, 비교 영상의 README 배치와 ADR-0004는 P3-38, GameplayCue는 P3-30에서 채점하므로 여기서 깎지 않는다. W17은 L2~L3이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다. 코드는 복잡한데 PR·Devlog·TIL에 설명이 없으면 진위 확인 후보로 표시한다.

### P3-30 (0.85점) — 목표: W20-01, W20-02, W20-03, W20-04, W20-05, W20-09, W20-10, W17-08

**모범 답안**

기준 시점은 exam-submit 태그다. 아래 순서로 연다.
1) PR 두 개: `is:pr head:feat/gameplay-cues`(W17), `is:pr head:feat/game-feel`(W20). 이름이 다르면 제목으로 찾는다.
2) 히트스톱: 맞은(또는 때린) 액터의 CustomTimeDilation을 DataAsset 값으로 낮추고 SetTimer로 원래 값(1.0)에 복구한다. UGameplayStatics::SetGlobalTimeDilation으로 전체를 멈췄다면 부분(멀티에서 다른 플레이어·서버 흐름이 꼬인다).
3) 셰이크: UCameraShakeBase 자식(C++ 또는 BP)과 재생 호출. PlayerController->ClientStartCameraShake, PlayerCameraManager->StartCameraShake, Cue 안에서 재생 모두 인정. 플래시: 머티리얼 스칼라(또는 벡터) 파라미터를 SetScalarParameterValueOnMaterials나 동적 머티리얼 인스턴스로 켰다가 타이머로 끈다.
4) DataAsset: UPrimaryDataAsset(또는 UDataAsset) 자식에 히트스톱 배율·시간, 셰이크 크기, 플래시 시간 같은 필드가 있다. 연출 코드에서 숫자 리터럴을 찾아 강도 상수가 없는지 본다(복구 값 1.0, 0 같은 값은 상수여도 된다).
5) GameplayCue(W17 PR): W15의 피격 연출 Multicast RPC나 직접 호출(SpawnSystemAtLocation, PlaySoundAtLocation 등)이 지워지고, GE_Damage의 Gameplay Cues 설정이나 ExecuteGameplayCue·AddGameplayCue(GameplayCue.* 태그)로 바뀌었는지 diff로 본다. 사망 Cue는 W17에 새로 생겼어도 된다. Cue Notify에 Niagara 시스템이 지정됐는지는 PR 캡처나 영상으로 본다(캡처가 없으면 블록3용 사본에서 에디터로 확인, 선택).
6) 사운드: Sound Cue(예: Random 노드) 또는 MetaSound Source 에셋이 Cue(권장)나 연출 코드에 연결됐는지. W20 이후 Shipping zip이나 v1.0.0 시연 영상에서 타격·피격 소리를 듣는다.
7) 외부 에셋: .gitignore에 외부 에셋 폴더 줄이 있는지, Clone에서 `git log --all --oneline -- Content/ThirdParty`(폴더 이름은 학생 것)가 비어 있는지, README에 받는 방법(출처 링크)이 있는지, 라이선스 종류가 README·PR·Devlog·TIL 중 한 곳에 있는지. 참고: CC0는 표기 의무가 없고 CC-BY는 저작자 표기가 필요하다. Fab 등 재배포 금지 에셋 원본은 공개 저장소에 올리면 안 된다.
8) 실행 확인(있을 때): W20 이후 Shipping zip에서 적을 여러 번 때려 멈칫·흔들림·번쩍임·이펙트·소리를 보고, 적을 처치해 사망 Cue를 본다.
- 만점 예: 1~8(또는 zip 대신 영상)이 모두 확인된다.
- 부분 예: 히트스톱 뒤 복구 누락이나 전역 정지(기준1 0.5). 셰이크만 있고 플래시 없음(기준2 1). 셰이크만 DataAsset이고 나머지는 상수(기준3 0.5), 2개만 DataAsset(기준3 1). 피격 Cue만 있고 W15 Multicast 연출이 남음(기준4 1). 사운드 에셋은 있는데 zip·영상에서 안 들림(기준5 0.5). .gitignore는 했지만 README에 받는 방법이 없음(기준6 1). 이력에 외부 원본이 커밋된 적 있음(기준6 0).
- 구술 질문: ① '히트스톱을 전체 시간 정지가 아니라 액터별로 건 이유는?' ② '연출을 GameplayCue로 옮기면 게임 로직 코드에서 무엇이 빠지고, 데디케이티드 서버에서는 무엇이 달라지나?'

**채점표 (10점)**

- [1.5] 히트스톱: 액터의 CustomTimeDilation을 짧게 낮추고 타이머로 복구, 전역 정지 없음(1.5) / 복구 누락이나 SetGlobalTimeDilation 전역 정지(0.5) / 없음(0)
- [2] 카메라 셰이크(UCameraShakeBase 자식 + 재생 호출)와 피격 플래시(머티리얼 파라미터 켜기·끄기)가 코드에 있고 GIF·영상·실행에서 보임(2) / 하나만(1) / 없음(0)
- [1.5] 세 연출의 강도를 DataAsset 필드에서 읽고 연출 코드에 강도 숫자 없음(1.5) / 1~2개만 DataAsset(0.5~1) / 모두 하드코딩(0)
- [2] 피격·사망 연출이 GameplayCue로 재생(W17 PR에서 W15 Multicast 연출·직접 호출 제거)되고 Cue에 Niagara 연결(2) / Cue 1개뿐, 직접 호출이 남음, Niagara 연결 확인 불가 중 하나(1) / 없음(0)
- [1] Sound Cue/MetaSound 에셋이 Cue(또는 연출 코드)에 연결되고 W20 이후 Shipping zip이나 시연 영상에서 타격·피격 소리가 들림(1) / 에셋만 있음(0.5) / 없음(0)
- [2] 외부 에셋: 폴더 .gitignore, 커밋 이력에 원본 없음, README에 받는 방법(출처), 라이선스 종류 기록(2) / 하나 빠짐(1) / 둘 이상 빠짐(0.5) / 원본이 이력에 있음(0)

> 검토에서 고친 점: 셰이크에 'IsLocallyControlled 확인 필수·공격한 로컬 플레이어만'을 요구. 커리큘럼에 없는 요구다. → ClientStartCameraShake, StartCameraShake, Cue 안에서 재생 등 재생 방법을 자유로 함. / PR에 '강도 값을 바꿔 찍은 GIF'를 요구. 커리큘럼에 없는 산출물이다. → 일반 연출 GIF·mp4로 바꿈. 값 비교는 있으면 좋은 것으로만 둠. / '최신 릴리즈 Shipping zip'에서 연출·소리를 확인하게 함. 커리큘럼은 zip 첨부를 W13(v0.3.0)에서만 요구해, W20 이후 zip이 없을 수 있다. → W20 이후 zip이 없으면 PR 영상과 v1.0.0 시연 영상(W22)으로 판단. evidence_weeks에 W22 추가. / README에 '출처·라이선스'를 요구. 커리큘럼은 README에 '받는 방법'만, 라이선스는 '확인'만 요구한다. 기준6 부분 점수도 거칠다. → README에는 받는 방법(출처). 라이선스 종류는 README·PR·Devlog·TIL 중 한 곳. 하나 빠짐 1, 둘 이상 0.5, 원본 커밋 0. / W17 PR에서 'C++ 직접 호출 제거'만 본다. 실제로 W15에 있던 것은 피격 연출 Unreliable Multicast다. 사망 연출은 W17 전에 없었다. → W15 Multicast 연출·직접 호출 제거로 바꿈. 사망 Cue는 새로 생겨도 인정. GIF에는 소리가 없으므로 사운드는 zip·영상으로 확인.

> 작성 메모: 문항 점수 0.85점(50×2÷118). 채점표 1점 = 0.085점. 심사 약 15분. 기준 시점은 exam-submit 태그다. 진위: P3-42 구술에서 이 문항이 뽑혀 히트스톱·GameplayCue 흐름이나 DataAsset 구조를 설명하지 못하면 이 문항 점수의 50%만 인정한다. 외부 에셋은 .gitignore 대상이라 Clone에서는 Niagara·사운드 참조가 비어 보인다. 정상이며 W20-10의 증거다. 실제 동작은 PR GIF·mp4, W20 이후에 만든 Shipping zip(P3-39에서 내려받은 것), v1.0.0 시연 영상(W22) 중 있는 것으로 본다. 커리큘럼은 zip 첨부를 W13(v0.3.0)에서만 요구하므로, 최신 zip이 W20 이전 빌드뿐이면 감점하지 말고 영상으로 판단한다. 소리는 GIF에 없으므로 zip이나 시연 영상으로 듣는다. GameplayCue Notify 종류(Static·Burst·Actor), Sound Cue/MetaSound, 셰이크 재생 방법은 자유다. DataAsset 클래스·Cue 태그 이름은 학생마다 다르니 역할로 본다. 콤보 윈도우 튜닝은 P3-16, UI 애니메이션은 P3-15, 플레이테스트는 P3-35에서 채점한다. W17·W20은 L2~L3이므로 AI 사용은 감점하지 않고 PR의 AI 활용 칸이 정직한지만 본다.

### P3-35 (0.85점) — 목표: W13-23, W19-08, W19-09, W20-11, W20-14

**모범 답안**

- 여는 순서(약 12분): ① Issues에서 W13 주 전후에 만든 이슈와 우선순위 라벨 ② label:bug 이슈(열린·닫힌) 표본 5개(5개보다 적으면 전부) ③ 열린 bug 이슈와 README Known Issues 대조 ④ W20 Devlog·W20 주 이슈·반영 PR ⑤ 타격감 기록 ⑥ Shipping zip 실행(약 5분, P3-39 확인과 함께): 반영 PR 1건의 변화, Known Issues 1건(1인으로 재현되는 것)의 증상.
- ① 통과: 이슈 본문에 누가(테스터 구분) 무엇을 했고(관찰) 무엇을 말했는지(피드백)가 있고, 플레이테스트 이슈마다 우선순위 라벨이 있다. 피드백을 Devlog에만 적고 이슈로 안 올렸으면 1점.
- ② 좋은 버그 이슈: 증상 한 줄 제목, 환경(에디터/Shipping, 1인/2인), 재현 1·2·3단계, 심각도. 기대·실제 결과는 있으면 좋지만 필수 아님. 비율은 표본 수로 나눈다(예: 3개 중 3개 = 100%).
- ③ 열린 bug가 있어도 모두 Known Issues에 증상이 있으면 만점(우회 방법·이슈 링크는 있으면 더 좋음). zip에서 Known Issues 1건이 적힌 대로 보이면 정직하게 쓴 것이다. 5분 플레이 중 Known Issues에 없는 크래시·진행 불가 버그가 나오면 ③을 한 단계 낮춘다.
- ④ 피드백이 3명 이상에게서 나왔는지(테스터 구분) 보고, 반영 PR(예: feat/game-feel)의 본문에 어떤 피드백을 반영했는지와 GIF나 테스트 방법이 있는지 본다. Closes #N은 있으면 좋지만 필수 아님. zip에서 그 변화가 보이면 통과. zip이 실행되지 않으면 PR GIF로 판단한다.
- ⑤ 3명 중 2명 이상 '있다'면 만점. 미달이어도 실제 응답과 원인 가설·개선(히트스톱·카메라 셰이크 강도 조정 등)을 적었으면 1점.
- 만점 예: W13 이슈 6건(테스터 3명, 우선순위 라벨), bug 표본 5/5에 재현 단계, 열린 bug 2건 모두 Known Issues, W20 Devlog에 테스터 3명 피드백과 반영 PR 2건, 타격감 3명 중 2명 '있다'. 부분 예: 재현 단계 없이 '가끔 멈춤'만 적은 bug가 많음(② 1점), Known Issues에 열린 bug 3건 중 1건만(③ 1점), 2차 피드백은 Devlog에 있으나 반영 PR이 없음(④ 1점).
- 구술 질문(의심될 때): '이 피드백(채점자가 고른 1건)에 그 우선순위를 붙인 기준은?'(심각도·빈도·고치는 비용, 진행 불가는 가장 높게) / '2차 플레이테스트 뒤 무엇을 바꿨고, 타격감 응답은 어땠나?'

**채점표 (10점)**

- [2] ① W13 테스터 3명의 관찰·피드백 이슈와 우선순위 라벨(2) / 3명 미만, 라벨 누락, Devlog에만 기록 중 하나(1) / 기록 없음(0)
- [2] ② bug 이슈 표본 5개(5개보다 적으면 전부)의 심각도와 번호 붙은 재현 단계(80% 이상 2 / 40~79% 1 / 40% 미만이거나 bug 이슈 없음 0)
- [2] ③ 열린 bug 이슈 0개, 또는 열린 bug가 모두 README Known Issues에 증상과 함께 있음(2) / 일부만 있음(1) / Known Issues 없이 방치(0). zip에서 Known Issues에 없는 크래시·진행 불가 버그가 나오면 한 단계 낮춤
- [2] ④ W20 2차 플레이테스트 3명 이상의 피드백 기록과 그것을 반영한 PR, zip이나 GIF로 변화 확인(2) / 피드백 기록만 있거나 3명 미만, 또는 반영을 확인할 수 없음(1) / 없음(0)
- [2] ⑤ 타격감 응답 3명 기록(Devlog·회고·PR·이슈 중 한 곳), 2명 이상 '있다'(2) / 미달이지만 원인·개선 기록(1) / 기록 없음(0)

> 검토에서 고친 점: ③이 Known Issues에 '이슈 링크'까지 요구한다. W19 과제는 'README의 Known Issues로 문서화'뿐이라 커리큘럼보다 높은 요구다. → 증상 기록만 있으면 만점이고, 이슈 링크와 우회 방법은 가산 요소로 바꿨다. 대신 zip에서 Known Issues에 없는 크래시를 발견하면 한 단계 낮추는 관찰 기준을 넣었다. / ④가 W20 2차 피드백의 '이슈'와 'Closes #N으로 닫은 PR'을 요구한다. W20 과제는 '플레이테스트 2차(3명+) → 피드백 반영'뿐이다. → 피드백 기록은 이슈, Devlog, PR 본문 중 한 곳이면 되고 반영 PR이 있으면 된다. Closes #N은 필수가 아니다. / ⑤ 타격감 기록 위치를 Devlog와 M5 회고로 한정한다. 커리큘럼(W20 DoD)은 위치를 정하지 않았다. → Devlog, M5 회고, 반영 PR, 이슈 중 한 곳이면 인정했다. / ② bug 이슈가 5개보다 적으면 '4개 이상' 기준을 판정할 수 없다. ①의 기준 문구에는 W13-23의 '관찰 → 피드백' 순서가 빠져 있다. → ②를 비율 기준(80% 이상 2점, 40~79% 1점, 5개 미만이면 전부)으로 바꾸고, ①의 기준 문구에 '관찰·피드백'을 넣었다.

> 작성 메모: 배점 50×2÷118 ≈ 0.85점. 심사 약 12분(Shipping zip 실행 5분은 P3-39 확인 때 함께). 테스터 실명은 필요 없다(A·B·C로 충분). 우선순위·심각도 라벨 이름은 커리큘럼이 정하지 않았으므로 아무 이름이나 인정(priority:high, P1, S2 등). W19는 Known Issues 문서화만 요구하므로 이슈 링크는 가산 요소일 뿐 필수가 아니다. W20 과제는 '피드백 반영'만 정하므로 2차 피드백은 이슈·Devlog·PR 본문 어디에 적어도 되고, Closes #N도 필수가 아니다. 타격감 응답의 기록 위치도 커리큘럼이 정하지 않아 W20 Devlog·M5 회고·반영 PR·이슈 중 한 곳이면 된다. 플레이테스트 이슈는 W13·W20 주 날짜 전후로 만든 것을 본다. 이슈는 태그에 묶이지 않으므로 제출일 뒤 생성·수정은 보지 않는다. P3-42 진위 확인에 뽑히면 구술 질문을 쓰고, 설명하지 못하면 이 문항 점수의 50%만 준다.

### P3-37 (0.85점) — 목표: W05-27, W18-21

**모범 답안**

기준 시점은 exam-submit 태그다. 아래 순서로 연다.
1) docs/adr/ADR-0001-interaction-detection.md: 상태·날짜·맥락·선택지 표·결정과 이유·결과 칸이 있는지.
2) 선택지 표(내용 예, 문장은 학생 것): Tick(매 프레임 검사, 반응은 가장 빠르지만 비용이 크고 대부분 낭비), 타이머(예: 0.1초, 싸고 체감 지연이 작음), Overlap(이벤트 기반이라 싸지만 '바라보는 대상'은 따로 트레이스가 필요하고 콜리전 설정에 의존).
3) 결정과 코드 대조: UInteractionComponent(.cpp, 이름은 학생 것)의 SetTimer 주기, SphereTrace, Tick 꺼짐(PrimaryComponentTick.bCanEverTick = false)이 ADR의 결정과 같은지. 이유에 이 프로젝트의 조건이 1개 이상 있는지(예: 포커스 대상은 1개, 0.1초 지연은 체감 안 됨, 대상 수가 적음). '결과'에 다시 볼 조건이 1개 이상 있는지(예: 대상이 수백 개, 2인에서 감지 위치, 반응 지연 불만). W15 이후 구현이 바뀌었어도 ADR 상태·결과에 적혀 있으면 맞는 것으로 본다.
4) 파일 History: 첫 커밋이 W05 무렵인지 본다. 시험 직전 첫 커밋이면 진위 확인 후보로 표시한다.
5) docs/perf/02-performance-report.md(또는 perf/02-…): 측정 환경 — 기기(CPU·GPU·RAM), 설정(해상도·품질·맵·적 수 등), 반복 횟수. 노트북 전원 연결·최고 성능 모드는 적었으면 좋다(감점 없음). 스크린샷 — stat unit·Insights 등의 전/후. 표 — 개선 3건, 같은 조건 여러 번, 중간값 등 대표값. 배운 점.
6) 표의 개선 1건 이상을 perf/ 브랜치 PR 본문과 대조해 수치가 같은지 본다(다르면 구술 후보).
- 만점 예: ADR이 '0.1초 타이머 SphereTrace를 고른 이유'를 이 프로젝트 조건으로 적고 코드와 맞다. 리포트가 개선 3건을 같은 조건 3회 측정 중간값으로 보여 주고, 배운 점이 그 수치를 든다.
- 부분 예: 템플릿 칸 1~2개 빠짐(기준1 0.5). 선택지 2개만 비교(기준2 0.5). 결정이 일반론뿐(기준3 1). 환경에 기기만 있음(기준4 0.5). 후 스크린샷만 있음(기준5 0.5). 개선 2건이거나 1회 값(기준6 1), 1건(기준6 0.5). 배운 점이 '측정이 중요하다' 같은 일반론뿐(기준7 0.5).
- 구술 질문: ① 'Overlap을 고르지 않은 이유를 이 프로젝트 조건으로 말해 보라.' ② '개선 3건 중 하나를 골라, 어떤 조건에서 몇 번 쟀고 왜 중간값을 썼는지 말해 보라.'

**채점표 (10점)**

- [1.5] ADR-0001에 템플릿 칸(상태·날짜·맥락·선택지 표·결정과 이유·결과)이 모두 있음(1.5) / 1~2칸 빠짐(0.5) / 없음(0)
- [1.5] 선택지 표에 Tick·타이머·Overlap 3개의 장점·단점(1.5) / 2개만이거나 장단점 한쪽만(0.5) / 없음(0)
- [2] 결정이 실제 UInteractionComponent 코드(타이머 주기·트레이스·Tick 꺼짐)와 같고, 이유에 이 프로젝트 조건 1개 이상, 결과에 다시 볼 조건 1개 이상(2) / 일반론만, 다시 볼 조건 없음, 코드와 다름 중 하나(1) / 둘 이상이거나 없음(0)
- [1.5] 성능 리포트 측정 환경: 기기·설정·반복 횟수가 모두 있음(1.5) / 1~2개만(0.5) / 없음(0)
- [1] 측정 스크린샷(stat unit·Insights 등)이 전/후 모두 있음(1) / 한쪽만(0.5) / 없음(0)
- [1.5] 개선 3건 각각 같은 조건에서 여러 번 잰 전/후 표(중간값 등 대표값)(1.5) / 2건이거나 1회 값(1) / 1건(0.5) / 없음(0)
- [1] 배운 점이 이 리포트의 항목·수치를 들어 적혀 있음(1) / 일반론만(0.5) / 없음(0)

> 검토에서 고친 점: 측정 환경에 해상도·Scalability·전원 모드를 필수로 둠. 커리큘럼은 '기기·설정·반복 횟수'이고 전원 모드는 노트북용 주의사항이다. → 기기·설정·반복 횟수 3가지로. 전원 모드는 감점 없는 권장. / '배운 점을 내 말로', '내 프로젝트 조건'이 주관적. '전후 스크린샷'은 0/1뿐. 개선 건수 부분 점수가 모호하다. → 배운 점은 리포트 항목·수치 언급 여부로. ADR 이유는 프로젝트 조건 1개·다시 볼 조건 1개로. 스크린샷 한쪽만 0.5. 개선 2건 1, 1건 0.5. / 문제 6번 '커밋 날짜가 증거'가 감점처럼 읽혀, notes(감점 없이 진위 후보)와 맞지 않는다. W15 이후 구현이 바뀐 경우의 처리도 없다. → 늦게 쓴 문서는 감점 없이 구술 확인 대상이라고 적음. 구현이 바뀌었으면 ADR 상태·결과에 적힌 경우 인정.

> 작성 메모: 문항 점수 0.85점(50×2÷118). 채점표 1점 = 0.085점. 심사 약 10분. 기준 시점은 exam-submit 태그다. 진위: P3-42 구술에서 이 문항이 뽑혀 ADR의 결정 이유나 성능 측정 방법을 설명하지 못하면 이 문항 점수의 50%만 인정한다. 블록3 P3-32에서 새로 잰 수치는 이 문항에 넣지 않는다. 트레이스 스코프·스트레스 맵 같은 W18 구현도 P3-32에서 본다. 커리큘럼 원칙은 '형식은 도구가, 내용은 내 말로'다. 그래서 이 프로젝트의 조건·수치 없이 일반론만 있으면 기준3·7에서 부분 점수를 준다. 파일 첫 커밋이 해당 주차가 아니라 시험 직전이면 감점하지 말고 진위 확인 후보로 표시한다. AI 사용 자체는 감점하지 않는다(W05 L1, W18 L2~L3).

### P3-38 (1.27점) — 목표: W13-25, W13-28, W22-02, W22-04, W22-09, C-57, W04-30, C-52, C-53, W00-26, W22-06, W17-16

**모범 답안**

기준 시점은 exam-submit 태그다(README 링크도 그 기준으로 누른다). 아래 순서로 연다.
1) 30초 판정을 가장 먼저 한다: 저장소 첫 화면(1920×1080 브라우저, 스크롤 없이)을 30초 보고 '무슨 게임·무엇을 했나·얼마나 깊게'를 말한다. 판단 근거: ① 무슨 게임 = 장르·인원(예: 2인 협동 근접 액션 웨이브 서바이벌) ② 무엇을 했나 = 핵심 기술 이름(예: 콤보 전투, 2인 협동, GAS) ③ 얼마나 깊게 = 수치나 기간(예: 6개월, 지연 200ms, ms 개선). 말한 개수로 점수를 준다.
2) README 구조(부록): 대표 GIF, 핵심 구현 표, 아키텍처 다이어그램(GitHub에서 Mermaid가 그림으로 보이는지, 그림 파일도 인정), Top 3, 성능 개선 표, 같은 기능의 진화, 개발 환경·빌드, 개발 기록 인덱스(Known Issues, 열린 버그가 없으면 '없음'도 인정). 핵심 구현 표는 행마다 코드·문서 링크를 눌러 열리는지 본다. W13 README 1차는 브랜치 메뉴에서 v0.3.0 태그로 바꿔 보면 확인할 수 있다(참고).
3) Top 3: 문제 → 해결 → 결과 수치 → TS 링크. 수치 예: '데미지 2회 적용 → 0건', 'BT 서비스 −1.2ms'.
4) 반응성 비교: README 핵심 섹션에 지연 200ms RPC 방식과 GAS 예측 영상(나란히 또는 두 칸). docs/adr/ADR-0004 History에 W15 작성 → W17 '결과' 갱신 커밋이 있는지.
5) 증거: docs/troubleshooting TS 3건 이상, docs/adr ADR 3건 이상이 README에서 링크되는지. README 증거 표(이름은 달라도 되고, 기록 인덱스 안의 달별 링크도 인정)에 달마다 대표 기록 3개. README History에 매달 갱신 커밋이 있으면 확실하다. Issues → Milestones → Closed에 M2~M5(M1은 P3-39에서 본다, M6은 열려 있어도 된다).
6) 영상·GIF: PR 목록에서 mp4가 붙은 PR 3개 이상(5~15초, 기능 하나, 판정 장면은 디버그 드로잉, 예: W07 판정 PR). README·Devlog GIF는 새 탭으로 열어 너비 800 정도인지(600~1000이면 인정).
7) 프로필: 계정 페이지의 사진·한 줄 소개, 프로필 README, 고정 저장소 UE5-ActionArena·unreal-study-log, 게임 저장소 About 한 줄·토픽, 학습 로그 README 표시.
- 만점 예: 30초 판정에서 3가지를 말하고, 표의 링크가 모두 열리고, Top 3에 수치·TS 링크, 비교 영상과 ADR-0004 갱신, M2~M5 닫힘, PR mp4와 README GIF, 프로필 정리가 모두 있다.
- 부분 예: 표 링크 일부 깨짐이나 칸 1~2개 빠짐(기준1 1). Top 3에 수치가 없음(기준2 0.5). 비교 영상은 있는데 ADR-0004 결과 칸이 W15 그대로(기준3 0.5). 마일스톤 일부가 열린 채 남음(기준4 1), 증거 표도 없고 마일스톤도 열림(기준4 0.5). GIF만 있고 PR mp4가 없음(기준5 0.5). 고정 저장소 없음(기준6 0.5). 30초에 '무슨 게임'만 말함(기준7 0.5).
- 구술 질문: ① 'Top 3 중 하나를 골라 그 수치를 어떻게 쟀고 어느 TS에 있는지 말해 보라.' ② '아키텍처 다이어그램에서 공격 1회가 데미지와 UI까지 가는 흐름을 짚어 보라.'

**채점표 (10점)**

- [2] README 부록 구조: 대표 GIF, 핵심 구현 표(행마다 코드·문서 링크가 열림), 아키텍처 다이어그램(Mermaid나 그림), 성능 개선 표, 같은 기능의 진화, 개발 환경·빌드, 개발 기록 인덱스(Known Issues)(2) / 링크 일부 깨짐이나 칸 1~2개 빠짐(1) / 3칸 이상 빠짐이나 없음(0)
- [1.5] 기술적 도전 Top 3가 문제 → 해결 → 결과 수치 → TS 링크(1.5) / 수치나 TS 링크가 빠짐(0.5) / 없음(0)
- [1.5] README 핵심 섹션에 지연 200ms W15(RPC) vs W17(GAS 예측) 비교 영상, ADR-0004 결과 칸이 W17에 갱신됨(1.5) / 하나만(0.5) / 없음(0)
- [1.5] TS 3건+·ADR 3건+ 링크, README 증거 표(또는 기록 인덱스)에 달마다 대표 기록 3개, 끝난 마일스톤 M2~M5 닫힘(1.5) / 일부만(0.5~1) / 없음(0)
- [1.5] PR·이슈에 캡처 도구 mp4 3건 이상(5~15초, 기능 하나, 판정 장면은 디버그 드로잉)과 README·Devlog에 GIF(너비 800 정도)(1.5) / 한 종류만이거나 조건 일부 미달(0.5~1) / 없음(0)
- [1] GitHub 프로필 사진·한 줄 소개·프로필 README, 고정 저장소 2개, 게임 저장소 About·토픽, 학습 로그 README 표시(1) / 일부(0.5) / 없음(0)
- [1] README 첫 화면 30초 판정: 무슨 게임·무엇을 했나·얼마나 깊게 중 2가지 이상(1) / 1가지(0.5) / 없음(0)

> 검토에서 고친 점: Mermaid만 인정. W13 과제는 '아키텍처 다이어그램'이다. 30초 판정이 주관적이고 0/1뿐이다. → 그림 파일도 인정. 30초 판정은 장르·인원 / 기술 이름 / 수치·기간의 3가지 근거로 세고, 1가지면 0.5. / W22 최종 README에서 증거 표가 기록 인덱스에 합쳐질 수 있다. mp4·GIF 기준은 부분 단계와 GIF 너비 허용 범위가 없다. → 기록 인덱스 안의 달별 링크도 인정. 기준5 부분 0.5~1, GIF 너비는 600~1000이면 인정. LocalPredicted 동작은 P3-29로 넘김.

> 작성 메모: 문항 점수 1.27점(50×3÷118). 채점표 1점 = 0.127점. 심사 약 20분. 진위: P3-42 구술에서 이 문항이 뽑혀 Top 3의 수치 근거나 아키텍처 흐름을 설명하지 못하면 이 문항 점수의 50%만 인정한다. 30초 판정은 다른 문서를 보기 전에 한다. 비개발 직군 보조가 있으면 보조가, 없으면 채점자가 README 첫 화면만 본다. 이 문항은 기록이 모여 있고 링크로 이어지는지를 본다. ADR-0001·성능 리포트 내용은 P3-37, 릴리즈와 M1 마일스톤은 P3-39, 타격감 연출은 P3-30, 비교 영상 속 LocalPredicted 동작은 P3-29에서 채점하므로 여기서 다시 깎지 않는다. 아키텍처 다이어그램은 부록이 Mermaid를 권하지만 W13 과제는 '아키텍처 다이어그램'이므로 그림 파일도 인정한다. 프로필·About은 제출 뒤에도 바뀔 수 있으니 심사한 날 화면을 캡처해 둔다. 프로필 README는 계정 이름과 같은 이름의 공개 저장소에 README.md를 두면 프로필에 보인다. W22는 L3이다. AI로 문장을 다듬은 것은 감점하지 않는다.

### P3-39 (0.85점) — 목표: W04-29, W08-26, W13-21, W13-24, W17-17, W20-12, W24-04, C-51

**모범 답안**

아래 순서로 연다.
1) 저장소 → Releases: v0.1.0·v0.2.0·v0.3.0·v0.4.0·v0.5.0·v1.0.0이 있는지. 릴리즈마다 태그·제목·노트·첨부를 본다.
2) Target main: Clone에서 `git branch -r --contains v0.1.0`에 origin/main이 나오는지 본다(다른 태그도 1~2개).
3) v0.1.0: 변경 내역과 20초 GIF. Issues → Milestones → Closed에 M1이 있고 닫힌 날짜가 v0.1.0 무렵인지.
4) v0.2.0: 디버그 판정을 켠 45초 영상(본문 영상·첨부·YouTube 링크 모두 인정). v0.3.0: '싱글플레이 MVP' 90초 영상. 길이는 ±15초면 인정.
5) v0.4.0: '2인 협동' 태그·릴리즈 노트. v0.5.0: RC 표시(제목이나 pre-release 체크)와 개선 전/후 비교 GIF(같은 동작의 전과 후).
6) CHANGELOG.md: `is:pr head:docs/changelog`가 Squash merge됐는지, 버전별 섹션(v0.1.0~v1.0.0)과 변경 내역이 있는지.
7) v1.0.0: 이번 버전에서 해낸 것과 2~3분 시연 영상 링크. CHANGELOG 링크는 있으면 좋다(감점 없음).
8) Shipping zip: 가장 최근 zip(v1.0.0 권장, 없으면 v0.3.0 이후 것)을 내려받아 짧은 영문 경로 폴더에 풀고 exe를 실행한다 → 메인 메뉴 → 게임 시작(2인 메뉴면 호스트) → 혼자 5분 플레이. 크래시·멈춤이 없으면 완료. 패키징 폴더 전체가 있어야 한다(루트 exe만 있으면 실행되지 않는다).
- 만점 예: 릴리즈 6개가 모두 있고 각 공개 자료가 붙어 있으며 zip이 바로 실행돼 5분 동안 문제없다.
- 부분 예: v0.1.0에 GIF가 없거나 M1이 열려 있음(기준1 0.5). 영상 대신 글만 있음(기준2·3 0.5). CHANGELOG를 main에 바로 커밋(기준4 1), 버전 구분 없음(기준4 0.5). v1.0.0에 영상 링크 없음(기준5 0.5). zip이 실행되지만 플레이 중 크래시(기준6 1.5). 폴더 일부가 빠져 실행 안 됨(기준6 1).
- 구술 질문: ① 'zip에 무엇을 넣었나? exe만 넣으면 왜 실행되지 않나?' ② '태그와 릴리즈는 어떻게 다르고, Target을 main으로 하는 이유는?'

**채점표 (10점)**

- [1.5] v0.1.0: 태그가 main 커밋, 릴리즈 노트와 20초 GIF, 마일스톤 M1 닫힘(1.5) / 1~2개 빠짐(0.5) / 릴리즈 없음(0)
- [1.5] v0.2.0 디버그 판정 45초 영상과 v0.3.0 '싱글플레이 MVP' 90초 플레이 영상(1.5) / 하나만 있거나 둘 다 영상 대신 글(0.5) / 없음(0)
- [1.5] v0.4.0 '2인 협동' 태그·릴리즈 노트와 v0.5.0(RC) 개선 전/후 비교 GIF(1.5) / 하나만(0.5) / 없음(0)
- [1.5] CHANGELOG.md가 docs/changelog 브랜치 PR로 merge되고 버전별(v0.1.0~v1.0.0) 변경 내역(1.5) / main 직접 커밋이거나 버전 일부 빠짐(1) / 버전 구분 없음(0.5) / 없음(0)
- [1] v1.0.0 태그·릴리즈 노트(이번 버전에서 해낸 것)·2~3분 시연 영상 링크(1) / 일부(0.5) / 없음(0)
- [3] Shipping zip 첨부(파일당 2GiB 이하), 채점자 PC에서 풀어 바로 실행, 5분 플레이 중 크래시·멈춤 없음(3) / 실행되지만 5분 안에 크래시·진행 불가(1.5) / 첨부했지만 실행 안 됨(1) / 없음(0)

> 검토에서 고친 점: CHANGELOG main 직접 커밋을 '버전 구분 없음'과 같은 0.5로 깎음. 문서는 main 직접 커밋이 허용되는데도 과하다. v1.0.0에 커리큘럼에 없는 'CHANGELOG 링크'를 요구한다. → main 직접 커밋은 1, 버전 구분 없음은 0.5. CHANGELOG 링크는 감점 없는 권장. / zip 기준이 3점/1점/0점뿐이라 '실행되지만 크래시'와 '실행 불가'를 구분하지 못한다. → 실행되지만 5분 안에 크래시 1.5, 실행 불가 1로 나눔. 진위·AI 문구 추가.

> 작성 메모: 문항 점수 0.85점(50×2÷118). 채점표 1점 = 0.085점. 릴리즈 확인 약 10분, zip 실행 약 10분. 진위: P3-42 구술에서 이 문항이 뽑혀 zip 구성이나 태그·릴리즈 차이를 설명하지 못하면 이 문항 점수의 50%만 인정한다. zip은 채점자 PC에서 실행해도 된다(다른 PC 실행이 목표). Shipping은 기본 설정에서 로그 파일을 남기지 않으므로 실패하면 에러 창을 캡처해 둔다. 채점자 PC에 VC++ 런타임이 없어서 생긴 실패는 응시자 탓이 아니므로 런타임을 설치하고 다시 실행한다. 내려받은 zip은 P3-24·P3-30 등 실행 확인 문항에서도 쓴다. 패키징 절차 자체는 블록3 P3-34에서 채점한다. 'Generate release notes'로 붙인 PR 목록만 있어도 이번 버전에서 해낸 것이 읽히면 노트로 인정한다. 커리큘럼은 문서를 main에 바로 커밋해도 된다고 하지만 W24 과제는 docs/changelog 브랜치를 지정하므로, main 직접 커밋은 기준4에서 조금만 깎는다. 릴리즈 노트를 AI로 다듬은 것은 감점하지 않는다.

### P3-40 (0.42점) — 목표: W01-34, C-31, C-49, C-50, C-56, W04-31, W08-27, W20-13, W12-21, W22-07

**모범 답안**

- 여는 순서(약 10분): ① ue5-til에서 채점자가 달마다 1~2개씩 고른 TIL 10개 ② docs/devlog에서 서로 다른 단계 4편(예: W03·W08·W15·W20) ③ docs/retro/M1~M5 ④ main의 'docs(…)' 커밋 3개를 열어 바뀐 파일 ⑤ unreal-study-log README.
- ① 통과: 키워드·배운 것·막힌 점 → 해결·다음 할 일이 그날 과제와 이어진 구체 내용(에러 원문, 숫자, 파일·함수 이름, 해 본 실험)으로 채워짐. HTML 형식의 '오늘 한 과제' 칸은 자동 목록이어도 된다. 커리큘럼 문장을 그대로 옮긴 '배운 것'은 불통과. '막힌 점: 없음'인 날은 괜찮다.
- ② 통과: 근거 칸에 실제 PR·커밋 링크, 배운 것 3줄이 내 말, 숫자 줄(커밋·PR·코테·학습 시간)이 채워짐.
- ③ 편마다 Keep·Problem·Try 세 칸이 그 달의 일(과제 이름, 버그, 관문 결과, AI-Off 결과)을 하나 이상 가리키면 통과. '- ' 빈칸이나 '열심히 하자'뿐이면 불통과. M3에는 루브릭 6항목(기능 완성도·코드 품질·엔진 이해·문제 해결 기록·협업 습관·AI 활용) 1~4점. HTML 초안의 '루브릭 자가 평가' 줄이 '_' 그대로면 점수 없음.
- ④ TIL이 학습 로그 저장소 ue5-til에, Devlog·회고가 게임 저장소 docs/devlog·docs/retro에 있는지 본다. 'docs(…)' 커밋 3개의 바뀐 파일에 Source/·Content/·Config/가 있으면 섞인 것이다(0.5). 문서를 docs/ 브랜치 PR로 올린 것은 감점하지 않는다('바로 커밋해도 된다'는 허용 규칙).
- ⑤ TIL 목록(월별·주제별 링크 등), 게임 저장소 docs/engine-notes 링크, 코테 '풀이 n문제'(사이트·유형별 등) 통계가 있는지 본다. README가 링크한 별도 인덱스 문서도 인정.
- 만점 예: TIL 9/10, Devlog 4/4, 회고 5편 + M3 6항목 점수, 위치 맞고 문서 커밋 깨끗, README 인덱스 세 가지. 부분 예: 회고가 M1·M2뿐(③ 1점), Devlog 1편을 docs/ 대신 루트에 둠(④ 0.5점), README에 TIL 목록만(⑤ 1점).
- 구술 질문(의심될 때): '이 TIL(채점자가 고른 1개)의 막힌 점 → 해결을 30초로 다시 말해 보라.' / 'M3 회고의 Try 하나를 다음 달에 어떻게 지켰나(또는 왜 못 지켰나)?'

**채점표 (10점)**

- [2] ① 표본 TIL 10개가 그날 내용으로 내 말(8개 이상 2 / 5~7개 1 / 4개 이하 0)
- [2] ② 표본 Devlog 4편의 근거 링크·배운 것 3줄·숫자(4편 2 / 2~3편 1 / 1편 이하 0)
- [3] ③ 회고 M1~M5 중 KPT 세 칸이 그 달의 일로 채워진 편 수와 M3 루브릭 6항목 점수(5편 + M3 점수 3 / 3~4편이거나 M3 점수 없음 2 / 1~2편 1 / 없음 0)
- [1] ④ TIL은 ue5-til, Devlog·회고는 docs/devlog·docs/retro에 있고 문서 커밋 표본 3개에 코드 파일 없음(1) / 위치 하나 다르거나 코드 섞인 커밋 있음(0.5) / 위치 둘 이상 다름(0)
- [2] ⑤ 학습 로그 README(또는 링크된 인덱스)의 TIL 목록·엔진 노트 링크·코테 통계(셋 2 / 하나·둘 1 / 없음 0)

> 검토에서 고친 점: ④ '문서 커밋에 코드 파일 섞임'은 P3-04 ④(PR 없는 코드 커밋)와 같은 커밋을 이중으로 감점한다. answer_key 안에서도 '감점'과 '다시 깎지 않는다'가 서로 모순된다. → ④를 기록 위치 중심으로 다시 썼다. 코드가 섞인 커밋은 이 문항에서 0.5까지만 깎는다고 정했다. / ③ 'KPT가 내 말'을 판정할 관찰 기준이 없다. → KPT 세 칸이 각각 그 달의 일(과제, 버그, 관문, AI-Off 결과)을 하나 이상 가리키면 통과로 정의했다. 초안 빈칸 '_'가 그대로면 점수가 없다. / ⑤가 README에만 인덱스를 요구한다. W22 과제는 '학습 로그 저장소 인덱스 정리'일 뿐 파일 위치를 정하지 않는다. → README가 링크한 별도 인덱스 문서도 인정했다.

> 작성 메모: 배점 50×1÷118 ≈ 0.42점. 심사 약 10분. 6개월 실제 기록을 본다. TIL·Devlog의 '언제 올렸나(리듬)'는 P3-04 ⑤, 이 문항은 '무엇을 썼나(내용)'와 '어디에 두었나(경로)'만 본다. HTML 초안 형식(📅·📌·✅·📖·🧱·➡️ 머리글)이면 '코드·실험' 대신 '오늘 한 과제' 칸을 인정. 회고 5편은 M1(W04)·M2(W08)·M3(W12)·M4(W16)·M5(W20). 6개월 회고(W24)는 이 문항에서 보지 않는다. HTML 회고 초안에는 모든 달에 '루브릭 자가 평가(1~4)' 줄이 있으나 채점은 M3만 본다. 문서 커밋에 코드가 섞인 것은 P3-04 ④에서도 걸리므로 여기서는 0.5까지만 깎는다. 파일 이름이 달라도 같은 역할의 문서면 인정. P3-42 진위 확인에 뽑히면 구술 질문을 쓰고, 설명하지 못하면 이 문항 점수의 50%만 준다.

> **구술** — 시험 마지막 날 이후 응시자별 40분

### P3-42 (0.85점) — 목표: W23-02, W23-03, W23-04, W21-10

**모범 답안**

진행표(40분): 0~5 소개 / 5~12 핵심 파일 2개 / 12~14 TS 30초 / 14~22 딥다이브 / 22~37 진위 확인 3문항×5분 / 37~40 여유·기록.
사전 준비: 사전 심사 때 진위 확인 3문항을 정하고, 학습 로그(interview/ 등)에 1분·3분 스크립트 파일이 있는지 봐 둔다. docs/deepdive.md에서 주제를 확인한다.
- 소개: 1분 버전 50~70초, 3분 버전 2분 40초~3분 20초. 장르·기간·인원 → 핵심 기술 3개(예: 데이터 주도 전투, 2인 협동+GAS 예측, 성능 개선 수치) → 어려웠던 문제 한 줄 → 배운 점. 숫자(기간, 지연 200ms, 개선 ms, 테스트 수)와 링크(README, 영상을 화면에서 가리킴)가 있어야 완료. 스크립트를 보고 읽으면 0.5.
- 핵심 파일: 응시자가 5개 이름을 말하면, 진위 확인 문항의 핵심 코드와 겹치지 않는 2개를 고른다. 기대 답 예(이름·설계는 학생 것, 자기 코드와 맞게 말하면 인정):
 · UCombatComponent: 섹션 예약 콤보, NotifyState 윈도우, 소켓 Sweep + TSet 1회 타격. 2인에서 입력은 클라, 판정·데미지는 서버.
 · GA_MeleeCombo: LocalPredicted, PlayMontageAndWait·WaitGameplayEvent, GE_Damage(SetByCaller)를 서버에서 적용.
 · UArenaAttributeSet: PreAttributeChange Clamp, PostGameplayEffectExecute에서 IncomingDamage → Health(서버), 속성 복제와 OnRep.
 · UInteractionComponent: 0.1초 타이머 SphereTrace, 대상이 바뀔 때만 OnFocusChanged, IInteractable은 Execute_로 호출. 2인에서 감지와 실행이 어느 머신에서 도는지는 자기 코드대로 말하면 된다.
 · 공격 BTTask: ExecuteTask가 InProgress → 끝나면 FinishLatentTask, AbortTask에서 정리. AIController는 서버에만 있다.
- TS 30초: 채점자가 docs/troubleshooting에서 1건을 고른다(진위 확인 문항과 다른 것). 부록 TS 템플릿 7번 구조(문제 → 좁힌 방법 → 원인 → 해결 → 규칙). 20~40초.
- 딥다이브 질문 예(3개 이상): A Unreal MCP 'AI에 맡긴 것과 사람이 검증한 것', B StateTree 'BT 대비 구조·디버깅·성능 차이', C CMC 커스텀 '러버밴딩이 왜 생기고 FSavedMove 플래그가 어떻게 막나', D 에디터 도구 '기획자가 무엇을 덜 하게 됐나, 잘못된 데이터는 어떻게 막나', E 엔진 분석 'GC 도달성이나 CMC 보정 흐름을 함수 순서로'. 공통 꼬리: 근거 수치, 한계와 다음 단계.
- 진위 확인(이 문항 점수에는 넣지 않는다)
 · 고르기: 사전 심사에서 의심 표시한 문항 우선. 없으면 배점이 큰 포트폴리오 문항 중 서로 다른 달에서 3개, 2개 이상은 코드 문항. P3-42는 고르지 않는다.
 · 방법: 응시자가 코드·문서를 직접 연다 → 핵심 흐름과 결정 이유를 말한다 → 그 문항 answer_key의 구술 질문 1~2개.
 · '설명 못 함'은 다음 중 하나: 2분 안에 핵심 코드·문서 위치를 못 찾음, 핵심 흐름을 틀리게 말하고 다시 물어도 못 고침, 결정 이유를 하나도 말하지 못함.
 · 기록: 문항 id · 판정 · 근거 한 줄. 설명 못 한 문항은 그 문항 점수 × 50%.
 · 'AI 도움을 받았다'는 말 자체로는 감점하지 않는다. PR 'AI 활용' 칸과 구술 내용이 크게 다르면(예: '없음'이라 적었는데 AI가 짰다고 말함) 따로 적어 P3-05(PR) 채점에 넘긴다.
- 부분 예: 스크립트 파일 없음(기준1 1.5). 3분 버전이 4분(기준1 1.5). 파일 1개만 4요소를 말함(기준2 1.5~2). 콤보 흐름에서 서버·클라 위치를 거꾸로 말함(기준2 0.5~1). TS에서 원인만 말함(기준3 0.5). 꼬리 질문 2개에만 근거를 댐(기준4 2).

**채점표 (10점)**

- [2.5] 소개: 학습 로그에 1분·3분 스크립트가 있고, 보지 않고 시간 안에(1분 50~70초, 3분 2분 40초~3분 20초) 장르·기간·인원 → 핵심 기술 3개 → 어려웠던 문제 → 배운 점을 숫자·링크로 말함(2.5) / 스크립트 없음·시간 초과·숫자 없음 중 하나(1.5) / 둘 이상이거나 스크립트를 보고 읽음(0.5) / 못 함(0)
- [3] 핵심 파일 2개: 파일마다 책임·핵심 함수 흐름·서버/클라 실행 위치·설계 이유나 한계를 3분 안에 설명(3) / 1개만 완전하거나 요소 일부 빠짐(1.5~2) / 흐름을 틀리게 설명(0.5~1) / 못 함(0)
- [1.5] TS 30초: 채점자가 고른 TS를 보지 않고 문제 → 좁힌 방법 → 원인 → 해결 → 규칙 순서로 20~40초에 말함(1.5) / 단계 1~2개 빠짐이나 시간 초과(0.5~1) / 못 함(0)
- [3] 딥다이브: docs/deepdive.md 주제로 꼬리 질문 3개 이상에 근거(수치·소스·영상 결과)로 답하고 한계·다음 단계를 말함(3) / 근거 있는 답 1~2개(1~2) / 못 함(0)

> 검토에서 고친 점: W23-03의 '스크립트 작성'을 확인하는 기준이 없다(말하기만 채점). → 기준1에 학습 로그의 1분·3분 스크립트 파일 확인을 넣고 2.5점으로 조정(기준2는 3점). / 코드 설명 요소 '다시 짠다면'은 커리큘럼에 없다. UInteractionComponent 기대 답 '감지는 로컬 플레이어에서'는 커리큘럼이 정한 설계가 아니다. → '설계 이유나 한계'로 바꿈. 2인 실행 위치는 자기 코드대로 말하면 인정. / 진위 3문항은 미리 정하는데 '2)에서 설명한 파일과 겹치지 않게' 고르라고 해 순서가 맞지 않는다. 'TS 문서는 보지 않는다'는 진위 확인(문서를 직접 엶)과 충돌한다. 시험 PC Clone에는 블록3 결함이 있다. → 2)의 파일을 진위 문항과 겹치지 않게 고름. P3-42 자신은 제외. 자료를 보지 않는 규칙은 1)~4)에만 적용. GitHub 웹이나 깨끗한 Clone만 씀.

> 작성 메모: 문항 점수 0.85점(50×2÷118). 채점표 1점 = 0.085점. 라이브 블록과 다른 시간에 40분으로 한다. 1)~4) 동안 응시자는 AI·메모 없이 저장소 화면(GitHub 웹 또는 결함을 심지 않은 깨끗한 Clone)만 공유하고, interview/ 스크립트와 TS 문서는 보지 않는다. 5) 진위 확인에서는 해당 코드·문서를 직접 연다. 시간 때문에 W23의 '핵심 파일 5개×3분'은 5개 이름 + 2개×3분으로, W21의 '10분 질의응답'은 8분으로 줄였다. 꼬리 질문은 커리큘럼 범위 안에서만 한다. 진위 확인 3문항은 사전 심사 때 미리 정하고 구술 때 알린다. 2)의 파일 2개는 진위 확인 문항의 핵심 코드와 겹치지 않게 고른다. 이 문항 채점표는 구술 능력(소개·코드 설명·TS·딥다이브)만 채점한다. 진위 확인 결과는 고른 3문항의 점수에만 50% 규칙으로 반영하고, P3-42 자신은 고르지 않는다. 딥다이브 주제는 docs/deepdive.md에서 확인하고, 없으면 구술 시작 때 응시자가 말한다. W23 AI 면접관 리허설처럼 AI로 연습한 것은 감점하지 않는다.
