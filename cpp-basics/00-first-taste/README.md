# 00-first-taste

처음으로 작성해 본 C++ 코드입니다. 이름을 입력받아 인사하는 콘솔 프로그램.

## Windows에서 실행하기 (Visual Studio)

1. Visual Studio → `새 프로젝트 만들기` → **`콘솔 앱`**(C++) → 이름 `FirstTaste` → 위치는 이 폴더
2. 자동으로 생긴 `.cpp` 내용을 지우고 [main.cpp](main.cpp) 내용을 붙여넣기
3. **`Ctrl+F5`** (디버깅하지 않고 시작) → 검은 창에 `이름을 입력하세요:`가 나오면 성공

### 한글이 깨져 보이면
- 메뉴 `프로젝트` → `속성` → `C/C++` → `명령줄` → 추가 옵션에 **`/utf-8`** 입력 → 다시 `Ctrl+F5`
- 그래도 깨지면 `main()` 첫 줄에 `system("chcp 65001 > nul");` 추가 (`#include <cstdlib>` 필요)

> 빌드 결과물(`x64/`, `.vs/`, `*.exe`)은 `.gitignore`에 들어 있어 Git에 올라가지 않습니다.
