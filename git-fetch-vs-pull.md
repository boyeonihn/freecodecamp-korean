# Git Fetch와 Git Pull 명령어의 차이점
#### 인보연 (Bo Yeon Ihn) 번역

![강아지가 물 속에서 막대기를 가져오면서 fetch 놀이하는 모습](https://cdn-media-2.freecodecamp.org/w1280/5f9c9e70740569d1a4ca3d14.jpg)

영어 원문: [Git Fetch vs Pull: What's the Difference Between the Git Fetch and Git Pull Commands?](https://www.freecodecamp.org/news/git-fetch-vs-pull/)

### Git pull과 fetch는 Git 사용자가 자주 사용하는 명령어입니다. 이 기사에서는 두 명령어의 차이점을 알아보겠습니다.

`pull`과 `fetch` 명령은 클론 저장소(clone repo)에서 작업할 때 사용할 가능성이 높습니다. 클론 저장소는 기존 저장소를 복제한 저장소이며, 다른 사람의 소스 코드의 복사본을 생성하는 것과 같습니다.  

기존 저장소에 적용된 변경 사항을 클론 저장소로 업데이트하려면 해당 변경 사항을 클론 저장소로 가져와야 합니다.  

이때 `fetch`와 `pull` 명령어가 매우 유용합니다.  

`git fetch`는 로컬 Git에 기존 원격 저장소에서 최신 메타데이터 정보를 확인하도록 지시하는 명령입니다. `fetch`는 원격 저장소에 변경사항이 있는지 확인만 하고 변경된 데이터를 로컬 Git에 가져오지 않습니다. 

반면 `git pull`은 원격 저장소에서 변경된 데이터를 로컬 Git에 가져오고 복사합니다.  

다음은 `pull` 명령을 사용하는 예시 구문입니다: 

```
git pull origin ankur bugfix
```

여기서 기억해야 할 것은 일반적으로 워크스테이션에 프로젝트 복사본이 세 개 이상 있다는 점입니다.

- 첫 번째 복사본은 사용자의 커밋 기록이 있는 사용자의 저장소입니다 (다시 말해, 이미 저장이 된 저장소). 
- 두 번째 복사본은 편집 및 작성 중이지만 사용자 저장소에 아직 커밋되지 않은 복사본입니다. 
- 세 번째 복사본은 원격 저장소의 로컬에 "캐시된 (cached)" 복사본입니다(복제된 원본일 가능성이 높습니다). 

`git fetch`를 사용하면 마지막 `pull` 이후 원격 저장소 또는 브랜치에 적용된 변경 사항을 확인할 수 있습니다. `pull`을 실행하면 현재 브랜치와 작업 복사본의 파일을 변경할 수 있으며 변경 내용이 손실될 수 있기 때문에 실행하기 전에 `fetch`로 확인하는 것이 유용합니다. 

```
git fetch    
git diff ...origin
```