# 2주차 문제 해설 :: 자료형, 연산자, 조건문, while문

본 문서에서는 2주차 문제에 대해 다룹니다.

이번 문서에서 다룰 문제리스트는 다음과 같습니다.

* A / B <https://www.acmicpc.net/problem/1008>
* 윤년 <https://www.acmicpc.net/problem/2753>
* 평균 점수 <https://www.acmicpc.net/problem/10039>
* 크냐? <https://www.acmicpc.net/problem/4101>
* 홀수 <https://www.acmicpc.net/problem/2576>


### A / B
A / B <https://www.acmicpc.net/problem/1008>

저번주에 풀었던 (A + B)[https://www.acmicpc.net/problem/1000], (A - B)[https://www.acmicpc.net/problem/1001]와 비슷한 맥락의 문제입니다. 하지만 덧셈과 뺄셈과는 다르게 나눗셈의 경우에는 정수에서 실수로 값이 바뀔 수도 있습니다. 그렇기 때문에 자료형을 실수형으로 바꿔줘야 하는데, 자료형을 바꾸는 것을 `캐스팅`한다고 표현합니다.

실수형 자료형으로는 `float`와 `double`형이 있습니다.

일반적으로는 `float` 자료형을 많이 쓰지만, 이 문제와 같이 좀 더 정밀한 실수를 사용해야 하는 경우에는 `double` 자료형을 사용합니다.

문제의 조건을 보면 `절대/상대 오차는 10^-9 까지 허용한다` 라고 표기되어 있기 때문에, 소수 9번째 자리까지 표시하도록 합니다.

```c
#include <stdio.h>

int main(){
	int a, b;
	scanf("%d %d", &a, &b);
	printf("%.9f\n", (double)a/b); // %.9와 double로 캐스팅
	return 0;
}
```

`printf` 부분을 보면, 포맷터가 `"%.9f"`로 되어있는 것을 확인할 수 있는데 이는, 오차를 줄이기위해서 소수 9번째 자리까지 출력하기 위함이고, 값이 들어가는 자리에는 (double)a/b로 되어있는데, 이는 `double` 자료형으로 캐스팅을 한다는 뜻이다.
`캐스팅`의 경우에는 앞으로 문제를 푸는데에 있어서 자주 쓰이곤 하니, 꼭 방법을 알아두는 것이 좋다.
