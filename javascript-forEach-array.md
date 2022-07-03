# JavaScript에서 forEach 함수를 사용해 배열 루프 돌리기
#### 인보연 (Bo Yeon Ihn) 번역

![위에서 내려다보는 나선형 계단의 사진](https://cdn-media-2.freecodecamp.org/w1280/5f9c99d8740569d1a4ca2204.jpg)

영어 원문: [JavaScript forEach – How to Loop Through an Array in JS](https://www.freecodecamp.org/news/javascript-foreach-how-to-loop-through-an-array-in-js/)   
원문 글쓴이: [Cem Eygi](https://www.freecodecamp.org/news/author/cemeygi/)

### JavaScript의 forEach 메서드는 배열을 순환하는 여러 방법 중 하나입니다. 각 방법에는 특정 기능이 있으며 사용자는 실행하는 작업에 따라 어떤 방법을 사용할지 결정해야 합니다. 

이 기사에서는 JavaScript의 forEach 메서드를 자세히 살펴보겠습니다. 

다음과 같은 배열이 있다고 가정해 보겠습니다: 

```javascript 
const numbers = [1, 2, 3, 4, 5];
```

기존의 `for` 반복문을 사용해 배열을 루프하는 방법은 다음과 같습니다:

```javascript 
for (i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
} 
```

## forEach() 메서드는 어떻게 다른가요? 
forEach 메서드도 배열을 통해 루프하는 데 사용되지만 기존의 `for`반복문과는 다른 함수를 사용합니다. 

forEach 메서드는 다음 매개 변수(parameter)와 함께 배열의 각 요소에 대한 콜백 함수(callback function)을 전달합니다:

- Current Value (명명된 매개변수) - 처리할 현재 요소
- Index (선택적 매개변수) - 처리할 현재 요소의 인덱스
- Array (선택적 매개변수) - forEach()를 호출한 배열

주어진 매개변수를 하나씩 설명하겠습니다. 

우선 forEach 메서드를 사용해 배열을 순환하려면 콜백 함수 (또는 익명 함수)가 필요합니다:

```javascript
numbers.forEach(function() {
    // code
});
```

콜백 함수는 각 요소에 대해 실행되며, 배열의 요소를 나타내는 매개 변수를 하나 이상 사용해야 합니다: 

```javascript
numbers.forEach(function(number) {
    console.log(number);
});
```

콜백 함수와 최소 한 개의 매개변수가 있다면 배열 루프 돌기가 실행됩니다: 

![루프가 돌면서 1에서 5 숫자를 출력한다](https://www.freecodecamp.org/news/content/images/2020/06/Ads-z-2.png)

ES6 화살표 함수 표현을 사용해 코드를 단순화할 수 있습니다:


```javscript
numbers.forEach(number => console.log(number));
```
<p align = "center">
Arrow Function Representation
</p>

## 선택적 매개변수
### Index(인덱스)
첫 번째 선택적 매개변수는 각 요소의 인덱스 번호를 나타내는 "index" 매개 변수입니다.

forEach 메서드에 두 번째 매개변수를 포함하면 요소의 인덱스 번호를 출력할 수 있습니다:

```javascript
numbers.forEach((number, index) => {
    console.log('Index: ' + index + ' Value: ' + number);
});
```

![루프가 돌면서 인덱스와 주어진 값을 출력한다](https://www.freecodecamp.org/news/content/images/2020/06/Ads-z-3.png)

### Array(배열)
Array 매개변수는 배열 자체입니다. 선택적 매개변수이며, 필요한 경우 다양한 작업에 사용할 수 있습니다. Array 매개변수를 호출하면, 배열의 요소 수만큼 배열이 출력됩니다: 

```javascript
numbers.forEach((number, index, array) => {
    console.log(array);
});
```

![루프가 돌면서 배열의 요소 값을 매번 출력한다](https://www.freecodecamp.org/news/content/images/2020/07/Ads-z.png)

다음 영상은 forEach() 메서드의 활용 사례를 볼 수 있습니다 (번역가 주석: 원문 글쓴이의 영상이기 때문에 내용은 영어로 되어있습니다)

<iframe width="560" height="315" src="https://www.youtube.com/embed/E2GawbHDFfs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 브라우저 지원 
Array.forEach 메서드는 IE 버전 8 이하를 제외한 모든 브라우저에서 지원됩니다.

![caniuse.com 웹사이트 스크린샷](https://www.freecodecamp.org/news/content/images/2020/06/Ads-z.png)*caniuse.com*

웹 개발에 대해 더 자세히 알고 싶으시면 제 ![유튜브 채널을](https://www.youtube.com/channel/UC1EgYPCvKCXFn8HlpoJwY3Q?view_as=subscriber) 방문하세요.

읽어주셔서 감사합니다.