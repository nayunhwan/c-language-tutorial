# 2주차 문제 해설 :: 자료형, 연산자, 조건문, while문

본 문서에서는 2주차 문제에 대해 다룹니다.

이번 문서에서 다룰 문제리스트는 다음과 같습니다.

* **A / B** <https://www.acmicpc.net/problem/1008>
* **윤년** <https://www.acmicpc.net/problem/2753>
* **평균 점수** <https://www.acmicpc.net/problem/10039>
* **크냐?** <https://www.acmicpc.net/problem/4101>
* **홀수** <https://www.acmicpc.net/problem/2576>


### A / B
**A / B** <https://www.acmicpc.net/problem/1008>

저번주에 풀었던 [A + B](https://www.acmicpc.net/problem/1000), [A - B](https://www.acmicpc.net/problem/1001)와 비슷한 맥락의 문제입니다. 하지만 덧셈과 뺄셈과는 다르게 나눗셈의 경우에는 정수에서 실수로 값이 바뀔 수도 있습니다. 그렇기 때문에 자료형을 실수형으로 바꿔줘야 하는데, 자료형을 바꾸는 것을 `캐스팅`한다고 표현합니다.

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

`printf` 부분을 보면, 포맷터가 `"%.9f"`로 되어있는 것을 확인할 수 있는데 이는, 오차를 줄이기위해서 소수 9번째 자리까지 출력하기 위함이고, 값이 들어가는 자리에는 (double)a/b로 되어있는데, 이는 `double` 자료형으로 캐스팅을 한다는 뜻입니다.
`캐스팅`의 경우에는 앞으로 문제를 푸는데에 있어서 자주 쓰이곤 하니, 꼭 방법을 알아두는 것이 좋습니다.

### 윤년
**윤년** <https://www.acmicpc.net/problem/2753>

드디어 처음으로 알고리즘 다운 문제를 풀 수 있는 문제입니다. 문제는 윤년을 구하는 문제인데, 조건을 잘 보면 윤년은 `4의 배수이면서, 100의 배수가 아닐때 또는 400의 배수일 때` 라고 정의되어 있습니다. 이 부분을 그대로 논리에 맞게 C언어 코드로 짜주면 됩니다.
차근차근 따라가보도록 하겠습니다.

(1) **4의 배수 이면서**

일단 윤년일 때의 첫 번째 조건입니다. 4의 배수라는 것은 어떤 수 n이 4로 나누었을 때의 나머지가 0이라는 것입니다. 이를 C언어로 작성을하면 `n % 4 == 0`이 됩니다. 그리고 이 조건은 뒤에 어떤 조건이 나와도 무조건 만족해야하는 식입니다. 따라서 `AND`연산을 해야합니다. `AND` 연산은 `A AND B` 라는 식이 있을 때, A도 `True`이고 B도 `True`일 때, 즉 양 변의 모든 식이 `True`일 때만 `True`가 나오는 연산입니다. C언어에서의 `AND` 연산은 `&&` 으로 나타냅니다.

따라서 위의 식을 나타내면, `(n % 4 == 0) && (100의 배수가 아닐 때 또는 400의 배수일 때)`으로 나타낼 수 있습니다.

(2) **100의 배수가 아닐 때 또는 400의 배수일 때**

여기도 첫 번째 연산과 동일하게 n이 m의 배수인지 아닌지를 판별하는 부분입니다. `100의 배수가 아닐 때`라는 것은 임의의 수 n을 100으로 나눴을 때의 나머지가 0이 아니라는 뜻이므로, C언어로 나타내면 `n % 100 != 0` 이 됩니다. 이어서 400의 배수일 때를 C언어로 나타내면 `n % 400 == 0`이 되고 이 조건은 `또는` 이므로 `OR` 연산을 나타냅니다. `OR` 연산은 `A OR B`가 있을 때 A가 `True` 이거나 B가 `True`이면 `True`이다 라는 뜻입니다. 즉, 양 변에 한 개의 값이라도 `True`면, 전체 식이 `True`가 됩니다. C언어에서 `OR`연산은 `||`으로 나타냅니다.

(3) **전체 식 완성하기**

앞 두 단계에서 걸쳐 만든 식을 이제 하나로 이어보도록 하겠습니다. `(n % 4 == 0) && (n % 100 != 0 || n % 400 == 0)`의 조건이 만들어지게 됩니다.

위의 논리를 이용해서 전체 코드를 완성해보면 다음과 같습니다.

```c
#include <stdio.h>

int main(){
	int n;
	scanf("%d", &n);
	if(n % 4 == 0 && (n % 100 != 0 || n % 400 == 0)) printf("1\n");
	else printf("0\n");
	return 0;
}
```

### 평균 점수
**평균 점수** <https://www.acmicpc.net/problem/10039>

이 문제는 제목만 보면 단순히 평균 값을 구하는 문제처럼 보일 수 있지만, 조건이 하나 있습니다. `40점 미만의 학생들은 항상 40점을 받게 된다` 이 조건이 있기 때문에 우리는 단순히 평균 값을 구하는 것에서 조금 더 나아가 생각할 필요가 있습니다.

문제를 접근하는 방법은 이와 같습니다.

1. scanf를 통해서 정수 n을 입력받는다.
2. 입력받은 정수 n이 40점 미만인지 확인하여, 40점 미만일 경우에는 n을 40으로 재정의한다.
3. 평균 값을 구한다. (n은 5의 배수이기 때문에 평균 값은 무조건 정수이다.)

```c
#include <stdio.h>

int main(){
	int sum = 0;
	for(int i = 0; i < 5; i++){
		int n;
		scanf("%d", &n);
		if(n < 40) sum += 40;
		else sum += n;
	}
	printf("%d\n", sum / 5);
	return 0;
}
```

### 크냐?
**크냐?** <https://www.acmicpc.net/problem/4101>

이 문제는 간단히 정수 a, b를 받아서 첫 번째 수가 두 번째 수보다 크면 `Yes`, 아니면 `No`를 출력하는 간단한 문제입니다. 하지만 여기서 지금까지 우리가 풀었던 문제와 다른 점이 하나있는데요, 바로 몇 번을 입력받을지가 정해져 있지 않다는 점입니다. 0 0이 나오기 전까지 계속 반복되야 하기 때문에 이 문제를 풀 때는 `for`을 이용해서 반복하는 것 보다 `while`을 이용하여 a와 b가 둘 다 0이 입력될 때 까지 계속 반복문이 실행되도록 합니다.

```c
#include <stdio.h>

int main(){
	while(true){
		int a, b;
		scanf("%d %d", &a, &b);
		if(a + b == 0) break;
		if(a > b) printf("Yes\n");
		else printf("No\n");
	}
	return 0;
}
```

### 홀수
**홀수** <https://www.acmicpc.net/problem/2576

이번 주 문제 중 가장 챌린지한 문제입니다. 7개의 자연수가 입력되는데, 입력된 수 중 홀수만을 골라 그 합을 구하고, 홀수 중 최소값을 찾는 문제입니다. 홀수를 판별하는 가장 쉬운 방법은 2로 나눠서 나머지가 있으면 `홀수`, 없으면 `짝수`로 판별합니다. 홀/짝 판별은 앞으로도 자주 쓰이는 기법이므로 꼭 알아둬야합니다.

최소값을 구하는 방법은 초기값을 최소값으로 나올 수 있는 최대의 수로 설정하는 것 입니다. 입력되는 수 n은 100보다 작은 자연수이므로 나올 수 있는 가장 큰 최소값은 99입니다. 따라서 int min의 초기값은 99로 설정합니다.

```c
#include <stdio.h>

int main(){
    int sum = 0;
    int min = 99;
    for(int i = 0; i < 7; i++){
        int n;
        scanf("%d", &n);
        if(n % 2 == 0) continue;
        sum += n;
        if(n < min) min = n;
    }
    if(sum == 0) printf("-1\n");
    else printf("%d\n%d\n", sum, min);
    return 0;
}
```
