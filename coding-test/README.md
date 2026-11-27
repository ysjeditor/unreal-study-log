# coding-test

C++ 코딩테스트 풀이. 문제는 커리큘럼 HTML의 **오늘 학습 → 오늘의 코딩테스트** 카드에 날마다 정해져 있습니다 (아래는 전체 목록).

- `baekjoon/` — `문제번호-제목.cpp` (예: `1000-A+B.cpp`)
- `programmers/` — `lv단계-문제이름.cpp` (예: `lv1-완주하지-못한-선수.cpp`)

필수 **78문제**(M1~M5) + 🔁 재풀이 **18회**(M2~M5) + 모의 시험 4회와 월·수 재풀이(M6). 단계별 관문: 누적 20 → 36(+재풀이 4) → 52(+재풀이 8) → 68(+재풀이 12) → 78(+재풀이 18). M2·M3 금요일의 원래 문제 8개는 (선택)입니다.

## 처음 푸는 법 (백준)

1. **계정 (처음 한 번)** — acmicpc.net 오른쪽 위 `회원가입` → 로그인
2. **문제 읽기** — **입력·출력 형식**과 **예제**를 먼저 본다. 예제 입력을 넣었을 때 예제 출력과 **글자 하나까지** 똑같이 나와야 한다
3. **코드 쓸 곳 (처음 한 번)** — Visual Studio → `새 프로젝트 만들기` → `콘솔 앱`(C++) → 이름 `CodingTest`, 위치 `C:\Projects` → `만들기`. 앞으로 문제마다 이 프로젝트의 `.cpp` 내용을 지우고 새로 쓴다
4. **실행해 보기** — 아래 뼈대에서 시작 → `Ctrl+F5`(디버그 없이 실행) → 까만 창에 예제 입력을 직접 타이핑하고 `Enter` → 출력이 예제와 같은지 확인
5. **제출** — 문제 페이지 `제출` → 언어 **C++17** → 코드 붙여넣기 → `제출` → **맞았습니다!!**가 나오면 성공. `틀렸습니다`면 예제 말고 다른 입력(가장 작은 값·가장 큰 값)을 직접 넣어 본다
6. **저장** — 맞은 코드를 아래 표의 파일 이름으로 학습 로그 저장소에 저장 → 그날 TIL을 올릴 때 같이 커밋

```cpp
#include <iostream>
using namespace std;

int main() {
    // 입력: cin >> 변수;
    // 출력: cout << 값 << '\n';
    return 0;
}
```

> `using namespace std;`는 코딩테스트에서만 쓰는 습관입니다. 언리얼 코드에서는 쓰지 않아요.

## 막히면 (30분 뒤)

정답 코드 대신 **힌트만** 받습니다. 카드의 '💡 AI 힌트 받기'를 쓰세요. 힌트나 풀이를 보고 풀었다면 카드 아래 **💡 힌트나 풀이를 보고 풀었어요**에 체크해 두세요. 3일이 지나면 재풀이 날에 그 문제가 먼저 나옵니다.

## 🔁 재풀이 (W05~W16 금요일 · W19·W20 일부 · M6 월·수)

예전에 푼 문제를 **AI·검색 없이, 예전 코드를 보지 않고** 다시 풉니다. 타이머는 30분(M4·M6는 20분). 같은 파일에 새로 써서 커밋하면 diff로 전과 비교할 수 있어요. 시간을 넘기면 멈추고 막힌 곳만 TIL에 적은 뒤, 다음 재풀이 날에 한 번 더 합니다.

## M1 · C++ 문법 체득 (백준 단계별 문법 1~5)

| 주차 | 요일 | 문제 | 오늘의 C++ / 포인트 | 파일 |
|---|---|---|---|---|
| W01 | 월 | [백준 2557 · Hello World](https://www.acmicpc.net/problem/2557) | `#include <iostream>`, `int main()`, `cout << "...";` — C# `Console.WriteLine`과 비교 | `2557-Hello-World.cpp` |
| W01 | 화 | [백준 1000 · A+B](https://www.acmicpc.net/problem/1000) | `cin >> a >> b;`로 입력 받기, `int` 변수 선언 | `1000-A+B.cpp` |
| W01 | 수 | [백준 1008 · A/B](https://www.acmicpc.net/problem/1008) | 정수 나눗셈과 실수 나눗셈(`double`)의 차이, 소수점 자릿수 출력 `cout << fixed; cout.precision(9);` | `1008-A-B.cpp` |
| W01 | 목 | [백준 10869 · 사칙연산](https://www.acmicpc.net/problem/10869) | `/`(몫)와 `%`(나머지), 줄바꿈 `'\n'` | `10869-사칙연산.cpp` |
| W01 | 금 | [백준 2588 · 곱셈](https://www.acmicpc.net/problem/2588) | `%`와 `/`로 자릿수 꺼내기 (385 → 5, 8, 3) | `2588-곱셈.cpp` |
| W02 | 월 | [백준 1330 · 두 수 비교하기](https://www.acmicpc.net/problem/1330) | `if` / `else if` / `else` — C#과 문법이 같다 | `1330-두-수-비교하기.cpp` |
| W02 | 화 | [백준 9498 · 시험 성적](https://www.acmicpc.net/problem/9498) | 범위 조건을 위에서부터 차례로 검사하기 | `9498-시험-성적.cpp` |
| W02 | 수 | [백준 2753 · 윤년](https://www.acmicpc.net/problem/2753) | `&&`(그리고) · `\|\|`(또는)와 괄호로 조건 묶기 | `2753-윤년.cpp` |
| W02 | 목 | [백준 2884 · 알람 시계](https://www.acmicpc.net/problem/2884) | 시간을 '분'으로 바꿔 계산 — 제출 전에 예제 말고 **경계 입력** 2개를 내가 만들어 넣어 본다: 가장 이른 시각 `0 0`, 45분을 빼면 앞 시간으로 넘어가는 `1 10`(답을 손으로 먼저 적고 비교). '틀렸습니다'가 나와도 이렇게 끝값부터 넣어 본다 | `2884-알람-시계.cpp` |
| W02 | 금 | [백준 2739 · 구구단](https://www.acmicpc.net/problem/2739) | `for (int i = 1; i <= 9; ++i)` 반복문 | `2739-구구단.cpp` |
| W03 | 월 | [백준 10950 · A+B - 3](https://www.acmicpc.net/problem/10950) | 테스트 케이스 개수 T를 먼저 받고 T번 반복하기 | `10950-A+B-3.cpp` |
| W03 | 화 | [백준 15552 · 빠른 A+B](https://www.acmicpc.net/problem/15552) | `ios::sync_with_stdio(false); cin.tie(nullptr);`, `endl` 대신 `'\n'` — 입출력이 많을 때의 속도 | `15552-빠른-A+B.cpp` |
| W03 | 수 | [백준 2438 · 별 찍기 - 1](https://www.acmicpc.net/problem/2438) | 이중 `for` (바깥 = 줄 번호, 안쪽 = 별 개수) | `2438-별-찍기-1.cpp` |
| W03 | 목 | [백준 10807 · 개수 세기](https://www.acmicpc.net/problem/10807) | `vector<int>`에 입력 저장하기 — C# `List<int>` ↔ `vector<int>` | `10807-개수-세기.cpp` |
| W03 | 금 | [백준 10818 · 최소, 최대](https://www.acmicpc.net/problem/10818) | 최솟값·최댓값 변수의 시작값 정하기, `min()` / `max()` — 제출 전에 경계 입력을 내가 만든다: N이 1일 때, 모든 수가 음수일 때(`3` / `-5 -1 -9`)도 맞나? | `10818-최소-최대.cpp` |
| W04 | 월 | [백준 3052 · 나머지](https://www.acmicpc.net/problem/3052) | `bool` 배열로 '이 값이 나온 적 있나' 표시하기 | `3052-나머지.cpp` |
| W04 | 화 | [백준 1546 · 평균](https://www.acmicpc.net/problem/1546) | `int`를 `double`로 바꿔 계산하기 (형 변환) | `1546-평균.cpp` |
| W04 | 수 | [백준 27866 · 문자와 문자열](https://www.acmicpc.net/problem/27866) | `std::string`과 인덱스 접근 `s[i]` (0부터 시작) | `27866-문자와-문자열.cpp` |
| W04 | 목 | [백준 11720 · 숫자의 합](https://www.acmicpc.net/problem/11720) | 문자 `'7'`을 숫자 7로 바꾸기: `c - '0'` | `11720-숫자의-합.cpp` |
| W04 | 금 | [백준 2675 · 문자열 반복](https://www.acmicpc.net/problem/2675) | 범위 기반 for `for (char c : s)`로 한 글자씩 돌기 | `2675-문자열-반복.cpp` |

## M2 · 브루트포스 · 정렬 · 집합과 맵 · 스택/큐/덱

| 주차 | 요일 | 문제 | 오늘의 C++ / 포인트 | 파일 |
|---|---|---|---|---|
| W05 | 월 | [백준 2798 · 블랙잭](https://www.acmicpc.net/problem/2798) | 3중 `for`로 모든 조합 검사 (i < j < k) | `2798-블랙잭.cpp` |
| W05 | 화 | [백준 2231 · 분해합](https://www.acmicpc.net/problem/2231) | 1부터 차례로 다 해 보기 + '자릿수 합' 함수 따로 만들기 | `2231-분해합.cpp` |
| W05 | 수 | [백준 2839 · 설탕 배달](https://www.acmicpc.net/problem/2839) | 5kg 봉지를 가장 많이 쓴 경우부터 하나씩 줄이며, 남은 무게가 3으로 나누어떨어지는 첫 경우가 답(끝까지 없으면 -1) — 5kg만 최대로 담고 끝내면 6kg 같은 입력에서 틀린다 | `2839-설탕-배달.cpp` |
| W05 | 목 | [백준 1436 · 영화감독 숌](https://www.acmicpc.net/problem/1436) | `to_string(n)`과 `find("666")`로 문자열 검사 | `1436-영화감독-숌.cpp` |
| W05 | 금 | [백준 10818 · 최소, 최대](https://www.acmicpc.net/problem/10818) | 🔁 **재풀이** (W03 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 19532 · 수학은 비대면강의입니다](https://www.acmicpc.net/problem/19532) — 범위가 작으면 방정식도 전부 대입해 본다 | `10818-최소-최대.cpp`<br>`19532-수학은-비대면강의입니다.cpp` |
| W06 | 월 | [백준 2750 · 수 정렬하기](https://www.acmicpc.net/problem/2750) | `#include <algorithm>`의 `sort(v.begin(), v.end())` | `2750-수-정렬하기.cpp` |
| W06 | 화 | [백준 1427 · 소트인사이드](https://www.acmicpc.net/problem/1427) | `string`도 정렬된다, 내림차순은 `greater<char>()` | `1427-소트인사이드.cpp` |
| W06 | 수 | [백준 11650 · 좌표 정렬하기](https://www.acmicpc.net/problem/11650) | `pair<int, int>`를 담은 `vector` 정렬 (첫 값 → 둘째 값 순) | `11650-좌표-정렬하기.cpp` |
| W06 | 목 | [백준 1181 · 단어 정렬](https://www.acmicpc.net/problem/1181) | 정렬 기준을 **람다**로 직접 정하기 (W5 람다 복습) + 중복 제거 `v.erase(unique(v.begin(), v.end()), v.end())` — `unique`는 겹치지 않는 값을 앞으로 모으고 새 끝 위치만 돌려준다. 실제로 지우는 것은 `erase` | `1181-단어-정렬.cpp` |
| W06 | 금 | [백준 2231 · 분해합](https://www.acmicpc.net/problem/2231) | 🔁 **재풀이** (W05 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 2587 · 대표값2](https://www.acmicpc.net/problem/2587) — 정렬한 뒤 가운데 값 = 중앙값 | `2231-분해합.cpp`<br>`2587-대표값2.cpp` |
| W07 | 월 | [백준 10815 · 숫자 카드](https://www.acmicpc.net/problem/10815) | `unordered_set`의 `count()`로 '있나?' 빠르게 확인 — 언리얼 `TSet`과 같은 역할 | `10815-숫자-카드.cpp` |
| W07 | 화 | [백준 10816 · 숫자 카드 2](https://www.acmicpc.net/problem/10816) | `map`으로 개수 세기 `cnt[x]++` — 없는 키를 `[]`로 읽으면 0으로 새로 생긴다(C# `Dictionary`는 예외가 난다). 카드가 50만 장이라 빠른 입출력 | `10816-숫자-카드-2.cpp` |
| W07 | 수 | [백준 7785 · 회사에 있는 사람](https://www.acmicpc.net/problem/7785) | `set`은 자동 정렬된다 + `erase`, 역순으로 출력하기 | `7785-회사에-있는-사람.cpp` |
| W07 | 목 | [백준 1620 · 나는야 포켓몬 마스터 이다솜](https://www.acmicpc.net/problem/1620) | `unordered_map<string, int>` + `vector<string>`로 양방향 찾기 — 질문의 첫 글자가 숫자(`isdigit(s[0])`)면 번호→이름, 아니면 이름→번호. C# `Dictionary`, 언리얼 `TMap` | `1620-나는야-포켓몬-마스터-이다솜.cpp` |
| W07 | 금 | [백준 1181 · 단어 정렬](https://www.acmicpc.net/problem/1181) | 🔁 **재풀이** (W06 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 14425 · 문자열 집합](https://www.acmicpc.net/problem/14425) — `unordered_set<string>` — 해시 기반이라 평균 O(1) 검색 | `1181-단어-정렬.cpp`<br>`14425-문자열-집합.cpp` |
| W08 | 월 | [백준 10773 · 제로](https://www.acmicpc.net/problem/10773) | `stack<int>`의 `push` · `pop` · `top` | `10773-제로.cpp` |
| W08 | 화 | [백준 9012 · 괄호](https://www.acmicpc.net/problem/9012) | 스택으로 짝 맞추기 (여는 괄호 push, 닫는 괄호 pop) | `9012-괄호.cpp` |
| W08 | 수 | [백준 28279 · 덱 2](https://www.acmicpc.net/problem/28279) | `deque<int>` — 앞뒤 양쪽에서 넣고 빼기(`push_front`·`push_back`·`pop_front`·`pop_back`) + 빠른 입출력(명령이 100만 개) | `28279-덱-2.cpp` |
| W08 | 목 | [백준 2164 · 카드2](https://www.acmicpc.net/problem/2164) | 큐로 '맨 위 버리고, 다음 장은 맨 아래로' 시뮬레이션 | `2164-카드2.cpp` |
| W08 | 금 | [백준 10816 · 숫자 카드 2](https://www.acmicpc.net/problem/10816) | 🔁 **재풀이** (W07 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 18258 · 큐 2](https://www.acmicpc.net/problem/18258) — `queue<int>`의 `front` · `back` · `pop` + 빠른 입출력 | `10816-숫자-카드-2.cpp`<br>`18258-큐-2.cpp` |

## M3 · 재귀 · 백트래킹 · DFS/BFS

| 주차 | 요일 | 문제 | 오늘의 C++ / 포인트 | 파일 |
|---|---|---|---|---|
| W09 | 월 | [백준 27433 · 팩토리얼 2](https://www.acmicpc.net/problem/27433) | 자기 자신을 부르는 함수 + 종료 조건, 큰 수는 `long long` | `27433-팩토리얼-2.cpp` |
| W09 | 화 | [백준 10870 · 피보나치 수 5](https://www.acmicpc.net/problem/10870) | 재귀 호출이 두 갈래로 나뉘는 모양을 종이에 그려 보기 | `10870-피보나치-수-5.cpp` |
| W09 | 수 | [백준 25501 · 재귀의 귀재](https://www.acmicpc.net/problem/25501) | 재귀 호출 횟수 세기 — 참조 매개변수 `int&`로 넘기기 | `25501-재귀의-귀재.cpp` |
| W09 | 목 | [백준 4779 · 칸토어 집합](https://www.acmicpc.net/problem/4779) | 문제를 '3등분 → 가운데 지우기 → 양쪽은 같은 문제'로 쪼개기 | `4779-칸토어-집합.cpp` |
| W09 | 금 | [백준 1620 · 나는야 포켓몬 마스터 이다솜](https://www.acmicpc.net/problem/1620) | 🔁 **재풀이** (W07 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 11729 · 하노이 탑 이동 순서](https://www.acmicpc.net/problem/11729) — 먼저 n=1·2·3을 손으로 옮겨 본다 → 함수 모양 `hanoi(n, from, to, via)`를 정하고 '맨 아래 1개를 옮기려면 위 n-1개를 어디로?'를 말로 쓴 뒤 코드로 — 이동 횟수는 2^n - 1 | `1620-나는야-포켓몬-마스터-이다솜.cpp`<br>`11729-하노이-탑-이동-순서.cpp` |
| W10 | 월 | [백준 15649 · N과 M (1)](https://www.acmicpc.net/problem/15649) | 백트래킹 첫 문제는 틀을 보고 따라 쓴다: `void dfs(int depth) { if (depth == M) { 출력; return; } for (int i = 1; i <= N; i++) { if (visited[i]) continue; visited[i] = true; pick[depth] = i; dfs(depth + 1); visited[i] = false; } }` → N=3, M=2의 호출 트리를 종이에 그리고 마지막 줄(되돌리기)이 왜 필요한지 한 줄로 (이번 주 Behavior Tree처럼 트리를 탐색) | `15649-N과-M-(1).cpp` |
| W10 | 화 | [백준 15650 · N과 M (2)](https://www.acmicpc.net/problem/15650) | 시작 번호를 매개변수로 넘겨 오름차순만 만들기 | `15650-N과-M-(2).cpp` |
| W10 | 수 | [백준 15651 · N과 M (3)](https://www.acmicpc.net/problem/15651) | 중복을 허용하면 `visited`가 필요 없다 | `15651-N과-M-(3).cpp` |
| W10 | 목 | [백준 15652 · N과 M (4)](https://www.acmicpc.net/problem/15652) | 비내림차순 — (2)와 (3)의 조합 | `15652-N과-M-(4).cpp` |
| W10 | 금 | [백준 2164 · 카드2](https://www.acmicpc.net/problem/2164) | 🔁 **재풀이** (W08 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 14888 · 연산자 끼워넣기](https://www.acmicpc.net/problem/14888) — 남은 연산자 개수를 '상태'로 들고 다니는 백트래킹 — 연산자 하나를 쓰면 개수를 줄이고 재귀, 돌아오면 다시 늘린다(15649의 '고르고 → 되돌리기'와 같은 틀). 최댓값·최솟값 초기값은 ±10억 바깥으로 | `2164-카드2.cpp`<br>`14888-연산자-끼워넣기.cpp` |
| W11 | 월 | [백준 24479 · 알고리즘 수업 - 깊이 우선 탐색 1](https://www.acmicpc.net/problem/24479) | 인접 리스트 `vector<int> adj[N]`(간선마다 양쪽에 `push_back`, 작은 번호부터 가려면 `sort`) + 재귀 DFS 틀: `void dfs(int v) { visited[v] = true; order[v] = ++cnt; for (int nx : adj[v]) if (!visited[nx]) dfs(nx); }` — 틀을 보고 쓴 뒤 작은 그래프로 방문 순서를 손으로 따라가 본다 | `24479-알고리즘-수업-깊이-우선-탐색-1.cpp` |
| W11 | 화 | [백준 24444 · 알고리즘 수업 - 너비 우선 탐색 1](https://www.acmicpc.net/problem/24444) | `queue`로 BFS 틀: 시작점을 넣고 표시 → 큐가 빌 때까지 앞에서 꺼내고 → 안 간 이웃을 표시하고 넣는다 — '넣을 때 표시'해야 같은 정점이 두 번 들어가지 않는다. 가까운 곳부터 방문 | `24444-알고리즘-수업-너비-우선-탐색-1.cpp` |
| W11 | 수 | [백준 2606 · 바이러스](https://www.acmicpc.net/problem/2606) | DFS/BFS로 '연결된 정점 수' 세기 | `2606-바이러스.cpp` |
| W11 | 목 | [백준 1260 · DFS와 BFS](https://www.acmicpc.net/problem/1260) | 같은 그래프를 두 방식으로 — 방문 순서 차이 비교 | `1260-DFS와-BFS.cpp` |
| W11 | 금 | [백준 15649 · N과 M (1)](https://www.acmicpc.net/problem/15649) | 🔁 **재풀이** (W10 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 2667 · 단지번호붙이기](https://www.acmicpc.net/problem/2667) — 2차원 격자도 그래프다: `dx[4]`·`dy[4]` + 2차원 `visited` — 아직 안 간 1을 만날 때마다 DFS/BFS 한 번 = 단지 1개, 방문한 칸 수 = 단지 크기 (24479 DFS와 같은 틀) | `15649-N과-M-(1).cpp`<br>`2667-단지번호붙이기.cpp` |
| W12 | 월 | [백준 1012 · 유기농 배추](https://www.acmicpc.net/problem/1012) | 격자 탐색 틀(W11 (선택) 2667과 같다): `int dx[4] = {1, -1, 0, 0}, dy[4] = {0, 0, 1, -1};` → 이웃 `(x + dx[k], y + dy[k])`가 범위 안 · 배추 · 안 간 칸이면 방문 — 안 간 배추를 만날 때마다 DFS/BFS 한 번 = 덩어리 1개 | `1012-유기농-배추.cpp` |
| W12 | 화 | [백준 2178 · 미로 탐색](https://www.acmicpc.net/problem/2178) | BFS = 가중치 없는 최단 거리 (거리 배열 `dist`) | `2178-미로-탐색.cpp` |
| W12 | 수 | [백준 1697 · 숨바꼭질](https://www.acmicpc.net/problem/1697) | 1차원 BFS: +1 / -1 / ×2 이동 | `1697-숨바꼭질.cpp` |
| W12 | 목 | [백준 7562 · 나이트의 이동](https://www.acmicpc.net/problem/7562) | 이동 방향 8개를 배열로 두기 | `7562-나이트의-이동.cpp` |
| W12 | 금 | [백준 15652 · N과 M (4)](https://www.acmicpc.net/problem/15652) | 🔁 **재풀이** (W10 문제) — AI·검색 없이 30분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터<br>(선택) 시간이 남으면 원래 금요일 문제 [백준 7576 · 토마토](https://www.acmicpc.net/problem/7576) — 시작점이 여러 개인 BFS — 처음에 익은 토마토(1)를 모두 큐에 넣고 시작, `dist`(날짜) 배열로 퍼진 날을 적는다. 끝나고 0이 남으면 -1 (2178 미로 탐색과 같은 틀) | `15652-N과-M-(4).cpp`<br>`7576-토마토.cpp` |

## M4 · 그리디 · 이분 탐색 · DP 기초

| 주차 | 요일 | 문제 | 오늘의 C++ / 포인트 | 파일 |
|---|---|---|---|---|
| W13 | 월 | [백준 11047 · 동전 0](https://www.acmicpc.net/problem/11047) | 큰 동전부터 쓰는 게 왜 항상 최선인지 말로 설명해 보기 | `11047-동전-0.cpp` |
| W13 | 화 | [백준 11399 · ATM](https://www.acmicpc.net/problem/11399) | 정렬 후 누적 합 — '짧은 사람 먼저' | `11399-ATM.cpp` |
| W13 | 수 | [백준 1931 · 회의실 배정](https://www.acmicpc.net/problem/1931) | 끝나는 시간 기준 정렬 — 정렬 기준 선택이 핵심 | `1931-회의실-배정.cpp` |
| W13 | 목 | [백준 1541 · 잃어버린 괄호](https://www.acmicpc.net/problem/1541) | `-`가 나온 뒤는 전부 빼기 — 파싱: 문자를 하나씩 보며 숫자면 `num = num * 10 + (c - '0')`, 기호를 만나면 지금까지의 숫자를 더하거나 뺀다 | `1541-잃어버린-괄호.cpp` |
| W13 | 금 | [Lv.1 폰켓몬](https://school.programmers.co.kr/learn/courses/30/lessons/1845) | 🔁 **재풀이** (프로그래머스 형식 · 해시) — AI·검색 없이 20분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터 · `solution` 함수로 | `lv1-폰켓몬.cpp` |
| W14 | 월 | [백준 1920 · 수 찾기](https://www.acmicpc.net/problem/1920) | 정렬 + `binary_search`, 또는 `lo` / `hi` / `mid`로 직접 구현 | `1920-수-찾기.cpp` |
| W14 | 화 | [백준 1654 · 랜선 자르기](https://www.acmicpc.net/problem/1654) | '답'을 이분 탐색하기 (매개변수 탐색), `long long` | `1654-랜선-자르기.cpp` |
| W14 | 수 | [백준 2805 · 나무 자르기](https://www.acmicpc.net/problem/2805) | 조건을 만족하는 최댓값 찾기 — 1654와 같은 틀 | `2805-나무-자르기.cpp` |
| W14 | 목 | [백준 2110 · 공유기 설치](https://www.acmicpc.net/problem/2110) | 1654·2805와 같은 틀 — ① 판정 함수 `can(d)`: 집을 정렬하고 첫 집에 설치, 직전 설치 위치와 d 이상 떨어진 집마다 설치해 C개 이상이면 참 ② `can(d)`가 참인 가장 큰 d를 이분 탐색 | `2110-공유기-설치.cpp` |
| W14 | 금 | [백준 2178 · 미로 탐색](https://www.acmicpc.net/problem/2178) | 🔁 **재풀이** (W12 문제) — AI·검색 없이 20분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터 | `2178-미로-탐색.cpp` |
| W15 | 월 | [백준 24416 · 알고리즘 수업 - 피보나치 수 1](https://www.acmicpc.net/problem/24416) | 재귀와 DP의 호출 횟수 비교 — 계산 결과를 저장해 두는 이유 | `24416-알고리즘-수업-피보나치-수-1.cpp` |
| W15 | 화 | [백준 1904 · 01타일](https://www.acmicpc.net/problem/1904) | 점화식 `dp[i] = dp[i-1] + dp[i-2]`와 나머지 연산 | `1904-01타일.cpp` |
| W15 | 수 | [백준 9461 · 파도반 수열](https://www.acmicpc.net/problem/9461) | 규칙을 찾아 점화식 세우기, `long long` | `9461-파도반-수열.cpp` |
| W15 | 목 | [백준 1912 · 연속합](https://www.acmicpc.net/problem/1912) | 'i번째에서 끝나는 최댓값'으로 상태 정의 — 'i-1에서 끝난 합에 이어 붙일까, i에서 새로 시작할까' 두 갈래만 비교, 답은 전체 중 최댓값 | `1912-연속합.cpp` |
| W15 | 금 | [백준 2110 · 공유기 설치](https://www.acmicpc.net/problem/2110) | 🔁 **재풀이** (W14 문제) — AI·검색 없이 20분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터 | `2110-공유기-설치.cpp` |
| W16 | 월 | [백준 1149 · RGB거리](https://www.acmicpc.net/problem/1149) | 2차원 DP `dp[i][색]` | `1149-RGB거리.cpp` |
| W16 | 화 | [백준 1932 · 정수 삼각형](https://www.acmicpc.net/problem/1932) | 위에서 내려오는 두 경로 중 큰 값 고르기 | `1932-정수-삼각형.cpp` |
| W16 | 수 | [백준 2579 · 계단 오르기](https://www.acmicpc.net/problem/2579) | '연속 세 칸 금지'를 상태에 담기 — i번째 계단에 '바로 전 칸에서 왔나 / 두 칸 전에서 왔나'로 나눠 `dp[i][1]`·`dp[i][2]` 두 칸으로 생각 | `2579-계단-오르기.cpp` |
| W16 | 목 | [백준 1463 · 1로 만들기](https://www.acmicpc.net/problem/1463) | 작은 수부터 채워 올라가는 bottom-up DP | `1463-1로-만들기.cpp` |
| W16 | 금 | [백준 1912 · 연속합](https://www.acmicpc.net/problem/1912) | 🔁 **재풀이** (W15 문제) — AI·검색 없이 20분, 예전 코드는 보지 않는다. 힌트를 보고 풀었던 문제가 있으면 그것부터 | `1912-연속합.cpp` |

## M5 · 우선순위 큐·최단경로 · DP · 구현

| 주차 | 요일 | 문제 | 오늘의 C++ / 포인트 | 파일 |
|---|---|---|---|---|
| W17 | 월 | [백준 1927 · 최소 힙](https://www.acmicpc.net/problem/1927) | `priority_queue`와 최소 힙 `greater<int>` | `1927-최소-힙.cpp` |
| W17 | 화 | [백준 11286 · 절댓값 힙](https://www.acmicpc.net/problem/11286) | 비교 기준을 직접 정하는 구조체(comparator) — `struct Cmp { bool operator()(int a, int b) const { … } };` → `priority_queue<int, vector<int>, Cmp> pq;` (`operator()`는 객체를 함수처럼 부르게 하는 연산자). `operator()`가 true를 돌려주면 그 원소 a가 **뒤로**(우선순위 낮게) 간다. 반대로 생각하기 쉬우니 (-1, 1, 2)로 true/false를 손으로 먼저 확인 | `11286-절댓값-힙.cpp` |
| W17 | 수 | [백준 11659 · 구간 합 구하기 4](https://www.acmicpc.net/problem/11659) | 누적 합 배열 `sum[i]`로 구간 합을 O(1)에 — 입력·출력이 많으니 `ios::sync_with_stdio(false); cin.tie(nullptr);`와 `endl` 대신 `'\n'` | `11659-구간-합-구하기-4.cpp` |
| W17 | 목 | [백준 2579 · 계단 오르기](https://www.acmicpc.net/problem/2579) | 🔁 **재풀이**(W16) — 예전 코드·AI 없이 25분, '연속 세 칸 금지'를 상태(dp 칸)에 어떻게 담았는지 주석 1줄로 — 다음 주 2156 포도주 시식이 이 풀이를 늘린다 | `2579-계단-오르기.cpp` |
| W18 | 월 | [백준 10844 · 쉬운 계단 수](https://www.acmicpc.net/problem/10844) | `dp[길이][마지막 숫자]` 상태 정의 — 처음 보는 2차원 DP라 길이 1·2일 때 표(행 = 길이, 열 = 0~9)를 손으로 채운 뒤 점화식을 쓴다. 30분 안에 못 풀면 답을 보지 말고 금요일(이 주에 코테 문제가 없는 날) 30분에서 이어서 — 다음 날 문제와 겹치지 않게 | `10844-쉬운-계단-수.cpp` |
| W18 | 화 | [백준 2156 · 포도주 시식](https://www.acmicpc.net/problem/2156) | 계단 오르기(2579)와 비교해 '이번 잔을 안 마시는 경우' 추가 — 먼저 지난주 목요일에 다시 푼 2579(W16) 풀이를 5분 읽고, 상태(dp 칸)가 무엇이 늘어나는지 1줄 적은 뒤 쓴다 | `2156-포도주-시식.cpp` |
| W18 | 수 | [백준 1932 · 정수 삼각형](https://www.acmicpc.net/problem/1932) | 🔁 **재풀이**(W16) — 예전 코드·AI 없이 25분, 위에서 내려오는 두 경로 중 큰 값을 고르는 점화식을 주석 1줄로 — W23 모의 시험의 정수 삼각형(Lv.3)과 같은 문제다 | `1932-정수-삼각형.cpp` |
| W18 | 목 | [백준 12865 · 평범한 배낭](https://www.acmicpc.net/problem/12865) | 0/1 배낭 — `dp[무게]`를 **뒤에서부터** 갱신: 앞에서부터 하면 같은 물건을 두 번 담는다(무게 1~5 표를 손으로 그려 확인) | `12865-평범한-배낭.cpp` |
| W19 | 월 | [백준 1753 · 최단경로](https://www.acmicpc.net/problem/1753) | 다익스트라 = 우선순위 큐 + 거리 배열 — `priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>>`(거리, 정점 — W17 1927의 최소 힙). 꺼낸 거리가 `dist[u]`보다 크면 `continue`(이미 더 짧은 길로 처리됨). 처음 보는 계열이라 코드 전에 정점 4개짜리 예로 dist 표를 손으로 갱신해 본다(10분). 30분 안에 못 풀면 답을 보지 말고 다음 날 코테 칸(재풀이 날)에서 이어서 | `1753-최단경로.cpp` |
| W19 | 화 | [백준 11286 · 절댓값 힙](https://www.acmicpc.net/problem/11286) | 🔁 **재풀이**(W17) — 예전 코드·AI 없이 25분, `operator()`가 true를 돌려주면 a가 뒤로 간다는 것을 주석 1줄로 — 같은 파일에 새로 써서 커밋 diff로 전과 비교 | `11286-절댓값-힙.cpp` |
| W19 | 수 | [백준 3190 · 뱀](https://www.acmicpc.net/problem/3190) | `deque`로 몸통 관리 (머리 추가 · 꼬리 제거) — 1초마다 순서: 머리를 한 칸 → 벽이나 내 몸이면 끝 → 사과면 꼬리 그대로, 아니면 `pop_back` → 그 초가 끝난 뒤 방향 전환(방향 배열을 시계 방향 순서로 두면 오른쪽 `(d + 1) % 4` · 왼쪽 `(d + 3) % 4`) | `3190-뱀.cpp` |
| W19 | 목 | [백준 13549 · 숨바꼭질 3](https://www.acmicpc.net/problem/13549) | 비용이 0과 1인 간선 — 0-1 BFS: `deque`에 비용 0(순간이동 ×2)이면 `push_front`, 1(한 칸 걷기)이면 `push_back`(어제 3190의 `deque`) — 월요일 다익스트라 코드로 바꿔 풀지 않는다(비용이 0·1뿐이면 우선순위 큐 없이 `deque` 하나로 된다는 것이 이 문제의 요점). W12 1697 숨바꼭질 BFS에서 순간이동만 비용 0으로 바뀐 문제 | `13549-숨바꼭질-3.cpp` |
| W20 | 월 | [백준 10844 · 쉬운 계단 수](https://www.acmicpc.net/problem/10844) | 🔁 **재풀이**(W18) — 예전 코드·AI 없이 25분, 길이 1·2 표(행 = 길이, 열 = 마지막 숫자 0~9)를 먼저 손으로 채우고 점화식을 주석 1줄로 | `10844-쉬운-계단-수.cpp` |
| W20 | 화 | [백준 11404 · 플로이드](https://www.acmicpc.net/problem/11404) | 3중 `for`로 모든 쌍 최단 거리 (거쳐 가는 점 k가 가장 바깥) — W19 다익스트라(한 점에서 출발)와 언제 무엇을 쓰는지 한 줄 비교 | `11404-플로이드.cpp` |
| W20 | 수 | [백준 3190 · 뱀](https://www.acmicpc.net/problem/3190) | 🔁 **재풀이**(W19) — 예전 코드·AI 없이 25분, 1초마다의 처리 순서(머리 → 충돌 → 사과 → 방향)를 주석 4줄로 먼저 쓰고 코드로 | `3190-뱀.cpp` |
| W20 | 목 | [백준 12865 · 평범한 배낭](https://www.acmicpc.net/problem/12865) | 🔁 **재풀이**(W18) — 예전 코드·AI 없이 25분, 왜 뒤에서부터 갱신하는지 주석 1줄로 | `12865-평범한-배낭.cpp` |

## M6 · 프로그래머스 모의 시험 (3문제 · 2시간 · AI 없이) + 월·수 재풀이

- **토요일** — 아래 3문제를 2시간 안에, AI와 검색 없이. 끝나면 몇 문제를 몇 분에 풀었는지, 못 푼 문제는 어디서 막혔는지 TIL에 적는다.
- **월·수** — 🔁 재풀이 20분. 지난주 모의 시험에서 못 푼 문제 → 없으면 M4·M5 재풀이 문제(커리큘럼 카드에 그날 문제가 나온다).

| 주차 | 요일 | 문제 3개 | 파일 |
|---|---|---|---|
| W21 | 토 | [Lv.1 완주하지 못한 선수](https://school.programmers.co.kr/learn/courses/30/lessons/42576)<br>[Lv.2 기능개발](https://school.programmers.co.kr/learn/courses/30/lessons/42586)<br>[Lv.2 타겟 넘버](https://school.programmers.co.kr/learn/courses/30/lessons/43165) | `lv1-완주하지-못한-선수.cpp`<br>`lv2-기능개발.cpp`<br>`lv2-타겟-넘버.cpp` |
| W22 | 토 | [Lv.1 K번째수](https://school.programmers.co.kr/learn/courses/30/lessons/42748)<br>[Lv.2 프로세스](https://school.programmers.co.kr/learn/courses/30/lessons/42587)<br>[Lv.2 게임 맵 최단거리](https://school.programmers.co.kr/learn/courses/30/lessons/1844) | `lv1-K번째수.cpp`<br>`lv2-프로세스.cpp`<br>`lv2-게임-맵-최단거리.cpp` |
| W23 | 토 | [Lv.1 모의고사](https://school.programmers.co.kr/learn/courses/30/lessons/42840)<br>[Lv.2 의상](https://school.programmers.co.kr/learn/courses/30/lessons/42578)<br>[Lv.3 정수 삼각형](https://school.programmers.co.kr/learn/courses/30/lessons/43105) | `lv1-모의고사.cpp`<br>`lv2-의상.cpp`<br>`lv3-정수-삼각형.cpp` |
| W24 | 토 | [Lv.1 체육복](https://school.programmers.co.kr/learn/courses/30/lessons/42862)<br>[Lv.3 입국심사](https://school.programmers.co.kr/learn/courses/30/lessons/43238)<br>[Lv.3 네트워크](https://school.programmers.co.kr/learn/courses/30/lessons/43162) | `lv1-체육복.cpp`<br>`lv3-입국심사.cpp`<br>`lv3-네트워크.cpp` |
