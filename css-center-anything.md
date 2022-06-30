#  CSS로 모든 요소(div, 텍스트)를 중앙 정렬하는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![분홍색 배경에 잘려진 아보카도 반 쪽이 정중앙에 있다](https://cdn-media-2.freecodecamp.org/w1280/5f9c98dd740569d1a4ca1c7d.jpg)

영어 원문: [How to Center Anything with CSS - Align a Div, Text, and More](https://www.freecodecamp.org/news/how-to-center-anything-with-css-align-a-div-text-and-more/)
글쓴이: [Kris Koishigawa](https://www.freecodecamp.org/news/author/kris/)


### 요소를 중앙 정렬하는 것은 CSS의 가장 어려운 측면 중 하나입니다.

방법 자체는 일반적으로 이해하기 어렵지 않지만, 중앙 정렬하는 방법이 너무 많다는 점이 어렵습니다.    

중앙 정렬하려는 HTML 요소가 무엇인지, 가로 또는 세로 방향으로 중앙 정렬하는 여부에 따라 사용하는 방법이 달라질 수 있습니다.    

이 튜토리얼에서는 여러 요소를 수평 중앙, 수직 중앙, 또는 수평-수직 모두 중앙 정렬하는 방법에 대해 설명합니다. 

## 수평으로 가운데 맞추는 방법

요소를 수평으로 중앙 정렬하는 것이 일반적으로 수직으로 중앙에 맞추는 것보다 쉽습니다. 다음은 수평으로 중앙에 배치할 수 있는 몇 가지 일반적인 요소와 이를 수행하는 다양한 방법입니다.

요소의 중심을 수평으로 맞추는 것은 일반적으로 수직 방향으로 맞추는 것보다 쉽습니다. 다음은 수평으로 중심을 잡고자 하는 몇 가지 일반적인 요소와 여러 가지 방법을 보여 줍니다.

```html
<p>Check out <a href="https://www.freecodecamp.org/">freeCodeCamp</a>.</p>
```

<p align="center">
    Check out <a href="https://www.freecodecamp.org/">freeCodeCamp</a>.
</p>


위의 링크를 클릭하면 브라우저가 현재 창 또는 현재 탭에서 링크를 엽니다. 이것은 모든 브라우저의 기본 동작입니다.    

새 탭에서 링크를 열려면 앵커 요소의 다른 속성을 살펴봐야 합니다.   


## Target 속성 
이 속성은 브라우저가 하이퍼링크를 어떻게 열지를 설정합니다.    

새 탭에서 링크를 열도록 하려면, `target` 속성을 `_blank`로 설정합니다.   

```html
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank">freeCodeCamp</a>.</p>
```

이제 다른 사용자가 링크를 클릭하면, 해당 사용자의 브라우저 설정에 따라 새 탭 또는 새 창에서 링크가 열립니다.    


## `target="_blank"`의 보안 문제점     

`target` 속성을 사용할 때마다 앵커 요소에 항상 `rel="noreferrer noopener"` 속성을 적용하는 것을 권장드립니다: 


```html
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>
```


출력되는 결과물은 다음과 같습니다: 

<p align="center">
    Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.
</p>



`rel` 속성은 현 페이지와 링크된 URL 사이의 관계를 설정합니다. 이를 `noopener norefererer`로 설정하면 [탭내빙](https://en.wikipedia.org/wiki/Tabnabbing)으로 알려진 피싱 공격을 막을 수 있습니다.   


## 탭내빙(tabnabbing)은 무엇인가요? 

'역 탭내빙(reverse tabnabbing)'이라고도 하는 '탭내빙(tabnabbing)'은 `window.object` API를 통해 당신의 웹 페이지에 부분적으로 접근하기 위해서 `target="_blank"`와 브라우저의 기본 동작을 이용하는 취약점 공격(exploit)입니다.

탭내빙을 사용하면, 연결한 페이지로 인해 당신의 페이지가 가짜 로그인 페이지로 재접속될 수 있습니다. 일반적으로 원래 탭이 아니라 방금 열린 탭에 집중하기 때문에 대부분의 사용자가 이 문제를 알아차리지 못합니다. 그런 다음 사용자가 원래 페이지로 다시 돌아오면 당신의 페이지 대신 가짜 로그인 페이지를 보게 될 것이고, 사용자는 가짜 로그인 페이지에 로그인 정보를 입력할지도 모릅니다.

탭내빙이 어떻게 작동하고 악의적인 행위자가 취약점 공격으로 무엇을 할 수 있는지 더 알고 싶다면 [Alex Yumashev의 기사](https://www.jitbit.com/alexblog/256-targetblank---the-most-underestimated-vulnerability-ever/)와 [OWASP의 기사](https://owasp.org/www-community/attacks/Reverse_Tabnabbing)를 확인해 보십시오.

탭내빙의 안전한 적용 예시를 보고 싶다면, 이 [페이지](https://mathiasbynens.github.io/rel-noopener/)와 [해당 깃허브 레포](https://github.com/mathiasbynens/rel-noopener)를 통해 취약점 공격 및 `rel` 속성에 대한 자세한 정보를 읽어보시길 바랍니다. 

## 요약 
HTML을 사용해 새 탭에서 링크를 여는 것은 매우 쉽습니다. 다음 세 가지 중요한 속성을 가진 앵커(`<a>`) 요소만 있으면 됩니다:

1. `href` 속성을 연결하고 싶은 페이지의 URL로 설정,
2. 브라우저의 설정에 따라 새 탭 또는 새 창에서 링크를 열도록 `target` 속성을 `_blank`로 설정,
3. 링크한 페이지에서 발생할 수 있는 보안 공격을 방지하기 위해 `rel` 속성을 `noreferrer noopener`로 설정해야 합니다. 


최종적으로 완성된 예시는 다음과 같습니다: 

```html
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>
```

그 결과 브라우저에 다음과 같은 출력이 표시됩니다: 

<p align="center">
    Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.
</p>

이 기사를 읽어주셔서 감사합니다. 즐겁게 코딩하시길 바랍니다.
