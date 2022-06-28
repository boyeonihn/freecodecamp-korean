# Python Modulus 나머지 연산자 - % 기호는 Python에서 무엇을 의미합니까? (해결)
#### 인보연 (Bo Yeon Ihn) 번역

![숲 배경에 있는 모듈러 연산자](https://www.freecodecamp.org/news/content/images/size/w2000/2020/01/python-modulo-image.jpg)

영어 원문: [The Python Modulo Operator - What Does the % Symbol Mean in Python? (Solved)](https://www.freecodecamp.org/news/the-python-modulo-operator-what-does-the-symbol-mean-in-python-solved/)   
원문 글쓴이: [Beau Carnes](https://www.freecodecamp.org/news/author/beau/)


### % 기호를 보면 퍼센트를 생각할 수 있습니다. 그러나 Python을 비롯한 대부분의 프로그래밍 언어에서는 다른 의미를 가집니다.


Python에서 `%` 기호는 나머지 연산자(modulo operator)라고 합니다. 이 연산자는 왼쪽 피연산자를 오른쪽 피연산자로 나눈 후 그 나머지를 반환합니다. 나눗셈 문제의 나머지를 계산할 때 사용합니다. 

나머지 연산자는 `+`, `-`, `/`, `*`, `**`, `//`와 같은 산술 연산자입니다.    

다음은 나머지 연산자의 기본 구문입니다:    

```
a % b 
```

위의 예시에서 `a`는 `b`로 나누고 나머지를 반환합니다. 숫자가 들어간 예를 보겠습니다.

```
7 % 2
```

예시의 결과는 <strong>1</strong>입니다. 2이 7에 3번 들어간 후 나머지로 <strong>1</strong>이 남습니다. 


아래 다이어그램은  `7 / 2` 와 `7 % 2` 산술식을 시각적으로 표현합니다 ("R" 는 "나머지"라는 뜻인 "remainder"를  의미합니다). 녹색 화살표가 가리키는 오른쪽에 있는 Python 로고는 나눗셈 문제의 나머지입니다. `7 % 2`의 답이기도 합니다. 

![7과2를 나누거나 모듈로 연산자를 사용했을 때의 결과를 표시해주는 그림](https://www.freecodecamp.org/news/content/images/2019/09/image-196.png)

다음은 다른 예입니다:

```
3 % 4
```

결과는 <strong>3</strong>입니다. 4는 3이란 숫자에 아예 들어가지 않아서 <strong>3</strong>이 그대로 남습니다. 아래 다이어그램이 이 산술식을 표현합니다. 나머지 연산자는 나눗셈 후 남은 값을 반환합니다. 나머지는 3입니다. 

![3과 4을 나누거나 모듈로 연산자를 사용했을 때의 결과를 표시해주는 그림](https://www.freecodecamp.org/news/content/images/2019/09/image-197.png)


## 나머지 연산자를 사용한 예시

나머지 연산자의 일반적인 용도 중 하나는 짝수 또는 홀수를 찾는 것입니다. 아래 코드는 모듈로 연산자를 사용하여 0에서 10 사이의 모든 홀수를 출력합니다.


```
for number in range(1, 10):
    if(number % 2 != 0):
        print(number)
```

결과: 

```
1
3
5
7
9
```

