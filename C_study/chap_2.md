# chap_2 기초 사항

- 프로그램을 이루는 구성 요소
- 주석의 개념
- 화면으로 출력
- 사용자로부터 입력

## 1. 프로그램을 이루는 구성 요소

### #include <stdio.h>
`#`으로 시작하는 문장은 전처리기 지시자이다. 전처리기(preprocessor)는 컴파일 전에 사전 작업을 하는 명령이다. `#include`는 소스 코드 안에 특정 파일을 포함시키라고 지시하는 명령어이다. `stdio.h`와 같은 파일들은 헤더 파일(header file)이라고 불리며 컴파일러가 필요로 하는 정보를 가지고 있다. 전처리기 지시자 끝에는 세미콜론(;)을 붙이면 안된다.

`stdio.h`라는 파일은 입출력 함수에 대한 정보를 가지고 있는 헤더 파일이다. 헤더 파일들은 일반적으로 `.h` 확장자를 가지고 있다. 대부분의 프로그램에서 한 개 이상의 헤더 파일을 사용한다.

- **헤더 파일**
    - 헤더 파일은 주로 외부 소스 파일에 정의된 변수나 함수를 쓰기 위해 만들어졌다. 컴파일러가 기본적으로 지원하는 표준 헤더와 사용자가 임의로 만든 사용자 헤더로 나눠진다.

- **헤더 파일 사용 방법**
    - 보통 소스 파일 맨 윗줄에 표기함으로써 해당 헤더파일에 들어있는 요소를 사용할 수 있다.
    ```C
    #include <전역 헤더 이름>
    #include "상대 경로 헤더 이름"
    ```

    - 꺽쇠 괄호(`<>`)는 컴파일러에서 환경에 따라 지정된 spec 경로에서 헤더를 찾거나 명시적으로 지정한 경로에서 파일을 찾지만, 큰 따옴표(`""`)는 해당 소스 파일이 위치한 경로에서 파일을 찾기에 컴파일러 옵션 없이도 상대 경로를 사용하는 것이 가능하다. 예를 들어 `#include "../common/common.h"`와 같이 사용된다.

- **표준 라이브러리 목록**
    - **stdio.h** : Standard Input Output(표준 입출력)  
      `printf`나 `scanf`처럼 콘솔 입/출력을 할 때, 외부 파일을 읽을 때 사용한다.
    - **time.h** : 시간 관련 함수와 구조체를 담고 있는 헤더이다.
    - **math.h** : 지수함수, 로그함수, 삼각함수, 거듭제곱 등 수학 관련 함수가 들어있다.
    - **stdlib.h** : 문자열 변환, 의사 난수 생성, 동적 메모리 관리 등의 함수들을 포함하고 있다.  
      주로 프로그램 제어 관련 함수가 들어가 있다. 동적 메모리 할당 함수인 `malloc`, `calloc` 함수도 이 헤더에 포함되어 있으며 시스템 명령어나 프로세스 제어 함수도 포함되어 있다.  
      **참고**: [위키피디아 stdlib.h 문서](https://en.wikipedia.org/wiki/C_standard_library)
    - **string.h** : 문자형 배열(`char* str` 또는 `char str[]`) 관련 헤더이다.  
      대표적인 함수로 `strcat`(문자열 합치기), `strcmp`(문자열 비교), `strlen`(문자열 길이), `strcpy`(문자열 복사) 등이 있다.  
      **참고**: [위키피디아 C 문자열 처리 문서](https://en.wikipedia.org/wiki/C_string_handling)
