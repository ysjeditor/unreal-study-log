# 수료 시험 B형 — 문제지

> 6개월 커리큘럼 전 범위 · 100점 · 1부·2부·3부 라이브 실기는 AI·인터넷 사용 불가 (라이브 실기는 엔진 소스·공식 문서 열람만 허용) · 3부 포트폴리오는 시험 7일 전 저장소 제출
> 라이브 실기 블록1·2의 클래스 이름: A형은 `Rune`, B형은 `Dusk` 접두사를 쓴다 (예: `ARuneCharacter`). 응시자가 다른 접두사를 써도 감점하지 않는다. 블록3과 포트폴리오는 본인 프로젝트 이름 그대로.

## 1부 필기 (30점 · 300분)

지필 2교시(각 150분). 설명형 서술과 코드 읽기(출력 예측, 빈칸 채우기, 결함 찾기, 다이어그램 그리기)로 구성. AI, 인터넷, 엔진 소스 열람 불가. 문항 점수 = 30점 × weight ÷ 1부 weight 합

### P1-001 (0.10점)

[상황] 실습 PC 3대 중 하나에 UE 5.8을 설치한다.
가: Windows 11 / VS 2026 18.0 / 6코어 3.2GHz / 32GB / 그래픽 8GB / SSD 여유 70GB
나: Windows 10 22H2 / VS 2022 17.14 / 쿼드코어 2.8GHz / 32GB / 12GB / SSD 250GB
다: Windows 10 21H2 / VS 2022 17.12 / 듀얼코어 3.0GHz / 16GB / 4GB / HDD 500GB
런처에는 5.8.0, 5.8.1, 5.8.2, 5.9 Preview가 보이고, W12에 'UE6 발표' 기사가 나올 예정이다.
(1) 설치할 버전과 과정 내내 다루는 방법, 5.8.0이 아닌 이유, UE6 소식에도 바꾸지 않는 이유를 쓰시오.
(2) 가·나·다가 각 항목(OS, VS, CPU, RAM, 그래픽)에서 공식 최소 요구사항을 충족하는지, 권장 사양까지 충족하는지 나눠 판단하고, 못 미치는 항목은 기준값과 함께 쓰시오.
(3) 설치 준비 측면에서 걸리는 PC와 문제, 설치 당일 준비 2가지와 이유를 쓰시오.

### P1-002 (0.10점)

[상황] 동기의 'UE 5.8 환경 세팅 메모'다. 다섯 항목 모두 틀렸거나 빠진 내용이 있다.
① 런처가 유니티 허브와 IDE 역할을 다 하니 Visual Studio는 필요 없음.
② 엔진은 5.8.0을 고를 것. 처음 나온 게 제일 안정적이니까.
③ 'Editor symbols for debugging'은 용량만 잡아먹으니 끌 것.
④ VS Installer는 'C++를 사용한 데스크톱 개발' 워크로드 하나면 충분.
⑤ 빌드가 MSVC 버전 에러로 실패하면 VS를 지우고 처음부터 다시 설치.
각 항목의 틀린 점, 고칠 내용, 이유를 쓰시오. ④는 워크로드 3개·구성 요소 3개 이상을, ⑤는 UE 5.8 권장 컴파일러 버전을 포함하시오.

### P1-003 (0.19점)

[상황] 팀원 저장소를 Clone하니 8GB가 넘고 Intermediate/Build/…, Binaries/Win64/… 파일이 수천 개 커밋돼 있다. 팀원 프로젝트 위치는 D:\게임 프로젝트\Arena Test 이고 가끔 원인 모를 빌드 에러가 난다.
(1) 잘못 올라간 것과 올리면 안 되는 이유를 쓰고, 올리지 않는 폴더 4개를 쓰시오.
(2) 반드시 있어야 하는 원본 4가지를 쓰고 유니티에서 커밋하던 것·안 하던 것과 대응시키시오.
(3) Binaries·Intermediate 없이 Clone해도 프로젝트를 쓸 수 있는 이유는?
(4) 경로의 문제와 권장 규칙, 함께 피할 OneDrive 관련 위치를 쓰시오.
(5) 다음은 어느 폴더·파일에서 하는가? (가) 엔진 모듈 의존성 추가 (나) 설정 ini 확인 (다) 새 메시·머티리얼 저장 (라) 새 클래스 .h/.cpp 추가 (마) .sln을 다시 만들 때 우클릭하는 파일

### P1-004 (0.29점)

[상황] 에디터를 켠 채 AArenaCharacter를 고친다. ①~⑥마다 'Live Coding'과 '에디터 종료 → VS F5' 중 하나를 고르고 이유를 한 줄로 쓰시오.
① .cpp의 StartSprint 안 if 조건 Speed > 0.f → Speed > 10.f
② .cpp의 생성자 안 SpringArm->TargetArmLength 300.f → 450.f
③ .h의 UPROPERTY(EditAnywhere) float SprintSpeed = 600.f; 기본값을 800.f로
④ .cpp의 Look 함수 안에 지역 변수를 추가해 계산식을 두 줄로 나눔
⑤ .h에 UPROPERTY(VisibleAnywhere) TObjectPtr<UStaticMeshComponent> Shield; 추가 + 생성자에서 CreateDefaultSubobject
⑥ .cpp의 BeginPlay에서 UE_LOG 상세 수준을 Warning → Log
(7) 친구가 '②는 .cpp만 고쳤으니 Live Coding이면 된다'고 한다. 틀린 이유를 포함해, 헤더·UPROPERTY·생성자 변경이 Live Coding으로 안전하지 않은 이유를 '클래스의 모양' 관점에서 3~4줄로 쓰고 헷갈릴 때의 원칙을 쓰시오.

### P1-005 (0.29점)

[상황] Shift를 떼도 계속 빠르다. AArenaCharacter::SetMoveSpeed(float NewSpeed) 첫 줄에 중단점을 걸고 F5로 실행했다. Shift를 누를 때는 멈추고 뗄 때는 한 번도 멈추지 않았다.
[호출 스택]
> AArenaCharacter::SetMoveSpeed(float NewSpeed) 줄 210
  AArenaCharacter::StartSprint(const FInputActionValue& Value) 줄 188
  (엔진 입력 처리 함수들)
[지역] NewSpeed = 900.0 / this = BP_ArenaCharacter_C_0
(1) 호출 스택 창이 보여 주는 정보와, 아래에서 위로 읽은 호출 경로를 쓰시오.
(2) 관찰(누를 때만 멈춤)과 지역 값으로 원인을 어디로 좁히는가? 다음 중단점 위치와 확인할 것을 쓰시오.
(3) ArenaCharacter.h를 고쳐 빌드하자 오류 목록에 60여 개가 떴다. 출력 창 앞부분:
[1/7] Compile ArenaCharacter.gen.cpp
ArenaCharacter.h(24): error C2065: 'USpringArmComponent': undeclared identifier
[2/7] Compile ArenaCharacter.cpp
ArenaCharacter.h(24): error C2065: 'USpringArmComponent': undeclared identifier
ArenaCharacter.cpp(15): error C2678: binary '=': no operator found ...
[3/7] Compile ArenaAnimInstance.cpp
ArenaCharacter.h(24): error C2065: 'USpringArmComponent': undeclared identifier
무엇부터 고치며, 왜 출력 창의 첫 error부터 읽는가?
(4) 동기가 아무것도 확인하지 않고 '스프린트가 안 꺼져요. 고쳐 주세요.'라며 .cpp 전체만 붙였다. 15분 룰로 문제점을 쓰고 질문을 3~5줄로 다시 쓰시오.

### P1-006 (0.19점)

[상황] 혼자 쓰는 저장소에서 Arena.umap(약 60MB)을 한 달간 50번 고쳐 커밋했다. 다음 달 친구가 레벨 디자인으로 합류한다.
(1) LFS 없이 운영했다면 50번의 커밋이 저장소·Clone에 주는 영향을 텍스트 vs 바이너리 기록 방식으로 설명하고, LFS를 썼다면 무엇이 달라지는지 쓰시오.
(2) 합류 후 둘이 같은 날 Arena.umap을 고치면 어떻게 되는가? .cpp라면 왜 덜 심각한가?
(3) (2)를 예방하는 LFS 기능·사용 방법과 Perforce의 대응 개념을 쓰시오.
(4) LFS 저장 사용량이 9.2GiB다. 무료 한도, 결제수단 없이 초과 시 일어나는 일과 일어나지 않는 일, 확인 위치를 쓰시오.

### P1-007 (0.19점)

(1) 알맞은 AI 도구 종류(채팅형/코드를 읽는 AI)와 예시 도구, 이유를 쓰시오. (가) '내 Source 폴더 전체에서 UPROPERTY가 빠진 UObject 포인터 멤버를 찾아 줘' (나) 'IMC와 IA의 역할을 유니티 Input System에 빗대 설명해 줘'
(2) 동기의 CLAUDE.md 초안: '- 엔진: UE 5.4 / 언어: C++ - 코드는 질문하면 바로 완성본으로 줘. - 설명은 짧게, 결과 코드만.' 이 파일의 용도를 쓰고, 커리큘럼 규칙 4가지 기준으로 고치거나 추가할 점을 모두 쓰시오.
(3) 각각 5원칙을 지켰는지와 해당 원칙을 쓰고, 어긴 것은 올바른 행동을 쓰시오. ① AI가 알려 준 SetTimer 오버로드를 F12로 열어 확인 후 사용 ② 버그를 로그·중단점으로 15분 좁힌 뒤 '확인한 것'과 질문 ③ 콤보 시스템 시작 때 '설계 단계와 주의점부터' 요청 ④ PR에 'AI 사용함'만 쓰고 도움·검증 내용은 없음 ⑤ 설명 못 하는 TWeakObjectPtr 캡처 코드를 커밋
(4) 학습자마다 맞는 단계·규칙·적용 구간을 쓰고 지금 방식이 맞는지 판정하시오. 민지(W5): AI 초안에 모든 줄 해설 후 커밋 / 준호(W14): AI가 쓴 코드에 해설만 달고 커밋 / 서연(W22): 혼자 작성 후 엣지 케이스·대안만 AI에 질문

### P1-008 (0.10점)

(1) 기록 '백준 2839 — 20분 만에 막혀 AI에게 정답 코드를 받아 제출, 맞았습니다. 끝.'에서 코테 규칙상 잘못된 점을 모두 찾아 올바른 행동을 쓰고, 규칙의 이유를 한 줄로 쓰시오.
(2) AI-Off 챌린지의 목적을 쓰고 친구 메모의 틀린 곳을 모두 고치시오: '① W4: IInteractable+문 상호작용, 60분 / ② W8: AFloatingItem 재작성, 30분 / ③ W13: HealthComponent+데미지+사망 델리게이트+체력바, 60분 / ④ W24: 모의 코테 3회만'
(3) W6 학습자가 'Unreal MCP로 AI에게 AnimBP·블렌드스페이스를 만들게 하면 빠르지 않냐'고 묻는다. W1~W20에 쓰지 않는 이유 2가지로 답하시오.
(4) Unreal MCP는 언제 어떤 일에 쓰는가? 자동화 예 2가지와 문서화할 것을 쓰시오.

### P1-009 (0.19점)

[상황] 아래는 한 학생이 '공격 쿨다운 표시' 기능을 만든 과정이다.
① GitHub 웹에서 '쿨다운 UI 만들기 — 완료 조건: 쿨다운 중 버튼이 회색' 카드를 만들었다(#14).
② 그 카드를 M3 묶음에 넣었다.
③ Desktop에서 `feat/cooldown-ui`를 만들어 작업했다.
④ 작업이 끝날 때마다 한 줄 메시지와 함께 저장했다.
⑤ 그 저장들을 GitHub에 올렸다.
⑥ 웹에서 '무엇을·왜·테스트 방법'을 적은 요청서를 열고 본문에 'Closes #14'를 썼다.
⑦ 요청서 화면에서 본편에 합쳤다.
⑧ 월말에 v0.3.0이라는 이름을 붙이고 GIF·변경 내역을 담은 페이지를 공개했다.

(1) ①~⑧에 해당하는 Git/GitHub 용어(저장소·커밋·푸시·브랜치·PR·머지·이슈·마일스톤·태그·릴리즈 중)를 각각 쓰시오. ④·⑤는 Desktop 버튼 이름도, ⑦은 합치는 방식도 쓰시오. 그리고 이 모든 것이 쌓이는 곳(저장소)이 무엇인지 한 줄로 정의하시오.
(2) ⑦ 뒤에 #14와 M3 달성률은 어떻게 되는가.
(3) ⑧에서 '태그'와 '릴리즈'는 각각 어느 부분인가.
(4) 학생이 "다음엔 ③·⑥·⑦을 빼고 main에 바로 커밋하겠다"고 한다. 무엇을 잃는지 2가지 쓰시오.

### P1-010 (0.19점)

[상황] 학생 B의 기록 습관은 다음과 같다.
- 주간 Devlog를 `feat/devlog-w9` 브랜치에 넣고 PR을 연다.
- 적 AI 코드는 귀찮아서 main에 바로 커밋한다.
- 릴리즈 노트·README·이슈는 써 본 적이 없다.
- TIL에 이번 주 쓴 내용: ① "BT 태스크가 바로 끝나 공격 몽타주가 끊김 → InProgress 반환 + FinishLatentTask로 해결" ② "원거리 적 감지를 Perception 시야 감각으로 정함 → 벽 뒤 감지가 자연스럽게 걸러짐" ③ "BTService TickNode는 Interval마다 불린다는 것을 BTService.h 주석으로 확인"

(1) B의 두 경로 습관을 규칙에 비추어 각각 판정하시오(규칙 위반인지, 위반은 아니지만 필요 없는 수고인지). 바로잡는 방법과 규칙 한 줄도 쓰시오.
(2) 커밋 메시지·PR 본문·이슈·TIL·docs 문서·릴리즈 노트·README 7곳에 각각 무엇을 언제 남기는지 표로 쓰시오. B가 써 본 적 없는 이슈·릴리즈 노트·README에는 '적 AI' 기능을 예로 무엇을 쓰면 되는지 한 줄씩 덧붙이시오.
(3) TIL ①②③을 어떤 문서로 승격하는가. 승격 기준(무엇 → 무엇)과 함께 쓰시오.
(4) B는 "6개월 끝나고 한꺼번에 README와 기록을 AI로 정리하면 된다"고 한다. 이 방식이 약한 이유 2가지를 쓰시오. 그리고 GitHub 기본 기능만으로 '계획 → 실행 → 성과'가 이어지는 구조를 쓰시오.

### P1-011 (0.19점)

[상황] 아래 대화에 답하는 형식으로, 각 경우 무엇을 어떤 순서로 하고 왜 그런지 쓰시오.
① "커밋 버튼을 너무 빨리 눌렀어. 파일 하나를 더 고치고 같이 커밋하고 싶어. Push는 안 했어."
② "그저께 Push한 커밋 메시지가 'asdf'야. 고치고 싶어."
③ "이슈 #8 작업을 main에서 시작해 버렸어. 아직 커밋은 안 했어."
④ "Push origin을 눌렀는데 안 올라가. 다른 PC에서 TIL을 하나 올렸던 것 같아."
⑤ "Changes에 처음 보는 파일이 수십 개 있고 지금 상태를 모르겠어. Discard Changes로 싹 지우거나 브랜치를 삭제하고 다시 만들까?"
마지막으로 '확인받고 누르는 버튼' 3가지를 쓰고, 공통 위험을 한 줄로 쓰시오.

### P1-012 (0.10점)

[상황] 신입 스터디원 C가 이렇게 말한다.
"과제 끝내고 GitHub 웹에서 PR을 만들려는데 내 브랜치가 안 보여. 그리고 매일 PR을 하나씩 꼭 만들어야 해? 오늘은 영상만 봤는데. 아, 알림의 회고 초안은 이미 다 채워져 있으니 그대로 올리면 되지?"
(1) C의 PR이 안 되는 이유와, 카드의 기록 단계 순서를 설명하시오. PR 본문은 어디서 가져오는가.
(2) '매일 PR' 질문에 답하시오.
(3) 🔔 알림의 '주간 Devlog'·'릴리즈'·'월간 회고' 초안에 각각 무엇이 미리 채워져 있는지 쓰시오. 각각 언제 올리는지, 릴리즈는 총 몇 번인지도 쓰시오.
(4) 초안을 그대로 올리면 안 되는 이유를 쓰시오.

### P1-013 (0.29점)

(1) 유니티 PlayerHealth.cs는 언리얼 C++에서 어떤 파일 구성에 대응하는가? 각 역할을 '선언/정의'로 쓰시오.
(2) 'ArenaCharacter.cpp 본문을 고치면 1개만 컴파일되는데, ArenaCharacter.h에 주석 한 줄만 바꿔도 30개가 다시 컴파일된다.' 이 현상을 헤더/소스 분리 원리로 설명하고 C#에서는 왜 나눌 필요가 없었는지 쓰시오.
(3) #include와 #pragma once의 역할을 쓰시오. Weapon.h에서 #pragma once를 지웠다. Sword.h·Bow.h가 모두 Weapon.h를 include하고 Inventory.cpp가 둘 다 include하면?
(4) 다음 헤더를 보고 답하시오.
01 #pragma once
02 #include "CoreMinimal.h"
03 #include "Components/ActorComponent.h"
04 #include "ArenaCharacter.h"
05 #include "HealthBarComponent.generated.h"
06 UCLASS()
07 class UHealthBarComponent : public UActorComponent
08 {
09     GENERATED_BODY()
10 public:
11     void BindTo(AArenaCharacter* Character);
12 private:
13     UPROPERTY() TObjectPtr<AArenaCharacter> Watched;
14 };
(가) 4행 대신 쓸 것과 include를 옮길 곳 (나) (2)의 재컴파일 문제와 관련해 좋아지는 점, 이름만으로 충분한 이유

### P1-014 (0.19점)

FloatingItem.h:
01 #pragma once
02 #include "CoreMinimal.h"
03 #include "GameFramework/Actor.h"
04 #include "Components/StaticMeshComponent.h"
05 #include "FloatingItem.generated.h"
06 UCLASS()
07 class AFloatingItem : public AActor
08 {
09     GENERATED_BODY()
10 public:
11     AFloatingItem();
12 protected:
13     virtual void BeginPlay() override;
14 public:
15     virtual void Tick(float DeltaTime) override;
16     UPROPERTY(EditAnywhere, Category = "Float")
17     float Frequency = 2.f;
18 private:
19     UPROPERTY(VisibleAnywhere)
20     TObjectPtr<UStaticMeshComponent> Mesh;
21     FVector StartLocation;
22 };
(1) 다음을 한 줄씩 설명하시오: 1, 5, 6, 7, 9행, 10·12·14·18행(각 블록이 어느 멤버까지 적용되는지), 13, 16~17, 19~20, 22행
(2) .cpp에서 생성자와 BeginPlay를 정의하는 첫 줄을 쓰고, 생성자 줄의 :: 앞뒤 이름의 뜻을 쓰시오.
(3) C# 습관대로 쓴 선언(UCLASS 등 생략)에서 틀린 곳 3종류를 찾아 고치시오.
public class AFloatingItem : public AActor
{
public:
    void ResetHeight();
    private float Speed = 1.f;
}

### P1-015 (0.29점)

// 헤더 일부
UPROPERTY(VisibleAnywhere) TObjectPtr<UStaticMeshComponent> Mesh;   // 생성자에서 생성
UPROPERTY(EditAnywhere) TObjectPtr<AActor> FollowTarget;            // 레벨에서 지정(비워 둘 수 있음)
UPROPERTY(EditAnywhere) FVector Offset = FVector(0.f, 0.f, 120.f);
// cpp
01 void AFloatingItem::Tick(float DeltaTime)
02 {
03     Super::Tick(DeltaTime);
04     FVector Base = FollowTarget->GetActorLocation();
05     FVector Goal = Base + Offset;
06     Goal.Z += FMath::Sin(RunningTime) * Amplitude;
07     Mesh->SetWorldLocation(Goal);
08     RunningTime += DeltaTime;
09 }
10 void AFloatingItem::GiveBonus(AActor* Picker)
11 {
12     AArenaCharacter* Hero = Cast<AArenaCharacter>(Picker);
13     UCharacterMovementComponent* Move = Hero->GetCharacterMovement();
14     Move->MaxWalkSpeed += BonusSpeed;
15 }
(1) 13행 Move는 무엇을 담는 변수이며, 포인터가 nullptr이란 무슨 뜻인가?
(2) 6행은 ., 7행은 ->를 쓰는 이유를 쓰고, 7행을 *와 .으로 다시 쓰시오. C#과 비교하시오.
(3) 크래시가 날 수 있는 줄 2개와 상황·이유를 쓰시오.
(4) 두 곳을 nullptr 검사 또는 IsValid()로 고친 코드를 쓰시오.

### P1-016 (0.19점)

각 에러마다 (가) 원문 해석 (나) 실제 원인 줄과 이유 (다) 고치는 법을 쓰시오. 에러 1은 가리키는 줄(51)과 고칠 줄이 다른 이유도 쓰시오.
[에러 1] FloatingItem.cpp
50     FVector NewLoc = GetActorLocation()
51     NewLoc.Z += DeltaHeight;
출력: FloatingItem.cpp(51): error C2146: syntax error: missing ';' before identifier 'NewLoc'
[에러 2] .h: void SetFloatRange(float MinZ, float MaxZ);
.cpp 70: void AFloatingItem::SetFloatRange(float Range) { MaxHeight = Range; }
출력: FloatingItem.cpp(70): error C2511: 'void AFloatingItem::SetFloatRange(float)': overloaded member function not found in 'AFloatingItem'
[에러 3] DamageZone.cpp (include는 "DamageZone.h" 하나뿐)
33     UGameplayStatics::ApplyDamage(OtherActor, 10.f, nullptr, this, nullptr);
출력: DamageZone.cpp(33): error C2653: 'UGameplayStatics': is not a class or namespace name

### P1-017 (0.19점)

(1) 접두사 규칙에 맞게 이름을 지으시오: (가) 레벨에 놓는 레버 액터 (나) UActorComponent 상속 인벤토리 컴포넌트 (다) 무기 수치 구조체 (라) 적 AI 상태 열거형 (마) 상호작용 인터페이스의 C++ 쪽 클래스 (바) 사망 여부 bool (사) 템플릿 컨테이너 예
(2) 다음 중 접두사가 틀린 2개를 이유와 함께 고치고, 엔진 빌드 도구가 접두사를 어떻게 다루는지 쓰시오: AArenaGameMode(AGameModeBase 파생) / FHitResultData(구조체) / ULeverActor(AActor 파생) / EWeaponType(열거형) / IsDead(bool 멤버)
(3) 팀원이 'UCLASS()와 GENERATED_BODY()는 C++ 문법상 없어도 되니 지우자'고 한다. 두 매크로의 역할을 UHT와 연결해 쓰고, 지우면 안 되는 이유를 쓰시오.
(4) 아래 위반을 고치고 Lever.generated.h를 누가 만드는지 쓰시오.
#pragma once
#include "CoreMinimal.h"
#include "GameFramework/Actor.h"
#include "Lever.generated.h"
#include "Components/BoxComponent.h"

### P1-018 (0.19점)

// 거리 cm, 각도 도. MoveSpeed=200(cm/초), SpinSpeed=45(도/초), 시작 X=0.
01 void AFloatingItem::Tick(float DeltaTime)
02 {
03     Super::Tick(DeltaTime);
04     FVector Velocity = FVector(MoveSpeed, 0.f, 0.f);
05     FVector Delta = Velocity * DeltaTime;
06     SetActorLocation(GetActorLocation() + Delta);
07     FRotator Spin = FRotator(0.f, SpinSpeed * DeltaTime, 0.f);
08     SetActorRotation(GetActorRotation() + Spin);
09 }
(1) 3초 뒤 X와 회전 각도, 7행 FRotator 두 번째 값이 어떤 회전인지 쓰시오.
(2) 4~6행의 FVector가 각각 무엇(속도·한 프레임 이동량·위치)을 나타내는지 쓰시오.
(3) 5행을 Delta = Velocity; 로 쓰면 1초 동안 120fps·30fps에서 각각 몇 cm 움직이는가? 문제와 DeltaTime의 해결 원리는?
(4) Tick(float DeltaTime)은 유니티의 무엇에 대응하는가?
(5) '빠른 직진·제자리 회전(MoveSpeed 0)·느린 이동+빠른 회전' 3종을 코드 수정 없이 만드는 방법을 프리팹 변형과 비교하고 C++ 부모·BP 자식 역할을 쓰시오.

### P1-019 (0.29점)

int GScore = 0;   // 전역
void SetToZero(int Value) { Value = 0; }
void Heal(int& Value)     { Value += 25; }
void Damage(int* Value)   { if (Value != nullptr) { *Value -= 40; } }
int main()
{
    int Hp = 80;
    int& Alias = Hp;
    int* Ptr = &Hp;
    Damage(Ptr);    cout << Hp << '\n';          // ①
    Heal(Alias);    cout << Hp << '\n';          // ②
    SetToZero(Hp);  cout << Hp << '\n';          // ③
    cout << (&Alias == &Hp) << '\n';             // ④
    cout << *Ptr << '\n';                        // ⑤
    cout << (Ptr == &Hp) << '\n';                // ⑥
    int* Shield = new int(30);
    delete Shield;
}
(1) ①~⑥의 출력을 쓰시오(bool은 1/0).
(2) Ptr = nullptr; 은 되는데 Alias를 다른 변수의 별칭으로 바꾸거나 int& Empty; 로 선언할 수 없는 이유를 포인터·참조 차이 3가지로 쓰시오.
(3) SetToZero가 Hp를 못 바꾼 이유와, 바꾸도록 고친 선언 두 가지를 쓰시오.
(4) Hp, Ptr, Shield(변수 자체), *Shield, GScore의 메모리 영역을 쓰고 스택과 힙의 차이(해제 시점·속도·크기·수명 관리)를 설명하시오.

### P1-020 (0.29점)

struct FEnemy { int Hp; };
void Spawn(int Count)
{
    for (int i = 0; i < Count; ++i)
    {
        FEnemy* E = new FEnemy{ 100 };
        E->Hp -= 10;
    }                               // (가)
}
int main()
{
    FEnemy* Boss   = new FEnemy{ 900 };
    FEnemy* Target = Boss;
    delete Boss;
    Boss = nullptr;                 // (나)
    if (Boss != nullptr) { Boss->Hp = 0; }
    Target->Hp -= 50;               // (다)
    Spawn(3);
    FEnemy A{ 300 };
    FEnemy B = A;                   // (라)
    B.Hp = 1;
    FEnemy* P = &A;
    P->Hp = 7;
    cout << A.Hp << ' ' << B.Hp << '\n';   // (마)
}
(1) Spawn(3)으로 누수되는 객체 수와, 언제 왜 해제할 수 없게 되는지 쓰시오.
(2) (나)에서 nullptr로 만들었는데도 (다)가 위험한 이유를 댕글링 개념으로 쓰시오.
(3) (마)의 출력과 이유를 쓰시오. C# class였고 A=new FEnemy{Hp=300}; B=A; B.Hp=1; P=A; P.Hp=7; 이면 A.Hp·B.Hp는? 'C++은 기본이 값 타입', 'C# 참조 타입 = 자동 관리되는 포인터' 관점으로 설명하시오.
(4) 누수와 댕글링의 차이를 증상 중심으로 쓰시오.

### P1-021 (0.29점)

class FEnemyBase
{
public:
    virtual void Move() { cout << "Base Move\n"; }
    void Shout() { cout << "Base Shout\n"; }
    virtual ~FEnemyBase() { cout << "~Base\n"; }
};
class FArcher : public FEnemyBase
{
public:
    FArcher() { Arrows = new int[50]; }
    void Move() override { cout << "Archer Move\n"; }
    void Shout() { cout << "Archer Shout\n"; }
    ~FArcher() { delete[] Arrows; cout << "~Archer\n"; }
private:
    int* Arrows;
};
int main()
{
    FEnemyBase* E = new FArcher();
    E->Move();    // ①
    E->Shout();   // ②
    delete E;     // ③
}
(1) ①~③ 출력과, ①②가 다르게 동작하는 이유를 쓰시오.
(2) ①의 원리를 vtable 개념으로 3줄 안팎으로 설명하시오.
(3) FEnemyBase 소멸자의 virtual을 지우면 ③의 출력과 결과는? 상속용 클래스 소멸자를 virtual로 하는 이유는?
(4) FArcher에 void Mvoe() override 오타를 내면? override 없이 오타를 내면 어떤 버그가 생기는가?
(5) final의 의미와 FArcher의 Move를 더 재정의 못 하게 하는 선언을 쓰고, ALifecycleProbe가 AActor를 상속하는 선언 첫 줄과 : public의 의미를 쓰시오.

### P1-022 (0.19점)

[코드 1]
void AArenaCharacter::BeginPlay()
{
    if (bDebugMode)
    {
        UE_LOG(LogTemp, Warning, TEXT("Debug start"));
        return;
    }
    Super::BeginPlay();
    SetupHUD();
}
증상: bDebugMode를 켠 BP_ArenaCharacter에서만 Event BeginPlay 노드가 실행되지 않는다.
[코드 2]
struct FScope
{
    int Id;
    FScope(int InId) { Id = InId; cout << "+" << Id << '\n'; }
    ~FScope() { cout << "-" << Id << '\n'; }
};
int main()
{
    FScope A(1);
    {
        FScope B(2);
        cout << "in\n";
    }
    FScope* C = new FScope(3);
    cout << "out\n";
    delete C;
}
(1) 증상의 원인을 Super::BeginPlay()의 역할과 연결해 쓰고(C# 비교 포함), 고친 코드를 쓰시오.
(2) [코드 2]의 출력 순서와 생성자·소멸자의 호출 시점·역할을 쓰시오.
(3) 컴파일 에러가 나는 곳을 모두 찾고 이유를 쓰시오.
class FInventory
{
public:    int GetCount() const { return Count; }
protected: void Sort() {}
private:   int Count = 0;
};
class FPlayerInventory : public FInventory
{
    void Test() { Sort(); Count = 5; }        // ① Sort ② Count
};
void External(FInventory& Inv) { Inv.GetCount(); Inv.Sort(); }   // ③ GetCount ④ Sort
(4) 세 접근 지정자의 차이와, 이렇게 나누는 이유를 한 줄로 쓰시오.

### P1-023 (0.19점)

// FWeaponStats: 이름(FString DisplayName)과 수치 20개를 가진 큰 구조체
01 TArray<int32> ComboScores;
02 SpringArm = CreateDefaultSubobject<USpringArmComponent>(TEXT("SpringArm"));   // 생성자 안
03 void AArenaCharacter::Look(const FInputActionValue& Value)
04 {
05     const FVector2D Axis = Value.Get<FVector2D>();
06     AddControllerYawInput(Axis.X);
07 }
08 AArenaCharacter* Hero = Cast<AArenaCharacter>(OtherActor);   // 어떤 함수 안
09 void PrintStats(FWeaponStats Stats)
10 {
11     auto Name = Stats.DisplayName;
12     UE_LOG(LogTemp, Log, TEXT("%s"), *Name);
13 }
14 void PrintAll(const TArray<FWeaponStats>& AllStats)
15 {
16     for (auto Stat : AllStats) { PrintStats(Stat); }
17 }
18 int32 AddScore(const int32& Score);
(1) 1·2·8행의 < > 안 타입의 뜻과, 8행에서 OtherActor가 캐릭터가 아니면 Hero는?
(2) 3행의 const와 &의 의미, 비슷한 C# 매개변수, & 없이 받으면 달라지는 점을 쓰시오.
(3) 11행·16행 auto의 추론 타입과 불필요한 복사 수정을 쓰시오.
(4) 9행의 문제와 수정을 쓰시오.
(5) 18행을 어떻게 고치고 왜 그런가?

### P1-024 (0.19점)

class IInteractTarget
{
public:
    virtual void OnInteract() __(가)__ ;   // 자식이 반드시 구현
    virtual ~IInteractTarget() {}
};
class ISaveable { public: virtual void Save() = 0; virtual ~ISaveable() {} };
class FPropBase { public: void Highlight() {} };
class FChest __(나)__     // FPropBase를 부모로, 두 인터페이스 함께 구현
{
public:
    void OnInteract() override { cout << "Open\n"; }
    void Save() override { cout << "Saved\n"; }
};
class FLever : public FPropBase, public IInteractTarget
{
public:
    void OnInteract() override { cout << "Pull\n"; }
};
int main()
{
    FChest Chest;  FLever Lever;
    IInteractTarget* T = &Lever;  T->OnInteract();   // ①
    ISaveable* S = &Lever;                             // ②
    ISaveable* S2 = &Chest;  S2->Save();             // ③
    IInteractTarget Raw;                               // ④
}
(1) (가)(나)를 채우고, (가) 함수와 그 함수를 가진 클래스의 명칭을 쓰시오.
(2) ①~④의 컴파일 여부와, 되는 줄은 출력, 안 되는 줄은 이유를 쓰시오.
(3) C# class Chest : PropBase, IInteractTarget, ISaveable과 같은 구조를 C++에서 만드는 방법을 '인터페이스 용도의 다중 상속'으로 설명하시오.
(4) C++ 추상 클래스와 C# interface의 차이 2가지 이상과, ISaveable에 int SaveVersion = 1; 을 넣을 수 있는지 쓰시오.

### P1-025 (0.29점)

[코드 1]
int Add(int A, int B) { return A + B; }
int Mul(int A, int B) { return A * B; }
int main()
{
    int (*Op)(int, int) = &Mul;   // 함수 포인터
    int R = Op(3, 4);
    Op = &Add;
    R = Op(R, 5);
    cout << R << '\n';
}
[코드 2]
void AWeaponSpawner::LoadWeapon()
{
    UAssetManager::GetStreamableManager().RequestAsyncLoad(WeaponPath,
        FStreamableDelegate::CreateLambda([this]()
        {
            SpawnLoadedWeapon();
            bLoaded = true;
        }));
}
(1) [코드 1]의 출력과 함수 포인터 개념을 C# Action/Func와 비교해 쓰시오.
(2) [this]가 캡처하는 것과 SpawnLoadedWeapon()을 바로 부를 수 있는 이유를 쓰고 C# 람다와 비교하시오.
(3) 로딩이 끝나기 전에 스포너가 레벨 전환으로 파괴됐다. 콜백 때 생길 수 있는 일과 이유를 쓰시오.
(4) (3)을 막는 방법 2가지 이상과 그중 하나의 코드를 쓰시오.
(5) SetTimer(Handle, [this]() { ... }, 5.f, false) 같은 타이머에서도 같은 위험이 생기는 이유를 한두 줄로 쓰시오.

### P1-026 (0.19점)

01 class UArenaAnimInstance : public UAnimInstance   // UCLASS·GENERATED_BODY 생략
02 {
03 public:
04     virtual void NativeInitializeAnimation() override;
05     virtual void NativeUpdateAnimation(float DeltaSeconds) override;
06     bool IsMoving() { return Speed > 3.f; }              // (가)
07     void ResetSpeed() const { Speed = 0.f; }             // (나)
08     float GetDirection() const { return Direction; }     // (다)
09 protected:
10     UPROPERTY(BlueprintReadOnly) float Speed = 0.f;
11     UPROPERTY(BlueprintReadOnly) float Direction = 0.f;
12     UPROPERTY() TObjectPtr<AArenaCharacter> CachedCharacter;
13 };
14 void UArenaAnimInstance::NativeInitializeAnimation()
15 {
16     Super::NativeInitializeAnimation();
17     ____(1)____
18 }
19 void UArenaAnimInstance::NativeUpdateAnimation(float DeltaSeconds)
20 {
21     Super::NativeUpdateAnimation(DeltaSeconds);
22     ____(2)____
23     Speed = CachedCharacter->GetVelocity().Size2D();
24 }
25 bool CanPlayFootstep(const UArenaAnimInstance& Anim) { return Anim.IsMoving(); }   // (라)
(1) (가)(나)(다)를 '문제없음/컴파일 에러/const를 붙여야 함'으로 판단하고 이유를 쓰시오. (나)는 어떻게 고치는가?
(2) (라)의 컴파일 여부와, const 멤버 함수의 약속·const 참조에서 호출 가능한 이유를 쓰시오.
(3) 빈칸 (1)(2)를 채우시오.
(4) '매번 NativeUpdateAnimation에서 Cast하면 되지 않냐'는 말에 반대 이유를 쓰시오.

### P1-027 (0.19점)

적이 죽을 때 떨어뜨리는 '드롭 항목 1개(아이템 이름 FName, 드롭 확률 float, 희귀도)'를 표현하려 한다. 희귀도는 일반·희귀·전설 3단계이고, 기획자가 블루프린트에서 값을 확인한다.
(1) 동료가 "struct로 만들면 멤버가 기본 private이라 밖에서 못 쓴다"고 말했다. 이 말의 무엇이 틀렸는지 바로잡고, 그렇다면 struct와 class의 실제 차이는 무엇인지 쓰라.
(2) 이 데이터를 UCLASS(UObject)가 아니라 USTRUCT로 만드는 것이 언리얼 관례에 맞는 이유를 쓰라.
(3) 드롭 항목 구조체와 희귀도 enum을 블루프린트에 노출되도록 선언하라.

### P1-028 (0.29점)

(1) 동료 코드에서 다음 선언을 발견했다. 문제와 올바른 선언을 쓰라.
    TSharedPtr<UWeaponData> CurrentWeaponData;  // UWeaponData는 UPrimaryDataAsset 파생
(2) 다음 두 상황에 맞는 포인터 타입을 고르고 이유를 쓰라.
  (a) 일반 C++ 클래스 FSoundQueue 객체를 HUD가 '참조는 하되 수명은 늘리지 않게' 들고 있다가, 쓸 때마다 아직 살아 있는지 확인한다.
  (b) 일반 C++ 설정 객체 FGameOptions를 여러 곳이 공유하며 절대 null이면 안 된다.
(3) std::unique_ptr·std::shared_ptr·std::weak_ptr에 대응하는 UE 타입을 쓰고, 셋의 소유 방식 차이를 '누가 지우는가' 관점에서 설명하라.

### P1-029 (0.29점)

(1) 채팅 시스템에서 FChatRoom은 TArray<TSharedPtr<FChatUser>> Users로 참가자를, FChatUser는 TSharedPtr<FChatRoom> CurrentRoom으로 방을 가리킨다. 방을 닫고 외부 참조를 모두 놓았는데 메모리가 줄지 않는다. 왜 그런지, 어느 쪽을 어떻게 바꿔야 하는지 쓰라.
(2) AI 경로점 5만 개가 든 TArray<FVector> PathPoints를 SetPath(TArray<FVector> InPoints)로 넘기는 코드가 프로파일러에 크게 잡힌다. 넘긴 뒤 PathPoints는 쓰지 않는다. '이동'이 왜 싸게 넘기는지 원리를 설명하고, 고친 호출 한 줄을 쓰라. 이동 후 PathPoints.Num()은 얼마라고 보는 것이 맞는가?
(3) 동료가 "소멸자 하나만 직접 만들었는데 객체를 대입하니 크래시가 난다"고 한다. Rule of Three/Five로 원인을 설명하고, 이런 문제를 아예 피하는 Rule of Zero를 설명하라.

### P1-030 (0.19점)

다음 코드를 읽고 답하라.

class AArenaCharacterBase : public ACharacter {
    GENERATED_BODY()
public:
    UPROPERTY() TObjectPtr<UCombatComponent> Combat;  // (가)
};

// 다른 파일: 아이템 상자 액터
void AArenaLootBox::Open(AArenaCharacterBase* Who)
{
    Who->Combat = nullptr;   // (나) 실수로 전투 기능을 지워 버림
}

void AArenaRangedEnemy::UpdateAI(int32 Mode)
{
    if (Mode == 0) { /* 대기 */ }
    else if (Mode == 1) { /* 거리 유지 */ }
    else if (Mode == 2) { /* 발사 */ }
    else if (Mode == 3) { /* 재장전 쿨다운 */ }
}

// 풀에서 재사용하는 회복 아이템
class AArenaHealPickup : public AActor {
    bool bConsumed = false;
    float HealAmount = 30.f;   // 웨이브 보너스로 실행 중 바뀔 수 있음
};

(1) (나) 같은 사고를 막으면서 자식 클래스(AArenaPlayerCharacter, AArenaEnemy)는 계속 Combat을 쓸 수 있게 하려면 (가)를 어떻게 바꾸는가? public·protected·private 차이로 설명하라.
(2) int 숫자 Mode로 AI 상태를 나누는 방식의 문제를 쓰고, 네 상태를 enum class로 선언한 뒤 UpdateAI의 매개변수 타입을 바꿔 쓰라.
(3) 회복 아이템을 풀에 반환했다가 다시 꺼냈더니 먹어지지 않고(bConsumed가 true로 남음), 회복량도 지난 웨이브 값이 남는다. 상태 리셋 함수의 이름·내용·호출 시점을 설계하라.

### P1-031 (0.29점)

아래 코드를 Epic C++ 코딩 표준 기준으로 리뷰하라.

// ArenaWeapon.h
#pragma once
#include "ArenaWeapon.generated.h"
#include "GameFramework/Actor.h"
enum weaponKind { SWORD, AXE };
struct weaponInfo { float dmg; int ammo; };
UCLASS()
class ArenaWeapon : public AActor {
    GENERATED_BODY()
public:
    UStaticMeshComponent* mesh;        // UPROPERTY 없음
    int32 GetAmmo() { return Info.ammo; }
    bool Equipped;
    weaponInfo Info;
    void DoEverything(float DeltaTime);  // Tick에서 호출, 120줄
};

// ArenaWeapon.cpp
#include "Engine/World.h"
#include "ArenaWeapon.h"
// DoEverything: 입력 확인 → 탄약 계산(최대 30 하드코딩) → 사운드 재생 → HUD 텍스트 갱신 → 히트 판정

(1) 코딩 표준 위반을 5개 이상 찾고 각각 고친 모습을 쓰라(접두사, const, include 순서, UObject 멤버 포인터 포함).
(2) DoEverything을 어떻게 나누고 이름 짓겠는가? Tick에서 매번 할 필요 없는 일은 무엇인가?
(3) 루브릭 '코드 품질'(1 하드코딩·거대 클래스 / 2 C++ 베이스 + BP 자식, 네이밍 준수 / 3 컴포넌트 책임 분리, 데이터 분리, GC 안전 / 4 확장 지점 설계 + 테스트, 리뷰하기 좋은 PR 크기)로 이 코드가 몇 점인지 근거와 함께 쓰고, 3점이 되려면 무엇이 필요한지 쓰라.

### P1-032 (0.29점)

아이템 시스템을 만든다. 플레이어가 지금까지 주운 '고유 아이템 액터'는 다시 주워도 중복 기록되면 안 되고, 아이템 ID(FName)로 아이템 정의를 찾는 표, 화면 왼쪽에 표시할 '획득 순서대로의 로그'가 필요하다.
(1) 세 용도에 맞는 언리얼 컨테이너와 C# 대응을 쓰라.
(2) TArray<AActor*> NearbyItems를 범위 기반 for로 순회해 유효한 아이템만 이름을 로그로 찍는 코드 뼈대를 쓰라. 원소 타입이 포인터라는 점이 코드에 어떻게 드러나는가?
(3) 동료가 매 프레임 PickedItems.Contains(Item)을 TArray로 2,000개에 대해 검사한다. 무엇이 문제이고 어떻게 바꾸는지 복잡도로 설명하라.
(4) TSet<AActor*>에 아이템을 넣을 때 무엇이 '키'가 되는가? 같은 블루프린트에서 스폰된 똑같은 포션 2개를 주우면 집합에 몇 개가 들어가는가? 이유는?
(5) 스택 push/pop, 큐 push/pop, 연결 리스트에서 k번째 원소 찾기의 복잡도를 쓰고, TArray 순회가 연결 리스트 순회보다 빠른 이유를 한 줄로 쓰라.

### P1-033 (0.19점)

(1) C# List<float> damages; damages.Add(12.5f); string playerName = "Hero"; 를 언리얼 타입으로 바꾸면?
(2) [학생 X]
TArray<int32> Scores;
Scores.Add(10);
int32* Best = &Scores[0];
for (int32 i = 0; i < 1000; ++i) { Scores.Add(i); }
*Best += 5;
[학생 Y] X와 같되 첫 Add 전에 Scores.Reserve(1100); 이 있다.
(가) 두 코드 끝의 Num() (나) 어느 쪽 마지막 줄이 위험하고 다른 쪽은 왜 안전한지 용량·재할당으로 (다) Y도 위험해지는 경우
(3) Num()과 용량(Slack)의 차이와, Add마다 한 칸씩 늘리지 않는 이유를 쓰시오.
(4) Hits.Add(FHitInfo(Loc, 20.f))와 Hits.Emplace(Loc, 20.f)의 차이는?
(5) 매 프레임 적 300마리 거리 목록을 새 TArray에 담아 정렬하는 함수에서 메모리 할당이 많이 보인다. 무엇을 바꾸겠는가?

### P1-034 (0.29점)

(1) 게임과 메신저를 동시에 실행했다. 메신저가 게임 변수를 직접 바꿀 수 없는 이유와, 게임 안의 게임 스레드·워커 스레드는 같은 변수를 동시에 건드릴 수 있는 이유를 프로세스·스레드 차이로 쓰고, 언리얼 주요 스레드 2가지 이상을 쓰시오.
(2) 게임 스레드와 워커 스레드의 역할을 쓰시오.
(3) 두 스레드가 같은 int KillCount에 KillCount++를 각각 1000번 실행하면 항상 2000인가? 데이터 경쟁으로 설명하시오.
(4) 게임 스레드 부담을 줄이려고 '워커 스레드(B)에서 해도 안전한 일은 모두 B로 옮긴다'는 원칙을 세웠다. 이 원칙에 따라 ①~⑤를 NativeUpdateAnimation(게임 스레드, A)과 NativeThreadSafeUpdateAnimation(워커 스레드, B) 중 어디에 둘지 이유와 함께 쓰시오. 둘 다 부적절하면 그렇게 쓰시오.
① Velocity = CachedCharacter->GetVelocity();
② Speed = Velocity.Size2D();
③ CachedCharacter->GetCharacterMovement()->MaxWalkSpeed = 300.f;
④ bCachedFalling = CachedCharacter->GetCharacterMovement()->IsFalling();
⑤ bIsInAir = bCachedFalling;
(5) NativeThreadSafeUpdateAnimation의 규칙을 한 문장으로 쓰고, 게임 객체 값을 안전하게 읽는 방법 2가지를 쓰시오.

### P1-035 (0.29점)

[설명형] 학생 클래스 ADoorActor(public: 영역)에 다음 네 멤버가 있다.
① UPROPERTY(VisibleAnywhere, Category="Door") TObjectPtr<UStaticMeshComponent> DoorMesh;
② UPROPERTY(EditAnywhere, meta=(ClampMin="1.0")) float OpenSeconds = 2.f;
③ UPROPERTY(EditAnywhere, BlueprintReadWrite, Category="Door") bool bLocked = false;
④ int32 OpenCount = 0;   // UPROPERTY 없음
(1) C#은 System.Reflection으로 클래스 정보를 알아낸다. 표준 C++에는 이런 기능이 없는데, 언리얼은 어떻게 클래스 정보를 알아내는지 UHT와 매크로(UCLASS·UPROPERTY·UFUNCTION·USTRUCT·UENUM)로 설명하라. 그리고 이 정보를 쓰는 엔진 시스템 세 가지를 예로 들라.
(2) ①~④ 각각에 대해 [BP 기본값 창에서 / 레벨에 놓은 문의 디테일 패널에서 / BP 그래프에서] 무엇이 가능한지 표로 채우라. ②에 0.2를 입력하면 어떻게 되는지도 쓰라.
(3) 아래는 ObjectMacros.h namespace UP 주석 3개의 요지다. 각 주석이 어떤 지정자의 것인지 고르고 내 말로 옮기라.
가. can be read or written from a blueprint
나. visible in all property windows, but cannot be edited
다. Specifies the category of the property. Usage: Category=CategoryName

### P1-036 (0.29점)

[설명형] (1) 다음 상황마다 NewObject·CreateDefaultSubobject·SpawnActor 중 무엇을 쓰는지 고르고 이유를 한 줄로 쓰라.
가. 전투 중 독 버프 정보를 담는 UBuffInfo(UObject 파생) 객체를 만든다.
나. ADoorActor 생성자에서 감지용 박스 콜리전 컴포넌트를 만든다.
다. 원거리 적이 투사체 AArenaProjectile을 발사한다.
(2) 학생이 투사체를 NewObject<AArenaProjectile>(this)로 만들었더니 화면에 아무것도 나타나지 않았다. 무엇이 잘못됐는지 설명하라. 같은 학생은 ADoorActor 생성자에서 GetWorld()->GetFirstPlayerController()로 플레이어를 찾아 멤버에 저장하려 했다. 이것도 왜 안 되는지, 어디로 옮겨야 하는지 쓰라.
(3) ADoorActor 생성자에 UE_LOG를 넣었더니 Play를 누르기 전, 에디터를 켤 때 이미 로그가 찍혔다. 그 이유를 CDO로 설명하라. CDO가 이후 만드는 문 인스턴스와 어떤 관계인지도 쓰라.

### P1-037 (0.48점)

[설명형] 학생 클래스 UWaveManager(UObject 파생)에 다음 멤버가 있다.
UPROPERTY() TArray<TObjectPtr<UWaveRule>> Rules;   // NewObject로 만든 규칙들
UWaveReward* PendingReward;                       // NewObject로 생성, UPROPERTY 없음
(1) GC의 동작 원리를 '루트 → 참조 그래프' 텍스트 그림 1장과 3문장으로 설명하라. 그림에 Rules의 원소와 PendingReward를 모두 넣으라. UWaveManager 자신은 게임 쪽 UPROPERTY로 붙잡혀 있다고 가정한다.
(2) 웨이브가 끝나고 몇 분 뒤 PendingReward->Grant()에서 크래시가 났다. 언제나 나는 것도 아니었다. 원인과 '가끔'인 이유를 설명하라.
(3) 학생이 'TObjectPtr은 원시 포인터와 뭐가 다르냐'고 묻는다. ObjectPtr.h 상단 주석 내용에 기대어 UE5에서 멤버를 TObjectPtr로 쓰는 이유를 설명하라.
(4) 체력바 위젯이 '내가 표시하는 적'을 기억한다. 적이 죽으면 위젯이 적을 살려 두면 안 된다. 어떤 포인터를 쓰고 사용 전에 무엇을 확인하는지 쓰라.

### P1-038 (0.19점)

[코드 읽기] UGCLabNote는 학생이 만든 빈 UObject 클래스다.

UCLASS()
class AGCLabActor : public AActor
{
    GENERATED_BODY()
    UGCLabNote* Raw = nullptr;              // UPROPERTY 없음
    UPROPERTY() TObjectPtr<UGCLabNote> Registered;
    TWeakObjectPtr<UGCLabNote> SeeRaw, SeeRegistered;
    FTimerHandle Timer;
    int32 Round = 0;
protected:
    virtual void BeginPlay() override;
    void Report();
};
void AGCLabActor::BeginPlay()
{
    Super::BeginPlay();
    Raw = NewObject<UGCLabNote>(this);
    Registered = NewObject<UGCLabNote>(this);
    SeeRaw = Raw;  SeeRegistered = Registered;
    GetWorldTimerManager().SetTimer(Timer, this, &AGCLabActor::Report, 3.f, true);
}
void AGCLabActor::Report()
{
    ++Round;
    UE_LOG(LogArena, Warning, TEXT("[%d] Raw:%s Registered:%s"), Round,
        SeeRaw.IsValid() ? TEXT("alive") : TEXT("gone"),
        SeeRegistered.IsValid() ? TEXT("alive") : TEXT("gone"));
    if (Raw != nullptr) { UE_LOG(LogArena, Warning, TEXT("%s"), *Raw->GetName()); }  // (★)
}

Play 후 4초쯤 GC를 강제로 실행했다. 그 사이 자동 GC는 돌지 않았다고 가정한다.
(1) [1]과 [2] 줄에 찍힐 내용을 예측하고 이유를 쓰라.
(2) 학생은 (★)에 nullptr 검사를 넣었으니 안전하다고 말한다. [2]에서 이 말이 맞는지 판단하고, 관찰 결과를 바르게 확인하려면 무엇을 검사해야 하는지 쓰라.
(3) Play 중 GC를 강제로 돌리려면 무엇을 입력하는지, 이 실험에서 왜 강제로 돌리는지 쓰라.

### P1-039 (0.19점)

[설명형] (1) 다음 값을 FName·FString·FText 중 무엇으로 저장할지 고르고 이유를 한 줄씩 쓰라.
가. 화면 아래 상호작용 안내 문구 'E: 문 열기'(일본어판에서는 일본어로 바뀌어야 함)
나. 스켈레톤의 뼈 이름 spine_01로 위치를 찾을 때 쓰는 이름
다. 세이브 파일 이름을 'Slot_' + 플레이어 이름으로 만들어 쓸 문자열
(2) 적 100마리가 매 프레임 태그 이름을 비교한다. 이때 FString 대신 FName을 쓰면 빠른 이유를 NameTypes.h에서 확인한 FName의 저장 방식으로 설명하라. FName(TEXT("Goblin")) == FName(TEXT("GOBLIN"))의 결과도 쓰라.
(3) 다음 두 줄을 언리얼 관례에 맞게 고쳐 쓰라.
FString Slot = FString("Slot_") + PlayerName;
UE_LOG(LogArena, Log, "Saved");

### P1-040 (0.10점)

[코드 읽기] 학생이 전투 로그 카테고리를 만들었다.

// CombatLog.h
#pragma once
#include "CoreMinimal.h"
DECLARE_LOG_CATEGORY_EXTERN(LogCombat, Log, All);

// HealthComponent.cpp
#include "CombatLog.h"
void UHealthComponent::ApplyDamage(float Amount)
{
    Health -= Amount;
    UE_LOG(_____①_____, Error, _____②_____("Health below zero: %f"), Health);
}

// WaveManager.cpp  (CombatLog.h를 include하지 않음)
void UWaveManager::StartWave()
{
    UE_LOG(LogCombat, Warning, TEXT("Wave start"));
}

(1) ①과 ②를 채우라. Health가 -10이면 이 로그가 Output Log에 어떻게 보이는지(카테고리·단계·색) 쓰라.
(2) 이 프로젝트에는 DEFINE_LOG_CATEGORY(LogCombat);가 어디에도 없다. 무엇이 문제인지, 어느 파일에 어떻게 넣어야 하는지 쓰라.
(3) WaveManager.cpp를 빌드하면 어떤 문제가 생기는지 이유와 함께 쓰라. 고치는 방법도 쓰라.

### P1-041 (0.39점)

[설명형] 유니티에서 옮겨 온 학생이 다음처럼 말한다. '언리얼 생성자가 Awake니까 거기서 GetWorld()로 플레이어를 찾고, Start 대신 Tick 첫 프레임에서 초기화할게요.'
(1) 언리얼 액터의 생명주기 순서(생성자 → … → GC)를 쓰라. 이를 근거로 학생 계획의 두 군데를 바로잡으라.
(2) 유니티 Awake/Start/Update/OnDestroy와 언리얼 함수의 대응을 표로 쓰라. 대응이 1:1이 아닌 이유를 CDO로 설명하라.
(3) Actor.h 선언 주석을 근거로 PostInitializeComponents와 BeginPlay가 각각 언제 불리는지, EndPlay는 어떤 경우들에 불리는지 내 말로 쓰라.
(4) 학생이 BeginPlay 중단점에서 콜스택을 캡처해 엔진 노트 01-actor-lifecycle.md를 쓰려 한다. 콜스택에서 Actor.cpp의 어떤 함수들이 보일지 쓰고, 그중 부모 BeginPlay가 맡는 일(컴포넌트 BeginPlay·블루프린트 BeginPlay 호출)을 설명하라. 노트에 함께 넣을 나머지 두 요소도 쓰라.

### P1-042 (0.29점)

[코드 읽기] ALifecycleProbe를 부모로 만든 BP 자식 BP_LifecycleProbe를 레벨에 1개 놓았다. 이 BP는 Event BeginPlay에서 Print String으로 'BP Ready'를 찍는다. 이 액터에는 학생이 만든 UFloatMotionComponent가 붙어 있다. 이 컴포넌트는 자신의 BeginPlay에서 시작 높이를 저장하고 움직이기 시작한다.

ALifecycleProbe::ALifecycleProbe()
{ PrimaryActorTick.bCanEverTick = true; UE_LOG(LogArena, Warning, TEXT("(a)")); }

void ALifecycleProbe::Tick(float DeltaTime)
{ Super::Tick(DeltaTime); if (!bLogged) { bLogged = true; UE_LOG(LogArena, Warning, TEXT("(b)")); } }

void ALifecycleProbe::PostInitializeComponents()
{ Super::PostInitializeComponents(); UE_LOG(LogArena, Warning, TEXT("(c)")); }

void ALifecycleProbe::EndPlay(const EEndPlayReason::Type Reason)
{ Super::EndPlay(Reason); UE_LOG(LogArena, Warning, TEXT("(d)")); }

void ALifecycleProbe::BeginPlay()
{ Super::BeginPlay(); UE_LOG(LogArena, Warning, TEXT("(e)")); }

(1) Play 후 2초 뒤 Stop했다. (a)~(e)와 'BP Ready'가 찍히는 순서를 쓰라. 'BP Ready'와 (e)의 앞뒤가 왜 그렇게 되는지 설명하라.
(2) 다른 학생이 BeginPlay를 { UE_LOG(LogArena, Warning, TEXT("(e)")); }로만 썼다(Super 호출 없음). 그러자 '부유 컴포넌트가 안 움직이고 BP의 Print도 안 나온다'고 했다. 원인을 설명하라.

### P1-043 (0.29점)

[설명형] 보물상자 액터 ATreasureChest를 만든다. 필요한 부분은 ① 상자 몸통 메시(충돌 있음) ② 뚜껑이 돌 경첩 위치(보이지 않는 기준점) ③ 경첩에 붙어 열리며 회전하는 뚜껑 메시 ④ 어떤 아이템을 줄지 고르는 보상 로직이다.
(1) ①~④ 각각을 UActorComponent·USceneComponent·UPrimitiveComponent 중 무엇으로 만들지 고르고 이유를 쓰라. RootComponent와 부착 계층도 쓰라.
(2) 이 상자를 유니티라면 어떤 구조로 만들었을지 쓰라. 언리얼의 'Actor + 여러 Component'와 대응시키라.
(3) 경첩은 몸통 기준 상대 위치 (0,-40,60)이다. 뚜껑은 경첩 기준 (0,40,0)이다. 상자 액터는 월드 (-300,0,0)에 있다(회전 없음). 뚜껑의 월드 위치를 구하라. 플레이어가 상자를 (-300,500,0)으로 밀었을 때 뚜껑의 상대·월드 위치가 각각 어떻게 되는지 쓰라. 상대/월드 Transform 개념으로 설명하라.

### P1-044 (0.29점)

[설명형] 포탑 ATurret 60개가 깔린 맵에서 게임 스레드 시간이 높다. 포탑의 Tick에서 지금 다음 일을 매 프레임 한다.
가. 플레이어가 사거리 안에 있는지 트레이스로 확인
나. 탄창이 비면 2초 뒤 재장전(누적 시간 변수로 직접 계산)
다. 플레이어를 조준 중일 때 포신을 목표 방향으로 매 프레임 부드럽게 회전
라. 머리 위 아이콘을 '공격 중/대기' 상태에 맞춰 매 프레임 바꿔 끼움
(1) 가~라를 각각 Tick 유지 / TickInterval / SetActorTickEnabled로 필요할 때만 / 타이머 / 델리게이트 이벤트 중 무엇으로 바꿀지 고르고 이유를 쓰라. Tick 대신 타이머를 쓰는 기준을 한 문장으로 쓰라.
(2) 다 때문에 Tick이 '조준 중'에만 필요하다. 참고: PrimaryActorTick.bCanEverTick이 false인 액터는 Tick 함수가 아예 등록되지 않아, 나중에 SetActorTickEnabled(true)를 불러도 Tick이 돌지 않는다. 생성자와 조준 시작·종료 때 Tick 설정을 어떻게 할지 쓰라(bCanEverTick 값 포함).
(3) 아무도 근처에 없는 포탑 60개에서 이 정리가 어떤 비용을 줄이는지 설명하라.

### P1-045 (0.29점)

[설명형] 유니티 2인 협동 생존 게임의 GameManager가 다음 일을 모두 했다.
가. 플레이어 개인별 처치 수와 사망 횟수(상대도 볼 수 있음)
나. 게임 오버 조건 검사와 다음 단계로 넘어가는 규칙
다. 현재 단계 이름과 남은 적 수(두 플레이어 화면에 표시)
라. 내 화면에만 보이는 체력바·미니맵 그리기
마. 마우스 시점 회전과 키 입력 처리
바. 총을 들고 달리는 캐릭터 몸체
(1) 가~바를 언리얼 GameMode·GameState·PlayerController·Pawn/Character·PlayerState·HUD에 하나씩 나눠 담으라. 각 클래스의 역할을 한 줄씩 쓰라.
(2) 리슨 서버 2인 플레이에서 GameMode·GameState는 어느 컴퓨터에 존재하는지 쓰라. 클라이언트 쪽 코드가 GameMode에서 '남은 적 수'를 읽으려 하면 어떻게 되는지 쓰라.
(3) 유니티의 GameManager 방식과 언리얼 방식의 차이를 한 문단으로 쓰라.
(4) 학생이 Play를 눌렀는데 엔진 기본 Pawn이 나오고 AArenaCharacter가 안 나온다. GameModeBase.h의 어떤 속성을 확인해야 하는지 쓰라. 그 레벨에서 내 GameMode가 쓰이는지도 함께 확인해야 하는 이유를 쓰라. InitGame이 무엇을 하는 시점인지도 쓰라.

### P1-046 (0.19점)

[설명형] 학생의 3인칭 캐릭터가 마우스를 조금만 움직여도 몸 전체가 카메라와 같이 휙휙 돈다. 원하는 동작은 '평소엔 카메라만 돌고 몸은 이동 방향을 향함, 조준 버튼을 누르는 동안은 몸이 카메라 정면을 향함'이다.
(1) ACharacter의 기본 컴포넌트 3개와 3인칭 카메라용 컴포넌트 2개를 쓰고, 각각 이 증상과 관계가 있는지 짧게 쓰라. Character.h에서 이동 컴포넌트를 얻는 함수 이름도 쓰라.
(2) 컨트롤러 회전과 캐릭터 회전의 차이로 증상의 원인을 설명하라. '평소'와 '조준 중'에 bUseControllerRotationYaw와 CMC의 bOrientRotationToMovement를 각각 어떻게 둘지 쓰라.
(3) 이 학생은 유니티에서 CharacterController로 이동을, Input System Action Map으로 '평소/조준' 입력을 나눴다. 언리얼에서 각각 무엇으로 바꾸는지 쓰라.

### P1-047 (0.29점)

[설명형] 걸어 다닐 때 Space는 '점프', Shift는 '달리기'다. 말(탈것)에 타면 Space가 '박차(가속)', Shift가 '내리기'여야 하고, 마우스 시점은 그대로 써야 한다.
(1) InputAction(IA), InputMappingContext(IMC), Trigger, Modifier, ETriggerEvent의 역할을 한 줄씩 쓰라. '내리기'를 실수로 누르지 않게 0.5초 눌러야 발동시키려면 어디에 무엇을 설정할지 쓰라.
(2) 탈것용 IMC를 따로 두는 이유를 쓰라. 말에 탈 때와 내릴 때 로컬 플레이어 서브시스템에 무엇을 하는지 쓰라. 기본 IMC를 지우지 않고 그대로 둔다면 Priority를 어떻게 줘야 Space가 점프 대신 박차로 동작하는지, Priority 매개변수의 뜻과 함께 쓰라.
(3) EnhancedInputComponent.h의 BindAction으로 묶을 수 있는 함수 형태 2가지 이상을 쓰라. '박차'는 Started, '달리기 종료'는 Completed에 묶는 이유를 쓰라.
(4) Space 키가 탈것 상태에서 AArenaCharacter::Boost까지 가는 흐름도(키 → IMC → IA → Trigger → 바인딩 함수)를 텍스트로 그리라.

### P1-048 (0.39점)

[설명형] 경비병이 (100,200,0)에 서서 정면 Forward = (0,1,0)을 보고 있다. 침입자는 (900,-400,0)에 있다. 경비병 시야는 정면 기준 좌우 45°(총 90°)다. 참고: cos45°≈0.71, cos53°≈0.60, cos60°=0.50, cos127°≈-0.60
(1) 경비병→침입자 벡터와 그 길이를 구하라. 정규화한 방향을 구하고, 방향을 비교하기 전에 정규화하는 이유를 쓰라.
(2) Forward와 정규화된 방향의 내적을 구하라. 침입자가 앞·뒤 어느 쪽인지, 사이각이 약 몇 도인지, 시야 안인지 판정하고 근거를 쓰라. 정규화하지 않은 벡터로 내적하면 값이 얼마인지도 쓰라.
(3) Forward × 방향(외적)의 Z 성분을 구해 좌·우를 판정하라. 이 판정이 맞는지 확인하는 방법을 쓰라.
(4) 이 계산을 유니티 Vector3.Dot / Vector3.Cross 대신 언리얼에서 쓸 함수 이름과, Vector.h의 연산자 버전으로 각각 한 줄씩 써 보라.

### P1-049 (0.19점)

[설명형] (1) 포탑이 현재 방향에서 목표 방향으로 1초 동안 부드럽게 돌아야 한다. Pitch·Yaw·Roll 값을 각각 따로 보간했더니 중간에 이상하게 꺾이고, 위를 바라볼 때 회전이 튀었다. 원인을 FRotator와 FQuat 차이로 설명하라. 어떻게 바꿀지와 쿼터니언을 쓰는 이유 3가지도 쓰라.
(2) 액터가 월드 (0,300,0)에 있고 Yaw 180°만 돌아 있다(스케일 1). 로컬 좌표 (200,0,50)에 붙은 머리 위 아이콘의 월드 좌표를 구하라. 로컬→월드 변환의 개념을 설명하라.
(3) 유니티 프로젝트의 '위로 5만큼 올리기' 코드 (0,5,0)을 언리얼로 그대로 옮기면 어떤 일이 생기는지 쓰라. 두 엔진의 좌표계(손잡이·위·앞)를 비교해 설명하라.
(4) 신입 면접 'CS 기본 — 3D 수학 요약' 질문에 답할 핵심 4가지를 한 줄씩 쓰라.

### P1-050 (0.29점)

[코드 읽기] 피격 방향 코드다. Hit*Montage는 UPROPERTY로 지정한 몽타주다. 참고: KismetAnimationLibrary의 CalculateDirection(Velocity, BaseRotation)은 BaseRotation 정면 기준 Velocity 방향 각도를 -180~180으로 돌려주며, 오른쪽이 +다.

float AArenaCharacter::GetHitDirection(const FVector& HitFrom) const
{
    FVector ToHit = HitFrom - GetActorLocation();
    ToHit.Z = 0.f;
    const float Len = ToHit.Size();                  // 벡터 길이
    if (Len <= 0.f) { return 0.f; }
    const FVector Dir = ToHit / _______①_______;
    const FVector Fwd = GetActorForwardVector();     // 정면, 길이 1
    float Deg = FMath::RadiansToDegrees(FMath::Acos(Fwd | Dir));
    const float SideZ = (Fwd ^ Dir).Z;
    Deg = (SideZ _______②_______ 0.f) ? Deg : -Deg;
    DrawDebugString(GetWorld(), HitFrom, SideZ > 0.f ? TEXT("R") : TEXT("L"),
        nullptr, FColor::White, 2.f);
    return Deg;
}
UAnimMontage* AArenaCharacter::PickHitMontage(float Deg) const
{
    if (FMath::Abs(Deg) <= 60.f)  return HitFrontMontage;
    if (FMath::Abs(Deg) >= 120.f) return HitBackMontage;
    return (Deg > 0.f) ? HitRightMontage : HitLeftMontage;
}

(1) ①을 채우고 이 줄이 하는 일을 쓰라. ②에 들어갈 비교 연산자를 쓰고 이유를 쓰라. Fwd | Dir와 Fwd ^ Dir가 각각 무엇을 계산하는지도 쓰라.
(2) 캐릭터는 (1000,500,0)에서 +X를 보고 있다. 공격자 P(1000,900,0), Q(700,400,0), S(1200,300,0) 각각에 대해 Deg의 부호와 대략 값, 선택되는 몽타주, 화면 글자(R/L)를 쓰라.
(3) 다른 학생이 ②에 <를 넣었다. P로 실험한 로그가 'MyDeg=-90.0 CalcDir=90.0'이었다. 이 로그가 무엇을 알려 주는지, 이 상태에서 P에 대해 어떤 몽타주가 재생되는지 쓰라.

### P1-051 (0.29점)

[설명형] 줍기 인터페이스를 만든다. 체력 물약 APotionPickup은 C++에서, 열쇠 BP_KeyPickup은 블루프린트 Class Settings에서 인터페이스를 추가해 구현한다.

UINTERFACE(MinimalAPI, Blueprintable)
class UPickupable : public UInterface { GENERATED_BODY() };

class ACTIONARENA_API IPickupable
{
    GENERATED_BODY()
public:
    UFUNCTION(BlueprintNativeEvent, BlueprintCallable)
    void OnPickedUp(AActor* Picker);
};

(1) 위 선언에서 UPickupable과 IPickupable이 각각 맡는 일을 쓰라. 왜 C#처럼 interface 하나로 끝나지 않는지 리플렉션과 연결해 설명하라. APotionPickup 헤더의 클래스 선언 첫 줄(상속 부분)을 쓰라.
(2) 줍기 코드가 다음과 같다. 열쇠를 주워도 아무 일이 없다.
IPickupable* P = Cast<IPickupable>(Overlapped);
if (P) { P->OnPickedUp(this); }
원인을 설명하고, C++ 물약과 BP 열쇠 모두에서 동작하도록 고친 코드를 쓰라.
(3) 유니티에서 IPickupable(C# interface)을 GetComponent<IPickupable>()로 찾아 부르던 방식과, 언리얼 방식의 대응을 설명하라.

### P1-052 (0.39점)

[설명형] UStaminaComponent가 '스태미나 바닥남' 이벤트(인자 없음)와 '스태미나 변화'(현재 값 float 1개)를 알린다. 듣는 쪽: 스태미나 변화는 블루프린트 HUD 위젯과 C++ 캐릭터 AArenaCharacter의 StopSprint 함수가 듣는다. 바닥남은 C++ 내부의 AI 판단 클래스 UFatigueBrain만 듣는다.
(1) 델리게이트 4종(단일/멀티캐스트 × 일반/다이나믹)의 차이를 쓰라. '스태미나 변화'와 '바닥남'에 각각 어떤 종류를 고를지 이유와 함께 쓰라.
(2) DelegateCombinations.h의 이름 규칙에 따라 두 델리게이트 타입(FOnStaminaChanged, FOnStaminaDepleted)의 선언을 한 줄씩 쓰라.
(3) AArenaCharacter의 StopSprint를 '스태미나 변화'에 바인딩하는 한 줄을 쓰라. 이때 StopSprint 선언에 꼭 필요한 것도 쓰라. UFatigueBrain의 OnDepleted 멤버 함수를 '바닥남'에 바인딩하는 한 줄도 쓰라. 캐릭터가 EndPlay에서 자신의 바인딩을 한꺼번에 해제하는 코드를 쓰라. 람다로 붙이려면 어떤 함수를 쓰는지도 쓰라.
(4) 다이나믹 델리게이트를 모든 곳에 쓰면 안 되는 이유를 쓰라. 유니티 C# event·Action·UnityEvent와 대응시키라.

### P1-053 (0.19점)

[설명형] 압력판 APressurePlate을 밟으면 가시 함정 ASpikeTrap 3개가 튀어나오고 문 1개가 닫힌다. 조건은 '압력판은 함정·문 클래스를 몰라야 한다'이다.
(1) 옵저버 패턴의 핵심 문장('보내는 쪽은 받는 쪽을 모른다')을 이 상황에 맞춰 설명하라. 델리게이트 Broadcast와 연결하라.
(2) 다음 세 설계를 장단점으로 비교하라.
가. 압력판이 TArray<ASpikeTrap*>와 ADoorActor*를 들고 각각의 함수를 직접 부른다.
나. 압력판이 OnPressed 멀티캐스트 델리게이트를 가지고, 함정·문이 자기가 반응할 압력판을 지정받아 바인딩한다.
다. 압력판이 TArray<AActor*> 대상 목록을 들고, 인터페이스 구현 여부를 확인해 Execute_로 '작동' 함수를 부른다.
(3) 6개월 포트폴리오 규모라는 전제로 하나를 골라 근거를 쓰라. 고른 설계에서 '함정 중 하나가 파괴된 뒤 압력판을 밟는 경우'에 주의할 점을 쓰라.

### P1-054 (0.19점)

[설명형] 학생의 원거리 적 코드 일부다.

void ARangedEnemy::BeginPlay()
{
    Super::BeginPlay();
    GetWorldTimerManager().SetTimer(AimTimer, this, &ARangedEnemy::CheckLineOfSight, 0.25f, true, 1.0f);
}
void ARangedEnemy::CheckLineOfSight()
{
    if (!Target.IsValid()) { return; }
    FHitResult Hit;
    const bool bHit = GetWorld()->LineTraceSingleByChannel(Hit, GetActorLocation(),
        Target->GetActorLocation(), ECC_Visibility);
    bCanShoot = bHit && Hit.GetActor() == Target.Get();
}

(1) 이 코드가 언제부터, 얼마나 자주, 무엇을 판정하는지 흐름으로 설명하라(마지막 인자 1.0f 포함).
(2) 유니티로 같은 일을 했다면 타이머와 트레이스를 각각 무엇으로 만들었을지 쓰라(코루틴·InvokeRepeating·Physics.Raycast 중심으로).
(3) 이 판정을 SweepSingleByChannel(구)로 바꾸면 무엇이 달라지는지 쓰라. 시야 판정에는 라인 트레이스가 더 맞는 이유도 쓰라.
(4) 적이 죽을 때 이 반복 타이머를 멈추는 방법을 쓰라. Target이 TWeakObjectPtr인 이유도 한 줄로 쓰라.

### P1-055 (0.29점)

[설명형] 다른 학생이 이렇게 만들었다. ① AnimGraph 안에 '캐릭터 속도 계산' 노드들을 넣었다. ② NativeInitializeAnimation에서 Speed를 한 번 계산해 두고 끝냈다. ③ 상태 머신에 Idle, Move, Jump 세 상태만 두고 Jump에서 바로 Idle로 돌아오게 했다.
(1) EventGraph와 AnimGraph의 역할을 쓰고, ①이 왜 맞지 않는지 쓰라.
(2) ②의 문제를 쓰라. NativeInitializeAnimation과 NativeUpdateAnimation에서 각각 할 일을 바르게 나눠 쓰라.
(3) 1D 블렌드스페이스에 Idle(0), Walk(150), Run(450)이 있다. Speed가 375일 때 어떤 애니메이션이 대략 어떤 비율로 섞이는지 쓰라. 블렌드스페이스가 왜 '상태 3개 전환'보다 로코모션에 자연스러운지 쓰라.
(4) ③을 Idle/Move ↔ Jump/Fall/Land 구조로 고치라. 상태 목록과 각 트랜지션 룰 조건을 쓰라.

### P1-056 (0.19점)

[설명형] (1) 구르기(회피) 애니메이션은 3m를 이동한다. 학생 A는 애니메이션은 제자리 구르기로 두고 코드로 캐릭터를 밀었다. 학생 B는 루트 모션을 썼다. 두 방식의 차이를 쓰라. 2인 협동 게임에서 B가 구르기를 몽타주로 재생하고 'Root Motion from Montages Only'로 두는 이유를 쓰라.
(2) 유니티에서 Animator Controller로 'Speed 파라미터 > 0.1이면 Idle→Run'을 만들었다. 이것을 언리얼 AnimBP에서 무엇으로 만드는지(변수·상태·조건) 대응시켜 쓰라.
(3) 유니티 프로젝트에서는 이동 스크립트, 전투 스크립트, 피격 스크립트가 각자 animator.SetBool·SetFloat를 불렀다. 언리얼에서 같은 값을 다루는 구조를 '밀어 넣기 vs 당겨오기'로 비교하라. 장단점과, 이 구조가 멀티스레드 애니메이션 업데이트에 유리한 이유를 쓰라.
(4) 엔진 노트 03-anim-update.md용으로 두 구조를 텍스트 화살표 그림으로 그리라. 그림에 위 세 스크립트(또는 그에 해당하는 언리얼 쪽 클래스)를 넣으라.

### P1-057 (0.29점)

차지 공격 몽타주 ChargeMontage에는 섹션 Start, Loop, Release가 있다. Loop는 버튼을 누르는 동안 반복돼야 한다.

void UCombatComponent::BeginPlay()
{
    Super::BeginPlay();
    AnimInstance = OwnerMesh->GetAnimInstance();
    AnimInstance->OnMontageBlendingOut.AddDynamic(this, &UCombatComponent::HandleBlendingOut);
    AnimInstance->OnMontageEnded.AddDynamic(this, &UCombatComponent::HandleEnded);
}
void UCombatComponent::OnChargePressed()
{
    AnimInstance->Montage_Play(ChargeMontage);
    AnimInstance->Montage_SetNextSection(TEXT("Start"), TEXT("Loop"), ChargeMontage); // (가)
    AnimInstance->Montage_SetNextSection(TEXT("Loop"),  TEXT("Loop"), ChargeMontage); // (나)
    bIsCharging = true;
}
void UCombatComponent::OnChargeReleased()
{
    if (!bIsCharging) return;
    AnimInstance->Montage_JumpToSection(TEXT("Release"), ChargeMontage);          // (다)
    bIsCharging = false;
}
void UCombatComponent::HandleBlendingOut(UAnimMontage* Montage, bool bInterrupted)
{
    if (Montage == ChargeMontage) { SetMovementEnabled(true); }
}
void UCombatComponent::HandleEnded(UAnimMontage* Montage, bool bInterrupted)
{
    if (Montage == ChargeMontage) { bIsCharging = false; ClearChargeState(); }
}

(1) 몽타주 에셋 안에서 섹션 정보는 어떤 구조로 저장되는가? Slot은 무엇이고, 이 몽타주가 보이려면 AnimBP에 무엇이 필요한가?
(2) 버튼을 3초 누르고 있다가 뗐다. 재생되는 섹션 순서를 쓰고 (가)(나)(다) 각각의 역할을 설명하라.
(3) (다)를 Montage_SetNextSection(TEXT("Loop"), TEXT("Release"), ChargeMontage)로 바꾸면 체감이 어떻게 달라지는가?
(4) 버튼을 떼기 전에 적에게 맞아 피격 몽타주가 같은 슬롯에서 재생됐다. HandleBlendingOut과 HandleEnded는 어떤 순서로 불리며 bInterrupted는 무엇인가? 이 상황에서 HandleEnded가 bIsCharging을 false로 만드는 것이 왜 중요한가?

### P1-058 (0.19점)

유니티 프로젝트를 언리얼로 옮기고 있다. 유니티 쪽 구현은 다음과 같았다.
- 구르기 애니메이션 상태의 StateMachineBehaviour: OnStateEnter에서 무적 ON, OnStateExit에서 무적 OFF
- 구르기 클립의 12프레임에 Animation Event "SpawnDust"로 먼지 이펙트 1회 생성
(1) 두 기능을 언리얼에서는 각각 무엇으로 구현하는지, 왜 그것이 대응되는지 쓰라.
(2) 동료가 무적 구간을 'AnimNotify 2개(무적 시작, 무적 끝)'로 만들자고 한다. AnimNotifyState 1개로 만드는 것과 비교해, 구간 처리 관점에서 어느 쪽이 나은지 이유를 쓰라.
(3) AnimNotify와 AnimNotifyState의 차이를 일반화해 설명하고, 전투에서 각각의 대표적 쓰임을 2개씩 쓰라.

### P1-059 (0.29점)

QA 버그 리포트: "공격 2타 도중 적에게 맞아 경직된 뒤, 다음 공격들이 적을 전혀 못 맞힌다. 가끔은 반대로 가만히 서 있는데도 근처 적이 계속 데미지를 입는다." 판정은 UAnimNotifyState_HitWindow의 NotifyBegin에서 켜고 NotifyEnd에서 끈다. 맞은 적 목록은 TSet으로 관리하고 NotifyBegin에서 비운다.
(1) 두 증상이 각각 왜 생길 수 있는지 노티파이 처리 흐름으로 설명하라. 노티파이에만 의존할 때 문제가 되는 상황을 이 경우 말고도 2가지 더 쓰라.
(2) 고치기 위한 안전장치를 어디에 무엇을 두는지 쓰라.
(3) 기획자가 "2타 입력이 자꾸 씹힌다"고 한다. 현재는 노티파이 윈도우 방식이다. 콤보 입력 윈도우의 개념을 설명하고, 입력 큐 방식으로 바꿀 때의 장점과 새로 생기는 위험을 쓰라.
(4) 수정 후 확인할 체크리스트를 4개 쓰라.

### P1-060 (0.29점)

방패를 든 적을 추가한다. 요구사항: 플레이어의 무기 판정은 방패에 막혀야 하고(방패 뒤 몸은 안 맞음), 플레이어 캐릭터 자신은 방패를 통과해 걸어 다녀도 되며(이동 충돌 없음), 바닥의 독 장판은 밟고 있는 동안만 감지하면 된다.
(1) 독 장판과 무기 판정에 각각 Overlap 이벤트와 Sweep 트레이스 중 무엇을 쓰겠는가? 두 방식의 장단점을 근거로 쓰라.
(2) 방패 컴포넌트에 새 Object Channel 'Shield'를 주고, 무기 판정은 Trace Channel 'Weapon'으로 한다. Object Channel과 Trace Channel의 차이를 설명하고, 요구사항을 만족하도록 방패의 응답(Weapon 채널, Pawn 채널)을 정하라.
(3) 무기가 방패에 막혔을 때 FHitResult로 ① 불꽃 이펙트 위치·방향 ② 막은 것이 방패인지 몸인지 구분하는 방법을 쓰라(BoneName·맞은 컴포넌트 등).
(4) 유니티에서 'Weapon 레이어와 Shield 레이어는 충돌, Player와 Shield는 무시'를 Layer Collision Matrix로 설정하던 것을 언리얼 개념으로 옮겨 설명하라.

### P1-061 (0.29점)

플레이어와 적이 각각 따로 구현돼 있다.
- 플레이어: 피격 시 체력 감소 → 화면 흔들림 → 피격 몽타주. 공격은 입력 콜백에서 몽타주·Sweep 판정을 직접 처리
- 적: 피격 시 체력 감소(복사본) → BT에 '피격됨' 표시 → 피격 몽타주. 공격은 BT 태스크가 적 클래스 안의 별도 공격 함수(플레이어 코드 복사본)를 호출
(1) 동료가 "적도 플레이어 공격 코드를 복사해 쓰면 빠르다"고 한다. 공격 로직을 UCombatComponent로 분리하는 편이 나은 이유를 쓰라.
(2) 공통 베이스 클래스로 올릴 멤버·함수와 자식에 남길 것을 나눠 쓰라.
(3) 피격 처리를 '공통 흐름(체력 감소 → 피격 몽타주)은 부모, 다른 부분(화면 흔들림 / BT 표시)만 자식'으로 설계하라. 가상 함수 이름·선언·override 위치를 쓰라.
(4) 면접관이 "플레이어와 적을 공통 베이스 클래스로 리팩터링한 이유는?"이라고 묻는다. 이 프로젝트 상황에 맞춰 '중복·데미지 파이프라인·버그 수정 위치' 관점으로 답하라. 또 자식이 (3)의 훅 대신 부모의 피격 함수 전체를 override하면서 Super 호출을 빼먹으면 무엇이 깨지는지, (3)의 설계가 이 실수를 어떻게 줄이는지 쓰라.

### P1-062 (0.39점)

(1) 함정 '독 장판'은 위에 서 있는 캐릭터에게 1초마다 5 데미지, '폭발 화살'은 맞은 지점·뼈에 따라 리액션이 달라야 한다. 각각 UGameplayStatics::ApplyDamage와 ApplyPointDamage 중 무엇을 쓰고 왜인가? ApplyDamage의 매개변수(대상, 데미지량, 가해 컨트롤러, 가해 액터, 데미지 종류)를 독 장판 상황에 맞게 채운 호출 한 줄을 쓰라.
(2) 독 장판에 UDamageType_Poison(학생이 만든 UDamageType 자식)을 넘겼다. 받는 쪽에서 이것을 어떻게 활용할 수 있는가?
(3) ApplyDamage를 호출한 순간부터 HealthComponent의 OnHealthChanged가 브로드캐스트되기까지의 흐름을 함수·델리게이트 이름으로 쓰라. 엔진의 어느 구현이 데미지 델리게이트를 브로드캐스트하는가?
(4) 동료의 버그: 플레이어 클래스에서 TakeDamage를 override해 '무적이면 0 반환'만 넣었더니, 무적이 아닐 때도 체력바가 안 줄어든다. 코드에 무엇이 빠졌는지와 그 이유를 쓰라.
(5) 유니티 SendMessage("TakeDamage")와 언리얼 방식의 대응과 차이를 쓰라.

### P1-063 (0.29점)

다음 코드를 읽고 답하라. FWeaponRow는 FTableRowBase를 상속한 행 구조체(Damage, Range)이다. State.Stunned·State.Dead 태그는 프로젝트에 등록돼 있다.

void UHealthComponent::BeginPlay()
{
    Super::BeginPlay();
    GetOwner()->OnTakeAnyDamage.AddDynamic(this, &UHealthComponent::OnDamaged);   // (가)
}
void UHealthComponent::OnDamaged(AActor* DamagedActor, float Damage,
    const UDamageType* DamageType, AController* InstigatedBy, AActor* DamageCauser)
{
    if (OwnerTags.HasTag(FGameplayTag::RequestGameplayTag(TEXT("State.Dead")))) return;
    Health -= Damage;                                                             // (나)
    OnHealthChanged.Broadcast(Health, MaxHealth);
}

float UArenaWeaponComponent::GetDamageFor(FName WeaponId) const
{
    TArray<FWeaponRow*> Rows;
    WeaponTable->GetAllRows<FWeaponRow>(TEXT("Lookup"), Rows);
    for (FWeaponRow* R : Rows)                                                    // (다)
    {
        if (R->Range > 300.f) return R->Damage;
    }
    return 0.f;
}

(1) (가)가 하는 일을 설명하고, 데미지를 주는 무기 코드가 HealthComponent를 직접 호출하지 않아도 체력이 깎이는 이유를 쓰라. OnDamaged가 호출되지 않는다면 의심할 것 2가지를 쓰라(선언·부모 클래스 쪽).
(2) (나)의 문제 2가지(체력 범위, 회복 데미지 등)를 찾아 고쳐라.
(3) (다)는 WeaponId를 쓰지 않아 엉뚱한 행을 돌려준다. 행 이름으로 한 행만 찾는 함수로 고쳐 쓰고, FindRow와 GetAllRows가 각각 어떤 상황에 맞는지 쓰라.
(4) 적이 기절했을 때 State.Stunned 태그를 붙이고 풀리면 떼려 한다. GameplayTags로 상태를 표시하는 방식이 bool 변수(bIsStunned, bIsDead…)를 늘리는 것보다 나은 점을 쓰라.

### P1-064 (0.29점)

(1) 다음 데이터를 DataAsset과 DataTable 중 어디에 둘지 고르고 이유를 쓰라.
  ① 레벨 1~100의 필요 경험치(열: 레벨, 필요 경험치) — 기획자가 엑셀로 곡선을 조정
  ② 스킬 8종: 스킬마다 아이콘·이펙트·몽타주를 참조하고, '화염 스킬' 부모 데이터를 상속해 일부만 바꿈
  ③ 캐릭터 스탯(MaxHealth, WalkSpeed, SprintSpeed, JumpZVelocity) — 플레이어 1명분, 다른 에셋 참조 없음 (어느 쪽이든 가능하다면 근거를 들어 하나를 고르라)
(2) 유니티 개발자 동료에게 ScriptableObject와 'CSV를 Resources에서 읽어 직접 split하던 코드'가 언리얼에서는 무엇으로 바뀌는지 설명하라.
(3) 상점 UI가 '모든 스킬 데이터 목록'을 하드코딩 배열 없이 얻고 싶다. Primary Asset ID와 Asset Manager가 이 문제를 어떻게 푸는지, UPrimaryDataAsset::GetPrimaryAssetId가 어떤 역할을 하는지 설명하라.

### P1-065 (0.19점)

AArenaEnemy와 웨이브 스포너에 다음 값이 하드코딩돼 있다.
① 고블린·오크·트롤 등 적 40종의 체력·이동 속도·드롭 골드 ② 보스 전용 등장 몽타주와 페이즈별 무기 메시 ③ 웨이브 간 휴식 시간 10.f ④ 사망 후 Destroy까지 5초 ⑤ 로그 카테고리 이름 ⑥ 적 이름 표시용 폰트 크기 18
(1) 각 값을 데이터로 뺄지, 뺀다면 DataAsset/DataTable 중 어디로 갈지 정하고 이유를 쓰라(③④⑥은 근거가 있으면 어느 쪽이든 인정).
(2) CSV 재임포트 후 어떤 적의 이동 속도가 0으로 들어와 적이 멈춰 버렸다. 이런 잘못된 데이터를 막는 방어 코드를 어디에 두고 무엇을 하겠는가?
(3) 팀에 공유할 ADR-0002를 쓴다. 저장 위치와, 이 결정에서 '선택지' 표와 '결과(좋아진 점/감수한 비용/다시 볼 조건)'에 무엇을 쓸지 쓰라.
(4) 기획자가 "수치 하나 바꾸려고 매번 프로그래머에게 빌드를 부탁한다"고 불평한다. 데이터 주도 설계가 이 상황을 포함해 협업에 주는 이점을 3가지 이상 쓰라.

### P1-066 (0.29점)

일시정지 메뉴 위젯 UArenaPauseWidget(C++ 부모)은 ESC를 누를 때마다 RemoveFromParent → AddToViewport로 같은 인스턴스를 숨겼다 다시 띄운다. 위젯은 GameState의 OnWaveChanged 델리게이트를 구독해 '현재 웨이브'를 표시한다. QA 리포트: "일시정지를 다섯 번 열고 닫은 뒤 웨이브가 바뀌면 웨이브 갱신 로그가 다섯 번 찍힌다."
(1) 개발자는 구독 코드를 NativeConstruct에만 넣었다. NativeConstruct/NativeDestruct 호출 시점으로 원인을 설명하고 고쳐라.
(2) 다른 개발자는 "그냥 위젯 Tick에서 매 프레임 GameState의 웨이브 번호를 읽어 텍스트에 넣으면 버그가 없다"고 한다. 이 방식과 Property Binding의 비용 문제를 설명하고 델리게이트 방식과 비교하라.
(3) C++에서 웨이브 텍스트 블록을 쓰려고 UPROPERTY(meta=(BindWidget)) TObjectPtr<UTextBlock> WaveText; 를 선언했다. 이 메타 지정자가 하는 일과, BP 디자이너에 WaveText가 없을 때의 결과를 쓰라.
(4) 유니티 Canvas/UGUI와 비교해 언리얼 UI 시스템의 이름과 'C++ 부모 + BP 레이아웃' 구성의 의미를 쓰라.

### P1-067 (0.29점)

던전 BP가 몬스터 스포너 50개를 갖고, 각 스포너는 UPROPERTY(EditAnywhere) TSubclassOf<AArenaEnemy> EnemyClass; 로 몬스터 BP 클래스를, UPROPERTY(EditAnywhere) TObjectPtr<USoundBase> SpawnSound; 로 사운드를 하드 참조한다. 던전에 들어가기만 해도 아직 나오지 않을 보스 몬스터의 텍스처까지 메모리에 올라온다.
(1) 왜 '아직 스폰하지 않은' 보스의 텍스처까지 로드되는지 설명하라. 소프트 레퍼런스로 바꾸면 무엇이 달라지는가?
(2) EnemyClass와 SpawnSound를 소프트 레퍼런스로 바꾼 선언을 쓰고, 두 선언의 타입이 왜 다른지 쓰라.
(3) 동료가 "TSoftObjectPtr을 쓰면 엔진이 알아서 메모리에 들고 있다가 쓸 때 준다"고 한다. TSoftObjectPtr이 실제로 저장하는 것을 근거로 이 말을 바로잡아라.
(4) 보스방 문이 열릴 때 보스 클래스를 바로 써야 해서 동기 로드로 불러오려 한다. 코드 한 줄과, 유니티에서 이에 대응하는 API, 그리고 이 방식의 위험을 쓰라.

### P1-068 (0.29점)

상점에서 무기 아이콘 텍스처 20개(TArray<TSoftObjectPtr<UTexture2D>>)를 비동기로 불러와 위젯에 표시한다. 상점 위젯 UArenaShopWidget이 요청한다.
(1) 이 흐름을 '요청 → 로딩 중 → 완료 콜백 → 표시' 4단계로 나누고, 단계마다 생길 수 있는 버그를 쓰라. 특히 ① 로딩 중 플레이어가 상점을 닫아 위젯이 제거·파괴됨 ② 상점을 빠르게 열고 닫기를 반복해 같은 요청이 여러 번 나감 ③ 표시 후 핸들을 바로 놓음 — 각각 어떤 결과가 생기는가?
(2) FStreamableHandle의 역할을 쓰고, '핸들을 유지하지 않고 다른 참조도 없으면' 어떤 일이 생기는지 아이콘 표시 상황으로 설명하라.
(3) 콜백을 [this] 람다 대신 안전하게 만드는 방법 2가지를 쓰라.
(4) 유니티에서 Addressables.LoadAssetAsync로 하던 일과 대응시키고, 언리얼에서 비동기 로드 함수 RequestAsyncLoad와 그 관리자를 얻는 GetStreamableManager가 각각 어느 엔진 헤더·클래스에 있는지, 반환 타입은 무엇인지 쓰라.

### P1-069 (0.29점)

레벨에 배치한 적이 BeginPlay 이후 가만히 서 있다는 버그를 조사한다. 적 BP의 AIController Class는 AArenaAIController로 지정돼 있다.

void AArenaAIController::BeginPlay()
{
    Super::BeginPlay();
    APawn* Player = UGameplayStatics::GetPlayerPawn(this, 0);
    MoveToActor(Player, 50.f);
}

(1) AIController와 Pawn의 관계를 설명하고, 'AIController가 Pawn을 Possess하지 못하면' 위 코드가 왜 아무 효과가 없는지 쓰라.
(2) MoveToActor가 실패할 수 있는 원인 2가지(레벨 설정 포함)와 실패/성공 결과를 코드에서 확인하는 방법을 쓰라.
(3) 결국 BT로 AI를 돌리기로 했다. 컨트롤러가 Pawn을 빙의하는 순간 virtual void OnPossess(APawn* InPawn)이 호출된다. BeginPlay 대신 이 함수에서 무엇을 호출해야 하는지 코드로 쓰고, 그 이유를 쓰라.
(4) 유니티 개발자 동료가 "NavMeshAgent.SetDestination이랑 같은 거죠?"라고 묻는다. 같은 점과 다른 점을 설명하라.

### P1-070 (0.29점)

성 경비병 AI 요구사항: (가) 경보가 울리면(Blackboard bAlarm = true) 경보 위치로 달려간다. (나) 플레이어가 보이면(TargetActor 설정) 추적해 공격한다. (다) 아무 일도 없으면 정해진 순찰 지점 사이를 오가며 지점마다 2초 대기한다. 우선순위는 (나) > (가) > (다)이다.
(1) 이 요구를 BT 텍스트 트리로 그려 엔진 노트 04-behavior-tree.md에 넣을 수 있게 하라. 각 노드에 종류(Composite/Task/Decorator/Service)와 역할을 한 줄씩 붙여라.
(2) 순찰 Sequence가 [다음 순찰 지점 계산 → MoveTo → Wait 2초]일 때, MoveTo가 실패(길 없음)하면 Wait은 실행되는가? Sequence와 Selector의 규칙으로 설명하라.
(3) 추적 중 플레이어와의 거리를 0.3초마다 Blackboard에 써 주는 노드는 어떤 종류이며, Task로 만들면 왜 어색한가?
(4) Decorator와 Task의 차이를 '조건'과 '행동'으로 설명하라.

### P1-071 (0.39점)

다음 C++ BT 노드를 읽고 답하라. URangedCombatComponent::BeginAim()은 2초 조준 후 발사하고 OnFireFinished(일반 멀티캐스트 델리게이트)를 브로드캐스트하며, CancelAim()은 조준을 취소한다.

UBTTask_AimAndFire::UBTTask_AimAndFire() { bCreateNodeInstance = true; } // AI마다 노드 인스턴스 생성

EBTNodeResult::Type UBTTask_AimAndFire::ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
{
    AArenaEnemy* Enemy = Cast<AArenaEnemy>(OwnerComp.GetAIOwner()->GetPawn());
    if (!Enemy) return EBTNodeResult::Failed;
    CachedComp = &OwnerComp;
    Enemy->Ranged->OnFireFinished.AddUObject(this, &UBTTask_AimAndFire::HandleFired);
    Enemy->Ranged->BeginAim();
    return EBTNodeResult::__(A)__;
}
void UBTTask_AimAndFire::HandleFired()
{
    __(B)__(*CachedComp, EBTNodeResult::Succeeded);
}
EBTNodeResult::Type UBTTask_AimAndFire::AbortTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
{
    __(C)__
    return EBTNodeResult::Aborted;
}

UBTService_FindCover::UBTService_FindCover() { __(D)__ }   // 1초마다 실행
void UBTService_FindCover::TickNode(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
{
    Super::TickNode(OwnerComp, NodeMemory, DeltaSeconds);
    const FVector Cover = FindNearestCover(OwnerComp);   // 학생 함수
    OwnerComp.GetBlackboardComponent()->SetValueAsVector(TEXT("CoverLocation"), Cover);
}

(1) 빈칸 (A)~(D)를 채우고 각각 왜 그런지 쓰라.
(2) 이 태스크의 실행 흐름을 'ExecuteTask 반환 → 조준 2초 동안 BT 상태 → 발사 완료 → BT 진행' 순서로 설명하라.
(3) 다른 태스크가 Blackboard의 CoverLocation을 GetValueAsVector로 읽어 MoveTo에 쓴다. Blackboard가 BT에서 하는 역할을 이 예로 설명하라.
(4) ExecuteTask가 반환할 수 있는 EBTNodeResult 값 중 Succeeded·Failed·InProgress의 의미를 각각 쓰라.

### P1-072 (0.29점)

원거리 적 BT: Root → Selector [ ① 공격 Sequence (Decorator: TargetActor Is Set, Observer Aborts = Self) , ② 탐색 Sequence (Decorator: LastKnownLocation Is Set) , ③ 대기 Wait ]
(1) 공격 중 플레이어가 시야에서 사라져 TargetActor가 비워졌다. ①에서 무슨 일이 일어나는가? 반대로 ② 탐색 중 플레이어가 다시 보여 TargetActor가 설정됐을 때, 현재 설정으로는 즉시 공격으로 바뀌는가? 바뀌게 하려면 무엇을 바꾸는가? Self / Lower Priority / Both를 각각 설명하라.
(2) 다음 요구를 기본 노드와 C++ 커스텀 노드로 나누고 이유를 쓰라: 거리 유지 이동, 2초 조준 후 투사체 발사(풀 Subsystem 사용), 발사 후 3초 쿨다운, 0.5초마다 플레이어와의 거리·시야 여부 갱신, 탐색 지점까지 이동 후 4초 두리번거리기.
(3) 신입 동료가 "StateTree가 최신이니 BT는 이제 몰라도 된다"고 한다. 두 도구의 구조 차이를 설명하고 이 말에 답하라.
(4) 유니티에서 넘어온 동료에게 언리얼 BT가 '엔진 내장'이라는 점이 왜 장점인지 설명하라.

### P1-073 (0.29점)

[상황] 원거리 적 AArenaArcherEnemy(컨트롤러 팀 ID 1)와 플레이어(IGenericTeamAgentInterface 구현, 팀 ID 0)가 있다. 시야 설정의 소속 감지는 '적(Enemies)'만 체크했다. 감지 처리 함수는 다음과 같다.

void AArenaArcherController::OnTargetPerceived(AActor* Actor, FAIStimulus Stimulus)
{
    Blackboard->SetValueAsObject(TEXT("TargetActor"), Actor);
}

문제 ①: 플레이어가 기둥 뒤로 숨어 시야에서 사라져도 적이 계속 쫓아온다.
문제 ②: 새로 만든 맵에서는 적이 유리창 너머의 플레이어를 전혀 감지하지 못한다(유리창 메시는 보이는 대로 둔 상태).

다음에 답하시오.
(1) 유니티라면 이 시야 체크를 어떻게 직접 만들었을지 쓰고, AI Perception이 대신 해 주는 것을 2가지 이상 쓰시오.
(2) 이 함수가 감지 이벤트에 연결되려면 어떤 이벤트에 어떻게 바인딩해야 하는지 쓰고, 문제 ①의 원인과 함수 수정 방향을 쓰시오.
(3) 팀 ID 0과 1 사이의 태도(Attitude)가 무엇이 되어 '적만 감지' 설정으로도 플레이어가 감지되는지 설명하고, 만약 플레이어가 팀 인터페이스를 구현하지 않았다면 어떻게 되는지 쓰시오.
(4) 시야 감지 점검 순서 5단계를 순서대로 쓰고, 문제 ②의 원인은 몇 번째 단계에서 잡히며 무엇을 확인해야 하는지 쓰시오.

### P1-074 (0.19점)

원거리 적 AI를 디버깅하는 4가지 상황이 있다. 각 상황에 Gameplay Debugger, Visual Logger, DrawDebug, 중단점 중 가장 알맞은 도구를 하나 고르고 이유를 한 줄로 쓰시오.
(가) 웨이브 5에서 10판에 한 번꼴로 원거리 적이 제자리에 멈춘다. 멈추기 직전에 어떤 판단을 했는지 나중에 확인하고 싶다.
(나) 적이 쏘는 방향 벡터가 실제로 플레이어 쪽을 향하는지 눈으로 보고 싶다.
(다) 지금 플레이 중인 적이 플레이어를 감지 중인지, 감지 범위가 어떻게 생겼는지 보고 싶다.
(라) 투사체 풀 반환 함수에서 같은 투사체가 두 번 반환되는 순간을 잡아 그 시점의 배열 내용과 호출 경로를 보고 싶다.

이어서 답하시오.
(2) Visual Logger를 쓰면 Gameplay Debugger로는 할 수 없는 무엇이 가능해지는지 '시간'의 관점에서 설명하시오.
(3) (가)를 분석하려고 AArenaArcherController::UpdateCombat 안에서 '현재 플레이어까지 거리'를 숫자로 Visual Logger에 남기는 한 줄을 쓰시오(거리 변수 이름은 Dist).

### P1-075 (0.29점)

다음은 원거리 마법사 적의 마법탄과 투사체 풀 코드다. AArenaMagicOrb, UProjectilePoolSubsystem(UWorldSubsystem 상속), AArenaCasterController는 학생이 만든 클래스이고, Pool은 UPROPERTY TArray<TObjectPtr<AArenaMagicOrb>>다.

// ① ArenaMagicOrb.cpp
AArenaMagicOrb::AArenaMagicOrb()
{
    Sphere = CreateDefaultSubobject<USphereComponent>(TEXT("Sphere"));
    RootComponent = Sphere;
    Movement = CreateDefaultSubobject<UProjectileMovementComponent>(TEXT("Movement"));
    Movement->(가) = 900.f;    // 느린 마법탄의 발사 속력
    Movement->(나) = true;     // 진행 방향을 바라보게
    Movement->ProjectileGravityScale = 0.f;
}
// ② ProjectilePoolSubsystem.cpp
void UProjectilePoolSubsystem::ReturnOrb(AArenaMagicOrb* Orb)
{
    Orb->Movement->StopMovementImmediately();
    Orb->SetActorHiddenInGame((다));
    Orb->SetActorEnableCollision((라));
    Orb->SetActorTickEnabled(false);
    Pool.Add(Orb);
}
AArenaMagicOrb* UProjectilePoolSubsystem::TakeOrb(const FTransform& Muzzle)
{
    if (Pool.Num() == 0) return GetWorld()->SpawnActor<AArenaMagicOrb>(OrbClass, Muzzle);
    AArenaMagicOrb* Orb = Pool.Pop();
    Orb->SetActorTransform(Muzzle);
    Orb->SetActorHiddenInGame(false);
    Orb->SetActorEnableCollision(true);
    Orb->SetActorTickEnabled(true);
    (마)   // 한 줄
    return Orb;
}
// ③ ArenaCasterController.cpp (BTService가 0.25초마다 호출)
void AArenaCasterController::UpdateCombat(AActor* Target)
{
    const float Dist = FVector::Dist(GetPawn()->GetActorLocation(), Target->GetActorLocation());
    if ((바))                        RetreatFrom(Target);   // 너무 가까우면 물러남
    else if (Dist > Stats.CastRange) MoveToActor(Target, Stats.CastRange - 100.f);
    else                             { StopMovement(); CastAt(Target); }
}

(1) (가)~(바)를 채우시오. (마)는 총구 앞 방향으로 발사 속력만큼 날아가게 하는 한 줄, (바)는 Stats.SafeDistance를 쓰는 조건이다.
(2) 풀이 비어 SpawnActor로 만든 마법탄은 (마) 없이도 날아가는데, Pop으로 꺼낸 마법탄은 (마)가 없으면 날아가지 않는다. 이유를 설명하시오.
(3) 기획자가 '바닥에 튕기며 굴러가는 마법탄'과 '플레이어를 추적하는 마법탄'을 요청했다. 직접 이동 코드를 짜야 하는지 답하시오.
(4) ③ 코드가 만드는 적의 행동을 거리 구간 3개로 설명하시오.

### P1-076 (0.19점)

투사체 풀을 넣은 뒤 테스터가 버그 2건을 보고했다.
버그 1: "투사체가 안 보이는데 맞았다. 맞은 위치는 아까 투사체가 사라졌던 곳 근처다."
버그 2: "재사용된 투사체는 첫 발에서 켰던 '불꽃 꼬리' 이펙트가 꺼져 있고, 남은 관통 횟수도 0인 채로 나온다. 두 값 모두 BeginPlay에서 설정하고 있다."
또 다른 팀원은 "PMC가 무거우니 Tick에서 위치를 직접 더해서 움직이자"고 말한다.

(1) 팀원의 제안에 반대하는 근거를 3가지 이상 쓰시오.
(2) 버그 2의 원인과 고치는 설계를 쓰시오.
(3) 버그 1의 원인을 쓰고, 풀에 반환할 때 꺼야 하는 것 3가지와 끄지 않으면 생기는 문제를 하나씩 쓰시오.

### P1-077 (0.19점)

Unreal Insights로 같은 맵·같은 조건에서 5회씩 측정해 중간값을 정리했다. 목표는 60fps(프레임당 약 16.6ms)다.

| 대상 | 생성 빈도 | 방식 | 1회 비용 | 비고 |
| 마법탄 투사체 | 초당 약 40발 | SpawnActor/Destroy | 0.35ms | 웨이브 후반 프레임 시간 20ms 안팎으로 상승 |
| 마법탄 투사체 | 초당 약 40발 | 풀(TakeOrb/ReturnOrb) | 0.02ms | 웨이브 후반 프레임 시간 15ms 안팎 |
| 보스 소환 연출 액터 | 스테이지당 1회 | SpawnActor | 1.50ms | 컷신 중 발생 |
| 바닥 핏자국 데칼 | 초당 약 3개 | 생성 | 0.04ms | 튐 없음 |

(1) 표를 해석해 어디에 풀을 적용하고 어디에는 적용하지 않을지 결정하고, 숫자를 근거로 이유를 쓰시오.
(2) '측정 후 결정' 원칙을 설명하고, 이 표가 없었다면 '1회 비용이 가장 큰 보스 연출 액터부터 풀링하자'는 판단이 왜 틀릴 수 있었는지 쓰시오.
(3) ADR-0003 '오브젝트 풀을 투사체에만 적용한 이유'의 「결정과 이유」와 「결과(좋아진 점 / 감수한 비용 / 다시 볼 조건)」를 작성하시오.

### P1-078 (0.29점)

학생이 투사체 풀과 저장 관리자를 다음처럼 만들었다.
- UArenaPoolManager: UObject를 상속하고 static UArenaPoolManager* Instance로 접근하는 싱글턴. 게임 레벨에서 처음 접근할 때 만든다.
- 메뉴 레벨 → 게임 레벨 → 메뉴 레벨 → 게임 레벨로 OpenLevel을 반복하면 두 번째 게임 레벨에서 Instance가 이미 사라진 이전 레벨의 투사체를 가리켜 크래시가 난다.
- 최고 기록과 설정을 관리하는 객체는 레벨이 바뀔 때마다 초기화돼 버린다.
유니티 출신인 학생은 "유니티에선 DontDestroyOnLoad와 UnityEngine.Pool로 끝났는데"라고 말한다.

(1) 풀과 기록·설정 관리자를 각각 어떤 Subsystem으로 바꿔야 하는지 쓰고, 유니티의 무엇에 대응하는지와 수명이 왜 맞는지 설명하시오.
(2) 위 크래시를 예로 들어, 싱글턴 대신 Subsystem을 쓰는 이유를 쓰시오.
(3) Subsystem 5종류(Engine·Editor·GameInstance·World·LocalPlayer)의 수명을 각각 한 줄로 쓰시오.
(4) 메뉴 레벨에는 풀이 필요 없다. WorldSubsystem.h의 어떤 함수로 이것을 처리하는지 쓰고, Initialize·Deinitialize가 각각 언제 무엇을 하는지 풀 예시와 함께 쓰시오.

### P1-079 (0.29점)

학생이 싱글플레이에서 남은 적 수 RemainingEnemies와 현재 웨이브 번호를 AArenaGameMode에 두고, HUD 위젯이 GetAuthGameMode로 읽어 표시하게 만들었다. 싱글에서는 잘 되었지만, Listen Server 2인으로 바꾸자 클라이언트 쪽 HUD만 웨이브와 남은 적이 표시되지 않는다.

(1) 클라이언트 HUD만 표시가 안 되는 이유를 GameMode가 존재하는 머신과 연결해 설명하시오.
(2) 다음을 GameMode와 GameState 중 어디에 둘지 분류하시오: (가) 남은 적 수 (나) 다음 웨이브까지 남은 초 (다) 적 스폰 위치 선택 함수 (라) 웨이브별 적 체력 배율 계산 (마) 현재 웨이브 번호 (바) EArenaPhase 단계를 바꾸는 함수
(3) 분류 기준을 한두 문장으로 쓰시오.
(4) 결과 화면에 '이번 판 참여자 이름 목록'을 보여 주려고 한다. GameStateBase.h에서 찾은 어떤 멤버를 쓰면 되는지, 그것이 무엇인지 쓰시오.

### P1-080 (0.19점)

학생이 설정 메뉴에서 값을 바꿀 때마다 저장하게 만들었다.

UCLASS()
class UArenaSettingsSave : public USaveGame
{
    GENERATED_BODY()
public:
    UPROPERTY() float MasterVolume = 1.0f;
    bool bInvertY = false;
    UPROPERTY() int32 BestScore = 0;
};

슬라이더를 움직일 때마다 UGameplayStatics::SaveGameToSlot을 호출한다. 테스트 결과 ① 볼륨 슬라이더를 끌면 화면이 뚝뚝 끊긴다. ② 재실행하면 볼륨과 최고 점수는 남아 있는데 Y축 반전 설정은 항상 꺼져 있다.

(1) ②의 원인을 'USaveGame에 무엇이 저장되는가'와 연결해 설명하고 고치시오.
(2) ①의 원인을 설명하고, 저장 함수를 무엇으로 바꾸며 왜 해결되는지 쓰시오.
(3) 유니티에서 같은 기능을 PlayerPrefs.SetFloat("Volume", v)로 만들었다면, 언리얼 USaveGame은 이것과 어떻게 대응되고 무엇이 다른지 쓰시오.

### P1-081 (0.19점)

v0.3.0 릴리즈 준비 중이다.

[상황 1] 패키징 단계에서 실패했다. 출력 로그 일부(간략화):
LogCook: Display: Cooking /Game/Maps/L_Arena
LogBlueprint: Error: [Compiler] BP_RangedEnemy : Function 'FireProjectile' not found (in node 'Call FireProjectile')
LogCook: Error: Unable to cook package /Game/AI/BP_RangedEnemy
Packaging: Error: Cook failed.
직전에 C++ 함수 AArenaRangedEnemy::FireProjectile의 이름을 FireAt으로 바꿨다.

[상황 2] 패키징된 Development 빌드가 원거리 적이 처음 공격할 때 꺼졌다. 크래시 정보의 콜스택 위쪽(간략화):
Unhandled Exception: EXCEPTION_ACCESS_VIOLATION reading address 0x0000000000000048
ActionArena!UProjectilePoolSubsystem::Acquire() [ProjectilePoolSubsystem.cpp:31]
ActionArena!AArenaRangedEnemy::FireAt() [ArenaRangedEnemy.cpp:112]
ActionArena!UBTTask_RangedAttack::ExecuteTask()
ActionArena!UBehaviorTreeComponent::ExecuteTask()

(1) 유니티 Build Settings → Build와 비교해, 언리얼 패키징에 포함된 단계가 무엇이고 그래서 이런 에러가 왜 패키징 때 드러나는지 쓰시오.
(2) 상황 1의 로그에서 원인을 읽어 내고 조치를 쓰시오.
(3) 상황 2의 로그·크래시 정보를 찾으려면 어느 폴더들을 보는지 쓰시오.
(4) 상황 2의 콜스택에서 문제가 난 함수와 호출 경로를 쓰고, 가장 유력한 원인과 확인할 것을 쓰시오.

### P1-082 (0.39점)

[상황] 스터디 팀이 PC 3대로 테스트한다. 서버 PC는 화면 없이 서버 프로그램만 돌리고, 플레이어 A·B는 각자 PC에서 접속한다. 플레이어 A의 공격 판정 코드가 A의 PC에서 다음처럼 실행된다.
EnemyHealth->Health -= 50.f;   // 적 체력은 복제되는 변수, 서버를 거치지 않음

(1) '서버 권위 모델'을 한두 문장으로 설명하시오.
(2) 위 코드가 실행되면 A 화면, B 화면, 서버에서 적 체력은 각각 어떻게 되는지, 그리고 잠시 뒤 A 화면은 어떻게 되는지 쓰고, 보안 측면의 문제도 쓰시오.
(3) 이 구성은 Listen Server와 Dedicated Server 중 무엇인지 쓰고, 둘의 차이를 쓰시오. 나중에 '친구 한 명이 방장이 되어 같이 플레이'하게 바꾸면 무엇이 되는지도 쓰시오.
(4) 서버 PC, A의 PC에서 NetMode는 각각 어떤 형태를 가리키는지 쓰고, NetMode가 무엇을 알려 주는 값인지 쓰시오.
(5) 올바른 흐름을 한 줄로 쓰시오.

### P1-083 (0.39점)

[상황] Dedicated Server 1대에 클라이언트 C1과 C2가 접속해 플레이한다. 레벨에는 서버가 조종하는 보스 AArenaBoss가 있다.

(1) 다음 표의 빈칸에 GetLocalRole() 값(Authority / AutonomousProxy / SimulatedProxy)을 채우시오.
| 액터 | 서버에서 | C1에서 | C2에서 |
| C1의 캐릭터 | (가) | (나) | (다) |
| 보스 | (라) | (마) | (바) |
(2) C2 화면에 보이는 C1 캐릭터의 움직임이 C1 화면에서보다 약간 늦고 부드럽게 따라오는 이유를 AutonomousProxy·SimulatedProxy 차이로 설명하시오.
(3) AArenaPlayerCharacter::OnDodge() 안에 두 가지 일을 넣으려 한다: ① 스태미나 차감(서버만) ② 회피 성공 UI와 카메라 연출(내가 조종하는 캐릭터에서만). 각각을 감쌀 if 조건을 쓰고 이유를 쓰시오. 그리고 전용 서버에서 ②의 조건이 어떤 값이 되는지 쓰시오.
(4) 유니티 Netcode의 IsServer, IsOwner는 각각 언리얼의 무엇에 대응하는지 쓰시오.

### P1-084 (0.39점)

다음은 NetLab의 복제되는 함정이다. AArenaTrap은 학생이 만든 클래스다.

// ArenaTrap.h (일부)
UPROPERTY(ReplicatedUsing = OnRep_Armed)
bool bArmed = true;
UFUNCTION()
void OnRep_Armed();

// ArenaTrap.cpp
#include "Net/UnrealNetwork.h"
AArenaTrap::AArenaTrap()
{
    PrimaryActorTick.bCanEverTick = false;
}
void AArenaTrap::GetLifetimeReplicatedProps(TArray<FLifetimeProperty>& OutLifetimeProps) const
{
    Super::GetLifetimeReplicatedProps(OutLifetimeProps);
    DOREPLIFETIME(AArenaTrap, bArmed);
}
void AArenaTrap::Disarm()          // 서버에서 호출된다
{
    if (!HasAuthority()) return;
    bArmed = false;
    UE_LOG(LogTemp, Log, TEXT("Disarm() on %s"), HasAuthority() ? TEXT("Server") : TEXT("Client"));
}
void AArenaTrap::OnRep_Armed()
{
    UE_LOG(LogTemp, Log, TEXT("OnRep_Armed on %s"), HasAuthority() ? TEXT("Server") : TEXT("Client"));
    SetSpikesVisible(bArmed);
}

(1) Listen Server(호스트 P1) + 클라이언트 P2 상황에서 서버가 Disarm()을 호출했다. P1·P2 각 머신에 찍히는 로그와 두 화면에서 가시가 사라지는지 예측하시오. 이 코드의 위험한 부분이 2곳 있다.
(2) 위험한 2곳을 각각 고치는 코드와 위치를 쓰시오. 이 변수를 블루프린트 RepNotify로 만들었다면 두 문제 중 어느 쪽이 생기지 않았을지 쓰시오.
(3) DOREPLIFETIME(AArenaTrap, bArmed)가 펼쳐진 코드가 하는 일을 설명하고, 변수 이름을 bArmd로 잘못 쓰면 언제(컴파일/실행) 어떤 이유로 알게 되는지 쓰시오.
(4) 엔진 소스 Actor.h에서 이 코드와 관련해 찾아볼 선언 4가지를 쓰고, 유니티 Netcode for GameObjects에서 이 변수에 대응하는 것을 쓰시오.

### P1-085 (0.39점)

[상황] Listen Server 2인 협동 게임의 네트워크 이벤트를 설계한다.

(1) 다음 4가지를 Server / Client / NetMulticast RPC 중 무엇으로 보낼지, Reliable과 Unreliable 중 무엇을 고를지 쓰고 이유를 한 줄씩 쓰시오.
(가) 클라이언트가 보물 상자를 열겠다는 요청
(나) 원거리 적이 쏠 때마다 나오는 총구 섬광(초당 여러 번)
(다) 한 플레이어에게만 '인벤토리가 가득 찼습니다' 메시지 띄우기
(라) 피격될 때마다 머리 위에 뜨는 데미지 숫자 연출
(2) 학생이 적 30마리의 피격 이펙트를 각각 0.05초 간격의 Reliable NetMulticast로 보냈다. 지연·손실 환경에서 무슨 일이 생길 수 있는지 쓰시오.
(3) 클라이언트 P2의 공격 판정 코드가 맞은 적 액터에 정의된 UFUNCTION(Server, Reliable) void ServerApplyHit(float Damage);를 Enemy->ServerApplyHit(20.f)로 호출했다. 서버에서 데미지가 들어가지 않는다. 이유를 오너십 규칙으로 설명하고 고치는 방법을 쓰시오.
(4) 유니티 Netcode의 ServerRpc/ClientRpc와 언리얼 RPC의 대응을 쓰시오.

### P1-086 (0.39점)

[상황] Dedicated Server 1대 + 클라이언트 C1, C2. 레벨에 보스 1마리(AIController가 조종)와 복제되는 보물 상자가 있다. 보스는 체력이 절반 아래로 떨어지면 '분노 상태'가 되어 눈이 빨갛게 빛나고, 그 순간 포효 사운드가 난다.

(1) 다음 객체가 서버, C1, C2 중 어디에 존재하는지 표로 쓰시오: GameMode, C1의 PlayerController, C1의 HUD, C1의 Pawn, C2의 PlayerState, GameState, 보스의 Pawn, 보스의 AIController.
(2) '분노 상태(빨간 눈)'와 '포효 사운드'를 각각 복제 프로퍼티와 Unreliable Multicast 중 무엇으로 보낼지 쓰고 이유를 쓰시오.
(3) 보스가 분노한 뒤 C3가 접속했다. 분노 상태를 Multicast로만 보냈다면 C3에게 보스가 어떻게 보이는지, 복제 프로퍼티로 보냈다면 어떻게 보이는지 쓰시오. 보물 상자 '열림'도 같은 기준으로 판단하시오.
(4) C1 클라이언트 코드에서 보스 Pawn의 GetController()로 블랙보드 값을 읽으려 했더니 null이다. 이유를 쓰고, C1이 보는 보스 Pawn은 어떤 역할(Role)의 액터인지 쓰시오.

### P1-087 (0.39점)

[상황] Listen Server: 호스트 P1 + 클라이언트 P2. NetLab에 복제되는 엘리베이터 버튼(bCalled, ReplicatedUsing=OnRep_Called)이 있고, 근접 전투를 2인용으로 바꾸는 중이다. 이번에는 호스트 P1이 직접 공격하는 경우도 함께 생각한다.

(1) P2가 엘리베이터 버튼을 눌러 엘리베이터가 내려오기까지의 과정을 'Server RPC → 서버에서 상태 변경 → 복제 → 클라이언트 OnRep' 순서로 시퀀스 다이어그램(Mermaid 문법 또는 '보내는 쪽 → 받는 쪽: 메시지' 형식의 줄 목록)으로 쓰시오. 참여자는 P2(클라), P1(서버)이다. HasAuthority 분기가 걸리는 곳과 OnRep이 불리는 곳(호스트 화면 포함)을 표시하시오.
(2) 근접 공격 흐름 '입력 → 몽타주 → 노티파이 판정 → ApplyDamage → 체력 UI'를 ① P2가 공격할 때 ② 호스트 P1이 공격할 때로 나눠, 각 단계가 어느 머신에서 실행되는지 표시하시오. ②에서 Server RPC가 실제로 네트워크를 타는지도 쓰시오.
(3) 엔진 노트 05-network-basics.md의 '어떤 클래스가 어디에 존재하나' 표를 4행만 쓰시오(GameMode, PlayerController, PlayerState, GameState).

### P1-088 (0.29점)

다음은 NetLab 실험 코드다(모두 학생이 만든 클래스). Listen Server: 호스트 P1 + 클라이언트 P2·P3, 나중에 P4가 접속한다. PIE + 지연 200ms 환경이다.

// ① NetLabCharacter.h
UFUNCTION(Server, Reliable) void ServerWave();
void ANetLabCharacter::ServerWave_Implementation() { UE_LOG(LogTemp, Log, TEXT("Wave from %s"), *GetName()); }
// P2의 PC에서 실행되는 코드
void ANetLabPlayerController::TestWave(ANetLabCharacter* Mine, ANetLabCharacter* P3Char)
{
    Mine->ServerWave();     // P2 자신의 캐릭터
    P3Char->ServerWave();   // P3의 캐릭터
}

// ② NetLabBossStatue: bReplicates = true
UPROPERTY(ReplicatedUsing = OnRep_Phase) int32 RepPhase = 1;
UFUNCTION(NetMulticast, Unreliable) void MulticastPhase(int32 NewPhase);
void ANetLabBossStatue::NextPhase()   // 서버에서 t=10초에 호출
{ RepPhase = 2; MulticastPhase(2); }
// 석상 왼쪽 표시판은 OnRep_Phase에서, 오른쪽 표시판은 MulticastPhase_Implementation에서 숫자를 바꾼다(서버에서는 NextPhase 안에서 둘 다 직접 갱신). 표시판 기본 숫자는 1.

// ③ NetLabCharacter.cpp
DOREPLIFETIME_CONDITION(ANetLabCharacter, Gold, COND_OwnerOnly);
// 서버가 P3의 캐릭터에 Gold = 150을 설정

(1) ①에서 두 호출 각각이 서버에서 실행되는지 쓰고 이유를 쓰시오. 실패한 쪽은 로그에서 무엇을 확인할 수 있는지, 'P3에게 손 흔들기'를 제대로 만들려면 어떻게 바꿔야 하는지 쓰시오.
(2) ②에서 P4가 t=30초에 접속했다. P2와 P4 화면에서 왼쪽·오른쪽 표시판 숫자를 각각 쓰시오.
(3) ③에서 P3의 캐릭터의 Gold 값은 P1(호스트), P2, P3, P4 머신에서 각각 얼마로 보이는지 쓰시오(기본값 0). 그리고 P2 화면에 '팀원 P3의 골드'를 보여 주는 기능을 새로 만든다면 이 조건이 왜 맞지 않는지 쓰시오.

### P1-089 (0.29점)

[상황] 보스 몬스터에 두 가지 연출이 있다.
- 'Slam': 땅을 한 번 내려찍는 2초짜리 몽타주
- 'Berserk': HP 30% 이하가 되면 죽을 때까지 몸이 붉게 빛나고 전용 대기 애니메이션 유지
2인 협동에서 클라이언트 B는 보스전 도중에 접속한다.
(1) Slam과 Berserk를 각각 NetMulticast와 복제 상태(복제 변수 + OnRep) 중 무엇으로 동기화할지 고르고, B가 접속했을 때 보이는 것을 근거로 설명하시오. Multicast라면 Reliable/Unreliable 중 무엇인가.
(2) 반대로 고르면(Slam을 상태로, Berserk를 Multicast로) 생기는 문제를 하나씩 쓰시오.
(3) 신입 동료가 "클라가 이동할 때마다 위치를 Server RPC로 보내고, 서버가 Multicast로 뿌리자"고 한다. 언리얼 캐릭터 이동이 이미 어떻게 처리되는지 들어 반박하시오.
(4) 그 처리를 엔진 소스에서 확인하려면 어느 헤더에서 무엇을 찾는가. 찾은 이름 2개의 역할을 한 줄씩 쓰시오.

### P1-090 (0.29점)

[상황] 다른 학생은 대시를 이렇게 만들었다. 클라이언트는 자기 CMC 값을 바꾸지 않고(클라 쪽 MaxWalkSpeed는 600 그대로) Server RPC `ServerDash()`만 보낸다. 서버는 RPC를 받으면 0.5초 동안 서버 쪽 MaxWalkSpeed를 2000으로 올렸다가 600으로 되돌린다. 지연 200ms 2인 테스트에서 클라이언트가 대시를 누르면 한참 뒤에야 반응이 오고, 대시 동안 캐릭터가 앞으로 순간이동하듯 뚝뚝 당겨진다.
(1) 이 문제를 관찰하고 기록하는 절차(환경 설정 → 관찰 → 기록)를 쓰시오.
(2) 왜 '앞으로 당겨지는' 보정이 생기는지 CMC의 클라 예측·서버 검증 흐름으로 설명하시오. 반대로 클라이언트가 먼저 자기 속도를 올리고 서버는 RPC가 도착한 뒤에 올리는 방식이었다면 보정 방향이 어떻게 되는지 비교하고, 두 경우의 공통 원인을 한 줄로 쓰시오.
(3) "서버 값만 바꾸면 서버 권위니까 안전한 것 아닌가?"라는 질문에 답하시오. 정석 해결 2가지도 쓰시오.
(4) 딥다이브 C의 'FSavedMove 압축 플래그' 방식이 이 문제를 어떻게 없애는지 개념으로 설명하시오. 이 방식이 W15 TS와 어떤 관계인지도 쓰시오.

### P1-091 (0.39점)

[상황] '독 장판' 기능을 GAS로 만든다. 장판에 들어가면 5초 동안 1초마다 체력이 4씩 줄고, 중독 중에는 회복 포션을 쓸 수 없다. 해독 스킬(쿨다운 8초, 마나 10 소모)을 쓰면 중독이 즉시 풀린다.
(1) 이 기능에 쓰이는 GAS 5요소를 그림 1장으로 그리시오. 각 요소가 무엇을 맡는지 표시하시오.
(2) 독 피해, 회복 금지, 해독 스킬, 해독 비용·쿨다운이 각각 어느 요소로 표현되는지 쓰시오.
(3) 동료가 "독 장판 액터가 캐릭터의 Health 변수를 직접 깎으면 되지 않나?"라고 한다. ASC가 GAS의 중심 컴포넌트로서 무엇을 맡는지 들어 답하시오.
(4) 유니티에서 이 기능을 직접 만들었다면 어떤 코드를 짰을지 예를 들고, GAS가 그 코드를 어떻게 대체하는지 비교하시오.

### P1-092 (0.39점)

아래는 보호막(Shield)이 있는 AttributeSet이다. 빈칸 ⓐ~ⓓ를 채우고 물음에 답하시오(UE 5.8).
```cpp
// .h — Health, MaxHealth, Stamina, MaxStamina, Shield, IncomingDamage 모두
//      FGameplayAttributeData + 아래 매크로로 선언됨
UPROPERTY(BlueprintReadOnly) FGameplayAttributeData Shield;
ATTRIBUTE_ACCESSORS(ⓐ________, Shield)

// .cpp
void UArenaAttributeSet::PreAttributeChange(const FGameplayAttribute& Attribute, float& NewValue)
{
  Super::PreAttributeChange(Attribute, NewValue);
  if (Attribute == ⓑ________)
    NewValue = FMath::Clamp(NewValue, 0.f, GetMaxStamina());
}
void UArenaAttributeSet::PostGameplayEffectExecute(const FGameplayEffectModCallbackData& Data)
{
  Super::PostGameplayEffectExecute(Data);
  if (Data.EvaluatedData.Attribute == ⓒ________)
  {
    float Damage = GetIncomingDamage();
    ⓓ________;                                   // 메타 속성 비우기
    const float Absorbed = FMath::Min(Damage, GetShield());
    SetShield(GetShield() - Absorbed);
    Damage -= Absorbed;
    SetHealth(FMath::Clamp(GetHealth() - Damage, 0.f, GetMaxHealth()));
  }
}
```
(1) ⓐ~ⓓ를 채우시오.
(2) ⓐ 줄의 매크로가 Shield에 대해 만들어 주는 함수 4개를 쓰시오. 이 코드에서 실제로 쓰인 것은 무엇인가. 이 매크로 정의는 원래 엔진의 어느 헤더 주석에 예시로 있는가.
(3) Health 60, MaxHealth 100, Shield 15일 때 IncomingDamage 40짜리 GE가 적용됐다. 처리 후 Shield와 Health는? 이어서 IncomingDamage 50이 오면?
(4) PreAttributeChange의 Clamp와 PostGameplayEffectExecute의 Clamp는 각각 어떤 상황을 막는가.
(5) 다른 팀원은 보호막 계산을 각 무기의 히트 코드 안에 넣자고 한다. 메타 속성 방식이 나은 이유 2가지를 쓰시오.

### P1-093 (0.39점)

[상황] 원거리 캐릭터용 GE와 어빌리티를 설계한다.
- GE_Poison: 6초 동안 2초마다 체력 -10 (적용 순간에는 실행하지 않도록 설정해, 2초·4초·6초에 한 번씩 총 3번 실행된다)
- GE_Arrow: 맞는 순간 체력 -25 (데미지 값은 코드에서 SetByCaller로 넣음)
- GE_Focus: 버프 아이콘이 꺼질 때(직접 제거)까지 크리티컬 확률 +15%
- GE_Slow: 4초 동안 이동속도 -150
(1) 각 GE의 EGameplayEffectDurationType 값과 Periodic 여부, Base/Current 중 무엇을 바꾸는지 쓰시오.
(2) 체력 100에서 GE_Poison이 끝까지 적용되면 체력은? 독이 끝나도 체력이 돌아오지 않는 이유는? 이동속도 600에서 GE_Slow가 끝나면?
(3) GE_Arrow의 Modifier를 설정할 때 무엇을 어떻게 정하는가(3요소).
(4) GA_ChargeShot의 흐름을 ActivateAbility·CommitAbility·EndAbility를 써서 설명하시오. 이 함수들을 GameplayAbility.h에서 확인하는 이유도 한 줄 쓰시오.
(5) 동료가 "CommitAbility는 그냥 로그용 체크 함수 아니야?"라고 한다. 바로잡으시오. 마나가 부족할 때의 동작도 쓰시오.

### P1-094 (0.39점)

[상황] 버그 리포트: "Listen Server 2인 PIE에서 호스트는 정상인데, 클라이언트 플레이어만 대시가 발동하지 않고 체력 UI가 0으로 보인다." 학생의 코드에서는 플레이어 ASC를 PlayerState에 두고, 초기화는 Character의 PossessedBy 안에서만 한다. 적 보스 1마리와 잡몹 40마리의 ASC는 각 Character에 있다. Replication Mode는 모두 Full이다.
(1) 클라이언트만 고장 나는 원인과 수정 방법을 쓰시오.
(2) Replication Mode 3종을 설명하시오. 이 설정에서 모두 Full을 쓰면 생기는 문제와, 플레이어·적에 맞는 모드를 쓰시오.
(3) 기획자가 "잡몹도 죽어도 버프가 남게 PlayerState에 ASC를 두자"고 한다. 적에게 Character가 맞는 이유를 쓰시오. 반대로 플레이어 ASC를 PlayerState에 둔 이점과 주의점을 한 줄씩 쓰시오.

### P1-095 (0.29점)

아래는 원거리 적(마법사)의 공격 BTTask와 어빌리티 코드다(UE 5.8).
```cpp
// BTTask_CastBolt.cpp
EBTNodeResult::Type UBTTask_CastBolt::ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
{
  APawn* Pawn = OwnerComp.GetAIOwner()->GetPawn();
  IAbilitySystemInterface* ASI = Cast<IAbilitySystemInterface>(Pawn);
  if (!ASI) return EBTNodeResult::Failed;
  UAbilitySystemComponent* ASC = ASI->GetAbilitySystemComponent();

  FGameplayAbilitySpecHandle H =
      ASC->GiveAbility(FGameplayAbilitySpec(BoltAbilityClass, 1));   // (A)
  ASC->TryActivateAbility(H);                                       // (B)
  return EBTNodeResult::Succeeded;                                  // (C)
}
// GA_CastBolt.cpp
UGA_CastBolt::UGA_CastBolt()
{
  InstancingPolicy   = EGameplayAbilityInstancingPolicy::InstancedPerExecution; // (D)
  NetExecutionPolicy = EGameplayAbilityNetExecutionPolicy::LocalPredicted;      // (E)
}
// ArenaEnemy.cpp — 체력 30% 이하가 되면 서버에서 호출
void AArenaEnemy::EnterEnrage()
{
  FGameplayEffectSpecHandle Spec = AbilitySystemComponent->MakeOutgoingSpec(
      EnrageEffect, 1.f, AbilitySystemComponent->MakeEffectContext());
  AbilitySystemComponent->ApplyGameplayEffectSpecToSelf(*Spec.Data.Get());   // (F)
}
```
(1) (A)(B)(F)의 ASC 함수가 각각 무엇을 하는지 쓰시오. 이 함수들이 선언된 엔진 헤더 이름도 쓰시오.
(2) (A)가 ExecuteTask 안에 있으면 적이 공격할 때마다 무슨 일이 생기는가. 어디로 옮겨야 하는지와 그 위치에서 지킬 조건도 쓰시오.
(3) (B)의 반환값을 무시하고 (C)에서 항상 Succeeded를 반환할 때의 문제 2가지와 고치는 방법을 쓰시오.
(4) (D)(E)는 각각 어떤 정책이고, 그 정의를 확인할 헤더는 어디인가. 플레이어가 조종하지 않는 적 어빌리티에는 어떤 네트워크 실행 정책이 더 의도에 맞는지 이유와 함께 쓰시오.
(5) 이 구조를 처음 설계할 때 tranek/GASDocumentation이나 Lyra 샘플을 어떤 식으로 참고하는 게 커리큘럼이 권한 방식인가.

### P1-096 (0.39점)

아래는 원거리 GA_ChargeShot 코드다(InstancedPerActor). 차지 몽타주는 1.2초이고, 0.8초에 `SendGameplayEventToActor(Owner, Event.Montage.Release 태그, Payload)`를 부르는 노티파이가 있다. C#의 동기식 함수 흐름에 익숙한 학생이 마지막 줄에 EndAbility를 넣었다.
```cpp
void UGA_ChargeShot::ActivateAbility(const FGameplayAbilitySpecHandle Handle,
  const FGameplayAbilityActorInfo* ActorInfo, const FGameplayAbilityActivationInfo ActivationInfo,
  const FGameplayEventData* TriggerEventData)
{
  if (!CommitAbility(Handle, ActorInfo, ActivationInfo))
  { EndAbility(Handle, ActorInfo, ActivationInfo, true, true); return; }
  UE_LOG(LogTemp, Log, TEXT("A start"));

  UAbilityTask_PlayMontageAndWait* T1 =
    UAbilityTask_PlayMontageAndWait::CreatePlayMontageAndWaitProxy(this, NAME_None, ChargeMontage);
  T1->OnCompleted.AddDynamic(this, &UGA_ChargeShot::OnMontageEnd);
  T1->OnBlendOut.AddDynamic(this, &UGA_ChargeShot::OnMontageEnd);
  T1->OnInterrupted.AddDynamic(this, &UGA_ChargeShot::OnMontageEnd);
  T1->OnCancelled.AddDynamic(this, &UGA_ChargeShot::OnMontageEnd);
  T1->ReadyForActivation();

  UAbilityTask_WaitGameplayEvent* T2 = UAbilityTask_WaitGameplayEvent::WaitGameplayEvent(
    this, FGameplayTag::RequestGameplayTag(TEXT("Event.Montage.Release")), nullptr, true);
  T2->EventReceived.AddDynamic(this, &UGA_ChargeShot::OnRelease);
  T2->ReadyForActivation();

  UE_LOG(LogTemp, Log, TEXT("B tasks ready"));
  EndAbility(Handle, ActorInfo, ActivationInfo, true, false);          // (X)
}
void UGA_ChargeShot::OnRelease(FGameplayEventData Payload)
{ UE_LOG(LogTemp, Log, TEXT("C fire")); /* 투사체 발사 */ }
void UGA_ChargeShot::OnMontageEnd()
{ UE_LOG(LogTemp, Log, TEXT("D end")); EndAbility(CurrentSpecHandle, CurrentActorInfo, CurrentActivationInfo, true, false); }
```
(1) AbilityTask가 어떤 단위인지(어빌리티 안에서 무엇을 맡고, 작업이 끝나거나 중단되면 어떻게 다음 로직으로 이어지는지) 2줄로 정의하시오. 그 정의를 근거로, 이 코드에서 찍히는 로그를 순서대로 예측하고 투사체가 나가지 않는 이유를 어빌리티 수명과 연결해 설명하시오.
(2) (X) 줄을 지우면 정상 재생 시 로그 순서는 어떻게 되는가. EndAbility는 어디에서 불리게 되는가.
(3) T1에 델리게이트를 4개 연결한 이유를 쓰시오. T2의 네 번째 인자 true는 어떤 의미로 읽히는가.
(4) 몽타주 델리게이트 종류, 이벤트 대기 방식, 노티파이에서 부르는 함수를 확인할 엔진 헤더 3개를 각각 쓰시오.

### P1-097 (0.29점)

[상황] 모의 면접에서 받은 질문 3개에 답하시오.
Q1. "데디케이티드 서버로 테스트했더니 서버 로그에 사망 사운드·이펙트 처리가 안 보이는데, 버그 아닌가요? 왜 사망 연출을 GameplayCue로 만들었죠?"
Q2. "지연 200ms에서 대시가 바로 나가던데, 서버 승인을 안 기다리고 어떻게 그렇게 되죠? 스태미나가 부족한 상태에서 서버가 거부하면 화면에서는 어떻게 되나요?"
Q3. "2인 협동 소규모 게임에 GAS는 과하지 않나요? 클라 예측을 직접 짜면 되잖아요."
(1) Q1: 정상인 이유와 GameplayCue를 쓴 이유를 함께 답하시오.
(2) Q2: 로컬 예측 원리로 답하시오. 예측 키, 승인, 거부를 모두 쓰시오.
(3) Q3: GAS 도입 비용을 인정하고(3가지), ADR-0004에서 비교한 선택지와 결정 근거로 답하시오. 비교 영상 같은 결과 증거도 언급하시오.
(4) GAS를 쓰다가 '태그가 안 붙는 것 같다'는 버그가 나면 어떤 명령으로 무엇을 확인하는가. 도입 근거를 ADR로 남겨 둔 것이 이 면접 질문에 어떻게 도움이 되는가.

### P1-098 (0.29점)

[상황] 동료 D가 금요일 밤에 이렇게 말한다. "주말에 HealthComponent를 통째로 지우고 AttributeSet으로 한 번에 바꿔서 PR 하나로 올릴게. 어차피 GAS로 갈 거잖아." 현재 HealthComponent에는 복제(OnRep), 사망 델리게이트(OnDeath → 리스폰), 체력바 갱신, 적 AI의 '체력 30% 이하면 도망' 판단이 연결돼 있다.
(1) D의 계획에서 생길 수 있는 위험 2가지를 구체적으로 쓰시오(위 연결 중 무엇이 깨질 수 있는지 포함).
(2) 같은 목표를 이루는 단계적 마이그레이션 계획을 순서대로 쓰시오. 각 단계의 '완료 확인 방법'을 포함하시오.
(3) 교체가 끝난 뒤 '안 깨졌다'를 증명하는 테스트 조건 3가지를 쓰시오(싱글/멀티/지연 등).
(4) 교체가 끝나면 README에 '같은 기능의 진화' 표의 체력 행을 쓴다. 칸(단계·주차·바꾼 이유·근거 링크 종류)을 채워 쓰시오.

### P1-099 (0.29점)

[상황] 보스전 맵에서 프레임이 떨어진다. `stat unit` 결과는 다음과 같다.
Frame 25.0ms · Game 11.2ms · Draw 12.0ms · GPU 24.6ms
친구는 "AI가 많으니까 BTService 주기를 0.1초에서 0.5초로 늘리고 Tick도 끄자"고 한다. 친구는 배터리로 노트북을 쓰며 한 번만 측정했다.
(1) 병목은 어디인가. 판단 근거와, 그 영역을 더 자세히 보려면 무엇을 하는지 쓰시오.
(2) 친구 제안의 효과를 예측하고, 왜 '측정 먼저'가 필요한지 설명하시오.
(3) 친구의 측정 방식에서 고칠 점 2가지를 쓰시오. 개선 후 5회 측정값 18.4 / 24.9 / 25.3 / 24.6 / 26.0ms에서 보고할 대표값과 이유를 쓰시오.
(4) 유니티 Profiler에 익숙한 친구에게, 언리얼에서 내 함수 구간 시간을 보는 방법을 대응 관계로 설명하시오.

### P1-100 (0.19점)

[상황] 동료가 "성능 조사는 전부 `stat unit` 하나로 하면 된다"고 한다. 다음 경우에 각각 무엇이 부족하고, 어떤 Insights 도구를 언제 써야 하는지 설명하시오.
① 30분 연속 플레이 테스트에서 점점 메모리가 차다가 Shipping 빌드가 꺼졌다.
② 투사체 200발이 날아다니는 장면에서 클라이언트만 끊긴다. 서버 프레임은 정상이다.
(3) 아래 코드의 빈칸 ⓐ~ⓒ를 채우시오. 각 매크로가 정의된 엔진 헤더 파일을 쓰고, 두 방식의 결과를 어디에서 보는지 쓰시오.
```cpp
ⓐ________(TEXT("Perception Update"), STAT_PerceptionUpdate, STATGROUP_Game);

void UArenaPerceptionService::TickNode(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
{
  ⓑ________(UArenaPerceptionService_TickNode);   // Insights 트레이스에 표시
  ⓒ________(STAT_PerceptionUpdate);               // stat 그룹으로 확인
  Super::TickNode(OwnerComp, NodeMemory, DeltaSeconds);
  // ... 감지 처리 ...
}
```

### P1-101 (0.29점)

[상황] Networking Insights로 본 복제 트래픽 상위 3개는 다음과 같다.
① 화살 투사체(한 번에 150개): 날아가는 1~2초 동안 위치가 계속 바뀜
② 레버·문 40개: 게임 중 거의 안 바뀌지만 계속 복제 검사됨
③ 플레이어 A만 있는 북쪽 구역의 적 스포너·적들: 남쪽 끝의 플레이어 B에게도 모두 복제됨
(1) ①②③ 각각에 NetUpdateFrequency·Dormancy·Relevancy 중 무엇이 가장 잘 맞는지 고르고 원리를 설명하시오.
(2) 동료가 "전부 NetUpdateFrequency를 1로 내리면 끝"이라고 한다. 생길 문제를 쓰시오.
(3) ②에 Dormancy를 적용한 뒤 "클라이언트에서 레버를 당겨도 문이 안 열린다"는 버그가 났다. 가능한 원인을 쓰시오.
(4) ③에서 B가 북쪽으로 이동하면 어떻게 되는가.

### P1-102 (0.19점)

[상황] 최적화 PR이 머지된 뒤 버그가 올라왔다(싱글 플레이 테스트 기준). "플레이어가 적을 등지고 있으면 적이 칼을 휘두르는데 데미지가 안 들어간다. 정면을 보면 정상이다." 이번 PR에서는 적 애니메이션 비용을 줄이려고 업데이트 비율 조정과 화면 밖 애니메이션 틱 옵션을 켰다. 적 공격 판정은 몽타주의 AnimNotifyState 구간에서 소켓 Sweep으로 한다.
(1) 이 버그의 원인을 추론하시오. 정면에서는 정상인 이유도 쓰시오.
(2) 원인을 확인할 방법과, 성능 이득을 최대한 유지하면서 고치는 방향 2가지를 쓰시오.
(3) 적이 많을 때 애니메이션 비용을 줄이는 방법 3가지를 쓰시오. 각 방법이 무엇을 줄이는지도 쓰시오.

### P1-103 (0.29점)

아래 코드는 웨이브 시작 함수 일부다. SpawnEnemy는 적을 실제로 스폰하고 성공 여부(bool)를 반환한다. 이 함수는 게임 중 10번 불리고, 그중 4번은 Row.Interval이 음수인 잘못된 데이터다.
```cpp
void AArenaGameMode::StartWave(const FWaveRow& Row)
{
  check(WaveTable != nullptr);                         // (1)
  if (!ensure(Row.Interval >= 0.f)) { Interval = 1.f; } // (2)
  check(SpawnEnemy(Row));                              // (3)
  verify(SpawnEnemy(Row));                             // (4)
}
```
(1) Development 빌드에서 WaveTable이 nullptr이면 (1)에서 무슨 일이 생기는가. Shipping 빌드에서는 (1)이 어떻게 처리되는가.
(2) Development 빌드에서 10번 중 잘못된 데이터 4번 동안 (2)는 콜스택을 몇 번 보고하는가. 게임은 계속되는가.
(3) 정상 데이터에서 Development 빌드와 Shipping 빌드에서 각각 적이 몇 마리 스폰되는가((3)(4) 기준, 한 번 호출에 SpawnEnemy 1회당 1마리). 이 차이가 왜 위험한지 쓰시오.
(4) (3)(4)를 의도대로(1마리 스폰 + 결과 검사) 고치시오.
(5) 이 동작들을 확인할 엔진 헤더는 무엇인가. 같은 W19에 '테스트 정의 매크로와 플래그'를 찾아본 헤더, 'Exec 치트 함수 예시'를 찾아본 헤더는 각각 무엇인가.

### P1-104 (0.19점)

[상황] 실제로 났던 버그 두 개를 다시 나지 않게 하려 한다.
- 버그 1: 풀에서 다시 꺼낸 화살이 이전에 박혔던 적을 계속 따라다니고, 첫 프레임에 충돌이 꺼져 있었다.
- 버그 2: 기절(State.Stunned)이 풀린 뒤에도 이동 입력이 막혀 있었다(태그 제거가 누락됨).
(1) 버그 1을 잡는 회귀 테스트를 설계하시오. 무엇을 하고 무엇을 검증하는지 3가지 이상 쓰시오.
(2) 버그 2를 잡는 태그 상태 전이 테스트를 설계하시오. 전이 순서와 검증 시점을 쓰시오.
(3) 버그 2처럼 '기절 → 해제', '기절 중 피격', '기절 중 사망' 같은 테스트 케이스를 여러 개 만들려 한다. 커리큘럼이 소개한 자동화 테스트 작성 방식 두 가지의 이름을 쓰고, Simple 방식은 어떤 매크로로 테스트를 정의하는지, 만든 테스트를 어디에서 실행하는지 쓰시오.
(4) 유니티에서 PlayMode 테스트로 '씬을 띄워 적 스폰 → 처치 → 웨이브 종료'를 확인했다. 언리얼에서는 무엇이 대응하는가. EditMode 테스트는 무엇에 대응하는가.
(5) 이 테스트들을 README·면접에서 어떻게 설명해야 가치가 있는지 쓰시오.

### P1-105 (0.19점)

[상황] 동료가 타격감을 넣으면서 피격 시 '게임 전체 시간 배율(Global Time Dilation)을 0.1로 0.15초 낮추는' 코드를 넣었다. 2인 테스트에서 이런 리포트가 왔다.
- "내가 안 때렸는데 내 캐릭터도 자꾸 멈칫해요."
- "웨이브 타이머와 적 이동이 가끔 이상하게 느려져요."
(1) 두 리포트의 원인을 설명하시오.
(2) 대안 설계를 쓰시오. 어떤 기능을, 어떤 액터에, 얼마 동안 적용하는가.
(3) 동료는 "히트스톱 중에는 데미지 판정도 멈춰야 진짜 같다"고 한다. 커리큘럼의 설계 원칙에 따라 답하시오.
(4) 유니티 경험이 있는 동료에게 Time.timeScale과 Cinemachine Impulse가 언리얼에서 무엇에 대응하는지 설명하시오.

### P1-106 (0.10점)

[상황] 스터디 후배가 AI를 이렇게 쓰고 있다. 각 경우 무엇이 문제인지 한 줄로 쓰고, 커리큘럼 프롬프트 라이브러리 방식으로 고친 프롬프트를 2~4줄로 쓰시오.
① "`void OnHit(const FHitResult& Hit)`랑 `GetOwner()->FindComponentByClass<UCombatComponent>()` 고쳐서 돌아가게 해줘." (사실은 코드 뜻을 모른다)
② "'Instant GE와 Duration GE의 차이' 면접 모범 답안 줘. 외울게."
③ "오브젝트 풀 Subsystem 전체 코드 짜줘." (지금은 W12, AI 레벨 L2)
④ "백준 12865 평범한 배낭 정답 코드 줘." (자기 코드는 시간 초과)

### P1-107 (0.19점)

[상황] 다음 다섯 상황에서 무엇을 하는지(또는 AI에게 보낼 프롬프트를) 쓰시오.
① AI가 점프 입력을 `PlayerInputComponent->BindAction("Jump", IE_Pressed, this, &ACharacter::Jump);`로 연결하라고 알려 줬다. 커리큘럼에서 배운 입력 방식과 다르다. 이 코드를 그대로 쓰기 전에 하는 확인 절차와, 그 결과를 어디에 남기는지 쓰시오.
② W0 환경 세팅 중 Visual Studio 설치 후 C++ 프로젝트 생성 단계에서 에러 창이 떴다. AI에게 보낼 '설치·설정 막힘' 프롬프트에 꼭 넣을 것 4가지를 쓰시오.
③ 적이 가끔 두 번 사망 처리된다(점수가 2배로 오름). 로그로 Die()가 같은 프레임에 두 번 불리는 것까지 확인했다. 디버깅 프롬프트를 쓰시오. 이 프롬프트를 보내기 전에 지켜야 하는 규칙도 쓰시오.
④ AI 코드 리뷰 결과 'Tick에서 매 프레임 FindComponentByClass 호출', 'TObjectPtr 멤버에 UPROPERTY 없음', '변수 이름이 a1'이 나왔다. 리뷰를 요청할 때 정렬 기준과 검사 항목은 무엇이었어야 하는가. 이 세 지적을 심각도 순으로 정렬하시오.
⑤ ACharacter의 PossessedBy가 언제 누구에게 불리는지 엔진 소스로 확인하고 싶다. 길잡이 프롬프트를 쓰시오. 이 프롬프트에서 '정답 설명' 대신 '파일명·함수명 순서'를 받는 이유도 쓰시오.

### P1-108 (0.10점)

[설명형] 학생이 쓴 프롬프트 3개다. 각각 무엇이 문제인지 쓰고, 조건을 다 갖춘 프롬프트로 고쳐 쓰라.
가. (W3 과제) "너는 면접관이야. 액터 생명주기에 대해 아무거나 물어봐."
나. "상호작용 감지를 Tick으로 할지 타이머로 할지 Overlap으로 할지 뭐가 제일 좋아? 예제 코드도 같이."
다. "메모 정리하면서 내가 빠뜨린 내용은 네가 알아서 채워 넣어 줘."
그리고 가를 고친 뒤 W3 과제를 끝냈다고 하려면 학습 기록에 무엇이 남아 있어야 하는지 쓰라.

### P1-109 (0.10점)

[설명형] (1) W2에 AI가 AGCLabActor 초안을 써 줬다. 그런데 TWeakObjectPtr<UGCLabItem> WatchLoose; 줄을 설명할 수 없다. L1 방식으로 이 상황을 처리하고 학습 로그 저장소에 올리기까지의 순서를 쓰라.
(2) 다음 세 줄에 L1 방식의 해설 주석을 한 줄씩 달라.
UPROPERTY() TObjectPtr<UGCLabItem> Kept;
Kept = NewObject<UGCLabItem>(this);
UE_LOG(LogArena, Warning, TEXT("Kept=%d"), WatchKept.IsValid());
(3) W22에 체력 회복 아이템을 L3 방식으로 만든다. L3 순서를 쓰고, AI에게 '전체 코드를 짜 줘'라고 하면 안 되는 이유와 대신 물을 질문 2개를 쓰라.

### P1-110 (0.19점)

L2 방식으로 내가 직접 쓴 AArenaRangedAIController 코드를 AI에게 'Epic C++ 코딩 표준 기준으로 리뷰해줘, 수정 코드는 내가 요청할 때만'이라고 요청해 다음 의견 6개를 받았다.
① Tick마다 GetPawn()->FindComponentByClass<UArenaCombatComponent>()를 부른다. BeginPlay/OnPossess에서 한 번 찾아 UPROPERTY 멤버에 저장해라.
② Target 포인터를 쓰기 전에 유효성 검사가 없다. 검사를 추가해라.
③ 함수 이름 DoIt()은 의미가 없다. TryFireAtTarget()처럼 바꿔라.
④ AI Perception 대신 Tick에서 직접 LineTrace를 쏴서 시야를 판정하는 게 더 확실하다.
⑤ 시야 반경은 AAIController::SetSightRadius(1500.f)로 바꿔라. (Visual Studio에서 F12·검색으로 찾아봤지만 AIController.h에 이런 선언이 없었다)
⑥ 코드에 있는 600.f(유지 거리)를 원거리 적 스탯 DataTable 행으로 옮겨라.

(1) 6개 각각을 채택/거절하고 이유를 한 줄씩 쓰시오.
(2) PR에 이 판단을 어떤 형식으로 남기는지 한 항목을 예로 쓰시오.
(3) ②를 반영하면서 AI가 예시로 보여 준 TWeakObjectPtr 줄을 그대로 붙여 넣었는데 왜 이 타입인지 설명할 수 없다. 커밋 전에 무엇을 해야 하는지 커리큘럼의 원칙과 함께 순서대로 쓰시오.

### P1-111 (0.10점)

M3(AI 레벨 L2) 기간에 '웨이브 구성 DataTable을 읽어 적을 스폰하는 스포너'를 만들려고 AI에게 '스포너 만들어줘'라고만 보냈더니 AI가 완성 코드 120줄을 먼저 보내 왔다.
(1) 이 요청이 어느 원칙을 어겼는지 쓰고, L2에 맞게 다시 보낼 프롬프트를 2~3문장으로 쓰시오(받은 코드를 어떻게 다룰지도 한 줄).
(2) 기능을 다 만든 뒤 PR의 'AI 활용 내역'을 세 칸(사용 범위 / 내가 검증·수정한 것 / AI가 틀렸던 것)으로 채워 예시를 쓰시오.

### P1-112 (0.10점)

[상황] 학생 F의 W12 결과물이다. 루브릭 '기능 완성도'·'코드 품질'·'엔진 이해'를 각각 1~4점으로 채점하고, 근거와 가장 먼저 보강할 행동 1가지를 각각 쓰시오.
- 기능: 메뉴 → 웨이브 → 게임오버가 돈다. 단, DataTable에 적 수가 0인 웨이브가 있으면 게임이 멈춘다. 데모 중 오류는 없었다.
- 코드: 웨이브·스폰·UI 갱신·세이브가 모두 AArenaGameMode 하나(2,000줄)에 있다. 적 체력 100, 스폰 간격 2.0이 코드에 숫자로 박혀 있다. 클래스 이름은 Epic 규칙(A/U 접두어)을 따랐다.
- 엔진 이해: "재사용 시 BeginPlay가 다시 안 불려서 Reset 함수를 만들었다"고 Devlog에 말로 설명했다. 소스나 콜스택 근거는 없다.
추가: 세 점수 중 1점이 있다면, 다음 단계로 넘어가기 전 어떻게 해야 하는지도 쓰시오.

### P1-113 (0.10점)

M3가 끝난 학생 B의 기록이다.
- 문제 해결: TS 문서는 없고, 버그를 만났던 날의 TIL에 '○○ 버그 고침' 메모가 3건 있다.
- Git: 기능 단위로 커밋했다. PR은 있지만 이슈와 연결되지 않았고 셀프 리뷰 체크도 비어 있다.
- AI 활용: 직접 작성 후 AI 리뷰를 받고 채택 근거를 PR에 남겼다. AI-Off 챌린지 ②를 시간 안에 성공했고, AI가 제안한 존재하지 않는 함수를 엔진 소스에서 확인해 거절한 사례를 TIL에 기록했다.

(1) 루브릭의 '문제 해결 기록', '협업 습관(Git)', 'AI 활용'을 각각 1~4점으로 채점하고 근거를 한 줄씩 쓰시오.
(2) docs/retro/M3.md에 쓸 Keep·Problem·Try를 한 줄씩 쓰시오. 그리고 월간 자가 평가에 쓰는 루브릭 6항목의 이름을 모두 쓰시오.

### P1-114 (0.10점)

(1) 이 커리큘럼의 '관문' 운영 방식을 한두 문장으로 설명하시오.
(2) 학생 D의 저장소를 단계별로 점검했다. 각 관문의 통과 여부와, 통과하지 못했다면 빠진 조건을 쓰시오.
- M2 시점: v0.2.0 릴리즈와 45초 영상 있음, '무기 추가' PR의 diff에 WeaponData.h 1줄 수정이 포함됨, TS 2건, ADR 2건, AI-Off ② 기록 있음, 코테 누적 42문제.
- M3 시점: 메뉴~게임오버 루프 동작, 적 AI 2종, 성능 수치 2건(Size Map, 풀링), TS 누적 3건, ADR 2건, 코테 누적 60문제.
- M4 시점(docs/retro/M4.md 작성 중): v0.3.0 패키징·릴리즈, README 1차, AI-Off ③은 하지 않음, NetLab 노트 + TS 누적 6건, GA_Dash 동작, 코테 누적 80문제.

### P1-115 (0.10점)

[상황] W24 말 학생 H의 상태다.
- 루브릭 자가 평가: 기능 3 · 코드 3 · 엔진 4 · 문제 해결 기록 3 · Git 3 · AI 활용 2
- 딥다이브 리포트 완료, 시연 영상·README 완성, 포트폴리오 PDF는 9쪽까지 작성
- 질문 은행 답변 85%, 지원 10곳 리스트와 매핑표 완료
- v1.0.0 릴리즈 완료, 6개월 회고는 숫자 없이 소감만 3줄
(1) 루브릭 평균을 구하고 M5~M6 목표 평균과 비교하시오. 보강해야 할 1점 항목이 있는지 판정하시오.
(2) M6 관문 조건 5가지를 쓰고, H의 통과 여부와 못 채운 조건을 쓰시오.
(3) H의 6개월 회고를 '숫자로' 다시 쓰려면 어떤 항목을 집계해야 하는가. 각 항목의 출처를 쓰시오.
(4) 같은 H가 W20 말에 M5 관문을 판정할 때 봤어야 할 조건 6가지를 쓰시오.

### P1-116 (0.19점)

[상황] 스터디원 세 명이 고른 딥다이브와 지원 계획이다.
- 정: D를 골랐다. 지원 회사는 MMO 서버 동기화를 강조하는 온라인 액션 게임사다.
- 무: B를 골랐다. "StateTree로 다시 만들면 끝"이라고 생각한다.
- 기: E를 골랐다. "강의 영상 3개를 요약해 블로그 3편"을 쓸 계획이다.
(1) 정에게 회사 성격에 맞는 주제를 추천하시오. 커리큘럼의 '회사 성격 → 주제' 추천 기준 3가지를 모두 쓰시오.
(2) 정이 이미 D를 상당히 진행했다면, D가 무엇을 만드는 주제인지 쓰고 면접에서 어떻게 연결해 말할지 한 줄 쓰시오.
(3) 무의 계획에 빠진 것을 B의 정의에 비추어 지적하시오. 비교 관점 3가지를 쓰시오.
(4) 기의 계획을 E의 정의에 비추어 고치시오. E의 분석 대상 2가지 중 하나를 고르고 근거를 무엇으로 삼는지 쓰시오.

### P1-117 (0.10점)

[상황] 친구가 딥다이브 B(적 AI를 StateTree로 재구현)를 하고 리포트 초안을 보여 줬다.
"StateTree로 근접 적을 만들었다. Idle, Chase, Attack 상태를 만들었고 잘 동작한다. 재미있었고 많이 배웠다. 다음엔 원거리 적도 해 보고 싶다."
(1) 친구가 작업을 시작하기 전에 했어야 할 이슈 분해를 5개 이내로 쓰시오(각 완료 조건 포함).
(2) 위 초안을 커리큘럼의 리포트 구조 4단계로 다시 구성하시오. 각 단계에 빠진 내용을 채우시오(가상의 수치 사용 가능, 수치라는 것만 표시).
(3) 리포트를 기술 블로그 1편으로 재가공할 때의 제목 예시와, 리포트에서 덜어 내거나 더해야 할 것을 쓰시오.

### P1-118 (0.19점)

[상황] 친구의 포트폴리오 초안이다.
- 영상: 5분 30초. 처음 40초가 메인 메뉴와 옵션 화면이고, 자막이 없으며, 전투 장면은 디버그 표시 없이 나온다. 전체 공개로 올렸다.
- PDF: 32쪽. 대부분 소스 코드 전체를 붙여 넣었고, 트러블슈팅·성능 수치는 없다.
- 1분 소개: "6개월 동안 정말 열심히 했고 다양한 기능을 만들었습니다. 열정이 있습니다."
(1) 영상의 문제 3가지를 지적하고, 커리큘럼 구성안으로 고친 구간 순서를 쓰시오.
(2) PDF를 15~20쪽 구성안으로 다시 짜시오(목차 10개 이상). 코드는 어떻게 넣어야 하는지 쓰시오. PDF를 따로 준비하는 이유도 쓰시오.
(3) 1분 소개를 커리큘럼 순서로 다시 쓰시오(가상 수치 가능).
(4) 3분 버전과 1분 버전은 무엇이 다른가. 두 버전을 스크립트로 써 두는 이유와 함께 쓰시오.

### P1-119 (0.10점)

[상황] 친구의 자기소개서와 지원 준비 상태다.
- 문장 1: "멀티플레이 구현에 자신 있습니다."
- 문장 2: "GAS를 능숙하게 다룹니다."
- 문장 3: "유니티에서 언리얼로 빠르게 적응했습니다."
- 지원 회사는 3곳이고 매핑표는 없다. 지난주 면접에서 'Dormancy가 뭔가요?'에 답하지 못했지만 기록은 없다. 현직자에게 "README가 너무 길다"는 피드백을 받았지만 아직 반영하지 않았다.
(1) 문장 1~3을 각각 근거 링크가 붙은 문장으로 고치시오(링크 종류를 명시, 가상 가능).
(2) 커리큘럼 기준으로 친구의 지원 준비에서 빠진 것을 쓰시오(회사 수·매핑표).
(3) Dormancy 질문 경험을 복기 문서로 남기는 형식을 쓰시오.
(4) README 피드백을 반영하는 방법과 그 과정을 남기는 방법을 쓰시오.

### P1-120 (0.10점)

[상황] 학생 J의 준비 방식이다.
- TS-006(스프린트 러버밴딩)을 면접에서 3분 동안 설명했는데 면접관이 중간에 끊었다.
- 질문 은행 답은 AI가 써 준 모범 답안을 눈으로 읽으며 외웠다.
- AI 면접관 모드에서 꼬리 질문을 받으면 막힐 때마다 AI에게 "모범 답 알려줘"라고 했다.
(1) TS-006을 30초 버전으로 쓰시오(원인: 클라 예측 속도와 서버 속도가 시점상 다름 → 서버 보정. 해결은 W15 시점 TS 기준으로 '정석 해결 방향 기록 + 이후 딥다이브 C로 구현'). TS 템플릿의 문장 틀을 따르시오.
(2) J의 질문 은행 준비 방식의 문제를 쓰시오. 커리큘럼의 AI-Off 방식으로 고치시오(녹음 포함).
(3) J의 AI 면접관 리허설 방식의 문제를 쓰시오. 올바른 진행 규칙과 횟수를 쓰시오.

### P1-121 (0.19점)

질문 은행(주차별 자가 점검 + 일반 질문)에서 뽑은 10문항이다. AI·자료 없이 각 문항에 1~3줄로 내 말로 답하시오. 채점 후 0점·부분 점수 문항은 오답 노트 대상으로 표시되어 돌려받는다.
1. Mesh->SetRelativeLocation()에서 ->와 .의 차이는?
2. 스택과 힙의 차이는?
3. C++ 추상 클래스와 C# 인터페이스의 차이는?
4. const 멤버 함수의 의미는?
5. 큰 구조체를 값으로 넘기면 무엇이 문제인가?
6. TSharedPtr과 TObjectPtr은 각각 언제 쓰나?
7. shared_ptr 순환 참조란?
8. CDO란 무엇인가?
9. Super::BeginPlay()를 빼먹으면?
10. UHT와 UBT는 무엇인가?

### P1-950 (0.19점)

[상황] 면접관 질문: "딥다이브로 한 걸 2분 안에 말해 주세요. 그런데 그 결과가 진짜인지는 어떻게 믿죠? AI가 다 해 준 건 아닌가요?" 이 회사는 '실시간 온라인 액션 게임 회사'다.
자신이 실제로 한 딥다이브 주제로 2분 분량(약 10~14줄)의 답변 스크립트를 쓰시오. 면접관의 의심(결과의 신뢰성, AI 의존)에 먼저 답하는 흐름이어도 되지만, 다음 5가지가 모두 들어가야 한다.
① 이 주제를 고른 이유와 이 회사 유형과의 연결(추천 주제가 아니라면 인정하고 전이되는 역량으로 연결)
② 해결한 문제와 결과(이슈 분해 포함)
③ 결과를 믿을 수 있는 근거(같은 조건 반복 측정·전후 비교 영상·엔진 소스 위치 등, 링크로)
④ AI에 맡긴 것과 내가 직접 검증한 것, 검증 방법
⑤ 한계와 다음 단계(무엇이 아직 증명되지 않았는지)

## 2부 코딩테스트 (20점 · 330분)

2부-A 주제별 21문항 210분(백준형 단일 주제, 테스트케이스별 부분 점수) + 2부-B 실전 세트 3문항 120분(프로그래머스형, W21 모의시험 형식). C++17과 Visual Studio 콘솔 앱 사용, AI·검색 불가. 풀이는 제출 저장소에 '문제번호-제목.cpp'로 커밋

### P2-01 (0.36점)

[P2-01 B형] 레이스 기록
시간 제한 1초 · 메모리 256MB

레이싱 게임의 기록 화면을 만든다. 한 경기의 총 주행 시간 S초, 바퀴 수 L, 차량 번호 N(세 자리 정수)이 주어질 때 다음 네 가지를 띄운다.
1. 총 주행 시간을 '분'과 '남는 초'로 바꾼 값
2. 한 바퀴당 평균 시간(실수)
3. 차량 번호의 백의 자리, 십의 자리, 일의 자리 숫자
4. 차량 번호 세 숫자의 평균

입력
첫째 줄에 S와 L이 공백으로 구분되어 주어진다. 둘째 줄에 N이 주어진다.

출력
첫째 줄: 분과 남는 초를 공백으로 구분해 출력한다. (예: 125초 → 2 5)
둘째 줄: 바퀴당 평균 시간 S ÷ L을 소수점 아래 셋째 자리까지(반올림) 출력한다.
셋째 줄: N의 백의 자리, 십의 자리, 일의 자리 숫자를 이 순서대로 공백으로 구분해 출력한다.
넷째 줄: 세 숫자의 평균을 소수점 아래 셋째 자리까지(반올림) 출력한다.

제한
- 0 ≤ S ≤ 2,000,000,000
- 1 ≤ L ≤ 100
- 100 ≤ N ≤ 999
- 채점 데이터에는 반올림 자리 바로 뒤가 정확히 5로 끝나 올림·내림이 애매한 값이 없다.

예제 입력 1
125 2
507

예제 출력 1
2 5
62.500
5 0 7
4.000

예제 입력 2
59 7
990

예제 출력 2
0 59
8.429
9 9 0
6.000

제출
- Visual Studio 콘솔 앱에서 Ctrl+F5로 예제 2개를 실행해 출력이 글자 하나까지 같은지 확인한 뒤 C++17로 제출한다.
- 파일 맨 아래 주석에, 직접 넣어 본 경계 입력 2개(가장 작은 값 쪽 1개, 가장 큰 값 쪽 1개)와 그때 콘솔에 나온 출력을 적는다.
- 'P2-01-레이스-기록.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-02 (0.36점)

[P2-02 B형] 날씨 경보와 세이브 시각
시간 제한 1초 · 메모리 256MB

게임 상단 바에 다음 세 가지를 판정해 띄운다.
1. 기온 T의 경보 단계: 35도 이상 HEAT, 25~34도 WARM, 10~24도 MILD, 0~9도 COLD, 0도 미만 FREEZE
2. 연도 Y가 '축제 연도'인지: Y가 3의 배수이면서, 동시에 'Y가 10의 배수가 아니거나 Y가 8의 배수'이면 축제 연도다.
3. 지금은 H시 M분이고, 마지막 세이브는 a시간 b분 전에 했다. 마지막 세이브 시각(24시간제)을 구한다. 전날로 넘어가면 전날의 시각을 출력한다.

입력
첫째 줄에 T, 둘째 줄에 Y, 셋째 줄에 H M a b가 공백으로 구분되어 주어진다.

출력
첫째 줄에 경보 단계 이름, 둘째 줄에 축제 연도이면 YES 아니면 NO, 셋째 줄에 세이브 시각의 시와 분을 공백으로 구분해 출력한다(앞에 0을 붙이지 않는다).

제한
- −50 ≤ T ≤ 50
- 1 ≤ Y ≤ 4000
- 0 ≤ H ≤ 23, 0 ≤ M ≤ 59, 0 ≤ a ≤ 23, 0 ≤ b ≤ 59

예제 입력 1
36
2025
1 20 2 30

예제 출력 1
HEAT
YES
22 50

예제 입력 2
-5
2010
14 5 0 5

예제 출력 2
FREEZE
NO
14 0

제출: 'P2-02-세이브-시각.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-03 (0.36점)

[P2-03 B형] 탑 미리보기
시간 제한 1초 · 메모리 256MB

건축 툴이 탑 T개를 한꺼번에 미리 보여 준다. 층수가 N인 탑은 N줄짜리 그림으로 그린다. i번째 줄(1 ≤ i ≤ N)에는 '.'을 N−i개 쓴 뒤 '*'을 2i−1개 쓴다.

입력
첫째 줄에 탑 개수 T가 주어진다. 다음 T줄에 각 탑의 층수 N이 한 줄에 하나씩 주어진다.

출력
탑마다 먼저 '[k]'(k는 1부터 시작하는 탑 번호)를 한 줄에 출력하고, 이어서 그 탑의 그림 N줄을 출력한다. 줄 끝에 공백이나 '.'을 붙이지 않는다.

제한
- 1 ≤ T ≤ 100,000
- 1 ≤ N ≤ 10
- 출력은 최대 110만 줄(약 17MB)이다.

예제 입력 1
2
3
1

예제 출력 1
[1]
..*
.***
*****
[2]
*

예제 입력 2
1
2

예제 출력 2
[1]
.*
***

채점 항목: 출력 결과와 함께, 입출력이 많을 때 속도를 높이는 C++ 입출력 설정과 줄바꿈 방식을 코드에서 확인한다(2점).

제출: 'P2-03-탑-미리보기.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-04 (0.36점)

[P2-04 B형] 레이싱 고도 기록
시간 제한 1초 · 메모리 256MB

레이싱 트랙을 달리며 기록 N개를 남겼다. 기록마다 지나간 체크포인트 번호 c와 직전 기록과 비교한 고도 변화 h(음수면 내리막)가 있다. 가장 큰 고도 변화와 가장 작은 고도 변화, 그리고 기록에 나온 서로 다른 체크포인트 수를 구하라.

입력
첫째 줄에 N이 주어진다. 다음 N줄에 각 기록의 c와 h가 공백으로 구분되어 주어진다.

출력
첫째 줄에 가장 큰 고도 변화와 가장 작은 고도 변화를 이 순서로(큰 값 먼저) 공백으로 구분해 출력한다. 둘째 줄에 서로 다른 체크포인트 수를 출력한다.

제한
- 1 ≤ N ≤ 100,000
- 0 ≤ c ≤ 50,000
- −1,000,000,000 ≤ h ≤ 1,000,000,000
- 입력(c와 h)은 모두 vector<int>에 저장한 뒤, 저장한 vector를 순회해 답을 구한다(코드 확인 채점 항목).

예제 입력 1
4
3 120
0 -40
3 75
8 -40

예제 출력 1
120 -40
3

예제 입력 2
2
5 0
5 0

예제 출력 2
0 0
1

제출: 'P2-04-고도-기록.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-05 (0.36점)

[P2-05 B형] 차량 번호판 검사
시간 제한 1초 · 메모리 256MB

차량 등록 시스템의 번호 S는 숫자로만 된 문자열이며 매우 길 수 있다(맨 앞이 0일 수도 있다). 다음 세 가지를 구하라.
1. S의 뒤에서 K번째 글자(오른쪽 끝 글자가 뒤에서 1번째)
2. S의 모든 자리 숫자의 합
3. 1 이상 M 이하 정수 중, 10진수로 썼을 때 "13"이 연속으로 들어 있지 않은 수의 개수(13, 113, 130, 1313은 들어 있는 수)

입력
첫째 줄에 S, 둘째 줄에 K, 셋째 줄에 M이 주어진다.

출력
세 줄에 걸쳐 1, 2, 3의 답을 차례로 출력한다.

제한
- 1 ≤ S의 길이 ≤ 100, S는 '0'~'9'로만 이루어진다.
- 1 ≤ K ≤ S의 길이
- 1 ≤ M ≤ 1,000,000

예제 입력 1
31415
2
20

예제 출력 1
1
14
19

예제 입력 2
8
1
13

예제 출력 2
8
8
12

제출: 'P2-05-번호판-검사.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-06 (0.71점)

[P2-06 B형] 카드 조합과 물약 상자
시간 제한 1초 · 메모리 256MB

카드 N장이 있고 i번째 카드의 숫자는 b_i이다.
(1) 서로 다른 카드 3장을 고른다. 세 숫자의 합 X의 '자릿수 합'(예: X = 1997이면 26)이 정확히 S가 되도록 고르는 방법(순서 상관없는 조합)의 수를 구하라. 숫자가 같은 카드라도 서로 다른 카드는 다른 카드로 본다.
(2) 물약 P병을 9병들이 상자와 5병들이 상자에 빈칸 없이 꽉 채워 남김없이 담는다. 상자를 가장 적게 쓸 때의 상자 수를 구하라. 그렇게 담을 수 없으면 -1을 구한다.

입력
첫째 줄에 N과 S, 둘째 줄에 b_1 … b_N, 셋째 줄에 P가 주어진다.

출력
첫째 줄에 (1)의 답, 둘째 줄에 (2)의 답을 출력한다.

제한
- 3 ≤ N ≤ 100, 1 ≤ S ≤ 60
- 1 ≤ b_i ≤ 100,000
- 1 ≤ P ≤ 100,000
- 자릿수 합은 int DigitSum(int x)처럼 별도 함수로 만들어 호출한다(채점 항목).

예제 입력 1
4 10
12 34 55 9
10

예제 출력 1
1
2

예제 입력 2
3 1
1 2 7
31

예제 출력 2
1
-1

제출: 'P2-06-카드-조합.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-07 (0.71점)

[P2-07 B형] 상점 재고 정리
시간 제한 1초 · 메모리 256MB

상점 재고 기록 N개(N은 홀수)가 있다. 기록마다 아이템 이름, 진열 층 f, 가격 p가 있다. 다음 다섯 가지를 차례로 출력한다.
① 기록을 가격 오름차순으로, 가격이 같으면 층 오름차순으로 정렬해 한 줄에 하나씩 'f p' 형식(층 먼저, 가격 나중)으로 출력한다.
② 아이템 이름을 길이가 짧은 것부터, 길이가 같으면 사전 역순(z쪽이 먼저)으로 정렬하고, 같은 이름은 한 번만 남겨 한 줄에 하나씩 출력한다.
③ 가격 N개의 중앙값을 출력한다.
④ 입력 순서로 i번째부터 j번째까지의 기록에서 가격만 모았을 때 k번째로 비싼 가격을 출력한다.
⑤ 태그 문자열 W(영문 소문자)의 글자들을 z쪽부터 내림차순으로 정렬한 문자열을 출력한다.

입력
첫째 줄에 N. 다음 N줄에 이름 f p. 다음 줄에 i j k. 마지막 줄에 W.

출력
①의 N줄, ②의 줄들, ③ 한 줄, ④ 한 줄, ⑤ 한 줄을 이 순서로 출력한다.

제한
- 1 ≤ N ≤ 1,001, N은 홀수
- 이름은 영문 소문자 1~20자이며 여러 기록에 같은 이름이 나올 수 있다.
- 1 ≤ f ≤ 50, 1 ≤ p ≤ 1,000,000
- 1 ≤ i ≤ j ≤ N, 1 ≤ k ≤ j − i + 1
- W는 영문 소문자 1~50자

예제 입력 1
5
sword 2 300
potion 1 50
shield 2 300
potion 3 50
axe 1 120
2 5 1
banana

예제 출력 1
1 50
3 50
1 120
2 300
2 300
axe
sword
shield
potion
120
300
nnbaaa

예제 입력 2
1
gem 9 777
1 1 1
z

예제 출력 2
9 777
gem
777
777
z

제출: 'P2-07-상점-재고.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-08 (0.71점)

[P2-08 B형] 아이템 도감과 인벤토리
시간 제한 1초 · 메모리 256MB

도감에 아이템 N개가 1번부터 N번까지 등록되어 있다. 인벤토리 기록 M개, 질의 Q개, 식당 주문 기록이 주어진다.
① 질의마다 답한다. 질의가 숫자이면 그 도감 번호의 아이템 이름을, 문자열이면 그 아이템의 도감 번호를 출력한다. 도감에 없는 이름이면 UNKNOWN을 출력한다.
② 기록 '+ 이름'(획득)과 '- 이름'(판매)을 모두 처리한 뒤 인벤토리에 남은 아이템 이름을 사전 역순(z쪽이 먼저)으로 한 줄에 공백으로 구분해 출력한다. 비어 있으면 NOTHING을 출력한다.
③ 주문 K건과 배달 완료 K−1건의 메뉴 이름이 주어진다. 배달 완료 목록은 주문 목록에서 정확히 한 건만 빠진 것이다. 같은 메뉴가 여러 번 주문될 수 있다. 배달되지 않은 메뉴 이름을 출력한다.

입력
첫째 줄에 N M Q.
다음 N줄에 1번부터 N번까지 아이템 이름.
다음 M줄에 '+ 이름' 또는 '- 이름'. 기록의 이름은 모두 도감에 있고, 인벤토리에는 같은 아이템이 최대 1개다(이미 가진 아이템의 획득, 없는 아이템의 판매는 없다).
다음 Q줄에 질의가 하나씩. 숫자로 시작하면 1 이상 N 이하 정수이고, 아니면 이름이다.
다음 줄에 K. 다음 K줄에 주문 메뉴, 그다음 K−1줄에 배달 완료 메뉴.

출력
①의 Q줄, ②의 한 줄, ③의 한 줄을 이 순서로 출력한다.

제한
- 1 ≤ N, M, Q ≤ 100,000, 2 ≤ K ≤ 100,000
- 이름은 영문 소문자와 숫자로 된 1~20자이고 첫 글자는 영문 소문자다. 도감의 이름은 서로 다르다.

예제 입력 1
5 5 3
sword
bow
axe
wand
orb
+ bow
+ orb
+ axe
- bow
+ sword
axe
5
staff
4
soup
rice
soup
tea
tea
soup
rice

예제 출력 1
3
orb
UNKNOWN
sword orb axe
soup

예제 입력 2
2 2 2
gem
ore
+ gem
- gem
2
ore
2
pie
pie
pie

예제 출력 2
ore
2
NOTHING
pie

제출: 'P2-08-아이템-도감.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-09 (0.71점)

[P2-09 B형] 열차 편성 · 대사 검사 · 보물 상자
시간 제한 1초 · 메모리 256MB

게임 서버 로그를 처리한다. 입력은 세 부분이다.
① 열차 편성 명령 N개를 차례로 처리한다. 열차는 처음에 비어 있다.
- head x: 맨 앞에 객차 x를 연결한다.
- tail x: 맨 뒤에 객차 x를 연결한다.
- cuthead: 맨 앞 객차를 떼고 그 번호를 출력한다. 객차가 없으면 0.
- cuttail: 맨 뒤 객차를 떼고 그 번호를 출력한다. 없으면 0.
- length: 객차 수를 출력한다.
- first: 맨 앞 객차 번호를 출력한다(떼지 않음). 없으면 0.
- end: 맨 뒤 객차 번호를 출력한다(떼지 않음). 없으면 0.
② NPC 대사 문자열 B개는 영문 소문자와 '{' '}' '<' '>'로 이루어진다. 글자는 무시하고 괄호만 보아 짝이 맞으면 YES, 아니면 NO를 출력한다. 짝이 맞는다는 것은 모든 닫는 괄호가 아직 닫히지 않은 가장 최근의 여는 괄호와 같은 종류로 짝지어지고, 끝에 남는 여는 괄호가 없다는 뜻이다. 괄호가 하나도 없으면 YES. 예: 'a<b{c}>d'는 YES, '{<}>'는 NO.
③ 보물 상자 R개가 1번부터 R번까지 순서대로 줄 서 있고, i번 상자에는 수 k_i가 적혀 있다. 줄 맨 앞 상자를 연다(줄에서 빠지고 연 순서에 기록된다). 그다음 방금 연 상자의 수 k만큼 '줄 맨 앞 상자를 꺼내 맨 뒤로 보내기'를 반복한다(줄이 비어 있으면 하지 않는다). 모든 상자를 열 때까지 반복한다. 상자를 연 순서를 구한다.

입력
첫째 줄에 N, 다음 N줄에 명령.
다음 줄에 B, 다음 B줄에 대사 문자열.
다음 줄에 R, 다음 줄에 k_1 … k_R.

출력
①에서 출력이 있는 명령마다 한 줄씩, 이어서 ②의 결과 B줄, 마지막 줄에 ③의 연 순서(상자 번호를 공백으로 구분)를 출력한다.

제한
- 1 ≤ N ≤ 500,000, 1 ≤ x ≤ 1,000,000
- 1 ≤ B ≤ 100, 대사 문자열 길이 1~100
- 1 ≤ R ≤ 10,000, 0 ≤ k_i ≤ 10

예제 입력 1
6
tail 3
head 8
end
cuthead
length
cuttail
2
a<b{c}>d
{<}>
4
2 0 1 3

예제 출력 1
3
8
1
3
YES
NO
1 4 3 2

예제 입력 2
2
first
cuttail
1
abc
1
5

예제 출력 2
0
0
YES
1

제출: 'P2-09-열차-편성.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-10 (0.71점)

[P2-10 B형] 성벽 설계와 석상 운반
시간 제한 1초 · 메모리 256MB

(1) 성벽: 길이 4^N인 칸이 처음에 모두 '_'이다. 함수 Build(시작 위치, 길이)는 다음처럼 동작한다.
- 길이가 1이면 그 칸을 '*'로 바꾸고 끝낸다.
- 길이가 1보다 크면 구간을 길이가 같은 4조각으로 나누고, 2번째·3번째 조각에 대해 이 순서로 Build를 호출한다. 1번째·4번째 조각은 '_' 그대로 둔다.
Build(0, 4^N)을 한 번 호출해 성벽을 완성하고, 그동안 Build가 호출된 총횟수(처음 호출 포함)를 센다. 호출 횟수를 세는 변수는 전역으로 두지 않고, Build의 참조 매개변수(int&)로 넘겨 센다(코드 확인 채점 항목).
(2) 석상 운반: 받침대 1, 2, 3이 있고 받침대 3에 크기가 모두 다른 석상 K개가 큰 것이 아래로 가게 쌓여 있다. 한 번에 한 받침대의 맨 위 석상 하나만 다른 받침대의 맨 위로 옮길 수 있고, 작은 석상 위에 큰 석상을 올릴 수 없다. 석상 K개를 모두 받침대 1로 옮기는 최소 횟수의 이동 순서를 구한다.
(3) 석상이 M개일 때 같은 규칙으로 받침대 3에서 받침대 1로 모두 옮기는 최소 이동 횟수를 구한다.

입력
첫째 줄에 N K M이 주어진다.

출력
첫째 줄: 성벽 문자열(길이 4^N)
둘째 줄: Build 호출 총횟수
셋째 줄: (2)의 최소 이동 횟수 X
다음 X줄: 이동을 순서대로 'a b'(받침대 a의 맨 위 석상을 받침대 b로) 형식으로
마지막 줄: (3)의 답

제한
- 0 ≤ N ≤ 8
- 1 ≤ K ≤ 14
- 1 ≤ M ≤ 62

예제 입력 1
1 2 3

예제 출력 1
_**_
3
3
3 2
3 1
2 1
7

예제 입력 2
0 1 5

예제 출력 2
*
1
1
3 1
31

제출: 'P2-10-성벽.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-11 (1.07점)

[P2-11 B형] 캐릭터 편성과 마나 계산
시간 제한 1초 · 메모리 256MB

(1) 서로 다른 캐릭터 코드(영문 대문자 한 글자) N개가 정렬되지 않은 채 주어진다. 파티 M자리를 채우는 세 가지 경우를 모두 출력한다. 경우 하나는 고른 코드를 자리 순서대로 공백으로 구분해 한 줄에 쓰고, 경우들은 사전순(앞자리부터 비교해 알파벳이 앞선 것이 먼저)으로 출력한다.
① 같은 캐릭터를 두 번 넣을 수 없다(순서가 다르면 다른 경우).
② 같은 캐릭터를 두 번 넣을 수 없고, 자리 순서대로 알파벳 오름차순인 경우만.
③ 같은 캐릭터를 여러 번 넣어도 된다.
(2) 마나 계산: 마나 수치 a_1 … a_K가 이 순서로 놓여 있다. 수치 사이 K−1칸에 연산자를 하나씩 넣는다. 넣을 연산자는 +, −, ×, %(나머지)의 개수로 주어지며(합 K−1) 모두 써야 한다. 연산자 우선순위를 무시하고 왼쪽부터 차례로 계산한다. %는 C++의 % 연산과 같다(결과의 부호는 왼쪽 수를 따른다. 예: (−7) % 3 = −1). 만들 수 있는 결과의 최댓값과 최솟값을 구한다. 예: 7 3 5에 −1개, %1개 → (7−3)%5 = 4, (7%3)−5 = −4.

입력
첫째 줄에 N M. 둘째 줄에 캐릭터 코드 N개(공백 구분). 셋째 줄에 K. 넷째 줄에 a_1 … a_K. 다섯째 줄에 +, −, ×, %의 개수.

출력
①의 경우들, '--' 한 줄, ②의 경우들, '--' 한 줄, ③의 경우들, '--' 한 줄, 최댓값 한 줄, 최솟값 한 줄을 이 순서로 출력한다.

제한
- 1 ≤ M ≤ N ≤ 6, 캐릭터 코드는 서로 다른 영문 대문자
- 2 ≤ K ≤ 11, 1 ≤ a_i ≤ 100
- 연산자를 어떤 순서로 넣어도 계산 중간값과 결과는 −1,000,000,000 이상 1,000,000,000 이하다.

예제 입력 1
3 2
C A B
3
7 3 5
0 1 0 1

예제 출력 1
A B
A C
B A
B C
C A
C B
--
A B
A C
B C
--
A A
A B
A C
B A
B B
B C
C A
C B
C C
--
4
-4

예제 입력 2
1 1
Z
2
6 4
0 0 0 1

예제 출력 2
Z
--
Z
--
Z
--
2
2

제출: 'P2-11-캐릭터-편성.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-12 (1.07점)

[P2-12 B형] 지하철 노선과 마나 배분
시간 제한 1초 · 메모리 256MB

지하철역 N개(1~N번)와 양방향 구간 E개가 있다. 출발역은 S이다.
① 재귀 DFS로 S부터 탐색한다. 한 역에서 갈 수 있는 역이 여럿이면 번호가 큰 역부터 간다. 1번 역부터 N번 역까지 각 역이 몇 번째로 방문되었는지(출발역이 1, 방문하지 못한 역은 0)를 공백으로 구분해 출력한다.
② queue를 쓰는 BFS로 S부터 탐색한다. 인접한 역은 번호가 큰 역부터 큐에 넣는다. ①과 같은 형식으로 출력한다.
③ S에서 갈 수 있는 역의 수(S 포함).
④ 노선망 전체의 '무리' 수. 구간으로 서로 오갈 수 있는 역끼리 한 무리이며, 구간이 없는 역도 혼자 한 무리다.
⑤ 마나 배분: 수 c_1 … c_L이 순서대로 있다. 0에서 시작해 모든 수를 하나도 빠짐없이 차례로 더하거나 빼되, 빼기는 최대 X번까지만 쓸 수 있다. 결과가 T가 되는 방법의 수를 구한다.

입력
첫째 줄에 N E S. 다음 E줄에 구간의 양 끝 역 u v. 같은 구간이 여러 번 주어질 수 있다. 다음 줄에 L X T. 다음 줄에 c_1 … c_L.

출력
①, ②는 N개의 수를 공백으로 구분해 한 줄씩, ③, ④, ⑤는 정수 한 줄씩, 모두 다섯 줄을 출력한다.

제한
- 1 ≤ N ≤ 1,000, 0 ≤ E ≤ 10,000, 1 ≤ S ≤ N
- 1 ≤ u, v ≤ N, u ≠ v
- 1 ≤ L ≤ 20, 0 ≤ X ≤ L, 1 ≤ c_i ≤ 200, −4,000 ≤ T ≤ 4,000

예제 입력 1
5 4 1
1 2
1 3
2 4
3 4
3 1 2
1 2 3

예제 출력 1
1 4 2 3 0
1 3 2 4 0
4
2
1

예제 입력 2
3 0 2
1 0 5
5

예제 출력 2
0 1 0
0 1 0
1
3
1

제출: 'P2-12-지하철-노선.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-13 (1.07점)

[P2-13 B형] 설원 순찰 지도  (시간 제한 1초 · 메모리 256MB · C++17)

설원 지도는 R행 C열 격자이고, 각 칸은 눈길 '.', 나무 '#', 출발점 'S', 도착점 'E' 중 하나다. 'S'와 'E'는 정확히 하나씩 있고, 둘 다 눈길처럼 지나갈 수 있다. 다음 세 값을 구하라.

① 숲의 개수: 상하좌우로 맞닿은 나무 칸들은 같은 숲이다. 나무가 하나도 없으면 0.
② 썰매 최단 이동: 상하좌우로 한 칸씩, 나무가 아닌 칸으로만 움직일 때 S에서 E까지의 최소 이동 횟수. 칸 수가 아니라 움직인 횟수다. 갈 수 없으면 -1.
③ 스쿠터 점프 최단 이동: 한 번에 (세로 2칸·가로 1칸) 또는 (세로 1칸·가로 2칸) 떨어진 칸으로 점프한다(체스 나이트와 같은 8방향). 착지 칸은 지도 안이고 나무가 아니어야 하며, 넘어가는 칸은 무엇이든 상관없다. S에서 E까지 최소 몇 번 점프해야 하는지 구한다. 갈 수 없으면 -1.

[입력]
첫 줄에 R, C (2 ≤ R, C ≤ 100)
다음 R줄에 한 줄마다 C개의 문자가 공백 없이 주어진다.

[출력]
①, ②, ③의 답을 한 줄에 하나씩 차례로 출력한다.

[예제 입력 1]
4 5
S..#.
.#.#.
.#...
##..E

[예제 출력 1]
2
7
5

[예제 입력 2]
4 4
S#..
##.#
..#.
.#.E

[예제 출력 2]
4
-1
2

### P2-14 (0.71점)

[P2-14 B형] 물류 센터 점검  (시간 제한 1초 · 메모리 256MB · C++17)

두 가지 점검을 차례로 처리하고 답을 두 줄로 출력하는 프로그램을 작성한다.

[점검 1] 배송 로봇 레일
레일은 0번부터 L번까지 위치가 있다. 로봇은 위치 N에 있고 목적지는 위치 K다. 로봇은 1초마다 현재 위치 X에서 X-1, X+1, 2×X 중 한 곳으로 이동한다. 0보다 작거나 L보다 큰 위치로는 이동할 수 없다. 목적지에 도착하는 최소 시간(초)을 구하라.

[점검 2] 정전 복구
R행 C열 격자에 발전소 'P', 정전된 집 'h', 빈터 'x'가 있다. 발전소에는 처음(0분)부터 전기가 들어와 있다. 1분마다, 전기가 들어온 칸(발전소 또는 이미 복구된 집)과 상하좌우로 맞닿은 정전된 집에 동시에 전기가 들어온다. 빈터로는 전기가 통하지 않는다. 모든 집이 복구되는 최소 시간(분)을 구하라. 정전된 집이 처음부터 없으면 0을, 끝까지 복구되지 않는 집이 있으면 -1을 출력한다.

[입력]
첫째 줄: L N K (1 ≤ L ≤ 100,000, 0 ≤ N, K ≤ L)
둘째 줄: R C (1 ≤ R, C ≤ 500)
다음 R줄: 길이 C의 문자열('P', 'h', 'x'). 'P'는 1개 이상 있다.

[출력]
첫째 줄에 점검 1의 답, 둘째 줄에 점검 2의 답을 출력한다.

[예제 입력 1]
15 4 15
3 4
Phxh
hxhh
hhhP

[예제 출력 1]
4
2

[예제 입력 2]
10 9 1
2 3
Pxh
xhh

[예제 출력 2]
8
-1

### P2-15 (0.71점)

[P2-15 B형] 상점 운영 그리디 5종  (시간 제한 1초 · 메모리 256MB · C++17)

상점 운영에서 생기는 다섯 가지 계산을 한 프로그램으로 처리한다. 입력의 다섯 블록을 차례로 읽고 답을 다섯 줄로 출력한다.

1. 거스름돈: 동전 N종의 값이 큰 순서 B1 > B2 > … > BN으로 주어진다. BN = 1이고, B(i)는 항상 B(i+1)의 배수다. 개수 제한은 없다. 손님이 X원짜리 물건을 사고 Y원을 냈을 때, 거스름돈 Y-X원을 주는 데 필요한 동전의 최소 개수를 구하라(거스름돈이 0이면 0).
2. 선물 포장: 직원 한 명이 P명의 선물을 한 명씩 포장한다. i번째 손님의 포장에는 t_i분이 걸린다. 각 손님이 기다리는 시간은 '자기 포장이 시작되기 전까지' 흐른 시간이다(자기 포장 시간은 포함하지 않는다). 순서를 마음대로 정할 때, 기다리는 시간 합의 최솟값을 구하라.
3. 이벤트 부스: Q개의 이벤트가 시작 시각 s와 길이 d로 주어지며, 구간 [s, s+d) 동안 부스를 쓴다. 부스는 하나뿐이다. 이벤트가 끝나는 시각에 다음 이벤트를 시작할 수 있다. d = 0인 이벤트도 같은 규칙을 따른다. 열 수 있는 이벤트의 최대 개수를 구하라.
4. 할인 식: 숫자와 '+', '-'로만 된 식이 주어진다. 수 앞에 0이 붙어 있을 수 있다(예: 00050은 50). 괄호를 원하는 곳에 쳐서 식의 값을 최소로 만들 때, 그 최솟값을 구하라.
5. 우산 대여: 직원 n명에게 1번부터 n번까지 번호가 있다. L명은 우산을 잃어버렸고, R명은 여분 우산을 하나씩 가지고 있다. 여분 우산은 번호가 바로 앞이나 바로 뒤인 사람에게만 빌려줄 수 있다. 여분이 있는 사람이 자기 우산을 잃어버렸다면 여분을 자기가 쓰고 빌려줄 수 없다. 우산을 가진 직원 수의 최댓값을 구하라.

[주석 요구] 제출 코드에 다음 세 가지를 각 1~2줄의 주석으로 남긴다. (a) 1번에서 큰 동전부터 쓰는 것이 왜 최선인지 (b) 2번의 정렬 기준과 근거 (c) 3번의 정렬 기준(같은 값일 때의 기준 포함)과 근거.

[입력]
N X Y
B1 B2 … BN
P
t1 … tP
Q
s1 d1
…(Q줄)
식
n L R
L명의 번호
R명의 번호

[제한]
1 ≤ N ≤ 10, 0 ≤ X ≤ Y ≤ 100,000,000, B1 ≤ 1,000,000
1 ≤ P ≤ 1,000, 1 ≤ t_i ≤ 1,000
1 ≤ Q ≤ 100,000, 0 ≤ s ≤ 1,000,000,000, 0 ≤ d ≤ 1,000,000,000
식: 길이 50 이하이고 숫자로 시작하고 끝난다. 각 수는 5자리 이하이며 앞에 0이 붙을 수 있다.
2 ≤ n ≤ 30, 1 ≤ L ≤ n, 1 ≤ R ≤ n. 한 목록 안의 번호는 겹치지 않는다.

[출력]
1~5번의 답을 한 줄에 하나씩 출력한다.

[예제 입력 1]
4 1250 5000
500 100 10 1
4
6 2 5 1
5
1 3
2 2
4 1
0 6
6 2
40-30+20+10
6 2 2
3 5
4 6

[예제 출력 1]
14
12
3
-20
6

[예제 입력 2]
3 380 1000
100 10 1
3
4 4 1
4
3 0
1 2
3 2
5 0
00070-020+010
5 2 1
3 4
4

[예제 출력 2]
8
6
4
40
4

### P2-16 (1.07점)

[P2-16 B형] 몬스터 도감과 방어선 설계  (시간 제한 1초 · 메모리 256MB · C++17)

세 부분을 차례로 처리해 출력한다.

1부분. 도감 조회: 도감에 몬스터 ID N개가 등록되어 있다(같은 값이 여러 번 나올 수 있다). 질의 M개마다 등록되어 있으면 1, 없으면 0을 '한 줄에 공백으로 구분해' 출력한다.
2부분. 방어탑 배치: 일직선 위에 설치 후보 위치 H개가 있다. 그중 C곳을 골라 방어탑을 세운다. 가장 가까운 두 방어탑 사이의 거리를 최대로 할 때, 그 거리를 구하라.
3부분. 스테이지 일정: 스테이지 S개를 1번부터 순서대로 플레이해야 하고, i번 스테이지는 p_i분이 걸린다. 순서를 바꾸지 않고 스테이지를 D개 이하의 연속된 묶음으로 나누어, 하루에 한 묶음씩 플레이한다. 하루 플레이 시간 중 가장 긴 날의 시간을 최소로 할 때, 그 값을 구하라.

[입력]
N M
a1 … aN
q1 … qM
H C
x1 … xH
S D
p1 … pS

[제한]
1 ≤ N, M ≤ 100,000, -1,000,000,000 ≤ a_i, q_j ≤ 1,000,000,000
2 ≤ C ≤ H ≤ 200,000, 0 ≤ x_i ≤ 1,000,000,000, 위치는 서로 다르고 정렬되어 있지 않다
1 ≤ D ≤ S ≤ 100,000, 1 ≤ p_i ≤ 1,000,000,000

[출력]
첫째 줄: 1부분의 답 M개(공백 구분)
둘째 줄: 2부분의 답
셋째 줄: 3부분의 답

[예제 입력 1]
5 4
40 -7 13 100 5
13 0 -7 41
6 4
3 14 6 20 11 1
5 3
4 2 7 3 5

[예제 출력 1]
1 0 1 0
5
8

[예제 입력 2]
2 3
1000000000 -1000000000
-1000000000 999999999 1000000000
2 2
0 1000000000
3 1
1000000000 1000000000 1000000000

[예제 출력 2]
1 0 1
1000000000
3000000000

### P2-17 (1.07점)

[P2-17 B형] 탑 오르기 계산기  (시간 제한 1초 · 메모리 256MB · C++17)

아래 두 함수는 n칸 계단을 한 번에 1칸, 2칸, 3칸씩 올라가는 방법의 수 Stair(n)을 구한다(Stair(1)=1, Stair(2)=2, Stair(3)=4).

int Stair(int n) {
    if (n <= 2) return n;
    if (n == 3) return 4;
    return Stair(n - 1) + Stair(n - 2) + Stair(n - 3);
}

int StairDP(int n) {
    dp[1] = 1; dp[2] = 2; dp[3] = 4;
    for (int i = 4; i <= n; i++)
        dp[i] = dp[i - 1] + dp[i - 2] + dp[i - 3];   // ②
    return dp[n];
}

다음 다섯 가지를 구하라.
1. Stair(a)를 한 번 호출했을 때 Stair 함수가 호출되는 총 횟수(첫 호출 포함)와, StairDP(a)에서 ② 줄이 실행되는 횟수. 두 수를 공백으로 구분해 출력한다.
2. Stair(b)를 1,000,000,007로 나눈 나머지.
3. 숲의 나무 수 G(c): 1일째에 나무 1그루가 심어진다. 나무는 죽지 않는다. 심어진 날을 1일째로 셀 때, 5일째 되는 날부터 매일 씨앗을 떨어뜨려 새 나무 1그루가 자란다(새 나무도 같은 규칙을 따른다). c일째의 나무 수를 구하라. 처음 14일은 다음과 같다.
   일: 1 2 3 4 5 6 7 8 9 10 11 12 13 14
   수: 1 1 1 1 2 3 4 5 7 10 14 19 26 36
4. 하루 점수 변화 기록 L개에서, 연속된 하루 이상의 구간을 골라 얻는 합의 최댓값.
5. 에너지 x에서 시작해 '5로 나누어떨어지면 5로 나누기', '2로 나누어떨어지면 2로 나누기', '1 빼기' 중 하나를 한 번에 하나씩 적용해 1을 만들 때, 필요한 최소 연산 횟수.

[입력]
a
b
c
L
v1 v2 … vL
x

[제한]
1 ≤ a ≤ 25, 1 ≤ b ≤ 1,000,000, 1 ≤ c ≤ 100, 1 ≤ L ≤ 100,000, -1,000 ≤ v_i ≤ 1,000, 1 ≤ x ≤ 1,000,000

[출력]
1~5번의 답을 한 줄에 하나씩 출력한다(1번은 두 수).

[예제 입력 1]
5
5
8
7
4 -6 3 2 -1 5 -9
6

[예제 출력 1]
7 2
13
5
9
2

[예제 입력 2]
1
3
2
2
-7 -3
1

[예제 출력 2]
1 0
4
1
-3
0

### P2-18 (1.07점)

[P2-18 B형] 마을 꾸미기 DP 4종  (시간 제한 1초 · 메모리 256MB · C++17)

네 가지 계산을 차례로 처리한다.

1. 지붕 색칠: 집 N채가 일렬로 있고, 집마다 지붕을 빨강·파랑·노랑·초록 네 색 중 하나로 칠한다. 집 i를 각 색으로 칠하는 비용이 주어진다. 이웃한 두 집의 지붕 색은 서로 달라야 한다. 비용 합의 최솟값을 구하라.
2. 광산 삼각형: 높이 T인 삼각형 모양으로 광석 값이 있고, 손실을 뜻하는 음수도 있다. 꼭대기에서 출발해 한 줄 내려갈 때마다 바로 아래 왼쪽이나 오른쪽 칸으로 간다. 맨 아래 줄까지 지나간 칸 값의 합의 최댓값을 구하라.
3. 같은 점수 배열 s_1..s_S로 두 규칙의 답을 공백으로 구분해 출력한다.
   (가) 탑 층계: 1층부터 S층까지 층마다 점수가 있다. 바닥(층이 아니다)에서 출발해 한 번에 1층 또는 2층 위로 오른다. 연속한 세 층을 모두 밟을 수는 없다. 꼭대기 S층은 반드시 밟아야 한다. 밟은 층 점수 합의 최댓값을 구한다.
   (나) 포션 진열대: 포션 S병이 일렬로 있다. 원하는 만큼 고를 수 있지만 연속으로 놓인 세 병을 모두 고를 수는 없다. 마지막 병을 꼭 고를 필요는 없다. 고른 점수 합의 최댓값을 구한다.
4. 암호 숫자: 이웃한 두 자리 숫자의 차가 2 이상인 L자리 양의 정수(예: 1, 307, 9292)의 개수를 1,000,000,007로 나눈 나머지. 첫 자리는 0일 수 없다.

[입력]
N
다음 N줄: 네 색의 비용
T
다음 T줄: i번째 줄에 i개의 정수
S
s1 … sS
L

[제한]
2 ≤ N ≤ 1,000, 비용은 1~1,000
1 ≤ T ≤ 500, 광석 값은 -100~100
1 ≤ S ≤ 10,000, 0 ≤ s_i ≤ 1,000
1 ≤ L ≤ 100

[출력]
네 줄에 1~4의 답을 출력한다(3번째 줄은 두 수).

[예제 입력 1]
3
30 50 20 40
10 60 40 35
50 30 70 15
3
-2
4 -6
-1 3 5
8
12 9 3 1 1 40 30 2
2

[예제 출력 1]
45
5
64 92
64

[예제 입력 2]
2
4 9 2 7
4 9 2 7
1
-100
2
0 1000
1

[예제 출력 2]
6
-100
1000 1000
9

### P2-19 (1.07점)

[P2-19 B형] 몬스터 사냥 기록과 스킬 장착  (시간 제한 1초 · 메모리 256MB · C++17)

두 가지를 계산한다.

1. 사냥 기록: 사냥한 몬스터의 레벨 기록 a_1..a_N이 시간 순서대로 있다. 순서를 유지한 채 몇 개를 골라 '뒤로 갈수록 엄격히 작아지는' 부분 수열을 만들 때, 가장 긴 길이를 구하라.
2. 스킬 장착: 스킬 M개가 있고 스킬 i는 데미지 d_i, 마나 비용 c_i를 가진다. 마나 비용 합이 B 이하가 되도록 스킬을 고른다. 각 스킬은 최대 한 번만 고를 수 있다. 데미지 합의 최댓값을 구하라.

[구현 조건] 2번은 1차원 배열 dp[마나]로 풀어야 한다. 마나 반복을 큰 쪽에서 작은 쪽으로 도는 이유를 코드 주석으로 2~3줄 남긴다.

[입력]
N
a1 … aN
B M
다음 M줄: d c (데미지가 먼저, 비용이 나중)

[제한]
1 ≤ N ≤ 1,000, 1 ≤ a_i ≤ 1,000
1 ≤ B ≤ 100,000, 1 ≤ M ≤ 100, 0 ≤ d_i ≤ 1,000, 1 ≤ c_i ≤ 100,000

[출력]
첫째 줄에 1번의 답, 둘째 줄에 2번의 답을 출력한다.

[예제 입력 1]
8
50 30 40 20 20 35 10 5
12 4
30 4
70 7
25 3
45 5

[예제 출력 1]
5
115

[예제 입력 2]
4
1 2 3 4
5 2
10 6
9 5

[예제 출력 2]
1
9

### P2-20 (1.07점)

[P2-20 B형] 매칭 서버와 배송망 점검  (시간 제한 1초 · 메모리 256MB · C++17)

세 부분을 차례로 처리한다.

1부분. 레벨 매칭: 기준 레벨 P가 주어지고, 정수 x가 Q개 차례로 들어온다. x ≥ 1이면 레벨 x인 플레이어가 대기열에 들어온다. x = 0이면, 대기열에서 레벨이 P에 가장 가까운(|레벨 - P|가 가장 작은) 플레이어를 꺼내 그 레벨을 출력한다. 가까운 정도가 같으면 레벨이 높은 플레이어를 먼저 꺼낸다. 대기열이 비어 있으면 0을 출력한다.
2부분. 단방향 배송망: 거점 V개와 '단방향' 도로 E개가 있다. 거점 S에서 출발해 갈 수 있는 거점들의 최단 거리 중 가장 큰 값과, 갈 수 없는 거점의 수를 공백으로 구분해 출력한다(S 자신은 거리 0으로 갈 수 있는 거점에 포함).
3부분. 페인트 타일: R행 C열 격자의 칸마다 대문자 색이 칠해져 있다. (1,1)에서 (R,C)까지 상하좌우로 이동한다. 같은 색 칸으로 옮기면 비용 0, 다른 색 칸으로 옮기면 비용 1이다. 최소 비용을 출력한다.

[입력]
Q P
x1 x2 … xQ (한 줄)
V E S
다음 E줄: u v w (u에서 v로 가는 길이 w의 단방향 도로)
R C
다음 R줄: 길이 C의 대문자 문자열

[제한]
1 ≤ Q ≤ 100,000, 1 ≤ P ≤ 1,000, 0 ≤ x ≤ 1,000
1 ≤ V ≤ 20,000, 0 ≤ E ≤ 200,000, 1 ≤ w ≤ 1,000, 1 ≤ S ≤ V. 같은 도로가 여러 번 있을 수 있다.
2 ≤ R, C ≤ 100

[출력]
1부분: x=0마다 한 줄씩 출력한다. 이어서 2부분 한 줄, 3부분 한 줄을 출력한다.

[예제 입력 1]
8 50
45 60 0 55 40 0 0 0
5 6 1
1 2 4
1 3 2
3 2 1
2 4 5
4 1 1
3 4 9
3 4
AABB
CABB
CCCB

[예제 출력 1]
45
55
60
40
8 1
1

[예제 입력 2]
3 10
0 10 0
3 1 2
1 2 7
2 2
AB
BA

[예제 출력 2]
0
10
0 2
2

### P2-21 (0.71점)

[P2-21 B형] 광산 레일 채굴량  (시간 제한 1초 · 메모리 256MB · C++17)

일직선 레일 위 N개 구역에 구역마다 광석량 a_1..a_N이 있다. 질의 Q개가 주어지며, 각 질의 'x y'는 x번 구역과 y번 구역 사이(양 끝 포함)의 광석량 합을 묻는다. x가 y보다 클 수도 있다. 질의마다 답을 출력하라.

[입력]
N Q
a1 … aN
다음 Q줄: x y

[제한]
1 ≤ N, Q ≤ 100,000, 0 ≤ a_i ≤ 10,000, 1 ≤ x, y ≤ N

[출력]
질의마다 한 줄에 합을 출력한다.

[예제 입력 1]
5 4
4 0 9 2 6
2 4
4 2
5 5
1 5

[예제 출력 1]
11
11
6
21

[예제 입력 2]
3 3
10000 10000 10000
3 1
2 3
1 1

[예제 출력 2]
30000
20000
10000

### P2-22 (1.43점)

[P2-22 B형] [실전 세트 1/3] 보드게임 엔진 — 주사위 기차와 연쇄 포탑  (프로그래머스형 · C++17 · 각 테스트 1초)

이 문항은 함수 두 개를 구현한다(1-가 6점, 1-나 4점). 방향은 북(위, 행 -1), 동(오른쪽, 열 +1), 남(아래, 행 +1), 서(왼쪽, 열 -1) 네 가지다. 오른쪽(시계 방향) 90° 회전은 북→동→남→서→북, 왼쪽 90° 회전은 그 반대 순서다.

━ 1-가. 주사위 기차 ━
vector<int> diceTrain(vector<string> board, vector<string> commands)

n행 m열 보드에서 각 칸은 '.'(빈칸) 또는 '#'(벽)이다. 기차는 길이 1로 맨 왼쪽 아래 칸 (n-1, 0)에서 '북쪽'을 보고 시작한다. 기관차 위에 주사위가 있으며, 처음에는 윗면 1, 아랫면 6, 북쪽 면 5, 남쪽 면 2, 동쪽 면 3, 서쪽 면 4다. commands의 각 문자열은 다음 중 하나이며 앞에서부터 처리한다.
- "L": 왼쪽으로 90° 회전, "R": 오른쪽으로 90° 회전, "U": 뒤로 돌기(180°). 회전할 때 주사위는 구르지 않는다.
- "F k"(k는 1~9인 한 자리 수): 한 칸 이동을 k번 반복한다.
한 칸 이동 규칙: 앞 칸이 보드 밖이거나, 벽이거나, 현재 기차가 차지한 칸(꼬리 포함)이면 게임이 즉시 끝나고 남은 명령은 모두 무시한다. 그렇지 않으면 기관차가 그 칸으로 이동하고 주사위가 이동 방향으로 한 번 구른다. 구른 뒤 주사위 '윗면'이 6이면 꼬리를 그대로 둔다(길이 +1). 6이 아니면 꼬리 칸을 비운다.
주사위가 구르는 규칙: 동쪽으로 구르면 동쪽 면→아랫면, 윗면→동쪽 면, 서쪽 면→윗면, 아랫면→서쪽 면이 된다(북·남 면은 그대로). 서쪽으로 구르면 서쪽 면→아랫면, 윗면→서쪽 면, 동쪽 면→윗면, 아랫면→동쪽 면이 된다. 북쪽으로 구르면 북쪽 면→아랫면, 윗면→북쪽 면, 남쪽 면→윗면, 아랫면→남쪽 면이 된다(동·서 면은 그대로). 남쪽으로 구르면 남쪽 면→아랫면, 윗면→남쪽 면, 북쪽 면→윗면, 아랫면→북쪽 면이 된다.
[성공한 한 칸 이동의 총 횟수, 끝났을 때 기차 길이]를 반환한다.
제한: 2 ≤ n, m ≤ 20, board[n-1][0]은 '.', 1 ≤ commands 길이 ≤ 200.

입출력 예
board = ["....", "....", "...."], commands = ["F 2", "R", "F 3", "R", "F 1"] → [6, 2]
board = ["..#..", ".....", "....."], commands = ["F 2", "R", "F 4", "R", "F 2", "L", "L", "F 9"] → [3, 2]
(예 1: 북쪽으로 두 칸 가는 동안 두 번째 이동 뒤 윗면이 6이라 길이가 2가 된다. 예 2: 동쪽 두 번째 칸이 벽이라 3번 이동하고 끝난다.)

━ 1-나. 연쇄 포탑 ━
string turretChain(string turrets, vector<vector<int>> ops)

포탑 K대가 일렬로 있고, turrets의 i번째 문자('N','E','S','W')는 i번 포탑(1부터)의 방향이다. ops의 각 원소 [i, r]은 i번 포탑을 r=1이면 시계 방향, r=-1이면 반시계 방향으로 90° 돌리라는 명령이다. 명령 하나를 처리하는 규칙은 다음과 같다.
- 먼저, 아무도 돌기 전의 방향을 기준으로 회전을 모두 정한다. i번은 r 방향으로 돈다. 이웃한 두 포탑이 '정반대 방향'(N과 S, 또는 E와 W)을 보고 있었고 한쪽이 돌기로 정해졌다면, 다른 쪽도 '같은 방향'으로 돈다. 이렇게 i에서 왼쪽과 오른쪽으로 한 대씩 퍼지며, 조건이 맞지 않는 곳에서 그 방향의 전파는 멈춘다.
- 정해진 회전을 동시에 적용한다.
모든 명령을 처리한 뒤의 방향 문자열을 반환한다.
제한: 2 ≤ K ≤ 50, 1 ≤ ops 길이 ≤ 100.

입출력 예
turrets = "NSNE", ops = [[1,1]] → "EWEE"
turrets = "ESWN", ops = [[2,-1],[4,1]] → "EEWE"

### P2-23 (1.07점)

[P2-23 B형] [실전 세트 2/3] 왕복 수도 정하기  (프로그래머스형 · C++17 · 각 테스트 1초)

도시 n개(1~n번)가 '단방향' 항로로 이어져 있다. 한 도시 c를 수도로 정하면, 다른 모든 도시 i에 대해 '수도에서 i로 가는 최단 시간 + i에서 수도로 돌아오는 최단 시간'(왕복 시간)이 정해진다. 수도의 평가값은 이 왕복 시간 중 가장 큰 값이다. 모든 다른 도시와 왕복이 가능한 도시만 수도가 될 수 있다. 평가값이 가장 작은 도시를 수도로 고르고, 같으면 번호가 작은 도시를 고른다. [수도 번호, 평가값]을 반환하라. 수도가 될 수 있는 도시가 없으면 [-1, -1]을 반환한다.

vector<int> solution(int n, vector<vector<int>> routes)

[제한]
- 2 ≤ n ≤ 100
- 1 ≤ routes 길이 ≤ 5,000. routes[i] = [from, to, cost]는 from에서 to로만 갈 수 있는 항로다(from ≠ to, 1 ≤ cost ≤ 100,000).
- 같은 출발·도착의 항로가 여러 개 있을 수 있다.

[입출력 예]
n = 4, routes = [[1,2,3],[2,3,4],[3,1,5],[3,4,2],[4,3,1],[2,1,6]] → [3, 12]
n = 3, routes = [[1,2,1],[2,3,1]] → [-1, -1]

[설명] 예 1에서 3번이 수도이면 왕복 시간은 1번 5+7=12, 2번 8+4=12, 4번 2+1=3이고, 최댓값 12가 가장 작다. 예 2는 돌아오는 항로가 없어 어느 도시도 수도가 될 수 없다.

### P2-24 (1.43점)

[P2-24 B형] [실전 세트 3/3] 방화벽 설치  (프로그래머스형 · C++17 · 각 테스트 1초)

창고 지도 grid에서 각 칸은 '.'(빈칸), '#'(벽), 'F'(불), 'T'(보물)다. 빈칸 중 정확히 k곳에 방화벽을 새로 세울 수 있다. 그다음 불은 0분에 모든 'F' 칸에서 동시에 시작해, 1분마다 상하좌우로 맞닿은 벽이 아닌 칸('.', 'T')으로 번진다. 보물에 불이 처음 닿는 시각을 가장 늦추도록 방화벽 위치를 고를 때, 그 시각(분)을 반환하라. 방화벽을 잘 세워 불이 보물에 아예 닿지 않게 할 수 있으면 -1을 반환한다.

int solution(vector<string> grid, int k)

[제한]
- 2 ≤ grid 행 수, 열 수 ≤ 8
- 'F'는 1개 이상, 'T'는 정확히 1개
- 1 ≤ k ≤ 3, 빈칸('.')은 k개 이상

[입출력 예]
grid = ["F.....", "......", "..T...", "......", ".....F"], k = 2 → 5
grid = ["F..#....", "...#....", "...#....", "......T."], k = 1 → -1
(예 2: 넷째 줄의 벽 틈 한 칸을 막으면 불이 보물에 닿지 않는다.)

[세트 기록] 실전 세트(P2-22~24)를 마치기 전에, 제출 저장소의 '실전세트-기록.md'에 세 문제 각각의 해결 여부(예제 통과 / 일부 / 미해결)와 걸린 시간(분)을 적어 세트 시간 안에 커밋한다.

## 3부-L 라이브 실기 (16.9점 · 720분)

- AI·인터넷 금지, 엔진 소스·공식 문서만 허용. 3블록 × 240분이고 블록마다 권장 시간 합은 200분 이하다(40분 여유).
- 블록1·2는 새 시험 프로젝트(A형 RuneArena·접두사 Rune, B형 DuskKeep·접두사 Dusk)에서, 블록3은 응시자 본인의 포트폴리오 저장소(UE5-ActionArena, 태그 exam-submit)를 채점자가 시험 PC에 Clone한 사본에서 한다. 채점자는 블록3 사본에 결함을 미리 심어 둔다.
- 과제마다 기능 브랜치 → PR → Squash merge로 올린다. PR 본문은 '무엇·왜, 테스트'면 충분하다(브랜치·커밋·PR 규칙은 3부-P의 P3-04·05에서 채점).
- 블록1에서 캐릭터(P3-10)를 끝내지 못했으면 블록2 시작 때 채점자가 주는 기준 커밋에서 시작할 수 있다. 이미 받은 블록1 점수는 바뀌지 않는다.

> **블록1 (240분 · 권장 합 200분)** — 새 시험 프로젝트: 세팅 · 저장소 · 디버깅 · AI-Off① · 프레임워크 · 캐릭터

### P3-01 (0.42점)

[3부-L 라이브·블록1·B형] 개발 환경 세팅 (권장 30분)
시작: UE 5.8·VS 설치 PC. 감독관이 VS 옵션 2개를 틀어 두었다. 프로젝트를 만들고 VS가 열리면 손을 든다(감독관이 VS 솔루션 설정을 한 번 바꾼다).
1) Games → Blank로 C:\Projects\DuskKeep 생성: C++·Desktop·Scalable·Starter Content 끔.
2) 저사양 가정: Scalability Low, 에디터가 뒤에 있을 때 CPU를 덜 쓰게 하는 설정 켬.
3) VS: 커리큘럼의 언리얼용 옵션 3가지를 점검해 틀린 것을 고치고, 무엇이 틀렸는지 메모.
4) 감독관 개입 뒤 솔루션 구성·플랫폼·시작 프로젝트를 커리큘럼 기준으로 바로잡고, 바뀌어 있던 것을 메모.
5) 에디터 메뉴로 Actor 부모 C++ 클래스 DuskBeacon 생성, VS에서 Ctrl+T로 .h/.cpp 열기.
6) 에디터를 닫고 .cpp의 정의를 BeginPlay(int32 Unused)로 바꿔 VS에서 빌드 → 출력 창 첫 error 줄 기록 → 되돌려 빌드 → 빌드 시간 기록.
제출: 채점자 화면 확인(Ctrl+T로 .cpp 열기 시연), 메모(P3-02에서 docs/exam-log.md로 올림).

### P3-02 (0.85점)

[3부-L 라이브·블록1·B형] 게임 저장소 만들기 (권장 30분)
시작: C:\Projects\DuskKeep(에디터 닫힘), 일부가 빠진 lfs-setup.txt(바탕화면), 설정이 틀어진 GitHub Desktop(시험 계정 로그인됨).
1) 계정·커밋 작성자 설정을 점검해 고치고 무엇이 틀렸는지 메모.
2) lfs-setup.txt를 커리큘럼 템플릿과 비교해 빠진 줄을 채운 뒤 최상위 .gitattributes로.
3) 폴더를 저장소로 생성(Ignore 템플릿·LFS 포함).
4) 첫 커밋 전 올라가면 안 되는 것을 점검해 제외.
5) 'chore: UE 5.8 프로젝트 생성'으로 main에 커밋하고, 공개 저장소 UE5-DuskKeep로 올림.
6) docs/exam-log.md(P3-01 메모 포함):
(a) Saved·Config·Intermediate·Content·.vs·DuskKeep.uproject를 원본/생성물로 나누고, 유니티 폴더와의 대응 1줄 + 생성물을 안 올리는 이유
(b) '*.wav …' 줄과 '* text=auto'의 뜻
(c) 경로 이유(C:\Projects, OneDrive 피함)
exam-log.md는 첫 커밋에 같이 넣거나, 올린 뒤 브랜치 → PR(무엇·왜) → Squash merge로 올린다.
제출: UE5-DuskKeep, 첫 커밋, exam-log.md.

### P3-06 (0.85점)

[3부-L 라이브·블록1·B형] 디버깅 시연 (권장 15분, 채점자 입회)
시작: P3-02까지 올린 main의 ADuskBeacon. 브랜치 feat/dusk-debug. 감독관 메모: "UE 5.8에서 AActor::Tick은 virtual void Tick(double DeltaTime)이다."
1) Super::BeginPlay() 아래 Warning 수준 UE_LOG "Beacon Lit" → 그 줄에 중단점 → 디버거 실행 → 액터 2개 배치 후 Play → 두 번 멈추는지 확인, 첫 멈춤의 호출 스택으로 BeginPlay를 누가 불렀는지 설명.
2) 에디터를 끄지 않고 "Beacon Lit (LC)"로 바꿔 반영·확인, 재시작이 필요 없는 이유 한 문장.
3) AActor 선언 파일과 UE_LOG 정의 파일을 VS 기능만으로 찾아 경로를 말한다.
4) 메모를 엔진 소스로 검증해 일지(docs/exam-log.md)에.
제출: 입회 확인, PR(무엇·왜, 테스트) → Squash merge(UE_LOG 변경, docs/exam/callstack-b.png, 일지).

### P3-07 (0.85점)

[3부-L 라이브·블록1·B형] AI-Off ①: 등불 (권장 40분: C++ 30분 + BP 10분)
시작: P3-06까지 merge된 main. 브랜치 feat/dusk-lantern. 시작·종료 시각은 감독관이 기록.
1) ADuskLantern: StaticMesh 루트.
2) 시작 위치 기준 상하 사인파 + RotationRate만큼 회전, 프레임레이트와 무관.
3) 디테일 패널 값: BobHeight(cm, 25), BobSpeed(rad/s, 3.0), RotationRate(FRotator 도/초, P0·Y60·R20), PhaseOffset(초, 0).
4) BP_DuskLantern 3개: BobHeight·BobSpeed는 (40, 2.0)으로 같게, PhaseOffset 0 / 0.5 / 1.0, 세 번째는 RotationRate Yaw −120.
5) 일지에 성공/막힌 지점·시간.
제출: PR(무엇·왜, 테스트, GIF) → Squash merge, .h/.cpp, 일지.

### P3-09 (0.42점)

[3부-L 라이브·블록1·B형] 프레임워크 뼈대 (권장 25분)
시작: P3-07까지 merge된 main. 바탕화면의 L_DuskTrial.umap을 에디터를 닫은 채 Content/Dusk/Maps에 넣고 시작. 감독관이 이 맵의 설정 하나를 바꿔 두었다. 브랜치 feat/dusk-framework.
1) 빈 C++ ADuskGameMode·ADuskPlayerController·ADuskCharacter를 알맞은 엔진 부모로.
2) BP 자식 3개를 Content/Dusk/Framework에 BP_ 접두사로.
3) 프로젝트 기본 GameMode·Pawn·PlayerController를 내 BP로.
4) L_DuskTrial에서 Play했을 때 내 캐릭터 대신 기본 구체 Pawn이 나오면 원인을 찾아 고치고 원인·메뉴를 일지(docs/exam-log.md)에.
5) Play 중 Outliner로 내 BP 인스턴스 확인.
제출: PR(무엇·왜, 테스트) → Squash merge(ini·BP·맵 변경 포함), 일지, 시연.

### P3-10 (1.27점)

[3부-L 라이브·블록1·B형] 3인칭 캐릭터와 입력 (권장 60분)
시작: P3-09까지 merge된 main. 브랜치 feat/dusk-character-input.
1) 콘텐츠 팩으로 마네킹을 추가해 BP_DuskCharacter 메시로 지정.
2) C++로 카메라 붐(길이 450)과 카메라. 마우스를 돌리면 카메라만 돌고 캐릭터는 이동 방향을 본다.
3) Content/Dusk/Input에 이동·시점·점프·질주 Input Action 4개와 Mapping Context 1개(IA_/IMC_ 접두사, 이름은 직접). 키: WASD 이동, 마우스 시점, Space 점프, Left Shift 질주.
4) 입력 에셋은 C++ 변수로 받아 BP에서 지정하고, 매핑 추가와 함수 연결은 C++에서.
5) Left Shift 동안 400 → 900, 떼면 400. 두 수치는 디테일 패널에서 바꿀 수 있게 하고, 나중에 데이터 에셋으로 옮길 곳임을 커리큘럼의 TODO 주석 형식으로 표시.
6) Play로 이동·시점·점프·질주 시연. 영상 끝에 BP_DuskCharacter의 질주 값을 600으로 바꿔 Play한 장면 포함.
제출: PR(무엇·왜, 테스트, GIF 또는 영상) → Squash merge, .h/.cpp.

> **블록2 (240분 · 권장 합 190분)** — 같은 시험 프로젝트: AI-Off② · AI-Off③ · 복제·RPC 실험

### P3-12 (1.69점)

[3부-L 라이브·블록2·B형] AI-Off ②: 사용 시스템 (권장 60분)
시작: 블록1까지 merge된 main(ADuskCharacter·블록1 IMC). 브랜치 feat/dusk-use. 시작·종료 시각은 감독관이 기록.
1) IDuskUsable: Use(AActor* User), GetUsePrompt()(FText). C++·BP 양쪽에서 구현 가능.
2) UDuskUseComponent: 매 프레임 검사 금지. 0.2초 주기로 캐릭터 위치에서 카메라가 보는 방향 400cm까지 반지름 40 구를 쓸어 대상 탐색. 대상이 바뀌었을 때만 BP에서도 받을 수 있는 OnUseTargetChanged(AActor*). F로 Use. 컴포넌트가 끝날 때 주기 실행을 멈춘다.
3) ADuskChest(C++): Use마다 뚜껑 Pitch 0↔−70.
4) BP_DuskBell: BP에서만 구현(문구 출력).
5) 일지에 시간·막힌 지점, 0.2초로 정한 근거 1줄.
제출: PR(무엇·왜, 테스트, 영상) → Squash merge, 코드, 일지.

### P3-14 (1.69점)

[3부-L 라이브·블록2·B형] AI-Off ③: 체력·데미지·사망 (권장 90분)
시작: P3-12까지 merge된 main. 브랜치 feat/dusk-health. 시작·종료 시각은 감독관이 기록.
1) UDuskHealthComponent: 최대·현재 체력, 체력 변화(새 체력, 최대)·사망을 BP에서도 받는 이벤트 2개. 데미지는 엔진 데미지 함수 → 소유 액터 데미지 이벤트로만 받는다(컴포넌트 직접 호출 금지). 0 미만 없음, 사망 이벤트 1회.
2) ADuskScarecrow(최대 150): 마우스 왼쪽 → 카메라 전방 트레이스 → 맞은 지점 정보를 담아 30. 0이 되면 사망 이벤트 로그(제거는 선택).
3) ADuskSpikeTrap: 플레이어가 겹친 동안 1초마다 20(타이머), 벗어나면 멈춤. 플레이어 최대 80.
4) 플레이어 사망: State.Dead 태그, 입력 차단, 래그돌 또는 몽타주, 5초 뒤 제거.
5) 허수아비 체력바(화면 또는 머리 위)가 체력 변화 이벤트로만 갱신.
제출: PR(무엇·왜, 테스트, 허수아비 5타·함정 사망 영상) → Squash merge, 일지(시간·막힌 지점).

### P3-25 (1.69점)

[3부-L 라이브·블록2·B형] 복제·RPC 실험 (권장 40분)
시작: P3-14까지 merge된 main. 브랜치 feat/netlab-chest. 새 맵 L_NetLab에서 실험한다.
1) ADuskNetChest: bReplicates=true. uint8 LidStage(0 닫힘, 1 반열림, 2 열림, ReplicatedUsing=OnRep_LidStage). 서버만 값을 올리고 OnRep에서 뚜껑 각도를 0°/45°/110°로 맞춘다. 리슨 서버 호스트 화면에서도 맞아야 한다.
2) 플레이어가 F를 누를 때마다 ADuskCharacter의 Server RPC(ServerPryChest)를 거쳐 서버가 단계를 올린다(P3-12 사용 시스템을 거쳐도, 새 입력을 만들어도 된다). 캐릭터에 int32 GoldPouch를 COND_OwnerOnly로 복제하고, 상자가 완전히 열릴 때 연 사람에게만 +50 한다. 서버는 Client RPC(ClientShowLoot)로 그 플레이어에게만 '+50'을 띄우고, NetMulticast(Unreliable)로 모두에게 반짝임 효과 또는 화면 메시지를 보여 준다.
3) Number of Players=2, Play As Listen Server, 네트워크 에뮬레이션(지연 150ms, 손실 5%)으로 검증한다. 영상에는 뚜껑 각도가 두 창에서 같이 바뀌고, '+50'이 연 사람 창에만 뜨는 장면이 나와야 한다.
4) PR 본문에 RPC 3종과 OnRep이 각각 어느 머신에서 실행되는지 표로 적는다.
제출: PR(무엇·왜, 테스트, 실행 위치 표, 설정 화면 캡처 2장, 2창 나란히 30초 이내 mp4 또는 GIF) → Squash merge.

> **블록3 (240분 · 권장 합 200분)** — 본인 포트폴리오 저장소 사본: Git 사고 · 셀프 리뷰 · 테스트·치트 · 프로파일링 · 패키징 · TS

### P3-41 (0.85점)

[3부-L 라이브·블록3·B형] Git 사고 대응 (권장 25분, 채점자 진행)
블록3은 내 포트폴리오 저장소 사본에서 한다(채점자가 시험용 원격 저장소에 올려 시험 PC에 Clone해 둠). GitHub Desktop만 쓴다(명령어 없이). 상황마다 '상황 · 한 일 · 화면 캡처'를 메모한다. 메모·캡처는 ⑤ 전까지 저장소 밖 C:\ExamNotes에 둔다.
① 채점자가 '지금 무슨 브랜치에서 무엇이 바뀌어 있나' 묻는다. 아무 버튼도 누르지 않는다(Fetch도). 위쪽 Current Repository·Current Branch가 보이게 Changes 탭과 History 탭을 한 장씩 캡처하고, 지금 브랜치·바뀐 파일·Push 안 한 커밋을 적은 질문 글 1개를 쓴다. 끝나면 채점자가 상태를 정리한다.
② 로컬 main에서 TESTING.md 첫 줄을 '# 테스트 안내 — 블록3 갱신'으로 바꾸고, 캐릭터 스탯 DataAsset(W8)의 MaxHealth를 150으로 바꿔 저장한다. 에디터를 닫고 커밋·Push한다. 안 되면 해결한다. 충돌이 나면 TESTING.md는 채점자 줄을 첫 줄로 남기고 내 문구 '블록3 갱신'은 둘째 줄로 옮긴다. DataAsset은 GitHub 쪽(origin) 파일을 고른다.
③ 채점자가 main을 체크아웃한 상태에서 '공통 캐릭터 베이스 클래스(W10 AArenaCharacterBase 또는 같은 역할) 헤더의 클래스 선언 위에 한 줄 설명 주석 달기'를 지시한다. 커밋 전에 main인 것을 알아채고 새 브랜치로 옮긴 뒤 커밋 → PR → Squash merge → main에서 Pull origin.
④ 채점자가 .gitignore에 손을 대 두었다. Changes에 Binaries·Intermediate가 보이면 대응한다.
⑤ 메모·캡처를 docs/exam/으로 옮기고 git-incidents.md를 main에 커밋한다. (가) 프로젝트 최상위의 memo.txt까지 체크해 커밋한 뒤, 그 커밋을 취소하고 md만 다시 커밋한다. (나) md 끝에 '이미 Push한 커밋이라면 어떻게 하고 왜 그런지' 한 줄을 더해 커밋하면서 메시지에 오타를 내고, Push 전에 바로잡는다. 끝나면 Push origin.
제출: git-incidents.md(main 직접 커밋·Push), ③의 PR(무엇·왜, 테스트).

### P3-33 (0.85점)

[3부-L 라이브·블록3·B형] 셀프 리뷰 PR (권장 20분)
시작: P3-41 이후 main. 에디터는 닫고 한다. 채점자가 리뷰 범위에 결함 6개를 심어 두었다: 헤더 include 1곳, UPROPERTY 누락 1곳, 불필요한 Tick 1곳, const 누락 1곳, Build.cs 불필요 모듈 2개. 리뷰 의견 카드 6장(일부는 틀린 의견)이 있다.
리뷰 범위: HUD 위젯 C++ 부모(W9 UArenaHUDWidget)·UProjectilePoolSubsystem(W12)의 .h/.cpp와 <내 모듈>.Build.cs. 이름이 다르면 채점자가 시작 때 같은 역할 파일을 알려 준다.
1) refactor/self-review 브랜치에서 결함을 찾아 고친다. 헤더 include는 전방 선언으로 바꾸고 include는 실제로 쓰는 .cpp로 옮긴다. 고친 곳마다 PR에 파일·줄·이유를 적는다.
2) Build.cs에서 쓰지 않는 모듈을 지운다. 지운 모듈마다 '안 쓴다'를 어떻게 확인했는지(검색어·결과)를 적고, 채점자가 고른 남긴 모듈 1개의 쓰는 곳(파일 하나)을 적는다. VS에서 빌드가 통과해야 한다.
3) PR에 카드 6장마다 채택/거절과 이유를 한 줄씩 남긴다.
4) PR 셀프 체크 '모든 줄을 설명할 수 있다'를 채운다. 채점자가 diff에서 고른 2줄을 1분 안에 설명한다. 엔진 소스(F12)로 확인한 내용 1개를 docs/exam/til-block3.md에 내 말로 적는다(같은 PR에 넣어도 된다).
제출: refactor/self-review PR(무엇·왜, 테스트) → Squash merge.

### P3-31 (1.27점)

[3부-L 라이브·블록3·B형] 자동화 테스트와 치트 (권장 35분)
시작: P3-33 merge 후 main. 채점자가 테스트로 잡아야 할 결함 2개(데미지 계산 1개, 무기 데이터 1개)를 심어 두었다. 기존 테스트를 보여 주는 과제가 아니다. 결함을 찾고, 새 테스트와 새 치트를 더한다.
1) test/automation 브랜치를 만든다. Tools → Session Frontend → Automation 탭(또는 Tools → Test Automation)에서 내 테스트 전체를 실행하고 결과를 캡처한다.
2) 실패한 테스트마다 원인을 찾아 고친다. 기존 테스트가 못 잡는 결함은 테스트나 검증 규칙을 먼저 더해 실패를 확인한 뒤 고친다.
3) 새 테스트 <내 접두사>.Damage.CritOnce를 IMPLEMENT_SIMPLE_AUTOMATION_TEST로 쓴다. 월드·액터 없이 내 데미지 함수만 불러, 같은 기본 데미지·방어력에서 크리티컬 결과가 내 공식대로 배율을 한 번만 적용한 값인지 두 경우(나누어떨어지는 값, 반올림·하한 경계 값)로 본다. 기대값은 내 공식으로 손으로 계산한다. PR에 게임 코드가 이 함수를 부르는 곳(파일·함수)을 1줄 적는다.
4) 웨이브 DataTable(W12)·무기 DataAsset(W8) 검증 테스트가 실제 에셋을 통과시키는지 결과로 보인다.
5) 내 치트 매니저(W19)에 새 Exec 치트 RefillHealth를 더한다. 적에게 맞아 체력을 줄인 뒤 실행하면 모든 플레이어의 체력·스태미나가 최대로 차고 HUD가 바로 바뀌어야 한다(PIE 1인). 기존 God·SkipWave·SpawnEnemy 5도 한 번씩 실행한다.
6) 전부 통과한 결과를 캡처하고 TESTING.md(테스트 목록·실행 방법·캡처)를 고친다. 블록3에서 찾았지만 못 고친 버그는 README Known Issues에 적는다(없으면 '없음').
제출: test/automation PR(무엇·왜, 테스트, 치트 시연 캡처나 짧은 영상) → Squash merge.

### P3-32 (1.27점)

[3부-L 라이브·블록3·B형] 프로파일링 (권장 35분)
시작: P3-31 merge 후 main. 채점자가 게임 스레드 비용을 키우는 결함 1개를 심어 두었다.
1) 노트북이면 전원을 연결하고, Windows 전원 모드를 '최고 성능'으로 둔다(캡처). 내 스트레스 맵(W18)에서 내 치트로 적 50 → 100마리와 투사체 100발을 바로 소환한다.
2) stat unit·stat fps·stat game을 켜고 캡처한다. Game·Draw·GPU 중 무엇이 병목인지와 근거를 적는다. 2인 PIE(Listen Server)로 한 번 더 실행해 stat net 캡처 1장을 남긴다.
3) Unreal Insights로 CPU 트레이스를 기록한다(화면 오른쪽 아래 Trace 메뉴 또는 Tools → Run Unreal Insights). W18에 넣은 내 스코프(웨이브 매니저·판정·AI 서비스 중) 1개 이상이 보이는 타임라인을 캡처하고, 게임 스레드 비용 상위 3개를 표(이름·ms)로 적는다. 액터 이름이 안 보이면 기록 전에 콘솔에 stat namedevents를 입력한다(확인 필요).
4) perf/<병목-이름> 브랜치에서, 원인으로 의심되는 함수에 TRACE_CPUPROFILER_EVENT_SCOPE와 SCOPE_CYCLE_COUNTER(내 stat 그룹)를 새로 넣고 stat <내 그룹>으로 확인한다. 심어진 결함을 짚는다.
5) 고치기 전과 후를 같은 조건(적 100·투사체 100, 같은 위치·카메라)에서 Game ms를 3번씩 읽어(PIE를 다시 시작하거나 같은 세션에서 10초 간격) 중간값을 PR 표에 적는다. docs/perf/02-performance-report.md에 '시험 블록3' 절(측정 환경·전후 표·배운 점 1줄)을 더한다.
제출: perf/<병목-이름> PR(무엇·왜, 테스트) → Squash merge.

### P3-34 (1.27점)

[3부-L 라이브·블록3·B형] Windows 패키징 (권장 40분, 패키징을 기다리는 동안 이 문항의 문서 작업 허용)
시작: P3-32 merge 후 main. 채점자가 패키징 결함 2개(쿠킹 때만 드러나는 것 1개, 시작 설정 1개)를 심어 두었다.
1) build/win-shipping 브랜치에서 Project Settings → Maps & Modes의 Game Default Map·Editor Startup Map·Default GameMode가 내 설계(README·원래 의도)와 맞는지 확인한다. 틀린 값은 고치고 전후를 캡처한다.
2) Platforms → Windows → Package Project에서 Binary Configuration을 Shipping으로 두고 Shipping 패키징부터 한다. 실패하면 Output Log에서 첫 Error 줄(쿠킹)을 찾아 원문·원인을 적고 고친 뒤 다시 패키징한다.
3) Binary Configuration을 Development로 바꿔 패키징한다. 기다리는 동안 Shipping 결과를 C:\ExamRun\B\Game으로 복사해 에디터 없이 10분 플레이한다. 의도한 맵으로 시작하는지 본다.
4) Development 빌드를 3분 이상 실행하고 실행 폴더의 <프로젝트 이름>\Saved\Logs에서 Error 줄이 0인지(남으면 원인) 확인한다. Shipping의 Saved는 보통 %LOCALAPPDATA%\<프로젝트 이름>\Saved에 생긴다(없으면 실행 폴더 쪽도 확인). 그 Saved\Crashes가 비었는지 확인한다.
제출: build/win-shipping PR(에러 줄 원문, 원인, 수정, Maps & Modes 전후, 로그·크래시 폴더 캡처(경로가 보이게), 실행 폴더 캡처) → Squash merge.

### P3-36 (1.69점)

[3부-L 라이브·블록3·B형] 트러블슈팅 2건 (권장 45분)
시작: P3-34 merge 후 main. 채점자가 버그 제보 카드 2장(채점자가 심은 런타임 결함)을 준다. 둘 다 재현해 원인을 찾아 고치고, TS 2건을 docs/troubleshooting/에 쓴다(번호는 내 TS 번호를 이어서, TS-0NN-<증상>.md).
- 카드 1(네트워크): '2인 PIE(Listen Server)에서 클라 플레이어만 대시·공격이 안 되고 체력바가 바뀌지 않는다. 서버 플레이어는 정상이다.' 근거: NetMode가 찍힌 로그 + (클라 쪽 중단점 콜스택 또는 클라 창의 showdebug abilitysystem 캡처).
- 카드 2(판정): '적의 한 번 공격에 플레이어 체력이 2~3번 깎인다.' 근거: DrawDebug 캡처와 프레임별 히트 로그. 가설 표에 'BT가 공격을 두 번 실행한다' 1행을 넣고 Visual Logger로 확인한 결과(캡처)를 적는다.
- fix/block3-bugs 브랜치 하나에 두 수정, TS 2건, TIL을 넣고 PR(무엇·왜, 테스트) → Squash merge.
- 진단하면서 docs/exam/til-block3.md에 '문제 → 해결'을 한두 줄 먼저 적고 TS로 옮긴다. TS에는 그 TIL 줄 링크를, TIL에는 TS 링크를 단다.
- 두 TS 모두 부록 템플릿 7칸을 채운다(칸마다 1~3줄이면 된다): 증상, 재현 단계, 가설과 검증 표(3행 이상, 기각한 가설 포함), 원인과 근거, 해결(diff 요약·PR 번호), 재발 방지(테스트·체크리스트·규칙), 면접 30초 버전.
- 도달성: 두 버그는 GC와 무관하다. 카드 2 TS 끝에 '부록: UPROPERTY 없는 UObject 포인터 멤버가 왜 위험한가'를 도달성으로 3줄 쓴다(P3-33에서 고친 멤버를 예로, 못 했으면 아무 예).
- 카드마다 15분이 지나도 원인을 못 찾으면 힌트 카드(원인 파일 이름)를 받을 수 있다. 받으면 그 TS 행 점수가 절반이 된다.
- 끝나면 채점자 앞에서 TS 1건의 30초 버전을 말한다.
제출: fix/block3-bugs PR.

## 3부-P 포트폴리오 심사 (33.1점 · 시험 전 제출 + 구술 40분)

- 시험 7일 전, 게임 저장소 UE5-ActionArena(태그 exam-submit)와 학습 로그 저장소 unreal-study-log 링크를 낸다. 채점자는 시험 전에 이슈·PR·커밋 이력, docs, README, 릴리즈, GIF·영상, Shipping zip을 심사한다.
- 아래 항목은 미리 공개하는 심사 기준이다(A·B형 공통). 클래스·파일 이름은 커리큘럼 이름 기준이며, 같은 역할이면 이름이 달라도 인정한다.
- 진위 규칙: 구술(P3-42)에서 채점자가 심사 항목 3개를 골라 핵심 코드·결정을 설명하게 한다. 설명하지 못한 항목은 그 항목 점수의 50%만 인정한다. 커리큘럼 AI 레벨 안의 AI 활용은 감점하지 않는다. PR 'AI 활용' 칸이 사실과 달라 보이면 그 항목을 구술 후보로 먼저 고른다.

### P3-03 (0.42점)

[3부-P 포트폴리오 심사] 학습 로그 Clone과 작업 관리 도구 (W00·W01 과제, 매주 이슈 정리)
준비할 곳: unreal-study-log 커밋 이력, UE5-ActionArena의 Labels·Milestones·Projects·Issues·PR.
1) unreal-study-log: W00에 C:\Projects로 Clone한 뒤 GitHub Desktop으로 올린 첫 커밋과, 그 뒤 매일 올린 TIL 커밋. HTML 카드로 만든 기록은 형식을 그대로 둔다.
2) 게임 저장소: 라벨 feat·bug·docs·perf, Projects의 Board 1개.
3) Milestones M1~M6: 마감일 = 각 단계 마지막 주(W04·W08·W12·W16·W20·W24)의 일요일. 버퍼 주를 써서 옮겼다면 회고나 Devlog에 한 줄 적어 둔다.
4) W01 PR: 모두 이슈와 M1 마일스톤이 연결되어 있다(W01 'PR 흐름 점검'에서 머지 뒤 채운 것도 된다). 그 뒤 기능 PR: 본문 Closes #N으로 머지 때 이슈가 닫히고, PR이나 그 이슈에 그 단계 마일스톤이 있다.
5) 매주 끝난 이슈를 닫고 다음 주 과제를 이슈로 만들어 마일스톤을 지정한다. 끝난 단계 마일스톤은 닫는다. 제출 시점에 열린 이슈는 Known Issues 버그나 남은 할 일뿐이어야 한다.
커리큘럼과 이름이 달라도 같은 역할이면 인정한다. 제출일 뒤에 만들거나 고친 이슈·PR은 보지 않는다.

### P3-04 (1.27점)

[3부-P 포트폴리오 심사] 브랜치·커밋 규칙과 기록 리듬 (W01 과제, 이후 모든 과제)
준비할 곳: UE5-ActionArena의 머지된 PR(Commits 탭 포함)과 main 이력, unreal-study-log의 ue5-til 이력.
1) 기능 브랜치 이름은 'type/기능'(feat·fix·refactor·perf·test·docs·chore). 주차 'Git 기록'의 이름(예: feat/floating-item, build/win-shipping)이나 HTML 카드 기본 이름(예: feat/w05-t1)도 인정.
2) 커밋 메시지는 '<type>(<scope>): 무엇을, 왜'. HTML 카드 기본 메시지(예: feat(core): …)도 된다. PR의 Commits 탭 기록을 지우거나 이력을 다시 쓰지 않는다.
3) 새 브랜치는 main을 Fetch origin → Pull origin으로 최신화한 뒤 만들고, 첫 Push는 Publish branch.
4) 코드(Source·Content·Config)는 main에 직접 커밋하지 않는다. W01 첫 프로젝트 커밋만 예외.
5) TIL은 학습일마다 unreal-study-log main에, Devlog(docs/devlog/WNN.md)는 그 주에 게임 저장소 main에 올린다. 보충으로 며칠 늦은 것은 괜찮다.

### P3-05 (1.69점)

[3부-P 포트폴리오 심사] PR 작업 보고서 (W01 과제, 이후 모든 기능 PR)
준비할 곳: UE5-ActionArena의 머지된 PR. 채점자가 기능 PR 8개를 고른다: W01 AFloatingItem, W04 캐릭터·입력, W07 콤보, W08 데이터·데미지, W10~W12 AI나 웨이브 1개, W15 2인 협동, W17 GAS 전환, W20 게임필(같은 역할의 다른 PR도 된다).
1) 본문: 무엇을/왜(관련 이슈), 변경 사항, 테스트 방법(번호 붙인 재현 단계, W14부터 'PIE 2인 Listen Server + 지연 200ms' 체크), 스크린샷/GIF, AI 활용 내역, 셀프 리뷰 체크. HTML 카드가 만든 본문 형식도 인정.
2) 화면이 바뀌는 기능 PR에는 GIF나 .mp4를 본문에 넣는다.
3) AI 활용 내역: 사용 범위, 내가 검증·수정한 것, AI가 틀렸던 것(L2부터는 AI 리뷰 의견의 채택/거절 이유). 그 주 AI 레벨 안의 사용은 감점하지 않고, 사실대로 적었는지만 본다.
4) Files changed의 코드 줄에 '왜 이렇게 했는지' 셀프 코멘트.
5) Squash and merge → Confirm squash and merge → Delete branch.
6) '혼자인데 왜 브랜치·PR을 거치나'를 W01 TIL·Devlog·PR에 적어 두거나 구술에서 답한다.

### P3-08 (0.85점)

[3부-P 포트폴리오 심사] 떠다니기 컴포넌트와 Tick 관리 (W03 과제3)
저장소 UE5-ActionArena(태그 exam-submit). 이름이 달라도 같은 역할이면 인정한다.
1) 코드: W1 AFloatingItem의 떠다니기 로직을 옮긴 UFloatMotionComponent(.h/.cpp). AFloatingItem에는 떠다니기 Tick 코드가 없고 bCanEverTick은 false다.
2) 재사용: 컴포넌트는 GetOwner()만 쓰고 소유 액터 클래스를 모른다. AFloatingItem이 아닌 다른 액터에서도 동작하는 모습을 W03 PR GIF나 다른 BP·맵 배치로 보인다.
3) Tick: 컴포넌트 Tick은 기본으로 꺼져 있고, 켜고 끄는 경로(함수나 옵션)가 코드에 있다.
4) PR: W03 refactor/float-motion-component PR(또는 Devlog W03)에 동작 GIF와 '테스트 방법'. 테스트 방법에는 Tick이 필요할 때만 도는지 확인한 방법(중단점·로그 등)을 적는다.
5) 설명: Tick 비용을 줄이는 방법 4가지와 저장소에서 쓴 곳(예: W05 상호작용 0.1초 타이머)을 PR 본문·TIL·Devlog W03·ADR-0001·코드 주석 중 한 곳에 적어 둔다.
6) 구술(P3-42)에서 이 항목이 뽑히면 Tick이 켜지는 줄을 짚어 설명한다.

### P3-11 (1.27점)

[3부-P 포트폴리오 심사] C++ AnimInstance 로코모션 (W06 과제1·2)
저장소 UE5-ActionArena(태그 exam-submit). 클래스·에셋 이름은 같은 역할이면 달라도 된다.
1) 코드: UArenaAnimInstance(.h/.cpp). Speed·Direction·bIsInAir·bIsAccelerating을 갱신한다. Character·CMC 포인터는 초기화 때 TryGetPawnOwner로 얻어 캐싱한다.
2) 에셋: 부모가 UArenaAnimInstance인 AnimBP를 플레이어 메시가 쓴다. AnimGraph에 로코모션 블렌드스페이스와 점프 상태 머신이 있다. 이벤트 그래프에는 매 프레임 Cast가 없다.
3) PR: W06 feat/anim-instance PR(또는 Devlog W06)에 걷기→달리기→점프→착지가 이어지는 GIF. ABP 캡처(부모 클래스·AnimGraph)가 있으면 확인이 빠르다.
4) 실행: Release에 첨부한 Shipping zip에서도 같은 동작이 보이면 GIF 대신 인정한다.
5) 외부 애니메이션 에셋을 저장소에서 뺐다면 README에 받는 방법이 있어야 채점자가 ABP를 열 수 있다.
6) 구술(P3-42)에서 뽑히면 NativeInitializeAnimation·NativeUpdateAnimation을 줄 단위로 설명한다.

### P3-13 (1.27점)

[3부-P 포트폴리오 심사] 인터페이스 상호작용과 레버 델리게이트 (W05 과제1~3)
저장소 UE5-ActionArena(태그 exam-submit). 클래스 이름은 같은 역할이면 달라도 된다.
1) 코드: IInteractable(Interact·GetInteractionText, BlueprintNativeEvent)과 이를 구현한 대상 3종(문 열림/닫힘·아이템 픽업·레버). 대상은 C++이나 BP 어느 쪽으로 구현해도 된다.
2) 레버: 레버 코드(.h/.cpp 또는 BP 그래프)는 문 클래스를 include하거나 언급하지 않고 델리게이트를 방송한다. 레버 1개에 문 2개가 연결된 맵(테스트 맵도 된다).
3) 0줄 구조: UInteractionComponent는 인터페이스만 안다. 대상을 추가한 PR(커밋)의 Files changed에 컴포넌트 파일이 없어야 한다. 그런 PR이 없으면 PR 본문이나 Devlog W05에 '새 대상을 추가해도 컴포넌트 수정 0줄'을 확인한 기록을 남긴다.
4) GIF: W05 feat/interaction-system PR 또는 Devlog W05에 대상 3종이 동작하는 모습과, 레버 1개로 문 2개가 열고 닫히는 모습. 레버·문 2개가 있는 맵 이름을 PR 본문에 적어 두면 채점자가 에디터로도 확인할 수 있다.
5) 구술(P3-42)에서 뽑히면 레버 → 문 연결에서 누가 누구를 아는지 설명한다.

### P3-15 (1.27점)

[3부-P 포트폴리오 심사] 이벤트 기반 HUD와 UI 애니메이션 (W09 과제1·2, W20)
저장소 UE5-ActionArena(태그 exam-submit). 클래스 이름은 같은 역할이면 달라도 된다.
1) 코드: C++ 부모 UArenaHUDWidget. meta=(BindWidget)으로 체력 바·스태미나 바·상호작용 프롬프트를 연결하고, 레이아웃 WBP의 부모가 이 클래스다.
2) 소유자: PlayerController 또는 AHUD가 위젯을 생성하고, 화면에 추가하고, UPROPERTY로 보관한다(2인 플레이에서는 로컬 PC에서만 만든다).
3) 갱신: 체력·스태미나·프롬프트(W5 OnFocusChanged)가 모두 델리게이트로 갱신된다. W15 OnRep이나 W16·W17 GAS 속성 변경 델리게이트로 바뀌었어도 된다. 바뀌는 모습은 W09 feat/hud PR GIF(체력·프롬프트)와 이후 PR GIF·Shipping zip(스태미나는 W16 대시 이후)으로 보인다.
4) 금지: HUD 위젯(레이아웃 WBP, C++ 부모, HUD 안 자식 위젯)에 NativeTick, 연결된 Event Tick, Property Binding이 하나도 없다.
5) UI 애니메이션: UMG 애니메이션 1개 이상이 이벤트로 재생된다(예: 피격 시 체력 바 번쩍임). 어느 위젯이든 된다. W20 feat/game-feel PR, v0.5.0 전/후 GIF, Shipping zip 중 한 곳에서 재생이 보이면 된다(없으면 채점자가 에디터 Play로 본다).
6) 구술(P3-42)에서 뽑히면 체력이 줄 때 바가 바뀌기까지의 호출 흐름을 설명한다.

### P3-16 (1.69점)

[3부-P 포트폴리오 심사] 3단 콤보와 입력 윈도우 (W07·W20 과제)
1) W07 콤보 PR(커리큘럼 브랜치 feat/combo-system): UCombatComponent의 몽타주 섹션 기반 3단 콤보. 입력 윈도우 안 입력만 다음 섹션으로 예약하고, 몽타주가 끝나거나 끊기면 상태를 초기화.
2) C++ UAnimNotifyState_ComboWindow·UAnimNotifyState_HitWindow: NotifyBegin/End에서 윈도우·판정을 켜고 끔(feat/weapon-sweep PR에 있어도 됨).
3) '윈도우 밖 입력은 무시된다' 확인 기록: 재현 단계와 결과를 PR '테스트 방법', TS-002, docs/devlog/W07.md 중 한 곳에 + 콤보 GIF(또는 영상).
4) W20 콤보 윈도우 조정: 무엇을 얼마나 바꿨는지(전/후 값이나 노티파이 위치)와 이유(플레이테스트 피드백 등)를 W20 PR, docs/devlog/W20.md, v0.5.0 릴리즈 노트, docs/retro/M5.md 중 한 곳에.
- exam-submit 태그 기준. 이름이 달라도 같은 역할이면 인정. W17에서 GAS로 옮겨 지금 코드가 달라도 W07 PR을 근거로 본다.

### P3-17 (1.69점)

[3부-P 포트폴리오 심사] 무기 Sweep 판정 (W07 과제)
1) W07 판정 PR(커리큘럼 브랜치 feat/weapon-sweep): 무기 소켓 2개(시작/끝)의 이전 프레임 위치 → 현재 위치를 이은 Sweep 코드.
2) 같은 코드에 TSet으로 스윙당 대상별 1회 타격, DrawDebug로 판정 경로·히트 지점 표시.
3) 커스텀 콜리전 채널 'Weapon'(프리셋을 만들었다면 프리셋도)을 추가한 PR: Files changed에 Config/DefaultEngine.ini 변경이 보일 것.
4) 30FPS 판정 검증 영상: t.MaxFPS 30 상태(stat fps 화면이나 본문의 측정 조건)에서 디버그 드로잉을 켜고 누락이 없음을 보인다. PR·docs/devlog/W07.md·v0.2.0 릴리즈 중 한 곳에 링크.
- exam-submit 태그 기준. 이름이 달라도 같은 역할이면 인정. W15·W17에서 서버 판정·GAS로 옮겼어도 W07 PR을 근거로 본다.

### P3-18 (0.85점)

[3부-P 포트폴리오 심사] 방향 판정과 피격 리액션 (W04·W11 과제)
1) W04 방향 판정 PR(커리큘럼 브랜치 feat/direction-debug): 방향 판정 디버그 액터. 플레이어 기준 앞/뒤(내적)·좌/우(외적)와 각도를 DrawDebugLine/DrawDebugString으로 표시.
2) W04 산출물 '방향 판정 디버그 영상'(또는 v0.1.0 릴리즈 GIF): 대상 주위를 돌 때 네 방향과 각도가 맞게 바뀌는 장면.
3) W11 피격 리액션 PR(feat/hit-reaction): W4 내적/외적 계산을 재사용해 앞/뒤/좌/우 히트 몽타주 선택, 경직·넉백.
4) 같은 PR이나 docs/devlog/W11.md에 네 방향 리액션과 경직·넉백이 보이는 GIF(또는 영상).
- exam-submit 태그 기준. 클래스·함수 이름이 달라도 같은 역할이면 인정.

### P3-19 (1.27점)

[3부-P 포트폴리오 심사] 데이터 주도 설계 (W08·W11 과제)
1) W08 데이터 PR(커리큘럼 브랜치 feat/data-assets): UCharacterStatData(MaxHealth·WalkSpeed·SprintSpeed·JumpZVelocity)를 캐릭터 초기화 때 적용하고, W4 'TODO(W8)' 주석과 스프린트 수치 상수를 없앰. PR '변경 사항'에 옮긴 수치를 적어 두면 확인이 쉽다.
2) UWeaponData(데미지 배율·콤보 몽타주·소켓 이름·판정 반경·메시)를 판정·데미지·콤보·장착 코드가 읽음. 무기 DataAsset 2종.
3) 두 번째 무기 PR(feat/second-weapon-data-only): Files changed에 .h/.cpp 0개, 새 무기 장착·타격 GIF.
4) 적 스탯 DataTable(FTableRowBase 행 구조체, CSV 임포트). CSV 수정 → 재임포트 흔적을 PR 본문, docs/devlog/W08.md, TIL, 저장소 CSV 원본의 커밋 이력 중 한 곳에.
5) W11 원거리 적 PR(feat/ranged-enemy): 원거리 적 스탯을 W8 행 구조체의 DataTable 행 추가로 정의.
- exam-submit 태그 기준. 이름이 달라도 같은 역할이면 인정.

### P3-20 (1.27점)

[3부-P 포트폴리오 심사] 소프트 레퍼런스와 비동기 로딩 (W09 과제)
1) W09 PR(커리큘럼 브랜치 perf/soft-weapon-refs): UWeaponData의 메시·몽타주를 TSoftObjectPtr로 바꾼 diff.
2) 무기 교체 코드: UAssetManager::GetStreamableManager().RequestAsyncLoad로 요청 → 완료 콜백에서 장착. 콜백 람다에는 캐릭터를 약한 포인터로 캡처하고 유효할 때만 접근.
3) 성능 노트 docs/perf/01-soft-reference.md: 캐릭터 BP의 Size Map 전/후 스크린샷과 수치(줄어든 양).
4) 참조 관계 근거: Reference Viewer 캡처나 '캐릭터 BP가 무엇을 참조하는지' 설명을 성능 노트, PR, W09 TIL 중 한 곳에.
5) 무기 교체 때 멈칫(히치)이 없음을 확인한 기록: 교체 GIF(또는 영상)와 확인 방법·결과(예: stat unit을 켜고 여러 번 교체)를 PR '테스트 방법'이나 성능 노트에.
- exam-submit 태그 기준. 이름이 달라도 같은 역할이면 인정.

### P3-21 (1.27점)

[3부-P 포트폴리오 심사] 공통 캐릭터 베이스 리팩터링 (W10 과제1)
저장소 UE5-ActionArena(태그 exam-submit). 클래스 이름은 같은 역할이면 달라도 된다.
1) 코드: AArenaCharacterBase(체력·전투 컴포넌트, 사망 처리). 플레이어(AArenaPlayerCharacter 또는 AArenaCharacter)와 AArenaEnemy가 상속하고, 다른 부분은 virtual override + Super로 나눈다. W17 이후 체력이 AttributeSet으로 옮겨졌어도 된다.
2) PR: W10 refactor/character-base PR 본문에 Before/After 클래스 다이어그램(Mermaid 또는 이미지).
3) 회귀 확인: 리팩터링 뒤 플레이어와 적이 모두 같은 경로로 피격·사망하는 모습. W10 PR '테스트 방법'·GIF, Devlog W10, Release Shipping zip(적 처치·플레이어 사망 → 게임오버) 중 한 곳에서 보이면 된다.
4) 한 곳 수정: 데미지 처리가 한 곳(HealthComponent, W17 이후엔 GE_Damage + AttributeSet)에만 있다. 그 한 곳을 고쳐 양쪽에 적용된 사례를 1개 이상 보인다. W10 PR 테스트 방법·Devlog W10의 확인 기록, 또는 W10 이후 공통 파일만 바꾼 체력·데미지 PR(예: W15 HealthComponent 복제 + OnRep, 데미지 버그 fix)이면 된다.
5) 구술(P3-42)에서 뽑히면 다이어그램을 보며 왜 수정이 한 곳에서 끝나는지 설명한다.

### P3-22 (1.69점)

[3부-P 포트폴리오 심사] 근접 적 AI — Behavior Tree와 C++ 태스크·서비스 (W10 과제)
대상: UE5-ActionArena 태그 exam-submit. 클래스·파일·브랜치 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) 코드: UBTTask_MeleeAttack, UBTService_UpdateTargetDistance(예: Source/ActionArena/AI/). W17에서 태스크가 어빌리티를 켜도록 바뀌었어도 된다.
2) 에셋: BT·BB 에셋과 NavMeshBoundsVolume이 놓인 게임 맵. 채점자가 저장소 사본을 에디터로 열어 P 키 화면, BB 키, BT 연결을 본다.
3) PR feat/melee-enemy-ai: 순찰 → 추적 → 공격 → 쿨다운 GIF. P 키 화면·BT 그래프 캡처가 PR·W10 Devlog·TIL에 있으면 함께 본다(필수 아님).
4) 문서: docs/engine-notes/04-behavior-tree.md — 내 BT 구조 그림과 노드별 역할.
5) 구술(P3-42)에서 이 항목이 뽑히면 태스크의 ExecuteTask → FinishLatentTask 흐름과 내 BT 구조를 설명한다.

### P3-23 (1.27점)

[3부-P 포트폴리오 심사] 적 Perception과 AI 디버깅 도구 (W11 과제)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) 코드: 적 AIController(또는 적)의 UAIPerceptionComponent 감각 설정(시야 + 피격), OnTargetPerceptionUpdated 처리, 피해를 줄 때의 Damage 자극 보고. Hearing은 코드에 없으면 W11 TIL에 정리한 내용으로 본다.
2) PR feat/ai-perception: W10의 '항상 플레이어 추적' 코드를 지운 diff와 감지 → 추적 → 놓침 → 순찰 복귀 GIF.
3) Gameplay Debugger(' 키) 화면: PR·TIL·디버깅 도구 노트의 캡처나 W22 시연 영상의 AI 디버거 장면 중 한 곳.
4) docs/troubleshooting/TS-003-*.md: '원인' 칸에 Visual Logger 화면 캡처를 넣고, 어느 시점에서 AI가 무엇을 판단했는지 짚어 설명한 TS.
5) 구술(P3-42)에서 이 항목이 뽑히면 감지·상실 처리 코드와 TS-003에서 Visual Logger로 원인을 찾은 과정을 설명한다.

### P3-24 (1.27점)

[3부-P 포트폴리오 심사] 한 판짜리 게임 루프 — 웨이브·메뉴·세이브 (W12 과제)
대상: UE5-ActionArena 태그 exam-submit과 Release의 Shipping zip. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) 코드: enum class EArenaPhase(Waiting/InWave/Break/GameOver), GameMode의 단계 전환, GameState의 단계·웨이브·남은 적 값.
2) 웨이브 행 구조체(적 종류·수·간격)와 DataTable 에셋, 그 표를 읽어 적을 만드는 스포너. 표 값은 PR 캡처가 있으면 그것으로, 없으면 채점자가 에디터에서 연다.
3) USaveGame 자식(최고 웨이브)과 저장·불러오기 코드, 메인 메뉴·일시정지·게임오버 위젯, OpenLevel 전환.
4) PR feat/wave-system·feat/menu-savegame의 GIF와 테스트 칸, W12 Devlog 목표 vs 결과 표, v0.3.0 90초 영상 중 한 곳에 '메뉴 → 게임 → 게임오버 → 메뉴 3회 연속, 재실행 후 기록 유지' 결과.
5) Shipping zip: 채점자가 최신 Release zip을 풀어 혼자 한 판 하고 다시 실행해 기록을 본다. 최신 빌드를 혼자 시작할 수 없으면 v0.3.0 zip으로 본다.
6) 구술(P3-42)에서 이 항목이 뽑히면 GameMode/GameState 분리 이유와 최고 기록을 불러와 저장하는 순서를 설명한다.

### P3-26 (1.69점)

[3부-P 포트폴리오 심사] 싱글 → 2인 협동 전환 (W15 과제, W14·W17 기록 포함)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다. W17에서 GAS로 바꾼 코드는 W15 PR diff로 확인한다.
1) PR feat/coop-combat: 입력 → ServerAttack(Server RPC) → 서버 판정·데미지 → 피격 연출 Multicast(Unreliable).
2) PR feat/replicated-health: HealthComponent 복제, OnRep → 델리게이트 → W9 HUD(위젯 구조 재사용).
3) PR feat/replicated-waves와 리스폰 PR: 스폰·AI·웨이브 서버 전용, GameState 웨이브·남은 적 복제 → 양쪽 HUD, 사망 → 리스폰(또는 관전), 리스폰 뒤 HUD가 보이는 GIF.
4) W14 이후 네트워크 PR: 테스트 칸 'PIE 2인 Listen Server + 지연 200ms'와 셀프 체크 '서버/클라 실행 위치 확인' 체크, 코드 주석이나 PR 본문의 실행 위치 표시.
5) 영상·기록: 지연 200ms 2인 상태 일치 영상(W15), 10분 연속 무버그 기록(영상, 또는 W17 Devlog·v0.4.0 릴리즈 노트의 조건·시간·결과), README의 RPC vs GAS 반응성 비교 영상.
6) 구술(P3-42)에서 이 항목이 뽑히면 클라이언트 공격이 어느 머신에서 어떤 순서로 실행되는지와 호스트 HUD 갱신 방법을 설명한다.

### P3-27 (1.69점)

[3부-P 포트폴리오 심사] GAS 세팅 — ASC·AttributeSet·태그 문서·ADR-0005 (W16 과제)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) .uproject의 GameplayAbilities 플러그인 켬, 게임 모듈 .Build.cs의 GameplayAbilities·GameplayTags·GameplayTasks 의존성.
2) UArenaAbilitySystemComponent와 배치: 플레이어는 PlayerState, 적은 Character. 서버·클라 초기화(InitAbilityActorInfo) 코드.
3) IAbilitySystemInterface 구현: 적과 플레이어 쪽(PlayerState나 플레이어 캐릭터)이 ASC를 돌려준다.
4) UArenaAttributeSet: Health·MaxHealth·Stamina·MaxStamina와 메타 속성 IncomingDamage, 범위 제한(Clamp), IncomingDamage → Health 반영.
5) docs/gas-tags.md: State.*·Ability.*·Event.*·Cooldown.* 계층과 태그별 용도.
6) docs/adr/ADR-0005-asc-location.md와 PR feat/gas-setup(무엇·왜, 테스트, AI 활용).
7) 구술(P3-42)에서 이 항목이 뽑히면 ASC 위치와 초기화 시점, IncomingDamage 처리를 설명한다.

### P3-28 (1.69점)

[3부-P 포트폴리오 심사] GameplayEffect 4종과 첫 어빌리티 GA_Dash (W16 과제)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) GE 4종: GE_Damage(Instant, SetByCaller), GE_StaminaRegen(Infinite·Periodic), GE_Dash_Cost, GE_Dash_Cooldown. BP 에셋이면 채점자가 에디터에서 설정을 연다. PR에 설정 캡처가 있으면 그것으로 본다(필수 아님).
2) GE_Damage에 SetByCaller로 데미지 값을 넣는 코드, GE_StaminaRegen을 시작할 때 적용하는 코드.
3) GA_Dash(C++ 또는 BP): CommitAbility로 비용·쿨다운 적용, 공격 중 태그가 있으면 발동 차단, 그 태그를 붙이는 곳.
4) PR feat/ga-dash: 테스트 칸 'PIE 2인 Listen Server + 지연 200ms' 체크와, 2인 PIE에서 클라이언트 쪽 플레이어의 대시 → 스태미나 감소 → 쿨다운 중 재사용 불가가 보이는 GIF(PR 대신 W16 Devlog에 있어도 된다. showdebug abilitysystem 화면이 있으면 확인이 쉽다).
5) 구술(P3-42)에서 이 항목이 뽑히면 CommitAbility가 하는 일과 GE 종류(Instant·Infinite·Periodic)의 차이를 설명한다.

### P3-29 (1.69점)

[3부-P 포트폴리오 심사] GAS 근접 콤보와 속성 기반 HUD (W17 과제1·2)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) GA_MeleeCombo(C++ 또는 BP, BP면 그래프 캡처를 PR에): PlayMontageAndWait의 완료·블렌드아웃·중단 → EndAbility, WaitGameplayEvent(Event.Montage.Hit), LocalPredicted 설정.
2) 타격 시점을 보내는 AnimNotify(SendGameplayEventToActor). 판정은 W7 UCombatComponent 함수를 다시 쓰고, GE_Damage는 SetByCaller로 값을 넣어 서버에서 적용한다. 서버에서만 들어가는 이유를 주석이나 PR·Devlog에 한 줄 적어 두면 좋다.
3) State.Dead 태그를 붙이는 코드와, 이 태그로 사망을 판단해 처리하는 코드(입력·어빌리티 차단, AI 정지 등).
4) HUD(W9 UArenaHUDWidget)는 GetGameplayAttributeValueChangeDelegate로 갱신하고, 위젯 표시 함수와 WBP는 W9 그대로 둔다.
5) PR refactor/combat-to-gas와, 지연 200ms에서 W15(RPC) vs W17(GAS 예측) 반응성 비교 영상(README 핵심 섹션).
6) README 핵심 구현 표에서 위 파일로 링크해 두면 확인이 빠르다.

### P3-30 (0.85점)

[3부-P 포트폴리오 심사] 타격감 연출·GameplayCue·외부 에셋 관리 (W17 과제3 · W20 과제1·2)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) 코드: 히트스톱(CustomTimeDilation), 카메라 셰이크(UCameraShakeBase 자식과 재생 호출), 피격 플래시(머티리얼 파라미터).
2) 세 연출의 강도를 담은 DataAsset 클래스와 에셋. 연출 코드에는 강도 숫자를 두지 않는다.
3) PR feat/gameplay-cues(W17): 피격·사망 연출을 GameplayCue로 옮긴 diff. W20에서 Cue에 Niagara와 Sound Cue(또는 MetaSound)를 연결한다. Cue 설정 캡처가 PR에 있으면 확인이 빠르다.
4) PR feat/game-feel(W20): 무엇·왜, 테스트, 연출 GIF·mp4.
5) 외부 에셋: 원본 폴더(예: Content/ThirdParty/)를 .gitignore에 넣고, README '개발 환경 · 빌드'에 받는 방법(출처 링크)을 적는다. 라이선스 종류는 README·PR·Devlog·TIL 중 한 곳에 적는다.
6) 연출과 소리는 W20 이후 Shipping zip이나 v1.0.0 시연 영상에서 확인한다.

### P3-35 (0.85점)

[3부-P 포트폴리오 심사] 플레이테스트와 버그 관리 (W13·W19·W20 과제)
준비할 곳: UE5-ActionArena의 Issues·PR·README, docs/devlog/W13·W19·W20.md, 최신 릴리즈의 Shipping zip.
1) W13 1차 플레이테스트: 지인 3명의 관찰·피드백을 이슈로 등록하고(테스터 A·B·C처럼 구분) 우선순위 라벨을 붙인다(라벨 이름은 자유).
2) 버그 이슈: 심각도(라벨이나 본문)와 번호 붙인 재현 단계.
3) W19: 제출 시점 열린 bug 이슈 0개가 목표. 못 고친 것은 README Known Issues에 증상을 적는다.
4) W20 2차 플레이테스트(3명 이상): 피드백 기록(이슈, Devlog, PR 본문 중 한 곳 이상)과 그것을 반영한 PR.
5) 타격감 질문 결과(3명 중 몇 명이 '있다')를 W20 Devlog·M5 회고·반영 PR 중 한 곳에 적는다. 미달이면 원인과 개선도 적는다.
채점자는 Shipping zip을 실행해 반영 내용 1건과 Known Issues 1건을 직접 본다.

### P3-37 (0.85점)

[3부-P 포트폴리오 심사] ADR-0001 상호작용 감지와 성능 리포트 (W05 과제5 · W18 과제4)
대상: UE5-ActionArena 태그 exam-submit. 이름은 커리큘럼 기준이고, 같은 역할이면 다른 이름도 인정한다.
1) docs/adr/ADR-0001-interaction-detection.md: 부록 ADR 템플릿 칸(상태·날짜·맥락·선택지 표·결정과 이유·결과).
2) 선택지 표에 Tick·타이머·Overlap 3개의 장점·단점. 결정은 실제 UInteractionComponent 구현과 같아야 한다. 나중에 구현이 바뀌었으면 상태나 결과 칸에 적는다.
3) '결과'에 좋아진 점·감수한 비용·다시 볼 조건.
4) docs/perf/02-performance-report.md: 측정 환경(기기·설정·반복 횟수), 측정 스크린샷(stat unit·Insights 등), 개선 3건의 전/후 표, 배운 점.
5) 표의 개선마다 perf/ 브랜치 PR을 링크해 두면 확인이 빠르다.
6) 그 주에 커밋한 기록이 가장 좋은 증거다. 늦게 쓴 문서는 감점하지 않지만 구술 확인 대상이 될 수 있다.

### P3-38 (1.27점)

[3부-P 포트폴리오 심사] README·영상·GitHub 프로필 (W00·W04·W13·W17·W22 과제, 매달 README 갱신)
대상: UE5-ActionArena 태그 exam-submit의 README, 내 GitHub 계정, unreal-study-log. 이름이 달라도 같은 역할이면 인정한다.
1) README 최종본(부록 구조): 대표 GIF, 핵심 구현 표(행마다 코드·문서 링크), 아키텍처 다이어그램(Mermaid 권장), 기술적 도전 Top 3(문제 → 해결 → 수치 → TS 링크), 성능 개선 표, 같은 기능의 진화, 개발 환경·빌드, 개발 기록 인덱스(Known Issues 포함).
2) 지연 200ms W15(RPC) vs W17(GAS 예측) 반응성 비교 영상을 README 핵심 섹션에 두고, ADR-0004 '결과' 칸을 갱신한다.
3) 증거: TS 3건 이상·ADR 3건 이상. 매달 대표 기록 3개(TS·ADR·영상)를 README 증거 표에 링크하고, 끝난 마일스톤을 닫는다.
4) 영상·GIF: PR·이슈에 캡처 도구 mp4(5~15초, 기능 하나, 판정 장면은 디버그 드로잉), README·Devlog에 ScreenToGif GIF(너비 800 정도).
5) GitHub 프로필: 사진·한 줄 소개, 프로필 README, 고정 저장소 2개(게임·학습 로그), 게임 저장소 About·토픽. 학습 로그 README가 브라우저에 보여야 한다.
6) README 첫 화면만 30초 보고 '무슨 게임·무엇을 했나·얼마나 깊게'를 알 수 있어야 한다.

### P3-39 (0.85점)

[3부-P 포트폴리오 심사] 릴리즈 6회·CHANGELOG·Shipping 빌드 (W04·W08·W13·W17·W20·W24 릴리즈)
대상: UE5-ActionArena의 GitHub Releases와 태그 exam-submit. 이름이 달라도 같은 역할이면 인정한다.
1) GitHub Releases에 v0.1.0·v0.2.0·v0.3.0·v0.4.0·v0.5.0·v1.0.0. 각각 태그(Target main)·제목·릴리즈 노트(이번 버전에서 해낸 것).
2) 공개 자료: v0.1.0 20초 GIF, v0.2.0 디버그 판정 45초 영상, v0.3.0 90초 플레이 영상, v0.5.0 개선 전/후 비교 GIF, v1.0.0 2~3분 시연 영상 링크.
3) 마일스톤 M1은 v0.1.0 때 닫는다.
4) CHANGELOG.md는 docs/changelog 브랜치 PR로 정리한다. 버전별 변경 내역.
5) Shipping 패키징 폴더 전체를 zip(파일당 2GiB 이하)으로 릴리즈에 첨부한다. 가장 최근 빌드를 v1.0.0에 두기를 권장한다.
6) 채점자가 다른 PC에서 zip을 내려받아 풀고 바로 실행한다.

### P3-40 (0.42점)

[3부-P 포트폴리오 심사] TIL·Devlog·월간 회고와 학습 로그 인덱스 (W01·W04·W08·W12·W16·W20·W22 과제)
준비할 곳: unreal-study-log(ue5-til, README), UE5-ActionArena(docs/devlog, docs/retro).
1) TIL: ue5-til/YYYY-MM-DD-주제.md. 키워드 / 배운 것 / 코드·실험(또는 오늘 한 과제) / 막힌 점 → 해결 / 다음 할 일을 내 말로.
2) Devlog: docs/devlog/W01.md~W24.md. 목표 vs 결과 표의 근거 칸에 PR·커밋 링크, 배운 것 3줄, 숫자 줄.
3) 월간 회고: docs/retro/M1.md~M5.md. Keep·Problem·Try를 그 달의 일로 채운다. M3에는 루브릭 6항목 자가 평가 점수.
4) TIL은 학습 로그 저장소, Devlog·회고는 게임 저장소 docs 폴더에 두고 main에 바로 커밋한다(docs PR도 된다). 문서 커밋에 코드 파일을 섞지 않는다.
5) unreal-study-log README(또는 README가 링크한 인덱스 문서): TIL 목록, 엔진 노트 링크, 코테 풀이 통계.
HTML 카드가 만든 초안 형식을 그대로 써도 된다. 빈칸을 내 말로 채웠는지 본다.

> **구술** — 시험 마지막 날 이후 응시자별 40분

### P3-42 (0.85점)

[3부-P 포트폴리오 심사 · 구술 40분] 프로젝트·코드 설명과 진위 확인 (W21·W23 과제)
대상: UE5-ActionArena 태그 exam-submit과 unreal-study-log. 1)~4)는 AI·메모 없이 내 저장소 화면(GitHub 웹 또는 채점자가 준 깨끗한 Clone)만 보며 말한다.
1) 소개(5분): 1분 버전, 이어서 3분 버전. 장르·기간·인원 → 핵심 기술 3개 → 가장 어려웠던 문제 → 배운 점. 숫자와 링크로. 1분·3분 스크립트는 학습 로그(interview/ 등)에 둔다.
2) 코드 설명(7분): 내 핵심 파일 5개 이름을 말하면 채점자가 2개를 고른다. 파일마다 3분: 책임, 핵심 함수 흐름, 서버/클라 실행 위치, 설계 이유나 한계.
3) TS 30초(2분): 채점자가 docs/troubleshooting에서 고른 TS 1건의 '면접 30초 버전'을 보지 않고 말한다.
4) 딥다이브(8분): docs/deepdive.md 주제로 꼬리 질문에 답한다.
5) 진위 확인(15분): 채점자가 포트폴리오 심사 문항 3개를 알려 준다. 문항마다 해당 코드·문서를 직접 열고 핵심 흐름과 결정 이유를 설명한다. 설명하지 못한 문항은 그 문항 점수의 50%만 인정한다.
남는 3분은 여유다.
