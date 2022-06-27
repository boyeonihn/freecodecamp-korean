# Python 리스트 길이 구하는 방법 
#### 인보연 (Bo Yeon Ihn) 번역

![날짜가 적혀 있는 일일 플래너](https://www.freecodecamp.org/news/content/images/size/w2000/2022/03/calendar-g2ed8847ef_1280.jpg)

영어 원문: [Python List Length – How to Get the Size of a List in Python](https://www.freecodecamp.org/news/python-list-length-how-to-get-the-size-of-a-list-in-python/)   
원문 글쓴이: [Kolade Chris](https://www.freecodecamp.org/news/author/kolade/)


### Python에서는 리스트를 사용해 문자열 및 숫자와 같은 다양한 유형의 데이터를 저장합니다.

리스트를 정의할 때는 대괄호 `[]`가 사용되며, 개별 값과 항복은 쉼표로 구분됩니다.    

Python 리스트의 길이를 확인하려면 내장 함수 `len()` 을 사용하면 됩니다.   

`len()` 함수 외에도 `for`문과 `length_hint()` 함수를 사용해 리스트의 길이를 구할 수 있습니다.    

이 기사에서는 리스트의 길이를 구하는 세 가지 방법을 보여드리겠습니다. 


## `For`문을 사용해 Python 리스트의 길이 구하는 방법 

튜플과 딕셔너리와 마찬가지로 리스트는 반복 가능한 이터러블(iterable)한 객체이기 때문에, Python의 `for`문을 사용해 리스트의 길이를 구할 수 있습니다. 

이 방법을 일반적으로 나이브 메서드(naïve method)라고 합니다. 

아래 예시는 나이브 메서드를 사용해 Python에서 리스트의 길이를 가져오는 방법을 보여줍니다. 


```
demoList = ["Python", 1, "JavaScript", True, "HTML", "CSS", 22]

# 카운터 변수를 생성합니다 
counter = 0

for item in demoList:
    # 리스트의 각 항목을 가져오기 위해 카운터 변수를 1씩 증가시킵니다 
    counter = counter + 1

    # 카운터 변수를 문자열로 변환해 결과를 콘솔에 출력합니다 
print("나이브 메서드(naive method)를 사용해 구한 리스트 길이의 값은: " + str(counter) + "입니다")
# 출력된 값: 나이브 메서드(naive method)를 사용해 구한 리스트 길이의 값은: 7입니다

```

## `len()` 함수를 사용해 리스트의 길이 구하는 방법 

반복 가능한 객체의 길이를 구하는 가장 일반적인 방법은 `len()` 함수를 사용하는 것입니다.     

이 방법은 `for`문을 사용하는 것보다 더 간단합니다.   

`len()` 메서드를 사용하는 구문은 `len(리스트이름)`입니다.  

아래 코드 블록은 `len()` 함수를 사용해 리스트의 길이를 가져오는 방법입니다:  


```
demoList = ["Python", 1, "JavaScript", True, "HTML", "CSS", 22]

sizeOfDemoList = len(demoList)

print("출력된 값: len() 메서드를 사용해 구한 리스트 길이의 값은: " + str(sizeOfDemoList) + "입니다")
# 출력된 값: len() 메서드를 사용해 구한 리스트 길이의 값은: 7입니다
```




## `length_hint()` 함수를 사용해 리스트의 길이 구하는 방법

`length_hint()` 메서드는 리스트 및 기타 반복 가능한 객체들의 길이를 구하는 덜 알려진 방법입니다.   

`length_hint()`는 operator 모듈에 정의되어 있어서 사용하려면 먼저 Python에서 불러와야 합니다.      

`length_hint()`를 사용하는 구문은 `length_hint(리스트이름)`입니다.    

아래 예시는 `length_hint()` 메서드를 사용해 리스트의 길이를 가져오는 방법입니다: 

```
from operator import length_hint

demoList = ["Python", 1, "JavaScript", True, "HTML", "CSS", 22]

sizeOfDemoList = length_hint(demoList)
print("length_hint() 메서드를 이용해 구한 리스트 길이의 값은: " + str(sizeOfDemoList) + "입니다")
# 출력된 값: length_hint() 메서드를 이용해 구한 리스트 길이의 값은: 7입니다 

```



## 글을 마치며

이 기사에서는 `for`문, `len()` 함수 및 operator 모듈의 `length_hint()` 함수의 세 가지 방법으로 리스트의 길이를 구하는 방법을 보여줬습니다.    

이 세 가지 방법 중 어떤 방법을 사용할지 궁금할 수 있습니다. 

`for`문과 `length_hint()` 함수에 비해 사용법이 간단한 `len()`을 사용하는 것을 추천합니다.    

또한 `len()`는 실행 속도가 `for`문과 `length_hint()`보다 빠른 편입니다.

이 글이 도움이 되었다면 필요한 다른 분들도 볼 수 있도록 공유해 주세요.

