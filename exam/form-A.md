# 수료 시험 A형 — 문제지

> 6개월 커리큘럼 전 범위 · 100점 · 1부·2부·3부 라이브 실기는 AI·인터넷 사용 불가 (라이브 실기는 엔진 소스·공식 문서 열람만 허용) · 3부 포트폴리오는 시험 7일 전 저장소 제출
> 라이브 실기 블록1·2의 클래스 이름: A형은 `Rune`, B형은 `Dusk` 접두사를 쓴다 (예: `ARuneCharacter`). 응시자가 다른 접두사를 써도 감점하지 않는다. 블록3과 포트폴리오는 본인 프로젝트 이름 그대로.

## 1부 필기 (30점 · 300분)

지필 2교시(각 150분). 설명형 서술과 코드 읽기(출력 예측, 빈칸 채우기, 결함 찾기, 다이어그램 그리기)로 구성. AI, 인터넷, 엔진 소스 열람 불가. 문항 점수 = 30점 × weight ÷ 1부 weight 합

### P1-001 (0.10점)

[상황] 동기: "5.9 Preview도 나왔고 UE6 소식도 있으니 최신 걸로 시작하자. 내 노트북은 Windows 10 21H2, VS 2022 17.10, 쿼드코어 3.0GHz, RAM 16GB, 그래픽 메모리 6GB, C 드라이브(HDD) 여유 60GB야. 카페에서 배터리로 설치 걸어 두면 되겠지?"
(1) 커리큘럼 방식의 엔진 버전 결정(무엇을 설치하고 언제까지 유지)을 쓰고, Preview·UE6를 포트폴리오에 쓰지 않는 이유를 2가지 이상 쓰시오.
(2) 이 노트북에서 UE 5.8 Windows 공식 요구사항·권장 사양에 못 미치는 항목을 모두 찾아 기준값과 함께 쓰시오.
(3) 설치 전 준비 2가지와 이유를 쓰시오.

### P1-002 (0.10점)

[상황] 유니티를 2개월 쓴 친구가 언리얼 C++ 환경을 만든다. 유니티 때 쓰던 Visual Studio가 이미 있다.
(1) '유니티 허브 + VS'는 언리얼에서 무엇의 조합에 대응하는가? 기존 VS에는 무엇을 추가하는가?
(2) 런처로 엔진을 설치할 때 (가) 버전 번호를 고르는 기준, (나) 'Editor symbols for debugging'을 켜면 얻는 것과 감수할 것을 쓰시오.
(3) VS Installer에서 체크할 워크로드 3개와 게임 개발 항목 아래 확인할 구성 요소 3개 이상을 쓰시오.
(4) 몇 주 뒤 빌드가 'MSVC 버전' 경고·에러로 실패한다. UE 5.8 권장 컴파일러 버전과, VS를 다시 깔지 않고 해결하는 순서·이유를 쓰시오.

### P1-003 (0.19점)

[상황] 동기가 프로젝트를 C:\Users\김민수\OneDrive\바탕 화면\언리얼 공부\MyArena 에 만들었다. 안의 목록: Binaries/ Config/ Content/ DerivedDataCache/ Intermediate/ Saved/ Source/ .vs/ MyArena.sln MyArena.uproject (Source/MyArena/에 MyArena.Build.cs와 .h/.cpp)
(1) 경로의 문제 2가지와 증상, 옮길 위치를 쓰시오.
(2) 목록을 '원본'과 '생성물'로 나누고 유니티의 어떤 폴더 관계와 같은지 쓰시오.
(3) Binaries·Intermediate·Saved·DerivedDataCache를 Git에 올리지 않는 이유를 쓰시오.
(4) Source/, Config/, Content/, .uproject, Build.cs가 무엇을 담는지 한 줄씩 쓰시오.

### P1-004 (0.29점)

[상황] 에디터를 켠 채 AFloatingItem을 고친다. ①~⑥마다 'Live Coding(Ctrl+Alt+F11)'과 '에디터 종료 → VS F5' 중 하나를 고르고 이유를 한 줄로 쓰시오.
① .cpp의 Tick 안 FMath::Sin(RunningTime * 2.f)의 2.f를 3.f로 바꿈
② .h에 UPROPERTY(EditAnywhere) float RotationSpeed = 90.f; 추가
③ .cpp의 생성자 안 PrimaryActorTick.bCanEverTick을 false로 바꿈
④ .cpp의 BeginPlay 안 UE_LOG 문구 변경
⑤ .h의 Amplitude UPROPERTY 지정자를 EditAnywhere → VisibleAnywhere
⑥ .h에 void ResetHeight(); 선언 추가 + .cpp에 정의
(7) 헤더·UPROPERTY·생성자 변경이 Live Coding으로 안전하지 않은 이유를 '클래스의 모양' 관점에서 3~4줄로 설명하고, 헷갈릴 때의 원칙을 쓰시오.

### P1-005 (0.29점)

[상황] 레버를 당긴 적 없는데 BP_FloatingItem 하나가 갑자기 높이 올라간다. AFloatingItem::SetHeight(float NewHeight) 첫 줄에 중단점을 걸고 F5로 실행하자 상호작용 키를 누를 때 멈췄다.
[호출 스택]
> AFloatingItem::SetHeight(float NewHeight) 줄 58
  AArenaLever::Interact_Implementation(AActor* Caller) 줄 31
  IInteractable::Execute_Interact(UObject* O, AActor* Caller)
  UInteractionComponent::TryInteract() 줄 77
  AArenaCharacter::OnInteractPressed(const FInputActionValue& Value) 줄 140
  (엔진 입력 처리 함수들)
[지역] NewHeight = 5000.0 / this = BP_FloatingItem_C_2
(1) 호출 스택 창이 보여 주는 것과, SetHeight가 불린 경로를 먼저 불린 것부터 쓰시오.
(2) 지역 값으로 알 수 있는 것과, 다음에 어디서 무엇을 확인할지 쓰시오.
(3) 헤더를 고쳐 빌드하자 오류 목록에 47개가 떴다. 출력 창 앞부분(WaveOffset·ClampHeight는 ArenaMath.h에 선언된 함수):
[1/5] Compile FloatingItem.cpp
ArenaMath.h(12): error C2143: syntax error: missing ';' before '}'
FloatingItem.cpp(40): error C3861: 'WaveOffset': identifier not found
[2/5] Compile ArenaLever.cpp
ArenaMath.h(12): error C2143: syntax error: missing ';' before '}'
ArenaLever.cpp(22): error C3861: 'ClampHeight': identifier not found
무엇부터 고치며, 왜 오류 목록이 아니라 출력 창의 첫 error부터 읽는가?
(4) 15분 룰에 따라 언제, 무엇을 담아 AI에 질문하는가? 이 상황의 질문을 3~5줄로 쓰시오.

### P1-006 (0.19점)

[상황] 2인 팀이 Git LFS 없이 작업한다. 둘이 같은 날 BP_Door.uasset을 각자 고쳐 Push하다 충돌했고, Clone에 20분이 걸린다.
(1) Git이 텍스트 파일과 .uasset·.umap을 기록하는 방식의 차이와, BP_Door 충돌을 코드처럼 합칠 수 없는 이유를 쓰시오.
(2) LFS를 쓰면 저장소에 무엇이 남고 실제 파일은 어떻게 되며, Clone·히스토리에 어떤 효과가 있는가?
(3) 같은 충돌을 미리 막는 LFS 기능과 사용 시점·방법, Perforce의 대응 개념을 쓰시오.
(4) '한도 넘으면 요금 폭탄?' 걱정에 답하시오: 무료 한도, 결제수단이 없을 때 초과 시 동작, 확인 위치.

### P1-007 (0.19점)

(1) 알맞은 AI 도구 종류(채팅형/코드를 읽는 AI)와 예시 도구, 이유를 쓰시오. (가) 'UPROPERTY가 GC에 왜 중요한지 C# GC와 비교해 설명해 줘' (나) '내 UInteractionComponent.cpp와 ArenaLever.cpp를 보고 델리게이트가 브로드캐스트되지 않는 원인을 찾아 줘'
(2) CLAUDE.md의 용도와 핵심 규칙 4가지를 쓰시오.
(3) 다음은 5원칙 중 무엇을 어겼는가? 원칙과 올바른 행동을 쓰시오. ① AI가 알려 준 GetActorForwardVector2D()를 그대로 붙였더니 빌드 실패 ② 크래시 2분 만에 에러 원문만 붙여 '고쳐 줘' ③ 이해 못 한 람다 코드를 동작해서 커밋 ④ 새 기능 첫 질문이 '전체 코드 다 써 줘' ⑤ AI가 크게 도운 기능의 PR에 AI 언급 없음
(4) L1·L2·L3의 방식·규칙·적용 구간을 쓰고, W6·W12·W23 학습자의 단계를 쓰시오.

### P1-008 (0.10점)

(1) 백준 문제를 35분째 못 풀고 있다. 지금 AI에게 무엇을 받고 무엇은 받지 않는가? 풀이를 보고 맞혔다면 그 뒤 무엇을 하는가? 이유를 한 줄로 쓰시오.
(2) AI-Off 챌린지의 목적을 쓰고 빈칸을 채우시오. ① 주차 (가), 과제 (나), 30분 / ② W8, 과제 (다), 제한 (라) / ③ 주차 (마), HealthComponent+데미지+사망 델리게이트+체력바, 제한 (바) / ④ W23, 과제 (사), 시간 제한
(3) Unreal MCP를 W1~W20 핵심 학습에 쓰지 않는 이유 2가지를 쓰시오.
(4) W21 딥다이브 A에서 Unreal MCP로 하는 일, 맡길 작업 예 2가지, 반드시 문서화할 것을 쓰시오.

### P1-009 (0.19점)

[상황] 같은 스터디의 친구가 묻는다. "혼자 만드는 포트폴리오인데 왜 브랜치를 만들고 PR까지 거쳐? 그냥 main에 저장하면 되잖아."
이 친구에게 게임 세이브에 빗대어 설명하는 글을 쓰시오(전체 12~16줄 안팎. 분량은 채점하지 않으며, 아래 (1)~(4)가 모두 들어가야 한다).
(1) 저장소·커밋·푸시가 각각 무엇이고, GitHub Desktop에서 커밋과 푸시에 해당하는 버튼은 무엇인가.
(2) 브랜치·PR·머지의 뜻과, 혼자여도 'PR → 머지' 순서를 지키는 이유 2가지. 머지는 어떤 방식으로 하는가.
(3) 이슈와 마일스톤은 무엇이고, PR 본문에 'Closes #5'라고 쓰면 무슨 일이 일어나는가.
(4) 태그와 릴리즈는 어떻게 다른가.

### P1-010 (0.19점)

[상황] W7 토요일, 학생이 콤보 입력이 가끔 씹히는 버그를 고쳤다. 오늘 메모는 세 줄이다.
(가) 콤보 입력이 씹힘 → 노티파이 윈도우가 끝나기 전에 입력 버퍼를 비우고 있었음 → 비우는 시점을 옮겨 해결
(나) 입력 윈도우를 타이머 대신 AnimNotifyState로 정함 → 몽타주 속도가 바뀌어도 구간이 같이 움직이기 때문
(다) AnimNotifyState의 NotifyBegin/End가 몽타주 재생 중 어느 시점에 불리는지 엔진 소스에서 확인함

(1) 오늘 코드 수정은 어떤 경로(브랜치·PR 여부)로 올리고, TIL은 어떤 경로로 올리는가. 규칙 한 줄도 쓰시오.
(2) 커밋 메시지·PR 본문·이슈·TIL·docs 문서·릴리즈 노트·README 7곳에 각각 무엇을 언제 남기는지 쓰시오. 그중 오늘 남기는 곳에는 ○를 표시하고, 오늘 쓸 내용을 한 줄씩 예로 쓰시오.
(3) (가)(나)(다)를 주말에 docs 문서로 승격하려 한다. 각각 어떤 문서가 되는가.
(4) 이 학생은 "기록은 한 달 뒤에 몰아서, AI에게 시켜 쓰겠다"고 한다. 커리큘럼의 기록 방식이 그렇게 하지 않는 이유 2가지와, PR·마일스톤·릴리즈가 무엇을 연결해 주는지 쓰시오.

### P1-011 (0.19점)

[상황] GitHub Desktop을 쓰다가 생긴 일 6가지다. 각각 무엇을 어떤 순서로 하고, 왜 그 방법이 안전한지(또는 주의점)를 쓰시오.
① 방금 커밋했는데 메시지에 오타가 있다. 아직 Push 전이다.
② `Current Branch`를 보니 main이다. 30분째 작업 중이고 아직 커밋하지 않았다.
③ `Push origin`을 눌렀더니 거부되고, 위쪽 버튼이 `Pull origin`으로 바뀌어 있다. 어제 GitHub 웹에서 README를 직접 고쳤다.
④ 일주일 쉬고 돌아왔더니 어디까지 했는지, 지금 어느 브랜치인지 모르겠다.
⑤ 인터넷 글에서 "꼬였으면 `Discard All Changes…` 누르고 `Force push` 하면 깔끔하다"고 한다.
⑥ (다른 날) 방금 커밋했는데 파일 하나를 빠뜨렸다. 이 커밋을 취소하고, 빠뜨린 파일까지 고친 뒤 함께 다시 커밋하고 싶다. 아직 Push 전이다.
추가: ①이나 ⑥에서 이미 Push했다면 어떻게 하는 게 안전하고, 왜 그런가.

### P1-012 (0.10점)

[상황] W10 화요일에 과제1(BTTask 순찰)을 끝냈다. 수요일에는 코드 변경 없이 개념 공부와 코테만 했다. 이번 주 일요일이 지나면 다음 주가 릴리즈 주간이고, 다음 주 말이 월말이다.
(1) 화요일, '📅 오늘 학습' 카드의 마지막 기록 단계를 어떤 순서로 하는가. PR 본문은 어디서 얻고, 그 본문에 무엇이 들어가야 하는가.
(2) 수요일에는 기록 단계를 어떻게 처리하는가. 그 이유는?
(3) 🔔 알림 3종(주간 Devlog·릴리즈·월간 회고)을 각각 언제 누르고, 받는 초안에 무엇이 채워져 있으며, 내가 할 일은 무엇인가. 릴리즈는 6개월간 몇 번인가.

### P1-013 (0.29점)

(1) 유니티 Coin.cs(MonoBehaviour)를 언리얼 C++로 만들면 파일 구성과 각 파일 내용은?
(2) .h/.cpp를 나누는 이유를 '다른 파일은 무엇을 include하나'와 '재컴파일 범위'로 설명하고, C#은 왜 필요 없었는지 쓰시오.
(3) #include와 #pragma once의 역할을 쓰시오. Coin.cpp가 Coin.h와 ArenaTypes.h를 include하고 Coin.h도 ArenaTypes.h를 include한다. ArenaTypes.h에 #pragma once가 없으면?
(4) 다음 헤더를 보고 답하시오.
01 #pragma once
02 #include "CoreMinimal.h"
03 #include "GameFramework/Actor.h"
04 #include "Enemy.h"
05 #include "Spawner.generated.h"
06 UCLASS()
07 class ASpawner : public AActor
08 {
09     GENERATED_BODY()
10 public:
11     void Register(AEnemy* NewEnemy);
12     UPROPERTY(EditAnywhere) TObjectPtr<AEnemy> LastSpawned;
13 };
(가) 4행을 전방 선언으로 바꾸는 방법과 Enemy.h include를 옮길 곳 (나) 전방 선언으로 충분한 이유와 좋아지는 점

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
12     virtual void Tick(float DeltaTime) override;
13 protected:
14     virtual void BeginPlay() override;
15     UPROPERTY(VisibleAnywhere)
16     TObjectPtr<UStaticMeshComponent> Mesh;
17     UPROPERTY(EditAnywhere, Category = "Float")
18     float Amplitude = 50.f;
19 private:
20     float RunningTime = 0.f;
21 };
(1) 다음을 한 줄씩 설명하시오: 1, 5, 6, 7, 9, 10(C#과 차이 포함), 12, 15~16, 17~18, 21행
(2) .cpp에서 Tick을 정의하는 첫 줄과 ::의 뜻을 쓰시오.
(3) C# 습관대로 쓴 선언(UCLASS 등 생략)에서 C++ 문법상 틀린 곳 3종류를 찾아 고치시오.
class AFloatingItem : public AActor
{
    public float Amplitude = 50.f;
    public void ResetHeight();
    protected override void BeginPlay();
}

### P1-015 (0.29점)

// 헤더 일부
UPROPERTY(EditAnywhere) TObjectPtr<AActor> LookTarget;   // 레벨에서 지정(비워 둘 수 있음)
UPROPERTY(VisibleAnywhere) TObjectPtr<USpringArmComponent> SpringArm;
// cpp
01 void AArenaCharacter::BeginPlay()
02 {
03     Super::BeginPlay();
04     UCharacterMovementComponent* Move = GetCharacterMovement();
05     Move->MaxWalkSpeed = WalkSpeed;
06     FVector MyLoc = GetActorLocation();
07     FVector TargetLoc = LookTarget->GetActorLocation();
08     FVector ToTarget = TargetLoc - MyLoc;
09     float Dist = ToTarget.Size();
10 }
11 void AArenaCharacter::OnHit(AActor* OtherActor)
12 {
13     AArenaCharacter* Other = Cast<AArenaCharacter>(OtherActor);
14     Other->SpringArm->TargetArmLength = 200.f;
15 }
(1) 4행 Move는 무엇을 담는 변수이며, nullptr이란 무슨 뜻인가?
(2) 5행은 ->, 9행은 .을 쓰는 이유를 쓰고, 5행을 *와 .으로 다시 쓰시오. C#과 비교하시오.
(3) 크래시가 날 수 있는 줄 2개와 상황·이유를 쓰시오.
(4) 두 곳을 nullptr 검사 또는 IsValid()로 고친 코드를 쓰시오.

### P1-016 (0.19점)

각 에러마다 (가) 원문 해석 (나) 실제 원인 줄과 이유 (다) 고치는 법을 쓰시오. 에러 1은 가리키는 줄(32)과 고칠 줄이 다른 이유도 쓰시오.
[에러 1] FloatingItem.cpp
31     Super::Tick(DeltaTime)
32     RunningTime += DeltaTime;
출력: FloatingItem.cpp(32): error C2146: syntax error: missing ';' before identifier 'RunningTime'
[에러 2] .h: void ApplyBonus(float Amount);
.cpp 45: void AFloatingItem::ApplyBonus(int32 Amount) { Amplitude += Amount; }
출력: FloatingItem.cpp(45): error C2511: 'void AFloatingItem::ApplyBonus(int32)': overloaded member function not found in 'AFloatingItem'
[에러 3] DirectionDebugActor.cpp (include는 "DirectionDebugActor.h" 하나뿐)
60     DrawDebugLine(GetWorld(), Start, End, FColor::Green, false, 0.f);
출력: DirectionDebugActor.cpp(60): error C3861: 'DrawDebugLine': identifier not found

### P1-017 (0.19점)

(1) 접두사의 뜻을 쓰시오: AFloatingItem, UHealthComponent, FWeaponData(구조체), TArray, EArenaPhase, IInteractable, bIsSprinting
(2) 규칙에 어긋난 두 선언의 문제와 수정, 규칙을 어기면 빌드에서 어떻게 되는지 쓰시오. ① UCLASS() class HealthComponent : public UActorComponent ② UCLASS() class UDoor : public AActor
(3) UCLASS()와 GENERATED_BODY()의 역할을 UHT와 연결해 설명하시오.
(4) 아래 include의 규칙 위반을 고치고, FloatingDoor.generated.h를 누가 만드는지 쓰시오.
#pragma once
#include "CoreMinimal.h"
#include "FloatingDoor.generated.h"
#include "GameFramework/Actor.h"

### P1-018 (0.19점)

// StartLocation.Z=100, Amplitude=50, Frequency=2, RotationSpeed=90(도/초). StartLocation은 BeginPlay에서 저장.
01 void AFloatingItem::Tick(float DeltaTime)
02 {
03     Super::Tick(DeltaTime);
04     RunningTime += DeltaTime;
05     FVector NewLocation = StartLocation;
06     NewLocation.Z += FMath::Sin(RunningTime * Frequency) * Amplitude;
07     SetActorLocation(NewLocation);
08     FRotator NewRotation = GetActorRotation();
09     NewRotation.Yaw += RotationSpeed * DeltaTime;
10     SetActorRotation(NewRotation);
11 }
(1) Z의 변화 범위와 FVector·FRotator가 나타내는 것을 쓰시오.
(2) 2초 동안 Yaw 변화량과, 60fps·30fps에서 같은 이유를 쓰시오.
(3) 9행을 Yaw += RotationSpeed; 로 바꾸면 1초 동안 60fps·30fps에서 각각 몇 도 도는가? 문제는?
(4) Tick·DeltaTime은 유니티의 무엇에 대응하는가?
(5) '빨리 도는·높이 뜨는·천천히 도는' 3종을 코드 수정 없이 만드는 방법을 유니티 프리팹·프리팹 변형과 비교하고, C++ 부모와 BP 자식의 역할을 쓰시오.

### P1-019 (0.29점)

int GKillCount = 0;   // 전역
void AddByValue(int Value)    { Value += 10; }
void AddByPointer(int* Value) { *Value += 10; }
void AddByRef(int& Value)     { Value += 10; }
int main()
{
    int Hp = 100;
    AddByValue(Hp);    cout << Hp << '\n';   // ①
    AddByPointer(&Hp); cout << Hp << '\n';   // ②
    AddByRef(Hp);      cout << Hp << '\n';   // ③
    int* Boss = new int(500);
    delete Boss;
}
(1) ①~③의 출력을 쓰시오.
(2) 세 함수 안에서 cout << &Value; 를 찍으면 main의 &Hp와 같은 주소가 나오는 함수는? AddByPointer 안에서 &Hp와 같은 값을 보려면 무엇을 출력하는가?
(3) 포인터와 참조의 차이 3가지를 쓰시오.
(4) Hp, Boss(변수 자체), *Boss, GKillCount의 메모리 영역을 쓰고, 스택과 힙의 차이(해제 시점·속도·크기·수명 관리)를 설명하시오.

### P1-020 (0.29점)

struct FItem { int Id; int Count; };
FItem* MakeItem(int Id) { return new FItem{ Id, 1 }; }
int* GetBonus() { int Bonus = 50; return &Bonus; }   // (가)
int main()
{
    FItem* Sword  = MakeItem(1);
    FItem* Shield = MakeItem(2);
    FItem* Alias  = Sword;
    delete Sword;
    Alias->Count = 5;              // (나)
    Shield = MakeItem(3);          // (다)
    int* B = GetBonus();
    cout << *B << '\n';            // (라)
    FItem Copy = *Shield;          // (마)
    Copy.Count = 99;
    cout << Shield->Count << '\n'; // (바)
    delete Shield;
}
(1) 누수가 생기는 줄과, 어떤 객체가 왜 해제될 수 없는지 쓰시오.
(2) 댕글링 포인터가 생기거나 쓰이는 곳을 모두(2곳 이상) 찾아 위험한 이유를 쓰시오.
(3) (바)의 출력과 이유를 쓰시오. FItem이 C# class였다면 무엇이 출력되는가? 'C++은 기본이 값 타입', 'C# 참조 타입 = 자동 관리되는 포인터' 관점으로 설명하시오.
(4) 누수와 댕글링의 차이를 증상 중심으로 쓰시오.

### P1-021 (0.29점)

class FWeapon
{
public:
    void PrintName() { cout << "Weapon\n"; }
    virtual void Attack() { cout << "Weapon Attack\n"; }
    ~FWeapon() { cout << "~Weapon\n"; }
};
class FSword : public FWeapon
{
public:
    FSword() { Trail = new int[100]; }
    void PrintName() { cout << "Sword\n"; }
    void Attack() override { cout << "Sword Slash\n"; }
    ~FSword() { delete[] Trail; cout << "~Sword\n"; }
private:
    int* Trail;
};
int main()
{
    FWeapon* W = new FSword();
    W->PrintName();   // ①
    W->Attack();      // ②
    delete W;         // ③
}
(1) ①~③ 출력과, ①②가 다르게 동작하는 이유를 쓰시오.
(2) ②의 원리를 vtable 개념으로 3줄 안팎으로 설명하시오.
(3) ③의 문제와 원인, FWeapon 수정 방법, 수정 후 ③ 출력을 쓰시오.
(4) Attack을 void Atack() override 로 오타 내면? override가 없었다면?
(5) final의 의미와 FSword를 더 상속 못 하게 하는 선언 첫 줄을 쓰고, AArenaCharacter가 ACharacter를 상속하는 선언 첫 줄과 : public의 의미를 쓰시오.

### P1-022 (0.19점)

[코드 1]
void ALifecycleProbe::BeginPlay()
{
    UE_LOG(LogTemp, Warning, TEXT("Probe BeginPlay"));
    CurrentHealth = StartHealth;
}   // Super::BeginPlay(); 없음
[코드 2]
struct FScope
{
    int Id;
    FScope(int InId) { Id = InId; cout << "+" << Id << '\n'; }
    ~FScope() { cout << "-" << Id << '\n'; }
};
void Run() { FScope X(1); cout << "run\n"; }
int main()
{
    FScope* P = new FScope(2);
    Run();
    cout << "main\n";
}   // delete P 없음
(1) Super::BeginPlay()가 무엇인지 C#과 비교하고, 빠지면 생기는 문제와 고친 코드를 쓰시오.
(2) [코드 2]의 출력 순서와 '-2'가 없는 이유, 생성자·소멸자의 호출 시점과 역할을 쓰시오.
(3) 다음 멤버에 알맞은 접근 지정자와 이유를 쓰시오: (가) 외부 UI가 읽는 float GetHealth() const (나) 엔진이 부르는 BeginPlay override (다) 이 클래스만 바꿔야 하는 CurrentHealth
(4) 다른 클래스에서 Probe->CurrentHealth = 0.f; 라고 쓰면? 세 접근 지정자의 차이를 쓰시오.

### P1-023 (0.19점)

// FDamageRecord: FString·FVector 등을 가진 큰 구조체(Amount는 float)
01 Camera = CreateDefaultSubobject<UCameraComponent>(TEXT("Camera"));   // 생성자 안
02 void AArenaCharacter::Move(const FInputActionValue& Value)
03 {
04     const FVector2D Input = Value.Get<FVector2D>();
05     AddMovementInput(GetActorForwardVector(), Input.Y);
06 }
07 void AArenaCharacter::OnOverlap(AActor* Other)
08 {
09     auto* Hero = Cast<AArenaCharacter>(Other);
10     if (Hero) { Hero->Heal(10.f); }
11 }
12 float SumDamage(TArray<FDamageRecord> Records)
13 {
14     float Total = 0.f;
15     for (FDamageRecord Rec : Records) { Total += Rec.Amount; }
16     return Total;
17 }
18 void SetMultiplier(const float& InValue);
(1) 1행·9행의 < > 안 타입이 뜻하는 것과 TArray<int32>의 <int32>의 뜻을 쓰시오.
(2) 2행의 &와 const의 의미, 비슷한 C# 매개변수, 함수 안에서 Value = FInputActionValue(); 를 쓰면?
(3) 9행 auto*의 실제 타입과 정해지는 방식은?
(4) 12·15행의 불필요한 복사를 고치고 비용이 드는 이유를 쓰시오.
(5) 18행을 셀프 리뷰에서 어떻게 고치고 왜 그런가?

### P1-024 (0.19점)

class IDamageable
{
public:
    virtual void TakeHit(int Amount) = 0;
    virtual bool IsDead() const = 0;
    virtual ~IDamageable() {}
};
class FActorBase { public: virtual void Update() {} protected: int Id = 0; };
class FBarrel : public FActorBase, public IDamageable
{
public:
    void TakeHit(int Amount) override { Hp -= Amount; }
    bool IsDead() const override { return Hp <= 0; }
private:
    int Hp = 30;
};
class FCrate : public IDamageable
{
public:
    void TakeHit(int Amount) override { Hp -= Amount; }
private:
    int Hp = 10;
};
int main()
{
    IDamageable* A = new FBarrel();   // ①
    IDamageable B;                     // ②
    FCrate C;                          // ③
    A->TakeHit(40);
    cout << A->IsDead() << '\n';       // ④
}
(1) = 0인 함수의 이름과, 그런 함수가 있는 클래스의 특징을 쓰시오.
(2) ①②③의 컴파일 여부와 이유, 에러 줄을 지웠을 때 ④의 출력을 쓰시오.
(3) FBarrel은 무엇과 무엇을 상속하는가? C# class Barrel : ActorBase, IDamageable과 비교해 C++에서 인터페이스를 표현하는 방법을 쓰시오.
(4) C++ 추상 클래스와 C# interface의 차이를 2가지 이상 쓰시오.

### P1-025 (0.29점)

[코드 1]
void Heal(int& Hp)   { Hp += 10; }
void Poison(int& Hp) { Hp -= 5; }
int main()
{
    void (*Effect)(int&) = &Heal;   // 함수 포인터
    int Hp = 50;
    Effect(Hp);
    Effect = &Poison;
    Effect(Hp);
    Effect(Hp);
    cout << Hp << '\n';
}
[코드 2]
void ADoor::StartAutoClose()
{
    GetWorldTimerManager().SetTimer(CloseHandle, [this]()
    {
        bIsOpen = false;
        DoorMesh->SetRelativeRotation(FRotator::ZeroRotator);
    }, 3.0f, false);
}
(1) [코드 1]의 출력과 함수 포인터 개념을 C# Action과 비교해 쓰시오.
(2) [this]의 뜻과 람다에서 멤버를 쓸 수 있는 이유를 쓰고 C# 람다와 비교하시오.
(3) 문을 연 1초 뒤 문 액터가 Destroy됐다. 3초 시점에 생길 수 있는 일과 이유를 쓰시오.
(4) (3)을 막는 방법 2가지 이상과 그중 하나의 코드를 쓰시오.
(5) 무기 에셋 비동기 로드 완료 콜백에서 this의 멤버를 쓸 때 확인할 것과 약한 포인터를 쓰는 이유를 쓰시오.

### P1-026 (0.19점)

01 class UArenaAnimInstance : public UAnimInstance   // UCLASS·GENERATED_BODY 생략
02 {
03 public:
04     virtual void NativeInitializeAnimation() override;
05     virtual void NativeUpdateAnimation(float DeltaSeconds) override;
06     float GetSpeed() { return Speed; }                                  // (가)
07     bool CheckFalling() const { bIsInAir = true; return bIsInAir; }    // (나)
08     float GetSpeedRatio(float MaxSpeed) { return Speed / MaxSpeed; }    // (다)
09 protected:
10     UPROPERTY(BlueprintReadOnly) float Speed = 0.f;
11     UPROPERTY(BlueprintReadOnly) bool bIsInAir = false;
12 };
13 void UArenaAnimInstance::NativeUpdateAnimation(float DeltaSeconds)
14 {
15     Super::NativeUpdateAnimation(DeltaSeconds);
16     AArenaCharacter* Character = Cast<AArenaCharacter>(TryGetPawnOwner());
17     if (Character == nullptr) { return; }
18     Speed = Character->GetVelocity().Size2D();
19     bIsInAir = Character->GetCharacterMovement()->IsFalling();
20 }
21 void PrintSpeed(const UArenaAnimInstance& Anim)
22 {
23     UE_LOG(LogTemp, Log, TEXT("%f"), Anim.GetSpeed());   // (라)
24 }
(1) (라)의 컴파일 에러 원인 줄과 이유, 수정을 쓰시오.
(2) (나)가 컴파일 에러인 이유와 const 멤버 함수의 약속을 쓰시오.
(3) 셀프 리뷰에서 (다)에 무엇을 지적하는가?
(4) 16행처럼 매 프레임 Cast하면 안 되는 이유를 쓰고, 초기화 때 1회 Cast해 캐싱하고 업데이트에서는 유효성만 확인하도록 멤버 선언과 두 함수를 고쳐 쓰시오.

### P1-027 (0.19점)

무기 시스템에서 '무기 1개의 수치 묶음(공격력 float, 공격 속도 float, 무기 종류)'을 블루프린트에서도 읽고 쓰고 싶다. 무기 종류는 검·창·도끼 3가지다.
(1) C++에서 struct와 class는 문법적으로 무엇이 다른가? 그리고 언리얼 관례에서 USTRUCT와 UCLASS는 각각 어떤 용도로 쓰는가? (GC 관점 포함)
(2) 이 수치 묶음을 블루프린트에 노출되는 구조체로 선언하라(이름은 관례에 맞게 직접 정한다).
(3) 무기 종류를 리플렉션에 노출되는 enum class로 선언하라. 그리고 이 enum에서 UENUM 매크로를 빼면 (2)의 구조체 멤버와 블루프린트에서 무엇이 안 되는지 한 줄로 쓰라.

### P1-028 (0.29점)

다음 세 상황에서 쓸 포인터 타입을 고르고 이유를 한 줄씩 쓰라.
(a) UObject가 아닌 일반 C++ 클래스 FPathCache 객체를 AI 시스템 세 곳이 함께 쓰고, 마지막 사용자가 놓으면 지워져야 한다.
(b) AArenaEnemy가 공격 대상 플레이어 액터를 '소유하지 않고 지켜보기만' 한다. 플레이어는 언제든 파괴될 수 있다.
(c) 세이브 파일 해석용 일반 C++ 객체 FSaveParser를 한 클래스만 단독으로 소유한다.
그다음 (d) TSharedPtr·TWeakPtr·TUniquePtr를 표준 C++ 스마트 포인터에 대응시키고 각각의 소유 방식을 설명하라. (e) 동료가 UObject를 TSharedPtr에 담자고 할 때 왜 안 되는지 설명하라.

### P1-029 (0.29점)

(1) 퀘스트 그래프에서 FQuestNode가 다음 노드를 TSharedPtr<FQuestNode> Next로, 이전 노드를 TSharedPtr<FQuestNode> Prev로 서로 가리킨다. 외부에서 두 노드를 가리키던 포인터를 모두 놓았는데 메모리가 해제되지 않는다. 원인을 참조 카운트로 설명하고 고치는 방법을 쓰라.
(2) 10MB짜리 TArray<uint8> ScreenshotBytes를 업로더 함수 Upload(TArray<uint8> Bytes)에 넘긴 뒤 원본은 더 이상 쓰지 않는다. 복사와 이동의 차이를 설명하고, 복사 없이 넘기는 호출 코드 한 줄과 호출 후 원본 배열의 상태를 쓰라.
(3) 생성자에서 new[]로 버퍼를 만들고 소멸자에서 delete[]하는 클래스 FRawBuffer가 있다. Rule of Three/Five 관점에서 무엇이 빠졌을 때 어떤 문제가 생기는지, Rule of Zero로는 어떻게 바꾸는지 쓰라.

### P1-030 (0.19점)

다음 코드를 읽고 답하라.

class AArenaCharacterBase : public ACharacter {
    GENERATED_BODY()
private:
    float Health = 100.f;
};

class AArenaEnemy : public AArenaCharacterBase {
    GENERATED_BODY()
public:
    void Heal(float Amount) { Health += Amount; }   // (가)
private:
    bool bIsPatrolling = true;
    bool bIsChasing = false;
    bool bIsAttacking = false;
};

// 풀(Pool)에서 재사용하는 투사체
void AArenaProjectile::ReturnToPool() { SetActorHiddenInGame(true); }
void AArenaProjectile::ActivateFromPool(const FVector& Start)
{
    SetActorLocation(Start);
    SetActorHiddenInGame(false);
}

(1) (가)는 컴파일되는가? 안 된다면 Health를 어떤 접근 지정자로 바꿔야 하는지, 그 지정자가 public·private과 어떻게 다른지 쓰라.
(2) bool 세 개로 AI 상태를 표현하는 방식의 위험을 쓰고, 순찰·추적·공격 상태를 enum class로 다시 선언하라.
(3) 이 투사체는 두 번째로 풀에서 꺼낼 때 '이전 발사의 이동 속도와 이미 맞힌 대상 목록(TSet<AActor*> HitActors)'이 남아 버그가 난다. 언리얼에서 풀 재사용 시 BeginPlay가 다시 불리지 않는다는 점을 고려해 상태 리셋 함수 ResetForReuse()에 들어갈 내용을 쓰고, 어디서 호출할지 쓰라.

### P1-031 (0.29점)

아래는 신입이 올린 PR이다. Epic C++ 코딩 표준 기준으로 셀프 리뷰하라.

// healthComp.h
#include "healthComp.generated.h"
#include "Components/ActorComponent.h"
UCLASS()
class healthComp : public UActorComponent {
    GENERATED_BODY()
public:
    float getHP() { return hp; }
    void process(float d, AActor* who);
    UPROPERTY() AActor* lastAttacker;
    bool dead;
    float hp;
};

// healthComp.cpp
#include "Kismet/GameplayStatics.h"
#include "healthComp.h"
void healthComp::process(float d, AActor* who) {
    hp -= d; lastAttacker = who;
    if (hp <= 0) { dead = true; /* 래그돌 15줄 */ /* UI 갱신 20줄 */ /* 점수 계산 10줄 */ }
    if (hp > 100.f) hp = 100.f;
}

(1) 코딩 표준 위반을 5개 이상 찾아 각각 고친 모습을 쓰라(네이밍 접두사, const, include 순서, UObject 멤버 포인터 포함).
(2) process 함수를 어떻게 나누고 어떤 이름을 붙이겠는가?
(3) 루브릭 '코드 품질'(1 하드코딩·거대 클래스 / 2 C++ 베이스 + BP 자식, 네이밍 준수 / 3 컴포넌트 책임 분리, 데이터 분리, GC 안전 / 4 확장 지점 설계 + 테스트, 리뷰하기 좋은 PR 크기)로 이 코드는 몇 점인가? 3점이 되려면 무엇을 바꿔야 하는가?

### P1-032 (0.29점)

무기 스윙 판정을 만든다. 한 번 휘두를 때 Sweep이 여러 프레임에 걸쳐 같은 적을 여러 번 맞히는데, 적마다 한 번만 데미지를 줘야 한다. 또 적 이름(FName)으로 적 스탯(FEnemyStat)을 찾는 표, 이번 스윙에 맞은 적들을 순서대로 담는 목록이 필요하다.
(1) 세 용도에 TArray·TSet·TMap 중 무엇을 쓰는지, C#의 무엇에 대응하는지 쓰라.
(2) 맞은 적 목록 TArray<AActor*> HitActors를 범위 기반 for로 돌며 각 적에게 데미지를 주는 코드 뼈대를 쓰라(데미지 함수는 DealDamage(AActor*)로 가정, null 검사 포함).
(3) 중복 타격 검사를 TArray::Contains로 할 때와 TSet으로 할 때의 시간 복잡도 차이와 선택 기준을 쓰라.
(4) TSet<AActor*>에서 '같은 원소'는 무엇을 기준으로 판단하는가? 체력·위치가 완전히 같은 적 2마리는 어떻게 취급되는가?
(5) TArray의 인덱스 접근·끝에 추가, TMap 키 검색, 정렬된 배열의 이분 탐색의 시간 복잡도를 쓰라.

### P1-033 (0.19점)

(1) C# List<string> names; names.Add("Sword"); string title = "Arena"; 를 언리얼 타입으로 바꾸면?
(2) (FEnemyInfo는 (이름, 체력) 생성자가 있는 구조체)
01 TArray<FEnemyInfo> Enemies;
02 Enemies.Add(FEnemyInfo(TEXT("Goblin"), 50));
03 FEnemyInfo& First = Enemies[0];
04 for (int32 i = 0; i < 100; ++i) { Enemies.Emplace(TEXT("Slime"), 10); }
05 First.Hp = 0;
06 UE_LOG(LogTemp, Log, TEXT("%d"), Enemies.Num());
(가) 6행 출력 (나) 5행이 위험한 이유를 용량·재할당으로 (다) 안전하게 만드는 방법 2가지
(3) Num()과 용량(Slack)의 관계, 용량이 부족할 때 Add하면 일어나는 일을 쓰시오.
(4) 2행 Add와 4행 Emplace의 차이는?
(5) 웨이브 시작 때 적 500마리 정보를 넣기 전에 할 일과 이유를 쓰시오.

### P1-034 (0.29점)

(1) 게임 실행 파일 하나를 실행하면 프로세스·스레드가 어떻게 존재하는가? 메모리 관점의 차이와 언리얼 주요 스레드 2가지 이상을 쓰시오.
(2) 게임 스레드와 워커 스레드의 역할을 쓰시오.
(3) 데이터 경쟁을 정의하고, 게임 스레드가 속도를 바꾸는 동안 워커 스레드가 읽는 예로 설명하시오.
(4) 문제가 있는 줄을 모두 찾아 이유를 쓰고 올바른 구조를 설명하시오.
void UArenaAnimInstance::NativeThreadSafeUpdateAnimation(float DeltaSeconds)
{
    Super::NativeThreadSafeUpdateAnimation(DeltaSeconds);
    AArenaCharacter* Character = Cast<AArenaCharacter>(TryGetPawnOwner());   // (가)
    Speed = Character->GetVelocity().Size2D();                              // (나)
    Character->bIsSprinting = Speed > 500.f;                                // (다)
    Direction = CachedDirection;   // (라) NativeUpdateAnimation(게임 스레드)에서 미리 복사한 값
}

### P1-035 (0.29점)

[설명형] 학생 클래스 AFloatingItem(public: 영역)에 다음 네 멤버가 있다.
① UPROPERTY(EditAnywhere, Category="Float") float BobHeight = 50.f;
② UPROPERTY(VisibleAnywhere) TObjectPtr<UStaticMeshComponent> Mesh;
③ UPROPERTY(EditAnywhere, BlueprintReadWrite, meta=(ClampMin="0.0")) float Speed = 100.f;
④ float ElapsedTime = 0.f;   // UPROPERTY 없음
(1) UHT가 이 매크로들을 읽고 하는 일을 쓰고, 엔진 시스템(에디터·블루프린트·GC·직렬화·네트워크) 가운데 세 가지가 이 정보를 각각 어떻게 쓰는지 예를 들라.
(2) ①~④ 각각에 대해 [BP 기본값 창에서 / 레벨에 놓은 인스턴스의 디테일 패널에서 / BP 그래프에서] 무엇이 가능한지 표로 채우라. ③에 -5를 입력하면 어떻게 되는지도 쓰라.
(3) 아래는 ObjectMacros.h namespace UP 주석 3개의 요지다. 각 주석이 어떤 지정자의 것인지 고르고 내 말로 옮기라. (힌트: archetype은 클래스 기본값, instance는 레벨에 놓은 개체)
가. can be edited by property windows, on archetypes and instances
나. visible in all property windows, but cannot be edited
다. Specifies the category of the property

### P1-036 (0.29점)

[설명형] (1) 다음 상황마다 NewObject·CreateDefaultSubobject·SpawnActor 중 무엇을 쓰는지 고르고 이유를 한 줄로 쓰라.
가. AArenaCharacter 생성자에서 카메라 붐(SpringArm) 컴포넌트를 만든다.
나. 게임 도중 퀘스트 진행 정보를 담는 UQuestData(UObject 파생) 객체를 하나 만든다.
다. 웨이브 매니저가 레벨에 적 AEnemyGoblin을 소환한다.
(2) 학생이 AArenaCharacter 생성자 마지막 줄에 GetWorld()->SpawnActor<AArenaWeapon>(WeaponClass); 를 넣었더니 에디터를 켤 때 크래시가 났다. 원인과 고치는 방법을 설명하라.
(3) CDO가 무엇인지 설명하라. BP_ArenaCharacter의 기본값 창에서 MaxHealth를 100에서 150으로 바꾸면 내부에서 무엇이 바뀌고, 그 뒤 새로 스폰하는 캐릭터는 몇으로 시작하는지 쓰라.

### P1-037 (0.48점)

[설명형] AArenaCharacter에 다음 멤버가 있다.
UPROPERTY() TObjectPtr<UInventory> Inventory;   // NewObject로 생성
UQuestLog* QuestLog;                           // NewObject로 생성, UPROPERTY 없음
(1) 언리얼 GC가 어떤 객체를 살리고 어떤 객체를 지우는지 '루트 → 참조 그래프' 텍스트 그림 1장과 3문장으로 설명하라. 그림에 Inventory와 QuestLog를 모두 넣으라.
(2) QuestLog가 왜 위험한지 설명하라. 수거된 뒤 QuestLog->AddEntry()를 부르면 무슨 일이 생기는지도 쓰라.
(3) UE5에서 UObject 멤버 포인터를 원시 포인터 대신 TObjectPtr로 선언하는 이유를 ObjectPtr.h 상단 주석 내용에 기대어 설명하라.
(4) 적 AI가 '현재 노리는 플레이어'를 기억해야 한다. 적이 플레이어의 생존을 붙잡아 두면 안 된다. 어떤 포인터를 쓰고 사용 전에 무엇을 확인하는지 쓰라.

### P1-038 (0.19점)

[코드 읽기] UGCLabItem은 학생이 만든 빈 UObject 클래스다.

UCLASS()
class AGCLabActor : public AActor
{
    GENERATED_BODY()
    UPROPERTY() TObjectPtr<UGCLabItem> Kept;
    UGCLabItem* Loose = nullptr;            // UPROPERTY 없음
    TWeakObjectPtr<UGCLabItem> WatchKept, WatchLoose;
    FTimerHandle CheckTimer;
protected:
    virtual void BeginPlay() override;
    void Check();
};
void AGCLabActor::BeginPlay()
{
    Super::BeginPlay();
    Kept = NewObject<UGCLabItem>(this);
    Loose = NewObject<UGCLabItem>(this);
    WatchKept = Kept;  WatchLoose = Loose;
    GetWorldTimerManager().SetTimer(CheckTimer, this, &AGCLabActor::Check, 5.f, true);
}
void AGCLabActor::Check()
{
    UE_LOG(LogArena, Warning, TEXT("Kept=%d Loose=%d"), WatchKept.IsValid(), WatchLoose.IsValid());
    UE_LOG(LogArena, Warning, TEXT("%s"), *Loose->GetName());   // (★)
}

Play를 누르고 7초쯤 GC를 강제로 실행했다. 그 사이 자동 GC는 돌지 않았다고 가정한다.
(1) 5초와 10초에 찍힐 첫 번째 로그를 예측하고 이유를 쓰라.
(2) 10초의 (★) 줄에서 무슨 일이 생길 수 있는지 쓰라.
(3) Play 중 GC를 강제로 돌리려면 무엇을 입력하는지, 이 실험에서 왜 GC를 강제로 돌리는지 쓰라.

### P1-039 (0.19점)

[설명형] (1) 다음 값을 FName·FString·FText 중 무엇으로 저장할지 고르고 이유를 한 줄씩 쓰라.
가. 무기를 붙일 소켓 이름 hand_r
나. 퀘스트 창에 보이는 제목 '고블린 소탕'(영어판에서는 영어로 바뀌어야 함)
다. 디버그 로그에 이어 붙일 문장 'Goblin took 25 damage'
(2) NameTypes.h를 보면 FName은 문자열 자체 대신 무엇을 저장하는가? 그것이 FName 비교가 빠른 이유와 어떻게 이어지는지 설명하라. FName(TEXT("Hand_R")) == FName(TEXT("hand_r"))의 결과도 쓰라.
(3) 다음 두 줄을 언리얼 관례에 맞게 고쳐 쓰라.
UE_LOG(LogArena, Warning, "Wave start");
FName Socket = FName("hand_r");

### P1-040 (0.10점)

[코드 읽기] 학생이 프로젝트 전용 로그 카테고리를 만들었다.

// ArenaLog.h
#pragma once
#include "CoreMinimal.h"
_____①_____(LogArena, Log, All);

// ArenaLog.cpp
#include "ArenaLog.h"
_____②_____(LogArena);

// ArenaCharacter.cpp
#include "ArenaLog.h"
void AArenaCharacter::BeginPlay()
{
    Super::BeginPlay();
    UE_LOG(LogArena, Warning, TEXT("Spawned HP=%d"), 100);
    UE_LOG(LogTemp, Warning, TEXT("temp check"));
}

(1) ①과 ②에 들어갈 매크로를 쓰고, 왜 .h와 .cpp에 하나씩 나눠 쓰는지 설명하라.
(2) Play하면 Output Log에 두 로그가 어떻게 보이는지(카테고리·단계·색) 쓰라. LogTemp 대신 LogArena를 쓰면 좋은 점 1가지도 쓰라.
(3) ②를 지우고 빌드하면 어떤 종류의 에러가 나는지 이유와 함께 쓰라.

### P1-041 (0.39점)

[설명형] (1) 레벨에 놓인 액터 하나의 생명주기 함수를 불리는 순서대로 쓰라(생성부터 GC까지).
(2) 유니티 Awake/Start/Update/OnDestroy를 언리얼 함수에 대응시키라. 1:1로 대응하지 않는 부분 하나를 CDO로 설명하라.
(3) Actor.h에서 PostInitializeComponents·BeginPlay·EndPlay·Tick 선언 위 주석을 읽었다. 각 함수가 '언제' 불리는지 내 말로 한 줄씩 쓰라. Tick 주석이 경고하는 설정도 쓰라.
(4) Actor.cpp의 AActor::DispatchBeginPlay와 AActor::BeginPlay를 따라가 보면, 내 액터에 붙은 컴포넌트의 BeginPlay와 블루프린트 Event BeginPlay는 어디서 불리는가? 이것을 바탕으로 엔진 노트 01-actor-lifecycle.md에 넣을 세 요소(콜스택 캡처·유니티 대응표·'Super를 빼먹으면?' 실험)를 각각 어떻게 얻는지 쓰라.

### P1-042 (0.29점)

[코드 읽기] ALifecycleProbe를 부모로 만든 BP 자식 BP_LifecycleProbe를 레벨에 1개 놓았다. 이 BP는 Event BeginPlay에서 Print String으로 'BP Begin'을 찍는다. 함수 순서는 파일에 적힌 순서일 뿐이다.

void ALifecycleProbe::EndPlay(const EEndPlayReason::Type Reason)
{ UE_LOG(LogArena, Warning, TEXT("[K]")); Super::EndPlay(Reason); }

void ALifecycleProbe::BeginPlay()
{ UE_LOG(LogArena, Warning, TEXT("[M]")); Super::BeginPlay(); }

void ALifecycleProbe::Tick(float DeltaTime)
{ Super::Tick(DeltaTime); if (++TickCount <= 2) UE_LOG(LogArena, Warning, TEXT("[P]%d"), TickCount); }

ALifecycleProbe::ALifecycleProbe()
{ PrimaryActorTick.bCanEverTick = true; UE_LOG(LogArena, Warning, TEXT("[Q]")); }

void ALifecycleProbe::PostInitializeComponents()
{ Super::PostInitializeComponents(); UE_LOG(LogArena, Warning, TEXT("[R]")); }

(1) Play를 누르고 3초 뒤 Stop했다. [K][M][P][Q][R]과 'BP Begin'이 찍히는 순서를 쓰라. [Q]가 Play 전에도 찍혀 있을 수 있는 이유도 쓰라.
(2) BeginPlay에서 Super::BeginPlay(); 줄을 지웠다. 'BP Begin'은 찍히는지, 이 액터에 붙은 컴포넌트의 BeginPlay는 불리는지 쓰고, 왜 그런지 설명하라. ([P]·[K] 로그의 변화는 채점하지 않는다.)

### P1-043 (0.29점)

[설명형] 회전 포탑 액터 ATurret을 만든다. 필요한 부분은 ① 받침 메시(충돌 있음) ② 받침 위에서 좌우로 도는 회전축(보이지 않는 기준점) ③ 회전축에 붙은 포신 메시 ④ 체력 로직이다.
(1) ①~④ 각각을 UActorComponent·USceneComponent·UPrimitiveComponent(예: StaticMeshComponent) 중 무엇으로 만들지 고르고 이유를 쓰라. 무엇을 RootComponent로 둘지, 부착 계층(부모-자식)은 어떻게 할지 쓰라.
(2) 유니티에서는 이 포탑을 어떤 구조로 만들었을지, 언리얼의 'Actor + 여러 Component'와 대응해 설명하라.
(3) 포신의 상대(Relative) 위치는 회전축 기준 (80,0,0)이다. 회전축은 받침 기준 (0,0,100)이고, 액터는 월드 (500,200,0)에 있다(회전 없음). 포신의 월드 위치를 구하라. 그 뒤 액터를 (700,200,0)으로 옮기면 포신의 상대 위치와 월드 위치가 각각 어떻게 되는지 쓰라. SceneComponent.h에서 본 상대/월드 Transform 개념으로 설명하라.

### P1-044 (0.29점)

[설명형] 적 80마리가 나오는 스트레스 맵에서 게임 스레드 시간이 높다. 적 AEnemyGoblin의 Tick에서 지금 다음 일을 매 프레임 한다.
가. 플레이어와의 거리를 재서 1500 안이면 추격 시작
나. 3초마다 체력 1 회복(누적 시간 변수로 직접 계산)
다. 피격 후 0.5초 동안 메시 색을 빨강→원래 색으로 부드럽게 보간
라. 체력바 위젯에 매 프레임 현재 체력 숫자를 넣음
(1) 가~라를 각각 Tick 유지 / TickInterval / SetActorTickEnabled로 필요할 때만 / 타이머 / 델리게이트 이벤트 중 무엇으로 바꿀지 고르고 이유를 쓰라. 타이머와 Tick을 고르는 기준을 한 문장으로 쓰라.
(2) 다로 인해 Tick이 '피격 직후 0.5초 동안만' 필요하다. 참고: PrimaryActorTick.bCanEverTick이 false인 액터는 Tick 함수가 아예 등록되지 않아, 나중에 SetActorTickEnabled(true)를 불러도 Tick이 돌지 않는다. 생성자와 피격 처리에서 Tick 설정을 어떻게 할지 쓰라(bCanEverTick 값 포함).
(3) 이렇게 정리하면 적이 많을 때 어떤 비용이 줄어드는지 설명하라.

### P1-045 (0.29점)

[설명형] 유니티로 만든 웨이브 게임의 GameManager가 다음 일을 모두 했다.
가. 적 소환 규칙과 승리·패배 판정
나. 남은 시간과 현재 웨이브 번호(모든 플레이어 화면에 표시)
다. 플레이어별 점수·닉네임
라. 키보드·마우스 입력을 받아 캐릭터에 전달
마. 화면 구석의 조준점·점수판 그리기
바. 실제로 걷고 점프하는 플레이어 몸체
(1) 가~바를 언리얼 GameMode·GameState·PlayerController·Pawn/Character·PlayerState·HUD에 하나씩 나눠 담으라. 각 클래스의 역할을 한 줄씩 쓰라.
(2) 2인 멀티플레이라면 GameMode와 GameState가 각각 어느 컴퓨터에 존재하는지 쓰라. 나를 GameMode에 두면 생기는 문제를 설명하라.
(3) 유니티에서는 이 일을 왜 GameManager 하나가 했고, 언리얼은 왜 나눠 두었는지 쓰라.
(4) AArenaGameMode가 Play 때 내 AArenaCharacter와 AArenaPlayerController를 만들게 하려면 GameModeBase.h의 어떤 속성에 무엇을 지정하는지 쓰라. InitGame이 언제 불리는 함수인지도 쓰라.

### P1-046 (0.19점)

[설명형] (1) ACharacter를 상속하면 기본으로 들어 있는 컴포넌트 3개와 각 역할을 쓰라. 3인칭 카메라를 위해 추가하는 컴포넌트 2개와 각 역할도 쓰라. 점프와 이동 컴포넌트 접근 함수를 Character.h에서 찾았다면 그 이름을 쓰라.
(2) '컨트롤러 회전'과 '캐릭터(액터) 회전'의 차이를 설명하라. 다음 두 설정에서 마우스를 오른쪽으로 돌리고 W(앞)를 누르면 캐릭터 몸이 어떻게 도는지 각각 쓰라.
설정 X: bUseControllerRotationYaw = true, CMC의 bOrientRotationToMovement = false
설정 Y: bUseControllerRotationYaw = false, CMC의 bOrientRotationToMovement = true
(3) 유니티 CharacterController와 Input System의 Action / Action Map은 언리얼에서 각각 무엇에 대응하는가? 대응 이유를 한 줄씩 쓰라.

### P1-047 (0.29점)

[설명형] 걷는 중에는 E가 '상호작용', I가 '인벤토리 열기'다. 인벤토리 UI가 열려 있으면 E가 '아이템 사용', WASD가 '슬롯 이동'이어야 한다.
(1) Enhanced Input의 InputAction(IA), InputMappingContext(IMC), Trigger, Modifier, ETriggerEvent가 각각 무슨 역할인지 한 줄씩 쓰라. 이 상황에서 각각 어떤 것을 만들지 예를 들라.
(2) IMC를 IMC_Default와 IMC_Inventory 두 개로 나누는 이유를 쓰라. 인벤토리를 열고 닫을 때 로컬 플레이어 서브시스템에 무엇을 하는지, AddMappingContext의 Priority 값을 어떻게 줄지 쓰라. 그 매개변수가 무슨 뜻인지도 쓰라.
(3) EnhancedInputComponent.h의 BindAction 오버로드를 읽었다면, 입력에 바인딩할 수 있는 함수 형태 2가지 이상을 쓰라. IA_Interact를 Started에, IA_Move를 Triggered에 묶는 이유도 쓰라.
(4) 엔진 노트 02에 그릴 '키 → … → 바인딩 함수' 흐름도를 텍스트로 그리라. E 키가 AArenaCharacter::Interact까지 가는 길을 예로 들라.

### P1-048 (0.39점)

[설명형] 플레이어가 (200,100,0)에 서서 정면 Forward = (1,0,0)을 보고 있다. 적은 (500,500,0)에 있다. 시야는 정면 기준 좌우 60°(총 120°)다. 참고: cos45°≈0.71, cos53°≈0.60, cos60°=0.50, cos127°≈-0.60
(1) 플레이어→적 벡터 ToTarget과 그 길이를 구하라. 정규화한 방향 벡터를 구하고, 정규화가 무슨 뜻인지 쓰라.
(2) Forward와 정규화된 방향의 내적을 구하라. 이것으로 적이 앞인지 뒤인지, 사이각이 약 몇 도인지, 시야 안인지를 판정하고 근거를 쓰라. 정규화하지 않은 ToTarget으로 내적하면 값이 얼마이고 무엇이 잘못되는지 쓰라.
(3) Forward × 방향(외적)의 Z 성분을 구해 적이 좌·우 어느 쪽인지 판정하라. 이 부호 해석을 디버그 드로잉으로 꼭 확인하라고 하는 이유를 쓰라.
(4) 유니티 Vector3.Dot / Vector3.Cross에 대응하는 언리얼 함수와, Vector.h에서 찾은 연산자 버전을 쓰라.

### P1-049 (0.19점)

[설명형] (1) FRotator와 FQuat는 각각 어떤 용도로 쓰는지 쓰라. 쿼터니언을 쓰는 이유 3가지를 쓰라(짐벌락이 무엇인지 한 줄 포함).
(2) 액터가 월드 (500,0,0)에 있고 Yaw 90°만 돌아 있다(스케일 1). 액터 로컬 좌표 (100,0,0)에 있는 총구 소켓의 월드 좌표를 구하라. 로컬 좌표와 월드 좌표의 차이도 설명하라.
(3) 유니티에서 쓰던 '앞=+Z, 위=+Y' 감각으로 언리얼 코드를 쓰면 어떤 실수가 나는지, 두 엔진의 좌표계(손잡이·위·앞)를 비교해 쓰라.
(4) 면접에서 '게임에 쓰는 3D 수학 요점을 30초로 말해 보라'고 했다. 핵심 4가지를 한 줄씩 쓰라.

### P1-050 (0.29점)

[코드 읽기] W4 방향 판정을 재사용한 피격 방향 코드다. Hit*Montage는 UPROPERTY로 지정한 몽타주다. 참고: KismetAnimationLibrary의 CalculateDirection(Velocity, BaseRotation)은 BaseRotation 정면 기준 Velocity 방향 각도를 -180~180으로 돌려주며, 오른쪽이 +다.

float AArenaCharacter::CalcHitAngle(const FVector& AttackerLoc) const
{
    const FVector Forward = GetActorForwardVector();        // 정면, 길이 1
    FVector ToAttacker = AttackerLoc - GetActorLocation();
    ToAttacker.Z = 0.f;                                     // 높이 차 무시
    ToAttacker = _______①_______;
    const float Dot = FVector::DotProduct(Forward, ToAttacker);
    float Angle = FMath::RadiansToDegrees(FMath::Acos(Dot)); // 0~180
    const FVector Cross = FVector::CrossProduct(Forward, ToAttacker);
    if (_______②_______) { Angle = -Angle; }
    DrawDebugLine(GetWorld(), GetActorLocation(), AttackerLoc,
        Angle > 0.f ? FColor::Red : FColor::Blue, false, 2.f);
    return Angle;                                           // -180~180
}
UAnimMontage* AArenaCharacter::SelectHitMontage(float Angle) const
{
    if (Angle >= -45.f && Angle <= 45.f) return HitFrontMontage;
    if (Angle > 45.f && Angle < 135.f)   return HitRightMontage;
    if (Angle < -45.f && Angle > -135.f) return HitLeftMontage;
    return HitBackMontage;
}

(1) ①에 들어갈 처리를 코드나 말로 쓰라. ①이 없으면 무엇이 틀어지는지 쓰라. ②의 조건을 쓰고, 왜 그 조건인지 쓰라.
(2) 캐릭터는 (0,0,0)에서 +X를 보고 있다. 공격자 P(0,-400,0), Q(-100,300,0), R(-600,50,0) 각각에 대해 Angle의 부호와 대략 범위, 선택되는 몽타주, 디버그 선 색을 쓰라.
(3) 학생이 같은 상황에서 CalculateDirection(공격자 방향 벡터, GetActorRotation())을 함께 로그로 찍었더니, 크기는 같은데 부호가 모두 반대였다. 어느 줄을 어떻게 잘못 썼을 가능성이 높은지 쓰라.

### P1-051 (0.29점)

[설명형] 상호작용 인터페이스를 만든다. 문 ADoorActor는 C++에서 구현하고, 보물상자 BP_Chest는 블루프린트의 Class Settings에서 인터페이스를 추가해 구현한다.

UINTERFACE(MinimalAPI, Blueprintable)
class U_____ : public _____ { GENERATED_BODY() };

class ACTIONARENA_API I_____
{
    GENERATED_BODY()
public:
    UFUNCTION(BlueprintNativeEvent, BlueprintCallable)
    void Interact(AActor* Interactor);
};

(1) 빈칸을 채우라. 언리얼 인터페이스가 이렇게 U 클래스와 I 클래스 두 개로 나뉜 이유를 리플렉션과 연결해 설명하라.
(2) 플레이어 코드가 다음과 같다.
if (Cast<IInteractable>(Target) != nullptr)
{
    IInteractable::Execute_Interact(Target, this);
}
문은 반응하는데 상자는 반응하지 않는다. 이유를 설명하고 바르게 고친 호출 코드를 쓰라.
(3) C# interface와 비교해 언리얼 방식의 대응 관계를 설명하라.

### P1-052 (0.39점)

[설명형] UHealthComponent가 체력 변화를 알린다. 이것을 듣는 쪽은 ① 블루프린트로 만든 체력바 위젯, ② C++ 사운드 관리자 UArenaSoundSubsystem의 OnHurt 함수, ③ 캐릭터 안에서 잠깐 쓰는 C++ 람다, 이렇게 셋이다.
(1) 델리게이트 4종(단일/멀티캐스트 × 일반/다이나믹)이 각각 무엇이 다른지 쓰라. 이 체력 변화 알림 OnHealthChanged에 어떤 종류를 고를지와 이유를 쓰라.
(2) DelegateCombinations.h의 매크로 이름 규칙을 근거로, 새 체력과 변화량(float 2개)을 넘기는 델리게이트 타입 FOnHealthChanged 선언 한 줄을 쓰라. 같은 매개변수를 C++ 내부에서만 쓴다면 선언이 어떻게 달라지는지도 쓰라.
(3) ② 사운드 관리자 안에서 OnHurt를 OnHealthChanged에 바인딩하는 한 줄을 쓰고, OnHurt 선언에 꼭 필요한 것을 쓰라. ③ 람다를 OnHealthChanged에 바로 붙일 수 없는 이유를 쓰라. 그래서 컴포넌트에 같은 매개변수의 C++ 전용 델리게이트 OnHealthChangedNative((2)의 두 번째 선언 타입)를 하나 더 두었다. 캐릭터가 람다를 여기에 붙이는 한 줄을 쓰라. 끝으로, 사운드 관리자가 종료될 때 OnHealthChanged에서 자기 바인딩을 한 번에 해제하는 한 줄을 쓰라.
(4) 다이나믹 델리게이트의 비용을 쓰라. C# event·Action·UnityEvent가 언리얼의 무엇에 대응하는지 쓰라.

### P1-053 (0.19점)

[설명형] 레버 ALever 1개로 문 ADoorActor 2개를 연다. 조건은 '레버는 문 클래스를 몰라야 한다'이다.
(1) 옵저버 패턴을 '보내는 쪽/받는 쪽'으로 설명하라. 언리얼 델리게이트 Broadcast가 왜 그 예인지 쓰라.
(2) 다음 세 설계를 장단점으로 비교하라.
가. 레버가 TArray<ADoorActor*>를 들고 레버가 직접 Door->Open()을 부른다.
나. 레버가 OnToggled 멀티캐스트 델리게이트를 가지고, 각 문이 자기가 연결될 레버를 에디터에서 지정받아 BeginPlay에서 바인딩한다.
다. 레버가 TArray<AActor*> 대상 목록을 들고, 인터페이스가 구현됐는지 확인해 Execute_로 호출한다.
(3) 6개월 포트폴리오 규모라는 전제로 하나를 골라 근거를 쓰라. 나중에 '레버로 함정도 켜기'가 추가될 때 고른 설계에서 무엇을 고쳐야 하는지 쓰라.

### P1-054 (0.19점)

[설명형] 학생의 UInteractionComponent 코드 일부다.

void UInteractionComponent::BeginPlay()
{
    Super::BeginPlay();
    GetWorld()->GetTimerManager().SetTimer(FocusTimer, this, &UInteractionComponent::UpdateFocus, 0.1f, true);
}
void UInteractionComponent::UpdateFocus()
{
    const FVector Start = CameraLocation();
    const FVector End = Start + CameraForward() * 300.f;
    FHitResult Hit;
    const bool bHit = GetWorld()->SweepSingleByChannel(Hit, Start, End, FQuat::Identity,
        ECC_Visibility, FCollisionShape::MakeSphere(20.f));
    AActor* NewFocus = bHit ? Hit.GetActor() : nullptr;
    if (NewFocus != Focused) { Focused = NewFocus; OnFocusChanged.Broadcast(Focused); }
}

(1) 이 코드가 언제, 무엇을, 얼마나 자주 하는지 흐름으로 설명하라.
(2) 유니티로 같은 일을 했다면 타이머 부분과 트레이스 부분을 각각 무엇으로 만들었을지 쓰라(코루틴·InvokeRepeating·Physics.Raycast 중심으로).
(3) SweepSingleByChannel 대신 LineTraceSingleByChannel을 쓰면 무엇이 달라지는지 쓰라. 상호작용 포커스에 구(Sphere)를 쓰는 장점도 쓰라.
(4) 컴포넌트가 상호작용을 그만해야 할 때 반복 타이머를 멈추는 방법을 쓰라.

### P1-055 (0.29점)

[설명형] 학생이 UArenaAnimInstance를 만들었다. 지금 NativeUpdateAnimation에서 매 프레임 Cast<AArenaCharacter>(TryGetPawnOwner())를 하고, Speed·bIsInAir를 계산한다. NativeInitializeAnimation은 비어 있다.
(1) Animation Blueprint의 EventGraph와 AnimGraph가 각각 무슨 일을 하는지 쓰라. C++ AnimInstance의 계산이 어느 쪽 역할을 대신하는지 쓰라.
(2) 위 코드를 고쳐, NativeInitializeAnimation과 NativeUpdateAnimation에서 각각 할 일을 나눠 쓰라. 그렇게 나누는 이유를 쓰라.
(3) 1D 블렌드스페이스에 Idle(Speed 0), Walk(Speed 200), Run(Speed 600)을 놓았다. Speed가 300이면 어떤 애니메이션이 대략 어떤 비율로 섞이는지 쓰라. 2D 블렌드스페이스로 바꿀 때 추가하는 축은 무엇인지 쓰라.
(4) 점프 상태 머신을 Idle/Move → JumpStart → Fall(Loop) → Land → Idle/Move로 만든다. 각 트랜지션 룰에 쓸 조건을 bIsInAir와 애니메이션 진행 상태로 쓰라.

### P1-056 (0.19점)

[설명형] (1) 3단 콤보 마지막 타격에서 캐릭터가 앞으로 한 걸음 내딛는다. 이 이동을 루트 모션으로 처리한다는 것이 무슨 뜻인지 쓰라. 장점과, 멀티플레이를 고려해 Root Motion Mode를 'Root Motion from Montages Only'로 두는 이유를 쓰라.
(2) 유니티 Animator Controller의 파라미터·상태·트랜지션이 언리얼 AnimBP의 무엇에 대응하는지 쓰라.
(3) 유니티는 스크립트가 animator.SetFloat("Speed", v)로 값을 '밀어 넣고', 언리얼은 AnimInstance가 매 프레임 값을 '당겨온다'. 이 두 구조의 차이와 각각의 장단점을 쓰라. 언리얼 방식이 멀티스레드 애니메이션 업데이트와 어떻게 연결되는지도 쓰라.
(4) 엔진 노트 03-anim-update.md에 넣을 '밀어 넣기 vs 당겨오기' 구조를 텍스트 화살표 그림 2개로 그리라.

### P1-057 (0.29점)

ComboMontage에는 섹션 Attack1, Attack2, Attack3이 있고, 에디터에서 섹션끼리 연결(다음 섹션 지정)은 하지 않았다. bComboWindowOpen은 콤보 입력 구간 NotifyState가 열고 닫는다. Montage_IsPlaying은 몽타주가 재생 중인지 돌려주는 함수다.

void UCombatComponent::BeginPlay()
{
    Super::BeginPlay();
    AnimInstance = OwnerMesh->GetAnimInstance();
    AnimInstance->OnMontageEnded.AddDynamic(this, &UCombatComponent::HandleMontageEnded);
}
void UCombatComponent::Attack()
{
    if (!AnimInstance->Montage_IsPlaying(ComboMontage))
    {
        ComboIndex = 1;
        AnimInstance->Montage_Play(ComboMontage);                  // (가)
        return;
    }
    if (bComboWindowOpen && ComboIndex < 3)
    {
        const FName Cur  = *FString::Printf(TEXT("Attack%d"), ComboIndex);
        const FName Next = *FString::Printf(TEXT("Attack%d"), ComboIndex + 1);
        AnimInstance->Montage_SetNextSection(Cur, Next, ComboMontage); // (나)
        ComboIndex++;
    }
}
void UCombatComponent::HandleMontageEnded(UAnimMontage* Montage, bool bInterrupted)
{
    if (Montage != ComboMontage) return;                            // (다)
    ComboIndex = 0;
    bComboWindowOpen = false;
}

(1) 몽타주의 Section과 Slot은 각각 무엇인가? AnimBP 쪽에 무엇이 없으면 (가)를 호출해도 화면에 애니메이션이 안 보이는가?
(2) 플레이어가 ① 처음 공격, ② Attack1 재생 중 입력 구간 안에서 공격, ③ Attack2 재생 중 입력 구간 밖에서 공격을 눌렀다. 재생되는 섹션 순서와 몽타주가 끝난 뒤 ComboIndex 값을 쓰라.
(3) (나)를 Montage_JumpToSection(Next, ComboMontage)로 바꾸면 무엇이 달라지는가?
(4) Attack2 도중 피격 몽타주가 같은 슬롯에서 재생되어 콤보 몽타주가 끊겼다. HandleMontageEnded는 불리는가? bInterrupted 값은? (다)가 필요한 이유는? 또 OnMontageBlendingOut에 바인딩했다면 호출 시점이 어떻게 다른가?

### P1-058 (0.19점)

공격 몽타주에 다음 다섯 가지를 붙이려 한다. 각각 AnimNotify와 AnimNotifyState 중 무엇이 맞는지 고르고 이유를 쓰라.
① 발이 땅에 닿는 순간 발소리 ② 칼날이 휘둘러지는 동안 무기 궤적 이펙트 ③ 무기 히트 판정이 켜져 있어야 하는 구간 ④ 다음 콤보 입력을 받아 주는 구간 ⑤ 공격 시작 순간 기합 사운드 1회
그리고 (2) AnimNotifyState의 Begin·Tick·End가 ③에서 각각 무슨 일을 하면 좋은지 쓰라. (3) 유니티에서 같은 일을 하던 Animation Event와 StateMachineBehaviour의 OnStateEnter/OnStateExit는 언리얼의 무엇에 대응하는지 설명하라.

### P1-059 (0.29점)

3단 콤보를 만든다.
(1) '콤보 입력 윈도우(입력 버퍼링)'란 무엇이고, 이것이 없으면 플레이어가 어떤 불편을 겪는가?
(2) 입력 버퍼링의 두 방식 — 노티파이 윈도우 방식(입력 구간 NotifyState가 열려 있을 때 들어온 입력만 다음 섹션 예약)과 입력 큐 방식(입력을 큐/버퍼에 저장해 두고 섹션 전환 시점에 꺼내 처리) — 을 장단점으로 비교하라.
(3) 히트 판정을 AnimNotifyState의 Begin/End에만 맡겼을 때 판정이 '켜진 채로 남거나' 누락되는 상황 3가지를 쓰고, 어떤 안전장치를 어디에 두는지 쓰라.
(4) 엣지 케이스 체크리스트를 4개 이상 쓰라(공격 중 피격, 몽타주 중단 포함).

### P1-060 (0.29점)

대검 휘두르기가 t.MaxFPS 30에서 샌드백을 가끔 그냥 통과한다. 현재는 칼날에 붙인 캡슐 콜리전의 Overlap 이벤트로 판정한다.
(1) 왜 빠른 무기가 Overlap 판정에서 통과하는지 설명하고, 소켓 2개(칼날 시작/끝) 기반 Sweep 판정이 이를 어떻게 막는지 쓰라. 두 방식의 장단점을 비교하라.
(2) 커스텀 채널 'Weapon'을 만들었다. Object Channel과 Trace Channel의 차이를 쓰고, 무기 Sweep이 적 몸은 맞히고 바닥·다른 무기는 무시하게 하려면 각 컴포넌트의 응답(Block/Overlap/Ignore)을 어떻게 생각해야 하는지 쓰라.
(3) Sweep 결과 FHitResult로 ① 피 이펙트를 맞은 지점에 표면 방향으로 생성 ② 머리를 맞히면 2배 데미지를 구현하려 한다. 각각 FHitResult의 어떤 정보를 쓰는가?
(4) 유니티의 Layer Collision Matrix와 비교해 설명하라.

### P1-061 (0.29점)

현재 코드 상황:
- AArenaPlayerCharacter: Health/MaxHealth, 데미지 받으면 체력 감소, 체력 0이면 Die()(래그돌 → 입력 차단 → 5초 뒤 Destroy → 게임오버 UI 표시), 콤보 공격·판정 코드 400줄이 캐릭터 클래스 안에 있음
- AArenaEnemy: Health/MaxHealth, 같은 체력 감소 코드 복사본, Die()(래그돌 → BT 정지 → 5초 뒤 Destroy → 남은 적 수 감소)
어제 플레이어의 체력 계산 버그를 고쳤는데 적 쪽은 그대로라 버그가 남았다.
(1) 콤보·판정 코드를 캐릭터 클래스가 아니라 UCombatComponent로 분리하는 이유를 쓰라.
(2) 공통 부모 AArenaCharacterBase로 올릴 것과 자식에 남길 것을 나눠 쓰라.
(3) Die()의 '공통 흐름은 부모, 다른 부분만 자식'을 virtual/override로 설계하라(함수 선언 수준).
(4) 이 리팩터링이 어제 같은 버그 상황을 어떻게 바꾸는지 쓰라.

### P1-062 (0.39점)

무기 Sweep이 적을 맞혔을 때 다음을 호출한다.

UGameplayStatics::ApplyPointDamage(HitActor, 25.f, SwingDir, Hit,
    OwnerController, GetOwner(), UDamageType_Slash::StaticClass());

(1) 이 호출 후 적의 UHealthComponent가 체력을 깎기까지 엔진 안에서 어떤 함수·델리게이트를 거치는지 순서대로 쓰라. 엔진 소스의 어느 함수 구현에서 델리게이트가 브로드캐스트되는가?
(2) 일곱 인자가 각각 무엇인지 쓰고, 같은 상황에서 ApplyDamage를 쓰지 않고 ApplyPointDamage를 쓰는 이유를 쓰라.
(3) UDamageType_Slash(학생이 만든 UDamageType 자식)를 넘기는 이유는? 넘기지 않으면(nullptr) 어떻게 되는가?
(4) 적 클래스가 TakeDamage를 override해 '방어 중이면 데미지 절반'을 구현했는데 Super::TakeDamage 호출을 빼먹었다. 무슨 일이 생기는가?
(5) 유니티에서 hit.SendMessage("TakeDamage", 25)로 하던 것과 비교하라.

### P1-063 (0.29점)

다음 코드를 읽고 답하라. FEnemyStatRow는 FTableRowBase를 상속한 행 구조체(MaxHealth 등)이고, StatTable은 UPROPERTY(EditAnywhere) TObjectPtr<UDataTable>이다. State.Dead 태그는 프로젝트에 등록돼 있다.

void UHealthComponent::BeginPlay()
{
    Super::BeginPlay();
    const FEnemyStatRow* Row = StatTable->FindRow<FEnemyStatRow>(StatRowName, TEXT("Health"));
    MaxHealth = Row->MaxHealth;                                   // (가)
    Health = MaxHealth;
    GetOwner()->OnTakeAnyDamage.AddDynamic(this, &UHealthComponent::HandleAnyDamage);
}

void UHealthComponent::HandleAnyDamage(AActor* DamagedActor, float Damage,
    const UDamageType* DamageType, AController* InstigatedBy, AActor* DamageCauser)
{
    Health = FMath::Clamp(Health - Damage, 0.f, MaxHealth);
    OnHealthChanged.Broadcast(Health, MaxHealth);
    if (Health <= 0.f)                                            // (나)
    {
        StateTags.AddTag(FGameplayTag::RequestGameplayTag(TEXT("State.Dead")));
        OnDeath.Broadcast();
    }
}

(1) HealthComponent가 체력을 갱신받는 구조를 '누가 브로드캐스트하고 누가 구독하는가'로 설명하라. HandleAnyDamage 선언에 반드시 붙어야 하는 매크로는 무엇이며 왜인가?
(2) StatRowName이 테이블에 없는 이름이면 (가)에서 무슨 일이 생기는가? 고친 코드를 쓰라.
(3) 이미 죽은 적이 한 번 더 맞으면 (나)에서 무슨 일이 생기는가? State.Dead 태그를 이용해 고쳐라.
(4) 웨이브 시작 시 테이블의 모든 적 행을 순회해 MaxHealth 합계를 구하려 한다. GetAllRows를 쓰는 코드 뼈대를 쓰라.

### P1-064 (0.29점)

다음 두 데이터를 만든다.
- 무기 12종: 무기마다 메시·콤보 몽타주·소켓 이름·판정 반경이 다르고, '검' 계열은 공통 값을 물려받아 일부만 바꾸고 싶다.
- 적 스탯 150종: 모두 같은 열(이름, 체력, 공격력, 이동 속도)이고 기획자가 스프레드시트로 밸런스를 잡는다.
(1) 각각 DataAsset(UPrimaryDataAsset)과 DataTable 중 무엇을 쓰는지 선택 기준과 함께 쓰라.
(2) 유니티에서 무기를 ScriptableObject로, 적 스탯을 CSV를 직접 읽어 파싱하던 경험과 각각 대응시켜 설명하라. DataTable이 직접 파싱보다 나은 점은?
(3) UWeaponData를 UDataAsset이 아니라 UPrimaryDataAsset으로 만들면 무엇이 달라지는가? Primary Asset ID와 Asset Manager가 무엇이고, GetPrimaryAssetId가 어떤 역할을 하는지 설명하라.

### P1-065 (0.19점)

UCombatComponent에 다음 값이 하드코딩돼 있다.
① 검 기본 데미지 25.f ② 콤보 몽타주 경로 문자열 ③ 무기 끝 소켓 이름 "BladeTip" ④ 판정 반경 30.f ⑤ DrawDebug 선 색 FColor::Red ⑥ 적 30종의 체력·공격력 if/else 표 ⑦ 루프 인덱스 최대값 3(콤보 단계 수는 무기마다 다를 수 있음)
(1) 각 값을 (가) 데이터로 뺄지 말지, (나) 뺀다면 DataAsset/DataTable 중 어디로 갈지 정하고 이유를 짧게 쓰라.
(2) 기획자가 데이터에 판정 반경 -5, 비어 있는 몽타주를 넣었다. 방어 코드를 어디에 두고 무엇을 하는지 쓰라.
(3) 이 결정을 ADR-0002 'DataAsset vs DataTable 선택 기준'으로 남긴다. 파일 위치와 맥락·선택지·결정과 이유·결과 항목에 들어갈 핵심을 쓰라.
(4) 데이터 주도 설계가 팀 협업에 주는 이점을 3가지 이상 쓰라.

### P1-066 (0.29점)

C++ 부모 UArenaHUDWidget(BP 자식이 레이아웃 담당)이 체력바를 보여 준다. 플레이어의 UHealthComponent에는 OnHealthChanged(float Health, float MaxHealth) 다이나믹 멀티캐스트 델리게이트가 있다.
(1) NativeConstruct와 NativeDestruct는 각각 언제 호출되는가? OnHealthChanged 구독과 해제를 어디에 두는지, 왜 짝으로 두는지 쓰라.
(2) 동료가 체력바 Percent를 Property Binding(또는 위젯 Tick)으로 매 프레임 Health/MaxHealth를 계산해 넣었다. 델리게이트 방식과 비용을 비교하라.
(3) UPROPERTY(meta=(BindWidget)) TObjectPtr<UProgressBar> HealthBar; 는 무엇을 의미하는가? BP 디자이너에서 프로그레스 바 이름을 HPBar로 지으면 어떻게 되는가? (UserWidget.h의 관련 주석 내용을 떠올려 설명)
(4) 유니티의 Canvas/UGUI에 대응하는 언리얼 UI 시스템은 무엇인가?

### P1-067 (0.29점)

Size Map을 보니 캐릭터 BP 하나가 800MB를 차지한다. UWeaponData에 UPROPERTY(EditAnywhere) TObjectPtr<UStaticMesh> Mesh; 와 TObjectPtr<UAnimMontage> ComboMontage; 가 있고, 캐릭터 BP는 무기 데이터 10개를 배열로 들고 있다.
(1) 왜 캐릭터 하나 로드에 800MB가 따라오는지 하드 레퍼런스의 로드 방식(참조 체인)으로 설명하고, 소프트 레퍼런스와 비교하라.
(2) 메시·몽타주를 소프트 레퍼런스로 바꾼 선언을 쓰라. 또 무기를 쏠 때 스폰할 투사체 '블루프린트 클래스'를 소프트로 참조하는 선언을 쓰라. 둘에 서로 다른 타입을 쓰는 이유는?
(3) TSoftObjectPtr 안에는 실제로 무엇이 저장되는가? 로드 전 .Get()은 무엇을 돌려주는가?
(4) 장착 직전에 메시를 즉시 불러와야 한다면 어떻게 쓰는가? 유니티의 무엇에 대응하며, 자주 쓰면 어떤 문제가 있는가?

### P1-068 (0.29점)

무기 교체 시 UWeaponData::Mesh(TSoftObjectPtr<UStaticMesh>)를 비동기로 불러와 장착한다.

void AArenaPlayerCharacter::EquipWeapon(UWeaponData* Data)
{
    FStreamableManager& SM = UAssetManager::GetStreamableManager();
    SM.RequestAsyncLoad(Data->Mesh.ToSoftObjectPath(),
        [this, Data]() { WeaponMeshComp->SetStaticMesh(Data->Mesh.Get()); });
}

(1) 이 흐름을 '요청 → 로딩 중 → 완료 콜백 → 장착' 4단계로 설명하고, 단계마다 생길 수 있는 버그를 하나씩 쓰라(요청한 캐릭터가 로딩 중 사망·파괴, 로딩 중 무기를 빠르게 두 번 교체, 핸들 해제 포함).
(2) RequestAsyncLoad의 반환값은 무엇이고, 이 코드처럼 반환값을 버리면 어떤 위험이 있는가? (장착 후 컴포넌트가 메시를 참조하는 경우와 비교)
(3) 위 버그들을 막도록 코드를 고쳐라(멤버 핸들 보관, 약한 포인터 확인 포함).
(4) 유니티 Addressables와 대응시켜 설명하라. RequestAsyncLoad와 GetStreamableManager는 각각 어느 엔진 헤더의 어느 클래스에 선언돼 있었는가?

### P1-069 (0.29점)

근접 적 AArenaEnemy를 만든다. 유니티에서는 적 오브젝트에 NavMeshAgent를 붙이고 agent.SetDestination(player.position)으로 쫓게 했다.
(1) 언리얼에서 AAIController와 AArenaEnemy(Pawn)의 관계를 'Possess'를 써서 설명하라. 유니티처럼 적 클래스 안에 AI 로직을 다 넣는 것과 비교해 장점은?
(2) BT 없이 먼저 테스트하려고 AArenaAIController에서 플레이어에게 이동시키려 한다. 호출할 함수와, 도착(또는 실패) 시 처리를 받는 방법을 쓰라. 레벨에 무엇이 없으면 이동이 실패하는가?
(3) 이동이 확인됐으니 BT로 바꾼다. 컨트롤러가 Pawn을 빙의하는 순간 virtual void OnPossess(APawn* InPawn)이 호출된다. 이 함수를 override해 BT를 실행하는 코드를 쓰고, BeginPlay가 아니라 여기서 실행하는 이유를 한 줄로 쓰라.
(4) 유니티 NavMeshAgent.SetDestination과 언리얼 MoveTo의 대응·차이를 쓰라.

### P1-070 (0.29점)

근접 적 요구사항: 평소엔 랜덤 지점으로 순찰하다가, 플레이어를 타깃으로 잡으면 추적하고, 사거리 안이면 공격한 뒤 1.5초 쿨다운을 갖는다. Blackboard 키는 TargetActor(Object), PatrolLocation(Vector), TargetDistance(Float)이다.
(1) Selector와 Sequence의 동작 차이를 '자식이 실패하면 어떻게 되는가'로 설명하라.
(2) 엔진 노트 04-behavior-tree.md에 넣을 BT 구조 그림을 텍스트 트리로 그려라. 각 노드 옆에 종류(Composite/Task/Decorator/Service)를 적어라.
(3) 그림 속 Task·Decorator·Service가 각각 무엇을 하는 노드인지 일반 정의와 함께 네 그림의 예로 설명하라.
(4) 루트 바로 아래를 Sequence로 바꾸면 어떤 문제가 생기는가?

### P1-071 (0.39점)

다음 C++ BT 노드를 읽고 답하라. UCombatComponent::StartAttack()은 공격 몽타주를 재생하고, 몽타주가 끝나면 OnAttackFinished(일반 멀티캐스트 델리게이트)를 브로드캐스트한다.

UBTTask_MeleeAttack::UBTTask_MeleeAttack() { bCreateNodeInstance = true; } // AI마다 노드 인스턴스 생성

EBTNodeResult::Type UBTTask_MeleeAttack::ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
{
    AArenaEnemy* Enemy = Cast<AArenaEnemy>(OwnerComp.GetAIOwner()->GetPawn());
    UObject* Target = OwnerComp.GetBlackboardComponent()->GetValueAsObject(TEXT("TargetActor"));
    if (!Enemy || !Target) return EBTNodeResult::Failed;
    CachedComp = &OwnerComp;
    Enemy->Combat->OnAttackFinished.AddUObject(this, &UBTTask_MeleeAttack::HandleFinished);
    Enemy->Combat->StartAttack();
    return EBTNodeResult::Succeeded;                                   // (가)
}
void UBTTask_MeleeAttack::HandleFinished()
{
    FinishLatentTask(*CachedComp, EBTNodeResult::Succeeded);           // (나)
}

void UBTService_UpdateTargetDistance::TickNode(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory, float DeltaSeconds)
{
    Super::TickNode(OwnerComp, NodeMemory, DeltaSeconds);
    UBlackboardComponent* BB = OwnerComp.GetBlackboardComponent();
    AActor* Target = Cast<AActor>(BB->GetValueAsObject(TEXT("TargetActor")));
    APawn* Self = OwnerComp.GetAIOwner()->GetPawn();
    if (Target && Self) BB->SetValueAsFloat(TEXT("TargetDistance"), FVector::Dist(Target->GetActorLocation(), Self->GetActorLocation()));
}

(1) Blackboard는 무엇이며, 이 코드에서 값을 읽는 곳과 쓰는 곳을 찾아라. 키 이름 문자열이 Blackboard 에셋의 키와 다르면 어떻게 되는가?
(2) (가) 때문에 생기는 버그를 설명하고 무엇으로 바꿔야 하는지 쓰라. (나)는 어떤 역할인가?
(3) 공격 중 플레이어가 사라져 Observer Aborts로 이 태스크가 중단되었다. 지금 코드에는 무엇이 없어 어떤 문제가 생기는가? AbortTask를 override해 무엇을 하는지 쓰라.
(4) 서비스를 0.4초마다 실행하려면 생성자에서 무엇을 설정하는가? 이 서비스는 언제 실행되고 언제 멈추는가?

### P1-072 (0.29점)

근접 적 BT: Root → Selector [ ① 추적·공격 Sequence (Decorator: Blackboard TargetActor Is Set) , ② 순찰 Sequence (랜덤 지점 이동 → Wait 3초) ]
버그: 순찰 중 플레이어를 발견해 TargetActor가 설정돼도, 적이 Wait 3초를 다 기다리고 나서야 추적을 시작한다.
(1) 왜 이런 일이 생기는지 설명하고, ① 데코레이터의 Observer Aborts를 무엇으로 설정해야 발견 즉시 순찰이 중단되는지 쓰라. Self / Lower Priority / Both 세 값의 의미를 각각 쓰라. 플레이어를 놓쳤을 때 추적도 즉시 멈추게 하려면?
(2) 이 적의 요구사항(순찰·추적·공격·쿨다운) 중 기본 제공 노드로 충분한 부분과 C++ 커스텀 Task·Service로 만들 부분을 나누고 이유를 쓰라.
(3) 팀장이 "새 프로젝트에선 StateTree도 검토하자"고 한다. Behavior Tree와 StateTree의 구조 차이를 쓰라.
(4) 유니티에서 BT를 쓰던 방식과 비교해, 언리얼 BT가 엔진에 내장돼 있다는 점이 개발에 주는 이점을 쓰라.

### P1-073 (0.29점)

[상황] 근접 적 AArenaMeleeEnemy의 AIController에 UAIPerceptionComponent와 시야(Sight) 감각을 붙였다. 시야 설정의 '소속 감지(Detection By Affiliation)'는 '적(Enemies)'만 체크했다. 플레이어 캐릭터 AArenaPlayerCharacter에는 팀 관련 코드를 하나도 넣지 않았다. 플레이를 해 보니 적이 정면 3m 앞의 플레이어를 전혀 감지하지 못한다.

다음에 답하시오.
(1) 유니티에서 같은 '시야 체크'를 직접 만든다면 어떻게 만들었을지 쓰고, 언리얼 AI Perception이 그 대신 해 주는 것을 2가지 이상 쓰시오.
(2) 감지/상실 시점에 Blackboard를 갱신하는 함수 void AArenaMeleeAIController::OnTargetPerceived(AActor* Actor, FAIStimulus Stimulus)를 연결하려 한다. 어떤 이벤트에 어떻게 바인딩하는지(함수 선언에 필요한 매크로 포함), 그리고 그 함수 안에서 '감지'와 '상실'을 무엇으로 구분하는지 쓰시오.
(3) 이 상황에서 감지가 안 되는 가장 유력한 원인을 팀 ID와 태도(Attitude)라는 말을 써서 설명하고, 해결 방법 2가지를 쓰시오.
(4) 원인을 모를 때 쓰는 '시야 감지 점검 순서' 5단계를 순서대로 쓰고, 이 상황의 원인은 몇 번째 단계에서 잡히는지 쓰시오.

### P1-074 (0.19점)

근접 적 AI를 디버깅하는 4가지 상황이 있다. 각 상황에 Gameplay Debugger, Visual Logger, DrawDebug, 중단점 중 가장 알맞은 도구를 하나 고르고 이유를 한 줄로 쓰시오.
(가) 적이 3초쯤 전에 갑자기 추적을 멈추고 순찰로 돌아갔다. 왜 그랬는지 지난 판단을 알고 싶다.
(나) 무기 Sweep 판정 반경이 실제 칼 크기와 맞는지 눈으로 보고 싶다.
(다) 지금 이 순간 적의 Blackboard 값과 BT의 실행 중인 노드를 보고 싶다.
(라) 데미지 계산 함수가 특정 입력에서 음수를 돌려준다. 그 순간 변수 값과 누가 이 함수를 불렀는지 보고 싶다.

이어서 답하시오.
(2) Gameplay Debugger와 Visual Logger의 차이를 '시간'의 관점에서 설명하시오.
(3) (가)를 분석하려고 AArenaMeleeAIController::OnTargetPerceived 안에서 '타깃을 잃었다'는 기록과 타깃 이름을 Visual Logger에 남기는 한 줄을 쓰시오.

### P1-075 (0.29점)

다음은 원거리 적의 화살과 투사체 풀 코드다. AArenaArrow, UProjectilePoolSubsystem(UWorldSubsystem 상속), AArenaArcherController는 학생이 만든 클래스이고, Free는 UPROPERTY TArray<TObjectPtr<AArenaArrow>>다.

// ① ArenaArrow.cpp
AArenaArrow::AArenaArrow()
{
    Collision = CreateDefaultSubobject<USphereComponent>(TEXT("Collision"));
    RootComponent = Collision;
    Movement = CreateDefaultSubobject<UProjectileMovementComponent>(TEXT("Movement"));
    Movement->(가) = 2500.f;   // 발사 속력
    Movement->(나) = true;     // 날아가는 방향으로 화살촉을 돌림
}
// ② ProjectilePoolSubsystem.cpp
AArenaArrow* UProjectilePoolSubsystem::Acquire(const FVector& Loc, const FVector& Dir)
{
    AArenaArrow* A = Free.Num() > 0 ? Free.Pop()
                                    : GetWorld()->SpawnActor<AArenaArrow>(ArrowClass, Loc, Dir.Rotation());
    A->SetActorLocationAndRotation(Loc, Dir.Rotation());
    A->SetActorHiddenInGame((다));
    A->SetActorEnableCollision((라));
    A->Movement->Velocity = (마);   // Dir은 길이 1
    return A;
}
void UProjectilePoolSubsystem::Release(AArenaArrow* A)
{
    A->Movement->StopMovementImmediately();
    A->SetActorHiddenInGame(true);
    A->SetActorEnableCollision(false);
    Free.(바)(A);
}
// ③ ArenaArcherController.cpp (BTService가 0.2초마다 호출)
void AArenaArcherController::UpdateCombat(AActor* Target)
{
    const float Dist = FVector::Dist(GetPawn()->GetActorLocation(), Target->GetActorLocation());
    if (Dist > Stats.MaxRange)      MoveToActor(Target, (사));
    else if (Dist < Stats.MinRange) RetreatFrom(Target);
    else                            { StopMovement(); FireAt(Target); }
}

(1) (가)~(사)를 채우시오. (사)는 '사거리 안쪽까지만 다가간다'는 의도에 맞게 쓰시오.
(2) (마) 줄을 지우면 '처음 스폰된 화살'과 '풀에서 재사용된 화살'은 각각 어떻게 날아가는지 쓰고 이유를 설명하시오.
(3) 기획자가 '벽에 한 번 튕기는 화살'과 '플레이어를 따라가는 화살'을 요청했다. Tick 이동 코드를 새로 짜야 하는지 답하시오.
(4) ③ 코드가 만드는 원거리 적의 행동을 거리 구간 3개로 설명하시오.

### P1-076 (0.19점)

팀 프로젝트 회의에서 팀원이 두 가지를 제안했다.
제안 1: "투사체는 ProjectileMovementComponent 없이 Tick에서 SetActorLocation(현재 위치 + 방향 * 속도 * DeltaTime)으로 직접 움직이자. 그게 더 단순하다."
제안 2: "오브젝트 풀에서 꺼낸 투사체의 초기화(체력 1, 이펙트 켜기)는 BeginPlay에 넣어 두면 재사용할 때도 자동으로 된다."

(1) 제안 1에 반대하는 근거를 3가지 이상 쓰시오.
(2) 제안 2가 틀린 이유를 쓰고, 대신 어떻게 설계해야 하는지 쓰시오.
(3) 풀에 반환할 때 끄고, 꺼낼 때 다시 켜야 하는 것 3가지를 쓰고, 각각 끄지 않으면 생기는 문제를 하나씩 쓰시오.

### P1-077 (0.19점)

Unreal Insights로 같은 맵·같은 PC(전원 연결, 최고 성능 모드)에서 3회씩 측정해 중간값을 정리했다. 목표는 60fps(프레임당 약 16.6ms)다.

| 대상 | 생성 빈도 | 방식 | 1회 비용 | 비고 |
| 화살 투사체 | 초당 약 30발 | SpawnActor/Destroy | 0.40ms | 2~3초마다 4ms 안팎의 프레임 튐 |
| 화살 투사체 | 초당 약 30발 | 풀(Acquire/Release) | 0.03ms | 프레임 튐 사라짐 |
| 적 캐릭터 | 웨이브 시작 때 20마리 | SpawnActor | 0.90ms | 웨이브당 1회, 휴식 시간 중 발생 |
| 데미지 숫자 위젯 | 초당 약 10개 | 생성 | 0.02ms | 측정상 눈에 띄는 튐 없음 |

(1) 표를 해석해 '어디에 풀을 적용하고 어디에는 적용하지 않을지' 결정하고, 숫자를 근거로 이유를 쓰시오.
(2) '측정 후 결정' 원칙이 무엇인지, 측정 없이 모든 것을 풀링하면 무엇이 문제인지 쓰시오.
(3) ADR-0003 '오브젝트 풀을 투사체에만 적용한 이유'의 「결정과 이유」와 「결과(좋아진 점 / 감수한 비용 / 다시 볼 조건)」를 작성하시오.

### P1-078 (0.29점)

유니티로 만든 게임을 언리얼로 옮긴다. 유니티 쪽에는 다음이 있었다.
- GameManager: static Instance 싱글턴 + DontDestroyOnLoad. 최고 기록과 사운드 설정을 들고 메뉴 ↔ 게임 씬을 오가도 유지된다.
- ArrowPool: UnityEngine.Pool의 ObjectPool<Arrow>로 화살을 재사용한다. 게임 씬에서만 쓴다.

(1) 각각을 언리얼에서 무엇으로 옮길지 쓰고, 그 Subsystem의 수명이 왜 그 역할에 맞는지 설명하시오.
(2) 언리얼에서 static 싱글턴 대신 Subsystem을 전역 서비스로 쓰는 이유를 쓰시오.
(3) Subsystem 5종류(Engine·Editor·GameInstance·World·LocalPlayer)의 수명을 각각 한 줄로 쓰시오.
(4) WorldSubsystem.h를 열었을 때 볼 수 있는 ShouldCreateSubsystem, Initialize, Deinitialize가 각각 언제 무엇을 하는 함수인지 쓰고, 화살 풀에서 Initialize·Deinitialize에 넣을 일을 하나씩 쓰시오.

### P1-079 (0.29점)

웨이브 서바이벌에 다음 데이터·함수가 있다. 각각을 AArenaGameMode와 AArenaGameState 중 어디에 둘지 고르시오.
(가) 현재 웨이브 번호
(나) 웨이브 구성 DataTable을 읽어 적을 스폰하는 함수와 스폰 타이머
(다) 남은 적 수
(라) 플레이어 수에 따른 난이도 배율 계산
(마) 휴식 시간의 남은 초
(바) 현재 게임 단계 EArenaPhase 값

(1) (가)~(바)를 분류하시오.
(2) 분류 기준을 한두 문장으로 쓰고, 지금은 싱글플레이인데도 이렇게 나누는 이유(M4 멀티 대비)를 GameMode가 어느 머신에 존재하는지와 연결해 설명하시오.
(3) 엔진 소스 GameStateBase.h에서 PlayerArray를 찾았다. 이것이 무엇인지, 그리고 이것이 GameState에 있다는 사실이 GameState의 역할에 대해 무엇을 말해 주는지 쓰시오.

### P1-080 (0.19점)

학생이 최고 웨이브 기록과 마우스 감도를 저장하는 클래스를 만들었다.

UCLASS()
class UArenaSaveGame : public USaveGame
{
    GENERATED_BODY()
public:
    UPROPERTY() int32 BestWave = 0;
    float MouseSensitivity = 1.0f;
};

게임오버 때 UGameplayStatics::SaveGameToSlot으로 저장한다. 테스트 결과 ① 게임을 다시 켜면 최고 기록은 남아 있는데 마우스 감도는 항상 1.0으로 돌아온다. ② 게임오버 화면이 뜨는 순간 화면이 살짝 멈칫한다.

(1) ①의 원인을 'USaveGame에 무엇이 저장되는가'와 연결해 설명하고 고치시오.
(2) ②의 원인을 설명하고, 어떤 함수로 바꾸며 왜 그게 해결이 되는지 쓰시오.
(3) 유니티의 PlayerPrefs와 비교해 USaveGame이 어떤 점에서 대응되고, 사용 방식은 어떻게 다른지 쓰시오.

### P1-081 (0.19점)

v0.3.0 릴리즈를 위해 Windows 패키징을 했다.

[상황 1] 에디터 PIE에서는 잘 되던 게임이 패키징 단계에서 실패했다. 출력 로그 일부(간략화):
LogCook: Display: Cooking /Game/Maps/L_Arena
LogLinker: Warning: /Game/Weapons/BP_Bow : Failed to load '/Game/FX/NS_ArrowTrail' (file not found)
LogCook: Error: Unable to cook package /Game/Weapons/BP_Bow
Packaging: Error: Cook failed.

[상황 2] 패키징에 성공한 Development 빌드를 지인이 플레이하다 웨이브 3 시작 때 꺼졌다. 크래시 정보의 콜스택 위쪽(간략화):
Unhandled Exception: EXCEPTION_ACCESS_VIOLATION reading address 0x0000000000000090
ActionArena!UArenaWaveSpawner::SpawnNextEnemy() [ArenaWaveSpawner.cpp:87]
ActionArena!FTimerManager::Tick()
ActionArena!UWorld::Tick()

(1) 유니티의 Build Settings → Build와 비교해, 언리얼 패키징에는 무엇이 포함되며 그래서 PIE에서는 안 보이던 문제가 왜 패키징에서 드러나는지 쓰시오.
(2) 상황 1의 로그에서 원인을 읽어 내고, 무엇을 확인·수정할지 쓰시오.
(3) 상황 2에서 로그와 크래시 정보를 찾으려면 어느 폴더들을 보는지 쓰시오.
(4) 상황 2의 콜스택에서 문제가 난 함수와 호출 경로를 쓰고, 가장 유력한 원인과 87번 줄 근처에서 확인할 것을 쓰시오.

### P1-082 (0.39점)

[상황] 2인 협동으로 바꾸는 중이다. 클라이언트 플레이어 P2가 체력 물약을 먹으면 P2의 PC에서 다음 코드가 실행된다.
HealthComponent->Health += 30.f;   // Health는 복제되는 변수, 서버를 거치지 않음
호스트 P1의 PC가 서버 역할을 하며 P1도 함께 플레이한다.

(1) '서버 권위 모델'을 한두 문장으로 설명하시오.
(2) 위 코드가 실행되면 P2 화면, P1(호스트) 화면에서 P2의 체력은 각각 어떻게 보이는지, 그리고 잠시 뒤 서버 복제가 일어나면 P2 화면은 어떻게 되는지 쓰고, 보안 측면의 문제도 쓰시오.
(3) 이 구성은 Listen Server와 Dedicated Server 중 무엇인지 쓰고, 둘의 차이를 쓰시오.
(4) P1의 PC와 P2의 PC에서 NetMode는 각각 어떤 형태를 가리키는지 쓰고, NetMode가 무엇을 알려 주는 값인지 쓰시오.
(5) 올바른 흐름을 한 줄로 쓰시오.

### P1-083 (0.39점)

[상황] Listen Server로 호스트 P1(서버 겸 플레이어)과 클라이언트 P2가 플레이한다. 레벨에는 서버가 조종하는 적 AArenaEnemy가 1마리 있다.

(1) 다음 표의 빈칸에 GetLocalRole() 값(Authority / AutonomousProxy / SimulatedProxy)을 채우시오.
| 액터 | P1(서버) 머신에서 | P2 머신에서 |
| P2의 캐릭터 | (가) | (나) |
| P1의 캐릭터 | (다) | (라) |
| 적 | (마) | (바) |
(2) AutonomousProxy와 SimulatedProxy의 차이를 쓰시오.
(3) AArenaPlayerCharacter::OnHitConfirmed() 안에 두 가지 일을 넣으려 한다: ① 대상에게 데미지 적용(서버만) ② 화면 흔들림과 타격 UI(내가 조종하는 캐릭터에서만). 각각을 감쌀 if 조건을 쓰고 이유를 쓰시오.
(4) 유니티 Netcode의 IsServer, IsOwner는 각각 언리얼의 무엇에 대응하는지 쓰시오.

### P1-084 (0.39점)

다음은 NetLab의 복제되는 문이다. AArenaDoor는 학생이 만든 클래스다.

// ArenaDoor.h (일부)
UPROPERTY(ReplicatedUsing = OnRep_IsOpen)
bool bIsOpen = false;
UFUNCTION()
void OnRep_IsOpen();

// ArenaDoor.cpp
#include "Net/UnrealNetwork.h"
AArenaDoor::AArenaDoor()
{
    bReplicates = true;
}
void AArenaDoor::GetLifetimeReplicatedProps(TArray<FLifetimeProperty>& OutLifetimeProps) const
{
    Super::GetLifetimeReplicatedProps(OutLifetimeProps);
    DOREPLIFETIME(AArenaDoor, bIsOpen);
}
void AArenaDoor::Open()            // 서버에서 호출된다
{
    if (!HasAuthority()) return;
    bIsOpen = true;
    UE_LOG(LogTemp, Log, TEXT("Open() on %s"), HasAuthority() ? TEXT("Server") : TEXT("Client"));
}
void AArenaDoor::OnRep_IsOpen()
{
    UE_LOG(LogTemp, Log, TEXT("OnRep_IsOpen on %s"), HasAuthority() ? TEXT("Server") : TEXT("Client"));
    PlayOpenAnimation();
}

(1) Listen Server(호스트 P1) + 클라이언트 P2 상황에서 서버가 Open()을 호출했다. P1·P2 각 머신에 찍히는 로그를 예측하고, 두 화면에서 문 애니메이션이 재생되는지 쓰시오.
(2) (1)의 문제를 고치는 한 줄과 넣을 위치를 쓰시오. 같은 변수를 블루프린트 RepNotify로 만들었다면 무엇이 달랐을지도 쓰시오.
(3) DOREPLIFETIME(AArenaDoor, bIsOpen) 매크로가 실제로 만들어 내는 코드가 하는 일을 설명하시오. 함수 매개변수 이름 OutLifetimeProps를 다른 이름으로 바꾸면 왜 문제가 되는지도 쓰시오.
(4) 엔진 소스 Actor.h에서 이 코드와 관련해 찾아볼 선언 4가지를 쓰고, 유니티 Netcode for GameObjects에서 이 코드에 대응하는 것을 쓰시오.

### P1-085 (0.39점)

[상황] Listen Server 2인 협동 액션 게임의 네트워크 이벤트를 설계한다.

(1) 다음 4가지를 Server / Client / NetMulticast RPC 중 무엇으로 보낼지, Reliable과 Unreliable 중 무엇을 고를지 쓰고 이유를 한 줄씩 쓰시오.
(가) 클라이언트가 공격 버튼을 눌렀다는 요청
(나) 적이 맞을 때마다 나오는 피격 스파크 이펙트(초당 수십 번 발생 가능)
(다) 특정 플레이어 한 명에게만 '보스 처치 보상 획득' 알림창 띄우기
(라) 캐릭터 발걸음마다 나는 발소리
(2) 학생이 조준 방향을 매 프레임 Reliable Server RPC로 보냈더니 지연 환경에서 점점 반응이 밀리다가 접속이 끊겼다. 이유를 쓰시오.
(3) 레벨에 미리 배치된 레버 액터 ALever에 UFUNCTION(Server, Reliable) void ServerPull();을 만들고, 클라이언트 P2가 레버 앞에서 E키를 누르면 Lever->ServerPull()을 부르게 했다. 서버에서 아무 일도 일어나지 않는다. 이유를 오너십 규칙으로 설명하고 고치는 방법을 쓰시오.
(4) 유니티 Netcode의 ServerRpc/ClientRpc와 언리얼 RPC의 대응을 쓰시오.

### P1-086 (0.39점)

[상황] Listen Server: 호스트 P1(서버 겸 플레이어) + 클라이언트 P2. 레벨에 적 1마리(AIController가 조종)와 복제되는 문이 있다.

(1) 다음 객체가 P1 머신과 P2 머신 중 어디에 존재하는지 표로 쓰시오: GameMode, P1의 PlayerController, P2의 PlayerController, P2의 HUD, P2의 Pawn, P2의 PlayerState, GameState, 적의 AIController.
(2) 문이 열릴 때 '문 열림 상태'와 '문 열리는 소리'를 각각 복제 프로퍼티와 Unreliable Multicast 중 무엇으로 보낼지 쓰고 이유를 쓰시오.
(3) 문이 열린 지 1분 뒤 P3가 접속했다. 문 열림을 Multicast로만 보냈다면 P3에게 문이 어떻게 보이는지, 복제 프로퍼티로 보냈다면 어떻게 보이는지 쓰시오.
(4) P2 머신에서 적 Pawn의 AI 상태를 표시하려고 GetController()를 AAIController로 캐스팅했더니 항상 null이다. 이유를 쓰고, P2가 보고 있는 적 Pawn은 어떤 역할(Role)의 액터인지 쓰시오.

### P1-087 (0.39점)

[상황] Listen Server: 호스트 P1 + 클라이언트 P2. NetLab의 복제되는 문(bIsOpen, ReplicatedUsing=OnRep_IsOpen)과 싱글에서 만든 근접 전투를 2인용으로 바꾸는 중이다.

(1) P2가 문 앞에서 E키를 눌러 문이 열리기까지의 과정을 'Server RPC → 서버에서 상태 변경 → 복제 → 클라이언트 OnRep' 순서로 시퀀스 다이어그램(Mermaid 문법 또는 '보내는 쪽 → 받는 쪽: 메시지' 형식의 줄 목록)으로 쓰시오. 참여자는 P2(클라), P1(서버)이다. HasAuthority 분기가 걸리는 곳과 OnRep이 불리는 곳(호스트 화면 포함)을 표시하시오.
(2) P2가 공격할 때 흐름 '입력 → 몽타주 → 노티파이 판정 → ApplyDamage → 체력 UI'의 각 단계가 P1(서버)·P2(오너 클라) 중 어디서 실행돼야 하는지 표시하고, 판정과 데미지를 그 위치에 두는 이유를 쓰시오.
(3) 엔진 노트 05-network-basics.md의 '어떤 클래스가 어디에 존재하나' 표를 이 상황에 맞게 4행만 쓰시오(GameMode, PlayerController, HUD, Pawn).

### P1-088 (0.29점)

다음은 NetLab 실험 코드다(모두 학생이 만든 클래스). Listen Server: 호스트 P1 + 클라이언트 P2, 나중에 P3가 접속한다. PIE 2인 + 지연 150ms 환경이다.

// ① NetLabButton: 레벨에 배치, Owner 없음
UFUNCTION(Server, Reliable) void ServerPress();
void ANetLabButton::ServerPress_Implementation() { PressCount++; UE_LOG(LogTemp, Log, TEXT("Pressed %d"), PressCount); }
// NetLabCharacter.cpp — P2가 E키를 누름
void ANetLabCharacter::OnInteract() { if (ANetLabButton* B = FindFocusedButton()) B->ServerPress(); }

// ② NetLabLamp: bReplicates = true
UPROPERTY(ReplicatedUsing = OnRep_Color) FLinearColor RepColor;     // 복제 변수
UFUNCTION(NetMulticast, Unreliable) void MulticastColor(FLinearColor C);
void ANetLabLamp::Paint(FLinearColor C)   // 서버에서 t=5초에 호출
{ RepColor = C; MulticastColor(C); }
// 램프는 두 개의 전구가 있다: 전구 A는 OnRep_Color에서, 전구 B는 MulticastColor_Implementation에서 색을 바꾼다(서버에서는 Paint 안에서 둘 다 직접 갱신).

// ③ NetLabCharacter.cpp
DOREPLIFETIME_CONDITION(ANetLabCharacter, SecretAmmo, COND_OwnerOnly);
// 서버가 P2의 캐릭터에 SecretAmmo = 7을 설정

(1) ①에서 P2가 E키를 누르면 서버에 'Pressed' 로그가 찍히는지 쓰고, 이유와 실패 시 로그에서 확인할 내용, 고치는 방법을 쓰시오.
(2) ②에서 Paint(빨강)이 t=5초에 호출되었고 P3가 t=20초에 접속했다. P2와 P3 화면에서 전구 A, 전구 B의 색을 각각 쓰시오(기본 색은 흰색).
(3) ③에서 P2의 캐릭터의 SecretAmmo 값은 P1(호스트) 머신, P2 머신, P3 머신에서 각각 얼마로 보이는지 쓰고(기본값 0), 이 조건을 어떤 데이터에 쓰면 좋은지 예를 하나 드시오.

### P1-089 (0.29점)

[상황] 2인 협동(Listen Server)에서 플레이어의 '3타 콤보' 공격 몽타주를 다른 플레이어 화면에도 보이게 하려 한다. 팀원 두 명이 다른 방법을 제안했다.
- 갑: 서버가 판정한 뒤 NetMulticast(Unreliable) RPC로 모든 머신에서 몽타주를 재생한다.
- 을: 복제 변수(예: ReplicatedUsing으로 묶은 공격 번호)를 서버가 바꾸고, OnRep에서 몽타주를 재생한다.
(1) 패킷 손실 5% 상황과, 공격 도중에 늦게 접속한 클라이언트 상황에서 갑·을 방식이 각각 어떻게 보이는지 비교하시오.
(2) '한 번 휘두르는 공격 연출'과 '30초간 유지되는 방어 자세'에는 각각 어느 방식이 맞는가. 이유는?
(3) 같은 팀원이 "그럼 캐릭터 이동도 직접 Server RPC로 동기화해야겠네"라고 한다. 왜 그럴 필요가 없는지 설명하시오.
(4) (3)의 예측·보정 코드가 엔진 어디에 있는지, 확인할 헤더 파일과 이름 2개를 쓰고 각각 한 줄로 설명하시오.

### P1-090 (0.29점)

[상황] 스프린트를 이렇게 만들었다. Shift를 누르면 클라이언트가 자기 CMC의 MaxWalkSpeed를 600 → 1000으로 바꾸고, 동시에 Reliable Server RPC `ServerSetSprint(true)`를 보낸다. 서버는 RPC를 받으면 서버 쪽 MaxWalkSpeed를 1000으로 바꾼다. 혼자 PIE로 해 보면 문제가 없는데, 친구와 테스트하니 달리기 시작할 때 캐릭터가 뒤로 튕기듯 끊긴다.
(1) 이 현상을 내 PC에서 재현·관찰하려면 어떤 조건을 맞춰 무엇을 보는가. 혼자 PIE에서는 왜 안 보였는가.
(2) 끊김(러버밴딩)이 생기는 이유를 CMC의 예측·검증 흐름으로 설명하시오. 시점 차이가 핵심이다.
(3) 정석 해결 2가지를 쓰시오.
(4) W21 딥다이브 C는 무엇을 만드는 것이고, W15의 이 문제와 어떤 관계인가.
(5) 이 경험을 TS 문서로 남길 때 '재현 단계'와 '원인' 칸에 들어갈 내용을 한 줄씩 쓰시오.

### P1-091 (0.39점)

[상황] 'GA_Dash: 스태미나 20 소모, 쿨다운 3초, 공격 중에는 사용 불가, 대시 중 1초간 피격 무시' 기능을 GAS로 만든다.
(1) GAS 구성요소 5개(ASC·AttributeSet·GameplayEffect·GameplayTags·GameplayAbility)의 관계를 박스와 화살표 그림 1장으로 그리시오. 화살표마다 무엇이 오가는지 짧게 적으시오.
(2) 위 대시 기능의 각 요구사항(스태미나 소모, 쿨다운, 공격 중 불가, 피격 무시)이 5요소 중 어디에 들어가는지 대응시키시오.
(3) 이 중 ASC를 '중심'이라고 부르는 이유를 쓰시오. ASC가 담당하는 일 2가지를 포함하시오.
(4) 유니티에서는 SkillManager·BuffManager를 직접 만들었다. 언리얼의 GAS는 무엇이 다른지 비교해 설명하시오.

### P1-092 (0.39점)

아래는 학생이 만든 UArenaAttributeSet 일부다(UE 5.8).
```cpp
// ArenaAttributeSet.h
#define ATTRIBUTE_ACCESSORS(ClassName, PropertyName) \
  GAMEPLAYATTRIBUTE_PROPERTY_GETTER(ClassName, PropertyName) \
  GAMEPLAYATTRIBUTE_VALUE_GETTER(PropertyName) \
  GAMEPLAYATTRIBUTE_VALUE_SETTER(PropertyName) \
  GAMEPLAYATTRIBUTE_VALUE_INITTER(PropertyName)

UPROPERTY(BlueprintReadOnly, ReplicatedUsing = OnRep_Health)
FGameplayAttributeData Health;
ATTRIBUTE_ACCESSORS(UArenaAttributeSet, Health)
UPROPERTY(BlueprintReadOnly) FGameplayAttributeData IncomingDamage;
ATTRIBUTE_ACCESSORS(UArenaAttributeSet, IncomingDamage)
// MaxHealth, Armor도 같은 방식으로 선언됨

// ArenaAttributeSet.cpp
void UArenaAttributeSet::PreAttributeChange(const FGameplayAttribute& Attribute, float& NewValue)
{
  Super::PreAttributeChange(Attribute, NewValue);
  if (Attribute == GetHealthAttribute())
    NewValue = FMath::Clamp(NewValue, 0.f, GetMaxHealth());
}
void UArenaAttributeSet::PostGameplayEffectExecute(const FGameplayEffectModCallbackData& Data)
{
  Super::PostGameplayEffectExecute(Data);
  if (Data.EvaluatedData.Attribute == GetIncomingDamageAttribute())
  {
    const float Damage = GetIncomingDamage();
    SetIncomingDamage(0.f);                               // (가)
    const float Final = FMath::Max(Damage - GetArmor(), 0.f);
    SetHealth(FMath::Clamp(GetHealth() - Final, 0.f, GetMaxHealth()));
  }
}
```
(1) `ATTRIBUTE_ACCESSORS(UArenaAttributeSet, Health)` 한 줄이 만들어 주는 함수 4개의 이름과 용도를 쓰시오. 이 매크로 정의는 원래 어디에 예시로 있는가.
(2) Health 80, MaxHealth 100, Armor 5에서 IncomingDamage +30짜리 Instant GE가 적용됐다. 처리 후 Health는? 이어서 IncomingDamage +100이 적용되면 Health는?
(3) (가) 줄을 지우면 두 번째 공격부터 어떤 버그가 생기는가.
(4) PreAttributeChange와 PostGameplayEffectExecute가 각각 이 코드에서 하는 일을 한 줄씩 쓰시오.
(5) 데미지를 Health에서 바로 빼지 않고 IncomingDamage를 거치는 이유 2가지를 쓰시오.

### P1-093 (0.39점)

[상황] 아래 GE 4개를 만든다.
- GE_Potion: 체력 +30
- GE_Haste: 10초 동안 이동속도 +200
- GE_Rage: 분노 태그가 붙어 있는 동안 계속 공격력 +10
- GE_StaminaRegen: 계속 유지되며 1초마다 스태미나 +5
(1) 각 GE의 지속 방식(Instant·Duration·Infinite)과 Periodic 여부를 쓰시오. 각 GE가 Base 값과 Current 값 중 무엇을 바꾸는지도 쓰시오.
(2) 이동속도 600에서 GE_Haste가 끝나면 값은 얼마로 돌아오는가. 이유는? 체력 50에서 GE_Potion을 먹고 10초 지나면 체력은?
(3) GameplayEffect.h에서 지속 방식을 정하는 enum 이름은 무엇인가. Modifier 하나를 설정할 때 정하는 3가지는 무엇인가.
(4) GA_Dash를 구현한다. ActivateAbility 안에서 CommitAbility와 EndAbility를 어떤 순서로 부르는지 흐름을 쓰시오. CommitAbility가 실제로 하는 일도 쓰시오.
(5) 스태미나 15(비용 20)이거나 쿨다운이 남은 상태에서 CommitAbility는 어떻게 되는가. 그때 어빌리티 코드는 무엇을 해야 하는가.

### P1-094 (0.39점)

[상황] 2인 협동 웨이브 게임에서 플레이어는 죽으면 5초 뒤 리스폰되고, 리스폰해도 레벨업으로 얻은 스킬과 영구 버프가 유지돼야 한다. 적은 웨이브마다 최대 60마리가 스폰·소멸된다.
(1) 플레이어와 적의 ASC를 각각 PlayerState와 Character 중 어디에 둘지 고르고 이유를 쓰시오. PlayerState에 둘 때 주의할 점 1가지도 쓰시오.
(2) Replication Mode 3종(Full·Mixed·Minimal)이 각각 무엇을 누구에게 복제하는지 쓰시오. 플레이어 ASC, 적 ASC, 혼자 하는 테스트 맵에는 각각 무엇이 맞는가.
(3) 플레이어 ASC 초기화를 서버와 클라이언트에서 각각 어느 함수에서 하는지 쓰시오. 왜 두 곳으로 나뉘는지도 설명하시오.

### P1-095 (0.29점)

아래는 적 근접 공격을 GAS로 바꾼 코드다(UE 5.8, 30줄 이내 발췌).
```cpp
// ArenaEnemy.cpp — ASC는 Character에 있음
void AArenaEnemy::BeginPlay()
{
  Super::BeginPlay();
  AbilitySystemComponent->InitAbilityActorInfo(this, this);
  if (HasAuthority())                                            // (1)
  {
    AttackHandle = AbilitySystemComponent->GiveAbility(
        FGameplayAbilitySpec(SlamAbilityClass, 1));               // (2)
    FGameplayEffectSpecHandle Spec = AbilitySystemComponent->MakeOutgoingSpec(
        InitStatsEffect, 1.f, AbilitySystemComponent->MakeEffectContext());
    AbilitySystemComponent->ApplyGameplayEffectSpecToSelf(*Spec.Data.Get()); // (3)
  }
}
// GA_EnemySlam.cpp
UGA_EnemySlam::UGA_EnemySlam()
{
  InstancingPolicy   = EGameplayAbilityInstancingPolicy::InstancedPerActor; // (4)
  NetExecutionPolicy = EGameplayAbilityNetExecutionPolicy::ServerOnly;       // (5)
}
// BTTask_UseSlam.cpp
EBTNodeResult::Type UBTTask_UseSlam::ExecuteTask(UBehaviorTreeComponent& OwnerComp, uint8* NodeMemory)
{
  AArenaEnemy* Enemy = Cast<AArenaEnemy>(OwnerComp.GetAIOwner()->GetPawn());
  if (!Enemy) return EBTNodeResult::Failed;
  const bool bStarted = Enemy->GetAbilitySystemComponent()
      ->TryActivateAbility(Enemy->GetAttackHandle());              // (6)
  return bStarted ? EBTNodeResult::Succeeded : EBTNodeResult::Failed; // (7)
}
```
(1) (2)(3)(6)의 ASC 함수가 각각 무엇을 하는지 쓰시오. 이 함수들을 직접 확인할 엔진 헤더 이름도 쓰시오.
(2) (1)에서 HasAuthority()로 감싼 이유를 쓰시오.
(3) (4)(5)가 각각 무엇을 정하는 설정인지 쓰고, 두 정책의 정의와 설명을 확인할 엔진 헤더 이름을 쓰시오. 이 적 공격에 ServerOnly가 문제없는 이유도 쓰시오(힌트: AIController가 어디에 있나).
(4) 슬램 몽타주는 1.5초다. (6)(7)이 실행되면 BT는 공격이 끝나기 전에 무엇을 하게 되는가. W10에서 배운 방식으로 고치는 방법을 쓰시오.
(5) 학생은 'AI는 Character에 ASC'라는 결정을 W16에 커뮤니티 GAS 문서와 Lyra 샘플을 참고해 내렸다. 이런 자료를 어떻게 읽어야 하는지 한 줄로 쓰시오.

### P1-096 (0.39점)

아래는 GA_MeleeCombo의 코드다(InstancedPerActor). 몽타주는 1.0초 길이이고, 0.3초와 0.6초에 AnimNotify가 있다. 각 노티파이는 `UAbilitySystemBlueprintLibrary::SendGameplayEventToActor(Owner, Event.Montage.Hit 태그, Payload)`를 호출한다.
```cpp
void UGA_MeleeCombo::ActivateAbility(const FGameplayAbilitySpecHandle Handle,
  const FGameplayAbilityActorInfo* ActorInfo, const FGameplayAbilityActivationInfo ActivationInfo,
  const FGameplayEventData* TriggerEventData)
{
  if (!CommitAbility(Handle, ActorInfo, ActivationInfo))
  { EndAbility(Handle, ActorInfo, ActivationInfo, true, true); return; }
  UE_LOG(LogTemp, Log, TEXT("1 Activate"));

  UAbilityTask_PlayMontageAndWait* MontageTask =
    UAbilityTask_PlayMontageAndWait::CreatePlayMontageAndWaitProxy(this, NAME_None, ComboMontage);
  MontageTask->OnCompleted.AddDynamic(this, &UGA_MeleeCombo::OnMontageCompleted);
  MontageTask->ReadyForActivation();

  UAbilityTask_WaitGameplayEvent* HitTask = UAbilityTask_WaitGameplayEvent::WaitGameplayEvent(
    this, FGameplayTag::RequestGameplayTag(TEXT("Event.Montage.Hit")));
  HitTask->EventReceived.AddDynamic(this, &UGA_MeleeCombo::OnHitEvent);
  HitTask->ReadyForActivation();
  UE_LOG(LogTemp, Log, TEXT("2 Tasks ready"));
}
void UGA_MeleeCombo::OnHitEvent(FGameplayEventData Payload)
{ UE_LOG(LogTemp, Log, TEXT("3 Hit")); /* GE_Damage 적용 */ }
void UGA_MeleeCombo::OnMontageCompleted()
{
  UE_LOG(LogTemp, Log, TEXT("4 Completed"));
  EndAbility(CurrentSpecHandle, CurrentActorInfo, CurrentActivationInfo, true, false);
}
```
(1) AbilityTask란 무엇인지 2줄로 설명하시오.
(2) 몽타주가 끝까지 정상 재생될 때 로그가 찍히는 순서를 쓰시오. '2 Tasks ready'가 '3 Hit'보다 먼저 찍히는 이유를 쓰시오.
(3) 0.2초에 플레이어가 피격되어 몽타주가 중단됐다. 어떤 로그가 찍히고 어떤 로그가 안 찍히는가. 그 뒤 공격 버튼을 다시 누르면 어떻게 되는가. 고치는 방법도 쓰시오.
(4) 이 코드를 이해하려고 확인할 엔진 헤더 3개와, 각 헤더에서 확인할 것을 쓰시오.

### P1-097 (0.29점)

[상황] 팀 회의에서 두 가지가 논의됐다.
- 갑: "피격 이펙트·사운드는 GA_Hit 안에서 직접 스폰하자. GameplayCue는 번거롭다."
- 을: "공격 반응성은 W15처럼 RPC로 두고 클라 예측을 직접 구현하자. GAS 예측은 배우기 어렵다."
(1) 갑에게 GameplayCue를 쓰는 이유 3가지를 설명하시오.
(2) GAS의 로컬 예측이 반응성을 높이는 원리를 쓰시오. 예: 지연 200ms에서 클라가 공격 버튼을 누름 → 서버가 승인/거부하는 두 경우. 예측 키라는 말을 포함하시오.
(3) 을의 주장에 대해 커리큘럼의 ADR-0004 '공격 반응성 개선 방식'은 어떤 선택지를 비교해 무엇으로 결정했는가. 맥락·선택지·결정과 이유·결과 칸에 들어갈 핵심을 한 줄씩 쓰시오.
(4) GAS 도입 비용 3가지와, 어빌리티가 안 켜질 때 쓰는 디버그 명령을 쓰시오. 도입 근거를 ADR로 남기는 이유도 쓰시오.

### P1-098 (0.29점)

[상황] 현재 체력은 UHealthComponent가 맡고 있다. 서버가 Health를 바꾸면 복제되고, OnRep → OnHealthChanged 델리게이트 → HUD 체력바로 이어진다. 데미지는 무기 판정 → ApplyDamage → HealthComponent에서 처리한다. 이것을 UArenaAttributeSet 기반으로 바꾸려 한다.
(1) 기존 기능을 깨지 않고 단계적으로 옮기는 순서를 4~5단계로 쓰시오. 각 단계에서 확인할 것과 PR 단위도 포함하시오.
(2) 한 번에 갈아엎지 않고 단계를 나누는 이유 2가지를 쓰시오.
(3) 교체 후 HUD는 어떤 방식으로 체력 변화를 받는가. W9에서 만든 위젯 쪽 인터페이스를 유지하는 것이 왜 중요한가.
(4) README의 '같은 기능의 진화' 표에 들어갈 '체력' 행을 쓰시오(4단계, 주차와 함께). 각 단계로 바꾼 이유를 한 줄씩 쓰고, 이 표가 면접에서 왜 쓸모 있는지 한 줄로 쓰시오.

### P1-099 (0.29점)

[상황] 적 100마리 스트레스 맵에서 프레임이 떨어진다. `stat unit` 결과는 다음과 같다.
Frame 33.1ms · Game 32.8ms · Draw 9.5ms · GPU 14.2ms
팀원은 "이펙트 머티리얼이 무거워서 그래. 머티리얼부터 줄이자"고 한다.
(1) 병목은 게임 스레드·렌더 스레드·GPU 중 어디인가. 판단 기준과 다음에 할 일을 쓰시오.
(2) '측정 먼저' 원칙에 따라 팀원의 제안을 반박하시오. 측정 없이 최적화하면 생기는 문제를 포함하시오.
(3) 노트북에서 개선 전 측정을 5번 했더니 Game 시간이 31.9 / 33.0 / 45.7 / 32.8 / 33.4ms였다. 측정 전에 맞출 환경 조건 2가지, 대표값과 그렇게 정하는 이유를 쓰시오.
(4) 유니티에서는 Profiler 창을 열고 `Profiler.BeginSample("WaveUpdate")`로 구간을 표시했다. 언리얼에서 대응하는 도구와 코드를 쓰시오.

### P1-100 (0.19점)

[상황] v0.5.0 출시 전에 세 가지 문제를 조사한다. 각 문제에 Unreal Insights의 어떤 도구(CPU 트레이스·Memory Insights·Networking Insights)를 쓸지 고르고, 그 도구로 무엇을 보는지 쓰시오.
① 무기 5종을 비동기 로딩한 뒤 레벨을 바꿔도 메모리 사용량이 계속 늘어난다.
② 2인 협동에서 지연 환경일 때 남은 적 수 HUD가 늦게 바뀐다. 어떤 액터가 복제 트래픽을 많이 쓰는지 알고 싶다.
③ 웨이브 시작 순간 프레임이 튄다. 내 UWaveManager의 SpawnWave 함수가 얼마나 걸리는지 알고 싶다.
(4) ③을 위해 SpawnWave에 측정 매크로를 넣으려 한다. Insights용 매크로와 stat 명령용 매크로 2가지를 각각 어떤 엔진 헤더에서 찾고, 코드에 어떻게 쓰는지 예시로 쓰시오.

### P1-101 (0.29점)

[상황] 2인 협동 맵에 다음 액터가 있다.
- 보물상자 200개: 처음엔 닫혀 있고, 열리면 그 뒤로 상태가 바뀌지 않는다.
- 적 100마리: 계속 움직인다. 서버가 초당 많이 복제 검사를 하고 있다.
- 맵 반대편 동굴의 장식용 회전 기둥 30개: 두 플레이어 모두 동굴 근처에 없다.
서버 CPU와 대역폭이 부족하다.
(1) NetUpdateFrequency가 무엇인지 쓰시오. 적 100마리에 어떻게 조정하고, 낮출 때 감수해야 할 점은 무엇인지 쓰시오.
(2) Dormancy의 원리를 쓰시오. 보물상자에 적용하는 방법과, 상자가 열릴 때 주의할 점을 쓰시오.
(3) Relevancy(관련성)의 원리를 쓰시오. 동굴 기둥에 어떻게 작용하는지 설명하시오.
(4) 세 방법을 적용한 뒤 효과를 무엇으로 확인하는가.

### P1-102 (0.19점)

[상황] 적 100마리 맵에서 Insights를 보니 게임 스레드에서 적의 CMC·애니메이션 업데이트가 큰 비중을 차지한다. 적 대부분은 플레이어에게서 멀거나 카메라 뒤에 있다. 적의 공격 판정은 몽타주의 AnimNotify 시점에 일어난다.
(1) 애니메이션 비용을 줄이는 방법 3가지를 쓰시오. 각각 '어떤 적'에게 효과가 큰지 쓰시오.
(2) 위 방법을 적용할 때, 판정에 쓰는 노티파이가 빠지지 않는지 반드시 확인해야 하는 이유를 구체적인 버그 예로 쓰시오.
(3) 적용 전/후 효과를 어떤 조건으로 비교해 기록하는가.

### P1-103 (0.29점)

[상황] 다음 네 곳에 check·ensure·verify 중 무엇을 쓸지 고르고 이유를 쓰시오.
① UProjectilePoolSubsystem을 얻어 왔는데 nullptr이다. 이 상태로는 이후 모든 투사체 코드가 망가진다.
② 웨이브 DataTable의 한 행에 적 수가 0으로 들어 있다. 개발 중에 알고 싶지만 게임은 기본값 1로 계속 돌아가야 한다. 이 검사는 웨이브마다 불린다.
③ `Pool->ReturnToPool(Projectile)`은 투사체를 풀에 돌려놓고 성공 여부(bool)를 반환한다. 결과가 true인지 확인하고 싶다.
④ 학생이 ③을 `check(Pool->ReturnToPool(Projectile));`로 썼다. Development 빌드에서는 잘 되다가 Shipping 빌드에서만 투사체가 바닥나는 버그가 났다.
(5) ④의 원인을 설명하시오. 세 매크로의 정의와 빌드 구성별 동작을 직접 확인하려면 어떤 엔진 헤더를 여는가. 같은 주에 읽은 AutomationTest.h와 CheatManager.h에서는 각각 무엇을 찾았는지도 한 줄씩 쓰시오.

### P1-104 (0.19점)

[상황] W19 과제로 자동화 테스트를 추가한다.
(1) 오브젝트 풀 반환 테스트를 설계하시오. 준비 → 실행 → 검증 순서로 쓰고, 검증 항목 3가지를 포함하시오(힌트: 재사용 시 BeginPlay가 다시 불리지 않는다).
(2) 게임플레이 태그 상태 전이 테스트를 설계하시오(예: 사망 시 State.Dead가 붙고, 공격 상태가 사라지며, 공격 어빌리티가 막힘). 검증할 것 3가지를 쓰시오.
(3) 커리큘럼이 소개한 언리얼 자동화 테스트 작성 방식 두 가지의 이름을 쓰시오. Simple Automation Test는 어떤 매크로로 테스트를 정의하는지, 두 방식으로 만든 테스트를 어디에서 실행하는지도 쓰시오.
(4) 유니티 Test Framework의 EditMode/PlayMode 테스트와 언리얼 Automation Test/Functional Test의 대응 관계를 쓰시오.
(5) 면접관이 "테스트가 6개뿐이네요?"라고 한다. 신입 포트폴리오에서 테스트가 무엇을 증명하는지 들어 답하시오.

### P1-105 (0.19점)

[상황] 유니티에서 액션 게임을 만들 때 학생은 타격 순간에 `Time.timeScale = 0.05f`를 0.08초 걸고, Cinemachine Impulse로 화면을 흔들었다. 이것을 언리얼 2인 협동 게임(Listen Server)으로 옮기려 한다.
(1) 두 연출에 대응하는 언리얼 기능을 각각 쓰시오.
(2) 유니티처럼 게임 전체 시간을 늦추는 방식(Global Time Dilation)을 2인 협동에서 쓰면 어떤 문제가 생기는지 2가지 쓰시오.
(3) 대신 어떤 액터의 CustomTimeDilation을 얼마 동안, 어떻게 낮추는지 쓰시오. 이 방식이 데미지 판정 로직에 영향을 주지 않도록 설계하는 이유를 쓰시오.
(4) 히트스톱 강도·시간을 코드에 숫자로 박지 않고 어디에 두는가.

### P1-106 (0.10점)

[상황] 다음 네 상황에서 AI에게 보낼 프롬프트를 각각 2~4줄로 쓰시오. 커리큘럼 프롬프트 라이브러리의 필수 요소가 빠지면 감점된다.
① 아래 코드가 이해되지 않는다.
`UPROPERTY(VisibleAnywhere) TObjectPtr<UStaticMeshComponent> Mesh;`
`AArenaProjectile* P = GetWorld()->SpawnActor<AArenaProjectile>(ProjectileClass, Loc, Rot);`
② 내일 모의 면접 질문 "OnRep 함수는 서버에서도 호출되나?"에 내 말로 답할 수 있게 공부하고 싶다.
③ 적 순찰 BTTask(C++)를 처음 구현하려 한다. AI 레벨은 L2다.
④ 백준 1912 '연속합'을 C++로 풀었는데 '틀렸습니다'가 나온다.
각 프롬프트 아래에, 그 프롬프트에서 AI가 '하지 말아야 할 것'을 한 줄씩 쓰시오.

### P1-107 (0.19점)

[상황] 다음 다섯 상황에서 무엇을 하는지(또는 AI에게 보낼 프롬프트를) 쓰시오.
① AI가 "`UGameplayStatics::GetNearestEnemyPawn(this)`를 쓰면 가장 가까운 적을 얻을 수 있다"고 알려 줬다. 이 API를 믿기 전에 Visual Studio에서 확인하는 절차를 쓰시오. 확인 결과 없는 함수였다면 무엇을 남기는지도 쓰시오.
② GAS를 추가하고 빌드했더니 `LNK2019: unresolved external symbol ... UAbilitySystemComponent ...` 링크 에러가 났다. AI에게 보낼 프롬프트를 쓰시오.
③ 2인 PIE에서 클라이언트의 체력바만 안 움직인다. 15분 동안 직접 좁혀 봤고, 서버에서 Health가 바뀌는 로그와 OnRep에 건 중단점이 클라에서 안 걸리는 것을 확인했다. 디버깅 프롬프트를 쓰시오.
④ PR을 올리기 전에 AI 코드 리뷰를 받는다. 리뷰 프롬프트에 넣을 기준과 점검 항목 6개를 쓰시오.
⑤ CommitAbility가 내부에서 어떤 순서로 동작하는지 엔진 소스로 직접 따라가 보고 싶다. 엔진 소스 길잡이 프롬프트를 쓰시오.

### P1-108 (0.10점)

[설명형] 학생이 쓴 프롬프트 3개다. 각각 빠진 조건을 찾고, 조건을 다 갖춘 프롬프트로 고쳐 쓰라.
가. (W3 과제) "내 ALifecycleProbe 코드 보고 생명주기 면접 질문 5개랑 모범 답안 한꺼번에 줘."
나. "레버랑 문 연결하는 코드 짜줘."
다. "오늘 공부 메모를 TIL로 예쁘게 다듬어 줘."
그리고 가의 결과를 W3 과제로 남기려면 무엇을 기록해야 하는지 쓰라.

### P1-109 (0.10점)

[설명형] (1) W1에 AI가 AFloatingItem 초안을 써 줬다. AI 의존도 L1 방식으로 이 코드를 학습 로그 저장소에 올리기까지의 작업 순서를 쓰라. 설명 못 하는 줄이 나오면 어떻게 하는지도 쓰라.
(2) 다음 세 줄에 L1 방식의 해설 주석을 한 줄씩 달라.
UPROPERTY(EditAnywhere) float Amplitude = 50.f;
Mesh = CreateDefaultSubobject<UStaticMeshComponent>(TEXT("Mesh"));
SetActorLocation(StartLocation + FVector(0.f, 0.f, Offset));
(3) W23에 웨이브 스포너를 L3 방식으로 만든다. 작업 순서를 쓰고, AI에게 무엇만 물어야 하는지 예를 2개 들라. L1과 L3를 쓰는 목적의 차이도 쓰라.

### P1-110 (0.19점)

L2 방식으로 내가 직접 쓴 UArenaHealthComponent 코드를 AI에게 'Epic C++ 코딩 표준 기준으로 리뷰해줘, 수정 코드는 내가 요청할 때만'이라고 요청해 다음 의견 6개를 받았다.
① AActor* CachedOwner;에 UPROPERTY()가 없다. UPROPERTY() + TObjectPtr로 바꿔라.
② 체력바는 TickComponent에서 매 프레임 갱신하는 게 안전하다.
③ bool 멤버 IsDead를 bIsDead로 바꿔라.
④ 값을 바꾸지 않는 GetHealthPercent()를 const 멤버 함수로 만들어라.
⑤ 데미지 처리에 UGameplayStatics::ApplyDamageSafe()를 써라. (Visual Studio에서 F12·검색으로 찾아봤지만 엔진에 이런 선언이 없었다)
⑥ 모든 멤버 함수에 virtual을 붙여 확장성을 높여라.

(1) 6개 각각을 채택/거절하고 이유를 한 줄씩 쓰시오.
(2) PR에 이 판단을 어떤 형식으로 남기는지 한 항목을 예로 쓰시오.
(3) ①을 채택해 고친 코드 중 TObjectPtr이 왜 필요한지 한 줄도 설명할 수 없다면, 커밋 전에 무엇을 해야 하는지 커리큘럼의 원칙과 함께 순서대로 쓰시오.

### P1-111 (0.10점)

M3(AI 레벨 L2) 기간에 새 기능 '원거리 적이 플레이어와 거리를 유지하며 발사'를 시작한다.
(1) AI에게 보낼 첫 프롬프트를 '힌트 먼저' 원칙과 L2의 범위 제한(코드는 내가 쓴다)이 드러나게 2~3문장으로 쓰시오.
(2) 기능을 다 만든 뒤 PR의 'AI 활용 내역'을 세 칸(사용 범위 / 내가 검증·수정한 것 / AI가 틀렸던 것)으로 채워 예시를 쓰시오.

### P1-112 (0.10점)

[상황] 학생 E의 W17 결과물이다. 루브릭 '기능 완성도'·'코드 품질'·'엔진 이해'를 각각 1~4점으로 채점하고, 근거와 '다음 점수로 올라가려면 필요한 것'을 한 줄씩 쓰시오.
- 기능: GA_MeleeCombo·GA_Dash가 동작한다. 스태미나가 0일 때 대시가 막히고, 콤보 도중 피격되면 어빌리티가 정상 종료된다. 2인 PIE는 지연 없이만 테스트했고 영상은 없다.
- 코드: C++ 베이스 클래스 + BP 자식, Epic 네이밍 준수. 전투는 UCombatComponent로, 수치는 DataAsset으로 분리했다. UObject 포인터는 모두 UPROPERTY + TObjectPtr다. 자동화 테스트는 없고, 이번 PR 하나에 변경 2,400줄이 들어갔다.
- 엔진 이해: CommitAbility가 비용·쿨다운을 적용한다는 것을 GameplayAbility.h 주석과 중단점 콜스택을 근거로 TS 문서에 설명했다. ASC 위치나 예측 방식의 대안 비교는 기록하지 않았다.

### P1-113 (0.10점)

M3가 끝난 학생 A의 기록이다.
- 문제 해결: TS 문서 3건이 템플릿대로 증상·가설·원인·해결이 있다. '재발 방지' 칸은 모두 비어 있다.
- Git: 기능 단위로 커밋했고, 모든 PR이 이슈와 연결되어 있으며 셀프 리뷰 체크가 되어 있다. 릴리즈 노트·CHANGELOG·라벨은 없다.
- AI 활용: 코드를 직접 쓴 뒤 AI 리뷰를 받았고 PR마다 채택/거절 이유가 있다. AI-Off 챌린지 ②는 시간 초과로 실패했다.

(1) 루브릭의 '문제 해결 기록', '협업 습관(Git)', 'AI 활용'을 각각 1~4점으로 채점하고 근거를 한 줄씩 쓰시오.
(2) docs/retro/M3.md에 쓸 Keep·Problem·Try를 한 줄씩 쓰시오. 그리고 월간 자가 평가에 쓰는 루브릭 6항목의 이름을 모두 쓰시오.

### P1-114 (0.10점)

(1) 이 커리큘럼의 '관문' 운영 방식을 한두 문장으로 설명하시오.
(2) 학생 C의 저장소를 단계별로 점검했다. 각 관문의 통과 여부와, 통과하지 못했다면 빠진 조건을 쓰시오.
- M2 시점: v0.2.0 릴리즈와 45초 영상 있음, 무기 추가 PR의 diff에 .h/.cpp 변경 없음, TS 2건, ADR 2건, AI-Off ② 기록 있음, 코테 누적 38문제.
- M3 시점: 메뉴~게임오버 루프 동작, 적 AI 2종, 성능 수치는 Size Map 1건만, TS 누적 3건, ADR 3건, 코테 누적 61문제.
- M4 시점(docs/retro/M4.md 작성 중): v0.3.0 패키징·릴리즈, README 1차, AI-Off ③ 기록, NetLab 노트 + TS 누적 6건, GA_Dash 동작, 코테 누적 76문제.

### P1-115 (0.10점)

[상황] W20을 마친 학생 G의 상태다.
- 루브릭 자가 평가: 기능 3 · 코드 3 · 엔진 3 · 문제 해결 기록 2 · Git 3 · AI 활용 1
- 릴리즈 v0.4.0·v0.5.0 공개, 반응성 전/후 비교 영상 있음
- 성능 리포트 개선 2건, 자동화 테스트 6개
- 열린 버그 이슈 2개(README Known Issues에 적음), 코테 누적 88문제
(1) 루브릭 평균을 구하고 단계별 목표 평균과 비교하시오. 다음 단계 전에 무엇부터 보강하는가.
(2) M5 관문 조건 6가지를 쓰고, G가 통과했는지 판정하시오. 못 채운 조건과 보강 계획을 쓰시오.
(3) W24에 쓸 6개월 회고(`docs/retro/6months.md`)에 넣을 숫자 항목을 쓰시오. 각 숫자를 어디서 집계할지도 쓰시오.
(4) M6 관문 조건 5가지를 쓰시오.

### P1-116 (0.19점)

[상황] 졸업 예정자 세 명이 각자 지원할 회사를 정했다.
- 갑: 실시간 온라인 PvP 액션 게임 회사
- 을: 사내 툴·콘텐츠 파이프라인 조직
- 병: 생성형 AI를 개발 과정에 적극 도입하는 회사
(1) 커리큘럼 추천에 따라 세 명에게 딥다이브 주제(A~E)를 하나씩 추천하고 이유를 쓰시오.
(2) 딥다이브 B·D·E가 각각 무엇을 하는지 2줄씩 설명하시오.
(3) B를 고른 학생은 BT 버전과 무엇을 비교해야 하는가. 비교 관점 3가지를 쓰시오.
(4) E를 고른 학생이 블로그를 쓸 때 '근거'로 써야 하는 것은 무엇인가.

### P1-117 (0.10점)

[상황] 딥다이브 C(스프린트를 FSavedMove 플래그로 네트워크 예측되게 구현)를 골랐다. 기간은 1주다.
(1) 이 작업을 이슈 5개 이내로 분해하시오. 각 이슈에 완료 조건을 한 줄씩 붙이시오.
(2) `docs/deepdive.md` 리포트를 커리큘럼 구조 4단계로 쓴다면 각 단계에 무엇이 들어가는지 이 주제로 쓰시오(수치·영상 포함).
(3) 같은 내용을 기술 블로그 1편으로 재가공할 때 리포트와 무엇을 다르게 하는지 2가지 쓰시오.

### P1-118 (0.19점)

[상황] 프로젝트 ActionArena(UE5 C++ 2인 협동 액션 웨이브 서바이벌, 6개월, 1인)로 지원 준비를 한다.
(1) 면접 첫 질문 "프로젝트를 1분 안에 소개해 보세요"에 대한 스크립트를 쓰시오. 커리큘럼 순서를 따르고, 숫자와 링크를 넣으시오(가상 수치 가능).
(2) 3분 버전을 만들 때 1분 버전에 무엇을 더하는지 2가지 쓰시오.
(3) 2~3분 시연 영상의 구성(구간 순서)을 쓰시오. 자막과 디버그 시각화를 넣는 이유를 쓰시오. 어디에 어떤 공개 방식으로 올리는지도 쓰시오.
(4) 기술 포트폴리오 PDF(15~20쪽)의 목차를 10개 항목 이상 쓰시오. 국내 채용에서 PDF를 따로 준비하는 이유를 한 줄로 쓰시오.

### P1-119 (0.10점)

[상황] 지원할 회사 공고의 요구사항 3개다: ① UE C++ 게임플레이 구현 능력 ② 멀티플레이 리플리케이션 이해 ③ 성능 최적화 경험.
(1) 공고 요구사항 ↔ 내 증거 매핑표를 3행으로 쓰시오. 각 행에 증거 링크의 종류(PR·TS·ADR·영상·리포트 등)를 구체적으로 쓰시오. 증거가 약한 행은 어떻게 표시하고 처리하는가. 커리큘럼 기준으로 지원 회사 리스트는 몇 곳으로 만들고, 매핑표는 어떤 단위로 만드는지도 쓰시오.
(2) 이력서·자기소개서에서 'C#/유니티 → UE C++ 전환 스토리'를 무엇으로 증명하는지 쓰시오. 자기소개 문장 2줄을 예로 쓰시오.
(3) 1차 면접이 끝났다. 복기 문서에 남길 항목 4가지를 쓰고, 이것이 왜 '학습 기록'인지 한 줄로 쓰시오.
(4) 제출 전에 현직자에게 포트폴리오 피드백을 받았다. 피드백을 받고 반영하는 과정을 어떻게 기록하는지 쓰시오.

### P1-120 (0.10점)

[상황] 다음은 학생의 TS-007 요약이다.
- 증상: 2인 협동에서 클라이언트가 공격하면 적이 데미지를 2번 받는다.
- 확인: 로그에 ApplyDamage가 서버와 클라이언트에서 각각 찍힘
- 원인: 판정·ApplyDamage가 권한 확인 없이 양쪽에서 실행됨
- 해결: HasAuthority() 분기로 서버에서만 데미지 적용
- 재발 방지: PR 셀프 리뷰 체크에 '서버/클라 실행 위치 확인' 추가
(1) 이 TS를 면접용 '30초 버전'으로 쓰시오. TS 템플릿의 문장 틀을 따르시오.
(2) 질문 은행 답변을 AI 없이 준비하는 과정을 순서대로 쓰시오. 녹음을 다시 들을 때 확인할 점 3가지도 쓰시오.
(3) AI 면접관 모드로 내 코드 꼬리 질문 리허설을 3회 진행한다. 진행 규칙(무엇을 AI에게 받고 무엇을 AI 없이 하는지)을 쓰시오. 이렇게 하는 이유도 쓰시오.

### P1-121 (0.19점)

질문 은행(주차별 자가 점검 + 일반 질문)에서 뽑은 10문항이다. AI·자료 없이 각 문항에 1~3줄로 내 말로 답하시오. 채점 후 0점·부분 점수 문항은 오답 노트 대상으로 표시되어 돌려받는다.
1. .h와 .cpp를 나누는 이유는?
2. 포인터와 참조의 차이 3가지는?
3. virtual이 없으면 어떻게 되나? override는 왜 붙이나?
4. const FInputActionValue& Value에서 const와 &의 의미는?
5. 람다에서 [this] 캡처가 위험한 경우는?
6. 중복 검사에 TArray::Contains와 TSet 중 무엇이 나은가?
7. UPROPERTY 없는 UObject 포인터 멤버가 위험한 이유는?
8. 생성자에서 GetWorld()나 다른 액터를 찾으면 안 되는 이유는?
9. C++에서 struct와 class의 차이는?
10. static 키워드의 의미 3가지는?

### P1-950 (0.19점)

[상황] 면접관 질문: "딥다이브(A~E)로 무엇을 골랐고, 그 선택이 우리 회사에 무엇을 보여 주나요?" 이 회사는 '사내 툴·콘텐츠 파이프라인 조직'이다.
자신이 실제로 한 딥다이브 주제로 2분 분량(약 10~14줄)의 답변 스크립트를 쓰시오. 다음 5가지가 이 순서로 들어가야 한다.
① 고른 이유(회사 유형과의 연결. 고른 주제가 이 회사의 추천 주제가 아니라면 그 사실을 인정하고 어떤 역량으로 연결되는지)
② 해결한 문제와 결과(이슈를 몇 개로 나눴고 무엇을 만들거나 분석했는지)
③ 근거(측정 수치·전후 비교·엔진 소스 중 무엇이 있는지, 링크로 말할 것)
④ AI 활용과 검증(무엇을 AI에 맡기고 무엇을 직접 확인했는지)
⑤ 한계와 다음 단계

## 2부 코딩테스트 (20점 · 330분)

2부-A 주제별 21문항 210분(백준형 단일 주제, 테스트케이스별 부분 점수) + 2부-B 실전 세트 3문항 120분(프로그래머스형, W21 모의시험 형식). C++17과 Visual Studio 콘솔 앱 사용, AI·검색 불가. 풀이는 제출 저장소에 '문제번호-제목.cpp'로 커밋

### P2-01 (0.36점)

[P2-01 A형] 던전 정산
시간 제한 1초 · 메모리 256MB

던전을 깬 파티가 골드 G를 얻었다. 파티원은 P명이다. 정산 화면에 다음 네 가지를 띄운다.
1. 한 명이 받는 골드(정수)와, 똑같이 나누고 남아 길드 금고로 가는 골드
2. 남김없이 똑같이 나눈다고 할 때 1인당 골드(실수)
3. 던전 입장 코드 C(네 자리 정수)의 일의 자리, 십의 자리, 백의 자리, 천의 자리 숫자
4. 입장 코드 네 숫자의 평균

입력
첫째 줄에 G와 P가 공백으로 구분되어 주어진다. 둘째 줄에 C가 주어진다.

출력
첫째 줄: 1인당 골드와 남는 골드를 공백으로 구분해 출력한다.
둘째 줄: 1인당 골드를 실수로 계산해 소수점 아래 넷째 자리까지(반올림) 출력한다.
셋째 줄: C의 일의 자리, 십의 자리, 백의 자리, 천의 자리 숫자를 이 순서대로 공백으로 구분해 출력한다.
넷째 줄: 네 숫자의 평균을 소수점 아래 둘째 자리까지 출력한다.

제한
- 0 ≤ G ≤ 2,000,000,000
- 1 ≤ P ≤ 100
- 1000 ≤ C ≤ 9999
- 채점 데이터에는 반올림 자리 바로 뒤가 정확히 5로 끝나 올림·내림이 애매한 값이 없다.

예제 입력 1
1000 3
2025

예제 출력 1
333 1
333.3333
5 2 0 2
2.25

예제 입력 2
95 4
7340

예제 출력 2
23 3
23.7500
0 4 3 7
3.50

제출
- Visual Studio 콘솔 앱에서 Ctrl+F5로 예제 2개를 실행해 출력이 글자 하나까지 같은지 확인한 뒤 C++17로 제출한다.
- 파일 맨 아래 주석에, 직접 넣어 본 경계 입력 2개(가장 작은 값 쪽 1개, 가장 큰 값 쪽 1개)와 그때 콘솔에 나온 출력을 적는다.
- 'P2-01-던전-정산.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-02 (0.36점)

[P2-02 A형] 레이드 알림
시간 제한 1초 · 메모리 256MB

길드 레이드 예약 화면에 다음 세 가지를 판정해 띄운다.
1. 전투력 점수 S의 등급: 900점 이상 S, 700~899점 A, 400~699점 B, 나머지 C
2. 연도 Y가 '이벤트 연도'인지: Y가 5의 배수이면서, 동시에 'Y가 홀수이거나 Y가 7의 배수'이면 이벤트 연도다.
3. 레이드는 H시 M분에 시작하고, 알림은 시작 K분 전에 울린다. 알림이 울리는 시각(24시간제)을 구한다. 전날로 넘어가면 전날의 시각을 출력한다.

입력
첫째 줄에 S, 둘째 줄에 Y, 셋째 줄에 H M K가 공백으로 구분되어 주어진다.

출력
첫째 줄에 등급(S, A, B, C 중 하나), 둘째 줄에 이벤트 연도이면 YES 아니면 NO, 셋째 줄에 알림 시각의 시와 분을 공백으로 구분해 출력한다(앞에 0을 붙이지 않는다).

제한
- 0 ≤ S ≤ 1000
- 1 ≤ Y ≤ 4000
- 0 ≤ H ≤ 23, 0 ≤ M ≤ 59, 0 ≤ K ≤ 1439

예제 입력 1
950
2025
0 30 45

예제 출력 1
S
YES
23 45

예제 입력 2
700
2020
12 0 0

예제 출력 2
A
NO
12 0

제출: 'P2-02-레이드-알림.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-03 (0.36점)

[P2-03 A형] 계단 지형 미리보기
시간 제한 1초 · 메모리 256MB

레벨 디자이너가 계단 지형 T개를 한꺼번에 미리 보려 한다. 높이가 N인 계단은 N줄짜리 그림으로 그린다. i번째 줄(1 ≤ i ≤ N)에는 '.'을 N−i개 쓴 뒤 '#'을 i개 쓴다.

입력
첫째 줄에 지형 개수 T가 주어진다. 다음 T줄에 각 지형의 높이 N이 한 줄에 하나씩 주어진다.

출력
지형마다 먼저 '#k'(k는 1부터 시작하는 지형 번호)를 한 줄에 출력하고, 이어서 그 지형의 그림 N줄을 출력한다. 줄 끝에 공백을 붙이지 않는다.

제한
- 1 ≤ T ≤ 100,000
- 1 ≤ N ≤ 10
- 출력은 최대 110만 줄(약 12MB)이다.

예제 입력 1
2
3
1

예제 출력 1
#1
..#
.##
###
#2
#

예제 입력 2
1
4

예제 출력 2
#1
...#
..##
.###
####

채점 항목: 출력 결과와 함께, 입출력이 많을 때 속도를 높이는 C++ 입출력 설정과 줄바꿈 방식을 코드에서 확인한다(2점).

제출: 'P2-03-계단-지형.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-04 (0.36점)

[P2-04 A형] 경매장 시세 기록
시간 제한 1초 · 메모리 256MB

경매장에서 하루 동안 거래 N건이 있었다. 거래마다 가격 변동값 d(음수면 하락)와 판매자 번호 s가 기록된다. 하루 동안 가장 낮은 변동값과 가장 높은 변동값, 그리고 거래에 참여한 서로 다른 판매자 수를 구하라.

입력
첫째 줄에 N이 주어진다. 둘째 줄에 d_1 … d_N이 공백으로 구분되어 주어진다. 셋째 줄에 s_1 … s_N이 공백으로 구분되어 주어진다(i번째 거래의 판매자가 s_i).

출력
첫째 줄에 가장 낮은 변동값과 가장 높은 변동값을 공백으로 구분해 출력한다. 둘째 줄에 서로 다른 판매자 수를 출력한다.

제한
- 1 ≤ N ≤ 100,000
- −1,000,000,000 ≤ d_i ≤ 1,000,000,000
- 1 ≤ s_i ≤ 100,000
- 입력(d와 s)은 모두 vector<int>에 저장한 뒤, 저장한 vector를 순회해 답을 구한다(코드 확인 채점 항목).

예제 입력 1
5
3 -7 12 0 -7
2 5 2 9 5

예제 출력 1
-7 12
3

예제 입력 2
2
0 0
7 7

예제 출력 2
0 0
1

제출: 'P2-04-경매장-시세.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-05 (0.36점)

[P2-05 A형] 행운의 쿠폰
시간 제한 1초 · 메모리 256MB

이벤트 쿠폰 번호 S는 숫자로만 된 문자열이며 매우 길 수 있다(맨 앞이 0일 수도 있다). 다음 세 가지를 구하라.
1. S의 K번째 글자(왼쪽 끝 글자가 1번째)
2. S의 모든 자리 숫자의 합
3. 1 이상 M 이하 정수 중, 10진수로 썼을 때 "77"이 연속으로 들어 있는 수의 개수(예: 77, 177, 770, 1077)

입력
첫째 줄에 S, 둘째 줄에 K, 셋째 줄에 M이 주어진다.

출력
세 줄에 걸쳐 1, 2, 3의 답을 차례로 출력한다.

제한
- 1 ≤ S의 길이 ≤ 100, S는 '0'~'9'로만 이루어진다.
- 1 ≤ K ≤ S의 길이
- 1 ≤ M ≤ 1,000,000

예제 입력 1
90210
3
100

예제 출력 1
2
12
1

예제 입력 2
7
1
76

예제 출력 2
7
7
0

제출: 'P2-05-행운의-쿠폰.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-06 (0.71점)

[P2-06 A형] 룬 조합과 주화
시간 제한 1초 · 메모리 256MB

대장장이가 룬 N개를 가지고 있다. i번째 룬의 힘은 a_i이다.
(1) 서로 다른 룬 3개를 골라 무기에 박으면, 세 힘의 합 X의 '자릿수 합'(예: X = 1997이면 1+9+9+7 = 26)만큼 무기가 빛난다. 가장 밝게 빛나게 할 때의 자릿수 합을 구하라. 힘이 같은 룬이라도 서로 다른 룬이면 함께 고를 수 있다.
(2) 강화 비용 G골드를 7골드 주화와 4골드 주화만으로 거스름돈 없이 정확히 낸다. 주화 개수를 가장 적게 할 때의 개수를 구하라. 정확히 낼 수 없으면 -1을 구한다.

입력
첫째 줄에 N, 둘째 줄에 a_1 … a_N, 셋째 줄에 G가 주어진다.

출력
첫째 줄에 (1)의 답, 둘째 줄에 (2)의 답을 출력한다.

제한
- 3 ≤ N ≤ 100
- 1 ≤ a_i ≤ 100,000
- 1 ≤ G ≤ 100,000
- 자릿수 합은 int DigitSum(int x)처럼 별도 함수로 만들어 호출한다(채점 항목).

예제 입력 1
5
19 28 7 50 101
15

예제 출력 1
17
3

예제 입력 2
3
1 1 1
17

예제 출력 2
3
-1

제출: 'P2-06-룬-조합.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-07 (0.71점)

[P2-07 A형] 레이드 기록 정리
시간 제한 1초 · 메모리 256MB

레이드 기록 N개(N은 홀수)가 있다. 기록마다 팀 번호 t, 점수 s, 닉네임이 있다. 다음 다섯 가지를 차례로 출력한다.
① (팀 번호, 점수) 쌍을 팀 번호 오름차순으로, 팀 번호가 같으면 점수 오름차순으로 정렬해 한 줄에 하나씩 't s' 형식으로 출력한다.
② 닉네임을 길이가 긴 것부터, 길이가 같으면 사전순(a가 먼저)으로 정렬하고, 같은 닉네임은 한 번만 남겨 한 줄에 하나씩 출력한다.
③ 점수 N개의 중앙값(크기순으로 가운데 값)을 출력한다.
④ 입력 순서로 i번째부터 j번째까지의 기록에서 점수만 모아 오름차순 정렬했을 때 k번째 점수를 출력한다.
⑤ 방 코드 C(숫자 문자열)의 숫자들을 큰 것부터 내림차순으로 정렬한 문자열을 출력한다.

입력
첫째 줄에 N. 다음 N줄에 t s 닉네임. 다음 줄에 i j k. 마지막 줄에 C.

출력
①의 N줄, ②의 줄들, ③ 한 줄, ④ 한 줄, ⑤ 한 줄을 이 순서로 출력한다.

제한
- 1 ≤ N ≤ 1,001, N은 홀수
- 1 ≤ t ≤ 100, 0 ≤ s ≤ 1,000,000
- 닉네임은 영문 소문자 1~20자이며 여러 기록에 같은 닉네임이 나올 수 있다.
- 1 ≤ i ≤ j ≤ N, 1 ≤ k ≤ j − i + 1
- C는 '0'~'9'로 이루어진 1~50자

예제 입력 1
5
2 300 kim
1 500 lee
2 100 park
1 500 kim
3 50 an
2 4 2
3091

예제 출력 1
1 500
1 500
2 100
2 300
3 50
park
kim
lee
an
300
500
9310

예제 입력 2
1
7 0 solo
1 1 1
0

예제 출력 2
7 0
solo
0
0
0

제출: 'P2-07-레이드-기록.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-08 (0.71점)

[P2-08 A형] 길드 홀 출입 관리
시간 제한 1초 · 메모리 256MB

길드원 N명이 등록 순서대로 1번부터 N번까지 번호를 받았다. 길드 홀 출입 기록 M개, 운영자 질의 Q개, 주간 보상 기록이 주어진다.
① 질의마다 답한다. 질의가 숫자이면 그 번호 길드원의 이름을, 문자열이면 그 이름의 번호를 출력한다. 등록되지 않은 이름이면 NONE을 출력한다.
② 출입 기록을 모두 처리한 뒤 홀 안에 남아 있는 길드원 이름을 사전 역순(z쪽이 먼저)으로 한 줄에 하나씩 출력한다. 아무도 없으면 EMPTY를 출력한다.
③ 주간 보상 대상 K명의 명단과 실제 수령자 K−1명의 명단이 주어진다. 수령자 명단은 대상 명단에서 정확히 한 명만 빠진 것이다. 대상 명단에는 같은 이름이 여러 번 나올 수 있다(보상 명단의 이름은 길드원 명부와 상관없다). 보상을 받지 못한 사람의 이름을 출력한다.

입력
첫째 줄에 N M Q.
다음 N줄에 1번부터 N번까지 길드원 이름.
다음 M줄에 출입 기록 '이름 in' 또는 '이름 out'. 기록의 이름은 모두 등록된 길드원이고, 홀에 없는 사람의 out이나 이미 있는 사람의 in은 없다.
다음 Q줄에 질의가 하나씩. 숫자로 시작하면 1 이상 N 이하 정수이고, 아니면 이름이다.
다음 줄에 K. 다음 K줄에 보상 대상 이름, 그다음 K−1줄에 수령자 이름.

출력
①의 Q줄, ②의 줄들, ③의 한 줄을 이 순서로 출력한다.

제한
- 1 ≤ N, M, Q ≤ 100,000, 2 ≤ K ≤ 100,000
- 이름은 영문 소문자와 숫자로 된 1~20자이고 첫 글자는 영문 소문자다. 길드원 이름은 서로 다르다.

예제 입력 1
4 6 4
ari
bob
cid
dan
ari in
cid in
bob in
ari out
dan in
cid out
2
dan
eve
1
3
kim
lee
kim
lee
kim

예제 출력 1
bob
4
NONE
ari
dan
bob
kim

예제 입력 2
1 2 1
solo
solo in
solo out
solo
2
x
y
y

예제 출력 2
1
EMPTY
x

제출: 'P2-08-길드-홀.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-09 (0.71점)

[P2-09 A형] 카드 덱 · 주문 검사 · 수리 대기열
시간 제한 1초 · 메모리 256MB

게임 서버 로그를 처리한다. 입력은 세 부분이다.
① 카드 덱 명령 N개를 차례로 처리한다. 덱은 처음에 비어 있다.
- top x: 덱 맨 위에 카드 x를 놓는다.
- bottom x: 덱 맨 아래에 카드 x를 넣는다.
- draw: 맨 위 카드를 빼고 그 번호를 출력한다. 덱이 비어 있으면 -1.
- burn: 맨 아래 카드를 빼고 그 번호를 출력한다. 비어 있으면 -1.
- count: 덱의 카드 수를 출력한다.
- peek: 맨 위 카드 번호를 출력한다(빼지 않음). 비어 있으면 -1.
- last: 맨 아래 카드 번호를 출력한다(빼지 않음). 비어 있으면 -1.
② 주문 문자열 B개는 '(' ')' '[' ']'로만 이루어진다. 짝이 맞으면 OK, 아니면 BROKEN을 출력한다. 짝이 맞는다는 것은 모든 닫는 괄호가 아직 닫히지 않은 가장 최근의 여는 괄호와 같은 종류로 짝지어지고, 끝에 남는 여는 괄호가 없다는 뜻이다. 예: '([])'는 OK, '([)]'는 BROKEN.
③ 장비 R개가 1번부터 R번까지 순서대로 수리 대기 줄에 서 있다. i번 장비의 손상은 d_i이다. 대장장이는 줄 맨 앞 장비를 꺼내 망치질을 최대 C번 한다(망치질 한 번에 손상 1 감소). 손상이 0이 되면 그 장비는 완성되어 줄에서 나가고, 아직 남아 있으면 줄 맨 뒤로 보낸다. 모든 장비가 완성될 때까지 반복한다. 장비가 완성되는 순서를 구한다.

입력
첫째 줄에 N, 다음 N줄에 명령.
다음 줄에 B, 다음 B줄에 주문 문자열.
다음 줄에 R C, 다음 줄에 d_1 … d_R.

출력
①에서 출력이 있는 명령마다 한 줄씩, 이어서 ②의 결과 B줄, 마지막 줄에 ③의 완성 순서(장비 번호를 공백으로 구분)를 출력한다.

제한
- 1 ≤ N ≤ 500,000, 1 ≤ x ≤ 100,000
- 1 ≤ B ≤ 100, 주문 문자열 길이 1~100
- 1 ≤ R ≤ 1,000, 1 ≤ C ≤ 100, 1 ≤ d_i ≤ 1,000

예제 입력 1
7
top 5
bottom 9
peek
burn
draw
draw
count
3
([])
([)]
((
3 2
3 1 4

예제 출력 1
5
9
5
-1
0
OK
BROKEN
BROKEN
2 1 3

예제 입력 2
3
last
bottom 1
last
1
)(
1 5
5

예제 출력 2
-1
1
BROKEN
1

제출: 'P2-09-카드-덱.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-10 (0.71점)

[P2-10 A형] 마법진 각인과 포탈 이동
시간 제한 1초 · 메모리 256MB

(1) 마법진: 길이 5^N인 칸이 처음에 모두 '.'이다. 함수 Carve(시작 위치, 길이)는 다음처럼 동작한다.
- 길이가 1이면 그 칸을 '#'으로 바꾸고 끝낸다.
- 길이가 1보다 크면 구간을 길이가 같은 5조각으로 나누고, 1번째·3번째·5번째 조각에 대해 이 순서로 Carve를 호출한다. 2번째·4번째 조각은 '.' 그대로 둔다.
Carve(0, 5^N)을 한 번 호출해 마법진을 완성하고, 그동안 Carve가 호출된 총횟수(처음 호출 포함)를 센다. 호출 횟수를 세는 변수는 전역으로 두지 않고, Carve의 참조 매개변수(int&)로 넘겨 센다(코드 확인 채점 항목).
(2) 포탈 이동: 포탈 1, 2, 3이 있고 포탈 1에 크기가 모두 다른 수정 K개가 큰 것이 아래로 가게 쌓여 있다. 한 번에 한 포탈의 맨 위 수정 하나만 다른 포탈의 맨 위로 옮길 수 있고, 작은 수정 위에 큰 수정을 올릴 수 없다. 수정 K개를 모두 포탈 2로 옮기는 최소 횟수의 이동 순서를 구한다.
(3) 수정이 M개일 때 같은 규칙으로 포탈 1에서 포탈 2로 모두 옮기는 최소 이동 횟수를 구한다.

입력
첫째 줄에 N K M이 주어진다.

출력
첫째 줄: 마법진 문자열(길이 5^N)
둘째 줄: Carve 호출 총횟수
셋째 줄: (2)의 최소 이동 횟수 X
다음 X줄: 이동을 순서대로 'a b'(포탈 a의 맨 위 수정을 포탈 b로) 형식으로
마지막 줄: (3)의 답

제한
- 0 ≤ N ≤ 7
- 1 ≤ K ≤ 15
- 1 ≤ M ≤ 60

예제 입력 1
1 2 3

예제 출력 1
#.#.#
4
3
1 3
1 2
3 2
7

예제 입력 2
0 1 4

예제 출력 2
#
1
1
1 2
15

제출: 'P2-10-마법진.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-11 (1.07점)

[P2-11 A형] 스킬 슬롯과 연금술
시간 제한 1초 · 메모리 256MB

(1) 서로 다른 스킬 번호 N개가 정렬되지 않은 채 주어진다. 스킬 슬롯 M칸을 채우는 세 가지 경우를 모두 출력한다. 경우 하나는 고른 스킬 번호를 슬롯 순서대로 공백으로 구분해 한 줄에 쓰고, 경우들은 사전순(앞 칸부터 비교해 번호가 작은 것이 먼저)으로 출력한다.
① 같은 스킬을 두 번 넣을 수 없다(순서가 다르면 다른 경우).
② 같은 스킬을 두 번 넣을 수 없고, 슬롯 순서대로 번호가 오름차순인 경우만.
③ 같은 스킬을 여러 번 넣어도 된다.
(2) 연금술: 재료 수치 a_1 … a_K가 이 순서로 놓여 있다. 재료 사이 K−1칸에 연산자를 하나씩 넣는다. 넣을 연산자는 +, −, ×, ÷의 개수로 주어지며(합 K−1) 모두 써야 한다. 연산자 우선순위를 무시하고 왼쪽부터 차례로 계산한다. ÷는 C++의 정수 나눗셈과 같다(소수점 아래 버림, 음수는 0 쪽으로). 만들 수 있는 결과의 최댓값과 최솟값을 구한다. 예: 5 3 2에 +1개, ×1개 → (5+3)×2 = 16, 5×3+2 = 17.

입력
첫째 줄에 N M. 둘째 줄에 스킬 번호 N개. 셋째 줄에 K. 넷째 줄에 a_1 … a_K. 다섯째 줄에 +, −, ×, ÷의 개수.

출력
①의 경우들, '--' 한 줄, ②의 경우들, '--' 한 줄, ③의 경우들, '--' 한 줄, 최댓값 한 줄, 최솟값 한 줄을 이 순서로 출력한다.

제한
- 1 ≤ M ≤ N ≤ 6, 스킬 번호는 1 이상 10,000 이하이고 서로 다르다.
- 2 ≤ K ≤ 11, 1 ≤ a_i ≤ 100
- 연산자를 어떤 순서로 넣어도 계산 중간값과 결과는 −1,000,000,000 이상 1,000,000,000 이하다.

예제 입력 1
3 2
30 10 20
3
5 3 2
1 0 1 0

예제 출력 1
10 20
10 30
20 10
20 30
30 10
30 20
--
10 20
10 30
20 30
--
10 10
10 20
10 30
20 10
20 20
20 30
30 10
30 20
30 30
--
17
16

예제 입력 2
1 1
7
2
4 9
0 1 0 0

예제 출력 2
7
--
7
--
7
--
-5
-5

제출: 'P2-11-스킬-슬롯.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-12 (1.07점)

[P2-12 A형] 던전 지도와 주문 조합
시간 제한 1초 · 메모리 256MB

던전에 방 N개(1~N번)와 양방향 통로 E개가 있다. 시작 방은 S이다.
① 재귀 DFS로 S부터 탐색한 방문 순서. 한 방에서 갈 수 있는 방이 여럿이면 번호가 작은 방부터 간다.
② queue를 쓰는 BFS로 S부터 탐색한 방문 순서. 인접한 방은 번호가 작은 방부터 큐에 넣는다.
③ S에서 통로를 따라 갈 수 있는 방의 수(S 제외).
④ 던전 전체의 '방 무리' 수. 통로로 서로 오갈 수 있는 방끼리 한 무리이며, 통로가 없는 방도 혼자 한 무리다.
⑤ 주문 조합: 수 c_1 … c_L이 순서대로 있다. 0에서 시작해 각 수마다 '더하기', '빼기', '쓰지 않기' 중 하나를 고른다. 결과가 T가 되도록 고르는 방법의 수를 구한다.

입력
첫째 줄에 N E S. 다음 E줄에 통로의 양 끝 방 u v. 같은 통로가 여러 번 주어질 수 있다. 다음 줄에 L T. 다음 줄에 c_1 … c_L.

출력
①, ②는 방 번호를 공백으로 구분해 한 줄씩, ③, ④, ⑤는 정수 한 줄씩, 모두 다섯 줄을 출력한다.

제한
- 1 ≤ N ≤ 1,000, 0 ≤ E ≤ 10,000, 1 ≤ S ≤ N
- 1 ≤ u, v ≤ N, u ≠ v
- 1 ≤ L ≤ 12, 1 ≤ c_i ≤ 200, −2,400 ≤ T ≤ 2,400

예제 입력 1
5 4 1
1 2
1 3
2 4
3 4
3 2
1 2 3

예제 출력 1
1 2 4 3
1 2 3 4
3
2
3

예제 입력 2
3 0 2
1 0
5

예제 출력 2
2
2
0
3
1

제출: 'P2-12-던전-지도.cpp' 이름으로 제출 저장소에 커밋한다.

### P2-13 (1.07점)

[P2-13 A형] 던전 탐험 지도  (시간 제한 1초 · 메모리 256MB · C++17)

던전 지도는 N행 M열 격자이고, 각 칸은 통로 '1' 또는 벽 '0'이다. 탐험가는 맨 왼쪽 위 칸 (1,1)에서 출발해 맨 오른쪽 아래 칸 (N,M)에 있는 출구로 가려 한다. (1,1)과 (N,M)은 항상 통로다. 다음 세 값을 구하는 프로그램을 작성하라.

① 통로 덩어리의 개수: 상하좌우로 맞닿은 통로 칸들은 같은 덩어리다.
② 걷기 최단 경로: 상하좌우로 한 칸씩 통로로만 움직일 때, (1,1)에서 (N,M)까지 지나는 칸 수의 최솟값. 출발 칸과 도착 칸도 센다. 갈 수 없으면 -1.
③ 나이트 점프 최단 경로: 체스의 나이트처럼 한 번에 (세로 2칸·가로 1칸) 또는 (세로 1칸·가로 2칸) 떨어진 칸으로 뛴다(8방향). 착지하는 칸은 지도 안의 통로여야 하고, 뛰어넘는 칸은 벽이어도 된다. (1,1)에서 (N,M)까지 최소 몇 번 뛰어야 하는지 구한다. 갈 수 없으면 -1.

[입력]
첫 줄에 N, M (2 ≤ N, M ≤ 100)
다음 N줄에 한 줄마다 M개의 문자('0' 또는 '1')가 공백 없이 주어진다.

[출력]
①, ②, ③의 답을 한 줄에 하나씩 차례로 출력한다.

[예제 입력 1]
4 6
110111
011001
111101
100111

[예제 출력 1]
1
9
4

[예제 입력 2]
3 4
1010
0001
0101

[예제 출력 2]
4
-1
3

### P2-14 (0.71점)

[P2-14 A형] 던전 이벤트 점검  (시간 제한 1초 · 메모리 256MB · C++17)

이벤트 두 가지를 점검하는 프로그램을 작성한다. 입력에는 두 이벤트의 데이터가 차례로 들어 있고, 답도 두 줄로 출력한다.

[이벤트 1] 순간이동 정령
수직선 위 위치 N에 플레이어가 있고, 위치 K에 포털이 있다. 플레이어는 1초마다 현재 위치 X에서 X-1, X+1, 2×X 중 한 곳으로 이동한다. 위치는 항상 0 이상 100,000 이하여야 하며, 이 범위를 벗어나는 이동은 할 수 없다. 포털에 도착하는 최소 시간(초)을 구하라.

[이벤트 2] 불길 확산
R행 C열 격자에 불 'F', 풀 '.', 바위 '#'가 있다. 처음 불은 0분에 붙어 있다. 그 뒤 1분마다, 불이 붙은 모든 칸에서 상하좌우로 맞닿은 풀 칸에 동시에 불이 옮겨붙는다. 바위는 타지 않고 불을 막는다. 모든 풀이 타는 데 걸리는 최소 시간(분)을 구하라. 처음부터 풀이 없으면 0을, 끝까지 타지 않는 풀이 있으면 -1을 출력한다.

[입력]
첫째 줄: N K (0 ≤ N, K ≤ 100,000)
둘째 줄: R C (1 ≤ R, C ≤ 500)
다음 R줄: 길이 C의 문자열('F', '.', '#'). 'F'는 1개 이상 있다.

[출력]
첫째 줄에 이벤트 1의 답, 둘째 줄에 이벤트 2의 답을 출력한다.

[예제 입력 1]
3 11
3 5
F..#.
.#...
...#F

[예제 출력 1]
3
4

[예제 입력 2]
10 3
2 4
F#..
.#..

[예제 출력 2]
7
-1

### P2-15 (0.71점)

[P2-15 A형] 레이드 준비 그리디 5종  (시간 제한 1초 · 메모리 256MB · C++17)

레이드를 준비하며 생기는 다섯 가지 계산을 한 프로그램으로 처리한다. 입력의 다섯 블록을 차례로 읽고 답을 다섯 줄로 출력한다.

1. 골드 지불: 동전 N종이 있고 값은 A1 < A2 < … < AN이다. A1 = 1이고, A(i+1)은 항상 A(i)의 배수다. 각 동전은 개수 제한이 없다. 금액 K를 정확히 맞추는 데 필요한 동전의 최소 개수를 구하라.
2. 강화 대기열: P명이 강화 NPC 한 명에게 한 사람씩 차례로 강화를 맡긴다. i번째 사람의 강화에는 t_i분이 걸린다. 각 사람이 기다리는 시간은 '자기 강화가 끝날 때까지 걸린 시간'(앞사람들의 시간 + 자기 시간)이다. 순서를 마음대로 정할 때, 모든 사람의 기다리는 시간 합의 최솟값을 구하라.
3. 레이드 예약: Q개의 레이드 신청이 있고, 각 신청은 시작 시각 s와 끝 시각 e(s ≤ e)로 주어진다. 레이드는 한 번에 하나만 진행할 수 있다. 한 레이드가 끝나는 시각에 다음 레이드를 바로 시작할 수 있다. s = e인 레이드도 있으며 같은 규칙을 따른다(이런 레이드는 같은 시각에 여러 개가 이어질 수 있다). 진행할 수 있는 레이드의 최대 개수를 구하라.
4. 데미지 식: 숫자와 '+', '-'로만 된 식이 주어진다. 괄호를 원하는 곳에 원하는 만큼 쳐서 식의 값을 최소로 만들 때, 그 최솟값을 구하라.
5. 예비 무기: 파티원 n명에게 1번부터 n번까지 번호가 있다. L명은 무기를 잃어버렸고, R명은 예비 무기를 하나씩 가지고 있다. 예비 무기는 번호가 바로 앞(번호-1)이거나 바로 뒤(번호+1)인 사람에게만 빌려줄 수 있다. 예비 무기를 가진 사람이 자기 무기를 잃어버렸다면, 그 예비 무기는 자기가 쓰고 남에게 빌려줄 수 없다. 무기를 가진 채로 레이드에 참여할 수 있는 사람 수의 최댓값을 구하라.

[주석 요구] 제출 코드에 다음 세 가지를 각 1~2줄의 주석으로 남긴다. (a) 1번에서 큰 동전부터 쓰는 것이 왜 최선인지 (b) 2번의 정렬 기준과 그 근거 (c) 3번의 정렬 기준(같은 값일 때의 기준 포함)과 그 근거.

[입력]
N K
A1 A2 … AN
P
t1 t2 … tP
Q
s1 e1
…(Q줄)
식 (공백 없는 문자열 한 줄)
n L R
L명의 번호
R명의 번호

[제한]
1 ≤ N ≤ 10, 1 ≤ K ≤ 100,000,000, AN ≤ 1,000,000
1 ≤ P ≤ 1,000, 1 ≤ t_i ≤ 1,000
1 ≤ Q ≤ 100,000, 0 ≤ s ≤ e ≤ 2,000,000,000
식: 길이 50 이하이며 숫자로 시작하고 숫자로 끝난다. 각 수는 앞자리가 0이 아닌 5자리 이하의 자연수이고, 연산자가 연속으로 오지 않는다.
2 ≤ n ≤ 30, 1 ≤ L ≤ n, 1 ≤ R ≤ n. 한 목록 안에서는 번호가 겹치지 않는다.

[출력]
1~5번의 답을 한 줄에 하나씩 출력한다.

[예제 입력 1]
4 2780
1 10 100 500
4
3 1 4 2
5
1 4
3 5
0 6
5 7
8 9
20+30-15+5-10
5 2 2
2 4
1 3

[예제 출력 1]
15
20
3
20
5

[예제 입력 2]
3 99
1 5 25
3
5 5 5
4
2 2
1 2
2 3
3 3
50-40+30
4 2 1
2 3
3

[예제 출력 2]
11
30
4
-20
3

### P2-16 (1.07점)

[P2-16 A형] 아이템 서버 점검  (시간 제한 1초 · 메모리 256MB · C++17)

아이템 서버의 세 기능을 점검한다. 입력의 세 부분을 차례로 처리해 출력한다.

1부분. 코드 조회: 등록된 아이템 코드 N개가 있다(같은 값이 여러 번 나올 수 있다). 조회할 코드 Q개마다, 그 코드가 등록되어 있으면 1, 없으면 0을 한 줄에 하나씩 출력한다.
2부분. 마나 막대 자르기: 길이가 제각각인 마나 막대 K개가 있다. 모든 조각의 길이가 같도록 잘라 조각을 P개 이상 만들려 한다. 조각 길이는 양의 정수이고, 자르고 남은 부분은 버린다. 만들 수 있는 조각 길이의 최댓값을 구하라. 답이 1 이상인 경우만 주어진다.
3부분. 입장 게이트: 게이트 G개가 있고, 게이트 i는 손님 한 명을 처리하는 데 t_i분이 걸린다. 한 게이트는 한 번에 한 명만 처리하고, 비는 즉시 다음 손님을 받을 수 있다. 손님 M명은 자기가 원하는 게이트에서 처리받는다(기다렸다가 더 빠른 게이트로 가도 된다). 0분에 시작해 모든 손님의 처리가 끝나는 최소 시간을 구하라.

[입력]
N
a1 … aN
Q
q1 … qQ
K P
len1 … lenK
G M
t1 … tG

[제한]
1 ≤ N, Q ≤ 100,000, -2,147,483,648 ≤ a_i, q_i ≤ 2,147,483,647
1 ≤ K ≤ 10,000, K ≤ P ≤ 1,000,000, 1 ≤ len_i ≤ 2,147,483,647
1 ≤ G ≤ 100,000, 1 ≤ M ≤ 1,000,000,000, 1 ≤ t_i ≤ 1,000,000,000

[출력]
1부분의 답 Q줄, 이어서 2부분의 답 한 줄, 3부분의 답 한 줄을 출력한다.

[예제 입력 1]
5
7 -3 15 2 9
4
9 4 -3 100
3 8
250 410 175
3 10
7 3 5

[예제 출력 1]
1
0
1
0
87
15

[예제 입력 2]
3
2147483647 -2147483648 0
3
0 2147483647 -1
2 3
2147483647 2147483647
1 1000000000
1000000000

[예제 출력 2]
1
1
0
1073741823
1000000000000000000

### P2-17 (1.07점)

[P2-17 A형] 던전 규칙 계산기  (시간 제한 1초 · 메모리 256MB · C++17)

아래 두 함수는 길이 n인 다리에 길이 1과 2짜리 판자를 빈틈없이 까는 방법의 수 Bridge(n)을 구한다(Bridge(1)=1, Bridge(2)=2).

int Bridge(int n) {
    if (n <= 2) return n;
    return Bridge(n - 1) + Bridge(n - 2);
}

int BridgeDP(int n) {
    dp[1] = 1; dp[2] = 2;
    for (int i = 3; i <= n; i++)
        dp[i] = dp[i - 1] + dp[i - 2];   // ②
    return dp[n];
}

입력으로 주어지는 값들로 다음 다섯 가지를 구하라.
1. Bridge(a)를 한 번 호출했을 때 Bridge 함수가 호출되는 총 횟수(첫 호출 포함)와, BridgeDP(a)에서 ② 줄이 실행되는 횟수. 두 수를 공백으로 구분해 출력한다.
2. Bridge(b)를 1,000,000,007로 나눈 나머지.
3. 슬라임 수 S(c): 1일째에 갓 태어난 슬라임 1마리가 있다. 슬라임은 죽지 않는다. 태어난 날을 1일째로 셀 때, 4일째 되는 날부터 매일 새끼를 1마리씩 낳는다(새끼도 같은 규칙을 따른다). c일째의 슬라임 수를 구하라. 처음 12일은 다음과 같다.
   일: 1 2 3 4 5 6 7 8 9 10 11 12
   수: 1 1 1 2 3 4 6 9 13 19 28 41
4. 하루 골드 증감 기록 L개에서, 연속된 하루 이상의 구간을 골라 얻는 합의 최댓값.
5. 숫자 1에서 시작해 '+1', '×3', '×4' 중 하나를 한 번에 하나씩 적용해 x를 만들 때, 필요한 최소 연산 횟수.

[입력]
a
b
c
L
v1 v2 … vL
x

[제한]
1 ≤ a ≤ 30, 1 ≤ b ≤ 1,000,000, 1 ≤ c ≤ 100, 1 ≤ L ≤ 100,000, -1,000 ≤ v_i ≤ 1,000, 1 ≤ x ≤ 1,000,000

[출력]
1~5번의 답을 한 줄에 하나씩 출력한다(1번은 두 수).

[예제 입력 1]
5
4
6
6
-2 5 -1 3 -8 4
10

[예제 출력 1]
9 3
5
4
7
3

[예제 입력 2]
1
1
1
3
-5 -2 -9
1

[예제 출력 2]
1 0
1
1
-2
0

### P2-18 (1.07점)

[P2-18 A형] 왕국 건설 DP 4종  (시간 제한 1초 · 메모리 256MB · C++17)

네 가지 계산을 차례로 처리한다.

1. 성벽 깃발: 성벽 탑 N개가 일렬로 있고, 탑마다 빨강·초록·파랑 깃발 중 하나를 단다. 탑 i에 각 색을 다는 비용이 주어진다. 이웃한 두 탑의 깃발 색은 서로 달라야 한다. 비용 합의 최솟값을 구하라.
2. 보물 피라미드: 높이 T인 삼각형 모양으로 보석 값이 있다. 꼭대기에서 출발해, 한 줄 내려갈 때마다 바로 아래 왼쪽이나 바로 아래 오른쪽 칸으로 간다. 맨 아래 줄까지 지나간 칸 값의 합의 최댓값을 구하라.
3. 같은 점수 배열 s_1..s_S로 두 규칙의 답을 공백으로 구분해 출력한다.
   (가) 징검다리: 강가(돌이 아니다)에서 출발해 한 번에 1개 또는 2개 앞의 돌로 뛴다. 연속한 세 개의 돌을 모두 밟을 수는 없다(강가는 돌로 치지 않는다). 마지막 S번째 돌은 반드시 밟아야 한다. 밟은 돌 점수 합의 최댓값을 구한다.
   (나) 보물 상자: 상자 S개가 일렬로 있고 i번째 상자의 점수는 s_i다. 원하는 상자를 몇 개든 열 수 있지만, 연속으로 놓인 세 상자를 모두 열 수는 없다. 마지막 상자를 꼭 열 필요는 없다. 연 상자 점수 합의 최댓값을 구한다.
4. 마법 숫자: 이웃한 두 자리 숫자의 차가 정확히 2인 L자리 양의 정수(예: 1357, 202, 86)의 개수를 1,000,000,007로 나눈 나머지. 첫 자리는 0일 수 없다. L=1이면 1~9의 9개다.

[입력]
N
다음 N줄: r g b
T
다음 T줄: i번째 줄에 i개의 정수
S
s1 … sS
L

[제한]
2 ≤ N ≤ 1,000, 비용은 1~1,000
1 ≤ T ≤ 500, 보석 값은 0~9,999
1 ≤ S ≤ 10,000, 0 ≤ s_i ≤ 1,000
1 ≤ L ≤ 100

[출력]
네 줄에 1~4의 답을 출력한다(3번째 줄은 두 수).

[예제 입력 1]
3
30 50 20
10 60 40
50 30 70
3
5
3 8
7 2 6
6
10 1 1 20 30 1
2

[예제 출력 1]
60
19
42 61
15

[예제 입력 2]
2
1 2 3
3 2 1
1
7
1
42
1

[예제 출력 2]
2
7
42 42
9

### P2-19 (1.07점)

[P2-19 A형] 강화 기록과 원정 가방  (시간 제한 1초 · 메모리 256MB · C++17)

두 가지를 계산한다.

1. 강화 기록: 무기 강화 수치 기록 a_1..a_N이 시간 순서대로 있다. 순서를 유지한 채 몇 개를 골라 '뒤로 갈수록 엄격히 커지는' 부분 수열을 만들 때, 가장 긴 길이를 구하라.
2. 원정 가방: 물건 M개가 있고 물건 i의 무게는 w_i, 가치는 v_i다. 무게 합이 K 이하가 되도록 물건을 골라 가방에 넣는다. 각 물건은 최대 한 번만 넣을 수 있다. 가치 합의 최댓값을 구하라.

[구현 조건] 2번은 1차원 배열 dp[무게]로 풀어야 한다. 무게 반복을 큰 쪽에서 작은 쪽으로 도는 이유를 코드 주석으로 2~3줄 남긴다.

[입력]
N
a1 … aN
M K
다음 M줄: w v

[제한]
1 ≤ N ≤ 1,000, 1 ≤ a_i ≤ 1,000
1 ≤ M ≤ 100, 1 ≤ K ≤ 100,000, 1 ≤ w_i ≤ 100,000, 0 ≤ v_i ≤ 1,000

[출력]
첫째 줄에 1번의 답, 둘째 줄에 2번의 답을 출력한다.

[예제 입력 1]
7
3 8 4 9 2 10 5
4 10
5 10
4 40
6 30
3 50

[예제 출력 1]
4
90

[예제 입력 2]
5
5 5 5 5 5
2 3
4 100
3 1

[예제 출력 2]
1
1

### P2-20 (1.07점)

[P2-20 A형] 길드 운영 서버  (시간 제한 1초 · 메모리 256MB · C++17)

세 부분을 차례로 처리한다.

1부분. 의뢰 게시판: 명령 Q개가 차례로 주어진다. '1 r'은 보상 r인 의뢰를 등록한다. 의뢰 번호는 등록된 순서대로 1, 2, 3, …이다. '2'는 등록된 의뢰 중 보상이 가장 큰 의뢰를 꺼내 그 번호를 출력한다. 보상이 같은 의뢰가 여럿이면 번호가 가장 작은 것을 꺼낸다. 게시판이 비어 있으면 -1을 출력한다.
2부분. 마을 도로망: 마을 V개와 '양방향' 도로 E개가 있다. 마을 S에서 출발할 때 (가) 마을 T까지의 최단 거리(갈 수 없으면 -1)와 (나) 최단 거리가 D 이하인 마을의 수(S 포함)를 공백으로 구분해 한 줄에 출력한다.
3부분. 무너진 성: R행 C열 격자에 빈칸 '.'과 잔해 '#'가 있다. (1,1)에서 (R,C)까지 상하좌우로 이동한다. 잔해 칸에 들어가려면 그 잔해를 부숴야 한다. 부숴야 하는 잔해 수의 최솟값을 출력한다.

[입력]
Q
다음 Q줄: '1 r' 또는 '2'
V E S T D
다음 E줄: u v w (마을 u와 v를 잇는 길이 w의 양방향 도로)
R C
다음 R줄: 길이 C의 문자열

[제한]
1 ≤ Q ≤ 100,000, 0 ≤ r ≤ 1,000,000,000
2 ≤ V ≤ 20,000, 1 ≤ E ≤ 200,000, 1 ≤ w ≤ 1,000, 1 ≤ S, T ≤ V, S ≠ T, 0 ≤ D ≤ 1,000,000,000. 같은 두 마을 사이에 도로가 여러 개 있을 수 있다.
2 ≤ R, C ≤ 100, (1,1)과 (R,C)는 '.'이다.

[출력]
1부분: '2' 명령마다 한 줄씩 출력한다. 이어서 2부분 한 줄, 3부분 한 줄을 출력한다.

[예제 입력 1]
7
1 50
1 80
1 50
2
2
1 80
2
5 6 1 5 7
1 2 3
2 3 4
1 3 10
3 4 2
4 5 1
2 5 9
4 5
..#..
##.#.
...##
.##..

[예제 출력 1]
2
1
4
10 3
2

[예제 입력 2]
3
2
1 7
2
3 1 1 3 0
1 2 5
2 2
.#
#.

[예제 출력 2]
-1
1
-1 1
1

### P2-21 (0.71점)

[P2-21 A형] 일일 접속 로그  (시간 제한 1초 · 메모리 256MB · C++17)

N일 동안 하루마다 접속자 수의 변화량 a_1..a_N이 기록되어 있다(음수도 있다). 질의 Q개가 주어지며, 각 질의 's len'은 s일째부터 len일 동안(s일 ~ s+len-1일) 변화량의 합을 묻는다. 질의마다 답을 출력하라.

[입력]
N Q
a1 … aN
다음 Q줄: s len

[제한]
1 ≤ N, Q ≤ 100,000, -1,000 ≤ a_i ≤ 1,000, 1 ≤ s, 1 ≤ len, s + len - 1 ≤ N

[출력]
질의마다 한 줄에 합을 출력한다.

[예제 입력 1]
6 4
3 -2 7 0 -5 4
1 3
3 1
2 5
6 1

[예제 출력 1]
8
7
4
4

[예제 입력 2]
3 2
-1000 1000 -1000
1 3
2 2

[예제 출력 2]
-1000
0

### P2-22 (1.43점)

[P2-22 A형] [실전 세트 1/3] 보드게임 엔진 — 주사위 뱀과 연쇄 회전 로봇  (프로그래머스형 · C++17 · 각 테스트 1초)

이 문항은 함수 두 개를 구현한다(1-가 6점, 1-나 4점). 방향은 북(위, 행 -1), 동(오른쪽, 열 +1), 남(아래, 행 +1), 서(왼쪽, 열 -1) 네 가지다. '왼쪽으로 90° 회전'은 북→서→남→동→북, '오른쪽으로 90° 회전'은 북→동→남→서→북 순서로 바뀐다.

━ 1-가. 주사위 뱀 ━
vector<int> diceSnake(vector<string> board, string commands)

n×n 보드에서 각 칸은 '.'(빈칸), 'A'(사과), '#'(바위)다. 뱀은 길이 1로 (0,0)에서 동쪽을 보고 시작한다. 뱀의 머리 위에 주사위가 하나 놓여 있으며, 처음에는 윗면 1, 아랫면 6, 북쪽 면 2, 남쪽 면 5, 동쪽 면 3, 서쪽 면 4다. commands의 문자를 앞에서부터 하나씩 처리한다.
- 'L': 왼쪽으로 90° 회전, 'R': 오른쪽으로 90° 회전한다(주사위는 구르지 않는다).
- 'F': 머리가 바라보는 방향으로 한 칸 이동하려 한다. 그 칸이 보드 밖이거나, 바위이거나, 현재 뱀 몸이 차지한 칸(꼬리 칸 포함)이면 게임이 즉시 끝나고 남은 명령은 무시한다. 그렇지 않으면 다음을 순서대로 한다.
  ① 머리가 그 칸으로 이동하고, 주사위가 이동 방향으로 한 번 구른다.
  ② 그 칸에 사과가 있으면 사과는 사라지고 꼬리는 그대로다(길이 +1). 사과가 없으면 꼬리 칸을 비운다(길이 유지).
  ③ 구른 뒤 주사위의 아랫면 숫자를 점수에 더한다.
- 주사위가 구르는 규칙: 동쪽으로 구르면 동쪽 면→아랫면, 윗면→동쪽 면, 서쪽 면→윗면, 아랫면→서쪽 면이 된다(북·남 면은 그대로). 서쪽으로 구르면 서쪽 면→아랫면, 윗면→서쪽 면, 동쪽 면→윗면, 아랫면→동쪽 면이 된다. 북쪽으로 구르면 북쪽 면→아랫면, 윗면→북쪽 면, 남쪽 면→윗면, 아랫면→남쪽 면이 된다(동·서 면은 그대로). 남쪽으로 구르면 남쪽 면→아랫면, 윗면→남쪽 면, 북쪽 면→윗면, 아랫면→북쪽 면이 된다.
[점수, 게임이 끝났을 때(또는 명령이 다 끝났을 때) 뱀의 길이]를 반환한다.
제한: 2 ≤ n ≤ 20, board[0][0]은 '.', 1 ≤ commands 길이 ≤ 1,000.

입출력 예
board = ["....", "..A.", "....", "...."], commands = "FFRFF" → [15, 2]
board = ["...", "#..", "..."], commands = "FRFRFF" → [8, 1]
(예 2: F로 바닥면 3, R 후 F로 바닥면 5를 얻어 8점. R 후 서쪽 칸이 바위라 게임이 끝난다.)

━ 1-나. 연쇄 회전 로봇 ━
string chainTurn(string robots, vector<vector<int>> ops)

로봇 K대가 일렬로 서 있고, robots의 i번째 문자('N','E','S','W')는 i번 로봇(1부터)이 바라보는 방향이다. ops의 각 원소 [i, r]은 i번 로봇을 회전시키라는 명령이다. r=1이면 오른쪽(시계 방향) 90°, r=-1이면 왼쪽 90°다. 명령 하나를 처리하는 규칙은 다음과 같다.
- 먼저, 아무도 돌기 전의 방향을 기준으로 누가 어느 쪽으로 돌지 모두 정한다. i번 로봇은 r 방향으로 돈다. i에서 왼쪽으로 한 대씩 가며, 바로 오른쪽 로봇(j+1)이 돌기로 정해졌고 j번과 j+1번이 '같은 방향'을 보고 있었다면 j번은 j+1번과 반대 방향으로 돈다. 조건이 맞지 않는 로봇을 만나면 그 너머의 로봇은 돌지 않는다. 오른쪽으로도 같은 방식으로 퍼진다.
- 정해진 회전을 모든 로봇에 동시에 적용한다.
모든 명령을 처리한 뒤의 방향 문자열을 반환한다.
제한: 2 ≤ K ≤ 50, 1 ≤ ops 길이 ≤ 100.

입출력 예
robots = "NNEE", ops = [[2,1]] → "WEEE"
robots = "EEES", ops = [[1,-1],[4,1]] → "NSNW"
(예 1: 2번이 시계 방향으로 돈다. 1번은 2번과 같은 N이었으므로 반시계로 돈다. 3번(E)은 2번이 돌기 전 방향(N)과 다르므로 돌지 않는다.)

### P2-23 (1.07점)

[P2-23 A형] [실전 세트 2/3] 모임 장소 정하기  (프로그래머스형 · C++17 · 각 테스트 1초)

마을 n개(1~n번)가 '양방향' 도로로 이어져 있다. 친구들이 friends에 적힌 마을에 한 명씩 산다. 모두가 모일 마을 X(1~n 중 어디든, 친구가 사는 마을도 가능)를 정하려 한다. 각 친구는 자기 마을에서 X까지 최단 경로로 이동한다. 친구 전원이 X에 갈 수 있는 마을 중, 친구들의 이동 시간 합이 가장 작은 마을을 고른다. 합이 같은 마을이 여럿이면 번호가 가장 작은 마을을 고른다. [X, 이동 시간 합]을 반환하라. 친구 전원이 갈 수 있는 마을이 하나도 없으면 [-1, -1]을 반환한다.

vector<int> solution(int n, vector<vector<int>> roads, vector<int> friends)

[제한]
- 2 ≤ n ≤ 100
- 1 ≤ roads 길이 ≤ 5,000. roads[i] = [a, b, t]는 마을 a와 b를 잇는 이동 시간 t의 양방향 도로다(a ≠ b, 1 ≤ t ≤ 100,000).
- 같은 두 마을을 잇는 도로가 여러 개 있을 수 있다.
- 1 ≤ friends 길이 ≤ n, friends의 원소는 서로 다르다.

[입출력 예]
n = 5, roads = [[1,2,4],[2,3,3],[3,4,2],[4,5,6],[1,5,10],[2,4,8]], friends = [1,3,5] → [3, 15]
n = 4, roads = [[1,2,5],[3,4,1]], friends = [1,4] → [-1, -1]

[설명] 예 1에서 X=3이면 1→2→3(7) + 0 + 5→4→3(8) = 15로 가장 작다. 예 2에서는 1과 4가 서로 다른 덩어리에 있어 모일 수 있는 마을이 없다.

### P2-24 (1.43점)

[P2-24 A형] [실전 세트 3/3] 구조 거점 배치  (프로그래머스형 · C++17 · 각 테스트 1초)

재난 지도 grid에서 각 칸은 '.'(길), '#'(벽), 'H'(집), 'B'(구조 거점 후보지)다. 후보지 중 정확히 k곳을 골라 구조 거점을 연다. 구조대는 열린 거점들에서 동시에 출발해 상하좌우로 한 칸에 1분씩 이동한다. 벽이 아닌 칸('.', 'H', 'B')은 모두 지나갈 수 있고, 열지 않은 후보지도 지나갈 수 있다. 각 집의 구조 시간은 가장 가까운 열린 거점에서 그 집까지의 최단 이동 시간이다. 모든 집의 구조 시간 합이 가장 작아지도록 거점을 고를 때, 그 합을 반환하라. 어떻게 골라도 구조대가 가지 못하는 집이 생기면 -1을 반환한다.

int solution(vector<string> grid, int k)

[제한]
- 2 ≤ grid 행 수, 열 수 ≤ 20
- 'B'는 1~10개, 'H'는 1~50개, 1 ≤ k ≤ 'B'의 개수

[입출력 예]
grid = ["H..B.", ".#.#.", "B..#H", "...#.", "H.B.."], k = 2 → 7
grid = ["HB", "##", "BH"], k = 1 → -1
(예 2: 위아래가 벽으로 나뉘어 있어 거점 하나로는 두 집에 모두 갈 수 없다.)

[세트 기록] 실전 세트(P2-22~24)를 마치기 전에, 제출 저장소의 '실전세트-기록.md'에 세 문제 각각의 해결 여부(예제 통과 / 일부 / 미해결)와 걸린 시간(분)을 적어 세트 시간 안에 커밋한다.

## 3부-L 라이브 실기 (16.9점 · 720분)

- AI·인터넷 금지, 엔진 소스·공식 문서만 허용. 3블록 × 240분이고 블록마다 권장 시간 합은 200분 이하다(40분 여유).
- 블록1·2는 새 시험 프로젝트(A형 RuneArena·접두사 Rune, B형 DuskKeep·접두사 Dusk)에서, 블록3은 응시자 본인의 포트폴리오 저장소(UE5-ActionArena, 태그 exam-submit)를 채점자가 시험 PC에 Clone한 사본에서 한다. 채점자는 블록3 사본에 결함을 미리 심어 둔다.
- 과제마다 기능 브랜치 → PR → Squash merge로 올린다. PR 본문은 '무엇·왜, 테스트'면 충분하다(브랜치·커밋·PR 규칙은 3부-P의 P3-04·05에서 채점).
- 블록1에서 캐릭터(P3-10)를 끝내지 못했으면 블록2 시작 때 채점자가 주는 기준 커밋에서 시작할 수 있다. 이미 받은 블록1 점수는 바뀌지 않는다.

> **블록1 (240분 · 권장 합 200분)** — 새 시험 프로젝트: 세팅 · 저장소 · 디버깅 · AI-Off① · 프레임워크 · 캐릭터

### P3-01 (0.42점)

[3부-L 라이브·블록1·A형] 개발 환경 세팅 (권장 30분)
시작: UE 5.8·VS 설치 PC. 감독관이 VS 옵션 2개를 틀어 두었다. 프로젝트를 만들고 VS가 열리면 손을 든다(감독관이 VS 솔루션 설정을 한 번 바꾼다).
1) Games → Blank로 C:\Projects\RuneArena 생성: C++·Desktop·Scalable·Starter Content 끔.
2) 에디터 부하 줄이기: Scalability Medium, 에디터가 뒤에 있을 때 CPU를 덜 쓰게 하는 설정 켬.
3) VS: 커리큘럼의 언리얼용 옵션 3가지를 점검해 틀린 것을 고치고, 무엇이 틀렸는지 메모.
4) 감독관 개입 뒤 솔루션 구성·플랫폼·시작 프로젝트를 커리큘럼 기준으로 바로잡고, 바뀌어 있던 것을 메모.
5) 에디터 메뉴로 Actor 부모 C++ 클래스 RuneMarker 생성, VS에서 Ctrl+T로 .h/.cpp 열기.
6) 에디터를 닫고 BeginPlay의 Super::BeginPlay(); 세미콜론을 지워 VS에서 빌드 → 출력 창 첫 error 줄 기록 → 되돌려 빌드 → 빌드 시간 기록.
제출: 채점자 화면 확인(Ctrl+T로 .cpp 열기 시연), 메모(P3-02에서 docs/exam-log.md로 올림).

### P3-02 (0.85점)

[3부-L 라이브·블록1·A형] 게임 저장소 만들기 (권장 30분)
시작: C:\Projects\RuneArena(에디터 닫힘), 일부가 빠진 lfs-setup.txt(바탕화면), 설정이 틀어진 GitHub Desktop(시험 계정 로그인됨).
1) 계정·커밋 작성자 설정을 점검해 고치고 무엇이 틀렸는지 메모.
2) lfs-setup.txt를 커리큘럼 템플릿과 비교해 빠진 줄을 채운 뒤 최상위 .gitattributes로.
3) 폴더를 저장소로 생성(Ignore 템플릿·LFS 포함).
4) 첫 커밋 전 올라가면 안 되는 것을 점검해 제외.
5) 'chore: UE 5.8 프로젝트 생성'으로 main에 커밋하고, 공개 저장소 UE5-RuneArena로 올림.
6) docs/exam-log.md(P3-01 메모 포함):
(a) Source·Binaries·Config·DerivedDataCache·Saved·RuneArena.sln을 원본/생성물로 나누고, 유니티 폴더와의 대응 1줄 + 생성물을 안 올리는 이유
(b) '*.umap …' 줄과 '* text=auto'의 뜻
(c) 경로 이유(C:\Projects, OneDrive 피함)
exam-log.md는 첫 커밋에 같이 넣거나, 올린 뒤 브랜치 → PR(무엇·왜) → Squash merge로 올린다.
제출: UE5-RuneArena, 첫 커밋, exam-log.md.

### P3-06 (0.85점)

[3부-L 라이브·블록1·A형] 디버깅 시연 (권장 15분, 채점자 입회)
시작: P3-02까지 올린 main의 ARuneMarker. 브랜치 feat/rune-debug. 감독관 메모: "AActor::GetActorForwardVector()는 FRotator를 반환한다."
1) Super::BeginPlay() 아래에 Warning 수준 UE_LOG로 'RuneMarker Ready'를 출력한다. 그 줄에 중단점 → VS 디버거로 에디터 실행 → 액터 1개 배치 후 Play → 멈춘 상태의 호출 스택으로 BeginPlay를 누가 불렀는지 설명 → 실행 계속.
2) 에디터를 끄지 않고 문구를 'RuneMarker Ready v2'로 바꿔 반영하고 Output Log에서 확인한다. 이 방법으로 반영하면 안 되는 변경 2가지를 말한다.
3) AActor 선언(BeginPlay·Tick 선언 포함)이 있는 파일과 UE_LOG가 정의된 파일을 VS 기능만으로 찾아 경로를 말한다.
4) 메모를 엔진 소스로 검증해 참/거짓과 근거(파일·선언)를 일지(docs/exam-log.md)에.
제출: 입회 확인, PR(무엇·왜, 테스트) → Squash merge(UE_LOG 변경, docs/exam/callstack-a.png, 일지).

### P3-07 (0.85점)

[3부-L 라이브·블록1·A형] AI-Off ①: 룬 구슬 (권장 40분: C++ 30분 + BP 10분)
시작: P3-06까지 merge된 main. 브랜치 feat/rune-orb. 시작·종료 시각은 감독관이 기록.
1) ARuneOrb: StaticMesh 컴포넌트가 루트.
2) Tick에서 시작 위치 기준 Z 사인파 상하 이동 + Yaw 회전, 프레임레이트와 무관.
3) EditAnywhere: Amplitude(cm, 30), Frequency(초당 왕복, 1), YawSpeed(도/초, 90).
4) BP_RuneOrb 3개 배치: (20, 0.5, 45) / (60, 1.5, 180) / (10, 3, −90).
5) 일지에 성공/막힌 지점·걸린 시간.
제출: PR(무엇·왜, 테스트, GIF) → Squash merge, RuneOrb.h/.cpp, 일지.

### P3-09 (0.42점)

[3부-L 라이브·블록1·A형] 프레임워크 뼈대 (권장 25분)
시작: P3-07까지 merge된 main. 바탕화면의 L_RuneTrial.umap을 에디터를 닫은 채 Content/Rune/Maps에 넣고 시작. 감독관이 이 맵의 설정 하나를 바꿔 두었다. 브랜치 feat/rune-framework.
1) 빈 C++ ARuneGameMode·ARunePlayerController·ARuneCharacter를 알맞은 엔진 부모로.
2) BP 자식 3개를 Content/Rune/Core에 BP_ 접두사로.
3) 프로젝트 기본 GameMode·Pawn·PlayerController를 내 BP로.
4) L_RuneTrial에서 Play했을 때 내 캐릭터 대신 기본 구체 Pawn이 나오면 원인을 찾아 고치고 원인·메뉴를 일지(docs/exam-log.md)에.
5) Play 중 Outliner로 내 BP 인스턴스 확인.
제출: PR(무엇·왜, 테스트) → Squash merge(ini·BP·맵 변경 포함), 일지, 시연.

### P3-10 (1.27점)

[3부-L 라이브·블록1·A형] 3인칭 캐릭터와 입력 (권장 60분)
시작: P3-09까지 merge된 main. 브랜치 feat/rune-character-input.
1) 콘텐츠 팩으로 마네킹을 추가해 BP_RuneCharacter 메시로 지정.
2) C++로 카메라 붐(길이 350)과 카메라. 마우스를 돌리면 카메라만 돌고 캐릭터는 이동 방향을 본다.
3) Content/Rune/Input에 이동·시점·점프·질주 Input Action 4개와 Mapping Context 1개(IA_/IMC_ 접두사, 이름은 직접). 키: WASD 이동, 마우스 시점, Space 점프, Left Shift 질주.
4) 입력 에셋은 C++ 변수로 받아 BP에서 지정하고, 매핑 추가와 함수 연결은 C++에서.
5) Left Shift 동안 450 → 750, 떼면 450. 두 수치는 디테일 패널에서 바꿀 수 있게 하고, 나중에 데이터 에셋으로 옮길 곳임을 커리큘럼의 TODO 주석 형식으로 표시.
6) Play로 이동·시점·점프·질주 시연. 영상 끝에 BP_RuneCharacter의 질주 값을 600으로 바꿔 Play한 장면 포함.
제출: PR(무엇·왜, 테스트, GIF 또는 영상) → Squash merge, .h/.cpp.

> **블록2 (240분 · 권장 합 190분)** — 같은 시험 프로젝트: AI-Off② · AI-Off③ · 복제·RPC 실험

### P3-12 (1.69점)

[3부-L 라이브·블록2·A형] AI-Off ②: 상호작용 (권장 60분)
시작: 블록1까지 merge된 main(ARuneCharacter·블록1 IMC). 브랜치 feat/rune-interaction. 시작·종료 시각은 감독관이 기록.
1) IRuneInteractable: Interact(AActor* Interactor), GetInteractionText()(FText). C++·BP 양쪽에서 구현 가능.
2) URuneInteractionComponent: 매 프레임 검사 금지. 0.1초 주기로 캐릭터 위치에서 카메라가 보는 방향 250cm까지 반지름 25 구를 쓸어 대상 탐색. 대상이 바뀌었을 때만 BP에서도 받을 수 있는 OnFocusChanged(AActor*). E로 Interact. 컴포넌트가 끝날 때 주기 실행을 멈춘다.
3) ARuneGate(C++): Interact마다 Yaw 0↔90.
4) BP_RuneSign: BP에서만 구현(문구 출력).
5) 일지에 시간·막힌 지점, 0.1초로 정한 근거 1줄.
제출: PR(무엇·왜, 테스트, 영상) → Squash merge, 코드, 일지.

### P3-14 (1.69점)

[3부-L 라이브·블록2·A형] AI-Off ③: 체력·데미지·사망 (권장 90분)
시작: P3-12까지 merge된 main. 브랜치 feat/rune-health. 시작·종료 시각은 감독관이 기록.
1) URuneHealthComponent: 최대·현재 체력, 체력 변화(새 체력, 최대)·사망을 BP에서도 받는 이벤트 2개. 데미지는 엔진 데미지 함수 → 소유 액터 데미지 이벤트로만 받는다(컴포넌트 직접 호출 금지). 0 미만 없음, 사망 이벤트 1회.
2) ARuneSandbag(최대 100): 마우스 왼쪽 → 카메라 전방 트레이스 → 맞은 지점 정보를 담아 20. 0이 되면 사망 이벤트 로그(제거는 선택).
3) 플레이어(최대 60) 디버그 키 K: 누르고 있는 동안 0.5초마다 자신에게 15(타이머), 떼면 멈춤.
4) 플레이어 사망: State.Dead 태그, 입력 차단, 래그돌 또는 몽타주, 5초 뒤 제거.
5) 샌드백 체력바(화면 또는 머리 위)가 체력 변화 이벤트로만 갱신.
제출: PR(무엇·왜, 테스트, 샌드백 5타·K로 플레이어 사망 영상) → Squash merge, 일지(시간·막힌 지점).

### P3-25 (1.69점)

[3부-L 라이브·블록2·A형] 복제·RPC 실험 (권장 40분)
시작: P3-14까지 merge된 main. 브랜치 feat/netlab-door. 새 맵 L_NetLab에서 실험한다.
1) ARuneNetDoor: bReplicates=true. bool bIsOpen(ReplicatedUsing=OnRep_IsOpen). 서버만 값을 바꾸고 OnRep에서 문 Yaw를 0°/90°로 맞춘다. 리슨 서버 호스트 화면에서도 맞아야 한다.
2) 플레이어가 E를 누르면 ARuneCharacter의 Server RPC(ServerToggleDoor)를 거쳐 서버가 문을 열고 닫는다(P3-12 상호작용을 거쳐도, 새 입력을 만들어도 된다). 캐릭터에 int32 OpenCount(초기 0)를 COND_OwnerOnly로 복제하고, 닫힌 문을 열 때마다 연 사람만 +1 한다. 서버는 Client RPC(ClientShowOpenCount)로 그 플레이어에게만 '내가 연 횟수 N'을 띄우고, 열릴 때 NetMulticast(Unreliable)로 모두에게 효과음 또는 화면 메시지를 보여 준다.
3) Number of Players=2, Play As Listen Server, 네트워크 에뮬레이션(지연 200ms, 손실 5%)으로 검증한다. 영상에는 두 플레이어가 각각 한 번 이상 문을 열고, '내가 연 횟수'가 연 사람 창에만 뜨는 장면이 나와야 한다.
4) PR 본문에 RPC 3종과 OnRep이 각각 어느 머신에서 실행되는지 표로 적는다.
제출: PR(무엇·왜, 테스트, 실행 위치 표, 설정 화면 캡처 2장, 2창 나란히 30초 이내 mp4 또는 GIF) → Squash merge.

> **블록3 (240분 · 권장 합 200분)** — 본인 포트폴리오 저장소 사본: Git 사고 · 셀프 리뷰 · 테스트·치트 · 프로파일링 · 패키징 · TS

### P3-41 (0.85점)

[3부-L 라이브·블록3·A형] Git 사고 대응 (권장 25분, 채점자 진행)
블록3은 내 포트폴리오 저장소 사본에서 한다(채점자가 시험용 원격 저장소에 올려 시험 PC에 Clone해 둠). GitHub Desktop만 쓴다(명령어 없이). 상황마다 '상황 · 한 일 · 화면 캡처'를 메모한다. 메모·캡처는 ⑤ 전까지 저장소 밖 C:\ExamNotes에 둔다.
① 채점자가 '지금 어디까지 했는지' 묻는다. 아무 버튼도 누르지 않는다(Fetch도). 위쪽 Current Repository·Current Branch가 보이게 Changes 탭과 History 탭을 한 장씩 캡처하고, 지금 브랜치·바뀐 파일·Push 안 한 커밋을 적은 질문 글 1개를 쓴다. 끝나면 채점자가 상태를 정리한다.
② 로컬 main에서 README 첫 줄 끝에 ' — 2인 협동 웨이브 서바이벌'을 붙이고, 기본 무기 DataAsset(W8)의 데미지 배율을 2.0으로 바꿔 저장한다. 에디터를 닫고 커밋·Push한다. 안 되면 해결한다. 충돌이 나면 README는 두 문구를 모두 남기고, DataAsset은 내 쪽(main) 파일을 고른다.
③ 채점자가 main을 체크아웃한 상태에서 'Config/DefaultGame.ini에 게임 설명 한 줄 넣기(Project Settings → Project → Description과 같은 값, 메모장으로 고쳐도 된다)'를 지시한다. 커밋 전에 main인 것을 알아채고 새 브랜치로 옮긴 뒤 커밋 → PR → Squash merge → main에서 Pull origin.
④ 채점자가 .gitignore에 손을 대 두었다. Changes에 Binaries·Intermediate가 보이면 대응한다.
⑤ 메모·캡처를 docs/exam/으로 옮기고 git-incidents.md를 main에 커밋한다. (가) 커밋 메시지에 오타를 내고 Push 전에 바로잡는다. (나) md 끝에 '이미 Push한 커밋이라면 어떻게 하고 왜 그런지' 한 줄을 더한다. 프로젝트 최상위의 scratch.txt까지 체크해 커밋한 뒤, 그 커밋을 취소하고 md만 다시 커밋한다. 끝나면 Push origin.
제출: git-incidents.md(main 직접 커밋·Push), ③의 PR(무엇·왜, 테스트).

### P3-33 (0.85점)

[3부-L 라이브·블록3·A형] 셀프 리뷰 PR (권장 20분)
시작: P3-41 이후 main. 에디터는 닫고 한다. 채점자가 리뷰 범위에 결함 6개를 심어 두었다: 헤더 include 1곳, UPROPERTY 누락 1곳, 불필요한 Tick 1곳, const 누락 1곳, Build.cs 불필요 모듈 2개. 리뷰 의견 카드 6장(일부는 틀린 의견)이 있다.
리뷰 범위: UCombatComponent(W7)·UInteractionComponent(W5)의 .h/.cpp와 <내 모듈>.Build.cs. 이름이 다르면 채점자가 시작 때 같은 역할 파일을 알려 준다.
1) refactor/self-review 브랜치에서 결함을 찾아 고친다. 헤더 include는 전방 선언으로 바꾸고 include는 실제로 쓰는 .cpp로 옮긴다. 고친 곳마다 PR에 파일·줄·이유를 적는다.
2) Build.cs에서 쓰지 않는 모듈을 지운다. 지운 모듈마다 '안 쓴다'를 어떻게 확인했는지(검색어·결과)를 적고, 채점자가 고른 남긴 모듈 1개의 쓰는 곳(파일 하나)을 적는다. VS에서 빌드가 통과해야 한다.
3) PR에 카드 6장마다 채택/거절과 이유를 한 줄씩 남긴다.
4) PR 셀프 체크 '모든 줄을 설명할 수 있다'를 채운다. 채점자가 diff에서 고른 2줄을 1분 안에 설명한다. 엔진 소스(F12)로 확인한 내용 1개를 docs/exam/til-block3.md에 내 말로 적는다(같은 PR에 넣어도 된다).
제출: refactor/self-review PR(무엇·왜, 테스트) → Squash merge.

### P3-31 (1.27점)

[3부-L 라이브·블록3·A형] 자동화 테스트와 치트 (권장 35분)
시작: P3-33 merge 후 main. 채점자가 테스트로 잡아야 할 결함 2개(데미지 계산 1개, 웨이브 데이터 1개)를 심어 두었다. 기존 테스트를 보여 주는 과제가 아니다. 결함을 찾고, 새 테스트와 새 치트를 더한다.
1) test/automation 브랜치를 만든다. Tools → Session Frontend → Automation 탭(또는 Tools → Test Automation)에서 내 테스트 전체를 실행하고 결과를 캡처한다.
2) 실패한 테스트마다 원인을 찾아 고친다. 기존 테스트가 못 잡는 결함은 테스트나 검증 규칙을 먼저 더해 실패를 확인한 뒤 고친다.
3) 새 테스트 <내 접두사>.Damage.DefenseFloor를 IMPLEMENT_SIMPLE_AUTOMATION_TEST로 쓴다. 월드·액터 없이 내 데미지 함수만 불러 두 경우를 본다: 일반 공격에서 방어력 = 기본 데미지, 크리티컬에서 방어력 ≥ 기본 데미지 × 크리티컬 배율. 기대값은 내 공식으로 손으로 계산한다. PR에 게임 코드가 이 함수를 부르는 곳(파일·함수)을 1줄 적는다.
4) 웨이브 DataTable(W12)·무기 DataAsset(W8) 검증 테스트가 실제 에셋을 통과시키는지 결과로 보인다.
5) 내 치트 매니저(W19)에 새 Exec 치트 KillAllEnemies를 더한다. 살아 있는 적을 모두 기존 사망 경로로 처치해 웨이브가 다음 단계로 넘어가야 한다(PIE 1인). 기존 God·SkipWave·SpawnEnemy 5도 한 번씩 실행한다.
6) 전부 통과한 결과를 캡처하고 TESTING.md(테스트 목록·실행 방법·캡처)를 고친다. 블록3에서 찾았지만 못 고친 버그는 README Known Issues에 적는다(없으면 '없음').
제출: test/automation PR(무엇·왜, 테스트, 치트 시연 캡처나 짧은 영상) → Squash merge.

### P3-32 (1.27점)

[3부-L 라이브·블록3·A형] 프로파일링 (권장 35분)
시작: P3-31 merge 후 main. 채점자가 게임 스레드 비용을 키우는 결함 1개를 심어 두었다.
1) 노트북이면 전원을 연결하고, Windows 전원 모드를 '최고 성능'으로 둔다(캡처). 내 스트레스 맵(W18)에서 내 치트로 적 50 → 100마리와 투사체 100발을 바로 소환한다.
2) stat unit·stat fps·stat game을 켜고 캡처한다. Game·Draw·GPU 중 무엇이 병목인지와 근거를 적는다. 2인 PIE(Listen Server)로 한 번 더 실행해 stat net 캡처 1장을 남긴다.
3) Unreal Insights로 CPU 트레이스를 기록한다(화면 오른쪽 아래 Trace 메뉴 또는 Tools → Run Unreal Insights). W18에 넣은 내 스코프(웨이브 매니저·판정·AI 서비스 중) 1개 이상이 보이는 타임라인을 캡처하고, 게임 스레드 비용 상위 3개를 표(이름·ms)로 적는다. 액터 이름이 안 보이면 기록 전에 콘솔에 stat namedevents를 입력한다(확인 필요).
4) perf/<병목-이름> 브랜치에서, 원인으로 의심되는 함수에 TRACE_CPUPROFILER_EVENT_SCOPE와 SCOPE_CYCLE_COUNTER(내 stat 그룹)를 새로 넣고 stat <내 그룹>으로 확인한다. 심어진 결함을 짚는다.
5) 고치기 전과 후를 같은 조건(적 100·투사체 100, 같은 위치·카메라)에서 Game ms를 3번씩 읽어(PIE를 다시 시작하거나 같은 세션에서 10초 간격) 중간값을 PR 표에 적는다. docs/perf/02-performance-report.md에 '시험 블록3' 절(측정 환경·전후 표·배운 점 1줄)을 더한다.
제출: perf/<병목-이름> PR(무엇·왜, 테스트) → Squash merge.

### P3-34 (1.27점)

[3부-L 라이브·블록3·A형] Windows 패키징 (권장 40분, 패키징을 기다리는 동안 이 문항의 문서 작업 허용)
시작: P3-32 merge 후 main. 채점자가 패키징 결함 2개(쿠킹 때만 드러나는 것 1개, 시작 설정 1개)를 심어 두었다.
1) build/win-shipping 브랜치에서 Project Settings → Maps & Modes의 Game Default Map·Editor Startup Map·Default GameMode가 내 설계(README·원래 의도)와 맞는지 확인한다. 틀린 값은 고치고 전후를 캡처한다.
2) Platforms → Windows → Package Project로 Development 패키징을 한다. 실패하면 Output Log에서 첫 Error 줄(쿠킹)을 찾아 원문·원인을 적고 고친 뒤 다시 패키징한다.
3) Binary Configuration을 Shipping으로 바꿔 패키징한다. 기다리는 동안 Development 빌드를 3분 이상 실행하고, 실행 폴더의 <프로젝트 이름>\Saved\Logs에서 Error 줄이 0인지(남으면 원인) 확인한다.
4) Shipping 결과를 C:\ExamRun\A로 복사해 에디터 없이 10분 플레이한다. 의도한 맵으로 시작하는지 본다. Shipping의 Saved는 보통 %LOCALAPPDATA%\<프로젝트 이름>\Saved에 생긴다(없으면 실행 폴더 쪽도 확인). 그 Saved\Crashes가 비었는지 확인한다.
제출: build/win-shipping PR(에러 줄 원문, 원인, 수정, Maps & Modes 전후, 로그·크래시 폴더 캡처(경로가 보이게), 실행 폴더 캡처) → Squash merge.

### P3-36 (1.69점)

[3부-L 라이브·블록3·A형] 트러블슈팅 2건 (권장 45분)
시작: P3-34 merge 후 main. 채점자가 버그 제보 카드 2장(채점자가 심은 런타임 결함)을 준다. 둘 다 재현해 원인을 찾아 고치고, TS 2건을 docs/troubleshooting/에 쓴다(번호는 내 TS 번호를 이어서, TS-0NN-<증상>.md).
- 카드 1(네트워크): '2인 PIE(Listen Server)에서 웨이브가 바뀌어도 클라 화면의 웨이브 번호·남은 적 수가 그대로다. 서버 화면은 정상이다.' 근거: NetMode가 찍힌 로그 + (클라 쪽 중단점 콜스택 또는 서버·클라 두 창 캡처).
- 카드 2(AI): '근접 적이 플레이어와 멀리 떨어져 있는데도 제자리에서 공격 모션을 반복한다.' 근거: Visual Logger 녹화 캡처. 가설 표에 '판정 범위 문제' 1행을 넣고 DrawDebug로 확인한 결과(캡처)를 적는다.
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
