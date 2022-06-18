.length로 자바스크립트 배열이 비어 있는지 확인하는 방법
=============
#### 매디슨 칸나 저 (Madison Kanna) | 인보연 역 (Bo Yeon Ihn)

![scene of a concrete road](https://www.freecodecamp.org/news/content/images/size/w2000/2020/09/road-690087_1920.jpg)


# 자바스크립트로 프로그래밍할 때, 주어진 배열이 비어 있는지 확인하는 방법을 알아야 할 수도 있습니다.
주어진 배열이 비어 있는지 알려면 배열의 .length 속성을 사용할 수 있습니다.   

length 속성은 배열의 길이를 설정하거나 반환합니다. 배열의 요소 수를 알면 배열이 비어 있는지 여부를 알 수 있습니다. 빈 배열은 0개의 요소를 갖고 있습니다.   

몇 가지 예를 살펴보겠습니다.   

## .length 예제 구문   

```
const myArray = ['Horses', 'Dogs', 'Cats'];
```   

우선 배열이 담겨 있는 myArray 변수를 생성합니다.   

length 속성을 사용하여 주어진 myArray 배열의 길이를 확인할 수 있습니다:   

```
myArray.length
```
   
배열에 3개의 요소가 있으므로 3을 반환합니다.     

.length를 사용하여 배열이 비어 있는지 확인하려면 세 가지 방법이 있습니다.     



### .length 첫번째 예시 
먼저 요소가 없는 새 배열을 만듭니다.   

`const arr = []`
이제 .length 속성을 사용하여 배열이 비어 있는지 확인할 수 있습니다.   

`arr.length`
배열에 0개의 요소가 있으므로 .length 속성은 0을 반환합니다.    


### .length 두번째 예시 
배열이 비어 있는지 여부를 명시적으로 확인할 수도 있습니다.    

`if (arr.length === 0) { console.log("Array is empty!") }`

배열이 비어 있으면 위의 메세지가 출력됩니다. 배열에 요소가 있으면 `if`문의 코드 블록은 실행되지 않습니다.   

다음은 .length를 사용하여 배열이 비어 있는지를 확인하는 세번째 방법입니다.   

### .length 세번째 예시 
.length 속성과 자바스크립트의 논리 연산자 NOT의 의미가 담긴 `!` 느낌표를 함께 사용하여 배열이 비어 있는지를 확인할 수 있습니다.   

`!` 연산자는 주어진 표현식을 부정합니다. 즉, 이 `!` 연산자는 배열이 비어 있으면 `true`를 반환하는 데 사용할 수 있습니다.   

세번째 예시에서 자바스크립트 콘솔을 열어 보겠습니다. Chrome 브라우저에서 콘솔을 열려면 Inspect(검사) -> Console(콘솔)을 클릭하면 됩니다.   

먼저 요소가 없는 새 배열을 생성합니다.   

![arr 변수를 생성한 걸 보여주는 스크린샷](https://www.freecodecamp.org/news/content/images/2020/10/image.png)

다음, 논리 연산자 `NOT` 을 .length 속성과 함께 사용하여 배열이 비어 있는지 여부를 확인해보겠습니다.    

![연산자 NOT를 이용해 배열 길이를 확인하는 스크린샷](https://www.freecodecamp.org/news/content/images/2020/10/Screen-Shot-2020-09-30-at-5.29.35-PM.png)

`NOT` 연산자를 사용하지 않았다면 `arr.length`는 `0`을 반환했을 것입니다. 연산자가 추가되었기 때문에, 피연산자가 `false`이면 `arr.length`는 `true`를 반환합니다. `arr.length`는 `0` 또는 false이므로 `true`를 반환합니다.   

이제 `!` 연산자를 `if`문과 함께 사용하여, 배열이 비어 있으면 메세지를 출력해보겠습니다.   

![연산자 NOT와 if문을 사용해 배열 길이를 확인하는 코드 스크린샷](https://www.freecodecamp.org/news/content/images/2020/10/image-2.png)

배열이 비어 있는지 여부를 확인할 때, 주어진 배열이 실제로 배열인지도 확인하는 것이 좋습니다.   

그 이유는 배열의 길이를 확인하려고 했을 때 배열 대신 문자열(string) 같은 다른 데이터 유형이 제공되는 경우가 있기 때문입니다.   

![배열이 아닌 문자열이 주어진 상황](https://www.freecodecamp.org/news/content/images/2020/10/image-7.png)

`length 속성`은 다른 데이터 유형에도 사용될 수 있기 때문에 배열이 실제로 예상한 배열인지 확인하는 것이 좋습니다.    

주어진 배열이 배열인지 확인하기 위해서 `Array.isArray()` 메서드를 사용하는 것이 좋습니다. 이 메서드는 전달된 인수가 배열인지 판별합니다. 전달된 인수가 배열인 경우, 이 메서드는 `true`를 반환합니다.    

이 방법을 예제에 추가해 보겠습니다.   


### Array.isArray() 메서드를 사용하는 방법
![Array.isArray() 메서드를 사용한 코드 스크린샷](https://www.freecodecamp.org/news/content/images/2020/10/image-3.png)


## 마무리   
본 아티클에서는 자바스크립트의 `length` 속성을 다양한 방법으로 사용하여 주어진 배열이 비어 있는지 여부를 확인할 수 있음을 배웠습니다. `length` 속성은 배열의 요소 수를 반환합니다.   

또한 `.length` 속성을 사용할 때 `Array.isArray` 메서드를 함께 사용하여 전달된 값이 예상대로 확인하는 것이 가장 좋다는 것도 배웠습니다. 
