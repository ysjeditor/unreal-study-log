# 🎮 언리얼 엔진 5 C++ 6개월 취업 포트폴리오 커리큘럼

> C#/유니티 입문자를 위한 'AI 지름길' 과정 — 학습 과정 자체가 포트폴리오가 되도록  
> 문서 v2.0 · 최종 수정 2026-11-25 · 기준 엔진 **Unreal Engine 5.8**

**날짜별 학습 카드**(넘기면서 학습 → 기록까지)·🔔 기록 알림·GitHub Desktop 따라 하기·면접 카드는 같은 폴더의 **[인터랙티브 가이드(UnrealEngine_6Month_Study_Guide.html)](./UnrealEngine_6Month_Study_Guide.html)**에서 할 수 있습니다.

## 목차
1. [과정 개요](#1-과정-개요)
2. [6개월 로드맵](#2-6개월-로드맵)
3. [주차별 커리큘럼](#3-주차별-커리큘럼)
4. [AI 학습법](#4-ai-학습법)
5. [포트폴리오 & Git](#5-포트폴리오--git)
6. [Git 기록 가이드](#6-git-기록-가이드)
7. [평가 기준 & 관문](#7-평가-기준--관문)
8. [면접 질문 은행](#8-면접-질문-은행)
9. [템플릿](#9-템플릿)
10. [자료 & 대응표](#10-자료--대응표)

---

## 1. 과정 개요

| 항목 | 내용 |
|---|---|
| **대상** | C#(클래스·인터페이스·배열) + 유니티(프리팹·애니메이션) 경험 2개월, C/C++ 경험 없음 |
| **기간** | 24주 커리큘럼 + 버퍼 2주 = 26주(약 6개월), 시작 전 0주차 3~5일 |
| **시간** | 주 22~25시간 기준 (평일 2.5시간 + 주말 5시간 + 매일 코테 30분). 시간이 적으면 '필수'만 |
| **환경** | UE 5.8 · Windows 11 · Visual Studio 2026 · GitHub Desktop(LFS) |
| **최종 산출물** | 2인 협동 액션 웨이브 서바이벌 프로토타입(C++/GAS/멀티) + 시연 영상 + 기술 포트폴리오 PDF + 6개월 학습 기록 저장소 |

### 이 과정의 'AI 지름길' 전략

**건너뛰는 것**
- C++ 문법책을 처음부터 끝까지 읽기, 콘솔 프로젝트만 몇 주씩 만들기
- C 언어, 템플릿 메타프로그래밍, STL 세부 구현 같은 '언리얼 실무에 바로 안 쓰는' 깊이
- 엔진 소스를 처음부터 통독하기 — 질문이 생겼을 때 그 함수만 찾아 읽는다

**절대 건너뛰지 않는 것**
- 포인터·참조·메모리 수명 — 언리얼 크래시의 대부분이 여기서 나온다
- 상속·virtual·Super — 엔진 클래스를 상속해 쓰는 것이 언리얼 개발의 기본 동작이다
- UPROPERTY와 GC, 리플렉션 — 유니티 출신이 가장 많이 틀리는 지점
- 컴파일·링크 에러 읽기, 중단점·콜스택 디버깅 — AI에게 묻기 전에 스스로 좁혀야 한다
- 내 코드를 말로 설명하기 — 코딩테스트·기술 면접·과제 전형에는 AI가 없다

> **방법:** C++은 별도 과정으로 배우지 않는다. 매주 언리얼 기능을 만들면서 그 주에 필요한 C++만 'C++ 생존 문법'으로 익히고, 매일 코딩테스트 1문제를 C++로 풀며 문법을 손에 붙인다. AI는 매달 의존도를 낮춰 가고(L1 → L3), 매달 한 번은 AI 없이 재구현해 실력을 확인한다.

### 기업이 보는 것 ↔ 이 과정이 남기는 증거

| 평가 포인트 | 이 과정의 증거 | 대비되는 면접 질문 |
|---|---|---|
| **C++ 기본기** | 코테 C++ 약 90문제 · W13 기본기 점검 · AI-Off 챌린지 4회 기록 | 포인터/참조, virtual, 메모리, 스마트 포인터 질문 |
| **엔진 이해도('왜?')** | 엔진 소스 노트 5편 + 콜스택 캡처 · ADR 5건 | UPROPERTY/GC, 액터 생명주기, CDO |
| **완성도** | 플레이 가능한 빌드 · 릴리즈 6회(v0.1 → v1.0) · 시연 영상 | 프로젝트 1분/3분 설명 |
| **문제 해결력** | 트러블슈팅(TS) 문서 6건 이상 — 증상·가설·검증·원인·해결·재발 방지 | 가장 어려웠던 버그는? |
| **네트워크 · GAS** | 2인 협동, Server RPC/OnRep, GAS 예측 전/후 반응성 비교 영상 | 리플리케이션·RPC·GAS 구성요소 |
| **최적화 감각** | Size Map·풀링·Insights 성능 리포트(전/후 ms) | 병목을 어떻게 찾나? |
| **협업 습관** | 이슈 → 브랜치 → PR(셀프 리뷰·AI 활용 내역) → 릴리즈, 커밋 규칙 | Git 충돌·바이너리 에셋 관리 |
| **성장 가능성** | 6개월 매일 TIL + 주간 Devlog + 월간 회고 + '같은 기능의 진화' 표 | 어떻게 공부하나? AI는 어떻게 쓰나? |

### 만들 게임 — 범위를 먼저 고정한다

| 항목 | 내용 |
|---|---|
| **가칭** | ActionArena — 3인칭 근접 액션 웨이브 서바이벌 (2인 협동) |
| **핵심 루프** | 메뉴 → 웨이브 전투(콤보·대시) → 휴식 → 다음 웨이브 → 게임오버 → 최고 기록 저장 |
| **범위 제한** | 맵 1개 · 플레이어 무기 2종 · 적 2종(근접/원거리) · 어빌리티 3~4개 · 2인 Listen Server |
| **만들지 않는 것** | 오픈월드, 인벤토리·퀘스트, 스토리, 커스텀 캐릭터 아트 — 범위가 포트폴리오를 죽인다 |

### 현실 체크
- **일정은 도전적이다.** 주 22~25시간 기준이다. 시간이 부족하면 '필수'만 하고, 그래도 밀리면 W13의 v0.3.0(싱글 MVP)을 1차 포트폴리오로 지원을 시작하고 이후 단계는 병행한다.
- **AI 지름길의 한계를 인정한다.** 코딩테스트·기술 면접·과제 전형에는 AI가 없다. 그래서 매주 C++ 생존 문법, 매일 코테, 매달 AI-Off 챌린지를 둔다.
- **Windows + Visual Studio는 업계 표준 환경과 같다.** 과제 전형·입사 후 환경과 거의 같고, 패키징한 Windows 빌드를 평가자가 바로 실행해 볼 수 있다. 그래도 **영상이 1순위 전달 수단**이다.
- **PC 사양을 먼저 확인한다.** 공식 권장은 RAM 32GB · 그래픽 메모리 8GB 이상이다. 그보다 낮으면 Scalable 설정·불필요한 앱 종료·짧은 PIE 세션으로 버티고, 무거운 에셋(메가스캔·고해상도 환경)은 쓰지 않는다.
- **버전 정보는 바뀐다.** Visual Studio·MSVC 버전 호환성, 플러그인 상태 같은 사실은 설치·사용 직전에 공식 문서로 재확인한다(이 문서 작성일: 2026-11-25).

### 학원·스터디에서 이 문서를 쓰는 법
- **주 1회 1:1 리뷰(30분)** — 그 주 PR 1개를 함께 보고, 해당 주차 자가 점검 질문 3개를 무작위로 묻는다.
- **월 1회 데모데이** — 릴리즈 기준 5분 시연 + 3분 질의. 루브릭 6항목으로 평가.
- **관문(Gate) 운영** — 단계마다 관문 체크리스트를 통과해야 다음 단계로. 버퍼 2주는 학습자 재량.
- **진척도 공유** — HTML 가이드에서 진척도를 JSON으로 내보내 멘토에게 전달(가져오기로 복원).
- **강사 체크 포인트** — UPROPERTY 누락 · 생성자 로직 · 무분별한 Tick · 하드 레퍼런스 · 권한 분기 누락 — 유니티 출신이 반복하는 5대 실수.

---

## 2. 6개월 로드맵

### 단계 요약

| 단계 | 주차 | 주제 | 릴리즈 | 이 단계가 증명하는 것 | AI 레벨 |
|---|---|---|---|---|---|
| 0 | W00 | 사전 준비 | — | 개발·기록 환경 | — |
| M1 | W01~W04 | 언리얼 C++ 첫걸음 | v0.1.0 움직이는 캐릭터 | C++을 몰라도 언리얼 C++로 시작할 수 있고, 내가 쓴 코드를 설명할 수 있다. | L1 — AI가 쓰고 내가 한 줄씩 해설 |
| M2 | W05~W08 | 상호작용 & 전투 | v0.2.0 콤보 전투 + 데이터 주도 무기 | 결합도 낮은 설계(인터페이스·델리게이트)와 데이터 주도 설계를 할 줄 안다. | L1~L2 — 새 개념은 AI 초안+해설, 반복 패턴은 내가 먼저 작성 |
| M3 | W09~W12 | UI · AI · 게임 루프 | (v0.3.0 준비) | 메모리를 의식하고(소프트 레퍼런스), 디버깅 도구로 근거를 제시하며, 한 판짜리 게임을 완성한다. | L2 — 내가 먼저 작성하고 AI가 리뷰 |
| M4 | W13~W16 | 기본기 점검 & 멀티플레이 & GAS 입문 | v0.3.0 싱글플레이 MVP | AI 없이도 기본을 구현하고, 싱글 게임을 멀티로 전환하며 생긴 문제를 해결할 수 있다. | L2 + AI-Off 점검 주간 |
| M5 | W17~W20 | GAS 완성 · 최적화 · 품질 | v0.4.0 2인 협동 → v0.5.0 RC | 실무 프레임워크(GAS)와 측정 기반 최적화, 테스트로 품질을 관리한다. | L2~L3 — 내가 작성하고 AI는 검증·대안 제시 |
| M6 | W21~W24 | 차별화 & 취업 패키지 | v1.0.0 최종 | 깊게 판 한 가지와, 그것을 설명하는 문서·영상·말하기 능력. | L3 — AI 없이 작성, AI로 검증 / 면접·코테는 AI-Off |
| 버퍼 | +2주 | 밀린 주차 보충 | — | 어디서든 사용(권장: W12 이후, W17 이후) | — |

### 주차 한눈에 보기

| 주차 | 언리얼 주제 | C++ 생존 문법 | 릴리즈 |
|---|---|---|---|
| [W00](#w00) | 개발 환경 & 포트폴리오 저장소 세팅 | — |  |
| [W01](#w01) | 첫 C++ 액터 만들기 | .h/.cpp · 포인터 첫 만남 |  |
| [W02](#w02) | 리플렉션 · UObject · GC | 포인터·참조·메모리 |  |
| [W03](#w03) | 액터·컴포넌트 생명주기 & 게임플레이 프레임워크 | 상속 · virtual · Super |  |
| [W04](#w04) | 캐릭터 · Enhanced Input · 3D 수학 | 템플릿 읽기 · const& | v0.1.0 · 움직이는 캐릭터 |
| [W05](#w05) | 인터페이스 · 델리게이트 · 타이머 — 상호작용 시스템 | 추상 클래스 · 람다 |  |
| [W06](#w06) | 애니메이션 C++ — AnimInstance & 로코모션 | const 함수 · 스레드 기초 |  |
| [W07](#w07) | 콤보 공격 — 몽타주 · 노티파이 · 히트 판정 | 컨테이너 · 해시 |  |
| [W08](#w08) | 데미지 파이프라인 & 데이터 주도 설계 | struct · enum · 전달 비용 | v0.2.0 · 콤보 전투 + 데이터 주도 무기 |
| [W09](#w09) | UI(UMG) & 비동기 로딩 | 스마트 포인터 · 콜백 수명 |  |
| [W10](#w10) | AI ① — AIController · Behavior Tree | 리팩터링 · 상속 설계 |  |
| [W11](#w11) | AI ② — Perception · 원거리 적 · 디버깅 도구 | 디버깅 습관 · 코드 리뷰 |  |
| [W12](#w12) | 게임 루프 — 웨이브 · Subsystem · 오브젝트 풀 · 세이브 | Subsystem · 리셋 설계 |  |
| [W13](#w13) | C++ 기본기 점검 & 싱글플레이 MVP | 총정리: 이동 · Rule of 3/5 | v0.3.0 · 싱글플레이 MVP (1차 지원 가능 시점) |
| [W14](#w14) | 네트워크 ① — 리플리케이션 · RPC · 권한 | 권한 분기 · 매크로 읽기 |  |
| [W15](#w15) | 네트워크 ② — 싱글 → 2인 협동 전환 | (실전 적용) |  |
| [W16](#w16) | GAS ① — ASC · AttributeSet · GameplayEffect · Tags · 첫 Ability | 매크로 보일러플레이트 · 모듈 |  |
| [W17](#w17) | GAS ② — 전투 이전 + 2인 협동 완성 | 비동기 흐름(AbilityTask) | v0.4.0 · 2인 협동 |
| [W18](#w18) | 프로파일링 & 최적화 | 측정 매크로 · 복사 제거 |  |
| [W19](#w19) | 품질 — 자동화 테스트 · 치트 · 버그 제로 · Shipping | 테스트 가능한 설계 |  |
| [W20](#w20) | 폴리시 & 게임필 | — | v0.5.0 · 릴리즈 후보(RC) |
| [W21](#w21) | 차별화 딥다이브 (택1) | — |  |
| [W22](#w22) | 포트폴리오 패키지 — 영상 · README · PDF | — |  |
| [W23](#w23) | 면접 대비 — 질문 은행 · 코드 설명 · 모의 코테 | — |  |
| [W24](#w24) | 지원 · v1.0.0 · 6개월 회고 | — | v1.0.0 · 최종 |

### 같은 기능의 진화 — 포트폴리오 스토리라인

면접에서 '이 기능은 처음엔 이렇게 만들었고, 이런 문제 때문에 이렇게 바꿨습니다'라고 말할 수 있게 일부러 같은 기능을 여러 번 발전시킨다.

| 기능 | 진화 과정 |
|---|---|
| **체력 · 데미지** | W5 델리게이트 컴포넌트 → W8 데이터·데미지 파이프라인 → W15 네트워크 복제 → W17 GAS AttributeSet |
| **공격** | W7 몽타주 콤보 + Sweep 판정 → W10 적 AI가 재사용 → W15 Server RPC → W17 GAS 어빌리티 + 예측 |
| **이동** | W4 Enhanced Input · 스프린트 → W8 스탯 데이터화 → W15 러버밴딩 TS → W16 GAS 대시 → W21-C CMC 예측 |
| **무기** | W8 DataAsset → W9 소프트 레퍼런스 비동기 로딩 → W20 타격감 데이터 |
| **방향 판정(수학)** | W4 내적·외적 디버그 → W6 CalculateDirection 비교 → W11 피격 방향 리액션 |
| **UI** | W9 이벤트 기반 HUD → W12 메뉴·게임오버 → W15 복제 값 반영 → W17 속성 변경 델리게이트 |
| **AI** | W10 Behavior Tree → W11 Perception · Visual Logger → W15 서버 전용 → W17 GAS 공격 → W21-B StateTree |

### 주간 리듬 (주 22~25시간)

| 요일 | 시간 | 할 일 |
|---|---|---|
| 월 | 2.5h | 이번 주 개념 + 엔진 소스 .h 먼저 읽기, 이슈 쪼개기 |
| 화~목 | 각 2.5h | 구현: 이슈 → 브랜치 → 작은 커밋 → PR |
| 금 | 2.5h | 버그 · 리팩터링 · PR 셀프 리뷰 · AI 리뷰 |
| 토 | 5h | 구현 마무리 + 문서(TS · ADR · 엔진 노트) + 영상·GIF 캡처 |
| 일 | 2h | 주간 Devlog · 회고 · 다음 주 계획 (가볍게) |
| 매일 | 40분 | 코딩테스트 1문제(C++) 30분 + TIL 10분 |

### 기능 1개를 배우는 5단계 루프

- **1. 질문** — 무엇을 만들고, 왜 필요한가? 이슈 1개로 적는다.
- **2. 설계** — AI 힌트 모드로 단계·클래스·주의점부터. 엔진 헤더로 API 확인.
- **3. 구현** — 이번 달 AI 레벨(L1~L3)대로 작성. 작게 커밋.
- **4. 증명** — 중단점·로그·디버그 드로잉·GIF로 '동작한다'를 보인다.
- **5. 기록** — TIL / TS / ADR / 엔진 노트 중 맞는 것 + PR 셀프 리뷰.

---

## 3. 주차별 커리큘럼

> 과제 표기: **[필수]** 시간이 부족해도 반드시 / **[심화]** 여유가 있을 때. 모든 주차(W01~)에는 공통 과제 2개(코테, TIL·Devlog)가 추가된다.  
> 엔진 소스 경로 안내: 경로는 UE 5.8 기준 안내다. 버전에 따라 위치가 바뀔 수 있으니 Visual Studio의 `Ctrl+T`(모두 이동)에 파일명만 넣어 찾는다. 읽는 순서: ① 헤더(.h)의 주석과 선언만 → ② 궁금한 함수 하나만 .cpp에서 → ③ 중단점으로 실제 호출 확인.

### 0주차 · 사전 준비

<a id="w00"></a>

#### W00 · 개발 환경 & 포트폴리오 저장소 세팅 (3~5일 · W1 시작 전)

> 🎯 **목표:** Windows PC에서 UE 5.8 C++ 프로젝트를 빌드·디버깅할 수 있고, 학습 기록이 GitHub에 쌓이기 시작한 상태를 만든다.

**핵심 개념**
- **버전 고정:** UE 5.8(2026-06 정식 출시, 작성 시점 최신 정식)의 최신 핫픽스를 설치하고 6개월간 바꾸지 않는다. 5.9는 Preview(2026-11)라 포트폴리오에 쓰지 않는다. UE6 소식이 나와도 흔들리지 않는다.
- **Windows 공식 요구사항(UE 5.8):** Windows 10 22H2 이상(권장 Windows 11). 개발 도구는 **Visual Studio 2026(18.0 이상)** 권장, VS 2022(17.14 이상)도 지원. 권장 사양은 쿼드코어 2.5GHz · **RAM 32GB** · 그래픽 메모리 8GB 이상 — 사양이 낮으면 가벼운 설정이 필수다.
- **Windows 빌드 루프:** `.cpp` 함수 안쪽만 고쳤다면 에디터를 켠 채 **Live Coding**(`Ctrl+Alt+F11` 또는 에디터 오른쪽 아래 Compile 버튼). 헤더(.h)·`UPROPERTY`·생성자를 바꿨다면 **에디터 종료 → Visual Studio에서 F5**로 다시 실행한다.
- **엔진 소스는 이미 내 컴퓨터에 있다:** 런처로 설치한 엔진에도 `Engine/Source`가 포함돼 Visual Studio에서 **F12(정의로 이동)**·**Ctrl+T(파일·심볼 검색)**로 바로 읽힌다. GitHub `EpicGames/UnrealEngine` 접근은 웹 검색·blame용 선택 사항.
- **경로 규칙:** 프로젝트는 `C:\Projects`처럼 **짧은 영문 경로**에 둔다. 한글이 들어간 경로와 OneDrive가 동기화하는 바탕화면·문서 폴더는 빌드 에러와 동기화 충돌의 흔한 원인이다.

**유니티/C#에서 건너오기**
- 유니티 허브 + Visual Studio ↔ Epic Games Launcher + Visual Studio (유니티 때와 같은 VS에 C++ 게임 개발 워크로드만 추가)
- 유니티에서 `Library/`·`Temp/`를 커밋하지 않듯, 언리얼은 `Binaries/`·`Intermediate/`·`Saved/`·`DerivedDataCache/`를 커밋하지 않는다.

**✅ 과제**
- [ ] `환경` **[필수]** **UE 5.8** 설치 (Epic Games Launcher)
    - 👣 **따라 하기: UE 5.8 설치 (Epic Games Launcher)**
        1. **런처 설치** — store.epicgames.com에서 **Epic Games Launcher**를 내려받아 설치 → 실행 → Epic 계정으로 로그인 (없으면 새로 만들기)
        2. **언리얼 화면으로** — 런처 왼쪽 메뉴 `Unreal Engine` → 위쪽 `Library`(라이브러리) 탭
        3. **버전 추가** — `ENGINE VERSIONS` 옆 노란 `+` 버튼 → 새로 생긴 칸의 버전 숫자 ▾ → **5.8.x 중 가장 높은 번호** 선택 → `Install`
        4. **위치·옵션** — 설치 위치는 기본값 그대로 → `Options`에 'Editor symbols for debugging'(디버깅용 기호)이 보이면 체크. 용량이 커지지만 엔진 내부까지 콜스택을 볼 수 있다
        5. **기다리는 동안** — 수십 GB라 **몇 시간** 걸릴 수 있다. 전원을 연결하고, 받는 동안 다음 과제(Visual Studio 설치)를 같이 진행. 디스크 여유는 100GB 이상(SSD 권장)
        6. **확인** — `Library`의 5.8 칸에 `Launch` 버튼이 보이면 완료 (지금 실행하지 않아도 된다)
- [ ] `환경` **[필수]** **Visual Studio 2026** 설치 (C++ 게임 개발 워크로드)
    - 👣 **따라 하기: Visual Studio 2026 설치 (C++ 게임 개발)**
        1. **왜 하나요?** — 언리얼 C++ 코드를 컴파일·디버깅하는 도구. UE 5.8 공식 문서는 일반 개발에 **Visual Studio 2026(18.0 이상)**을 권장한다(VS 2022 17.14 이상도 지원). 무료인 **Community** 버전이면 된다
        2. **내려받기** — visualstudio.microsoft.com → `Community` 다운로드 → 받은 설치 파일 실행 → **Visual Studio Installer**가 열린다
        3. **워크로드 고르기** — `워크로드`(Workloads) 탭에서 체크: **C++를 사용한 게임 개발**(Game development with C++) · **C++를 사용한 데스크톱 개발**(Desktop development with C++) · **.NET 데스크톱 개발**(.NET desktop development)
        4. **구성 요소 확인** — 오른쪽 `설치 세부 정보`의 게임 개발 항목 아래 **C++ profiling tools**, **C++ AddressSanitizer**, **Windows 11 SDK(10.0.26100 이상)**, **Unreal Engine 관련 도구**(IDE support · Test Adapter)가 체크돼 있는지 확인. 'Unreal Engine installer'는 런처를 이미 깔았으면 꺼도 된다
        5. **설치** — `설치` → 용량이 커서 30분~1시간 걸린다 → 끝나면 재부팅
        6. **기억해 둘 것** — UE 5.8 공식 권장 컴파일러는 **MSVC 14.50**이다. 나중에 빌드가 MSVC 버전 경고·에러로 실패하면 Installer → `수정` → `개별 구성 요소`에서 'MSVC v14.50' 빌드 도구를 추가로 설치
- [ ] `환경` **[필수]** Visual Studio를 언리얼용으로 설정하기
    - 👣 **따라 하기: Visual Studio를 언리얼용으로 설정**
        1. **처음 실행** — Visual Studio 실행 → Microsoft 계정 로그인은 선택(`나중에`) → 개발 설정은 `Visual C++`, 테마는 원하는 것
        2. **오류 목록 자동 표시 끄기** — 메뉴 `도구`(Tools) → `옵션`(Options) → `프로젝트 및 솔루션` → '빌드가 오류와 함께 끝나면 항상 오류 목록 표시' **체크 해제** — 언리얼의 진짜 에러는 `출력`(Output) 창에 나온다
        3. **IntelliSense 설정** — 같은 `옵션` → `텍스트 편집기` → `C/C++` → `고급`(Advanced)에서 '외부 종속성 폴더 사용 안 함'을 True, `IntelliSense`에서 '64비트 IntelliSense 사용' 켜기
        4. **툴바 넓히기(선택)** — 위쪽 `Development Editor`가 보이는 칸이 좁으면 툴바 끝 ▾ → `단추 추가 또는 제거`에서 솔루션 구성 칸 너비를 넓히기
        5. **다음 단계** — 언리얼 프로젝트와 연결은 다음 과제 '연습 프로젝트 Sandbox'에서 한다
- [ ] `환경` **[필수]** 에디터를 가볍게 설정하기 (PC 사양이 낮을 때 특히)
    - 👣 **따라 하기: 에디터를 가볍게 만들기 (PC 사양이 낮을 때 특히)**
        1. **프로젝트 만들 때** — 프로젝트 브라우저 `Games` → `Blank` → 오른쪽 옵션: `C++` · Target Platform `Desktop` · Quality Preset `Scalable` · `Starter Content` 체크 해제
        2. **화질 낮추기** — 에디터 뷰포트 위쪽 툴바의 **계기판(속도계) 아이콘** → Scalability 항목에서 `Medium`(느리면 `Low`). UE 5.5 이전은 오른쪽 위 `Settings` 메뉴에 있다
        3. **뒤에 있을 때 CPU 줄이기** — 에디터 창 왼쪽 위 메뉴 `Edit` → `Editor Preferences` → 위쪽 검색창에 `Use Less CPU` → `Use Less CPU when in Background` 체크
        4. **작업 습관** — 에디터를 쓸 땐 브라우저 탭·다른 앱을 줄이고, ▶ Play는 짧게 확인하고 ■ Stop
- [ ] `환경` **[필수]** 연습 프로젝트 `Sandbox`로 '빌드 → 중단점 → Live Coding' 해 보기 (커밋 안 함)
    - 👣 **따라 하기: 연습 프로젝트로 '빌드 → 중단점 → Live Coding' 해 보기**
        1. **프로젝트 만들기** — 런처 `Unreal Engine` → `Library` → 5.8 `Launch` → 프로젝트 브라우저 `Games` → `Blank` → `C++`·`Desktop`·`Scalable`·Starter Content 해제 → 위치 `C:\Projects` · 이름 `Sandbox` → `Create` → 잠시 뒤 **Visual Studio가 자동으로 열린다** (첫 컴파일에 몇 분)
        2. **C++ 클래스 만들기** — 에디터 메뉴 `Tools` → `New C++ Class…` → `Actor` → 이름 `MyActor` → `Create Class` → 컴파일이 끝나면 Visual Studio에 `MyActor.h/.cpp`가 생긴다 → **에디터를 닫는다**
        3. **구성 확인** — Visual Studio 위쪽 칸이 `Development Editor` · `Win64`인지, 오른쪽 `솔루션 탐색기`에서 `Games` 아래 `Sandbox`가 **굵게**(시작 프로젝트) 보이는지 확인. 아니면 `Sandbox` 우클릭 → `시작 프로젝트로 설정`. 맨 위에 구성 요소가 부족하다는 노란 알림이 뜨면 `설치`
        4. **코드 한 줄** — `Ctrl+T` → `MyActor.cpp` 입력해 열기 → `BeginPlay()` 안 `Super::BeginPlay();` 바로 아랫줄에 아래 코드 붙여넣기 → `Ctrl+S`  `UE_LOG(LogTemp, Warning, TEXT("Hello Unreal from C++!"));`
        5. **중단점 찍기** — 방금 붙인 줄을 클릭하고 **F9** (또는 줄 번호 왼쪽 회색 여백 클릭) → 빨간 점이 생기면 중단점('이 줄에서 멈춰라')
        6. **디버그 실행** — **F5** (위쪽 ▶ `로컬 Windows 디버거`) → 빌드가 끝나면 언리얼 에디터가 뜬다 (처음엔 몇 분)
        7. **멈추는지 확인** — 콘텐츠 브라우저 `C++ Classes` → `Sandbox`의 `MyActor`를 레벨로 끌어다 놓기 → ▶ `Play` → Visual Studio가 앞으로 나오며 그 줄에서 멈추고, 아래 `호출 스택`(Call Stack) 창에 호출 순서가 보이면 성공 → **F5**로 계속
        8. **Live Coding 해 보기** — 에디터를 켠 채 Visual Studio에서 로그 문구만 바꾸고 `Ctrl+S` → 에디터로 돌아가 `Ctrl+Alt+F11`(또는 오른쪽 아래 Compile 버튼) → 다시 Play하면 바뀐 문구가 `Window` → `Output Log`에 보인다
        9. **빌드 규칙 기억하기** — `.cpp` 함수 안만 고쳤으면 **Live Coding**. 헤더(.h)·`UPROPERTY`·생성자를 고쳤으면 **에디터 종료 → Visual Studio에서 F5**. 헷갈리면 언제나 뒤쪽이 안전
        10. **시간 기록** — Visual Studio 아래 `출력`(Output) 창에 나온 빌드 시간을 TIL에 적어 두기 (나중에 비교 기준)
- [ ] `Git` **[필수]** **GitHub Desktop** 설치·로그인 → 이름·이메일 확인 → Git LFS 무료 한도 확인 (카드의 따라 하기 순서대로)
    - 👣 **따라 하기: GitHub Desktop 설치 · 로그인**
        1. **설치** — desktop.github.com에서 GitHub Desktop을 내려받아 설치 파일 실행 (자동으로 설치되고 바로 실행된다)
        2. **로그인** — `Sign in to GitHub.com` → 브라우저에서 `Authorize desktop` 승인 → Desktop으로 돌아오기
        3. **계정 확인** — 메뉴 `File` → `Options…` → `Accounts`에 내 GitHub 계정이 보이면 OK
        4. **이름·이메일** — 같은 창의 `Git` 탭에서 Name·Email이 GitHub 계정과 같은지 확인 → `Save`
        5. **작업 폴더** — 파일 탐색기(`Win+E`) → `내 PC` → `로컬 디스크 (C:)`에 `Projects` 폴더 만들기 → 앞으로 모든 저장소를 `C:\Projects`에 둔다 (한글·공백 없는 짧은 경로, OneDrive 폴더는 피하기)
        6. **무료 한도 확인** — GitHub 웹 Settings의 결제(Billing) 메뉴에서 Git LFS 무료 한도 확인(저장 10GiB · 월 10GiB). 결제수단이 없으면 초과 시 업로드가 막힐 뿐 요금은 나가지 않는다
- [ ] `Git` **[필수]** 학습 로그 저장소 `unreal-study-log`를 Windows PC로 가져오기 (Clone → `C:\Projects`)
    - 👣 **따라 하기: 학습 로그 저장소를 Windows PC로 가져오기 (Clone)**
        1. **Clone 열기** — GitHub Desktop 메뉴 `File` → `Clone repository…` → `GitHub.com` 탭
        2. **저장소 고르기** — 목록에서 `unreal-study-log` 선택 → 아래 `Local path`를 `C:\Projects\unreal-study-log`로 → `Clone`
        3. **확인** — 메뉴 `Repository` → `Show in Explorer` → `curriculum`·`ue5-til`·`cpp-basics`·`coding-test` 폴더가 보이면 성공
        4. **커리큘럼 열기** — `curriculum` 폴더의 `UnrealEngine_6Month_Study_Guide.html`을 **Chrome 또는 Edge**로 열고 즐겨찾기에 추가 — 앞으로 매일 여기서 시작
        5. **맥에서 체크한 게 있다면** — 맥 브라우저에서 ⚙ → `진척도 내보내기` → 받은 파일을 Windows로 옮겨 ⚙ → `진척도 가져오기` (없으면 건너뛰기)
- [ ] `Git` **[필수]** GitHub 프로필 정리(사진·한 줄 소개) + 브라우저에서 학습 로그 저장소의 README가 보이는지 확인
- [ ] `AI` **[필수]** AI 도구 2개 준비 + AI 학습 원칙 읽기
    - 👣 **따라 하기: AI 도구 준비**
        1. **채팅형 AI 1개** — Claude·ChatGPT·Gemini 중 하나 — 개념 질문과 설명용
        2. **코드를 읽는 AI 1개** — GitHub Copilot(Visual Studio 내장), Claude Code, Cursor 중 하나 — 내 프로젝트 파일을 보며 답하게 할 때
        3. **규칙 파일** — `CLAUDE.md`는 W1 첫날 카드의 '파일 받기'로 게임 저장소에 넣는다. 'UE 5.8 · Epic 코딩 표준 · 힌트 먼저 · 모든 줄 해설' 규칙이 들어 있다
        4. **원칙 읽기** — 📚 전체 커리큘럼 → `AI 학습법` 탭의 5원칙과 AI 레벨(L1→L3)을 한 번 읽기
- [ ] `소스` [심화] (선택) Epic Games 계정 ↔ GitHub 연동 → EpicGames 조직 초대 수락 → 웹에서 `EpicGames/UnrealEngine` 열람 확인

**📦 산출물:** 학습 로그 저장소 첫 커밋 · 빌드 시간 기록(이후 비교 기준) · AI 규칙 파일

**🏁 완료 기준(DoD)**
- 빈 C++ 프로젝트에서 중단점이 걸리고 콜스택이 보인다.
- `.cpp`를 고친 뒤 Live Coding(`Ctrl+Alt+F11`)으로 에디터를 끄지 않고 반영되는 것을 확인했다.
- GitHub에 학습 로그 저장소가 보이고, GitHub Desktop에서 그 저장소가 열린다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[협업·Git] 언리얼 프로젝트에서 Git에 올리지 않는 폴더와 그 이유는?</summary>

`Binaries`·`Intermediate`·`Saved`·`DerivedDataCache`는 빌드 산출물·캐시·로그라 언제든 재생성된다. 올리면 용량 폭증·충돌만 생긴다. 원본은 `Source`·`Config`·`Content`·`.uproject`.
</details>

<details><summary>[협업·Git] .uasset을 Git LFS로 관리하는 이유는?</summary>

바이너리라 diff·merge가 불가능하고 크다. LFS는 저장소엔 포인터만 두고 실제 파일은 별도 저장소에 둬서 클론·히스토리를 가볍게 유지한다. 팀에선 파일 잠금(lock)으로 동시 수정 충돌을 예방한다(회사에서 많이 쓰는 Perforce의 체크아웃과 같은 개념).
</details>

**🤖 AI 프롬프트**
```text
나는 Windows PC에서 UE 5.8 C++ 개발 환경을 만들고 있어. Visual Studio 버전·워크로드 선택, 언리얼용 VS 옵션, 프로젝트 경로 규칙, 에디터 성능 설정을 체크리스트로 정리해줘. 각 항목마다 '제대로 됐는지 확인하는 방법'을 붙이고, 확실하지 않은 버전 정보는 '공식 문서 확인 필요'라고 표시해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 과제1 UE 5.8 설치 (Epic Games Launcher) · 과제2 Visual Studio 2026 설치 (C++ 게임 개발 워크로드) · 자가 점검
- Day 2 (화, 약 3시간): 과제3 Visual Studio를 언리얼용으로 설정하기
- Day 3 (수, 약 3시간): 과제5 연습 프로젝트 Sandbox로 '빌드 → 중단점 → Live Coding'… · 과제4 에디터를 가볍게 설정하기 (PC 사양이 낮을 때 특히)
- Day 4 (목, 약 3시간): 과제6 GitHub Desktop 설치·로그인 → 이름·이메일 확인 → Git L… · 과제7 학습 로그 저장소 unreal-study-log를 Windows PC로 가… · 자가 점검
- Day 5 (금, 약 3시간): 과제8 GitHub 프로필 정리(사진·한 줄 소개) + 브라우저에서 학습 로그 저… · 과제9 AI 도구 2개 준비 + AI 학습 원칙 읽기 · 과제10 (선택) Epic Games 계정 ↔ GitHub 연동 → EpicGame…(심화) · TIL
- Day 6 (토, 약 5.5시간): 휴식
- Day 7 (일, 약 2.5시간): 휴식

**📒 이번 주 Git 기록**
- 남길 기록: 학습 로그 저장소 Clone → `C:\Projects\unreal-study-log` (게임 저장소는 W1)

**➕ 심화(선택):** `.editorconfig` 추가로 들여쓰기·줄바꿈 규칙 통일 / Visual Studio 단축키 손에 익히기: F12 정의 이동 · Shift+F12 참조 찾기 · Ctrl+T 검색 · F9 중단점 · F5 디버그 실행 · Ctrl+Shift+B 빌드

---

### M1 · 언리얼 C++ 첫걸음 (W01~W04)

> **이 단계가 증명하는 것:** C++을 몰라도 언리얼 C++로 시작할 수 있고, 내가 쓴 코드를 설명할 수 있다.  
> **릴리즈:** v0.1.0 움직이는 캐릭터 · **AI 레벨:** L1 — AI가 쓰고 내가 한 줄씩 해설  
> **코딩테스트(C++):** 백준 단계별 1~6단계(입출력·조건·반복·배열·함수·문자열) — C++ 문법 체득용, 주 5문제

<a id="w01"></a>

#### W01 · 첫 C++ 액터 만들기

> 🎯 **목표:** AI와 함께 첫 C++ 액터를 만들고, 그 코드의 **모든 줄을 내 말로 설명**할 수 있게 된다.

**🧩 C++ 생존 문법:** 헤더(.h)=선언 / 소스(.cpp)=정의, `#include`와 `#pragma once`, 클래스 선언 문법(`public:`, 끝의 `;`), 범위 지정 `::`, 포인터 첫 만남(`UStaticMeshComponent* Mesh`, `->`, `nullptr`)

**핵심 개념**
- UE 프로젝트 구조: `Source/`(코드) · `Content/`(에셋) · `Config/`(설정 ini) · `.uproject` · `*.Build.cs`(모듈 의존성) — `Binaries/`·`Intermediate/`는 생성물
- 접두사 규칙: `A`(Actor) · `U`(UObject) · `F`(구조체·일반) · `T`(템플릿) · `E`(열거형) · `I`(인터페이스) · `b`(bool)
- `UCLASS()`·`GENERATED_BODY()` 첫 인사, `UE_LOG`로 출력, `FVector`/`FRotator`, `Tick(float DeltaTime)`
- C++ 부모 클래스 → 에디터에서 블루프린트 자식 클래스 만들기 (값만 다른 변형 = 유니티 프리팹 변형)

**유니티/C#에서 건너오기**
- MonoBehaviour 스크립트 1개(.cs) ↔ `.h` + `.cpp` 한 쌍
- `Update()` + `Time.deltaTime` ↔ `Tick(float DeltaTime)`
- 프리팹·프리팹 변형 ↔ C++ 부모 + 블루프린트(BP) 자식 클래스

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/GameFramework/Actor.h` | `class AActor : public UObject` 선언부와 `BeginPlay`, `Tick` 선언 찾기 (지금은 '어디 있는지'만) |
| `Engine/Source/Runtime/Core/Public/Logging/LogMacros.h` | `UE_LOG` 매크로가 정의된 위치 확인 |

**✅ 과제**
- [ ] `구현` **[필수]** UE 프로젝트 `ActionArena` 만들고 GitHub Desktop으로 게임 저장소 올리기
    - 👣 **따라 하기: 게임 저장소 만들기 (UE 프로젝트 연결)**
        1. **프로젝트 만들기** — 언리얼 에디터: Games → Blank → C++ · Desktop · Scalable · Starter Content 끔 · 위치 `C:\Projects` · 이름 `ActionArena` → Create → Visual Studio와 에디터가 열리면 에디터는 한 번 닫기
        2. **LFS 설정 파일 넣기** — 아래 '파일 받기'로 `gitattributes.txt`를 받기 → 파일 탐색기 위쪽 `보기` → `표시` → `파일 확장명` 켜기 → 파일을 `C:\Projects\ActionArena`로 옮기고 이름을 `.gitattributes.`(**끝에 점 하나 더**)로 바꾸면 끝의 점이 사라지며 `.gitattributes`가 된다. `CLAUDE.md`도 같은 폴더에 넣기
        3. **저장소로 만들기** — GitHub Desktop `File` → `Add Local Repository…` → `Choose…`로 `ActionArena` 폴더 선택 → 안내 문구의 `create a repository` 클릭
        4. **만들기 창** — Name은 **그대로**(`ActionArena`) · Git Ignore는 `UnrealEngine` 선택 · README 체크 안 함 → `Create Repository` → Git LFS를 묻는 창이 뜨면 `Initialize Git LFS`
        5. **빠진 파일 확인** — 왼쪽 `Changes` 탭에 `Binaries`·`Intermediate`·`Saved`·`DerivedDataCache`가 **보이면 안 됨**(보이면 멈추고 질문). `Thumbs.db`·`desktop.ini` 같은 윈도우 파일이 보이면 우클릭 → `Ignore file`. 남은 파일이 있으면 Summary에 `chore: UE 5.8 프로젝트 생성` → `Commit to main`
        6. **GitHub에 올리기** — 위쪽 `Publish repository` → Name을 `UE5-ActionArena`로 바꾸고 `Keep this code private` 체크 해제 → `Publish Repository`
        7. **웹에서 정리 도구 켜기** — 브라우저에서 저장소 열기 → `Issues` → `Labels`(feat·bug·docs·perf), `Milestones`(M1~M6, 마감일 = 각 단계 마지막 주 일요일) → `Projects` → `New project` → Board
- [ ] `구현` **[필수]** `AFloatingItem` 액터: StaticMesh 컴포넌트 + Tick에서 사인파 상하 이동·회전. 속도·높이는 `UPROPERTY(EditAnywhere)`로 노출
    - 👣 **따라 하기: 첫 PR 해 보기**
        1. **오늘이 첫 PR** — 이 과제를 끝내면 오늘 카드의 **기록 ① Push → ② PR** 순서로 생애 첫 PR을 만든다
        2. **이슈 먼저 (선택)** — 브라우저에서 `UE5-ActionArena` → `Issues` → `New issue` → 제목 `AFloatingItem 액터 만들기` → `Submit new issue` → 번호(예: #1)를 PR 카드의 '이슈 번호'에 넣으면 합칠 때 이슈가 자동으로 닫힌다
        3. **이후 규칙** — 앞으로 과제를 끝낸 날마다 같은 순서로 PR을 남긴다. 올릴 변경이 없는 날은 카드의 '건너뛰기'
- [ ] `구현` **[필수]** BP 자식 `BP_FloatingItem` 3개를 서로 다른 값으로 레벨에 배치 (프리팹 변형과 비교해 TIL에 기록)
- [ ] `AI` **[필수]** AI가 만든 코드를 **한 줄도 빠짐없이 해설 주석**을 단 버전으로 다시 써서 학습 로그 저장소에 올리기 (레벨 L1)
- [ ] `학습` **[필수]** 컴파일 에러 3종을 일부러 내고 읽기: 세미콜론 누락, 선언-정의 시그니처 불일치, `#include` 누락 → 에러 원문 + 내 해석을 TIL에 기록
- [ ] `Git` **[필수]** PR 흐름 점검: 이번 주 PR마다 셀프 코멘트가 있는지, 이슈·마일스톤(M1)이 연결됐는지 GitHub 웹에서 확인하고 빠진 것 채우기 (이후 모든 기능을 이 흐름으로)
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** `FloatingItem.h/.cpp` · 해설 주석 버전 코드(학습 로그) · 첫 PR

**🏁 완료 기준(DoD)**
- AI 없이 `FloatingItem.h`의 각 줄이 무엇인지 말로 설명할 수 있다.
- 디테일 패널에서 값을 바꾸면 BP마다 다르게 움직인다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[C++] .h와 .cpp를 나누는 이유는?</summary>

선언(무엇이 있는지)과 정의(어떻게 동작하는지)를 분리. 다른 파일은 헤더만 `#include`해서 사용하므로 구현이 바뀌어도 재컴파일 범위가 줄어든다. C#은 컴파일러가 프로젝트 전체를 한 번에 보므로 분리가 필요 없다.
</details>

<details><summary>[UE 코어] AFloatingItem의 A, UStaticMeshComponent의 U는 무슨 의미인가?</summary>

A=AActor 파생(레벨에 배치 가능), U=UObject 파생. 그 밖에 F(구조체·일반 클래스), T(템플릿), E(열거형), I(인터페이스), b(bool). 엔진 빌드 도구가 접두사를 검사한다.
</details>

<details><summary>[C++] Mesh-&gt;SetRelativeLocation()에서 -&gt;와 .의 차이는?</summary>

`->`는 포인터가 가리키는 객체의 멤버에 접근(`(*Mesh).`와 같음), `.`은 객체(또는 참조) 자신의 멤버에 접근. C#은 참조 타입도 `.`만 쓴다.
</details>

<details><summary>[UE 코어] GENERATED_BODY()와 *.generated.h는 무엇인가?</summary>

UHT(Unreal Header Tool)가 리플렉션용 코드를 자동 생성하고, 그 코드를 클래스 안에 끼워 넣는 자리가 `GENERATED_BODY()`. `.generated.h` include는 항상 헤더의 마지막 include여야 한다.
</details>

**🤖 AI 프롬프트**
```text
나는 C#/유니티 2개월 차이고 C++은 처음이야. 아래 언리얼 C++ 코드(.h/.cpp)를 한 줄씩 C#과 비교해서 설명해줘. 특히 *, ->, ::, #include, UCLASS/UPROPERTY/GENERATED_BODY의 의미를 짚어주고, 마지막에 내가 이해했는지 확인할 질문 3개를 내줘. 정답은 내가 답한 뒤에 알려줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 UE 프로젝트 ActionArena 만들고 GitHub Desktop으로… · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제2 AFloatingItem 액터 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제3 BP 자식 BP_FloatingItem 3개를 서로 다른 값으로 레벨에 배… · 과제4 AI가 만든 코드를 한 줄도 빠짐없이 해설 주석을 단 버전으로 다시 써서… · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제5 컴파일 에러 3종을 일부러 내고 읽기 · 코테 · 자가 점검 · TIL
- Day 5 (금, 약 3시간): 과제6 PR 흐름 점검 · 코테 · 자가 점검 · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/floating-item`
- 남길 기록: 게임 저장소 `UE5-ActionArena` 만들기 + 첫 PR
- 남길 기록: 학습 로그: 해설 주석 버전 코드
- 주간 Devlog: `docs/devlog/W01.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** 같은 움직임을 Tick 대신 Timeline 컴포넌트로 구현해 보고 차이 기록

---

<a id="w02"></a>

#### W02 · 리플렉션 · UObject · GC

> 🎯 **목표:** 'C#에선 GC가 알아서 해줬는데, 언리얼에선 왜 `UPROPERTY()`를 빼먹으면 크래시가 나는가'를 **실험으로 증명**하고 첫 트러블슈팅 문서를 쓴다.

**🧩 C++ 생존 문법:** 스택 vs 힙, 포인터 vs 참조(`&`), `new`/`delete`와 메모리 누수, 댕글링 포인터, 'C# 참조 타입 = 자동 관리되는 포인터'라는 관점, `nullptr` 체크 습관

**핵심 개념**
- UHT 리플렉션: `UCLASS` · `UPROPERTY` · `UFUNCTION` · `USTRUCT` · `UENUM`이 엔진(에디터·블루프린트·GC·직렬화·네트워크)에 정보를 알려주는 방식
- `UPROPERTY` 지정자: `EditAnywhere` · `VisibleAnywhere` · `BlueprintReadWrite` · `Category` · `meta=(ClampMin=...)`
- UObject 생성 3종 구분: `NewObject`(일반 UObject) · `CreateDefaultSubobject`(생성자 안 컴포넌트) · `SpawnActor`(월드에 액터)
- GC 원리: 루트에서 **도달 가능한** UObject만 살아남고, `UPROPERTY`로 등록된 포인터가 그 '연결선'이다. `TObjectPtr`, `TWeakObjectPtr`, `IsValid()`
- 문자열 3종 `FString`/`FName`/`FText`, 컨테이너 첫 만남 `TArray`

**유니티/C#에서 건너오기**
- C# 값 타입/참조 타입 → C++은 '전부 기본이 값 타입', 참조가 필요하면 포인터(`*`)·참조(`&`)로 **명시**한다.
- C# `ref` 매개변수 ↔ C++ 참조 매개변수(`int& Value`)
- C#의 `List<T>` ↔ `TArray<T>`, `string` ↔ `FString`

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/CoreUObject/Public/UObject/ObjectMacros.h` | `namespace UP` 아래 `UPROPERTY` 지정자 목록과 각 주석 — 내가 쓴 지정자 3개 원문 찾기 |
| `Engine/Source/Runtime/CoreUObject/Public/UObject/ObjectPtr.h` | `TObjectPtr` 상단 주석: 왜 UE5에서 원시 포인터 대신 쓰는가 |
| `Engine/Source/Runtime/Core/Public/Containers/Array.h` | `Add` · `Emplace` · `Reserve` · `Num` — 용량(Slack)이 늘어나는 방식 |
| `Engine/Source/Runtime/Core/Public/UObject/NameTypes.h` | `FName`이 문자열 대신 무엇을 저장하는지(이름 테이블 인덱스) |

**✅ 과제**
- [ ] `학습` **[필수]** 순수 C++ 포인터 실험 3개(Visual Studio에서 C++ `콘솔 앱` 프로젝트를 만들어 Ctrl+F5로 실행): 값 전달 / 포인터 전달 / 참조 전달로 함수 안에서 값 바꾸기 + 주소 출력 → 지난번 C# `ref` TIL과 비교
- [ ] `구현` **[필수]** `AGCLabActor`로 'UPROPERTY가 없으면 GC가 지운다' 실험하기
    - UObject 멤버 2개 만들기 — 하나는 `UPROPERTY()`를 붙이고, 하나는 붙이지 않는다
    - 둘 다 `TWeakObjectPtr`로도 가리켜 둔다 (사라졌는지 관찰용)
    - ▶ Play 중 콘솔(📍 메뉴 위치 참고)에 `obj gc` 입력 → GC를 강제로 실행
    - `IsValid()` 결과를 로그로 찍어 어느 쪽이 사라졌는지 확인
    - TIL에 '수거된 객체를 원시 포인터로 건드리면 크래시나 메모리 오염이 생긴다'까지 기록
- [ ] `문서` **[필수]** **TS-001** 작성: 'UPROPERTY 누락 시 GC 수거' — 증상·재현·원인(도달성)·해결·재발 방지 (부록 템플릿)
- [ ] `구현` **[필수]** `UPROPERTY` 지정자 놀이터: 지정자 10개를 붙여 디테일 패널·블루프린트에서 차이 확인 → 표로 정리
- [ ] `구현` **[필수]** 프로젝트 로그 카테고리 정의(`DECLARE_LOG_CATEGORY_EXTERN`/`DEFINE_LOG_CATEGORY`) → 이후 모든 로그는 이 카테고리로
- [ ] `소스` **[필수]** `ObjectMacros.h`에서 내가 쓴 지정자 3개의 원문 주석을 찾아 TIL에 인용 + 내 말로 번역
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** TS-001 · UPROPERTY 지정자 표 · 프로젝트 로그 카테고리

**🏁 완료 기준(DoD)**
- UPROPERTY가 GC에 어떤 의미인지 그림 1장 + 3문장으로 설명할 수 있다.
- 실험 로그로 '등록 안 된 쪽만 수거됨'을 보여줄 수 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[C++] 포인터와 참조의 차이 3가지는?</summary>

포인터: 주소를 담는 변수, 다른 대상으로 바꿀 수 있고, `nullptr` 가능, `*`로 역참조. 참조: 기존 객체의 별칭, 선언 시 반드시 초기화, 대상을 바꿀 수 없고, null이 없다.
</details>

<details><summary>[C++] 스택과 힙의 차이는?</summary>

스택: 함수 지역 변수, 함수가 끝나면 자동 해제, 빠름, 크기 제한. 힙: `new` 등으로 동적 할당, 수명을 직접(또는 GC·스마트 포인터가) 관리, 상대적으로 느림.
</details>

<details><summary>[UE 코어] UPROPERTY 없는 UObject 포인터 멤버가 위험한 이유는?</summary>

GC는 리플렉션에 등록된 참조(UPROPERTY 등)만 따라가며 도달성을 판단한다. 등록 안 된 포인터만 붙잡고 있으면 수거 대상이 되고, 수거 후 그 포인터는 해제된 메모리를 가리키는 댕글링 포인터가 된다 → 접근 시 크래시.
</details>

<details><summary>[UE 코어] NewObject, CreateDefaultSubobject, SpawnActor의 차이는?</summary>

NewObject: 런타임에 일반 UObject 생성. CreateDefaultSubobject: 생성자 안에서 컴포넌트·서브오브젝트를 기본값으로 생성. SpawnActor: 월드에 액터 생성(액터는 NewObject로 만들지 않는다).
</details>

<details><summary>[UE 코어] FName/FString/FText는 각각 언제 쓰나?</summary>

FName: 불변·대소문자 무시·인덱스 비교라 빠름(식별자, 소켓 이름, 태그). FString: 가변 문자열(조작·로그). FText: 현지화되는 UI 표시용 문자열.
</details>

<details><summary>[UE 코어] TWeakObjectPtr은 언제 쓰나?</summary>

객체를 소유(생존 연장)하지 않고 관찰만 할 때(타깃, 캐시, 콜백). 대상이 사라지면 `IsValid()`가 false가 되어 댕글링을 막는다.
</details>

**🤖 AI 프롬프트**
```text
C#의 GC와 언리얼의 GC를 비교해서 설명해줘. 특히 UPROPERTY를 빼먹었을 때 객체가 수거되는 과정을 '루트 → 참조 그래프' 텍스트 그림으로 보여줘. 내가 직접 확인할 실험은 코드 말고 절차만 단계별로 알려줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 순수 C++ 포인터 실험 3개(Visual Studio에서 C++ 콘솔 앱… · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제6 ObjectMacros.h에서 내가 쓴 지정자 3개의 원문 주석을 찾아 T… · 과제5 프로젝트 로그 카테고리 정의(DECLARE_LOG_CATEGORY_EXTE… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제4 UPROPERTY 지정자 놀이터 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제2 AGCLabActor로 'UPROPERTY가 없으면 GC가 지운다' 실험하기 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제3 TS-001 작성 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · 자가 점검 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/gc-lab` · `feat/log-category`
- 남길 기록: `docs/troubleshooting/TS-001-uproperty-gc.md`
- 주간 Devlog: `docs/devlog/W02.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** `AddReferencedObjects`가 필요한 경우(UPROPERTY를 못 쓰는 컨테이너) 조사해 노트로 정리

---

<a id="w03"></a>

#### W03 · 액터·컴포넌트 생명주기 & 게임플레이 프레임워크

> 🎯 **목표:** 언리얼이 내 코드를 **언제·누가·어떤 순서로** 부르는지 콜스택으로 확인하고, 프로젝트 뼈대(GameMode·Controller·Character)를 C++로 세운다.

**🧩 C++ 생존 문법:** 상속(`: public AActor`), `virtual` / `override` / `final`, `Super::BeginPlay()`(C#의 `base.`), 생성자·소멸자, 접근 지정자(`public`/`protected`/`private`), 가상 함수가 '부모 타입으로 자식 함수 호출'을 가능하게 하는 원리(vtable은 개념만)

**핵심 개념**
- 액터 생명주기: 생성자(CDO 포함) → `PostInitializeComponents` → `BeginPlay` → `Tick` → `EndPlay` → (GC)
- 생성자에서는 컴포넌트 생성·기본값만. 월드·다른 액터 접근은 `BeginPlay`부터
- 컴포넌트 3층: `UActorComponent`(로직) · `USceneComponent`(위치·부착) · `UPrimitiveComponent`(렌더·충돌), `RootComponent`
- Tick 관리: `PrimaryActorTick.bCanEverTick`, `TickInterval`, `SetActorTickEnabled`
- 게임플레이 프레임워크: GameMode · GameState · PlayerController · Pawn/Character · PlayerState · HUD — 멀티플레이에서 '어느 컴퓨터에 존재하는지'도 미리 표시해 둔다(M4 대비)

**유니티/C#에서 건너오기**
- `Awake`/`Start`/`Update`/`OnDestroy` ↔ 생성자·`PostInitializeComponents`/`BeginPlay`/`Tick`/`EndPlay` (1:1이 아닌 부분이 CDO)
- GameObject + 여러 MonoBehaviour ↔ Actor + 여러 Component
- 유니티의 직접 만든 GameManager ↔ 엔진이 역할을 나눠 둔 GameMode/GameState

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/GameFramework/Actor.h` | `PostInitializeComponents` · `BeginPlay` · `EndPlay` · `Tick` 선언 위 주석 |
| `Engine/Source/Runtime/Engine/Private/Actor.cpp` | `AActor::DispatchBeginPlay`와 `AActor::BeginPlay` — 컴포넌트 BeginPlay와 블루프린트 BeginPlay가 어디서 호출되나 |
| `Engine/Source/Runtime/Engine/Classes/Components/SceneComponent.h` | `AttachToComponent`, 상대/월드 Transform |
| `Engine/Source/Runtime/Engine/Classes/GameFramework/GameModeBase.h` | `DefaultPawnClass`, `PlayerControllerClass`, `InitGame` |

**✅ 과제**
- [ ] `구현` **[필수]** `ALifecycleProbe`: 생명주기 함수를 전부 override해 `UE_LOG` → 실제 출력 순서 표 작성 + `BeginPlay` 중단점 콜스택 캡처
- [ ] `구현` **[필수]** 프로젝트 뼈대: `AArenaGameMode`, `AArenaPlayerController`, `AArenaCharacter`(빈 껍데기) C++ → BP 자식 → 프로젝트 설정에 지정
- [ ] `구현` **[필수]** W1의 둥둥 떠다니는 로직을 재사용 컴포넌트 `UFloatMotionComponent`로 분리 리팩터링 (어떤 액터에 붙여도 동작, Tick은 필요할 때만)
- [ ] `문서` **[필수]** 엔진 노트 `01-actor-lifecycle.md`: 콜스택 캡처 + 유니티 대응표 + 'Super를 빼먹으면?' 실험 결과
- [ ] `AI` **[필수]** AI '면접관 모드'로 생명주기 꼬리 질문 5개를 받고 내 답과 채점 결과를 기록
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 엔진 노트 01 · GameMode/Controller/Character 뼈대 · 재사용 컴포넌트

**🏁 완료 기준(DoD)**
- BeginPlay 콜스택을 보며 '월드 → … → AActor::BeginPlay' 흐름을 설명할 수 있다.
- GameMode 등 6개 클래스의 역할을 한 줄씩 말할 수 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[UE 코어] 생성자에서 GetWorld()나 다른 액터를 찾으면 안 되는 이유는?</summary>

생성자는 CDO(클래스 기본 객체)를 만들 때도 실행되고 월드에 배치되기 전이라 월드가 없을 수 있다. 생성자에선 컴포넌트 생성·기본값 설정만, 게임 로직은 BeginPlay에서.
</details>

<details><summary>[UE 코어] CDO란 무엇인가?</summary>

Class Default Object. 클래스마다 엔진이 만들어 두는 기본값 템플릿 객체. 새 인스턴스는 CDO 값을 복사해서 시작하고, BP 기본값 편집은 CDO를 수정하는 것이다.
</details>

<details><summary>[C++] virtual이 없으면 어떻게 되나? override는 왜 붙이나?</summary>

부모 타입 포인터로 호출하면 부모 함수가 불린다(정적 바인딩). `override`는 '재정의 의도'를 컴파일러에 알려 시그니처 오타를 컴파일 에러로 잡아준다.
</details>

<details><summary>[UE 코어] Super::BeginPlay()를 빼먹으면?</summary>

부모의 처리(컴포넌트 BeginPlay 호출, 블루프린트 BeginPlay 이벤트 등)가 실행되지 않아 '블루프린트 이벤트가 안 불린다' 같은 미묘한 버그가 생긴다.
</details>

<details><summary>[UE 코어] ActorComponent와 SceneComponent의 차이는?</summary>

ActorComponent: 위치 없는 로직(체력, 인벤토리). SceneComponent: Transform이 있어 부착·계층 가능(카메라 붐, 기준점). PrimitiveComponent: 렌더·충돌 가능(메시, 콜리전).
</details>

<details><summary>[게임플레이] GameMode와 GameState의 차이는?</summary>

GameMode는 규칙을 담당하고 서버에만 존재. GameState는 모두가 알아야 하는 게임 상태를 담고 모든 클라이언트로 복제된다.
</details>

<details><summary>[최적화] Tick 비용을 줄이는 방법 3가지는?</summary>

기본은 `bCanEverTick=false`, 필요할 때만 `SetActorTickEnabled`, `TickInterval`로 주기 낮추기, 타이머·델리게이트 이벤트로 대체.
</details>

**🤖 AI 프롬프트**
```text
AActor의 생명주기를 Unity MonoBehaviour와 표로 비교해줘. 1:1로 대응되지 않는 부분(CDO, PostInitializeComponents)은 왜 대응이 안 되는지 따로 설명하고, 엔진 소스에서 내가 직접 확인할 함수 이름 3개를 파일 경로와 함께 알려줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 ALifecycleProbe · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 프로젝트 뼈대 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 W1의 둥둥 떠다니는 로직을 재사용 컴포넌트 UFloatMotionComp… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 엔진 노트 01-actor-lifecycle.md · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 AI '면접관 모드'로 생명주기 꼬리 질문 5개를 받고 내 답과 채점 결과… · 자가 점검 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/game-framework` · `refactor/float-motion-component` · `feat/lifecycle-probe`
- 남길 기록: `docs/engine-notes/01-actor-lifecycle.md`
- 주간 Devlog: `docs/devlog/W03.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** `EndPlay`의 `EEndPlayReason` 값별로 언제 호출되는지 실험(레벨 전환, Destroy, PIE 종료)

---

<a id="w04"></a>

#### W04 · 캐릭터 · Enhanced Input · 3D 수학

🏁 **릴리즈:** v0.1.0 · 움직이는 캐릭터

> 🎯 **목표:** C++로 3인칭 캐릭터 조작(이동·시점·점프·달리기)을 완성하고, 내적·외적으로 **방향 판정**을 직접 구현해 시각화한다.

**🧩 C++ 생존 문법:** 템플릿 '읽는 법'(`TArray<int32>`, `Cast<AArenaCharacter>(Actor)`, `CreateDefaultSubobject<UCameraComponent>(TEXT("Camera"))`), const 참조 매개변수(`const FInputActionValue& Value`), `auto`, `TEXT()` 매크로

**핵심 개념**
- `ACharacter` = Capsule + SkeletalMesh + CharacterMovementComponent(CMC), SpringArm + Camera
- 컨트롤러 회전 vs 캐릭터 회전: `bUseControllerRotationYaw`, `bOrientRotationToMovement`
- Enhanced Input: InputAction(IA) · InputMappingContext(IMC) · Trigger/Modifier · `ETriggerEvent` · 로컬 플레이어 서브시스템에 IMC 추가
- 3D 수학: 벡터 정규화·길이, **내적**(앞/뒤·시야각) · **외적**(좌/우), `FRotator` vs `FQuat`(짐벌락), 로컬↔월드 좌표, UE 좌표계(왼손·Z-up·X-forward)

**유니티/C#에서 건너오기**
- Input System의 Action / Action Map ↔ InputAction / InputMappingContext
- CharacterController ↔ CharacterMovementComponent
- `Vector3.Dot` / `Vector3.Cross` ↔ `FVector::DotProduct` / `FVector::CrossProduct` (유니티 Y-up, 언리얼 Z-up)

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Plugins/EnhancedInput/Source/EnhancedInput/Public/EnhancedInputComponent.h` | `BindAction` 오버로드들 — 어떤 함수 형태를 바인딩할 수 있나 |
| `Engine/Plugins/EnhancedInput/Source/EnhancedInput/Public/EnhancedInputSubsystemInterface.h` | `AddMappingContext`의 우선순위(Priority) 매개변수 |
| `Engine/Source/Runtime/Engine/Classes/GameFramework/Character.h` | `Jump`, `GetCharacterMovement`, 기본 컴포넌트 구성 |
| `Engine/Source/Runtime/Core/Public/Math/Vector.h` | `DotProduct`, `CrossProduct`, `operator\|`, `operator^` |

**✅ 과제**
- [ ] `구현` **[필수]** `AArenaCharacter` 만들기: 카메라 + 마네킹 + 이동·시점·점프
    - `SpringArm`(카메라 붐) + `Camera` 컴포넌트 추가
    - 마네킹 확보: 콘텐츠 브라우저 `+ Add` → `Add Feature or Content Pack…` → `Third Person` → `Add to Project`
    - 입력 에셋 만들기: 콘텐츠 브라우저 빈 곳 우클릭 → `Input` → `Input Action` 3개(IA_Move·IA_Look·IA_Jump) + `Input Mapping Context` 1개
    - C++에서 이 에셋들을 `UPROPERTY`로 받고 `BindAction`으로 함수에 연결
    - BP 자식에서 에셋을 지정하고 ▶ Play로 이동·시점·점프 확인
- [ ] `구현` **[필수]** Sprint(Shift 누르는 동안 `MaxWalkSpeed` 변경) — 수치는 UPROPERTY로 노출하고 `// TODO(W8): 데이터 에셋으로 이전` 주석
- [ ] `구현` **[필수]** 방향 판정 디버그 액터: 플레이어 기준 대상이 앞/뒤(내적)·좌/우(외적)인지와 각도를 `DrawDebugLine`/`DrawDebugString`으로 표시 (W11 피격 방향 리액션에서 재사용)
- [ ] `문서` **[필수]** 엔진 노트 `02-enhanced-input.md`: 키 → IMC → IA → Trigger → 바인딩 함수 흐름도 + 유니티 Input System 비교
- [ ] `AI-Off` **[필수]** **월간 AI-Off 챌린지 ①:** 빈 액터에서 `AFloatingItem`을 AI 없이 30분 안에 다시 작성 → 성공/막힌 지점을 회고에 기록
- [ ] `Git` **[필수]** Milestone M1 종료 → GitHub Release **v0.1.0** + 20초 GIF + 월간 회고(KPT)
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** v0.1.0 릴리즈 · 엔진 노트 02 · 방향 판정 디버그 영상

**🏁 완료 기준(DoD)**
- 키보드·마우스로 이동·시점·점프·달리기가 동작한다.
- 방향 판정이 디버그 드로잉으로 정확히 표시된다.
- v0.1.0 릴리즈 페이지에 GIF와 변경 내역이 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[수학] 내적 결과가 음수라면 무슨 뜻인가?</summary>

두 벡터 사이 각이 90°보다 크다. 정규화된 Forward와 '대상 방향'의 내적이 음수면 대상이 뒤쪽. 값 자체가 cosθ라 시야각 판정에도 쓴다.
</details>

<details><summary>[수학] 외적으로 좌/우를 판정하는 방법은?</summary>

Forward × ToTarget 결과의 Z 성분 부호(UE는 Z-up)로 판단. 좌표계 손잡이에 따라 부호 해석이 달라지므로 디버그 드로잉으로 꼭 확인한다.
</details>

<details><summary>[수학] 쿼터니언을 쓰는 이유는?</summary>

오일러각의 짐벌락을 피하고, 회전 보간(Slerp)이 자연스럽고, 회전 합성이 안정적이다. 언리얼은 편집용 FRotator와 연산용 FQuat를 함께 쓴다.
</details>

<details><summary>[게임플레이] IMC를 여러 개 두는 이유는?</summary>

상황별 입력 세트(기본/UI/탈것)를 우선순위로 추가·제거해 컨텍스트를 전환하고, 같은 키를 상황마다 다른 의미로 재사용하기 위해.
</details>

<details><summary>[C++] const FInputActionValue&amp; Value에서 const와 &amp;의 의미는?</summary>

&: 복사 없이 원본을 참조로 전달(비용 절감). const: 함수 안에서 수정 금지. C#의 `in` 매개변수와 비슷하다.
</details>

**🤖 AI 프롬프트**
```text
Enhanced Input으로 이동/시점/점프를 C++로 바인딩하려고 해. 정답 코드는 주지 말고 ① 필요한 에셋 ② 헤더에 선언할 것 ③ cpp에서 할 일 ④ 흔한 실수를 단계별 체크리스트로만 줘. 내가 작성한 코드를 보여주면 그때 리뷰해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 AArenaCharacter 만들기 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 Sprint(Shift 누르는 동안 MaxWalkSpeed 변경) · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 방향 판정 디버그 액터 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 엔진 노트 02-enhanced-input.md · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 월간 AI-Off 챌린지 ① · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 릴리즈 · 월간 회고

**📒 이번 주 Git 기록**
- 브랜치: `feat/character-input` · `feat/sprint` · `feat/direction-debug`
- 남길 기록: `docs/engine-notes/02-enhanced-input.md`
- 남길 기록: `docs/retro/M1.md`
- 🏷 릴리즈: `v0.1.0` (🔔 알림 → 릴리즈)
- 주간 Devlog: `docs/devlog/W04.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Enhanced Input의 Modifier(데드존, 감도)와 Trigger(Hold, Tap) 실험

**🚪 M1 관문 — 다음 단계로 넘어가는 조건**

- [ ] v0.1.0 릴리즈(GIF 포함)
- [ ] TS-001 작성
- [ ] 엔진 노트 2편(생명주기, Enhanced Input)
- [ ] AI-Off 챌린지 ① 기록
- [ ] 코테 누적 20문제
- [ ] W1~W4 자가 점검 질문 70% 이상 답변

---

### M2 · 상호작용 & 전투 (W05~W08)

> **이 단계가 증명하는 것:** 결합도 낮은 설계(인터페이스·델리게이트)와 데이터 주도 설계를 할 줄 안다.  
> **릴리즈:** v0.2.0 콤보 전투 + 데이터 주도 무기 · **AI 레벨:** L1~L2 — 새 개념은 AI 초안+해설, 반복 패턴은 내가 먼저 작성  
> **코딩테스트(C++):** 정렬, 스택/큐/덱, 해시(unordered_map/set), 브루트포스 — 주 5문제

<a id="w05"></a>

#### W05 · 인터페이스 · 델리게이트 · 타이머 — 상호작용 시스템

> 🎯 **목표:** 문·아이템·레버를 **같은 방식으로** 다루는 상호작용 시스템을 인터페이스와 델리게이트로 만든다 — '결합도 낮은 설계'를 코드로 증명.

**🧩 C++ 생존 문법:** 순수 가상 함수 `= 0`과 추상 클래스(C# interface와 비교), 인터페이스 용도의 다중 상속, 함수 포인터 개념과 람다 `[this](){ }` 캡처(C# 람다·Action과 비교), '캡처한 this가 먼저 사라지면?'

**핵심 개념**
- `UInterface`/`IInterface` 이중 구조, `BlueprintNativeEvent` + `Execute_` 호출, `Implements<>()`
- 델리게이트 4종: 단일/멀티캐스트 × 일반/다이나믹, `AddDynamic` · `AddUObject` · `AddLambda` · `RemoveAll`
- `FTimerManager`(`SetTimer`/`ClearTimer`)로 Tick 대체, 트레이스(`LineTrace`/`SphereTrace`)로 포커스 대상 찾기
- 옵저버 패턴: '보내는 쪽은 받는 쪽을 모른다'

**유니티/C#에서 건너오기**
- C# `interface` ↔ `UInterface` + `IInterface`
- C# `event` / `Action` / `UnityEvent` ↔ 델리게이트
- 코루틴 / `InvokeRepeating` ↔ `FTimerManager`, `Physics.Raycast` ↔ `LineTraceSingleByChannel`

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/CoreUObject/Public/UObject/Interface.h` | `UInterface` 클래스와 사용 예 주석 |
| `Engine/Source/Runtime/Core/Public/Delegates/DelegateCombinations.h` | `DECLARE_DYNAMIC_MULTICAST_DELEGATE_*` 매크로 이름 규칙 |
| `Engine/Source/Runtime/Engine/Public/TimerManager.h` | `SetTimer` 오버로드, `FTimerHandle` |
| `Engine/Source/Runtime/Engine/Classes/Engine/World.h` | `LineTraceSingleByChannel`, `SweepSingleByChannel` |

**✅ 과제**
- [ ] `구현` **[필수]** `IInteractable`(`Interact`, `GetInteractionText`) — `BlueprintNativeEvent`로 C++·BP 모두 구현 가능하게
- [ ] `구현` **[필수]** `UInteractionComponent`: 0.1초 타이머로 카메라 전방 SphereTrace → 포커스 대상이 바뀌면 `OnFocusChanged` 브로드캐스트 (Tick 사용 금지)
- [ ] `구현` **[필수]** 상호작용 대상 3종: 문(열림/닫힘), 아이템 픽업, 레버 → 레버는 델리게이트로 문 여러 개와 연결 (레버는 문 클래스를 몰라야 함)
- [ ] `구현` **[필수]** `UHealthComponent` 초안: Health/MaxHealth, `OnHealthChanged`·`OnDeath` 다이나믹 멀티캐스트 델리게이트 (W8에서 데미지 파이프라인과 연결)
- [ ] `문서` **[필수]** **ADR-0001** '상호작용 감지: Tick vs 타이머 vs Overlap' 선택 근거
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** ADR-0001 · 상호작용 시스템 · HealthComponent 초안

**🏁 완료 기준(DoD)**
- 새 상호작용 대상을 추가할 때 `UInteractionComponent` 코드 수정이 0줄이다.
- 레버 1개로 문 2개가 동작한다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[UE 코어] 언리얼 인터페이스가 UInterface/IInterface 두 개인 이유는?</summary>

UInterface(U 클래스)는 리플렉션·블루프린트 등록용 빈 껍데기, IInterface는 실제 C++ 가상 함수 선언. 리플렉션 시스템이 UObject 기반이라 분리가 필요하다.
</details>

<details><summary>[UE 코어] Cast&lt;IInteractable&gt; 대신 Execute_Interact를 써야 하는 경우는?</summary>

블루프린트에서 인터페이스를 구현한 액터는 C++ Cast가 실패한다. `Implements<UInteractable>()`로 확인 후 `IInteractable::Execute_Interact(Actor, ...)`로 호출해야 C++·BP 구현 모두 동작한다.
</details>

<details><summary>[UE 코어] 다이나믹 델리게이트는 언제 쓰나?</summary>

블루프린트 노출·직렬화가 필요할 때. 리플렉션 기반이라 UFUNCTION 바인딩이 필요하고 일반 델리게이트보다 느리다. C++ 내부용이면 일반 델리게이트.
</details>

<details><summary>[C++] 람다에서 [this] 캡처가 위험한 경우는?</summary>

람다가 객체보다 오래 살 때(타이머·비동기 콜백) 이미 파괴된 this에 접근해 크래시. UE에선 `AddUObject`·`CreateWeakLambda`·`TWeakObjectPtr` 캡처로 수명 안전성을 확보한다.
</details>

<details><summary>[C++] C++ 추상 클래스와 C# 인터페이스의 차이는?</summary>

C++엔 interface 키워드가 없어 순수 가상 함수만 가진 클래스로 표현하고, 다중 상속으로 여러 개를 구현한다. 멤버 변수·구현을 가질 수도 있다.
</details>

<details><summary>[최적화] Tick 대신 타이머를 쓰는 기준은?</summary>

매 프레임 필요 없는 주기적 검사(0.1~1초)나 지연 실행은 타이머. 매 프레임 보간·물리 연동처럼 프레임 단위가 필요한 것만 Tick.
</details>

**🤖 AI 프롬프트**
```text
레버가 문을 직접 알지 못하게(결합도 낮게) 연결하는 방법을 언리얼 델리게이트로 설계하고 싶어. 설계 선택지 2~3개를 장단점 표로 비교해줘. 코드는 아직 주지 마.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 IInteractable(Interact, GetInteractionTex… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 UInteractionComponent · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 상호작용 대상 3종 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 UHealthComponent 초안 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 ADR-0001 '상호작용 감지 · 자가 점검 · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/interaction-system` · `feat/health-component`
- 남길 기록: `docs/adr/ADR-0001-interaction-detection.md`
- 주간 Devlog: `docs/devlog/W05.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** 상호작용 대상 하이라이트(Custom Depth + 포스트 프로세스 아웃라인)

---

<a id="w06"></a>

#### W06 · 애니메이션 C++ — AnimInstance & 로코모션

> 🎯 **목표:** 게임 로직 값(속도·방향·공중 여부)이 **C++ AnimInstance를 거쳐** 애니메이션으로 흘러가는 구조를 만든다.

**🧩 C++ 생존 문법:** const 멤버 함수(`float GetSpeed() const`), 멤버 캐싱(매 프레임 Cast 대신 초기화 때 1회), 스레드 기초(게임 스레드 vs 워커 스레드, 데이터 경쟁 개념)

**핵심 개념**
- Animation Blueprint 구조: EventGraph / AnimGraph, 부모 클래스를 C++ `UAnimInstance`로 지정
- `NativeInitializeAnimation`, `NativeUpdateAnimation`, (심화) `NativeThreadSafeUpdateAnimation` + Property Access
- 블렌드스페이스(속도·방향), 상태 머신(Idle/Move ↔ Jump/Fall/Land), 루트 모션 개념

**유니티/C#에서 건너오기**
- Animator Controller(파라미터·상태·트랜지션) ↔ AnimBP(변수·상태 머신·트랜지션 룰)
- 유니티: 스크립트가 `Animator.SetFloat`로 값을 '밀어 넣음' ↔ 언리얼: AnimInstance가 매 프레임 값을 '당겨옴'

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/Animation/AnimInstance.h` | `NativeInitializeAnimation`, `NativeUpdateAnimation`, `NativeThreadSafeUpdateAnimation`, `TryGetPawnOwner` |
| `Engine/Source/Runtime/AnimGraphRuntime/Public/KismetAnimationLibrary.h` | `CalculateDirection` — W4 내적·외적 계산과 비교 |

**✅ 과제**
- [ ] `구현` **[필수]** `UArenaAnimInstance`: Speed, Direction, bIsInAir, bIsAccelerating — Character·CMC 포인터는 초기화 때 캐싱
- [ ] `구현` **[필수]** AnimBP(부모=`UArenaAnimInstance`) + 로코모션 블렌드스페이스 + 점프 상태 머신
- [ ] `학습` **[필수]** `CalculateDirection` 결과를 W4에서 만든 내 각도 계산과 비교 → 같은 값이 나오는지 로그로 확인
- [ ] `문서` **[필수]** 엔진 노트 `03-anim-update.md`: 유니티 '밀어 넣기' vs 언리얼 '당겨오기' 구조 그림
- [ ] `구현` [심화] (심화) `NativeThreadSafeUpdateAnimation`으로 옮기고 Unreal Insights에서 게임 스레드 시간 비교
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 엔진 노트 03 · 로코모션 AnimBP

**🏁 완료 기준(DoD)**
- 걷기·달리기·점프·착지 전환이 자연스럽고, AnimBP 이벤트 그래프에 매 프레임 Cast가 없다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[애니메이션] AnimInstance에서 매 프레임 Cast하면 안 되는 이유는?</summary>

Cast는 비용이 있고 결과가 매 프레임 같다. 초기화 때 캐싱하고 유효성만 확인한다.
</details>

<details><summary>[애니메이션] NativeThreadSafeUpdateAnimation에서 하면 안 되는 것은?</summary>

워커 스레드에서 실행되므로 게임 스레드 객체의 상태 변경, 스레드 안전하지 않은 UObject 접근 금지. 미리 복사해 둔 값이나 Property Access로 읽기만 한다.
</details>

<details><summary>[C++] const 멤버 함수의 의미는?</summary>

그 함수가 객체 상태를 바꾸지 않는다는 약속. const 객체·const 참조에서도 호출할 수 있고, 실수로 값을 바꾸면 컴파일 에러가 난다.
</details>

<details><summary>[애니메이션] 루트 모션이란? 네트워크에서 주의점은?</summary>

애니메이션의 루트 뼈 이동을 캐릭터 실제 이동으로 쓰는 방식. 공격·회피 이동이 정확해진다. 멀티플레이에선 몽타주의 루트 모션만 안정적으로 지원되므로 'Root Motion from Montages Only'를 기본으로.
</details>

**🤖 AI 프롬프트**
```text
유니티 Animator에서 SetFloat로 값을 넣어주던 방식과 언리얼 AnimInstance가 NativeUpdateAnimation에서 값을 가져오는 방식을 비교해서, 장단점과 언리얼이 이 방식을 택한 이유(멀티스레드 업데이트 포함)를 설명해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 UArenaAnimInstance · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 AnimBP(부모=UArenaAnimInstance) + 로코모션 블렌드스… · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 CalculateDirection 결과를 W4에서 만든 내 각도 계산과 비… · 코테 · 자가 점검 · TIL
- Day 5 (금, 약 3시간): 과제4 엔진 노트 03-anim-update.md · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 (심화) NativeThreadSafeUpdateAnimation으로 옮기…(심화) · 보충 · 이번 주 문서 다듬기 · 커밋·Push · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/anim-instance`
- 남길 기록: `docs/engine-notes/03-anim-update.md`
- 주간 Devlog: `docs/devlog/W06.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Motion Matching 샘플 구경만 하기 (구현은 W21 후보) / Anim Layer 인터페이스로 무기별 애니메이션 레이어 분리

---

<a id="w07"></a>

#### W07 · 콤보 공격 — 몽타주 · 노티파이 · 히트 판정

> 🎯 **목표:** 입력 버퍼가 있는 3단 콤보와, **프레임이 떨어져도 새지 않는** 무기 히트 판정을 구현한다.

**🧩 C++ 생존 문법:** `TArray`/`TSet`/`TMap`(C# `List`/`HashSet`/`Dictionary`), 범위 기반 for(`for (AActor* Hit : HitActors)`), 해시 기반 중복 검사, 포인터를 키로 쓴다는 의미

**핵심 개념**
- AnimMontage: Section · Slot · `Montage_Play` · `Montage_JumpToSection` · `Montage_SetNextSection` · `OnMontageEnded`/`OnMontageBlendingOut`
- AnimNotify(한 시점) vs AnimNotifyState(구간: Begin → Tick → End)
- 콤보 입력 윈도우(입력 버퍼링), 판정 방식 비교(콜리전 Overlap vs 소켓 기반 Sweep 트레이스)
- 커스텀 콜리전 채널·프리셋(`DefaultEngine.ini`에 저장), 스윙당 중복 타격 방지(`TSet`), `DrawDebug` 시각화
- 전투 로직은 캐릭터가 아니라 `UCombatComponent`로 분리(책임 분리)

**유니티/C#에서 건너오기**
- Animation Event ↔ AnimNotify, StateMachineBehaviour의 Enter/Exit ↔ AnimNotifyState
- Layer Collision Matrix ↔ 콜리전 채널 + Block/Overlap/Ignore 응답

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/Animation/AnimMontage.h` | 섹션·슬롯 구조, `CompositeSections` |
| `Engine/Source/Runtime/Engine/Classes/Animation/AnimNotifies/AnimNotifyState.h` | `NotifyBegin`/`NotifyTick`/`NotifyEnd` 시그니처 |
| `Engine/Source/Runtime/Engine/Classes/Animation/AnimInstance.h` | `Montage_Play`, `Montage_JumpToSection`, `OnMontageEnded` |
| `Engine/Source/Runtime/Engine/Classes/Engine/HitResult.h` | `FHitResult`에 담기는 정보(ImpactPoint, ImpactNormal, BoneName…) |

**✅ 과제**
- [ ] `구현` **[필수]** `UCombatComponent`: 공격 입력 → 몽타주 섹션 기반 3단 콤보 (입력 윈도우 안의 입력만 다음 섹션 예약)
- [ ] `구현` **[필수]** `UAnimNotifyState_ComboWindow`, `UAnimNotifyState_HitWindow` C++ 작성
- [ ] `구현` **[필수]** 무기 소켓 2개(시작/끝) 기반 Sweep: 이전 프레임 위치 → 현재 위치를 이어서 판정(프레임 드랍 대응) + `TSet`으로 스윙당 1회 타격 + DrawDebug
- [ ] `구현` **[필수]** 커스텀 콜리전 채널 'Weapon' 추가 → PR에서 `Config/DefaultEngine.ini` diff로 확인
- [ ] `구현` **[필수]** 테스트 더미(샌드백) 액터 + HealthComponent 연결
- [ ] `문서` **[필수]** TS 1건: 콤보·판정 구현 중 버그(노티파이 누락, 중복 타격 등)
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 콤보·판정 시스템 · TS 1건 · 30FPS 판정 검증 영상

**🏁 완료 기준(DoD)**
- `t.MaxFPS 30`에서도 판정 누락이 없음을 디버그 영상으로 증명한다.
- 콤보 입력 윈도우 밖의 입력은 무시된다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[애니메이션] AnimNotify와 AnimNotifyState의 차이는?</summary>

Notify는 한 시점 이벤트(발소리, 이펙트), NotifyState는 Begin~End 구간이라 판정 활성 구간·콤보 입력 구간에 적합하다.
</details>

<details><summary>[애니메이션] 판정을 노티파이에만 의존하면 생길 수 있는 문제는?</summary>

몽타주 중단·블렌드아웃 경계, 메시가 화면 밖이라 애니메이션 틱이 생략되는 설정, 극단적 저프레임에서 시작/종료 처리가 꼬일 수 있다. 몽타주 종료 콜백에서도 판정 상태를 정리하는 안전장치를 둔다.
</details>

<details><summary>[게임플레이] Overlap 판정과 Trace(Sweep) 판정의 장단점은?</summary>

Overlap: 설정이 간단하고 이벤트 기반이지만 빠른 무기는 프레임 사이를 통과(터널링)할 수 있다. Sweep: 구간을 연속으로 검사해 정확하지만 직접 호출하고 관리해야 한다.
</details>

<details><summary>[C++] 중복 검사에 TArray::Contains와 TSet 중 무엇이 나은가?</summary>

TArray.Contains는 선형 탐색 O(n), TSet은 해시 기반 평균 O(1). 요소가 많거나 검사가 잦으면 TSet.
</details>

<details><summary>[게임플레이] Object Channel과 Trace Channel의 차이는?</summary>

Object Channel은 액터(컴포넌트) 자신의 '종류', Trace Channel은 트레이스 쿼리에 쓰는 채널. 각 컴포넌트가 채널마다 Block/Overlap/Ignore 응답을 가진다.
</details>

**🤖 AI 프롬프트**
```text
3단 콤보에서 '입력 버퍼링'을 구현하는 대표 방식 2가지(노티파이 윈도우 방식 vs 입력 큐 방식)를 비교해줘. 섹션 전환에 쓰는 함수 이름만 알려주고, 엣지 케이스(공격 중 피격, 몽타주 중단)를 체크리스트로 줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 UCombatComponent · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 UAnimNotifyState_ComboWindow, UAnimNotify… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 무기 소켓 2개(시작/끝) 기반 Sweep · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 커스텀 콜리전 채널 'Weapon' 추가 → PR에서 Config/Defa… · 과제5 테스트 더미(샌드백) 액터 + HealthComponent 연결 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제6 TS 1건 · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/combo-system` · `feat/weapon-sweep`
- 남길 기록: `docs/troubleshooting/TS-002-<증상>.md`
- 주간 Devlog: `docs/devlog/W07.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** 히트 시 짧은 히트스톱(W20에서 본격) 프로토타입

---

<a id="w08"></a>

#### W08 · 데미지 파이프라인 & 데이터 주도 설계

🏁 **릴리즈:** v0.2.0 · 콤보 전투 + 데이터 주도 무기

> 🎯 **목표:** 수치를 코드에서 몰아내고(DataAsset/DataTable), **'코드 수정 0줄로 무기 추가'**가 가능한 구조를 만든다.

**🧩 C++ 생존 문법:** struct vs class(기본 접근 지정자 차이), `USTRUCT(BlueprintType)`, `enum class`/`UENUM`, 큰 구조체를 값으로 넘길 때의 복사 비용 → `const&` 전달

**핵심 개념**
- `UGameplayStatics::ApplyPointDamage` → `AActor::TakeDamage` → `OnTakeAnyDamage`/`OnTakePointDamage`, `UDamageType`
- HealthComponent가 소유 액터의 데미지 이벤트를 구독하는 구조
- `UPrimaryDataAsset`(캐릭터 스탯·무기 데이터), `UDataTable` + `FTableRowBase`(CSV 임포트 — 기획 협업), Primary Asset ID/Asset Manager 개념
- 매직 넘버 제거, 사망 처리(래그돌/몽타주 + 타이머 Destroy), GameplayTags 첫 도입(`State.Dead` — GAS 대비)

**유니티/C#에서 건너오기**
- ScriptableObject ↔ `UDataAsset`/`UPrimaryDataAsset`
- CSV·JSON 테이블 직접 파싱 ↔ DataTable(에디터 임포트 내장)
- `SendMessage("TakeDamage")` ↔ `ApplyDamage` / `TakeDamage`

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/Kismet/GameplayStatics.h` | `ApplyDamage`, `ApplyPointDamage` 매개변수 |
| `Engine/Source/Runtime/Engine/Private/Actor.cpp` | `AActor::TakeDamage` 구현에서 `OnTakeAnyDamage`가 브로드캐스트되는 위치 |
| `Engine/Source/Runtime/Engine/Classes/Engine/DataAsset.h` | `UPrimaryDataAsset::GetPrimaryAssetId` |
| `Engine/Source/Runtime/Engine/Classes/Engine/DataTable.h` | `FindRow`, `GetAllRows` |

**✅ 과제**
- [ ] `구현` **[필수]** `UCharacterStatData`(PrimaryDataAsset): MaxHealth, WalkSpeed, SprintSpeed, JumpZVelocity → 캐릭터 초기화 때 적용 (W4 TODO 해결)
- [ ] `구현` **[필수]** `UWeaponData`: 데미지 배율·콤보 몽타주·소켓 이름·판정 반경·메시 → **무기 2종을 데이터만으로 추가**
- [ ] `구현` **[필수]** 데미지 파이프라인: 판정 → `ApplyPointDamage` → HealthComponent → 사망(태그 `State.Dead`, 입력 차단, 래그돌, 5초 뒤 Destroy)
- [ ] `구현` **[필수]** 적 스탯 DataTable(CSV 임포트) — 스프레드시트에서 수정 → 재임포트 흐름 체험
- [ ] `문서` **[필수]** **ADR-0002** 'DataAsset vs DataTable 선택 기준'
- [ ] `AI-Off` **[필수]** **월간 AI-Off 챌린지 ②:** `IInteractable` + 문 상호작용을 AI 없이 60분 안에 재구현
- [ ] `Git` **[필수]** Release **v0.2.0** + 45초 영상(디버그 판정 ON) + 월간 회고
- [ ] `코테` **[필수]** 5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** v0.2.0 · ADR-0002 · 데이터만 바꾼 무기 추가 PR(.h/.cpp 변경 0)

**🏁 완료 기준(DoD)**
- 무기 추가 PR의 diff에 `.h`/`.cpp` 변경이 없다 — 이 PR 링크가 포트폴리오의 근거가 된다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[설계] DataAsset과 DataTable은 언제 각각 쓰나?</summary>

DataAsset: 객체 단위 데이터(무기 1개 = 에셋 1개), 다른 에셋 참조·상속·에디터 편집이 편하다. DataTable: 같은 구조의 행이 많은 데이터(적 스탯 100종), CSV·스프레드시트 연동에 강하다.
</details>

<details><summary>[UE 코어] TakeDamage를 오버라이드할 때 Super를 호출해야 하는 이유는?</summary>

부모 구현이 OnTakeAnyDamage/OnTakePointDamage 델리게이트 브로드캐스트 등 기본 처리를 한다. 빼먹으면 구독자(HealthComponent 등)에 이벤트가 가지 않는다.
</details>

<details><summary>[설계] 데이터 주도 설계의 협업상 이점은?</summary>

기획자가 빌드 없이 밸런스를 수정하고, 프로그래머는 로직에 집중하며, 변경 이력이 데이터 단위로 분리되고, 테스트용 데이터 세트 교체가 쉽다.
</details>

<details><summary>[C++] C++에서 struct와 class의 차이는?</summary>

기본 접근 지정자만 다르다(struct=public, class=private). 언리얼 관례상 USTRUCT는 가벼운 값 타입 데이터 묶음(GC 대상 아님), UCLASS는 UObject.
</details>

<details><summary>[C++] 큰 구조체를 값으로 넘기면 무엇이 문제인가?</summary>

호출마다 복사 비용. const 참조로 넘긴다. 반대로 int·float처럼 작은 값은 값 전달이 낫다.
</details>

**🤖 AI 프롬프트**
```text
내 무기 시스템을 DataAsset으로 분리하려고 해. 아래 하드코딩된 값 목록을 보고 (1) 데이터로 뺄 값 (2) DataAsset/DataTable 중 맞는 쪽 (3) 데이터가 잘못 입력됐을 때 방어 코드 위치를 표로 제안해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 UCharacterStatData(PrimaryDataAsset) · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 UWeaponData · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 데미지 파이프라인 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 적 스탯 DataTable(CSV 임포트) · 과제5 ADR-0002 'DataAsset vs DataTable 선택 기준' · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제6 월간 AI-Off 챌린지 ② · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 릴리즈 · 월간 회고

**📒 이번 주 Git 기록**
- 브랜치: `feat/data-assets` · `feat/damage-pipeline` · `feat/second-weapon-data-only`
- 남길 기록: `docs/adr/ADR-0002-dataasset-vs-datatable.md`
- 남길 기록: `docs/retro/M2.md`
- 🏷 릴리즈: `v0.2.0` (🔔 알림 → 릴리즈)
- 주간 Devlog: `docs/devlog/W08.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Asset Manager에 PrimaryAssetType 등록 후 ID로 무기 목록 조회

**🚪 M2 관문 — 다음 단계로 넘어가는 조건**

- [ ] v0.2.0 릴리즈(45초 영상)
- [ ] 코드 변경 0줄로 무기 추가한 PR
- [ ] TS 누적 2건
- [ ] ADR 2건
- [ ] AI-Off 챌린지 ② 기록
- [ ] 코테 누적 40문제

---

### M3 · UI · AI · 게임 루프 (W09~W12)

> **이 단계가 증명하는 것:** 메모리를 의식하고(소프트 레퍼런스), 디버깅 도구로 근거를 제시하며, 한 판짜리 게임을 완성한다.  
> **릴리즈:** (v0.3.0 준비) · **AI 레벨:** L2 — 내가 먼저 작성하고 AI가 리뷰  
> **코딩테스트(C++):** 재귀, DFS/BFS, 그래프 탐색 — 주 4~5문제

<a id="w09"></a>

#### W09 · UI(UMG) & 비동기 로딩

> 🎯 **목표:** Tick 없는 **이벤트 기반 HUD**를 만들고, 무기 에셋을 '필요할 때만' 비동기로 불러와 메모리 차이를 **수치로** 보여준다.

**🧩 C++ 생존 문법:** `TSharedPtr`/`TSharedRef`/`TWeakPtr`(UObject가 아닌 객체용) vs `TObjectPtr`/`TWeakObjectPtr`(UObject용), `std::shared_ptr` 개념 대응, 비동기 콜백 시점에 객체가 이미 파괴된 경우, 람다에 약한 포인터 캡처

**핵심 개념**
- C++ 부모 `UUserWidget` + `meta=(BindWidget)`, `NativeConstruct`/`NativeDestruct`
- UI 갱신은 델리게이트로(Property Binding·Tick 지양), 위젯 소유자(PlayerController/HUD)
- 하드 vs 소프트 레퍼런스(`TSoftObjectPtr`, `TSoftClassPtr`), Reference Viewer·Size Map
- `UAssetManager::GetStreamableManager().RequestAsyncLoad` + `FStreamableHandle`, 로딩 완료 콜백

**유니티/C#에서 건너오기**
- Canvas/UGUI ↔ UMG
- `Resources.Load` ↔ 동기 로드(`LoadSynchronous`), Addressables ↔ 소프트 레퍼런스 + StreamableManager

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/UMG/Public/Blueprint/UserWidget.h` | `NativeConstruct`, `BindWidget` 관련 주석 |
| `Engine/Source/Runtime/Engine/Classes/Engine/StreamableManager.h` | `RequestAsyncLoad` 오버로드, `FStreamableHandle`의 역할 |
| `Engine/Source/Runtime/Engine/Classes/Engine/AssetManager.h` | `GetStreamableManager` |
| `Engine/Source/Runtime/CoreUObject/Public/UObject/SoftObjectPtr.h` | `TSoftObjectPtr`이 실제로 저장하는 것(경로) |

**✅ 과제**
- [ ] `구현` **[필수]** HUD 위젯 C++ 부모 `UArenaHUDWidget` + BP 레이아웃: 체력·스태미나 바, 상호작용 프롬프트(W5 `OnFocusChanged` 구독)
- [ ] `구현` **[필수]** 모든 UI 갱신을 델리게이트 이벤트로 (Tick·Property Binding 0개)
- [ ] `구현` **[필수]** `UWeaponData`의 메시·몽타주를 `TSoftObjectPtr`로 전환 → 무기 교체 시 `RequestAsyncLoad` → 완료 콜백에서 장착 (콜백 시점에 캐릭터가 죽었으면? 약한 포인터 확인)
- [ ] `문서` **[필수]** 성능 노트 `perf/01-soft-reference.md`: Size Map 전/후 스크린샷 + 수치
- [ ] `구현` [심화] (심화) 데미지 숫자 팝업 위젯
- [ ] `코테` **[필수]** 4~5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 이벤트 기반 HUD · Size Map 전/후 수치

**🏁 완료 기준(DoD)**
- Size Map에서 캐릭터 BP의 참조 메모리가 줄어든 수치를 기록했고, 무기 교체 시 멈칫(히치)이 없다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[UI·에셋] UI를 Tick이나 Property Binding으로 갱신하면 문제는?</summary>

값이 안 바뀌어도 매 프레임 평가된다. 위젯이 많아지면 게임 스레드 비용이 커진다. 이벤트(델리게이트) 기반이면 바뀔 때만 갱신한다.
</details>

<details><summary>[UI·에셋] 하드 레퍼런스가 메모리를 키우는 이유는?</summary>

하드 참조된 에셋은 참조한 쪽이 로드될 때 함께 로드되고, 그 에셋이 참조하는 것도 연쇄로 로드된다(참조 체인). BP 하나가 수백 MB를 끌고 올 수 있다.
</details>

<details><summary>[UI·에셋] 비동기 로드 완료 콜백에서 주의할 점은?</summary>

요청한 객체가 그 사이 파괴됐을 수 있으니 약한 포인터로 확인한다. 핸들을 유지하지 않고 다른 참조도 없으면 로드된 에셋이 다시 GC될 수 있다.
</details>

<details><summary>[C++] TSharedPtr과 TObjectPtr은 각각 언제 쓰나?</summary>

TSharedPtr: UObject가 아닌 일반 C++ 객체의 참조 카운팅. UObject는 GC가 관리하므로 TSharedPtr에 넣지 않고 UPROPERTY TObjectPtr/TWeakObjectPtr을 쓴다.
</details>

<details><summary>[C++] shared_ptr 순환 참조란?</summary>

두 객체가 서로를 shared로 가리키면 참조 카운트가 0이 되지 않아 누수. 한쪽을 weak으로 바꿔 끊는다.
</details>

**🤖 AI 프롬프트**
```text
TSoftObjectPtr과 FStreamableManager로 무기 메시를 비동기 로드하는 흐름을 '요청 → 로딩 중 → 완료 콜백 → 장착' 순서도로 설명하고, 단계별로 생길 수 있는 버그(객체 파괴, 중복 요청, 핸들 해제)를 표로 정리해줘. 코드는 내가 쓸게.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 HUD 위젯 C++ 부모 UArenaHUDWidget + BP 레이아웃 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 모든 UI 갱신을 델리게이트 이벤트로 (Tick·Property Bindi… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 UWeaponData의 메시·몽타주를 TSoftObjectPtr로 전환 →… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 성능 노트 perf/01-soft-reference.md · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 (심화) 데미지 숫자 팝업 위젯(심화) · 보충 · 이번 주 문서 다듬기 · 커밋·Push · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/hud` · `perf/soft-weapon-refs`
- 남길 기록: `docs/perf/01-soft-reference.md`
- 주간 Devlog: `docs/devlog/W09.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** UMG MVVM(Model-View-ViewModel) 플러그인으로 HUD 하나 재작성해 보고 비교

---

<a id="w10"></a>

#### W10 · AI ① — AIController · Behavior Tree

> 🎯 **목표:** 플레이어와 적이 **공통 베이스를 공유**하도록 리팩터링하고, C++ 태스크로 움직이는 근접 적 AI를 만든다.

**🧩 C++ 생존 문법:** 공통 부모 추출 리팩터링(`AArenaCharacterBase`), `protected` 활용, 가상 함수로 '다른 부분만' 재정의, `enum class` 상태로 생각하기

**핵심 개념**
- `AAIController`, Possess, NavMesh(NavMeshBoundsVolume, 뷰포트에서 `P`로 확인), MoveTo
- Behavior Tree: Selector / Sequence, Task, Decorator, Service, Blackboard
- C++ BTTask(`ExecuteTask`, 지연 태스크 → `FinishLatentTask`, `AbortTask`), BTService(`TickNode`), Observer Aborts
- 참고: StateTree — UE5에서 범용 로직용으로 확장 중인 상태 머신 도구(W21 비교 후보)

**유니티/C#에서 건너오기**
- NavMeshAgent.SetDestination ↔ AIController MoveTo
- 유니티는 BT가 기본 기능이 아님(에셋 스토어) ↔ 언리얼은 엔진 내장 + 디버거 제공

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/AIModule/Classes/AIController.h` | `MoveToActor`, `OnMoveCompleted`, `RunBehaviorTree` |
| `Engine/Source/Runtime/AIModule/Classes/BehaviorTree/BTTaskNode.h` | `ExecuteTask`, `AbortTask`, `EBTNodeResult` |
| `Engine/Source/Runtime/AIModule/Classes/BehaviorTree/BTService.h` | `TickNode`, Interval |
| `Engine/Source/Runtime/AIModule/Classes/BehaviorTree/BlackboardComponent.h` | `SetValueAsObject`, `GetValueAsVector` |

**✅ 과제**
- [ ] `구현` **[필수]** 리팩터링: `AArenaCharacterBase`(Health·Combat 컴포넌트, 사망 처리) ← `AArenaPlayerCharacter`, `AArenaEnemy` — PR에 Before/After 클래스 다이어그램
- [ ] `구현` **[필수]** 근접 적 BT: 순찰(랜덤 지점) → 플레이어 추적 → 사거리 안이면 공격 → 쿨다운
- [ ] `구현` **[필수]** `UBTTask_MeleeAttack`(C++): CombatComponent 재사용, 몽타주가 끝나면 `FinishLatentTask`
- [ ] `구현` **[필수]** `UBTService_UpdateTargetDistance`(C++)
- [ ] `문서` **[필수]** 엔진 노트 `04-behavior-tree.md`: 내 BT 구조 그림 + 노드별 역할
- [ ] `코테` **[필수]** 4~5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 공통 베이스 리팩터링 PR · 근접 적 AI · 엔진 노트 04

**🏁 완료 기준(DoD)**
- 플레이어·적이 같은 데미지 파이프라인을 쓰고, 버그 수정이 한 곳에서 끝난다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[AI] Selector와 Sequence의 차이는?</summary>

Selector: 자식 중 하나라도 성공하면 성공(우선순위 선택). Sequence: 자식이 모두 순서대로 성공해야 성공(하나 실패 시 중단).
</details>

<details><summary>[AI] Latent(지연) Task는 어떻게 동작하나?</summary>

ExecuteTask에서 InProgress를 반환하고, 몽타주 등 작업이 끝나면 FinishLatentTask로 결과를 통보한다. 중단될 때를 위해 AbortTask도 처리해야 한다.
</details>

<details><summary>[AI] Observer Aborts는 무엇인가?</summary>

데코레이터 조건이 바뀌면 실행 중인 브랜치를 중단시키는 설정(Self / Lower Priority / Both). 예: 플레이어를 발견하면 순찰을 즉시 중단.
</details>

<details><summary>[설계] 공통 베이스 클래스로 리팩터링한 이유는?</summary>

체력·전투·사망 로직 중복 제거, 플레이어와 적이 같은 데미지 파이프라인을 써서 버그 수정이 한 곳에서 끝난다. 차이는 가상 함수로만 재정의.
</details>

<details><summary>[AI] Behavior Tree와 StateTree의 차이는?</summary>

BT: 조건 평가·우선순위 기반 의사결정 트리, 기존 프로젝트에 많다. StateTree: 상태 머신과 셀렉터를 합친 구조로 UE5에서 범용 로직용으로 확장 중. 실무에선 둘 다 만날 수 있다.
</details>

**🤖 AI 프롬프트**
```text
내 적 AI의 요구사항(순찰/추적/공격/쿨다운)을 Behavior Tree로 설계하려고 해. 노드 트리를 텍스트 다이어그램으로 제안하고, 어떤 노드를 C++로 만들고 어떤 건 기본 노드를 쓸지 이유와 함께 표로 정리해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 리팩터링 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 근접 적 BT · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 UBTTask_MeleeAttack(C++) · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 UBTService_UpdateTargetDistance(C++) · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 엔진 노트 04-behavior-tree.md · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `refactor/character-base` · `feat/melee-enemy-ai`
- 남길 기록: `docs/engine-notes/04-behavior-tree.md`
- 주간 Devlog: `docs/devlog/W10.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** 같은 적을 StateTree로도 만들어 구조 비교 (W21-B로 확장 가능)

---

<a id="w11"></a>

#### W11 · AI ② — Perception · 원거리 적 · 디버깅 도구

> 🎯 **목표:** 보고·반응하는 적 2종을 만들고, '왜 AI가 이렇게 행동했는지'를 **디버깅 도구로 증명**한다.

**🧩 C++ 생존 문법:** (복습 주간) 포인터 유효성 검사 습관, 함수 길이·이름 짓기 — AI 코드 리뷰를 'Epic 코딩 표준' 기준으로 받아 보기

**핵심 개념**
- `UAIPerceptionComponent`(Sight·Hearing·Damage), `OnTargetPerceptionUpdated`, 팀 구분(`IGenericTeamAgentInterface`)
- 원거리 적 + `UProjectileMovementComponent`
- 피격 반응: 경직·넉백·방향별 히트 리액션 — W4 내적/외적 재사용
- Gameplay Debugger(`'` 키), Visual Logger(`UE_VLOG`), (심화) EQS로 공격 위치 선정

**유니티/C#에서 건너오기**
- `Physics.OverlapSphere` + Raycast로 직접 만들던 시야 체크 ↔ AI Perception 내장

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/AIModule/Classes/Perception/AIPerceptionComponent.h` | `OnTargetPerceptionUpdated`, 감각 설정 |
| `Engine/Source/Runtime/AIModule/Classes/GenericTeamAgentInterface.h` | `GetGenericTeamId`, 팀 태도(Attitude) |
| `Engine/Source/Runtime/Engine/Classes/GameFramework/ProjectileMovementComponent.h` | `InitialSpeed`, `bRotationFollowsVelocity`, 바운스·호밍 |

**✅ 과제**
- [ ] `구현` **[필수]** 근접 적에 Perception(시야 + 피격 감지) → 감지/상실 시 Blackboard 갱신 (W10의 '항상 플레이어 추적' 제거)
- [ ] `구현` **[필수]** 원거리 적: 거리 유지 + 투사체 발사 — 스탯은 DataTable 행 추가로 (W8 구조 재사용)
- [ ] `구현` **[필수]** 피격 방향 리액션: W4 내적/외적으로 앞/뒤/좌/우 히트 몽타주 선택
- [ ] `문서` **[필수]** Visual Logger로 AI 의사결정을 녹화 → 버그 1건을 찾아 TS 문서(녹화 화면 근거)
- [ ] `문서` **[필수]** 디버깅 도구 비교 노트: Gameplay Debugger vs Visual Logger vs DrawDebug vs 중단점
- [ ] `코테` **[필수]** 4~5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 적 2종 · Visual Logger 근거 TS · 디버깅 도구 노트

**🏁 완료 기준(DoD)**
- AI 의사결정 버그 1건을 Visual Logger 화면을 근거로 설명한 TS 문서가 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[AI] AI 시야 감지가 안 될 때 확인 순서는?</summary>

Gameplay Debugger로 Perception 표시 → 시야 반경·각도 → 소속 감지 설정(팀 인터페이스가 없으면 모두 '중립'이라 중립 감지를 켜야 함) → 자극 소스 등록 → 시야 트레이스를 막는 콜리전.
</details>

<details><summary>[AI] Gameplay Debugger와 Visual Logger의 차이는?</summary>

Gameplay Debugger: 지금 이 순간 상태를 화면에 오버레이. Visual Logger: 시간축으로 녹화해 과거 프레임의 판단·위치를 되감아 분석.
</details>

<details><summary>[게임플레이] 투사체를 Tick 이동 대신 ProjectileMovementComponent로 만드는 이유는?</summary>

속도·중력·바운스·호밍이 내장돼 있고 충돌을 고려한 이동을 하며, 네트워크 보간 기능도 제공한다. 직접 구현할 버그를 줄인다.
</details>

**🤖 AI 프롬프트**
```text
AI Perception으로 시야 감지가 안 되는 문제를 디버깅하고 있어. 가능한 원인을 확률 높은 순으로 5개, 각각 에디터/콘솔에서 확인하는 방법을 알려줘. 해결 코드는 확인한 뒤에 물어볼게.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 근접 적에 Perception(시야 + 피격 감지) → 감지/상실 시 Bl… · 코테 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 원거리 적 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 피격 방향 리액션 · 코테 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 Visual Logger로 AI 의사결정을 녹화 → 버그 1건을 찾아 TS… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 디버깅 도구 비교 노트 · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/ai-perception` · `feat/ranged-enemy` · `feat/hit-reaction`
- 남길 기록: `docs/troubleshooting/TS-003-<증상>.md`
- 주간 Devlog: `docs/devlog/W11.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** EQS로 '플레이어가 보이면서 거리 유지되는 지점' 찾기

---

<a id="w12"></a>

#### W12 · 게임 루프 — 웨이브 · Subsystem · 오브젝트 풀 · 세이브

> 🎯 **목표:** '시작 → 웨이브 → 휴식 → 게임오버 → 기록 저장'이 도는 **한 판짜리 게임 루프**를 완성한다.

**🧩 C++ 생존 문법:** 싱글턴 대신 수명이 명확한 Subsystem, 재사용 객체의 '상태 리셋 함수' 설계

**핵심 개념**
- GameMode(규칙) / GameState(공유 상태) 분리 — 웨이브 번호·남은 적 수는 GameState에 (M4 멀티 대비)
- 웨이브 구성 DataTable, 스포너, 게임 상태 `enum class EArenaPhase`
- Subsystem 수명: Engine / GameInstance / World / LocalPlayer
- 오브젝트 풀(WorldSubsystem으로 투사체 풀) — **측정 후 결정** 원칙
- `USaveGame`(최고 기록·설정), `AsyncSaveGameToSlot`, 메인 메뉴·일시정지·게임오버 UI, `OpenLevel`

**유니티/C#에서 건너오기**
- 싱글턴 GameManager + DontDestroyOnLoad ↔ GameInstance Subsystem
- PlayerPrefs ↔ USaveGame, `UnityEngine.Pool` ↔ 직접 구현한 풀 Subsystem

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/GameFramework/GameStateBase.h` | `PlayerArray`, 복제되는 상태 |
| `Engine/Source/Runtime/Engine/Classes/GameFramework/SaveGame.h` | `USaveGame` — 무엇이 저장되나(UPROPERTY 직렬화) |
| `Engine/Source/Runtime/Engine/Classes/Kismet/GameplayStatics.h` | `SaveGameToSlot`, `AsyncSaveGameToSlot`, `LoadGameFromSlot` |
| `Subsystems/WorldSubsystem.h (Engine 모듈 — Visual Studio Ctrl+T로 파일명 검색)` | `ShouldCreateSubsystem`, `Initialize`/`Deinitialize` |

**✅ 과제**
- [ ] `구현` **[필수]** 게임 흐름 `EArenaPhase`(Waiting/InWave/Break/GameOver) — GameMode가 전환하고 GameState가 보관
- [ ] `구현` **[필수]** 웨이브 구성 DataTable(웨이브별 적 종류·수·간격) + 스포너
- [ ] `구현` **[필수]** `UProjectilePoolSubsystem`(WorldSubsystem): 투사체 재사용 + 반환 시 상태 리셋 → Unreal Insights로 '스폰 vs 풀' 비용 수치 기록
- [ ] `구현` **[필수]** 메인 메뉴 / 일시정지 / 게임오버 UI + 최고 웨이브 기록 SaveGame
- [ ] `문서` **[필수]** **ADR-0003** '오브젝트 풀을 투사체에만 적용한 이유'(측정 근거 포함)
- [ ] `Git` **[필수]** 월간 회고 (M3 종료) — 루브릭 자가 평가 포함
- [ ] `코테` **[필수]** 4~5문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 완성된 게임 루프 · ADR-0003 · 풀링 측정 수치

**🏁 완료 기준(DoD)**
- 메뉴 → 게임 → 게임오버 → 메뉴 루프가 3회 연속 끊김 없이 돌고, 기록이 재실행 후에도 유지된다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[게임플레이] GameMode와 GameState에 둘 데이터의 구분 기준은?</summary>

규칙·서버만 알아야 하는 것(스폰 로직, 난이도 계산)은 GameMode, 모든 플레이어가 봐야 하는 상태(현재 웨이브, 남은 적, 남은 시간)는 GameState.
</details>

<details><summary>[UE 코어] Subsystem의 종류와 수명은?</summary>

Engine(엔진 전체), Editor(에디터), GameInstance(게임 실행~종료, 레벨 전환에도 유지), World(월드 단위), LocalPlayer(로컬 플레이어 단위). 싱글턴 대신 수명이 명확한 전역 서비스.
</details>

<details><summary>[최적화] 언리얼에서 오브젝트 풀링 시 주의점은?</summary>

재사용 시 BeginPlay가 다시 불리지 않으므로 명시적 Reset/Activate 함수가 필요하고, 충돌·Tick·가시성을 켜고 꺼야 한다. 측정 없이 무조건 적용하지 않는다.
</details>

<details><summary>[최적화] AsyncSaveGameToSlot을 쓰는 이유는?</summary>

직렬화와 디스크 쓰기를 게임 스레드에서 동기로 하면 멈칫(히치)이 생긴다. 비동기로 처리해 플레이를 끊지 않는다.
</details>

**🤖 AI 프롬프트**
```text
웨이브 서바이벌의 게임 흐름(대기/웨이브/휴식/게임오버)을 GameMode와 GameState로 나눠 설계하려고 해. 데이터·함수를 어디에 둘지 표로 제안하고, 나중에 멀티플레이로 바꿀 때 문제가 될 설계를 미리 경고해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 게임 흐름 EArenaPhase(Waiting/InWave/Break/Ga… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 웨이브 구성 DataTable(웨이브별 적 종류·수·간격) + 스포너 · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 UProjectilePoolSubsystem(WorldSubsystem) · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 메인 메뉴 / 일시정지 / 게임오버 UI + 최고 웨이브 기록 SaveGa… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 ADR-0003 '오브젝트 풀을 투사체에만 적용한 이유'(측정 근거 포함) · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 월간 회고

**📒 이번 주 Git 기록**
- 브랜치: `feat/wave-system` · `perf/projectile-pool` · `feat/menu-savegame`
- 남길 기록: `docs/adr/ADR-0003-projectile-pool.md`
- 남길 기록: `docs/retro/M3.md`
- 주간 Devlog: `docs/devlog/W12.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** 난이도 곡선을 Curve 에셋으로 데이터화

**🚪 M3 관문 — 다음 단계로 넘어가는 조건**

- [ ] 메뉴~게임오버 루프 완성
- [ ] 적 AI 2종
- [ ] 성능 수치 2건(Size Map, 풀링)
- [ ] TS 누적 3건
- [ ] ADR 3건
- [ ] 코테 누적 58문제

---

### M4 · 기본기 점검 & 멀티플레이 & GAS 입문 (W13~W16)

> **이 단계가 증명하는 것:** AI 없이도 기본을 구현하고, 싱글 게임을 멀티로 전환하며 생긴 문제를 해결할 수 있다.  
> **릴리즈:** v0.3.0 싱글플레이 MVP · **AI 레벨:** L2 + AI-Off 점검 주간  
> **코딩테스트(C++):** 그리디, 이분 탐색, DP 기초 — 주 4문제

<a id="w13"></a>

#### W13 · C++ 기본기 점검 & 싱글플레이 MVP

🏁 **릴리즈:** v0.3.0 · 싱글플레이 MVP (1차 지원 가능 시점)

> 🎯 **목표:** 'AI 없이도 설명·구현할 수 있는가'를 점검하고, 남에게 보여줄 수 있는 **첫 플레이 가능 빌드**를 낸다.

**🧩 C++ 생존 문법:** 총정리 — 메모리(스택·힙·누수·댕글링), 복사 vs 이동(`std::move`의 직관, UE `MoveTemp`), Rule of 3/5/0, 가상 소멸자, 스마트 포인터 3종, const 정확성, 전방 선언으로 헤더 의존성 줄이기

**핵심 개념**
- Epic C++ 코딩 표준 셀프 리뷰(네이밍, const, include 순서, `TObjectPtr`)
- include 최소화·전방 선언(빌드 시간), `.Build.cs` 모듈 의존성 정리
- 패키징: Windows Development/Shipping, Maps & Modes, 쿠킹 에러 읽기, `Saved/Logs`·`Saved/Crashes`
- 플레이테스트 운영: 관찰 → 피드백 → 이슈 등록 → 우선순위 라벨

**유니티/C#에서 건너오기**
- 유니티 Build Settings → Build ↔ Platforms → Windows → Package Project (쿠킹 포함)

**✅ 과제**
- [ ] `AI-Off` **[필수]** C++ 필기 점검: 이 문서 W1~W12의 C++ 자가 점검 질문을 AI 없이 답변 → 틀린 것만 오답 노트
- [ ] `AI-Off` **[필수]** **월간 AI-Off 챌린지 ③(90분):** 빈 프로젝트에 'HealthComponent + 데미지 + 사망 델리게이트 + 체력바'를 AI 없이 구현 → 막힌 지점 기록
- [ ] `구현` **[필수]** 전체 코드 셀프 리뷰 PR: 네이밍, const, UPROPERTY 누락, 불필요한 Tick, include 정리 — AI 리뷰 결과와 '내가 채택/거절한 이유'를 함께 기록
- [ ] `구현` **[필수]** Windows 패키징(Shipping) 성공 → 다른 폴더에 풀어 실행 확인 → zip으로 묶어 GitHub Release에 첨부(파일당 2GiB 이하) — 평가자가 바로 실행해 볼 수 있다
- [ ] `구현` **[필수]** 지인 3명 플레이테스트 → 피드백을 이슈로 등록하고 우선순위 라벨
- [ ] `Git` **[필수]** Release **v0.3.0** '싱글플레이 MVP' + 90초 영상 + README 1차 완성(기능 표·아키텍처 다이어그램)
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** v0.3.0 · README 1차 · C++ 오답 노트 · AI-Off 90분 기록

**🏁 완료 기준(DoD)**
- 이 시점의 저장소만으로도 지원서를 낼 수 있다: README · 영상 · TS 3건 이상 · ADR 3개.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[C++] 가상 소멸자가 필요한 이유는?</summary>

부모 포인터로 자식 객체를 delete할 때 소멸자가 virtual이 아니면 부모 소멸자만 호출돼 자식의 자원이 새어 나간다. 상속해서 쓸 클래스는 소멸자를 virtual로.
</details>

<details><summary>[C++] 복사와 이동의 차이는?</summary>

복사는 자원을 복제, 이동은 자원의 소유권만 넘기고 원본은 빈 상태가 된다. 큰 버퍼를 싸게 전달할 수 있다. UE에서는 MoveTemp.
</details>

<details><summary>[C++] Rule of Three/Five/Zero란?</summary>

소멸자·복사 생성자·복사 대입(+이동 생성자·이동 대입) 중 하나를 직접 정의하면 나머지도 정의해야 한다(자원 관리 일관성). Zero는 자원 관리를 스마트 포인터·컨테이너에 맡겨 아무것도 정의하지 않는 것이 이상적이라는 원칙.
</details>

<details><summary>[C++] 헤더에서 include 대신 전방 선언을 쓰는 이유는?</summary>

포인터·참조로만 쓰면 타입의 정의가 필요 없다. 의존성과 재컴파일 범위, 빌드 시간이 줄어든다. 실제로 멤버를 쓰는 .cpp에서 include한다.
</details>

<details><summary>[C++] 메모리 누수와 댕글링 포인터의 차이는?</summary>

누수: 해제하지 않아 못 쓰는 메모리가 쌓임. 댕글링: 이미 해제된 메모리를 가리키는 포인터(접근 시 크래시·오염).
</details>

<details><summary>[C++] TArray에 요소를 추가한 뒤 이전에 받아둔 요소 포인터·참조가 위험한 이유는?</summary>

용량을 넘으면 더 큰 메모리로 재할당·이동하므로 이전 주소가 무효가 된다. 필요한 크기를 알면 Reserve로 예방하고, 추가 후엔 다시 얻는다.
</details>

**🤖 AI 프롬프트**
```text
너는 게임회사 UE 클라이언트 신입 면접관이야. 내 HealthComponent 코드(첨부)를 보고 C++ 기본기(포인터, const, 메모리, virtual)를 확인하는 꼬리 질문 5개를 하나씩 해줘. 내가 답하면 채점하고 부족한 부분만 짧게 보충해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 C++ 필기 점검 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제2 월간 AI-Off 챌린지 ③(90분) · 코테 · 자가 점검 · TIL
- Day 3 (수, 약 3시간): 과제3 전체 코드 셀프 리뷰 PR · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제4 Windows 패키징(Shipping) 성공 → 다른 폴더에 풀어 실행 확… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제5 지인 3명 플레이테스트 → 피드백을 이슈로 등록하고 우선순위 라벨 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · 자가 점검 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 릴리즈

**📒 이번 주 Git 기록**
- 브랜치: `refactor/self-review` · `build/mac-shipping`
- 남길 기록: `README.md` 1차
- 남길 기록: 학습 로그: AI-Off ③ 기록
- 🏷 릴리즈: `v0.3.0` (🔔 알림 → 릴리즈)
- 주간 Devlog: `docs/devlog/W13.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** 다른 PC(학원·지인)에서 저장소를 Clone해 처음부터 빌드되는지 확인 — 빠진 파일·설정을 찾는 좋은 테스트

---

<a id="w14"></a>

#### W14 · 네트워크 ① — 리플리케이션 · RPC · 권한

> 🎯 **목표:** 별도 실험 맵(NetLab)에서 **'어떤 코드가 어느 컴퓨터에서 실행되는가'**를 몸으로 익힌다.

**🧩 C++ 생존 문법:** 권한 분기 습관(`HasAuthority()`, `IsLocallyControlled()`), 매크로가 만들어 내는 코드 읽기(`DOREPLIFETIME`)

**핵심 개념**
- 서버 권위 모델, Listen Server vs Dedicated Server, NetMode
- Role/RemoteRole: Authority · AutonomousProxy · SimulatedProxy
- `bReplicates`, `GetLifetimeReplicatedProps` + `DOREPLIFETIME(_CONDITION)`, `ReplicatedUsing`/`OnRep_` (C++에선 서버에서 자동 호출 안 됨)
- RPC: Server / Client / NetMulticast, Reliable / Unreliable, 오너십(소유하지 않은 액터에서는 Server RPC 불가)
- 클래스별 존재 위치: GameMode=서버만, PlayerController=서버+소유 클라, HUD=소유 클라만, Pawn·PlayerState·GameState=모두
- PIE 멀티(Play As Listen Server, 플레이어 2명), 네트워크 에뮬레이션(지연·패킷 손실)

**유니티/C#에서 건너오기**
- Netcode for GameObjects의 NetworkVariable ↔ 복제 프로퍼티
- ServerRpc/ClientRpc ↔ Server/Client/NetMulticast RPC, IsServer/IsOwner ↔ HasAuthority/IsLocallyControlled

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Public/Net/UnrealNetwork.h` | `DOREPLIFETIME` 매크로가 실제로 하는 일 |
| `Engine/Source/Runtime/Engine/Classes/GameFramework/Actor.h` | `bReplicates`, `GetLifetimeReplicatedProps`, `HasAuthority`, `GetLocalRole` |
| `Engine/Source/Runtime/Engine/Private/ActorReplication.cpp` | 액터 복제 관련 구현 훑어보기(전부 이해하려 하지 않기) |

**✅ 과제**
- [ ] `구현` **[필수]** `L_NetLab` 실험 맵에서 네트워크 실험 4가지
    - ① 복제되는 문: 서버만 상태를 바꾸고, `OnRep`으로 클라이언트 화면에 반영
    - ② Server RPC 버튼: 내 것이 아닌 액터에서 호출하면 실패하는 로그 확인 (오너십)
    - ③ NetMulticast vs 복제 변수: 늦게 들어온 클라이언트에게 무엇이 보이는지 비교
    - ④ `COND_OwnerOnly` 변수: 주인에게만 복제되는지 확인
- [ ] `구현` **[필수]** 모든 실험을 PIE 2인 + 네트워크 에뮬레이션(지연 150~200ms, 손실 5%)으로 확인
- [ ] `문서` **[필수]** 엔진 노트 `05-network-basics.md`: '어떤 클래스가 어디에 존재하나' 표 + 'Server RPC → 상태 변경 → 복제 → OnRep' 시퀀스 다이어그램(Mermaid)
- [ ] `문서` **[필수]** TS 1건: 네트워크 실험에서 예상과 달랐던 동작
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** NetLab 맵 · 엔진 노트 05 · TS 1건

**🏁 완료 기준(DoD)**
- 실험 4종을 보며 각 코드가 서버/클라이언트 중 어디서 실행되는지 설명할 수 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[네트워크] Server RPC를 호출할 수 있는 조건은?</summary>

호출하는 클라이언트가 그 액터의 소유 연결이어야 한다(Owner 체인이 그 클라의 PlayerController). 아니면 호출이 버려진다.
</details>

<details><summary>[네트워크] OnRep 함수는 서버에서도 호출되나?</summary>

C++에선 서버에서 값을 바꿔도 자동 호출되지 않는다. 서버(리슨 서버 호스트 포함)에서도 필요하면 직접 호출한다. 블루프린트 RepNotify는 서버에서도 호출된다.
</details>

<details><summary>[네트워크] Reliable RPC를 남발하면?</summary>

재전송·순서 보장 비용으로 대역폭과 버퍼가 포화되고 심하면 연결이 끊긴다. 자주 보내는 연출성 이벤트는 Unreliable.
</details>

<details><summary>[네트워크] NetMulticast와 복제 프로퍼티는 어떻게 골라 쓰나?</summary>

상태(체력, 문 열림)는 복제 프로퍼티 — 늦게 들어온 클라도 최신 상태를 받는다. 일회성 연출(이펙트, 사운드)은 Unreliable Multicast.
</details>

<details><summary>[네트워크] AutonomousProxy와 SimulatedProxy의 차이는?</summary>

AutonomousProxy: 내가 조종하는 내 폰(클라 측 사본). SimulatedProxy: 다른 플레이어·AI의 복제본으로 서버 상태를 받아 보간해 보여준다.
</details>

**🤖 AI 프롬프트**
```text
언리얼 리플리케이션을 처음 배워. Listen Server + 클라이언트 1명 상황에서 클라이언트가 문 열기 버튼을 누를 때 각 머신(서버/클라)에서 실행되는 코드 순서를 mermaid 시퀀스 다이어그램으로 그려줘. HasAuthority 분기와 OnRep 호출 시점을 꼭 표시해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 L_NetLab 실험 맵에서 네트워크 실험 4가지 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 모든 실험을 PIE 2인 + 네트워크 에뮬레이션(지연 150~200ms,… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 엔진 노트 05-network-basics.md · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 TS 1건 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/netlab`
- 남길 기록: `docs/engine-notes/05-network-basics.md`
- 남길 기록: `docs/troubleshooting/TS-004-<증상>.md`
- 주간 Devlog: `docs/devlog/W14.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Dedicated Server 모드로도 PIE 실행해 차이 관찰

---

<a id="w15"></a>

#### W15 · 네트워크 ② — 싱글 → 2인 협동 전환

> 🎯 **목표:** 싱글 MVP를 2인 협동으로 바꾸며 생기는 버그를 **기록하고 고치는 과정 자체**를 포트폴리오 소재로 만든다.

**핵심 개념**
- 입력 → Server RPC → 서버 판정 흐름, 공격 몽타주 동기화(Multicast vs 복제 상태)
- 이동은 CMC가 예측까지 처리 — 하지만 스프린트 속도를 RPC로만 바꾸면 보정(러버밴딩) 발생 → 관찰·기록
- HealthComponent 복제(`SetIsReplicatedByDefault`, OnRep → UI)
- AI·스폰·웨이브는 서버에서만, GameState 복제로 HUD 갱신, 사망·리스폰

**유니티/C#에서 건너오기**
- 유니티 Netcode에서도 같은 질문: '이 코드는 서버에서 도나, 오너에서 도나?'

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Engine/Classes/GameFramework/CharacterMovementComponent.h` | `FSavedMove_Character`, `ClientAdjustPosition` 이름만 찾아두기(W21-C 예고) |

**✅ 과제**
- [ ] `구현` **[필수]** 공격: 클라 입력 → `ServerAttack` RPC → 서버에서 판정·데미지 → 피격 연출 Multicast(Unreliable)
- [ ] `구현` **[필수]** HealthComponent 복제 + OnRep → 델리게이트 → UI (W9 구조가 그대로 재사용되는지 확인)
- [ ] `구현` **[필수]** 웨이브·남은 적 GameState 복제 → 양쪽 HUD 갱신, 적 스폰과 AI는 서버에서만
- [ ] `구현` **[필수]** 사망 → 리스폰(또는 관전) 흐름
- [ ] `문서` **[필수]** TS 최소 2건: 예) 클라에서 데미지 2번 적용, 스프린트 러버밴딩, 클라 UI만 갱신 안 됨
- [ ] `문서` **[필수]** **ADR-0004** '공격 반응성 개선 방식' — 선택지(클라 예측 직접 구현 / GAS 예측) 비교 후 'GAS 도입'으로 결정
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 2인 협동 동작 · TS 2건+ · ADR-0004

**🏁 완료 기준(DoD)**
- 지연 200ms에서도 2인 플레이의 상태가 어긋나지 않는다(반응 지연은 있어도 불일치는 없음) — 영상으로 기록.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[네트워크] 클라이언트에서 체력을 직접 깎으면?</summary>

서버 권위 위반. 다른 머신엔 반영되지 않고 서버 복제가 다시 덮어써 불일치가 생기며, 치트에도 취약하다.
</details>

<details><summary>[네트워크] 스프린트 속도를 RPC로만 바꾸면 끊기는(러버밴딩) 이유는?</summary>

CMC는 클라가 먼저 예측 이동하고 서버가 검증한다. 클라와 서버의 속도 값이 시점상 다르면 서버가 위치를 보정한다. 정석은 CMC 커스텀(SavedMove 플래그)이나 예측 가능한 구조(GAS 등).
</details>

<details><summary>[네트워크] 늦게 접속한 플레이어가 적 상태를 올바르게 보려면?</summary>

상태는 복제 프로퍼티로 보내야 한다. Multicast로 보낸 과거 이벤트는 늦게 들어온 클라가 받지 못한다.
</details>

<details><summary>[AI] AIController는 클라이언트에 존재하나?</summary>

서버에만 존재한다. 클라는 적 Pawn의 복제본(SimulatedProxy)만 본다.
</details>

**🤖 AI 프롬프트**
```text
싱글플레이로 만든 근접 전투를 Listen Server 2인 협동으로 바꾸려고 해. 현재 흐름(입력→몽타주→노티파이 판정→ApplyDamage)을 보고 단계마다 서버/클라 중 어디서 실행돼야 하는지 표시하고, 바꿀 때 흔히 생기는 버그 5개를 미리 알려줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 공격 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 HealthComponent 복제 + OnRep → 델리게이트 → UI (… · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 웨이브·남은 적 GameState 복제 → 양쪽 HUD 갱신, 적 스폰과… · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 사망 → 리스폰(또는 관전) 흐름 · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 TS 최소 2건 · 과제6 ADR-0004 '공격 반응성 개선 방식' · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/coop-combat` · `feat/replicated-health` · `feat/replicated-waves`
- 남길 기록: `docs/troubleshooting/TS-005-<증상>.md`
- 남길 기록: `docs/troubleshooting/TS-006-<증상>.md`
- 남길 기록: `docs/adr/ADR-0004-attack-responsiveness.md`
- 주간 Devlog: `docs/devlog/W15.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Network Insights(Unreal Insights)로 복제 트래픽 상위 항목 확인

---

<a id="w16"></a>

#### W16 · GAS ① — ASC · AttributeSet · GameplayEffect · Tags · 첫 Ability

> 🎯 **목표:** GAS 핵심 5요소를 이해하고, **대시를 첫 GameplayAbility**(비용·쿨다운 포함)로 만든다.

**🧩 C++ 생존 문법:** 매크로 기반 보일러플레이트 읽기(`ATTRIBUTE_ACCESSORS` 패턴), 모듈 의존성 추가(`GameplayAbilities`, `GameplayTags`, `GameplayTasks`)

**핵심 개념**
- `UAbilitySystemComponent`(ASC), `IAbilitySystemInterface`
- `UAttributeSet`: Health·MaxHealth·Stamina + 메타 속성 IncomingDamage, `PreAttributeChange`/`PostGameplayEffectExecute`
- `UGameplayEffect`: Instant / Duration / Infinite, Periodic, Modifier, SetByCaller
- `UGameplayAbility`: `ActivateAbility` · `CommitAbility`(비용·쿨다운) · `EndAbility`, GameplayTags 계층 설계
- ASC 위치(플레이어=PlayerState, 적=Character), Replication Mode(Full/Mixed/Minimal), 초기화 타이밍(서버 `PossessedBy`, 클라 `OnRep_PlayerState`)

**유니티/C#에서 건너오기**
- 유니티엔 대응 내장 기능이 없다 — '스킬·버프·스탯을 엔진이 제공하는 프레임워크'로 이해. 국내 UE 공고 우대사항에 자주 등장한다.

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/AbilitySystemComponent.h` | `GiveAbility`, `TryActivateAbility`, `ApplyGameplayEffectSpecToSelf` |
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/AttributeSet.h` | 속성 접근자 매크로 예시 주석, `FGameplayAttributeData` |
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/Abilities/GameplayAbility.h` | `ActivateAbility`, `CommitAbility`, `EndAbility`, 인스턴싱·네트워크 실행 정책 |
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/GameplayEffect.h` | `EGameplayEffectDurationType`, Modifier 구조 |

**✅ 과제**
- [ ] `구현` **[필수]** 플러그인 활성화 + `.Build.cs` 의존성 + `UArenaAbilitySystemComponent`
- [ ] `구현` **[필수]** `UArenaAttributeSet`: Health·MaxHealth·Stamina·MaxStamina + 메타 IncomingDamage, 범위 제한(Clamp)
- [ ] `구현` **[필수]** ASC 위치 결정: 플레이어 PlayerState, 적 Character — **ADR-0005**
- [ ] `구현` **[필수]** GE: GE_Damage(Instant, SetByCaller), GE_StaminaRegen(Infinite·Periodic), GE_Dash_Cost, GE_Dash_Cooldown
- [ ] `구현` **[필수]** GameplayTags 설계 문서(`State.*`, `Ability.*`, `Event.*`, `Cooldown.*`) + GA_Dash(공격 중 사용 불가 태그 조건)
- [ ] `학습` **[필수]** 커뮤니티 GAS 문서(tranek/GASDocumentation) 앞부분 + Lyra 샘플의 ASC 구조 훑기(전부 읽지 않기)
- [ ] `Git` **[필수]** 월간 회고 (M4 종료)
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** GA_Dash · ADR-0005 · 태그 설계 문서

**🏁 완료 기준(DoD)**
- 대시가 2인 PIE에서 비용·쿨다운과 함께 동작하고, GAS 구성요소 5개를 그림 1장으로 설명할 수 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[GAS] ASC를 PlayerState에 둘 때와 Character에 둘 때의 차이는?</summary>

PlayerState: 폰이 죽고 리스폰돼도 속성·어빌리티가 유지된다(플레이어). Character: 폰과 수명을 같이하고 구조가 단순하다(적·소모성 유닛). PlayerState는 기본 복제 빈도가 낮아 올려야 할 수 있다.
</details>

<details><summary>[GAS] Instant와 Duration/Infinite GameplayEffect의 차이는?</summary>

Instant: Base 값을 영구 변경(데미지·회복). Duration/Infinite: 적용 중에만 Current 값을 수정(버프). Periodic이면 주기마다 실행된다.
</details>

<details><summary>[GAS] Replication Mode 3종은?</summary>

Full: 모든 GE를 모든 클라에 복제(싱글·소규모). Mixed: GE는 소유 클라에만, 태그·큐는 모두에게(플레이어용). Minimal: GE 복제 없이 태그·큐만(AI용).
</details>

<details><summary>[GAS] 메타 속성(IncomingDamage)을 쓰는 이유는?</summary>

데미지를 임시 속성으로 받은 뒤 PostGameplayEffectExecute에서 방어력·보호막을 계산해 Health에 반영 → 계산 로직이 한 곳에 모이고 서버에서만 처리된다.
</details>

<details><summary>[GAS] CommitAbility는 무엇을 하나?</summary>

비용(Cost GE)과 쿨다운(Cooldown GE)을 실제로 적용하는 '확정' 단계. 적용할 수 없으면 실패를 반환한다.
</details>

**🤖 AI 프롬프트**
```text
GAS를 처음 써. 내 게임(근접 콤보, 대시, 체력/스태미나, 2인 협동)에 필요한 GAS 구성요소만 최소로 골라서, 만들 클래스와 각각의 책임을 표로 정리해줘. Lyra 수준의 확장성은 필요 없고 6개월 포트폴리오 범위로 제한해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제6 커뮤니티 GAS 문서(tranek/GASDocumentation) 앞부분… · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 플러그인 활성화 + .Build.cs 의존성 + UArenaAbilityS… · 과제2 UArenaAttributeSet · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제3 ASC 위치 결정 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제4 GE · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제5 GameplayTags 설계 문서(State.*, Ability.*, Ev… · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 월간 회고

**📒 이번 주 Git 기록**
- 브랜치: `feat/gas-setup` · `feat/ga-dash`
- 남길 기록: `docs/adr/ADR-0005-asc-location.md`
- 남길 기록: `docs/gas-tags.md`
- 남길 기록: `docs/retro/M4.md`
- 주간 Devlog: `docs/devlog/W16.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** GameplayEffectExecutionCalculation으로 방어력 공식 구현

**🚪 M4 관문 — 다음 단계로 넘어가는 조건**

- [ ] v0.3.0 MVP 패키징·릴리즈
- [ ] README 1차
- [ ] AI-Off 챌린지 ③(90분) 기록
- [ ] NetLab 노트 + TS 누적 6건
- [ ] GA_Dash 동작
- [ ] 코테 누적 74문제

---

### M5 · GAS 완성 · 최적화 · 품질 (W17~W20)

> **이 단계가 증명하는 것:** 실무 프레임워크(GAS)와 측정 기반 최적화, 테스트로 품질을 관리한다.  
> **릴리즈:** v0.4.0 2인 협동 → v0.5.0 RC · **AI 레벨:** L2~L3 — 내가 작성하고 AI는 검증·대안 제시  
> **코딩테스트(C++):** 최단경로, DP, 구현(시뮬레이션) — 주 4문제

<a id="w17"></a>

#### W17 · GAS ② — 전투 이전 + 2인 협동 완성

🏁 **릴리즈:** v0.4.0 · 2인 협동

> 🎯 **목표:** 기존 전투·체력을 GAS로 옮기고, 같은 지연 환경에서 **'전/후 반응성 비교 영상'**을 만든다.

**🧩 C++ 생존 문법:** 콜백·비동기 흐름 읽기(AbilityTask의 델리게이트 연결), 기존 코드를 안전하게 갈아엎는 마이그레이션 순서

**핵심 개념**
- GA_MeleeCombo: AbilityTask `PlayMontageAndWait` + `WaitGameplayEvent`
- AnimNotify → `SendGameplayEventToActor`(Event.Montage.Hit) → GE_Damage(SetByCaller)
- 사망 = `State.Dead` 태그 + GameplayCue(이펙트·사운드), 로컬 예측(LocalPredicted)
- UI는 `GetGameplayAttributeValueChangeDelegate`로, HealthComponent → AttributeSet 마이그레이션, 적도 GA로 공격

**유니티/C#에서 건너오기**
- 유니티에서 직접 만들던 스킬·버프 매니저를 엔진 프레임워크로 대체하는 경험

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/Abilities/Tasks/AbilityTask_PlayMontageAndWait.h` | 완료·중단·블렌드아웃 델리게이트 |
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/Abilities/Tasks/AbilityTask_WaitGameplayEvent.h` | 이벤트 태그로 대기하는 방식 |
| `Engine/Plugins/Runtime/GameplayAbilities/Source/GameplayAbilities/Public/AbilitySystemBlueprintLibrary.h` | `SendGameplayEventToActor` |

**✅ 과제**
- [ ] `구현` **[필수]** GA_MeleeCombo + 몽타주·이벤트 연동 (W7 판정 로직 재사용)
- [ ] `구현` **[필수]** HealthComponent → AttributeSet 기반 교체 — UI는 속성 변경 델리게이트 구독 (W9 위젯 인터페이스 유지 확인)
- [ ] `구현` **[필수]** 사망·피격 이펙트를 GameplayCue로
- [ ] `구현` **[필수]** 적 공격도 GA로 (BTTask에서 어빌리티 활성화)
- [ ] `문서` **[필수]** 비교 영상: 지연 200ms에서 W15(RPC 방식) vs W17(GAS 예측) 공격 반응성 나란히 → README 핵심 섹션, ADR-0004 결과 업데이트
- [ ] `Git` **[필수]** Release **v0.4.0** '2인 협동'
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** v0.4.0 · 반응성 비교 영상 · ADR-0004 결과

**🏁 완료 기준(DoD)**
- 2인 플레이 10분 연속 무버그 + 비교 영상이 README에 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[GAS] AbilityTask란?</summary>

어빌리티 안에서 비동기 작업(몽타주 재생 대기, 이벤트 대기, 타깃 대기)을 수행하는 단위. 완료·중단 델리게이트로 흐름을 이어 간다.
</details>

<details><summary>[GAS] GameplayCue를 쓰는 이유는?</summary>

순수 연출(이펙트·사운드)을 게임 로직과 분리하고 네트워크로 효율적으로 전달한다. 연출이라 데디케이티드 서버에선 실행되지 않는다.
</details>

<details><summary>[GAS] 로컬 예측이 반응성을 높이는 원리는?</summary>

클라가 서버 승인 전에 먼저 실행하고(예측 키), 서버가 승인하면 유지, 거부하면 되돌린다. 지연을 체감에서 숨긴다.
</details>

<details><summary>[설계] GAS 도입의 비용은?</summary>

학습 곡선, 보일러플레이트, 디버깅 난이도(`showdebug abilitysystem` 활용). 작은 게임엔 과할 수 있으므로 도입 근거를 ADR로 남긴다.
</details>

**🤖 AI 프롬프트**
```text
GAS로 근접 콤보를 구현할 때 PlayMontageAndWait와 WaitGameplayEvent를 어떻게 조합하는지 흐름만 설명해줘. 그리고 'AnimNotify에서 SendGameplayEventToActor로 히트 이벤트를 보내는 방식'의 장단점과 네트워크에서 주의할 점을 알려줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 GA_MeleeCombo + 몽타주·이벤트 연동 (W7 판정 로직 재사용) · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 HealthComponent → AttributeSet 기반 교체 · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 사망·피격 이펙트를 GameplayCue로 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 적 공격도 GA로 (BTTask에서 어빌리티 활성화) · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 비교 영상 · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 릴리즈

**📒 이번 주 Git 기록**
- 브랜치: `refactor/combat-to-gas` · `feat/gameplay-cues`
- 남길 기록: ADR-0004 결과 업데이트 + 반응성 비교 영상 링크
- 🏷 릴리즈: `v0.4.0` (🔔 알림 → 릴리즈)
- 주간 Devlog: `docs/devlog/W17.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** GameplayEffect로 버프(공격력 증가 10초) 아이템 추가

---

<a id="w18"></a>

#### W18 · 프로파일링 & 최적화

> 🎯 **목표:** '느린 것 같다'가 아니라 **ms 단위 근거**로 병목 3개를 찾아 개선하고 전/후 수치를 남긴다.

**🧩 C++ 생존 문법:** 측정용 매크로(`TRACE_CPUPROFILER_EVENT_SCOPE`, `SCOPE_CYCLE_COUNTER`), 불필요한 복사 제거(`const&`), 컨테이너 `Reserve`

**핵심 개념**
- 측정 먼저 원칙, `stat unit` · `stat fps` · `stat game` · `stat net`
- 게임 스레드 / 렌더 스레드 / GPU 병목 구분
- Unreal Insights: CPU 트레이스, Memory Insights, Networking Insights
- Tick 정리, 적 다수일 때 CMC·애니메이션 비용(업데이트 비율, 화면 밖 애니메이션 틱 옵션), 네트워크 `NetUpdateFrequency`·Dormancy·Relevancy
- 측정 주의: 노트북이면 전원을 연결하고 Windows 전원 모드를 '최고 성능'으로, 같은 조건에서 여러 번 측정해 중간값 사용

**유니티/C#에서 건너오기**
- Unity Profiler ↔ Unreal Insights, `Profiler.BeginSample` ↔ `TRACE_CPUPROFILER_EVENT_SCOPE`

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Core/Public/ProfilingDebugging/CpuProfilerTrace.h` | `TRACE_CPUPROFILER_EVENT_SCOPE` 사용법 |
| `Engine/Source/Runtime/Core/Public/Stats/Stats.h` | `DECLARE_CYCLE_STAT`, `SCOPE_CYCLE_COUNTER` |

**✅ 과제**
- [ ] `구현` **[필수]** 스트레스 테스트 맵: 적 50 → 100마리, 투사체 다수 (치트로 즉시 소환)
- [ ] `구현` **[필수]** 내 코드 핵심 함수(웨이브 매니저, 판정, AI 서비스)에 `TRACE_CPUPROFILER_EVENT_SCOPE` 추가 → Insights에서 식별
- [ ] `구현` **[필수]** 병목 Top 3 개선 (예: 적 Tick 정리, 애니메이션 업데이트 비율, 트레이스 빈도, 복제 빈도) — 각각 전/후 ms
- [ ] `문서` **[필수]** `perf/02-performance-report.md`: 측정 환경(기기·설정·반복 횟수), 스크린샷, 전/후 표, 배운 점 — 포트폴리오 핵심 페이지
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 성능 리포트 · 트레이스 스코프가 추가된 코드

**🏁 완료 기준(DoD)**
- 개선 3건 각각에 같은 조건·여러 번 측정한 전/후 수치가 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[최적화] 프레임 저하 원인이 게임/렌더/GPU 중 어디인지 어떻게 구분하나?</summary>

`stat unit`에서 Game·Draw·GPU 시간 중 프레임 시간에 가장 가까운 항목이 병목. 그 영역을 Insights로 상세 분석한다.
</details>

<details><summary>[최적화] 측정 없이 최적화하면 안 되는 이유는?</summary>

병목이 아닌 곳을 고치면 효과 없이 복잡도만 늘어난다. 직관은 자주 틀린다.
</details>

<details><summary>[네트워크] NetUpdateFrequency와 Dormancy는?</summary>

NetUpdateFrequency: 액터의 복제 검사 빈도. Dormancy: 변화 없는 액터를 복제 대상에서 휴면 처리해 서버 CPU와 대역폭을 아낀다.
</details>

<details><summary>[최적화] 적이 많을 때 애니메이션 비용을 줄이는 방법은?</summary>

거리·가시성에 따라 업데이트 빈도 낮추기(Update Rate Optimization), 화면 밖이면 애니메이션 틱 생략, 불필요한 본·노드 정리. 단, 판정에 필요한 노티파이가 빠지지 않는지 확인.
</details>

**🤖 AI 프롬프트**
```text
Unreal Insights 트레이스 스크린샷(첨부)을 같이 읽자. 바로 답을 주지 말고 '어느 트랙의 어떤 항목을 먼저 봐야 하는지' 순서대로 질문해줘. 내가 찾은 걸 말하면 해석을 도와줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 스트레스 테스트 맵 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 내 코드 핵심 함수(웨이브 매니저, 판정, AI 서비스)에 TRACE_CP… · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 병목 Top 3 개선 (예 · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 보충 · 이번 주 문서 다듬기 · 자가 점검 · TIL
- Day 6 (토, 약 5.5시간): 과제4 perf/02-performance-report.md · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `perf/stress-test` · `perf/<병목-이름>`
- 남길 기록: `docs/perf/02-performance-report.md`
- 주간 Devlog: `docs/devlog/W18.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Memory Insights로 레벨 로드 시 메모리 상위 에셋 분석

---

<a id="w19"></a>

#### W19 · 품질 — 자동화 테스트 · 치트 · 버그 제로 · Shipping

> 🎯 **목표:** '잘 돌아가는 것 같다'를 **테스트와 이슈 트래커로 증명**한다.

**🧩 C++ 생존 문법:** 테스트 가능한 설계: 계산 로직을 월드·액터에 의존하지 않는 순수 함수로 분리

**핵심 개념**
- Automation Test(`IMPLEMENT_SIMPLE_AUTOMATION_TEST`, Automation Spec), Test Automation 창(또는 Session Frontend)에서 실행
- `UCheatManager` Exec 치트(무적·웨이브 스킵·적 소환) — 시연 촬영용
- `check` / `ensure` / `verify`와 Shipping에서의 동작 차이, 크래시 콜스택 읽기
- 버그 분류(심각도·재현 단계), Known Issues 문서화

**유니티/C#에서 건너오기**
- Unity Test Framework(EditMode/PlayMode) ↔ Automation Test / Functional Test

**🔍 엔진 소스 읽기**

| 파일 | 찾아볼 것 |
|---|---|
| `Engine/Source/Runtime/Core/Public/Misc/AutomationTest.h` | `IMPLEMENT_SIMPLE_AUTOMATION_TEST`, `EAutomationTestFlags` |
| `Engine/Source/Runtime/Engine/Classes/GameFramework/CheatManager.h` | Exec 함수 예시 |
| `Engine/Source/Runtime/Core/Public/Misc/AssertionMacros.h` | `check`/`ensure`/`verify` 정의와 빌드 구성별 동작 |

**✅ 과제**
- [ ] `구현` **[필수]** 자동화 테스트 5개+: 데미지 계산(방어력·크리티컬), 웨이브 DataTable 검증(빈 행·음수), 무기 DataAsset 필수 필드 검증, 풀 반환, 태그 상태 전이
- [ ] `구현` **[필수]** `UArenaCheatManager`: God, SkipWave, SpawnEnemy N
- [ ] `구현` **[필수]** 열린 버그 이슈 0개 목표 — 못 고친 것은 README의 Known Issues로
- [ ] `구현` **[필수]** Shipping 패키징 + 30분 연속 플레이(로그 에러·크래시 0)
- [ ] `문서` **[필수]** `TESTING.md`: 테스트 목록·실행 방법·결과 스크린샷
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 자동화 테스트 5+ · TESTING.md · 치트 매니저

**🏁 완료 기준(DoD)**
- 테스트가 모두 통과하는 스크린샷과, 열린 버그 0개(또는 Known Issues 문서)가 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[품질] check, ensure, verify의 차이는?</summary>

check: 실패 시 크래시, Shipping에선 기본적으로 식 자체가 제거된다. ensure: 실패 시 콜스택을 보고하고 계속 진행(기본 첫 1회만 보고). verify: Shipping에서도 식은 평가된다(부수효과가 있는 식에 사용).
</details>

<details><summary>[품질] 테스트하기 쉬운 코드를 만드는 방법은?</summary>

계산 로직을 액터·월드에 의존하지 않는 순수 함수로 분리하고, 입력 → 결과 구조로 만든다. 데이터 검증도 별도 함수로.
</details>

<details><summary>[품질] 신입 포트폴리오에서 자동화 테스트가 의미하는 것은?</summary>

기능 구현을 넘어 품질·회귀 방지를 생각하는 개발자라는 증거. 개수보다 '무엇을 왜 테스트했는지' 설명이 중요하다.
</details>

**🤖 AI 프롬프트**
```text
내 데미지 계산 함수(첨부)에 대한 언리얼 Automation Test 케이스를 경계값 위주로 10개 뽑아줘. 테스트 코드는 1개만 예시로 쓰고 나머지는 내가 작성할게.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 자동화 테스트 5개+ · 코테 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 UArenaCheatManager · 코테 · 자가 점검 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 열린 버그 이슈 0개 목표 · 코테 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제4 Shipping 패키징 + 30분 연속 플레이(로그 에러·크래시 0) · 자가 점검 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제5 TESTING.md · 커밋·Push · PR · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `test/automation` · `feat/cheat-manager`
- 남길 기록: `TESTING.md`
- 주간 Devlog: `docs/devlog/W19.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Functional Test 액터로 '적 스폰 → 처치 → 웨이브 종료' 통합 테스트

---

<a id="w20"></a>

#### W20 · 폴리시 & 게임필

🏁 **릴리즈:** v0.5.0 · 릴리즈 후보(RC)

> 🎯 **목표:** 영상 첫 10초에 **'손맛'**이 느껴지도록 다듬는다 — 평가자는 코드보다 영상을 먼저 본다.

**핵심 개념**
- 히트스톱(`CustomTimeDilation`, 아주 짧게), 카메라 셰이크(`UCameraShakeBase`), 피격 플래시(머티리얼 파라미터)
- 사운드(Sound Cue/MetaSound 기초), Niagara 이펙트를 GameplayCue에 연결, UI 애니메이션
- 입력 반응성 튜닝(콤보 윈도우), (심화) 키 리바인딩

**유니티/C#에서 건너오기**
- 유니티 Time.timeScale 조작·Cinemachine Impulse ↔ CustomTimeDilation·Camera Shake

**✅ 과제**
- [ ] `구현` **[필수]** 히트스톱 + 카메라 셰이크 + 피격 플래시 — 강도는 모두 DataAsset으로 조절
- [ ] `구현` **[필수]** 무료 에셋으로 이펙트·사운드 적용 — 라이선스 확인, 외부 에셋 원본은 공개 저장소 커밋 제외 목록으로 관리
- [ ] `구현` **[필수]** 플레이테스트 2차(3명+) → 피드백 반영
- [ ] `Git` **[필수]** Release **v0.5.0**(RC) + 개선 전/후 비교 GIF + 월간 회고
- [ ] `코테` **[필수]** 4문제(C++) 풀이·커밋
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** v0.5.0 · 전/후 비교 GIF

**🏁 완료 기준(DoD)**
- 플레이테스터 3명 중 2명 이상이 '타격감이 있다'고 답한다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[게임플레이] 히트스톱을 전체 시간 정지(Global Time Dilation)가 아니라 액터별로 거는 이유는?</summary>

멀티플레이에서 전체 시간을 멈추면 다른 플레이어·서버 흐름이 꼬인다. 맞은 액터·때린 액터의 CustomTimeDilation만 짧게 낮춰 연출하고 판정 로직엔 영향이 없게 한다.
</details>

**🤖 AI 프롬프트**
```text
액션 게임의 타격감을 높이는 연출 요소를 우선순위로 7개 뽑고, 각각 언리얼에서 어떤 기능으로 구현하는지와 멀티플레이에서 주의할 점을 표로 정리해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 코테 · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제1 히트스톱 + 카메라 셰이크 + 피격 플래시 · 코테 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제2 무료 에셋으로 이펙트·사운드 적용 · 코테 · 커밋·Push · PR · TIL
- Day 4 (목, 약 3시간): 과제3 플레이테스트 2차(3명+) → 피드백 반영 · 코테 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 보충 · 이번 주 문서 다듬기 · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 릴리즈 · 월간 회고

**📒 이번 주 Git 기록**
- 브랜치: `feat/game-feel`
- 남길 기록: `docs/retro/M5.md`
- 🏷 릴리즈: `v0.5.0` (🔔 알림 → 릴리즈)
- 주간 Devlog: `docs/devlog/W20.md` (🔔 알림 → 주간 Devlog)

**➕ 심화(선택):** Enhanced Input User Settings로 키 리바인딩 UI

**🚪 M5 관문 — 다음 단계로 넘어가는 조건**

- [ ] v0.4.0·v0.5.0 릴리즈
- [ ] 반응성 전/후 비교 영상
- [ ] 성능 리포트(개선 3건)
- [ ] 자동화 테스트 5개+
- [ ] 열린 버그 0(또는 Known Issues)
- [ ] 코테 누적 90문제

---

### M6 · 차별화 & 취업 패키지 (W21~W24)

> **이 단계가 증명하는 것:** 깊게 판 한 가지와, 그것을 설명하는 문서·영상·말하기 능력.  
> **릴리즈:** v1.0.0 최종 · **AI 레벨:** L3 — AI 없이 작성, AI로 검증 / 면접·코테는 AI-Off  
> **코딩테스트(C++):** 프로그래머스 기출 · 모의 시험(시간 제한) — 주 2회

<a id="w21"></a>

#### W21 · 차별화 딥다이브 (택1)

> 🎯 **목표:** '신입인데 이것까지 해봤네' 소리를 들을 **한 가지를 깊게** 판다. 지원할 회사 성격에 맞춰 고른다.

**핵심 개념**
- **A. AI 활용 특화 — Unreal MCP:** UE 5.8의 실험적 'Unreal MCP' 플러그인으로 AI 에이전트(Claude Code·Cursor 등)가 에디터 기능을 호출하게 만들고, 웨이브 데이터 생성·레벨 배치 같은 반복 작업을 자동화. 무엇을 AI에 맡기고 무엇을 사람이 검증했는지 문서화
- **B. AI 설계 — StateTree:** 적 AI를 StateTree로 재구현해 BT 버전과 구조·디버깅·성능을 비교
- **C. 네트워크 특화 — CMC 커스텀:** 스프린트·대시를 `FSavedMove` 플래그로 네트워크 예측되게 구현 — W15 러버밴딩 TS의 '정석 해결'
- **D. 툴 특화 — 에디터 유틸리티:** 기획자용 웨이브 편집기(Editor Utility Widget 또는 에디터 모듈)
- **E. 엔진 분석 특화:** CMC 이동 예측·보정 흐름 또는 GC 흐름을 소스 근거로 블로그 3편

**유니티/C#에서 건너오기**
- 추천: 온라인·액션 게임 회사 → C, 툴·파이프라인 조직 → D, AI 도입에 적극적인 회사 → A

**✅ 과제**
- [ ] `선택` **[필수]** A~E 중 1개 선택 → 이슈 분해(5개 이내) → 구현 또는 분석
- [ ] `문서` **[필수]** 딥다이브 리포트: 문제 정의 → 접근 → 결과(수치·영상) → 한계와 다음 단계
- [ ] `문서` **[필수]** 기술 블로그 1편으로 재가공
- [ ] `코테` **[필수]** 모의 시험 1회(시간 제한, AI 없이)
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 딥다이브 리포트 · 블로그 1편

**🏁 완료 기준(DoD)**
- 면접에서 10분 동안 이 주제만으로 질의응답이 가능하다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[네트워크] (C 선택 시) CMC에서 커스텀 이동을 네트워크 예측되게 하려면?</summary>

입력 상태를 FSavedMove의 압축 플래그로 저장해 서버로 보내고, 서버와 클라가 같은 입력으로 같은 이동을 재현하게 한다. 그래야 서버 보정 없이 예측 결과가 일치한다.
</details>

**🤖 AI 프롬프트**
```text
나는 [A~E 중 선택한 주제]로 1주 딥다이브를 하려고 해. 신입 포트폴리오에서 설득력이 생기도록 범위를 5개 이슈로 쪼개고, 각 이슈의 완료 기준과 '면접에서 받을 질문'을 함께 제안해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 이어서(오늘 분량) · 자가 점검 · 커밋·Push · TIL
- Day 2 (화, 약 3시간): 과제1 이어서(오늘 분량) · 커밋·Push · TIL
- Day 3 (수, 약 3시간): 과제1 이어서(오늘 분량) · 커밋·Push · TIL
- Day 4 (목, 약 3시간): 과제1 A~E 중 1개 선택 → 이슈 분해(5개 이내) → 구현 또는 분석 · 커밋·Push · PR · TIL
- Day 5 (금, 약 3시간): 과제2 딥다이브 리포트 · 커밋·Push · PR · TIL
- Day 6 (토, 약 5.5시간): 과제3 기술 블로그 1편으로 재가공 · 코테 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `feat/deepdive-<주제>`
- 남길 기록: `docs/deepdive.md`
- 남길 기록: 블로그 1편
- 주간 Devlog: `docs/devlog/W21.md` (🔔 알림 → 주간 Devlog)

---

<a id="w22"></a>

#### W22 · 포트폴리오 패키지 — 영상 · README · PDF

> 🎯 **목표:** 평가자가 **30초 안에** '무슨 게임이고, 무엇을 했고, 얼마나 깊게 했는지' 알게 만든다.

**핵심 개념**
- 시연 영상 2~3분(부록 구성안), YouTube 일부 공개
- README 최종본(부록 구조) — 기능 표의 각 행이 코드·문서로 링크
- 기술 포트폴리오 PDF 15~20쪽(부록 구성안) — 국내 채용은 PDF 제출이 많다
- GitHub 프로필 README + 고정 저장소(게임 프로젝트, 학습 로그), 저장소 About·토픽

**✅ 과제**
- [ ] `문서` **[필수]** 시연 영상 2~3분 제작 (자막으로 기술명 표기, 디버그 시각화 장면 포함)
- [ ] `문서` **[필수]** README 최종본 + 같은 기능의 진화 표 + 기술적 도전 Top 3
- [ ] `문서` **[필수]** 기술 포트폴리오 PDF 15~20쪽
- [ ] `Git` **[필수]** GitHub 프로필 README, 고정 저장소, 학습 로그 저장소 인덱스(TIL·엔진 노트·코테 통계) 정리
- [ ] `문서` **[필수]** 현직자·커뮤니티 1명 이상에게 피드백 받기 → 반영
- [ ] `코테` **[필수]** 모의 시험 1회(시간 제한, AI 없이)
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 영상 · README · PDF · 프로필

**🏁 완료 기준(DoD)**
- 비개발자 지인이 README 첫 화면만 보고 30초 안에 프로젝트를 설명할 수 있다.

**🎤 자가 점검 · 면접 질문** (답은 펼쳐서 확인)

<details><summary>[프로젝트] 이 프로젝트를 1분 안에 소개해 보라.</summary>

장르·기간·인원 → 핵심 기술 3개(데이터 주도 전투, 2인 협동+GAS 예측, 성능 개선 수치) → 가장 어려웠던 문제 한 줄 → 배운 점. 숫자와 링크로 말한다.
</details>

**🤖 AI 프롬프트**
```text
내 README 초안(첨부)을 채용 담당자 입장에서 30초 동안 훑어본다고 가정하고, 눈에 걸리는 곳·빠진 근거·너무 긴 곳을 우선순위로 지적해줘. 문장을 대신 써주지는 말고 고칠 방향만 알려줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 시연 영상 2~3분 제작 (자막으로 기술명 표기, 디버그 시각화 장면 포함) · 자가 점검 · TIL
- Day 2 (화, 약 3시간): 과제2 README 최종본 + 같은 기능의 진화 표 + 기술적 도전 Top 3 · 커밋·Push · PR · TIL
- Day 3 (수, 약 3시간): 과제3 이어서(오늘 분량) · TIL
- Day 4 (목, 약 3시간): 과제3 기술 포트폴리오 PDF 15~20쪽 · TIL
- Day 5 (금, 약 3시간): 과제4 GitHub 프로필 README, 고정 저장소, 학습 로그 저장소 인덱스(… · TIL
- Day 6 (토, 약 5.5시간): 과제5 현직자·커뮤니티 1명 이상에게 피드백 받기 → 반영 · 코테 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 브랜치: `docs/readme-final`
- 남길 기록: `README.md` 최종
- 남길 기록: 포트폴리오 PDF
- 남길 기록: GitHub 프로필 README
- 주간 Devlog: `docs/devlog/W22.md` (🔔 알림 → 주간 Devlog)

---

<a id="w23"></a>

#### W23 · 면접 대비 — 질문 은행 · 코드 설명 · 모의 코테

> 🎯 **목표:** **AI 없는 자리**(코테·기술 면접·과제)에서 내 코드와 기본기를 증명한다.

**핵심 개념**
- 이 문서의 질문 은행 전체(주차별 자가 점검 + 일반 질문)
- 코드 설명 면접: 내 핵심 파일 5개를 화면 공유하듯 3분씩 설명
- 프로젝트 설명 1분/3분 버전, 트러블슈팅 사례 '30초 버전'
- CS 기본: 프로세스/스레드, 메모리 구조, 자료구조 복잡도, 3D 수학 요약

**✅ 과제**
- [ ] `AI-Off` **[필수]** 질문 은행 답변 스크립트 작성 → 소리 내어 녹음 → 다시 듣고 수정
- [ ] `AI` **[필수]** AI 면접관 모드로 내 코드 꼬리 질문 리허설 3회 (질문만 받고 답은 AI 없이)
- [ ] `AI-Off` **[필수]** 모의 코딩테스트 3회(시간 제한, AI 없이)
- [ ] `문서` **[필수]** 프로젝트 설명 1분/3분 스크립트
- [ ] `코테` **[필수]** 모의 시험 1회(시간 제한, AI 없이)
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** 답변 스크립트 · 모의 코테 기록

**🏁 완료 기준(DoD)**
- 질문 은행의 90% 이상을 막힘없이 답하고, 모의 코테에서 3문제 중 2문제 이상 해결한다.

**🤖 AI 프롬프트**
```text
너는 국내 게임회사 UE 클라이언트 신입 기술 면접관이야. 내 포트폴리오 요약(첨부)을 보고 실제 면접처럼 질문을 하나씩 해줘. 내가 답하면 다음 질문 전에 '좋았던 점 1개, 보완점 1개'만 짧게 피드백해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 이어서(오늘 분량) · TIL
- Day 2 (화, 약 3시간): 과제1 질문 은행 답변 스크립트 작성 → 소리 내어 녹음 → 다시 듣고 수정 · TIL
- Day 3 (수, 약 3시간): 과제2 AI 면접관 모드로 내 코드 꼬리 질문 리허설 3회 (질문만 받고 답은 A… · TIL
- Day 4 (목, 약 3시간): 과제3 이어서(오늘 분량) · TIL
- Day 5 (금, 약 3시간): 과제4 프로젝트 설명 1분/3분 스크립트 · TIL
- Day 6 (토, 약 5.5시간): 과제3 모의 코딩테스트 3회(시간 제한, AI 없이) · 코테 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog

**📒 이번 주 Git 기록**
- 남길 기록: 학습 로그: 면접 답변 스크립트
- 남길 기록: 학습 로그: 모의 코테 기록
- 주간 Devlog: `docs/devlog/W23.md` (🔔 알림 → 주간 Devlog)

---

<a id="w24"></a>

#### W24 · 지원 · v1.0.0 · 6개월 회고

🏁 **릴리즈:** v1.0.0 · 최종

> 🎯 **목표:** 학습 기록을 **지원서의 근거**로 바꾸고, 지원 과정도 기록으로 남긴다.

**핵심 개념**
- 공고 요구사항 ↔ 내 증거(링크) 매핑
- 이력서 1쪽 + 자기소개서: C#/유니티 → UE C++ 전환 스토리를 '학습 과정 기록'으로 증명
- 6개월을 숫자로: 커밋·PR·TS·ADR 개수, 코테 문제 수, 성능 개선 %

**✅ 과제**
- [ ] `문서` **[필수]** 지원 회사 10곳 리스트 + 공고 요구사항 ↔ 내 증거 매핑표
- [ ] `문서` **[필수]** 이력서 1쪽 + 자기소개서
- [ ] `Git` **[필수]** Release **v1.0.0** + `CHANGELOG.md` 정리
- [ ] `문서` **[필수]** 6개월 회고 블로그(숫자 포함)
- [ ] `문서` **[필수]** 지원 시작 + 면접 후 복기 문서화(지원 기록도 학습 기록)
- [ ] `코테` **[필수]** 모의 시험 1회(시간 제한, AI 없이)
- [ ] `기록` **[필수]** 매일 TIL + 주간 Devlog 1편 (부록 템플릿)

**📦 산출물:** v1.0.0 · 이력서·자소서 · 6개월 회고

**🏁 완료 기준(DoD)**
- 지원서의 모든 주장에 링크(PR·TS·영상·리포트)가 붙어 있다.

**🤖 AI 프롬프트**
```text
아래 채용 공고 요구사항과 내 포트폴리오 링크 목록을 보고, 요구사항별로 '내가 제시할 증거'를 매핑한 표를 만들어줘. 증거가 약한 항목은 솔직하게 표시하고, 1주 안에 보강할 수 있는 방법을 제안해줘.
```

**📅 요일별 계획** (날짜는 HTML의 '오늘 학습'에서 시작일을 정하면 계산됩니다)
- Day 1 (월, 약 3시간): 이번 주 개념·엔진 소스 공부 · 과제1 지원 회사 10곳 리스트 + 공고 요구사항 ↔ 내 증거 매핑표 · TIL
- Day 2 (화, 약 3시간): 과제2 이어서(오늘 분량) · TIL
- Day 3 (수, 약 3시간): 과제2 이력서 1쪽 + 자기소개서 · TIL
- Day 4 (목, 약 3시간): 과제4 6개월 회고 블로그(숫자 포함) · TIL
- Day 5 (금, 약 3시간): 과제5 지원 시작 + 면접 후 복기 문서화(지원 기록도 학습 기록) · TIL
- Day 6 (토, 약 5.5시간): 보충 · 이번 주 문서 다듬기 · 코테 · TIL
- Day 7 (일, 약 2.5시간): 주간 복습(자가 점검 전체) + 🔔 주간 Devlog
- 🔔 알림으로 하는 일: 릴리즈

**📒 이번 주 Git 기록**
- 브랜치: `docs/changelog`
- 남길 기록: `CHANGELOG.md`
- 남길 기록: `docs/retro/6months.md`
- 🏷 릴리즈: `v1.0.0` (🔔 알림 → 릴리즈)
- 주간 Devlog: `docs/devlog/W24.md` (🔔 알림 → 주간 Devlog)

**🚪 M6 관문 — 다음 단계로 넘어가는 조건**

- [ ] 딥다이브 리포트
- [ ] 영상·README·PDF 완성
- [ ] 질문 은행 90% 답변
- [ ] 지원 10곳 + 매핑표
- [ ] v1.0.0 + 6개월 회고

---

## 4. AI 학습법

### AI 의존도 3단계 — 매달 한 칸씩 내려간다

| 레벨 | 방식 | 규칙 | 적용 구간 |
|---|---|---|---|
| **L1** | AI가 쓰고 → 내가 해설 | AI가 초안을 쓰고, 나는 모든 줄에 해설 주석을 달아 다시 쓴다. 설명 못 하는 줄은 질문해서 해결한 뒤 커밋. | W1~W8 |
| **L2** | 내가 쓰고 → AI가 리뷰 | 설계·단계 힌트만 받고 내가 작성한다. AI 리뷰 의견마다 '채택/거절 + 이유'를 PR에 남긴다. | W9~W20 |
| **L3** | AI 없이 쓰고 → AI로 검증 | AI 없이 작성한 뒤 엣지 케이스·대안만 AI에게 묻는다. 면접·코테 대비 모드. | W17~W24 |

### AI 페어 프로그래밍 5원칙

1. **설명 못 하는 코드는 커밋하지 않는다** — PR 셀프 리뷰 체크리스트 1번. 모르는 줄은 AI에게 다시 묻고, 이해한 내용을 TIL에 내 말로 쓴다.
2. **엔진 API는 소스에서 확인한다** — AI는 UE4 시절 API나 존재하지 않는 함수를 지어내기도 한다. Visual Studio에서 F12(정의로 이동)로 시그니처·주석을 직접 확인하고, 틀렸던 사례는 TIL에 기록한다(면접 소재).
3. **15분 룰** — 버그는 15분 동안 직접 좁힌다(로그·중단점·콜스택). 그다음 AI에게 '내가 시도한 것'과 함께 묻는다.
4. **힌트 먼저, 코드는 마지막** — 새 기능은 '설계·단계·주의점'부터 묻는다. 코드를 받더라도 마지막 단계에서.
5. **PR에 AI 활용 내역을 남긴다** — 무엇을 AI가 도왔고, 무엇을 검증·수정했는지. 'AI를 책임 있게 쓰는 개발자'라는 증거가 된다.

### AI-Off 챌린지 (AI 없이 재구현)

| 주차 | 이름 | 과제 |
|---|---|---|
| W4 | AI-Off ① | `AFloatingItem`을 빈 액터에서 30분 안에 재작성 |
| W8 | AI-Off ② | `IInteractable` + 문 상호작용을 60분 안에 재구현 |
| W13 | AI-Off ③ | HealthComponent + 데미지 + 사망 델리게이트 + 체력바를 90분 안에 |
| W23 | AI-Off ④ | 모의 코테 3회 + 질문 은행 녹음 답변 |

### 프롬프트 라이브러리

**코드 해설 (L1)**
```text
나는 C#/유니티 2개월 차이고 C++은 처음이야. 아래 언리얼 C++ 코드를 한 줄씩 C#과 비교해서 설명해줘. *, &, ->, ::, 매크로(UCLASS/UPROPERTY 등)의 의미를 짚고, 마지막에 이해 확인 질문 3개를 내줘. 정답은 내가 답한 뒤에 알려줘.
```
**힌트 모드 (L2)**
```text
[기능]을 언리얼 C++로 구현하려고 해. 정답 코드는 주지 말고 구현 단계를 5단계로 쪼개서 각 단계의 목표와 사용할 클래스·함수 이름만 알려줘. 내가 단계별 코드를 보여주면 그때 리뷰해줘.
```
**코드 리뷰**
```text
Epic C++ 코딩 표준과 UE 5.8 기준으로 아래 코드를 리뷰해줘. GC 안전성(UPROPERTY/TObjectPtr), 네트워크 권한, Tick 사용, 하드 레퍼런스, 네이밍, const를 확인하고 심각도 순으로 정리해줘. 수정 코드는 내가 요청할 때만.
```
**에러 해석**
```text
이 컴파일/링크 에러 원문을 해석해줘. 원인 후보를 가능성 높은 순서로 3개, 각각 확인하는 방법을 알려줘. 고치는 코드는 마지막에 하나만.
```
**디버깅 (15분 룰 이후)**
```text
증상: [ ]. 재현 단계: [ ]. 내가 이미 확인한 것: [로그/중단점 결과]. 다음에 확인할 것을 우선순위로 3개만 제안해줘.
```
**엔진 소스 길잡이**
```text
UE 5.8의 [클래스::함수]가 내부적으로 어떤 순서로 동작하는지, 내가 엔진 소스에서 직접 따라가 볼 수 있게 파일명·함수명만 순서대로 짚어줘. 확실하지 않은 부분은 '확인 필요'로 표시해줘.
```
**면접관 모드**
```text
너는 게임회사 UE 클라이언트 신입 면접관이야. 내 코드(첨부)를 보고 꼬리 질문 5개를 하나씩 해줘. 내가 답하면 채점하고 부족한 부분만 짧게 보충해줘.
```
**설계 비교**
```text
[문제]를 해결하는 설계 선택지 2~3개를 장단점 표로 비교해줘. 6개월 포트폴리오 규모라는 전제로 추천 1개와 이유를 붙여줘. 코드는 쓰지 마.
```

> **Unreal MCP 참고:** UE 5.8에는 AI 에이전트(Claude Code, Cursor 등)가 에디터 기능을 도구로 호출할 수 있는 실험적 플러그인 'Unreal MCP'가 들어 있다. 에디터 조작을 AI에 맡기면 배울 기회가 줄어드므로 W1~W20 핵심 학습에는 쓰지 않고, W21 딥다이브 A(에디터 자동화)에서만 쓴다. 실험 기능이라 버전마다 동작이 다를 수 있다.

---

## 5. 포트폴리오 & Git

### 기록이 곧 포트폴리오다

| 기록 | 보여주는 역량 | 채용에서의 쓰임 |
|---|---|---|
| 매일 TIL (학습 로그 저장소) | 꾸준함 · 학습 방식 | GitHub 잔디, '어떻게 공부했나요?'에 대한 근거 |
| 주간 Devlog | 계획 대비 실행력 | 주차별 목표 vs 결과 표 → 자기 관리 능력 |
| 트러블슈팅(TS) | 문제 해결력 | 면접 단골 '가장 어려웠던 버그' 답변 재료 |
| ADR(설계 결정 기록) | 설계 사고 | '왜 그렇게 만들었나요?'에 대안 비교로 답함 |
| 엔진 소스 노트 | 엔진 이해 깊이 | '동작 원리'를 소스 근거로 설명 |
| 이슈 · PR · 릴리즈 | 협업 습관 · 점진적 개발 | v0.1 → v1.0 변경 이력, 셀프 리뷰 |
| 성능 리포트 | 측정 기반 최적화 | 전/후 ms 수치 |
| AI-Off 기록 · PR의 AI 활용 내역 | AI에 의존하지 않는 기본기 | 'AI 없이도 할 수 있나요?'에 대한 증거 |

### 저장소 구조

```text
UE5-ActionArena/                 ← 게임 프로젝트 (메인 포트폴리오)
├── Source/ActionArena/
│   ├── Character/       ArenaCharacterBase, PlayerCharacter, Enemy, AnimInstance
│   ├── Combat/          CombatComponent, AnimNotifyState_*, Projectile
│   ├── Interaction/     IInteractable, InteractionComponent, Door, Lever, Pickup
│   ├── AI/              EnemyAIController, BTTask_*, BTService_*
│   ├── AbilitySystem/   ASC, AttributeSet, Abilities/, Effects/
│   ├── Game/            GameMode, GameState, PlayerState, PlayerController, CheatManager
│   ├── Data/            CharacterStatData, WeaponData, 테이블 Row 구조체
│   ├── UI/              HUDWidget, 메뉴 위젯
│   ├── Subsystems/      ProjectilePoolSubsystem
│   └── Tests/           Automation Tests
├── Content/             ← Git LFS · 직접 만든 BP·DataAsset·맵만 (외부 에셋 제외)
├── Config/
├── docs/
│   ├── devlog/          W01.md, W02.md …
│   ├── troubleshooting/ TS-001-uproperty-gc.md …
│   ├── adr/             ADR-0001-interaction-detection.md …
│   ├── engine-notes/    01-actor-lifecycle.md …
│   ├── perf/            01-soft-reference.md, 02-performance-report.md
│   ├── retro/           M1.md … M5.md, 6months.md (월간 회고)
│   └── images/          GIF·스크린샷 (5MB 이하)
├── .github/             ISSUE_TEMPLATE/, pull_request_template.md
├── .gitignore  .gitattributes  CLAUDE.md(AI 규칙)
├── CHANGELOG.md  TESTING.md
└── README.md

unreal-study-log/                ← 학습 로그 + 이 커리큘럼 (C:\Projects에 Clone)
├── curriculum/          이 커리큘럼 HTML·MD (브라우저로 HTML을 열어 매일 학습)
├── ue5-til/             매일 TIL · 2026-12-01-주제.md (CSharpCourse의 TodayILearn과 구분)
├── cpp-basics/          포인터·참조 실험, 해설 주석 코드 (00-first-taste = 첫 C++)
├── coding-test/         baekjoon/, programmers/ (C++)
├── ai-off/              AI-Off 챌린지 기록
├── interview/           면접 답변 스크립트
└── README.md            폴더 안내 · 진행 기록
```

### 작업 흐름

- **이슈** — 작업 1개 = 이슈 1개. 라벨(feat/bug/docs/perf) + 마일스톤(M1~M6)
- **브랜치** — `feat/combo-window`, `fix/double-damage`, `docs/ts-007` — main은 항상 실행 가능
- **커밋** — 작게, 자주. 타입(scope): 요약 — 한국어 요약 OK
- **PR** — 템플릿 사용, 셀프 코멘트, AI 활용 내역, GIF. merge 후 브랜치 삭제
- **릴리즈** — 월말·기능 묶음마다 태그 + Release 노트 + 영상/GIF + CHANGELOG

### 릴리즈 계획

| 버전 | 주차 | 이름 | 핵심 | 공개 자료 |
|---|---|---|---|---|
| v0.1.0 | W4 | 움직이는 캐릭터 | Enhanced Input · 방향 판정 시각화 | 20초 GIF |
| v0.2.0 | W8 | 콤보 전투 + 데이터 주도 무기 | 몽타주·노티파이·Sweep 판정·DataAsset | 45초 영상 |
| v0.3.0 | W13 | 싱글플레이 MVP | AI 2종 · 게임 루프 · UI · 세이브 · 패키징 | 90초 영상 + 빌드 |
| v0.4.0 | W17 | 2인 협동 | 리플리케이션 · GAS · 예측 비교 | 반응성 비교 영상 |
| v0.5.0 | W20 | 릴리즈 후보 | 최적화 · 테스트 · 타격감 | 전/후 GIF |
| v1.0.0 | W24 | 최종 | 딥다이브 + 문서·영상·PDF 완성 | 2~3분 시연 영상 |

> **용량·라이선스:** GitHub Free 개인 계정의 LFS 기본 제공량은 저장 10GiB · 월 대역폭 10GiB(결제수단이 없으면 초과 시 차단). 원본 에셋·외부 에셋은 올리지 않고, Fab 등 외부 에셋 원본을 공개 저장소에 올리면 라이선스 위반이 될 수 있으니 `Content/ThirdParty/`처럼 폴더를 분리해 `.gitignore`하고 README에 받는 방법을 적는다. 영상은 YouTube, 빌드는 Release 첨부(파일당 2GiB 이하).

---

## 6. Git 기록 가이드 (GitHub Desktop)

> 명령어는 쓰지 않습니다. 모든 기록은 **GitHub Desktop**의 버튼과 GitHub 웹사이트로 남깁니다. '📅 오늘 학습' 카드의 마지막 단계와 🔔 알림이 그날 해야 할 기록을 순서대로 안내하니, 이 탭은 처음 설정과 문제가 생겼을 때 찾아보는 참고서로 쓰세요.

> ⚠️ 학원에서 정한 규칙(커밋 메시지·파일명·PR 방식)이 있으면 그 규칙이 우선입니다. 이 가이드는 언리얼용으로 새로 만드는 저장소 2개(게임 프로젝트 `UE5-ActionArena`, 학습 로그 `unreal-study-log`)를 기준으로 합니다.  
> 버튼 이름은 GitHub Desktop 화면에 영어로 보이는 그대로 적었습니다. 버전에 따라 이름이 조금 다를 수 있어요.

### 왜 이 방식인가
- **몰아서 쓰지 않고 그날 남긴다** — 기록 날짜가 커밋 시간으로 증명됩니다. 6개월 뒤에 기억으로 재구성한 기록은 증거가 약합니다.
- **형식은 도구가, 내용은 내 말로** — 카드가 칸과 문구를 채워 주고, 나는 배운 것·막힌 것만 내 말로 씁니다. AI가 대신 쓴 기록은 면접관이 금방 알아봅니다.
- **GitHub 기본 기능이 기록을 정리해 준다** — PR·마일스톤·릴리즈만 써도 '계획 → 실행 → 성과'가 저절로 연결됩니다.

### Git 5분 개념 (게임 비유)

| 용어 | 비유 | 뜻 |
|---|---|---|
| **저장소 (repository)** | 게임 폴더 + 모든 세이브 기록 | 프로젝트 파일과 변경 이력 전체. 내 컴퓨터와 GitHub에 하나씩 있다. |
| **커밋 (commit)** | 세이브 포인트 | '무엇을 했는지' 한 줄 메시지와 함께 그 순간의 파일 상태를 저장한다. Desktop의 `Commit to …` 버튼. |
| **브랜치 (branch)** | 세이브 슬롯 분기 | `main`은 항상 실행되는 본편. 새 기능은 분기 슬롯(`feat/...`)에서 만들고 끝나면 합친다. Desktop 위쪽 `Current Branch`. |
| **푸시 (push)** | 클라우드 세이브 업로드 | 내 컴퓨터의 커밋을 GitHub에 올린다. Desktop의 `Push origin` 버튼. |
| **풀 리퀘스트 (PR)** | 작업 보고서 | '이 분기를 본편에 합칠게요' 요청서. 무엇을·왜·어떻게 테스트했는지 적는 곳이라 **포트폴리오에서 가장 많이 읽히는 기록**이다. |
| **머지 (merge)** | 분기를 본편에 합치기 | GitHub 웹의 PR 화면에서 `Squash and merge`. 혼자여도 PR → 머지 순서를 지킨다. |
| **이슈 (issue)** | 퀘스트 카드 | 할 일과 완료 조건. PR 본문에 `Closes #3`을 쓰면 머지할 때 자동으로 닫힌다. |
| **태그 · 릴리즈** | 버전 스냅샷 + 패치 노트 | `v0.1.0`처럼 이름 붙인 시점과, GIF·변경 내역을 담은 발표 페이지. GitHub 웹의 `Releases`. |
| **마일스톤** | 챕터 목표 | 이슈 묶음(M1~M6). 달성률이 자동으로 표시돼 '계획대로 해냈다'의 증거가 된다. |

### 어디에 무엇을 남기나

| 기록 장소 | 무엇을 | 언제 |
|---|---|---|
| 커밋 메시지 | 무엇을 바꿨나 (한 줄) | 작업이 끝날 때마다 · 하루 1~3회 |
| PR 본문 | 왜 · 어떻게 · 테스트 방법 · GIF · AI 활용 | 과제(기능) 하나를 끝낸 날 — 오늘 학습 카드에 자동으로 나옴 |
| 이슈 | 할 일 · 완료 조건 | 작업 시작 전 (선택) |
| TIL (학습 로그) | 오늘 배운 것을 내 말로 | 매일 |
| docs/ 문서 | 트러블슈팅 · 설계 결정 · 엔진 노트 · Devlog | 주 1~2편 |
| 릴리즈 노트 | 이번 버전에서 해낸 것 | 릴리즈 주간 (6회) |
| README | 전체 요약 + 증거 링크 | 월 1회 갱신 |

> 규칙 하나만 기억하기: **코드는 브랜치 + PR, 문서(TIL·Devlog·회고)는 main에 바로 커밋해도 된다.**

### 처음 한 번 설정

**GitHub Desktop 설치 · 로그인**

1. **설치** — desktop.github.com에서 GitHub Desktop을 내려받아 설치 파일 실행 (자동으로 설치되고 바로 실행된다)
2. **로그인** — `Sign in to GitHub.com` → 브라우저에서 `Authorize desktop` 승인 → Desktop으로 돌아오기
3. **계정 확인** — 메뉴 `File` → `Options…` → `Accounts`에 내 GitHub 계정이 보이면 OK
4. **이름·이메일** — 같은 창의 `Git` 탭에서 Name·Email이 GitHub 계정과 같은지 확인 → `Save`
5. **작업 폴더** — 파일 탐색기(`Win+E`) → `내 PC` → `로컬 디스크 (C:)`에 `Projects` 폴더 만들기 → 앞으로 모든 저장소를 `C:\Projects`에 둔다 (한글·공백 없는 짧은 경로, OneDrive 폴더는 피하기)
6. **무료 한도 확인** — GitHub 웹 Settings의 결제(Billing) 메뉴에서 Git LFS 무료 한도 확인(저장 10GiB · 월 10GiB). 결제수단이 없으면 초과 시 업로드가 막힐 뿐 요금은 나가지 않는다

**학습 로그 저장소를 Windows PC로 가져오기 (Clone)**

1. **Clone 열기** — GitHub Desktop 메뉴 `File` → `Clone repository…` → `GitHub.com` 탭
2. **저장소 고르기** — 목록에서 `unreal-study-log` 선택 → 아래 `Local path`를 `C:\Projects\unreal-study-log`로 → `Clone`
3. **확인** — 메뉴 `Repository` → `Show in Explorer` → `curriculum`·`ue5-til`·`cpp-basics`·`coding-test` 폴더가 보이면 성공
4. **커리큘럼 열기** — `curriculum` 폴더의 `UnrealEngine_6Month_Study_Guide.html`을 **Chrome 또는 Edge**로 열고 즐겨찾기에 추가 — 앞으로 매일 여기서 시작
5. **맥에서 체크한 게 있다면** — 맥 브라우저에서 ⚙ → `진척도 내보내기` → 받은 파일을 Windows로 옮겨 ⚙ → `진척도 가져오기` (없으면 건너뛰기)

**게임 저장소 만들기 (UE 프로젝트 연결)**

1. **프로젝트 만들기** — 언리얼 에디터: Games → Blank → C++ · Desktop · Scalable · Starter Content 끔 · 위치 `C:\Projects` · 이름 `ActionArena` → Create → Visual Studio와 에디터가 열리면 에디터는 한 번 닫기
2. **LFS 설정 파일 넣기** — 아래 '파일 받기'로 `gitattributes.txt`를 받기 → 파일 탐색기 위쪽 `보기` → `표시` → `파일 확장명` 켜기 → 파일을 `C:\Projects\ActionArena`로 옮기고 이름을 `.gitattributes.`(**끝에 점 하나 더**)로 바꾸면 끝의 점이 사라지며 `.gitattributes`가 된다. `CLAUDE.md`도 같은 폴더에 넣기
3. **저장소로 만들기** — GitHub Desktop `File` → `Add Local Repository…` → `Choose…`로 `ActionArena` 폴더 선택 → 안내 문구의 `create a repository` 클릭
4. **만들기 창** — Name은 **그대로**(`ActionArena`) · Git Ignore는 `UnrealEngine` 선택 · README 체크 안 함 → `Create Repository` → Git LFS를 묻는 창이 뜨면 `Initialize Git LFS`
5. **빠진 파일 확인** — 왼쪽 `Changes` 탭에 `Binaries`·`Intermediate`·`Saved`·`DerivedDataCache`가 **보이면 안 됨**(보이면 멈추고 질문). `Thumbs.db`·`desktop.ini` 같은 윈도우 파일이 보이면 우클릭 → `Ignore file`. 남은 파일이 있으면 Summary에 `chore: UE 5.8 프로젝트 생성` → `Commit to main`
6. **GitHub에 올리기** — 위쪽 `Publish repository` → Name을 `UE5-ActionArena`로 바꾸고 `Keep this code private` 체크 해제 → `Publish Repository`
7. **웹에서 정리 도구 켜기** — 브라우저에서 저장소 열기 → `Issues` → `Labels`(feat·bug·docs·perf), `Milestones`(M1~M6, 마감일 = 각 단계 마지막 주 일요일) → `Projects` → `New project` → Board

**첫 PR 해 보기**

1. **오늘이 첫 PR** — 이 과제를 끝내면 오늘 카드의 **기록 ① Push → ② PR** 순서로 생애 첫 PR을 만든다
2. **이슈 먼저 (선택)** — 브라우저에서 `UE5-ActionArena` → `Issues` → `New issue` → 제목 `AFloatingItem 액터 만들기` → `Submit new issue` → 번호(예: #1)를 PR 카드의 '이슈 번호'에 넣으면 합칠 때 이슈가 자동으로 닫힌다
3. **이후 규칙** — 앞으로 과제를 끝낸 날마다 같은 순서로 PR을 남긴다. 올릴 변경이 없는 날은 카드의 '건너뛰기'

`.gitattributes` 내용 (게임 저장소를 만들기 전에 프로젝트 폴더에 넣기):
```gitattributes
# 언리얼 바이너리 에셋 → Git LFS
*.uasset filter=lfs diff=lfs merge=lfs -text
*.umap   filter=lfs diff=lfs merge=lfs -text
*.fbx    filter=lfs diff=lfs merge=lfs -text
*.wav    filter=lfs diff=lfs merge=lfs -text

# 텍스트 줄바꿈 정규화
* text=auto
```

### 매일: 게임 작업 올리기 (커밋 · Push)

1. **저장소 고르기** — GitHub Desktop 위쪽 `Current Repository` → `ActionArena`
2. **브랜치 확인** — `Current Branch`가 오늘 작업 브랜치인지 확인. **처음이면**: `Current Branch`를 `main`으로 두고 `Fetch origin`(→ `Pull origin`이 뜨면 클릭) → `Current Branch` → `New Branch` → 아래 이름 붙여넣기 → `Create Branch` (바뀐 파일을 가져갈지 물으면 `Bring my changes to …`)
3. **바뀐 파일 확인** — 왼쪽 `Changes` 목록에 오늘 만든 파일이 보이는지 확인 (`Binaries`·`Intermediate`가 보이면 커밋하지 말고 질문)
4. **메시지 쓰기** — 왼쪽 아래 `Summary` 칸에 아래 커밋 메시지 붙여넣기
5. **커밋** — `Commit to …` 버튼 클릭
6. **올리기** — 위쪽 `Publish branch`(처음) 또는 `Push origin` 클릭 → 버튼이 `Fetch origin`으로 바뀌면 완료

### 기능이 완성되면: PR 열기 → 합치기

1. **브랜치 확인** — GitHub Desktop `Current Branch`가 PR로 올릴 작업 브랜치인지 확인 (Push까지 끝난 상태)
2. **PR 열기** — 메뉴 `Branch` → `Create pull request` (Ctrl+R) → 브라우저에 GitHub 화면이 열린다
3. **내용 붙이기** — 제목 칸에 PR 제목, 본문 칸에 PR 본문을 붙여넣기 → GIF·영상 파일을 본문에 끌어다 놓기
4. **만들기** — 초록색 `Create pull request` 클릭
5. **셀프 리뷰** — PR 화면 `Files changed` 탭 → 설명하고 싶은 코드 줄 번호 옆 `+` → 왜 이렇게 했는지 한두 줄 → `Add single comment`
6. **합치는 방식 고르기** — `Conversation` 탭 아래 초록 버튼 오른쪽 **▾** → `Squash and merge` 선택 (한 번 고르면 다음부터 기본값이 된다)
7. **합치기** — `Squash and merge` → `Confirm squash and merge` → 보라색 `Merged`가 뜨면 `Delete branch`
8. **내 컴퓨터 정리** — GitHub Desktop `Current Branch` → `main` → `Fetch origin` → `Pull origin` → 메뉴 `Branch` → `Delete…`로 방금 쓴 작업 브랜치 지우기 (다음 날은 새 브랜치에서 시작)

### 매일: TIL 올리기

1. **저장소 고르기** — GitHub Desktop 위쪽 `Current Repository` → `unreal-study-log`
2. **파일 넣기** — 메뉴 `Repository` → `Show in Explorer` → `ue5-til` 폴더 열기 → 파일 탐색기 왼쪽 `다운로드` 폴더의 TIL 파일을 끌어다 넣기 (📁 바로 저장했다면 건너뛰기)
3. **메시지 쓰기** — Desktop 왼쪽 `Changes`에 파일이 보이면 `Summary` 칸에 아래 메시지 붙여넣기
4. **커밋·올리기** — `Commit to main` → 위쪽 `Push origin`

### 주간 Devlog · 월간 회고 올리기

1. **저장소 고르기** — GitHub Desktop `Current Repository` → `ActionArena`, `Current Branch` → `main` → `Fetch origin`(→ `Pull origin`이 뜨면 클릭)
2. **파일 넣기** — 메뉴 `Repository` → `Show in Explorer` → `docs/devlog(또는 docs/retro)` 폴더 열기(없으면 `docs` 안에 만들기) → 다운로드 폴더의 파일 끌어다 넣기
3. **내 말로 채우기** — 그 파일을 Visual Studio나 메모장으로 열어 빈칸을 내 말로 채우고 저장
4. **커밋·올리기** — Desktop `Summary`에 아래 메시지 붙여넣기 → `Commit to main` → `Push origin`

### 릴리즈 만들기 (GitHub 웹)

1. **릴리즈 페이지** — 브라우저에서 `UE5-ActionArena` 저장소 → 오른쪽 `Releases` → `Create a new release`(또는 `Draft a new release`)
2. **태그 만들기** — `Choose a tag` → 아래 버전 이름 입력 → `Create new tag: … on publish` 클릭 (Target은 `main`)
3. **내용 붙이기** — `Release title`에 제목, 큰 칸에 본문 붙여넣기 → (선택) `Generate release notes`로 PR 목록 추가 → GIF·영상 끌어다 놓기
4. **공개** — `Publish release` 클릭 → GitHub Desktop에서 `Fetch origin` 한 번

### GIF · 영상 만들기

1. **녹화** — Windows 11 **캡처 도구**(시작 메뉴에서 '캡처 도구') → 🎥 녹화 → `+ 새로 만들기` → 언리얼 뷰포트 영역만 드래그 → `시작` → 5~15초 시연 → `중지` → 저장 (.mp4)
2. **PR·이슈엔 그대로** — .mov 파일을 GitHub 본문 칸에 그대로 끌어다 놓아도 된다 (10MB 이하 권장)
3. **GIF로 만들기** — 무료 프로그램 **ScreenToGif**(screentogif.com) 설치 → `Recorder` → 뷰포트 영역에 창을 맞추고 녹화 → `Stop` → 편집 창에서 `Save as` → GIF (너비 800 정도) → README·Devlog에 사용
4. **잘 찍는 요령** — 기능 하나만, 짧게, 판정 범위는 디버그 드로잉을 켜고 찍는다

### 매주 · 매달
- **주간 Devlog (일요일)** — 🔔 알림의 'W0X 주간 Devlog'를 누르면 이번 주 과제 결과가 채워진 초안이 나온다 → 내 말로 채우고 Desktop으로 올리기
- **TIL 승격** — 이번 주 TIL 중 '문제 → 해결'은 트러블슈팅, '선택 → 이유'는 설계 결정, '원리 → 근거'는 엔진 노트로 옮겨 쓴다 (템플릿 탭)
- **이슈 정리** — GitHub 웹에서 끝난 이슈 닫기 · 다음 주 과제를 이슈로 만들기 · 마일스톤 지정
- **릴리즈 (6회)** — 🔔 알림의 '릴리즈'를 누르면 릴리즈 노트 초안과 GitHub 웹 순서가 나온다
- **월간 회고** — 🔔 알림의 '월간 회고'를 누르면 진척도·관문 체크 상태가 채워진 초안이 나온다 → Keep·Problem·Try를 내 말로
- **README 갱신** — 이번 달 대표 기록 3개(TS·ADR·영상)를 README 증거 표에 링크하고, 마일스톤을 닫는다

### 망했을 때

| 상황 | 이렇게 | 주의 |
|---|---|---|
| 어디까지 했는지 모르겠다 | GitHub Desktop 화면(위쪽 `Current Repository`·`Current Branch`, `Changes`·`History` 탭)을 스크린샷으로 찍어 AI·멘토에게 질문 | 보기만 하는 건 아무것도 바뀌지 않으니 안전 |
| 커밋 메시지를 잘못 썼다 (Push 전) | `History` 탭 → 맨 위 커밋 우클릭 → `Amend Commit…` → 메시지 고치기 | 이미 Push했다면 그냥 두는 게 안전 |
| 방금 커밋을 취소하고 싶다 (Push 전) | 커밋 직후 왼쪽 아래에 생기는 `Undo` 버튼 | 파일 변경은 그대로 남고 커밋만 취소된다 |
| main에서 작업을 시작해 버렸다 (커밋 전) | `Current Branch` → `New Branch` → 이름 입력 → `Bring my changes to …` 선택 | 바뀐 파일이 새 브랜치로 따라온다 |
| 파일 변경을 버리고 싶다 | `Changes`에서 파일 우클릭 → `Discard Changes…` | ⚠️ 되돌리기 어렵다. 확실할 때만 |
| Push가 안 된다 | 위쪽 버튼이 `Pull origin`이면 먼저 누르고 → 그다음 `Push origin` | GitHub 쪽에 내 컴퓨터에 없는 변경이 있을 때 |
| 충돌(conflict) 창이 떴다 | 코드 파일: 파일 옆 메뉴로 편집기에서 열어 `<<<<<<<`~`>>>>>>>` 구간 정리 후 저장 / 에셋(.uasset): 어느 쪽 파일을 쓸지 고르기 → `Continue merge`(또는 `Commit merge`) | 헷갈리면 멈추고 화면을 찍어 질문 |
| `Binaries`·`Intermediate`가 Changes에 잔뜩 보인다 | 커밋하지 말 것. `.gitignore`가 프로젝트 폴더 최상위에 있는지 확인 (파일 탐색기 `보기` → `표시` → `숨긴 항목`으로 숨김 파일 보기) | 이미 커밋했다면 멘토와 함께 정리 |
| Git LFS를 묻는 창이 떴다 | `Initialize Git LFS` 클릭 | `.uasset`을 LFS로 올리기 위해 필요 |
| 이 버튼은 확인받고 누르기 | `Discard All Changes…`, `Force push`, 브랜치 삭제 | ⚠️ 작업이 사라질 수 있다 |

### 메모를 TIL로 정리할 때 쓰는 AI 프롬프트 (내 문장은 그대로)
```text
아래는 내가 오늘 공부하며 적은 메모야. 문장은 바꾸지 말고 TIL 템플릿(키워드 / 배운 것 / 코드·실험 / 막힌 점 → 해결 / 다음 할 일) 칸에 맞게 배치만 해줘. 빈 칸은 채우지 말고 '비어 있음'이라고 표시해줘.
```

---

## 7. 평가 기준 & 관문

### 루브릭 (월말 자가 평가 · 멘토 평가 공용)

| 기준 | 1 미흡 | 2 기본 | 3 우수 | 4 탁월 |
|---|---|---|---|---|
| **기능 완성도** | 데모 중 오류·미완성 | 핵심 흐름 동작 | 예외·엣지 케이스 처리 | 멀티·저프레임까지 검증, 영상 증거 |
| **코드 품질** | 하드코딩·거대 클래스 | C++ 베이스 + BP 자식, 네이밍 준수 | 컴포넌트로 책임 분리, 데이터 분리, GC 안전 | 확장 지점 설계 + 테스트, 리뷰하기 좋은 PR 크기 |
| **엔진 이해** | '이렇게 하면 된다'만 앎 | 동작 원리를 말로 설명 | 엔진 소스·콜스택을 근거로 설명 | 대안 비교·트레이드오프를 ADR로 |
| **문제 해결 기록** | 기록 없음 | TIL에 메모 | TS 템플릿으로 원인·해결 | 재발 방지(테스트·규칙)까지 |
| **협업 습관(Git)** | 몰아서 커밋 | 기능 단위 커밋 | 이슈 ↔ PR 연결, 셀프 리뷰 | 릴리즈 노트 · CHANGELOG · 라벨 운영 |
| **AI 활용** | AI 코드를 그대로 사용 | 모든 줄 해설 주석 | 직접 작성 후 AI 리뷰, 채택 근거 기록 | AI-Off 재구현 성공, AI 오류를 소스로 검증한 사례 |

> 목표 평균: M1~M2 2점 · M3~M4 2.5~3점 · M5~M6 3점 이상. 1점 항목이 있으면 다음 단계로 넘어가기 전에 그 항목부터 보강한다.

관문 체크리스트는 각 단계 마지막 주차 아래에 있습니다.

---

## 8. 면접 질문 은행

주차별 자가 점검 질문이 곧 면접 질문입니다. 답은 해당 주차의 접힌 답을 펼쳐 보세요. 아래는 카테고리별 목록과 주차에 없는 일반 질문입니다.

**C++** (21)

- `.h`와 `.cpp`를 나누는 이유는? → [W01](#w01)
- `Mesh->SetRelativeLocation()`에서 `->`와 `.`의 차이는? → [W01](#w01)
- 포인터와 참조의 차이 3가지는? → [W02](#w02)
- 스택과 힙의 차이는? → [W02](#w02)
- `virtual`이 없으면 어떻게 되나? `override`는 왜 붙이나? → [W03](#w03)
- `const FInputActionValue& Value`에서 const와 &의 의미는? → [W04](#w04)
- 람다에서 `[this]` 캡처가 위험한 경우는? → [W05](#w05)
- C++ 추상 클래스와 C# 인터페이스의 차이는? → [W05](#w05)
- const 멤버 함수의 의미는? → [W06](#w06)
- 중복 검사에 `TArray::Contains`와 `TSet` 중 무엇이 나은가? → [W07](#w07)
- C++에서 struct와 class의 차이는? → [W08](#w08)
- 큰 구조체를 값으로 넘기면 무엇이 문제인가? → [W08](#w08)
- `TSharedPtr`과 `TObjectPtr`은 각각 언제 쓰나? → [W09](#w09)
- shared_ptr 순환 참조란? → [W09](#w09)
- 가상 소멸자가 필요한 이유는? → [W13](#w13)
- 복사와 이동의 차이는? → [W13](#w13)
- Rule of Three/Five/Zero란? → [W13](#w13)
- 헤더에서 include 대신 전방 선언을 쓰는 이유는? → [W13](#w13)
- 메모리 누수와 댕글링 포인터의 차이는? → [W13](#w13)
- TArray에 요소를 추가한 뒤 이전에 받아둔 요소 포인터·참조가 위험한 이유는? → [W13](#w13)
<details><summary>static 키워드의 의미 3가지는?</summary>

함수 안 static 변수: 프로그램 수명 동안 유지. 클래스 static 멤버: 모든 인스턴스가 공유. 파일 범위 static: 그 파일 안에서만 보이는 내부 링크.
</details>


**UE 코어** (17)

- `AFloatingItem`의 A, `UStaticMeshComponent`의 U는 무슨 의미인가? → [W01](#w01)
- `GENERATED_BODY()`와 `*.generated.h`는 무엇인가? → [W01](#w01)
- `UPROPERTY` 없는 UObject 포인터 멤버가 위험한 이유는? → [W02](#w02)
- `NewObject`, `CreateDefaultSubobject`, `SpawnActor`의 차이는? → [W02](#w02)
- `FName`/`FString`/`FText`는 각각 언제 쓰나? → [W02](#w02)
- `TWeakObjectPtr`은 언제 쓰나? → [W02](#w02)
- 생성자에서 `GetWorld()`나 다른 액터를 찾으면 안 되는 이유는? → [W03](#w03)
- CDO란 무엇인가? → [W03](#w03)
- `Super::BeginPlay()`를 빼먹으면? → [W03](#w03)
- ActorComponent와 SceneComponent의 차이는? → [W03](#w03)
- 언리얼 인터페이스가 UInterface/IInterface 두 개인 이유는? → [W05](#w05)
- `Cast<IInteractable>` 대신 `Execute_Interact`를 써야 하는 경우는? → [W05](#w05)
- 다이나믹 델리게이트는 언제 쓰나? → [W05](#w05)
- `TakeDamage`를 오버라이드할 때 `Super`를 호출해야 하는 이유는? → [W08](#w08)
- Subsystem의 종류와 수명은? → [W12](#w12)
<details><summary>UHT와 UBT는 무엇인가?</summary>

UHT(Unreal Header Tool): 리플렉션 매크로를 읽어 .generated.h 코드 생성. UBT(Unreal Build Tool): .Build.cs·.Target.cs를 기반으로 모듈 의존성과 빌드를 조율.
</details>

<details><summary>Build.cs의 Public/Private 의존성 차이는?</summary>

Public: 내 public 헤더가 그 모듈 타입을 노출해 나를 쓰는 모듈도 필요로 함. Private: 내 구현(.cpp)에서만 사용. 불필요한 Public 의존은 빌드 시간을 늘린다.
</details>


**게임플레이** (7)

- GameMode와 GameState의 차이는? → [W03](#w03)
- IMC를 여러 개 두는 이유는? → [W04](#w04)
- Overlap 판정과 Trace(Sweep) 판정의 장단점은? → [W07](#w07)
- Object Channel과 Trace Channel의 차이는? → [W07](#w07)
- 투사체를 Tick 이동 대신 ProjectileMovementComponent로 만드는 이유는? → [W11](#w11)
- GameMode와 GameState에 둘 데이터의 구분 기준은? → [W12](#w12)
- 히트스톱을 전체 시간 정지(Global Time Dilation)가 아니라 액터별로 거는 이유는? → [W20](#w20)

**수학** (4)

- 내적 결과가 음수라면 무슨 뜻인가? → [W04](#w04)
- 외적으로 좌/우를 판정하는 방법은? → [W04](#w04)
- 쿼터니언을 쓰는 이유는? → [W04](#w04)
<details><summary>FTransform의 적용 순서와 로컬→월드 변환은?</summary>

스케일 → 회전 → 이동 순으로 적용된다. 자식의 월드 Transform은 부모 월드 Transform에 자식 로컬 Transform을 합성한 결과.
</details>


**애니메이션** (5)

- AnimInstance에서 매 프레임 Cast하면 안 되는 이유는? → [W06](#w06)
- `NativeThreadSafeUpdateAnimation`에서 하면 안 되는 것은? → [W06](#w06)
- 루트 모션이란? 네트워크에서 주의점은? → [W06](#w06)
- AnimNotify와 AnimNotifyState의 차이는? → [W07](#w07)
- 판정을 노티파이에만 의존하면 생길 수 있는 문제는? → [W07](#w07)

**AI** (7)

- Selector와 Sequence의 차이는? → [W10](#w10)
- Latent(지연) Task는 어떻게 동작하나? → [W10](#w10)
- Observer Aborts는 무엇인가? → [W10](#w10)
- Behavior Tree와 StateTree의 차이는? → [W10](#w10)
- AI 시야 감지가 안 될 때 확인 순서는? → [W11](#w11)
- Gameplay Debugger와 Visual Logger의 차이는? → [W11](#w11)
- AIController는 클라이언트에 존재하나? → [W15](#w15)

**UI·에셋** (3)

- UI를 Tick이나 Property Binding으로 갱신하면 문제는? → [W09](#w09)
- 하드 레퍼런스가 메모리를 키우는 이유는? → [W09](#w09)
- 비동기 로드 완료 콜백에서 주의할 점은? → [W09](#w09)

**네트워크** (10)

- Server RPC를 호출할 수 있는 조건은? → [W14](#w14)
- OnRep 함수는 서버에서도 호출되나? → [W14](#w14)
- Reliable RPC를 남발하면? → [W14](#w14)
- NetMulticast와 복제 프로퍼티는 어떻게 골라 쓰나? → [W14](#w14)
- AutonomousProxy와 SimulatedProxy의 차이는? → [W14](#w14)
- 클라이언트에서 체력을 직접 깎으면? → [W15](#w15)
- 스프린트 속도를 RPC로만 바꾸면 끊기는(러버밴딩) 이유는? → [W15](#w15)
- 늦게 접속한 플레이어가 적 상태를 올바르게 보려면? → [W15](#w15)
- NetUpdateFrequency와 Dormancy는? → [W18](#w18)
- (C 선택 시) CMC에서 커스텀 이동을 네트워크 예측되게 하려면? → [W21](#w21)

**GAS** (8)

- ASC를 PlayerState에 둘 때와 Character에 둘 때의 차이는? → [W16](#w16)
- Instant와 Duration/Infinite GameplayEffect의 차이는? → [W16](#w16)
- Replication Mode 3종은? → [W16](#w16)
- 메타 속성(IncomingDamage)을 쓰는 이유는? → [W16](#w16)
- CommitAbility는 무엇을 하나? → [W16](#w16)
- AbilityTask란? → [W17](#w17)
- GameplayCue를 쓰는 이유는? → [W17](#w17)
- 로컬 예측이 반응성을 높이는 원리는? → [W17](#w17)

**최적화** (7)

- Tick 비용을 줄이는 방법 3가지는? → [W03](#w03)
- Tick 대신 타이머를 쓰는 기준은? → [W05](#w05)
- 언리얼에서 오브젝트 풀링 시 주의점은? → [W12](#w12)
- `AsyncSaveGameToSlot`을 쓰는 이유는? → [W12](#w12)
- 프레임 저하 원인이 게임/렌더/GPU 중 어디인지 어떻게 구분하나? → [W18](#w18)
- 측정 없이 최적화하면 안 되는 이유는? → [W18](#w18)
- 적이 많을 때 애니메이션 비용을 줄이는 방법은? → [W18](#w18)

**품질** (3)

- check, ensure, verify의 차이는? → [W19](#w19)
- 테스트하기 쉬운 코드를 만드는 방법은? → [W19](#w19)
- 신입 포트폴리오에서 자동화 테스트가 의미하는 것은? → [W19](#w19)

**설계** (4)

- DataAsset과 DataTable은 언제 각각 쓰나? → [W08](#w08)
- 데이터 주도 설계의 협업상 이점은? → [W08](#w08)
- 공통 베이스 클래스로 리팩터링한 이유는? → [W10](#w10)
- GAS 도입의 비용은? → [W17](#w17)

**협업·Git** (3)

- 언리얼 프로젝트에서 Git에 올리지 않는 폴더와 그 이유는? → [W00](#w00)
- `.uasset`을 Git LFS로 관리하는 이유는? → [W00](#w00)
<details><summary>바이너리 에셋 충돌은 어떻게 관리하나?</summary>

LFS 잠금(lock) 또는 Perforce 체크아웃으로 동시 수정 방지, 에셋 담당 분리, 작은 단위 PR. 텍스트(코드)와 달리 merge가 불가능하다는 점이 핵심.
</details>


**CS** (2)

<details><summary>프로세스와 스레드의 차이는? 언리얼의 주요 스레드는?</summary>

프로세스는 독립 메모리 공간의 실행 단위, 스레드는 프로세스 안에서 메모리를 공유하는 실행 흐름(공유 자원 동기화 필요). UE: 게임 스레드, 렌더 스레드, RHI 스레드, 태스크 워커 스레드.
</details>

<details><summary>배열(TArray) 순회가 연결 리스트보다 빠른 이유는?</summary>

메모리가 연속이라 CPU 캐시 적중률이 높다. 데이터 지향 설계(예: Mass)의 배경이 되는 개념.
</details>


**프로젝트** (4)

- 이 프로젝트를 1분 안에 소개해 보라. → [W22](#w22)
<details><summary>이 프로젝트에서 가장 어려웠던 문제와 해결 과정은?</summary>

TS 문서 1건을 '증상 → 가설 → 검증 → 원인 → 해결 → 재발 방지' 순서로 2분 안에. 콜스택·수치 같은 근거를 꼭 포함한다.
</details>

<details><summary>왜 유니티가 아니라 언리얼인가?</summary>

내 말로: 지원 분야(국내 대형·온라인 프로젝트)의 엔진, C++과 엔진 소스로 원리를 확인할 수 있다는 점, 6개월간 소스를 읽으며 해결한 구체적 사례 1개.
</details>

<details><summary>AI를 어떻게 활용했나? AI 없이도 할 수 있나?</summary>

5원칙(설명 가능한 코드만 커밋, 소스로 API 확인, 15분 룰, 힌트 먼저, PR에 기록) + AI-Off 챌린지 결과 + AI가 틀렸던 API를 엔진 소스로 확인한 사례.
</details>


---

## 9. 템플릿

### .gitignore (언리얼 + Windows)
GitHub Desktop에서 저장소를 만들 때 Git Ignore를 `UnrealEngine`으로 고르면 자동으로 생긴다. 아래는 직접 관리하고 싶을 때의 예시.

````gitignore
# Unreal 생성물
Binaries/
Intermediate/
Saved/
DerivedDataCache/
Plugins/**/Binaries/
Plugins/**/Intermediate/

# IDE / 플랫폼
.idea/
.vs/
.vscode/
*.sln
Thumbs.db
desktop.ini
.DS_Store

# 외부 에셋(라이선스상 공개 저장소 업로드 금지) — 받는 방법은 README에
Content/ThirdParty/

# 패키징 결과
Packaged/
````

### .gitattributes (Git LFS)
게임 저장소를 만들기 전에 프로젝트 폴더에 넣는다(오늘 학습 W01 카드에 '파일 받기' 버튼). 문서용 GIF·PNG는 작게 만들어 일반 파일로 둔다.

````gitattributes
# 언리얼 바이너리 에셋 → Git LFS
*.uasset filter=lfs diff=lfs merge=lfs -text
*.umap   filter=lfs diff=lfs merge=lfs -text
# 원본 에셋(필요할 때만)
*.fbx    filter=lfs diff=lfs merge=lfs -text
*.wav    filter=lfs diff=lfs merge=lfs -text

# 텍스트 줄바꿈 정규화
* text=auto
````

### CLAUDE.md (AI 규칙 파일 예시)
AI 도구가 프로젝트 루트의 규칙 파일을 읽는다면 같은 내용을 해당 도구 형식으로 둔다.

````markdown
# 프로젝트 규칙 (AI용)
- 엔진: Unreal Engine 5.8 / 언어: C++ / 플랫폼: Windows 11 · Visual Studio 2026
- 나는 C#/유니티 출신 C++ 입문자다. 설명은 C#과 비교해서 해줘.
- 코딩 표준: Epic C++ Coding Standard (접두사 A/U/F/T/E/I, b 접두 bool)
- UObject 멤버 포인터는 반드시 UPROPERTY() + TObjectPtr.
- 새 기능은 코드보다 '설계 단계와 주의점'을 먼저 제시하고, 코드는 내가 요청할 때만.
- 존재가 확실하지 않은 엔진 API는 '엔진 소스 확인 필요'라고 표시.
- 멀티플레이(W14~): 모든 로직에 서버/클라이언트 실행 위치를 명시.
````

### 커밋 메시지 규칙

````text
<type>(<scope>): <무엇을, 왜>

type : feat | fix | refactor | perf | test | docs | chore
scope: core, input, combat, anim, ai, ui, data, net, gas, build

예)
feat(combat): 무기 소켓 기반 Sweep 판정 추가 (저프레임 판정 누락 방지)
fix(net): 클라이언트에서 데미지가 두 번 적용되던 문제 수정 (TS-007)
refactor(core): 플레이어/적 공통 베이스 AArenaCharacterBase 추출
perf(ai): BTService 주기 0.1s → 0.25s, 적 100마리 기준 게임 스레드 -1.8ms
````

### PR 템플릿 (.github/pull_request_template.md)

````markdown
## 무엇을 / 왜
- 관련 이슈: #

## 변경 사항
-

## 테스트 방법
- [ ] PIE 싱글
- [ ] PIE 2인 Listen Server + 지연 200ms (W14부터)
- 재현 단계:

## 스크린샷 / GIF

## AI 활용 내역
- 사용 범위: (설계 질문 / 초안 생성 / 리뷰 / 디버깅)
- 내가 검증·수정한 것:
- AI가 틀렸던 것(있다면):

## 셀프 리뷰 체크
- [ ] 모든 줄을 설명할 수 있다
- [ ] UObject 포인터에 UPROPERTY + TObjectPtr
- [ ] 불필요한 Tick 없음
- [ ] 수치는 데이터로(하드코딩 없음)
- [ ] 서버/클라 실행 위치 확인 (W14부터)
````

### 주간 Devlog (docs/devlog/W01.md)

````markdown
# W01 · 첫 C++ 액터 (12/07 ~ 12/13)

## 목표 vs 결과
| 목표 | 결과 | 근거(PR·커밋) |
|---|---|---|
|  |  |  |

## 핵심 구현 (GIF 1개)

## 배운 것 3줄 (내 말로)
1.
2.
3.

## 막혔던 것 → 어떻게 풀었나 (TS 링크)

## AI 활용 회고
- 도움이 된 질문:
- AI가 틀렸던 답과 확인 방법:

## 다음 주 계획

## 숫자
커밋 _ · PR _ · 코테 _문제 · 학습 _시간 · AI 레벨 L_
````

### 트러블슈팅 (docs/troubleshooting/TS-001-*.md)
면접 답변 재료. '30초 버전'까지 써 두면 그대로 말할 수 있다.

````markdown
# TS-001 · <증상 한 줄>
- 날짜: / 엔진: UE 5.8 / 관련 PR: #

## 1. 증상
(스크린샷, 로그·에러 원문)

## 2. 재현 단계
1.
2.

## 3. 가설과 검증
| 가설 | 확인 방법 | 결과 |
|---|---|---|
|  |  |  |

## 4. 원인
(근거: 콜스택 캡처 / 엔진 소스 위치 / Visual Logger 화면)

## 5. 해결
(diff 요약)

## 6. 재발 방지
(규칙 · 테스트 · 체크리스트 추가)

## 7. 면접 30초 버전
"___ 문제가 있었고, ___로 원인을 좁혀 ___임을 확인했습니다. ___로 해결했고, 이후 ___를 규칙으로 만들었습니다."
````

### 설계 결정 기록 (docs/adr/ADR-0001-*.md)

````markdown
# ADR-0001 · <결정 제목>
- 상태: 제안 / 채택 / 대체됨(→ ADR-000X)
- 날짜:

## 맥락
(어떤 문제를 풀어야 했나)

## 선택지
| 선택지 | 장점 | 단점 |
|---|---|---|
| A |  |  |
| B |  |  |

## 결정과 이유

## 결과
(좋아진 점 / 감수한 비용 / 나중에 다시 볼 조건)
````

### 엔진 소스 노트 (docs/engine-notes/01-*.md)

````markdown
# <클래스::함수> 읽기 노트
- 파일: Engine/Source/...  (UE 5.8)
- 읽게 된 질문:

## 한 줄 요약

## 호출 흐름 (콜스택 캡처)

## 핵심 코드 (10줄 이내 인용 + 내 해설)

## C# / 유니티와 비교

## 내 프로젝트에 적용한 것
````

### 월간 회고 (docs/retro/M1.md)
🔔 알림의 '월간 회고'를 열면 관문 체크 상태까지 채워진 초안을 받을 수 있다.

````markdown
# M1 회고 (W1~W4)

## 숫자
커밋 _ · PR _ · TS _ · ADR _ · 코테 누적 _ · 학습 시간 _ · 루브릭 평균 _

## Keep (계속할 것)
## Problem (문제였던 것)
## Try (다음 달 시도할 것)

## AI-Off 챌린지 결과
## 다음 달 리스크와 대응
````

### 게임 저장소 README 구조

````markdown
# ActionArena — UE5 C++ 2인 협동 액션 웨이브 서바이벌
![대표 GIF](docs/images/hero.gif)

> C#/유니티 입문 2개월 차에서 시작해 6개월간 언리얼 C++로 만든 프로젝트입니다.
> 학습 과정 전체(Devlog · 트러블슈팅 · 설계 결정 · 엔진 소스 노트)를 이 저장소에 기록했습니다.

[▶ 시연 영상 2분](링크) · [📄 기술 포트폴리오 PDF](링크) · [📈 개발 기록](docs/devlog)

## 핵심 구현
| 기능 | 핵심 클래스 | 기술 포인트 | 문서 |
|---|---|---|---|
| 콤보 전투 | UCombatComponent | AnimNotifyState 윈도우, 소켓 Sweep 판정 | TS-004 |
| 2인 협동 | UArenaAttributeSet | GAS 예측, 지연 200ms 반응성 비교 | ADR-0004 |

## 아키텍처
(Mermaid 클래스·흐름 다이어그램)

## 기술적 도전 Top 3
1. 문제 → 해결 → 결과(수치) → [TS 링크]

## 성능 개선
| 항목 | 전 | 후 |
|---|---|---|

## 같은 기능의 진화
체력: 델리게이트 컴포넌트(W5) → 데이터 파이프라인(W8) → 복제(W15) → GAS(W17)

## 개발 환경 · 빌드
UE 5.8 · Windows · Visual Studio 2026 / 외부 에셋 받는 방법

## 개발 기록 인덱스
Devlog · Troubleshooting · ADR · Engine Notes · Known Issues
````

### 기술 포트폴리오 PDF 구성 (15~20쪽)

````text
1   표지 — 이름 · 지원 포지션(UE 클라이언트) · 연락처 · GitHub/영상 QR
2   자기소개 — C#/유니티 → UE C++ 전환 스토리, 핵심 역량 3가지
3   프로젝트 개요 — 장르 · 기간 · 환경 · 범위 · 영상 QR
4   아키텍처 — 클래스 구조 · 모듈 · 데이터 흐름
5-10  핵심 기술 4개 (각 1~2쪽: 문제 → 설계 → 코드 발췌 → 결과)
       예) 콤보·판정 / 데이터 주도 무기 / 2인 협동 + GAS 예측 / 게임 루프·풀링
11-13 트러블슈팅 3건 (TS 요약)
14    성능 개선 (전/후 표)
15    같은 기능의 진화 타임라인
16    학습 방식 — AI 활용 원칙 · AI-Off 결과 · 6개월 숫자
17    엔진 소스 분석 요약
````

### 시연 영상 구성 (2~3분)

````text
0:00–0:10  훅: 가장 화려한 2인 전투 장면
0:10–0:40  게임 루프 요약 (메뉴 → 웨이브 → 게임오버)
0:40–1:40  기술 시연 (화면 하단 자막으로 기술명)
           · 콤보 + 판정 디버그 드로잉
           · 데이터만 바꿔 무기 추가
           · AI 디버거(Perception · BT)
           · 2인 협동 + 지연 200ms 반응성 전/후 비교
1:40–2:10  성능 전/후 수치, 코드 구조 다이어그램
2:10–2:30  GitHub 주소 · 연락처
````

---

## 10. 자료 & 대응표

### 추천 자료

| 분류 | 자료 | 용도 |
|---|---|---|
| 공식 | [Epic Developer Community 문서 (UE 5.8)](https://dev.epicgames.com/documentation/en-us/unreal-engine) | 코딩 표준 · Gameplay Framework · Enhanced Input · Networking · GAS · Unreal Insights |
| 공식 | [Visual Studio 설정 (UE 공식)](https://dev.epicgames.com/documentation/en-us/unreal-engine/setting-up-visual-studio-development-environment-for-cplusplus-projects-in-unreal-engine) | 설치할 워크로드·구성 요소와 UE 버전별 VS 버전 표 — 설치 직전에 재확인 |
| 공식 | [하드웨어·소프트웨어 사양 (UE 공식)](https://dev.epicgames.com/documentation/en-us/unreal-engine/hardware-and-software-specifications-for-unreal-engine) | 권장 PC 사양 |
| 공식 | [Epic C++ 코딩 표준](https://dev.epicgames.com/documentation/en-us/unreal-engine/epic-cplusplus-coding-standard-for-unreal-engine) | W13 셀프 리뷰 기준 |
| 공식 | [Unreal MCP (UE 5.8 실험 기능)](https://dev.epicgames.com/documentation/unreal-engine/unreal-mcp-in-unreal-editor) | W21 딥다이브 A |
| 샘플 | Lyra Starter Game (Fab, 무료) | GAS·모듈 구조 참고용 — 초반엔 너무 크니 W16 이후 '부분'만 |
| 커뮤니티 | [GASDocumentation (tranek)](https://github.com/tranek/GASDocumentation) | GAS 사실상 표준 커뮤니티 문서 (W16~W17) |
| 커뮤니티 | [Tom Looman 블로그](https://www.tomlooman.com) | UE C++ 가이드 · 최적화 · 실무 팁 |
| 한국어 | 이득우의 언리얼 프로그래밍 Part 1~4 (인프런) | UE5 C++ · 게임플레이 프레임워크 · 네트워크 · GAS 한국어 강의 |
| 한국어 | [씹어먹는 C++ (모두의코드)](https://modoocode.com) | C++ 생존 문법을 더 깊게 보고 싶을 때 |
| 한국어 | 이득우의 게임 수학 (책) | W4 3D 수학 보강 |
| 설계 | [Game Programming Patterns](https://gameprogrammingpatterns.com) | 옵저버 · 컴포넌트 · 오브젝트 풀 · 상태 패턴 (한국어판: 게임 프로그래밍 패턴) |
| C++ | [cppreference / learncpp](https://www.learncpp.com) | 문법 레퍼런스 |
| 코테 | [백준 + solved.ac](https://solved.ac) | 단계별 문제 · 티어 관리 |
| 코테 | [프로그래머스 코딩테스트 연습](https://school.programmers.co.kr/learn/challenges) | 기업 기출 유형 · 모의 시험 |

### 유니티 → 언리얼 대응표

| 유니티 | 언리얼 |
|---|---|
| GameObject | AActor |
| MonoBehaviour (컴포넌트) | UActorComponent / USceneComponent |
| Transform | USceneComponent(RootComponent) / FTransform |
| Prefab · Prefab Variant | C++ 부모 + 블루프린트 자식 클래스 |
| ScriptableObject | UDataAsset / UPrimaryDataAsset, DataTable |
| Awake / Start / Update / OnDestroy | 생성자 · BeginPlay / Tick / EndPlay |
| Instantiate / Destroy | GetWorld()->SpawnActor<T>() / Destroy() |
| Coroutine · InvokeRepeating | FTimerManager(SetTimer), AbilityTask |
| C# event · UnityEvent | 델리게이트(DECLARE_DYNAMIC_MULTICAST_DELEGATE …) |
| interface | UInterface + IInterface |
| List / Dictionary / HashSet | TArray / TMap / TSet |
| string | FString / FName / FText |
| Animator Controller · Animation Event | Animation Blueprint · AnimNotify(State) |
| CharacterController | UCharacterMovementComponent |
| Physics.Raycast · OnTriggerEnter | LineTraceSingleByChannel · OnComponentBeginOverlap |
| Layer Collision Matrix | 콜리전 채널 / 프리셋 (Block · Overlap · Ignore) |
| Input System (Action Map) | Enhanced Input (InputMappingContext · InputAction) |
| Canvas / UGUI | UMG (UUserWidget) |
| Resources · Addressables | 소프트 레퍼런스 + StreamableManager / AssetManager |
| PlayerPrefs | USaveGame |
| 싱글턴 GameManager · DontDestroyOnLoad | GameMode / GameState / GameInstance Subsystem |
| NavMeshAgent | AIController + NavMesh + MoveTo |
| Netcode for GameObjects | 내장 리플리케이션(Replicated · RPC) |
| Profiler | Unreal Insights · stat 명령 |
| Debug.Log · Gizmos | UE_LOG · DrawDebugHelpers |
| Assembly Definition | 모듈(.Build.cs) |

### 언리얼 에디터 메뉴 위치 (UE 5.8 기준)

| 기능 | 어디에 있나 |
|---|---|
| **콘솔 명령 입력** | ▶ Play 중 `` ` `` 키(Esc 아래, 숫자 1 왼쪽). 안 열리면 메뉴 `Window` → `Output Log` 아래쪽 `Cmd` 칸에 입력 |
| **Visual Studio 프로젝트 파일 다시 만들기** | `.uproject` 파일 우클릭 → `Generate Visual Studio project files` (Windows 11은 `추가 옵션 표시` 안에 있음). 파일을 추가·삭제했는데 VS에 안 보일 때 |
| **빌드 에러 읽기** | Visual Studio 아래 `출력`(Output) 창에서 **첫 번째** `error`부터 읽는다. `오류 목록`보다 정확하다 |
| **Editor Preferences** | 에디터 창 왼쪽 위 메뉴 `Edit` → `Editor Preferences` → 위쪽 검색창에 설정 이름 입력 |
| **Project Settings** | 메뉴 `Edit` → `Project Settings` (콜리전 채널: `Engine` → `Collision`, 기본 맵·GameMode: `Project` → `Maps & Modes`) |
| **화질(Scalability)** | 뷰포트 위쪽 툴바의 계기판(속도계) 아이콘 → Scalability. UE 5.5 이전은 오른쪽 위 `Settings` |
| **콘텐츠 팩 추가** | 콘텐츠 브라우저 `+ Add` → `Add Feature or Content Pack…` → `Third Person` → `Add to Project` |
| **C++ 클래스 만들기** | 메뉴 `Tools` → `New C++ Class…` → 부모 클래스 선택 → 이름 → `Create Class` (Visual Studio에 파일이 생긴다 — 헤더를 고칠 땐 에디터를 닫고 F5) |
| **BP 자식 만들기** | 콘텐츠 브라우저 `C++ Classes` 폴더에서 내 클래스 우클릭 → `Create Blueprint class based on …` |
| **입력 에셋** | 콘텐츠 브라우저 빈 곳 우클릭 → `Input` → `Input Action` / `Input Mapping Context` |
| **Animation Blueprint · Blend Space** | 콘텐츠 브라우저 우클릭 → `Animation` → `Animation Blueprint`(부모로 내 AnimInstance 선택) / `Blend Space` |
| **몽타주 · 노티파이** | 애니메이션 시퀀스 우클릭 → `Create` → `Create AnimMontage`. 노티파이는 몽타주 창 아래 `Notifies` 줄 우클릭 → `Add Notify State` |
| **DataAsset · DataTable** | 콘텐츠 브라우저 우클릭 → `Miscellaneous` → `Data Asset`(내 클래스 선택) / `Data Table`(행 구조체 선택). CSV는 콘텐츠 브라우저로 끌어다 놓으면 가져오기 창이 뜬다 |
| **Behavior Tree · Blackboard** | 콘텐츠 브라우저 우클릭 → `Artificial Intelligence` → `Behavior Tree` / `Blackboard` |
| **NavMesh** | 툴바 `+`(Quickly add to the project) → `Volumes` → `Nav Mesh Bounds Volume`를 바닥 크기에 맞추기 → 뷰포트에서 `P` 키로 초록 영역 확인 |
| **Gameplay Debugger** | ▶ Play 중 `'`(작은따옴표) 키 → 숫자 키로 카테고리 켜고 끄기 |
| **Visual Logger** | 메뉴 `Tools` → `Debug` → `Visual Logger` → 녹화(●)를 켜고 Play |
| **Size Map · Reference Viewer** | 콘텐츠 브라우저에서 에셋 우클릭 → `Size Map…` / `Reference Viewer…` |
| **Unreal Insights** | 메뉴 `Tools` → `Run Unreal Insights` (또는 화면 오른쪽 아래 `Trace` 메뉴). 버전에 따라 위치가 조금 다르다 |
| **2인 멀티 Play** | 툴바 ▶ Play 옆 `⋮` → `Number of Players` = 2, `Net Mode` = `Play As Listen Server` |
| **네트워크 에뮬레이션** | `Edit` → `Editor Preferences` → `Level Editor` → `Play` → `Multiplayer Options` → `Enable Network Emulation` (지연·손실 값 입력) |
| **플러그인 켜기** | 메뉴 `Edit` → `Plugins` → 검색 → 체크 → 에디터 재시작 |
| **패키징** | 툴바 `Platforms` → `Windows` → `Package Project` (Shipping은 같은 메뉴의 `Binary Configuration`에서 선택) |
| **자동화 테스트 실행** | 메뉴 `Tools` → `Session Frontend` → `Automation` 탭 (또는 `Tools` → `Test Automation`) |
| **World Settings** | 메뉴 `Window` → `World Settings` (이 레벨에서 쓸 GameMode 지정) |

### 용어집

| 용어 | 뜻 |
|---|---|
| **핫픽스** | 큰 버전(5.8) 안에서 버그만 고친 작은 업데이트(5.8.1, 5.8.2…). 가장 높은 번호를 쓰면 된다. |
| **콜스택 (호출 스택)** | 지금 이 줄에 오기까지 어떤 함수가 어떤 순서로 불렸는지 쌓인 목록. 중단점에서 멈추면 Visual Studio 아래 `호출 스택` 창에 보인다. |
| **중단점 (Breakpoint)** | '이 줄에서 멈춰라' 표시. 멈춘 상태에서 변수 값과 콜스택을 볼 수 있다. |
| **디버그 실행** | 디버거를 붙여 실행하는 것. 중단점에서 멈추려면 Visual Studio에서 **F5**(디버깅 시작)로 실행해야 한다. |
| **빌드 · 컴파일** | 내가 쓴 C++ 코드를 컴퓨터가 실행할 수 있는 파일로 바꾸는 과정. |
| **링크 에러** | 선언(.h)은 있는데 정의(.cpp의 함수 본문)를 못 찾을 때 나는 에러. |
| **헤더 · 소스** | `.h`는 '무엇이 있는지'(선언), `.cpp`는 '어떻게 동작하는지'(정의). |
| **IDE** | 코드 편집·빌드·디버깅을 한 곳에서 하는 프로그램 (Visual Studio, Rider). |
| **IntelliSense** | Visual Studio가 엔진·프로젝트 코드를 읽어 자동완성·정의 이동 데이터를 만드는 기능. 처음 열면 오래 걸리고, 끝나야 F12·자동완성이 빠르다. |
| **₩ 와 \** | 한글 Windows에서는 경로 구분 기호 `\`가 글꼴에 따라 `₩`로 보인다. 같은 글자이니 그대로 쓰면 된다 (예: `C:\Projects` = `C:₩Projects`). |
| **솔루션 탐색기 · 시작 프로젝트** | 솔루션 탐색기는 Visual Studio 오른쪽 파일 목록. 굵게 보이는 프로젝트가 시작 프로젝트이고, F5를 누르면 그 프로젝트가 실행된다 (내 게임 프로젝트여야 함). |
| **Live Coding** | 에디터를 켠 채 `.cpp`를 다시 컴파일해 바로 반영하는 기능(`Ctrl+Alt+F11`). 헤더(.h)·`UPROPERTY`·생성자를 바꿨다면 에디터를 끄고 Visual Studio에서 F5로 다시 실행한다. |
| **솔루션 구성** | Visual Studio 위쪽에서 고르는 빌드 모드. 언리얼 작업은 보통 `Development Editor` + `Win64`. |
| **PIE** | Play In Editor — 에디터 안에서 ▶ Play로 게임을 바로 실행해 보는 것. |
| **뷰포트 · 콘텐츠 브라우저** | 뷰포트는 가운데 3D 화면(유니티 Scene 뷰), 콘텐츠 브라우저는 아래쪽 에셋 목록(유니티 Project 창). |
| **레벨 (맵)** | 게임의 한 장면 (유니티 Scene). |
| **블루프린트 (BP)** | 언리얼의 시각적 스크립트. 이 과정에서는 주로 'C++ 부모의 값만 바꾼 자식 클래스'로 쓴다(유니티 프리팹 변형처럼). |
| **액터 · 컴포넌트** | 액터는 레벨에 놓을 수 있는 모든 것(유니티 GameObject), 컴포넌트는 액터에 붙이는 기능 조각(유니티 MonoBehaviour). |
| **CDO** | 클래스마다 엔진이 만들어 두는 '기본값 견본 객체'. 새 객체는 이 값을 복사해서 시작한다. |
| **리플렉션** | 엔진이 내 클래스의 변수·함수 목록을 알 수 있게 하는 장치. `UCLASS`·`UPROPERTY`·`UFUNCTION`이 그 표시다. |
| **GC (가비지 컬렉션)** | 안 쓰는 객체를 엔진이 자동으로 지우는 기능. 언리얼은 `UPROPERTY`로 연결된 객체만 '쓰는 중'으로 본다. |
| **UPROPERTY** | 변수를 엔진에 등록하는 표시. 에디터 노출·저장·GC 보호가 여기서 정해진다. |
| **포인터 · 참조** | 포인터(`*`)는 객체의 '주소'를 담는 변수, 참조(`&`)는 기존 객체의 '다른 이름'. C#의 참조 타입이 자동으로 해 주던 일을 직접 표시한다. |
| **Tick** | 매 프레임 불리는 함수 (유니티 Update). 많이 쓰면 느려진다. |
| **델리게이트** | '이 일이 생기면 알려줘' 연결 장치 (C# event · Action). |
| **몽타주 · 노티파이** | 몽타주는 공격처럼 원할 때 재생하는 애니메이션 묶음, 노티파이는 애니메이션 특정 시점에 보내는 신호(유니티 Animation Event). |
| **DataAsset · DataTable** | 수치를 코드 밖 에셋으로 빼는 방법. DataAsset은 객체 하나(유니티 ScriptableObject), DataTable은 표(CSV). |
| **리플리케이션 · RPC** | 리플리케이션은 서버의 값을 클라이언트에 자동 복사하는 것, RPC는 다른 컴퓨터의 함수를 부르는 것. |
| **리슨 서버** | 한 플레이어의 게임이 서버 역할도 같이 하는 멀티플레이 방식. |
| **GAS** | Gameplay Ability System — 스킬·버프·스탯을 만드는 언리얼 공식 프레임워크. |
| **Git LFS** | `.uasset` 같은 큰 파일을 Git과 따로 보관하는 확장 기능. |
| **브랜치 · 커밋 · Push** | 브랜치는 작업용 분기, 커밋은 세이브 포인트, Push는 GitHub에 올리기. |
| **PR · 머지** | PR은 '이 분기를 main에 합칠게요' 작업 보고서, 머지는 실제로 합치는 것. |

### C# → C++ 대응표

| C# | C++ / 언리얼 |
|---|---|
| class (참조 타입) | class/struct는 기본이 '값'. 참조는 포인터(*)·참조(&)로 명시 |
| new (GC가 관리) | new/delete(수동), 스마트 포인터 / UE: NewObject · SpawnActor + GC |
| ref / out | 참조 매개변수(T&) |
| in 매개변수 | const T& |
| null | nullptr |
| interface | 순수 가상 함수(= 0)만 가진 추상 클래스 / UE: UInterface |
| abstract · virtual · override · sealed | = 0 · virtual · override · final |
| base.Method() | Super::Method() |
| using · IDisposable | RAII (소멸자에서 정리) |
| 제네릭 List<T> | 템플릿 TArray<T> |
| delegate · Action · Func · 람다 | 함수 포인터 · 람다 / UE: 델리게이트, TFunction |
| var | auto |
| foreach | 범위 기반 for: for (auto& X : Array) |
| property get/set | Getter/Setter 함수 (UE: UPROPERTY로 에디터 노출) |
| 예외(try/catch) | UE는 예외를 쓰지 않음 → check / ensure / 반환값 검사 |
| System.Reflection | 표준 C++엔 없음 → UHT가 만드는 UE 리플렉션 |
| 하나의 .cs 파일 | .h(선언) + .cpp(정의) |

---

_이 문서와 HTML 가이드는 같은 원본 데이터에서 생성되었습니다. 버전·호환성 정보는 작성일(2026-11-25) 기준이므로 설치 직전에 공식 문서로 재확인하세요._
