# 1주차 문제 해설 (C언어 입문)
본 문서에서는 1주차 문제에 대해 다룹니다.

이번 문서에서 다룰 문제리스트는 다음과 같습니다.

* Hello World <https://www.acmicpc.net/problem/2557>
* A + B <https://www.acmicpc.net/problem/1000>
* A - B <https://www.acmicpc.net/problem/1001>
* 오늘 날짜 <https://www.acmicpc.net/problem/10699>
* 고양이 <https://www.acmicpc.net/problem/10171>

## Hello World
Hello World <https://www.acmicpc.net/problem/2557>

가장 기본적인 `Hello World!`를 출력함수를 통해서 출력하는 문제입니다.

코드는 간단합니다.

```c
#include <stdio.h>

int main(){
  printf("Hello World!\n");
  return 0;
}
```

C언어의 기본적인 문법, Main 함수의 이해, Stdio.h 헤더파일 Import, 출력함수 printf에 대해 알고 있었다면 무리없이 쉽게 풀 수 있는 문제였습니다.

## A + B
A + B <https://www.acmicpc.net/problem/1000>

이번에는 두 정수 A와 B를 받아서 결과값으로 A+B 값을 출력하는 문제입니다. 이번 문제도 C언어의 기본적인 문법을 알고 있다면, 무리없이 쉽게 풀 수 있는 문제입니다.

```c
#include <stdio.h>

int main(){
  int a, b;
  scanf("%d %d", &a, &b);
  printf("%d\n", a+b);
  return 0;
}
```

Hello World 문제와 다른 점이 있다면, 이번 문제에서는 scanf 함수, 즉 입력함수가 추가되었다는 점입니다. scanf에서는 변수의 `주소값`을 넣어줘야한다는 점을 꼭 기억하시길 바랍니다.
