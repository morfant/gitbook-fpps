# Week 01

## 목표

C 언어란 무엇인지 알아봅시다

첫 코드를 작성해 봅시다.

한 학기 수업의 전체적인 그림을 알려드림.



### 개발환경 준비

#### CLI?

Command Line Interface



#### 컴파일?(Compile)

인간의 언어인 소스코드를 컴퓨터가 이해할 수 있는 기계어로 바꾸는 과정



#### 파이썬과 다른 점

별도의 컴파일 과정이 필요하지 않다.

인터프리터가 파이썬 코드를 한 줄씩 읽고, 이를 바이트코드로 변환하여 실행한다.



#### 코드 에디터

VSCode 설치



#### 컴파일러 설치

OSX : clang/clang++ (기본 내장)

Windows  : gcc/g++ (설치 필요)



#### Hello, World!

{% code title="hello_world.c" lineNumbers="true" %}
```c
// Hello, World!
#include <stdio.h>

int main()
{
    printf("Hello, World!/n");
    return 0;
}
```
{% endcode %}

코드 분석!



#### 컴파일!

```bash
clang hello_world.c -o hello # osx
gcc hello_world.c -o hello # osx, Windows, linux
```





## 과제

수업을 듣는 이유 간단히 적어 제출하기
