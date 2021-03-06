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

문제의 룰은 간단합니다. `n`번째의 줄에는 `n`개의 별을 출력하는 문제입니다. 이 문제를 풀기 위해서는 `이중 for문`을 사용해야합니다.
첫 번째의 `for`문은 줄의 개수, 두 번째 `for`문은 별의 개수를 담당하는 반복문입니다.

첫 번째 `for`는 `0`부터 `n`번까지 실행되야하고, 두 번째 `for`는 `i`번째 줄에서 `i`개만큼의 `*`을 출력해야하므로, 이를 로직으로 표현하면 다음과 같습니다.

```c
for(int i = 0; i < n; i++){
  for(int j = 0; j <= i; j++){
    putchar('*');
  }
  putchar('\n');
}
```

여기서 변수 `i`는 줄의 개수, `j`는 별의 개수를 뜻합니다. `i`번째 줄에서, `j`는 `i`개 만큼의 별을 출력해야하기 때문에 0부터 i번 *을 출력하도록 합니다. 그리고 별을 다 찍은 이후에는 개행문자 `\n`을 사용하여 줄바꿈을 해줍니다.

> 글자 수가 한 글자인 '문자'를 출력하고 싶을 때는 printf보다 오버헤드가 작은 putchar 함수를 사용하는 것을 권장합니다.

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


### 별찍기-2
**별찍기-2** <https://www.acmicpc.net/problem/2439>

이 문제도 [별찍기-1](https://www.acmicpc.net/problem/2438) 문제와 동일하게 반복문을 연습하는데 가장 좋은 예제입니다. 꼭 자신의 손으로 풀어보는 것을 권장합니다.

위에서 풀었던 별찍기-1 문제와 비슷하지만 살짝 더 어렵습니다. 이 문제를 풀기 위해서도 `이중 for문`을 사용해야합니다.
별찍기-1와 다른 점은 먼저 `i`번째 줄에서 `n-i`개의 공백을 찍은 다음 `i`개의 `*`을 찍는 것이 규칙입니다.

우리는 여기서 또 중요하게 짚고가야 할 것이 있습니다. 보통 for문의 경우에는 `i`값을 0부터 시작하도록 코딩을 하는 습관을 들이는 것이 중요합니다. 그렇기 때문에 n번의 연산을 하기위해서는 `0~n-1`까지 반복문이 실행되야합니다. 다시 한번 위의 예제와 대입해서 생각해보면, `i`번째 줄에서 `n-i`개의 공백을 출력한다는 뜻은 `0`부터 `n-1-i`번째의 반복에서는 공백을 그 이후에서는 `*`을 찍으면 됩니다.

이것을 코드로 나타내면 아래와 같습니다.

```c
for(int i = 0; i < n; i++){
		for(int j = 0; j < n; j++){
			if(j >= n-1-i) putchar('*');
			else putchar(' ');
		}
		putchar('\n');
	}
```

`i`와 `j`의 실질적인 범위가 `0 ~ n-1`이기 때문에 `j`가 `n-1-i`번째 부터 `*`을 출력하도록 하는 것입니다. 처음 반복문을 접했을 경우 0부터 카운팅하는 것이 익숙하지 않기 때문에 위의 코드가 이해가 갈 때까지 계속해서 스스로 연습해보는 시간이 절대적으로 필요합니다.

```c
#include <stdio.h>

int main(){
	int n;
	scanf("%d", &n);
	for(int i = 0; i < n; i++){
		for(int j = 0; j < n; j++){
			if(j >= n-1-i) putchar('*');
			else putchar(' ');
		}
		putchar('\n');
	}
	return 0;
}
```

### 나는 요리사다
**나는 요리사다** <https://www.acmicpc.net/problem/2953>

`max`, `max_index`의 스킬을 활용하여 풀 수 있는 문제입니다. 우리는 `5번`의 케이스와, 각 케이스는 `4개`의 점수로 이뤄져 있기 때문에 총 `20번`의 입력이 일어나야 합니다. 따라서 `이중 for문`을 이용하여 입력을 쉽게 받도록 합니다.
각 케이스별로 4개의 값을 받은 합계를 나타내는 정수형 변수인 `sum`을 `0`을 초기 값으로 선언, 변수 `n`을 입력받을 때마다 `sum`에 더하고, 4개의 값을 모두 더한 총합이 `max`보다 클 경우에는 해당 `i`번 째의 줄이 최대 값이 되어야 하므로, 이때의 합계를 `max`값으로 재정의, 이때의 `i`값을 `max_index`로 저장하는데 컴퓨터는 `0`으로 시작하는 반면, 우리가 일반적으로 수를 셀 때는 `1`부터 시작하기 때문에 `i+1`로 `max_index`값을 설정해줍니다.

`이중 for문`에 대한 이해가 있다면 큰 어려움 없이 풀 수 있는 문제였습니다.

```c
#include <stdio.h>

int main(){
	int max = 0, max_index = 0;
	for(int i = 0; i < 5; i++){
		int sum = 0;
		for(int j = 0; j < 4; j++){
			int n;
			scanf("%d", &n);
			sum += n;
		}
		if(sum > max){
			max = sum;
			max_index = i+1;
		}
	}
	printf("%d %d\n", max_index, max);
	return 0;
}
```

## 수 정렬하기
**수 정렬하기** <https://www.acmicpc.net/problem/2750>

**알고리즘을 시각적으로 보여주는 사이트** <https://visualgo.net/>

**거품 정렬 Wiki** <https://ko.wikipedia.org/wiki/%EA%B1%B0%ED%92%88_%EC%A0%95%EB%A0%AC>

수 정렬 알고리즘은 앞으로 컴퓨터공학 및 알고리즘 문제를 푸는데 있어서 매우 중요합니다.

우리는 이번 문제에서는 시간복잡도가 `O(n^2)`으로, 상당히 느린 알고리즘이지만, 구현하기가 간단한 편에 속하는 `거품정렬` 알고리즘을 사용하여 이번 문제를 해결하도록 하겠습니다.

거품정렬 알고리즘은 다음과 같습니다.

```c
for(int i = 0; i < n; i++){
  for(int j = 0; j < n-1-i; j++){
    if(arr[j] > arr[j+1]){
      SWAP(arr[j], arr[j+1]);
    }
  }
}
```

이 코드가 `거품정렬`의 가장 기본적인 형태입니다. `SWAP`은 따로 정의한 매크로로 `arr[j]`와 `arr[j+1]`의 값을 바꾼다는 `매크로`입니다.

```c
#include <stdio.h>
#define SWAP(a,b) {int t = a; a = b; b = t;}

int main(){
	int n;
	int input[1001];

	scanf("%d", &n);

	for(int i = 0; i < n; i++){
		scanf("%d", &input[i]);
	}

	for(int i = 0; i < n; i++){
		for(int j = 0; j < n-i-1; j++){
			if(input[j] > input[j+1]) SWAP(input[j], input[j+1]);
		}
	}

	for(int i = 0; i < n; i++) printf("%d\n", input[i]);
	return 0;
}
```

C언어에서 매크로는 `main`함수 이전에 `#define`이라는 명령어를 통해서 선언해 줄 수 있으며, `SWAP`의 내용은 파라미터를 `a`, `b`를 받은다음, 임의 `int`형 변수 `t`를 선언하고 `t`에 `a`값을 대입, `a`에 `b`값을 대입, `b`에 `t`값을 대입하여 결과적으로는 `a`와 `b`의 위치를 바꾸는 역할을 하는 매크로입니다. 함수를 통해서 구현을 해도 되지만, 좀 더 미려한 코드를 짜기 위해서 `매크로`의 사용법도 익혀주면 매우 좋습니다.
