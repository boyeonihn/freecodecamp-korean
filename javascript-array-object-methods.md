# JavaScript 객체 배열 튜토리얼 - JS 배열 메서드를 사용해 객체를 생성, 업데이트 및 루프하는 방법 
#### 인보연 (Bo Yeon Ihn) 번역

![이미지의 왼쪽에는 어떤 함수가 가장 적합할까요?라는 질문과 함께 배열의 push, splice, insertAt 메서드들이 적혀 있습니다. 오른쪽에는 복잡한 고속도로 교차로에 차 여러 대가 진입하는 장면이 있습니다. ](https://www.freecodecamp.org/news/content/images/size/w2000/2020/05/js-tutorial-cover.jpg)

영어 원문: [JavaScript Array of Objects Tutorial – How to Create, Update, and Loop Through Objects Using JS Array Methods](https://www.freecodecamp.org/news/javascript-array-of-objects-tutorial-how-to-create-update-and-loop-through-objects-using-js-array-methods/)   
원문 글쓴이: [Ondrej Polesny](https://www.freecodecamp.org/news/author/ondrej/)


### 저는 평균적으로 일주일에 18번 JSON 데이터로 작업합니다. 그럼에도 불구하고 JSON 데이터를 다룰 때마다 구체적인 메서드 사용법을 검색해야 합니다. 이럴 때마다 명쾌한 해답을 주는 안내서가 있다면 얼마나 좋을까요?

이 기사에서는 JavaScript에서 객체 배열의 기본 사용법에 대해 설명하겠습니다. 

JSON은 JavaScript Object Notation의 약자이며, Javascript 객체 문법을 따르는 문자 기반의 데이터 형식입니다. JSON로 작업한 적이 있다면 JavaScript 객체도 익숙하실 것입니다. 

객체 생성은 다음과 같이 간단합니다: 

```javascript
{
  "color": "purple",
  "type": "minivan",
  "registration": new Date('2012-02-03'),
  "capacity": 7
}
```

위의 객체는 자동차를 나타냅니다. 자동차는 여러 종류와 색상이 있을 수 있고, 각 객체는 특정 자동차를 나타냅니다.  

![객체를 상징하는 보라색 차](https://www.freecodecamp.org/news/content/images/2020/05/purple.png)

대부분의 경우 외부 서비스로부터 이런 객체 데이터를 받습니다. 그러나 경우에 따라 제가 이 온라인 샵을 만들 때처럼 객체와 해당 배열을 직접 만들어야 합니다: 

![다양한 음식들이 나열되어 있는 메뉴의 웹사이트](https://www.freecodecamp.org/news/content/images/2020/05/categories.jpg)

각 범주별 목록 항목이 HTML에서 다음과 같이 작성됩니다:

![메뉴 중 하나의 항목의 데이터가 담긴 HTML 코드 블록](https://www.freecodecamp.org/news/content/images/2020/05/code.jpg)

이 코드를 수동으로 12번 반복하는 작업은 매우 번거롭고 유지보수가 어렵습니다. 

## 객체 배열 생성하기 

자동차 객체로 잠시 돌아가보겠습니다. 이 자동차 세트를 살펴보겠습니다: 

![일렬로 나열된 객체를 상징하는 다양한 색깔의 자동차들](https://www.freecodecamp.org/news/content/images/2020/05/cars.jpg)

이 자동차 세트를 다음과 같이 배열로 나타낼 수 있습니다: 

```javascript
let cars = [
  {
    "color": "purple",
    "type": "minivan",
    "registration": new Date('2017-01-03'),
    "capacity": 7
  },
  {
    "color": "red",
    "type": "station wagon",
    "registration": new Date('2018-03-03'),
    "capacity": 5
  },
  {
    ...
  },
  ...
]

```

일반적으로 객체 배열은 자주 조작하기 때문에 항상 동일하게 유지되지 않습니다. 기존 객체 배열에 새 객체를 추가해보겠습니다.

## Array.unshift를 사용해 새 객체를 배열 앞에 추가하기

![새로운 자동차 객체를 배열 맨 앞에 추가하는 이미지](https://www.freecodecamp.org/news/content/images/2020/05/beginning.jpg)

객체를 배열 맨 앞쪽에 추가하려면 `Array.unshift`를 사용해야 합니다. 

```javascript
let car = {
  "color": "red",
  "type": "cabrio",
  "registration": new Date('2016-05-02'),
  "capacity": 2
}
cars.unshift(car);
```

## Array.push를 사용해 새 객체를 배열 뒤에 추가하기

![새로운 자동차 객체를 배열 맨 끝에 추가하는 이미지](https://www.freecodecamp.org/news/content/images/2020/05/ending.jpg)

객체를 배열 맨 뒤쪽에 추가하려면 `Array.push`를 사용해야 합니다.

```javascript
let car = {
 "color": "red",
 "type": "cabrio",
 "registration": new Date('2016-05-02'),
 "capacity": 2
}
cars.push(car);
```

## Array.splice를 사용해 새 객체를 배열 중간에 추가하기
![새로운 자동차 객체를 배열의 특정 인덱스에 추가하는 이미지](https://www.freecodecamp.org/news/content/images/2020/05/middle.jpg)

객체를 배열 중간에 추가하려면 `Array.splice`를 사용해야 합니다. 이 메서드는 기존 요소를 삭제할 수도 있어서 매우 편리합니다. 다음과 같은 매개변수가 있습니다: 

```javascript
Array.splice(
  {배열의 변경을 시작할 인덱스},
  {배열에서 제거할 요소의 수},
  {배열에 추가할 요소}
);
```

예를 들어, 빨간색 폭스바겐 카브리오를 다섯 번째 위치에 추가하려면 다음과 같은 코드를 실행합니다:

```javascript
let car = {
  "color": "red",
  "type": "cabrio",
  "registration": new Date('2016-05-02'),
  "capacity": 2
}
cars.splice(4, 0, car);
```


## 객체 배열을 통한 루프 
여기서 질문 하나 하겠습니다. 객체 배열을 반복하는 이유는 무엇입니까? 대부분의 경우, 객체 배열을 통한 루프는 항상 목적을 위한 수단이기 때문에, 루프를 통해 이루고 싶은 주된 목적은 따로 있습니다. 

JavaScript는 반복 로직을 구현하지 않아도 원하는 문제를 해결할 수 있는 많은 기능을 제공합니다. 한 번 살펴보겠습니다. 

### Array.find를 사용해 배열 내 특정 값을 만족하는 객체 찾기 
빨간색 차를 찾고 싶다고 가정해 보겠습니다. 이때 `Array.find` 메서드를 사용합니다. 

![차 객체 배열 중 빨간 차 객체 하나를 찾는 것을 시각화한 이미지](https://www.freecodecamp.org/news/content/images/2020/05/cars-colorred.jpg)

```javascript
let car = cars.find(car => car.color === "red");
```

`Array.find` 메서드는 일치하는 첫 번째 요소를 반환합니다. 

``` javascript
console.log(car);
// 출력된 값:
// {
//   color: 'red',
//   type: 'station wagon',
//   registration: 'Sat Mar 03 2018 01:00:00 GMT+0100 (GMT+01:00)',
//   capacity: 5
// }
```

한 번에 여러 값을 검색할 수도 있습니다: 

`let car = cars.find(car => car.color === "red" && car.type === "cabrio");`

이런 경우, 배열의 마지막 객체가 반환됩니다. 

### Array.filter를 사용해 특정 조건을 만족하는 모든 객체 찾기 
`Array.find` 함수는 조건을 만족하는 첫 번쨰 객체만 반환합니다. 빨간 차를 모두 구하려면 `Array.filter`를 사용해야 합니다.

![차 객체 배열 중 빨간 차 객체 모두 찾는 것을 시각화한 이미지](https://www.freecodecamp.org/news/content/images/2020/05/cars-colorred2.jpg)

```javascript
let redCars = cars.filter(car => car.color === "red");
console.log(redCars);
// 출력된 값:
// [
//   {
//     color: 'red',
//     type: 'station wagon',
//     registration: 'Sat Mar 03 2018 01:00:00 GMT+0100 (GMT+01:00)',
//     capacity: 5
//   },
//   {
//     color: 'red',
//     type: 'cabrio',
//     registration: 'Sat Mar 03 2012 01:00:00 GMT+0100 (GMT+01:00)',
//     capacity: 2
//   }
// ]
```

## Array.map를 사용해 배열 내 객체를 바꾸기 
`Array.map`를 사용해 기존 객체 배열을 다른 객체 배열로 변환하는 일은 매우 자주 하는 작업입니다. 이 메서드를 사용해 자동차를 크기에 따라 세 그룹으로 분류해보겠습니다: 

![여러 색과 크기의 차 객체들을 담은 배열](https://www.freecodecamp.org/news/content/images/2020/05/cars-sizes.jpg)

``` javascript
let sizes = cars.map(car => {
  if (car.capacity <= 3){
    return "small";
  }
  if (car.capacity <= 5){
    return "medium";
  }
  return "large";
});
console.log(sizes);
// 출력된 값:
// ['large','medium','medium', ..., 'small']
```


더 많은 값이 필요한 경우 새 객체를 생성할 수도 있습니다:

```javascript
let carsProperties = cars.map(car => {
 let properties = {
   "capacity": car.capacity,
   "size": "large"
 };
 if (car.capacity <= 5){
   properties['size'] = "medium";
 }
 if (car.capacity <= 3){
   properties['size'] = "small";
 }
 return properties;
});
console.log(carsProperties);
// 출력된 값:
// [
//   { capacity: 7, size: 'large' },
//   { capacity: 5, size: 'medium' },
//   { capacity: 5, size: 'medium' },
//   { capacity: 2, size: 'small' },
//   ...
// ]
```

### Array.forEach를 사용해 객체에 새로운 속성 추가하기
자동차 크기 값도 유지하고 싶으면 어떡해야 할까요? 이 경우, 새 속성 `size`를 객체에 정의할 수 있습니다. `Array.forEach` 함수의 좋은 활용 사례입니다. 

```javascript
cars.forEach(car => {
 car['size'] = "large";
 if (car.capacity <= 5){
   car['size'] = "medium";
 }
 if (car.capacity <= 3){
   car['size'] = "small";
 }
});
```

### Array.sort를 사용해 속성별로 배열의 객체 정렬하기 
객체 반환이 끝나면 일반적으로 객체들을 사용자 정의된 기준에 따라 정렬합니다. 

일반적으로 정렬은 모든 객체가 가지고 있는 속성 중 하나의 값을 기준으로 합니다. 기반으로 합니다. `Array.sort` 함수를 사용하기 위해서는 정렬 순서를 정의하는 함수를 제공해야 합니다.

자동차를 용량에 따라 내림차순으로 정렬해보겠습니다. 

![차량 용량 크기 순으로 배열 정리를 한 이미지](https://www.freecodecamp.org/news/content/images/2020/05/cars-sort.jpg)

```javascript
let sortedCars = cars.sort((c1, c2) => (c1.capacity < c2.capacity) ? 1 : (c1.capacity > c2.capacity) ? -1 : 0);
console.log(sortedCars);
// 출력된 값:
// [
//   {
//     color: 'purple',
//     type: 'minivan',
//     registration: 'Wed Feb 01 2017 00:00:00 GMT+0100 (GMT+01:00)',
//     capacity: 7
//   },
//   {
//     color: 'red',
//     type: 'station wagon',
//     registration: 'Sat Mar 03 2018 01:00:00 GMT+0100 (GMT+01:00)',
//     capacity: 5
//   },
//   ...
// ]
```

`Array.sort` 함수는 두 객체를 비교해 정렬 함수의 결과가 양수이면 첫 번째 객체를 두 번째 위치에 놓습니다. 정렬 기능은 해당 질문을 묻는 것과 같습니다: 첫 번째 객체는 두 번째 위치에 놓아야 하나요?

![차 객체가 정렬되는 프로세스](https://www.freecodecamp.org/news/content/images/2020/05/sort.png)

불필요한 정렬을 방지하기 위해 비교되는 두 객체의 값이 같을 때 `0`값이 반환되도록 설정해야 합니다. 

### `Array.every`와 `Array.includes`를 사용해 배열의 객체가 조건을 충족하는지 확인하기 
배열의 객체가 주어진 조건을 충족하는지 확인할 때 `Array.every` 또는 `Array.some`를 사용할 수 있습니다. 예를 들어:

배열에 빨간색 카브리오가 있습니까? 모든 차 객체에 최소 4명 이상 탑승할 수 있나요? 또는 웹과 연관된 조건의 예는: 장바구니에 특정 제품이 있습니까? 

```javascript
cars.some(car => car.color === "red" && car.type === "cabrio");
// 출력된 값: true

cars.every(car => car.capacity >= 4);
// 출력된 값: false
```

`Array.includes`는 `Array.some`과 비슷하지만 원시 자료형에서만 작동한다는 중요한 차이점이 있습니다. 

## 요약 
이 기사에서는 객체 배열의 생성, 조작, 변환 및 루프와 관련된 기본 기능들에 대해 설명했습니다. 대부분의 객체 배열 사례는 이 메서드를 통해 풀 수 있는 문제들입니다. 
In this article, we went through the basic functions that help you create, manipulate, transform, and loop through arrays of objects. They should cover most cases you will stumble upon.

더 고급 기능이 필요한 사용 사례가 있는 경우 이 [자세한 가이드 [영문]](https://www.freecodecamp.org/news/data-structures-101-arrays-a-visual-introduction-for-beginners-7f013bcc355a/) 를 살펴보거나 [W3 schools 참조 자료](https://www.w3schools.com/Jsref/jsref_obj_array.asp)를 확인해보세요. 

또는 [제게 연락해 주신다면](https://twitter.com/ondrabus) 제가 새로운 기사를 준비하겠습니다 :-)