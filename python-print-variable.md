# Python에서 문자열과 변수 출력하는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![타자기로 문서 작성하는 사람](https://www.freecodecamp.org/news/content/images/size/w2000/2021/12/denise-jans-_dXkaD3l574-unsplash.jpg)

영어 원문: [Python Print Variable – How to Print a String and Variable](https://www.freecodecamp.org/news/python-print-variable-how-to-print-a-string-and-variable/)   
원문 글쓴이: [Dionysia Lemonaki](https://www.freecodecamp.org/news/author/dionysia/)


### Python은 유연하고 다목적으로 사용할 수 있는 프로그래밍 언어입니다. 보통 한 가지를 프로그래밍하기 위해 다양한 방법으로 작업을 수행할 수 있습니다.

이 튜토리얼에서는 문자열과 변수를 함께 출력할 수 있는 몇 가지 방법을 살펴보겠습니다. 

그럼 시작해볼까요?

## Python에서 `print()` 함수 사용하기 

Python에서 무언가를 출력하려면 `print()` 함수를 사용합니다. `print` 키워드 뒤에 괄호 `()` 한 쌍을 붙입니다.

```
#문자열 출력하는 방법
print("Hello world")

#정수 출력하는 방법 
print(7)

#변수 출력하는 방법 
#변수 자체를 출력하려면 변수 이름만 표기합니다 

fave_language = "Python"
print(fave_language)

#출력된 값

#Hello world
#7
#Python
```

괄호를 생략하면 오류가 발생합니다:

```
print "hello world"

#코드 실행 후 출력된 값:
#File "/Users/dionysialemonaki/python_articles/demo.py", line 1
#    print "hello world"
#    ^^^^^^^^^^^^^^^^^^^
#SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

Visual Studio Code에서 [Python 확장 프로그램](https://marketplace.visualstudio.com/items?itemName=ms-python.python)을 다운로드 받고 Python 코드를 작성하면, 잘못된 코드에 밑줄과 힌트가 표시되어 오류가 발생했다는 것을 알 수 있습니다:

![오류가 발생해서 코드가 밑줄이 그어져있고 힌트가 표시됩니다](https://www.freecodecamp.org/news/content/images/2021/12/Screenshot-2021-12-07-at-3.08.14-PM.png)

위에서 얘기했듯이, `print()` 함수는 텍스트 및 숫자 데이터, 변수 및 기타 데이터 유형 같은 모든 종류의 정보를 출력하는 데 사용됩니다.    

또한 변수와 결합된 텍스트(또는 문자열)를 한 번에 출력할 수도 있습니다. 다음 섹션에서는 이 작업을 수행하는 몇 가지 방법에 대해 다루겠습니다.    

## Python에서 문자열을 변수와 결합해서(concatenation) 출력하기

사전에 따르면, "concatenate"은 무언가를 일렬로 함께 연결하는 것을 의미합니다.

Python에서는 `+` 덧셈 연산자를 사용하여 다양한 항목 또는 데이터를 추가합니다.

결합하기(concatenation)는 문자열에만 사용되기 때문에 문자열과 연결하려는 변수가 정수 데이터 유형이면 `str()` 함수를 사용해 문자열로 변환해야 합니다.

다음 예시에서는 변수 값을 다른 문자열과 함께 출력해보겠습니다. 

문자열은 큰따옴표로 묶고 변수 이름은 묶지 않고 덧셈 연산자를 사용해 모두 함께 연결합니다.


```
fave_language = "Python"

print("I like coding in " + fave_language + " the most")

#output
#I like coding in Python the most

```
문자열을 결합할 때는 공백을 직접 추가해야 합니다. 이전 예에서 따옴표 안에 공백을 포함하지 않았다면 다음과 같이 출력됩니다: 

```
fave_language = "Python"

print("I like coding in" + fave_language + "the most")

#output
#I like coding inPythonthe most
```

공백을 별도로 추가할 수도 있습니다: 

```
fave_language = "Python"

print("I like coding in" + " " + fave_language + " "  + "the most")

#output
#I like coding in Python the most
```

이 방법은 오류가 발생하기 쉽고 시간이 오래 걸릴 수 있기 때문에 문자열과 변수를 출력하는 데 가장 선호하는 방법은 아닙니다.


## Python에서 변수와 문자열을 쉼표로 구분하여 출력하기 

변수와 텍스트를 쉼표로 구분 지어서 두 데이터 유형을 함께 출력할 수 있습니다. 

```
first_name = "John"

print("Hello",first_name)

#output
#Hello John

```

위의 예에서는 먼저 큰따옴표로 출력할 텍스트 (문자열 `Hello`)를 묶습니다. 

해당 텍스트와 `first_name` 변수가 가르키는 값을 구분하기 위해 텍스트를 묶은 닫힘 따옴표 뒤에 쉼표를 추가합니다. 

또한 변수 뒤에 다음과 같이 텍스트를 더 추가할 수 있습니다: 

```
first_name = "John"

print("Hello",first_name,"good to see you")

#output
#Hello John good to see you

```

이 방법은 두 개 이상의 변수가 있을 때도 실행됩니다: 

```
first_name = "John"
last_name = "Doe"

print("Hello",first_name,last_name,"good to see you")

#output
Hello John Doe good to see you
```

모든 항목을 쉼표로 구분해야 합니다. 위의 예시에 나타난 것과 같이 텍스트와 변수를 구분할 때, 그리고 변수와 변수 사이를 구분할 때 쉼표를 추가해야 합니다. 

쉼표를 `first_name`과 `last_name` 변수 사이에 추가하지 않으면 다음과 같은 오류가 발생됩니다. 


```
first_name = "John"
last_name = "Doe"

print("Hello",first_name last_name,"good to see you")

#output
#File "/Users/dionysialemonaki/python_articles/demo.py", line 4
#    print("Hello",first_name last_name,"good to see you")
#                 ^^^^^^^^^^^^^^^^^^^^
#SyntaxError: invalid syntax. Perhaps you forgot a comma?
```
보시다시피 Python 오류 메시지는 매우 유용하며 디버깅 프로세스를 조금 더 수월하게 해줍니다 :)

## 파이썬에서 문자열 포매팅(string formatting) 방법을 사용해 변수와 문자열 출력하기 

변수 값을 추가할 위치에 중괄호 `{}` 한 쌍을 포함하여 문자열 포매팅을 합니다.

```
first_name = "John"

print("Hello {}, hope you're well!")
```

이 예에서는 하나의 변수 `first_name`이 있습니다.    

`print()`문 안에는 출력해야 하는 텍스트를 묶은 큰따옴표 `""` 한 쌍이 있습니다.    

큰따옴표 안에 변수 `first_name`의 값을 배치하고 싶은 곳에 중괄호 `{}` 쌍을 표기했습니다.    

이 코드를 실행하면 다음과 같은 출력이 나타납니다: 

```
#output
#Hello {}, hope you're well!
```

`first_name` 값이 실제로 출력되지 않았습니다.    

변수 값을 출력하려면 문자열의 닫힌 따옴표 바로 뒤에 `.format()` 문자열 메서드를 추가해야 합니다. 


```
first_name = "John"

print("Hello {}, hope you're well!".format(first_name))

#output
#Hello John, hope you're well!
```

변수가 두 개 이상 있으면 출력하려는 변수의 개수만큼 중괄호 `{}`를 사용합니다.

```
first_name = "John"
last_name = "Doe"

print("Hello {} {}, hope you're well!")
```

이 예에서는 두 개의 변수를 생성하고 두 변수를 차례로 출력하려고 합니다. 변수를 대체할 위치에 중괄호 `{}` 두 쌍을 추가했습니다.

`.format()` 메서드를 사용할 때는 변수 이름을 배치하는 순서가 중요합니다.    

다시 말해, `.format()` 메소드 내에서 먼저 추가된 변수의 값은 첫 번째 중괄호 `{}` 쌍에 위치하고, 두 번째로 추가된 변수의 값은 두 번째 중괄호 `{}` 쌍에 위치합니다.

메서드 내에서는 변수 이름을 쉼표로 구분해야 합니다:

```
first_name = "John"
last_name = "Doe"

print("Hello {} {}, hope you're well!".format(first_name,last_name))

#output
#Hello John Doe, hope you're well!
```

메서드 내에  변수의 순서를 반대로 바꾼다면 출력된 값도 다르게 나타납니다.

```
first_name = "John"
last_name = "Doe"

print("Hello {} {}, hope you're well!".format(last_name,first_name))

#output
#Hello Doe John, hope you're well!
```

## Python에서 `f-strings`를 사용해 변수와 문자열을 출력하기
`f-strings`은 이전 섹션에서 다룬 방법보다 문자열 포매팅을 더 읽기 쉽고 간결하게 만들어 줍니다. 

구문은 더 쉽고 수동으로 입력해야 할 항목이 비교적으로 적습니다. 

`f-string`을 만드는 일반적인 구문은 다음과 같습니다: 

```
print(f"I want this text printed to the console!")

#output
#I want this text printed to the console!
```

먼저 `print()` 함수 안에 있는 따옴표 `""` 쌍 앞에 문자  `f` 를 붙여줍니다. 

변수를 문자열과 함께 한 줄에 출력하려면 따옴표 바로 앞인 동일한 위치에 문자 `f`를 표기합니다.

그런 다음 따옴표 안에 원하는 텍스트를 추가하고 변수 값을 추가할 위치에 변수 이름를 묶은 중괄호 `{}` 쌍을 추가합니다.

```
first_name = "John"

print(f"Hello, {first_name}!")

#output
#Hello, John!
```

두 개 이상의 변수를 출력하려면 두 번째 변수 이름을 묶은 중괄호 `{}` 쌍을 추가합니다.


```
first_name = "John"
last_name = "Doe"

print(f"Hello, {first_name} {last_name}!")

#output
#Hello, John Doe!
```

변수 이름을 배치하는 순서에 따라 출력된 값이 달라지기 떄문에 변수 이름을 원하는 순서로 정렬해야 합니다. 

변수 이름의 순서를 거꾸로 하면 다음과 같은 값이 출력됩니다: 

```
first_name = "John"
last_name = "Doe"

print(f"Hello, {last_name} {first_name}!")

#output
#Hello, Doe John!
```


## 결론 
끝까지 읽어주셔서 감사합니다! 이 튜토리얼에서는 Python에서 문자열과 변수를 한 줄로 함께 출력하는 몇 가지 방법을 배웠습니다.

Python에 대해 더 배우고 싶다면 freeCodeCamp의 [Python 수료증 과정](https://www.freecodecamp.org/learn/scientific-computing-with-python/)에 대해 더 알아보시길 바랍니다. 이 수료증 과정은 기초부터 시작해서 점차 고급 개념으로 진도를 나가기 때문에 초보자에게 적합합니다. 또한 5개의 프로젝트를 진행하면서 수료과정 동안 습득한 모든 프로그래밍 지식을 응용할 수 있습니다.

즐거운 코딩 되시길! 
