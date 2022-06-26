# Push, Unshift 및 Concat 메서드를 사용해 JavaScript 배열에 요소를 추가하는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![자바스크립트 요소 추가 메서드들 - Push, Unshift, Concat](https://www.freecodecamp.org/news/content/images/size/w2000/2020/08/Hello--my-name-is-Matthew.-Nice-to-meet-you..png)

영어 원문: [JavaScript Array Insert - How to Add to an Array with the Push, Unshift, and Concat Functions](https://www.freecodecamp.org/news/javascript-array-insert-how-to-add-to-an-array-with-the-push-unshift-and-concat-functions/)   
원문 글쓴이: [Nehemiah Kivelevitz](https://www.freecodecamp.org/news/author/nehemiah/)


JavaScript 배열은 제가 가장 좋아하는 데이터 유형 중 하나입니다. 동적이고 사용하기 쉬우며, 프로그래머가 활용할 수 있는 다양한 내장 메서드들을 제공합니다.

그러나 옵션이 많을수록 어떤 메서드를 사용해야 할지 결정하는 것이 더 혼란스러울 수 있습니다.

이 기사에서는 JavaScript 배열에 요소를 추가하는 몇 가지 일반적인 방법에 관해 설명하려고 합니다.


## Push 메서드

첫 번째는, 가장 일반적으로 접할 수 있는 JavaScript 배열 메서드인 `push()`입니다. `push()` 메서드는 배열 끝에 요소를 추가하는 데 사용합니다. 

요소가 담긴 배열이 있다고 가정해 보겠습니다. 각 요소는 수행해야 하는 작업을 나타내는 문자열입니다. 이때, 이전 작업을 먼저 완료할 수 있도록 배열의 끝에 새 항목을 추가하는 것이 좋습니다.

코드 형식의 예를 살펴보겠습니다:


```
const arr = ['첫 번째 항목', '두 번째 항목', '세 번째 항목'];

arr.push('네 번째 항목');

console.log(arr); // ['첫 번째 항목', '두 번째 항목', '세 번째 항목', '네 번째 항목']

```

이렇게 `push` 메서드는 배열의 끝에 요소를 추가해주는 간단하고 좋은 코딩 구문을 제공해줍니다. 

한 번에 두세 개의 요소를 배열에 추가하고 싶다면, 어떻게 해야 할까요? 동일한 `push` 메서드로 여러 개의 요소를 추가할 수 있습니다.

```
const arr = ['첫 번째 항목', '두 번째 항목', '세 번째 항목'];

arr.push('네 번째 항목', '다섯 번째 항목');

console.log(arr); // ['첫 번째 항목', '두 번째 항목', '세 번째 항목', '네 번째 항목', '다섯 번째 항목']

```

배열에 몇 가지 항목을 추가했으니 현재 배열에 요소가 얼마나 있는지, 혹은 해야 할 작업이 너무 많은 건 아닌지 알고 싶을 수 있습니다. 

다행히도, `push()`는 요소가 추가된 후의 배열의 길이를 반환 값으로 가지고 있습니다.


```
const arr = ['첫 번째 항목', '두 번째 항목', '세 번째 항목'];

const arrLength = arr.push('네 번째 항목', '다섯 번째 항목');

console.log(arrLength); // 5
console.log(arr); // ['첫 번째 항목', '두 번째 항목', '세 번째 항목', '네 번째 항목', '다섯 번째 항목']
```

## Unshift 메서드

모든 작업이 동일하게 생성되지는 않습니다. 배열에 작업 항목을 추가하다가 갑자기 다른 항목보다 더 급한 작업이 생길 수도 있습니다.

이때 배열의 맨 처음에 항목을 추가할 수 있는 `unshift()` 메서드를 소개합니다.


```
const arr = ['첫 번째 항목', '두 번째 항목', '세 번째 항목'];

const arrLength = arr.unshift('급한 항목 1', '급한 항목 2');

console.log(arrLength); // 5 
console.log(arr); // ['급한 항목 1', '급한 항목 2', '첫 번째 항목', '두 번째 항목', '세 번째 항목']

```


위의 예시를 보면, `unshift()` 메서드는 `push()` 메서드와 마찬가지로, 요소들이 추가된 새 배열의 길이를 반환한다는 것을 알 수 있습니다. 또한 한 번에 두 개 이상의 요소를 추가할 수 있습니다. 


## Concat 메서드
`concat()` 메서드는 '함께 연결하다'라는 뜻을 가진 'concatenate'의 줄임말로, 두 개 이상의 배열을 결합하는 데 사용합니다.

위에서 말했듯이, `unshift()`와 `push()` 메서드는 새 배열의 길이를 반환합니다. 반면에 `concat()`은 완전히 새로운 배열을 반환합니다. 

이것은 매우 중요한 차이점이며, 기존 배열을 변형하고 싶지 않을 경우(예: React state에 저장된 배열), `concat()`이 매우 유용합니다.

다음은 상당히 기본적이고 간단한 활용 사례입니다:

```
const arr1 = ['?', '?'];
const arr2 = ['?', '?'];

const arr3 = arr1.concat(arr2);

console.log(arr3); // ["?", "?", "?", "?"] 

```


이제 두 개 이상의 배열을 결합하고 싶다고 가정해 보겠습니다. 이럴 때도 `concat()` 메서드를 사용할 수 있습니다.

```
const arr1 = ['?', '?'];
const arr2 = ['?', '?'];
const arr3 = ['?', '?'];

const arr4 = arr1.concat(arr2,arr3);

console.log(arr4); // ["?", "?", "?", "?", "?", "?"]
```

## concat를 사용해 기존 배열 복제하는 방법 

기존 배열을 변형하고 싶지 않을 때 `concat()` 메서드가 유용할 수 있다고 말했던 것을 기억하십니까? 이 개념을 활용해서 한 배열의 내용을 새 배열로 복사하는 방법을 살펴보겠습니다.




```
const arr1 = ["a", "b", "c", "d", "e", "f"];

const arr2 = [].concat(arr1);

arr2.push("g");

console.log(arr1) //["a", "b", "c", "d", "e", "f"]
console.log(arr2) //["a", "b", "c", "d", "e", "f", "g"]
```


이렇게 `concat()`을 사용해서 배열을 본질적으로 "복제"할 수 있습니다. 

그러나 이 복제 과정에는 작은 문제가 있습니다. 새 배열은 복사된 배열의 "얕은 복사본(shallow copy)"입니다. 즉, 복사 과정 중 객체 내 데이터 자체가 아닌 참조 값(reference)이 복사되어 전달됩니다. 

이 개념을 더 명확하게 설명하기 위해 예를 살펴봅시다.


```
const arr1 = [{food:"apple"}, {food:"banana"}, {food:"cranbery"}]

const arr2 = [].concat(arr1);

//change only arr2
arr2[1].food = "MELON";
arr2.push({food:"strawberry"})

console.log(arr1) //[ {food:'apple'}, {food:'MELON'}, {food:'cranbery'} ]

console.log(arr2) //[ {food:'apple'}, {food:'MELON'}, {food:'cranbery'}, {food: 'strawberry'} ]
```

이 예를 통해 기존 배열을 직접 변경하지는 않았지만, 결국 기존 배열은 복제된 배열에서 변경한 사항의 영향을 받았다는 것을 알 수 있습니다.

배열의 "깊은 복사(deep clone)"를 올바르게 수행하는 여러 가지 다른 방법이 있지만, 이것은 독자분들의 몫으로 남겨두겠습니다.

## 글을 마치며 

배열 끝에 요소를 추가하려면 `push()`를 사용합니다. 배열 맨 앞에 요소를 추가해야 하는 경우에는 `unshift()`를 사용합니다. 그리고 `concat()`을 사용하여 배열을 결합할 수 있습니다.

이 세 가지 메서드 외에 배열에 요소를 추가할 수 있는 다양한 메서드들이 많이 있으니, 독자분들도 다른 다양한 배열 메서드들 한 번 찾아보시길 바랍니다!

언제든지 트위터를 통해 제게 독자분이 좋아하는 배열 요소 추가 메서드를 알려주시길 바랍니다!


영어 원문을 읽고 싶으시다면 [JavaScript Array Insert - How to Add to an Array with the Push, Unshift, and Concat Functions](https://www.freecodecamp.org/news/javascript-array-insert-how-to-add-to-an-array-with-the-push-unshift-and-concat-functions/) 를 읽어보세요. 
