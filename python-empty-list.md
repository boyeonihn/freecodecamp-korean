# Python에서 빈 리스트 만드는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![파이썬 로고와 영문으로 빈 리스트라고 적혀 있는 배너](https://www.freecodecamp.org/news/content/images/size/w2000/2020/06/Empty-list.png)

영어 원문: [Python Empty List Tutorial – How to Create an Empty List in Python](https://www.freecodecamp.org/news/python-empty-list-tutorial-how-to-create-an-empty-list-in-python/)   
글쓴이: [Estefania Cassingena Navone](https://www.freecodecamp.org/news/author/estefaniacn/)


### Python에서 빈 리스트 생성하는 방법을 알고 싶으시면 이 기사를 계속 읽어보시길 바랍니다. 

이 기사에서는 다음 내용을 배울 수 있습니다: 
- 대괄호 `[]`를 사용해 빈 리스트 만드는 방법
- `list()` 함수를 사용해 빈 리스트 만드는 방법
- 두 방법의 사용 사례 
- `timeit` 모듈을 통해 어떤 방법이 더 효율적이고 실행 속도가 빠른지 비교하는 방법

<strong>그럼 시작하겠습니다.</strong> ✨    

## 🔹 대괄호 `[]`를 사용하는 방법 

다음과 같이 빈 대괄호 `[]` 쌍을 사용해 빈 리스트를 만들 수 있습니다.


![변수가 빈 리스트를 표현하는 대괄호 한 쌍을 가르키고 있는 코드](https://www.freecodecamp.org/news/content/images/2020/06/image-131.png)

💡 <strong>팁</strong>: 이후 프로그램에 사용할 수 있게 빈 리스트를 변수에 저장합니다.    

예를 들어: 

```
num = [] 
```

빈 리스트의 길이는 다음과 같이 0입니다:    

```
>>> num = []
>>> len(num)
0
```

빈 리스트는 거짓같은 값(falsy)입니다. 즉, 불리언(Boolean) 문맥에서 `False`로 평가됩니다. 


```
>>> num = []
>>> bool(num)
False

```

### 빈 리스트에 요소 추가하는 방법 

`append()`와 `insert()` 메서드를 사용해 빈 리스트에 요소를 추가할 수 있습니다: 

- `append()`는 리스트 맨 끝에 요소를 추가합니다.
- `insert()`는 선택한 리스트의 특정 인덱스에 요소를 추가합니다.    

리스트는 비어 있는지 여부에 따라 참 같은 또는 거짓같은 값으로 평가될 수 있어서 다음과 같이 조건문에 사용할 수 있습니다.


```
if num:
	print("이 리스트는 비어 있지 않습니다")
else:
	print("이 리스트는 비어 있습니다")
```

이 코드 블록이 출력하는 값은 다음과 같습니다:

```
이 리스트는 비어 있습니다
```

리스트가 비어 있기 때문에 `False`로 평가됩니다.    


일반적으로: 
- 리스트가 비어 있지 않다면 `True`로 평가되어서 `if`문이 실행됩니다. 
- 리스트가 비어 있다면 `False`로 평가되어서 `else`문이 실행됩니다.


### 예시: 

다음 예시에서는 빈 리스트를 생성하고 변수 `num`에 할당합니다. 그런 다음 `for`문을 사용해 일련의 정수인 요소들을 비어 있는 리스트에 추가합니다: 

```
>>> num = []
>>> for i in range(3, 15, 2):
	num.append(i)

```


요소들이 성공적으로 추가되었고 리스트가 더 이상 비어 있지 않다는 것을 확인하기 위해 변수의 값을 체크합니다: 


```
>>> num
[3, 5, 7, 9, 11, 13]
```

💡 <strong>팁</strong>: 일반적으로 빈 리스트에 첫 번째 요소를 추가하기 위해서는 `append()`를 사용하지만, 인덱스가 0인 `insert()` 메서드를 호출하여 같은 요소를 추가할 수도 있습니다.


```
>>> num = []
>>> num.insert(0, 1.5) # 실수형인 1.5를 리스트의 인덱스 0에 추가합니다
>>> num
[1.5]
```

## 🔸 `list()` 생성자 사용하는 방법

빈 리스트를 생성하는 또 다른 방법은 새 리스트 객체를 생성하는 `list()` 생성자를 사용하는 것입니다. 

[Python 설명서](https://docs.python.org/ko/3/library/stdtypes.html#lists)에 따르면: 

> 인수가 주어지지 않으면, 생성자는 새로운 빈 리스트인 `[]` 을 만듭니다.

![var라는 변수에 list() 함수가 저장되어 있는 코드](https://www.freecodecamp.org/news/content/images/2020/06/image-132.png)

💡 <strong>팁</strong>: `list()` 생성자를 사용하면 메모리에 새 리스트 객체를 생성하게 되는데, 인수가 주어지지 않았기 때문에 메모리에 비어 있는 리스트가 생성됩니다. 


예를 들어서: 

```
num = list()
```

빈 리스트의 길이는 다음과 같이 0입니다:   

```
>>> num = list()
>>> len(num)
0
```

리스트가 비어 있으면 <strong>거짓같은 값</strong>입니다 (불리언 문맥에서 `False`로 평가됩니다):

```
>>> num = list()
>>> bool(num)
False
```

### 예시: 

`list()` 생성자를 사용해 만든 리스트 객체는 완전히 기능하는 리스트이기 때문에 다음과 같은 요소를 추가할 수 있습니다:

```
>>> num = list()
>>> for i in range(3, 15, 2):
	num.append(i)
```

결과는 다음과 같이 비어 있지 않는 리스트입니다: 

```
>>> num
[3, 5, 7, 9, 11, 13]
```

## 🔹 두 방법의 사용 사례 
- 일반적으로 문자열, 딕셔너리 또는 튜플과 같은 기존에 있는 반복 가능(iterable)한 객체에서 리스트를 생성할 때 `list()`를 사용합니다. 
- 대괄호 `[]`는 구문이 간결하고 빠르기 때문에 일반적으로 Python에서 빈 리스트를 생성할 때 사용합니다. 

## 🔸 두 방법의 효율 
위에서 말했듯이, `[]` 방법이 `list()` 생성자보다 빠릅니다.

하지만 얼마나 더 빠를까요? 

[timeit](https://docs.python.org/ko/3/library/timeit.html) 모듈을 사용해 실행 속도 효율을 확인해 보겠습니다.

이 모듈을 사용하려면 일단 Python 프로그램에서 불러와야 합니다:

```
>>> import timeit
```

timeit 모듈의 [timeit 함수](https://docs.python.org/ko/3/library/timeit.html#timeit.Timer.timeit)를 사용할 예정인데, 이 함수는 다음 구문을 사용해 호출할 수 있습니다:

![timeit 모듈의 timeit 함수를 활용한 코드](https://www.freecodecamp.org/news/content/images/2020/06/image-129.png)
> `timeit.timeit()` 메서드의 인자는 실행 시간을 측정할 코드와 선언한 코드의 수행 횟수입니다. 

💡 <strong>팁</strong>: 해당 코드는 특정 순간에 실행 중일 수 있는 다른 프로세스와 같은 외부 요인에 의해 발생할 수 있는 시간 차이를 줄이기 위해 여러 번 반복됩니다. 따라서 비교 목적으로 코드의 결과를 더욱 신뢰할 수 있습니다.

🚦 <strong>결과를 보실 준비가 되셨나요?</strong> 코드와 출력은 다음과 같습니다:

먼저, 모듈을 Python에 불러옵니다. 

```
>>> import timeit
```

그런 다음, 각 구문을 테스트합니다.

### Testing `[]`:
```
>>> timeit.timeit('[]', number=10**4)
0.0008467000000109692
```


### Testing `list()`:
```
>>> timeit.timeit('list()', number=10**4)
0.002867799999989984
```

💡 <strong>팁</strong>: 실행 시간을 측정하고 싶은 코드는 작은 따옴표 `''` 또는 큰 따옴표 `""`로 감싸야 합니다. `timeit` 함수는 실행 시간을 초 단위로 반환합니다.    
    

다음 결과를 비교합니다:
- `[]`: `0.0008467000000109692`
- `list()`: `0.002867799999989984`


`[]`가 `list()`보다 훨씬 빠르다는 것을 알 수 있습니다. 이 테스트에서는 약`0.002`초의 차이가 있었습니다.

```
>>> 0.002867799999989984 - 0.0008467000000109692
0.0020210999999790147
```

이 시점에서 다음과 같은 궁금증이 생길 수 있습니다: 동일한 작업을 수행하는 경우 `list()`가 `[]`보다 덜 효율적인 이유는 무엇일까요?    

`list()`는 함수의 이름을 찾고 호출한 다음 메모리에 리스트 객체를 생성해야 하기 때문에 더 느립니다. 반면에 `[]`는 메모리에 리스트를 생성하는 데 많은 중간 단계가 필요하지 않은 "바로 가기"와 같습니다.    

이 시간 차이는 프로그램의 성능에 큰 영향을 미치지는 않지만, 실행 속도 비교를 통해 어떤 방법이 더 효율적이고 각 방법이 실행될 때 백그라운드에서 어떻게 작동하는지 알 수 있습니다.    


## 🔹 요약
대괄호 `[]` 쌍 또는 `list()` 생성자를 사용하여 빈 리스트를 생성할 수 있습니다. `list()`는 인수가 전달되지 않으면 빈 리스트를 생성하는 Python의 내장 함수입니다.    

대괄호 `[]`는 실행 속도가 빠르고 간단하기 때문에 일반적으로 Python에서 빈 리스트를 생성할 때 사용합니다.    

<strong>제 글이 도움이 되었기를 바랍니다</strong>. 이 글을 통해 Python 프로젝트에서 빈 리스트를 만들 수 있습니다.    

원문 글쓴이의 [온라인 강좌](https://www.udemy.com/user/estefania-cn/)를 구경해보시고, [트위터](https://twitter.com/EstefaniaCassN) 계정도 팔로우 해주세요.

리스트에 대해 더 배우고 싶다면, 아래 기사들을 한 번 읽어보세요:
- [Python List Append – How to Add an Element to an Array, Explained with Examples](https://www.freecodecamp.org/news/python-list-append-how-to-add-an-element-to-an-array-explained-with-examples/)
- [The Python Sort List Array Method – Ascending and Descending Explained with Examples](https://www.freecodecamp.org/news/the-python-sort-list-array-method-ascending-and-descending-explained-with-examples/)
- [Python List Append VS Python List Extend – The Difference Explained with Array Method Examples](https://www.freecodecamp.org/news/python-list-append-vs-python-list-extend/)