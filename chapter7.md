# 3주차 문제 해설 :: for문, 1차원 배열, 정렬

본 문서에서는 3주차 문제에 대해 다룹니다.

이번 문서에서 다룰 문제의 리스트는 다음과 같습니다.

* **별찍기-1** <https://www.acmicpc.net/problem/2438>
* **별찍기-2** <https://www.acmicpc.net/problem/2439>
* **나는 요리사다** <https://www.acmicpc.net/problem/2953>
* **수 정렬하기** <https://www.acmicpc.net/problem/2750>
* **오르막길** <https://www.acmicpc.net/problem/28467>

### 별찍기-1
**별찍기-1** <https://www.acmicpc.net/problem/2438>

별찍기 문제 시리즈는 반복문을 연습하는데 가장 유명하고 좋은 예제입니다. 꼭 자신의 손으로 풀어보는 것을 권장합니다.

문제의 룰은 간단합니다. n번째의 줄에는 n개의 별을 출력하는 문제입니다. 이 문제를 풀기 위해서는 `이중 for문`을 사용해야합니다.
첫 번째의 `for`문은 줄의 개수, 두 번째 `for`문은 별의 개수를 담당하는 반복문입니다.

첫 번째 for는 0부터 n까지를 돌아야하고, 두 번째 for는 i번째 줄에서 i개만큼의 별을 출력해야하므로, 이를 로직으로 표현하면 다음과 같습니다.

```c
for(int i = 0; i < n; i++){
  for(int j = 0; j <= i; j++){
    putchar('*');
  }
  putchar('\n');
}
```

```c
#include <stdio.h>

int main(){
	int n;
	scanf("%d", &n);
	for(int i = 0; i < n; i++){
		for(int j = 0; j <= i; j++){
			putchar('*');
		}
		putchar('\n');
	}
	return 0;
}
```
