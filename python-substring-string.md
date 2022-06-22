# PYTHON 파이썬 문자열 자르는 방법
#### 인보연 번역 (Bo Yeon Ihn)

![강철 와이어 로프 사진](https://cdn-media-2.freecodecamp.org/w1280/5f9c9e45740569d1a4ca3c3e.jpg)
영어 원문: [How to Check if a JavaScript Array is Empty or Not with .length](https://www.freecodecamp.org/news/how-to-substring-a-string-in-python/)

### Python은 문자열을 부분 문자열(substring)로 만드는 여러 가지 방법을 제공하는데, 이것을 ‘슬라이싱(slicing)’이라고 부릅니다 .
구문은 다음과 같습니다.
```
String[start:end:step]
```
여기서,
`start`: 부분 문자열의 시작 인덱스입니다. 이 인덱스의 문자는 부분 문자열에 포함됩니다. 시작 인덱스를 생략하면 기본값인 0이 지정됩니다.    
`end`: 부분 문자열의 끝 인덱스입니다. 이 인덱스의 문자는 부분 문자열에 포함되지 않습니다. `end`가 생략되거나 지정된 값이 문자열 길이를 초과하면 기존 문자열의 길이와 동일하다고 가정합니다.    
`step`: 현재 문자에서 `step`간격으로 문자를 추출합니다. `step`을 생략하면 기본값인 1로 설정됩니다. 

## 기본 사용법 
`string[start:end]`: `start` 인덱스부터 `end`-1 인덱스  (`end` 인덱스는 제외)의 문자들을 슬라이싱합니다.    
`string[:end]`: 문자열의 맨 처음부터 `end`-1 인덱스 (`end` 인덱스는 제외)의 문자들을 슬라이싱합니다.    
`string[start:]`: `start` 인덱스부터 문자열의 마지막까지 슬라이싱합니다.    
`string[start:end:step]`: `start` 인덱스부터 `end`-1 인덱스 범위 내에 `step`간격으로 슬라이싱합니다. 

## 예시
### 1. 문자열의 첫 5 문자를 슬라이싱하기 
```
string = "freeCodeCamp"
print(string[0:5])
```
출력된 값:    

```
> freeC
```

참고: `print(string[:5])`는 `print(string[0:5])`와 같은 결과를 반환합니다.

### 2. 문자열의 세 번째 문자부터 시작하는 4자 길이의 부분 문자열을 추출하기     

```
string = "freeCodeCamp"
print(string[2:6])
```    

출력된 값:    

```
> eeCo
```

### 3. 문자열의 마지막 문자 추출하기     

```
string = "freeCodeCamp"
print(string[-1])
```

출력된 값:    
```
> p
```

위 예시를 보면 알 수 있듯이, `start` 또는 `end` 인덱스는 음수일 수 있습니다. 음수 인덱스는 주어진 문자열의 뒤에서부터 문자를 접근한다는 뜻입니다. -1 인덱스는 문자열의 마지막 문자를 가르키고, -2는 마지막에서 두 번째 문자를 가르키는 식입니다. 

### 4. 문자열의 마지막 5자를 부분 문자열로 추출하기    

```
string = "freeCodeCamp"
print(string[-5:])
```
출력된 값:    

```
> eCamp
```

### 5. 첫번째 문자와 마지막 4개의 문자를 제외한 부분 문자열 추출하기     

```
string = "freeCodeCamp"
print(string[1:-4])
```
출력된 값:    

```
> reeCode
```

### 6. 문자열 내 두 칸 간격으로 슬라이싱하기    

```
string = "freeCodeCamp"
print(string[::2])
```

출력된 값:    

```
> feCdCm
```
