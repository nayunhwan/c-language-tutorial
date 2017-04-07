# 1주차 문제 해설 (C언어 입문)
본 문서에서는 1주차 문제에 대해 다룹니다.

이번 문서에서 다룰 문제리스트는 다음과 같습니다.

* Hello World <https://www.acmicpc.net/problem/2557>
* A + B <https://www.acmicpc.net/problem/1000>
* A - B <https://www.acmicpc.net/problem/1001>
* 오늘 날짜 <https://www.acmicpc.net/problem/10699>
* 고양이 <https://www.acmicpc.net/problem/10171>

### Hello World
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

### A + B
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


### A - B
A - B <https://www.acmicpc.net/problem/1001>

이번에는 두 정수 A와 B를 받아서 결과값으로 A-B 값을 출력하는 문제입니다. A + B 문제와 동일하지만 +가 -로만 바뀌었습니다.

```c
#include <stdio.h>

int main(){
  int a, b;
  scanf("%d %d", &a, &b);
  printf("%d\n", a-b);
  return 0;
}
```

### 오늘 날짜
오늘 날짜 <https://www.acmicpc.net/problem/10699>

이번에는 현재 날짜를 기준으로 오늘 날짜를 YYYY-MM-DD 형식으로 출력하는 문제입니다. ex)2017-04-07 이 문제도 printf 함수의 사용법만 알고있다면 쉽게 풀 수 있는 문제입니다.

```c
#include <stdio.h>

int main(){
  printf("2017-04-07\n");
  return 0;
}
```

이 문제에서 유의할 점은 이 문제를 푸는 시각의 현재 날짜를 입력해야 한다는 점입니다. 이 문서를 작성일이 2017년 4월 7일이기 때문에 출력값을 2017-04-07로 지정한 것 뿐이며, 만약에 이 문제를 푸는 날짜가 2018년 12월 31일일 경우에는 2018-04-07이 출력되도록 문제를 풀어야 합니다.
