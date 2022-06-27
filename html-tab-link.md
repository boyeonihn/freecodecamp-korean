#  HTML을 사용해 새 탭에서 링크를 여는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![파란, 보라, 초록색 총 세 개의 탭이 종이에 그려져 있다](https://cdn-media-2.freecodecamp.org/w1280/5f9c98dd740569d1a4ca1c7d.jpg)

영어 원문: [How to Use HTML to Open a Link in a New Tab](https://www.freecodecamp.org/news/how-to-use-html-to-open-link-in-new-tab/)
글쓴이: [Kris Koishigawa](https://www.freecodecamp.org/news/author/kris/)



### 브라우저 탭은 참 유용합니다. 탭은 여러 개의 온라인 작업을 동시에 수행하고 멀티태스킹하는 걸 가능하게 합니다. 

탭은 이제 매우 보편화되어서 링크를 클릭하면 새 탭에서 열릴 가능성이 높습니다.    

새 탭에서 링크를 열도록 하는 방법이 궁금하시다면 이 기사를 계속 읽어보시길 바랍니다!    

## <a> 앵커 요소 

웹 페이지에 하이퍼링크를 생성하려면 텍스트 혹은 그림 같은 요소를 앵커 요소(`<a>`)로 감싸고 연결하고 싶은 링크 URL를 `href` 속성에 설정해야 합니다.    




```

<p>Check out <a href="https://www.freecodecamp.org/">freeCodeCamp</a>.</p>


```

<p align="center">
    Check out <a href="https://www.freecodecamp.org/">freeCodeCamp</a>.
</p>


위의 링크를 클릭하면 브라우저가 현재 창 또는 탭에서 링크를 엽니다. 이것은 모든 브라우저의 기본 동작입니다.    

새 탭에서 링크를 열려면 앵커 요소의 다른 속성을 살펴봐야 합니다.   


## Target 속성 
이 속성은 브라우저가 하이퍼링크를 어떻게 열지를 설정합니다.    

새 탭에서 링크를 열도록 하려면, `target` 속성을 `_blank`으로 설정합니다.   

```
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank">freeCodeCamp</a>.</p>

```

이제 다른 사용자가 링크를 클릭하면 해당 사용자의 브라우저 설정에 따라 새 탭 또는 새 창에 링크가 열립니다.    


## `target="_blank"`의 보안 문제점     

`target` 속성을 사용하실 때마다 앵커 요소에 항상 `rel="noreferrer noopener"` 속성을 적용하는 것을 권장 드립니다: 


```
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>

```


출력되는 결과물은 다음과 같습니다: 

<p align="center">
    Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>..
</p>



`rel` 속성은 현 페이지와 링크된 URL 사이의 관계를 설정합니다. 이를 `noopener no refererer`로 설정하면 [탭 내빙](https://en.wikipedia.org/wiki/Tabnabbing)으로 알려진 피싱 유형을 방지할 수 있습니다.    


## 탭내빙 (tabnabbing)은 무엇인가요? 

역 탭내빙 (reverse tabnabbing)라고도 하는 탭내빙(tabnabbing)은 `target="_blank`와 함께 브라우저의 기본 동작을 사용해 `window.object` API를 통해 웹 페이지에 부분적으로 액세스하는 정보 탈취 공격 기술입니다.    

탭내빙을 사용하면 연결한 페이지가 가짜 로그인 페이지로 이동할 수 있습니다. 일반적으로 페이지의 원래 탭이 아니라 방금 열린 탭에 집중하기 때문에 대부분의 사용자가 이 문제를 알아차리지 못합니다. 그런 다음 사용자가 원래 페이지로 다시 전환하면 가짜 로그인 페이지가 대신 보이고 로그인 세부 정보를 입력할 수 있습니다.    

탭내빙이 어떻게 작동하고 어떻게 악용할 수 있는 것에 대해 더 알고 싶다면 [Alex Yumashev의 기사](https://www.jitbit.com/alexblog/256-targetblank---the-most-underestimated-vulnerability-ever/)와 [OWASP의 기사](https://owasp.org/www-community/attacks/Reverse_Tabnabbing)를 확인해 보십시오.

탭내빙의 안전한 적용 예시를 보고 싶다면, 이 [페이지](https://mathiasbynens.github.io/rel-noopener/)와 [해당 깃허브 레포](https://github.com/mathiasbynens/rel-noopener)를 통해 이 기법을 통한 정보 탈취 및 `rel` 속성에 대한 자세한 정보를 읽어보시길 바랍니다. 

## 요약 
HTML을 사용해 새 탭에서 링크를 여는 것은 매우 쉽습니다. 다음 세 가지 중요한 속성을 가진 앵커(`<a>`) 요소만 있으면 됩니다:

1. `href` 속성이 연결하고 싶은 페이지의 URL로 설정,
2. 브라우저의 설정에 따라 새로운 탭 또는 창에서 링크를 열도록 `target` 속성이 `_blank`로 설정,
3. 링크하는 페이지에서 발생할 수 있는 보안 공격을 방지하기 위해 `rel` 속성이 `noreferrer noopener`로 설정되어야 합니다. 


최종적으로 완성된 예시는 다음과 같습니다: 

```
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>
```

그 결과 브라우저에 다음과 같은 출력이 표시됩니다: 

<p align="center">
    Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>..
</p>

이 기사를 읽어주셔서 감사합니다. 즐겁게 코딩하시길 바랍니다.
