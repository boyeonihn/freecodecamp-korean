# JavaScript에서 문자열을 역순으로 뒤집는 세 가지 방법
#### 인보연 (Bo Yeon Ihn) 번역

![아치형 건축물을 아래에서 바라보며 찍은 사진](https://cdn-media-1.freecodecamp.org/images/1*aFrHLdCeSRv4z-hsfCA6hw.jpeg)

영어 원문: [Three Ways to Reverse a String in JavaScript](https://www.freecodecamp.org/news/how-to-reverse-a-string-in-javascript-in-3-different-ways-75e4763c68cb/)   
원문 글쓴이: [Sonya Moisset](https://www.freecodecamp.org/news/author/sonya/)


### 이 기사는 freeCodeCamp의 기본 알고리즘 작성법 - [문자열 반전 튜토리얼](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-algorithm-scripting/reverse-a-string)을 기반으로 합니다. 

문자열 반전하기는 기술 인터뷰에서 가장 자주 묻는 JavaScript 질문 중 하나입니다. 인터뷰 진행자는 문자열을 뒤집는 여러 방법을 작성하도록 요청하거나, 내장된 메서드를 사용하지 않고 문자열을 반전하도록 요청하거나, 또는 재귀(recursion)를 사용해 문자열을 반전하도록 요청할 수 있습니다.    

JavaScript에는 문자열을 반전하는 내장 메서드가 없지만, 이 점을 제외하더라도 다른 다양한 방법이 있습니다.   

다음은 JavaScript에서 문자열을 반전시킬 수 있는 가장 흥미로운 세 가지 방법입니다.

## 알고리즘 문제
<blockquote>
    <p>제공된 문자열을 반대로 바꿉니다.</p>
    <p>문자열을 반전시키기 전에 문자열을 배열로 변환해야 할 수도 있습니다.</p>
    <p>반환되는 결과가 문자열이어야 합니다.</p>
</blockquote>

```javascript
function reverseString(str) {
    return str;
}
reverseString("hello");
```

## 제공되는 테스트 케이스 
- reverseString("hello") 은 "olleh"를 반환해야 합니다.
- reverseString("Howdy") 은 "ydwoH"를 반환해야 합니다.
- reverseString("Greetings from Earth") 은 "htraE morf sgniterG"를 반환해야 합니다.

## 1. 내장 함수들을 사용해 문자열 반전하기 

이 솔루션에서는 `String.protype.split()`, `Array.protype.reverse()`, 그리고 `Array.protype.join()`의 총 세가지 메서드를 사용합니다:

- `split()` 메서드는 문자열을 부분 문자열(substring)로 구분해 문자열 객체를 여러 개의 문자열로 이루어진 배열로 분할합니다.
- `reverse()` 메서드는 배열을 반전합니다. 첫 번째 배열 요소는 마지막 요소가 되고 마지막 요소는 첫 번째 요소가 됩니다.
- `join()` 메서드는 배열의 모든 요소를 문자열로 결합합니다.


```javascript
function reverseString(str) {
    // 1. split() 메서드를 사용해 새 배열을 반환하기
    var splitString = str.split(""); // var splitString = "hello".split("");
    // ["h", "e", "l", "l", "o"]
 
    // 2. reverse() 메서드를 사용해 새 배열의 순서를 뒤집기
    var reverseArray = splitString.reverse(); // var reverseArray = ["h", "e", "l", "l", "o"].reverse();
    // ["o", "l", "l", "e", "h"]
 
    // 3. join() 메서드를 사용해 배열의 모든 요소를 문자열로 결합하기
    var joinArray = reverseArray.join(""); // var joinArray = ["o", "l", "l", "e", "h"].join("");
    // "olleh"
    
    // 4. 반전된 문자열을 반환하기
    return joinArray; // "olleh"
}
 
reverseString("hello");

```

## 세 메서드를 한 줄에 작성하기 

``` javascript
function reverseString(str) {
    return str.split("").reverse().join("");
}
reverseString("hello");
```

## 2. 내림차순으로 반복하는 for문으로 문자열 반전하기

```javascript
function reverseString(str) {
    // 1. 새로 생성될 문자열을 담을 빈 문자열을 만들기
    var newString = "";
 
    // 2. for문을 작성하기
        /* 반복문의 시작점은 문자열의 마지막 문자 "o"의 인덱스인 (str.length - 1)입니다.
        i가 0보다 크거나 같은 한 코드는 반복적으로 수행됩니다.
        코드가 반복할 때마다 i의 값을 줄입니다 */
    for (var i = str.length - 1; i >= 0; i--) { 
        newString += str[i]; // 또는 newString = newString + str[i];
    }
    /* 코드의 이 단계에서는 hello의 길이는 5입니다
        코드가 반복할 때마다: i = str.length - 1 그리고 newString = newString + str[i]
        첫 번째 반복:    i = 5 - 1 = 4,         newString = "" + "o" = "o"
        두 번째 반복:   i = 4 - 1 = 3,         newString = "o" + "l" = "ol"
        세 번째 반복:    i = 3 - 1 = 2,         newString = "ol" + "l" = "oll"
        네 번째 반복:   i = 2 - 1 = 1,         newString = "oll" + "e" = "olle"
        다섯 번째 반복:    i = 1 - 1 = 0,         newString = "olle" + "h" = "olleh"
    for 반복문이 끝납니다*/
 
    // 3. 반전된 문자열을 반환하기
    return newString; // "olleh"
}
 
reverseString('hello');
```
## 주석을 생략한 코드 
``` javascript
function reverseString(str) {
    var newString = "";
    for (var i = str.length - 1; i >= 0; i--) {
        newString += str[i];
    }
    return newString;
}
reverseString('hello');
```

## 3. 재귀로 문자열 반전하기 
이 솔루션에서는 `String.prototype.substring()`와 `String.prototype.charAt()`의 두 가지 메서드를 사용합니다:

- `substring()` 메서드는 기존 문자열의 특정 시작 인덱스부터 끝 인덱스 범위 내에 위치한 문자를 부분 문자열로 반환합니다.

```javascript
"hello".substr(1); // "ello"
```

- `charAt()` 메서드는 문자열의 특정 인덱스에 위치하는 문자를 반환합니다.

```javascript
"hello".charAt(0); // "h"
```

재귀 깊이는 문자열의 길이와 같습니다. 이 솔루션은 실행 속도가 매우 느리기 때문에 문자열이 매우 길고 스택 크기가 중요한 경우 가장 효율적인 문자열 반전 방법이 아닙니다.

```javascript
function reverseString(str) {
  if (str === "") // This is the terminal case that will end the recursion
    return "";
  
  else
    return reverseString(str.substr(1)) + str.charAt(0);
/* 
재귀 메서드의 첫 번째 단계
You need to remember that you won’t have just one call, you’ll have several nested calls

Each call: str === "?"        	                  reverseString(str.subst(1))     + str.charAt(0)
1st call – reverseString("Hello")   will return   reverseString("ello")           + "h"
2nd call – reverseString("ello")    will return   reverseString("llo")            + "e"
3rd call – reverseString("llo")     will return   reverseString("lo")             + "l"
4th call – reverseString("lo")      will return   reverseString("o")              + "l"
5th call – reverseString("o")       will return   reverseString("")               + "o"

재귀 메서드의 두 번째 단계
The method hits the if condition and the most highly nested call returns immediately

5th call will return reverseString("") + "o" = "o"
4th call will return reverseString("o") + "l" = "o" + "l"
3rd call will return reverseString("lo") + "l" = "o" + "l" + "l"
2nd call will return reverserString("llo") + "e" = "o" + "l" + "l" + "e"
1st call will return reverserString("ello") + "h" = "o" + "l" + "l" + "e" + "h" 
*/
}
reverseString("hello");
```


## 주석을 생략한 코드
```javascript
function reverseString(str) {
  if (str === "")
    return "";
  else
    return reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```


## 조건부 삼항 연산자를 사용한 코드
```javascript
function reverseString(str) {
  return (str === '') ? '' : reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```

<strong>JavaScript에서 문자열을 반전시키기는</strong> 기술 면접에서 물어볼 수 있는 간단한 알고리즘 문제입니다. 비교적 쉬운 방법을 사용해 문제를 풀 수 있고, 재귀를 사용하거나 또는 더 복잡한 솔루션을 사용하는 등 다양한 접근 방식을 선택할 수 있습니다. 

제 글이 도움이 되셨기를 바랍니다. 이 기사는 freeCodeCamp 알고리즘 문제에 대한 "FCC 알고리즘 문제 해결하는 방법" 시리즈의 일부입니다. 이 시리즈에서는 알고리즘을 풀기 위해 몇 가지 해결책을 제안하고 프로그램이 어떻게 실행되는지를 단계별로 설명합니다.

<p>
    <a href="https://www.freecodecamp.org/news/three-ways-to-repeat-a-string-in-javascript-2a9053b93a2d/">
    <strong>JavaScript에서 문자열을 반복하는 세 가지 방법 [영문]</strong> </br>
    이 기사에서는 freeCodeCamp의 "Repeat a string repeat a string" 알고리즘 문제를 해결하는 방법을 설명합니다. 여기에는…
    </a>
</p>

<p>
    <a href="https://www.freecodecamp.org/news/two-ways-to-confirm-the-ending-of-a-string-in-javascript-62b4677034ac/">
    <strong>JavaScript에서 문자열의 끝을 확인하는 두 가지 방법 [영문]</strong> </br>
    이 기사에서는 freeCodeCamp의 "Confirm Ending" 알고리즘 문제를 해결하는 방법을 설명합니다.
    </a>
</p>

<p>
    <a href="https://www.freecodecamp.org/news/how-to-factorialize-a-number-in-javascript-9263c89a4b38/">
    <strong>JavaScript에서 숫자를 인수분해하는 세 가지 방법 [영문]</strong> </br>
    이 기사는 freeCodeCamp의 기본 알고리즘 작성법 "숫자 인수분해"튜토리얼을 기반으로 합니다. 
    </a>
</p>

<p>
    <a href="https://www.freecodecamp.org/news/two-ways-to-check-for-palindromes-in-javascript-64fea8191fd7/">
    <strong>JavaScript에서 회문(팰린드롬)을 확인하는 두 가지 방법 [영문]</strong> </br>
    이 기사는 freeCodeCamp의 기본 알고리즘 작성법의 "회문 확인" 튜토리얼을 기반으로 합니다.
    </a>
</p>

<p>
    <a href="https://www.freecodecamp.org/news/three-ways-to-find-the-longest-word-in-a-string-in-javascript-a2fb04c9757c/">
    <strong>JavaScript에서 문자열에서 가장 긴 단어를 찾는 세 가지 방법 [영문]</strong> </br>
    이 기사는 freeCodeCamp의 기본 알고리즘 작성법의 "회문 확인" 튜토리얼을 기반으로 합니다.
    </a>
</p>

<p>
    <a href="https://www.freecodecamp.org/news/three-ways-to-title-case-a-sentence-in-javascript-676a9175eb27/">
    <strong>JavaScript에서 문장을 타이틀 케이스(대문자화)하는 세 가지 방법 [영문]</strong> </br>
    이 기사는 freeCodeCamp의 기본 알고리즘 작성법의 "Title Case a Sentence" 튜토리얼을 기반으로 합니다.
    </a>
</p>

독자분들만의 솔루션이나 제안 사항이 있으면 아래 댓글란에 공유해주세요. 

[Medium](https://medium.com/@sonya.moisset), [Twitter](https://twitter.com/SonyaMoisset), [Github](https://github.com/SonyaMoisset) 또는 [LinkedIn](https://www.linkedin.com/in/sonyamoisset/) 에서 저를 팔로우할 수 있습니다. ;-)

#StayCurious, #KeepOnHacking & #MakeItHappen!

## 참고자료: 
- [`split()` 메서드 — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
- [`reverse()` 메서드 — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
- [`join()` 메서드 — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
- [`String.length` — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- [`substring()` 메서드 — MDN- ](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
- [`charAt()` 메서드 — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)