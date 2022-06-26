# Git 로컬 브랜치 이름 변경하는 방법
#### 인보연 (Bo Yeon Ihn) 번역

![나뭇가지가 가득한 나무](https://www.freecodecamp.org/news/content/images/size/w2000/2021/11/mila-tovar-NTiW908Uc1A-unsplash.jpg)

영어 원문: [Git Rename Branch – How to Change a Local Branch Name](https://www.freecodecamp.org/news/git-rename-branch-how-to-change-a-local-branch-name/)   
원문 글쓴이: [Jessica Wilkins](https://www.freecodecamp.org/news/author/jessica-wilkins/)


### 프로젝트 개발하는 동안 로컬 브랜치의 이름을 변경해야 할 경우가 있습니다. 

이 기사에서는 Git에서 로컬 브랜치 이름을 변경하는 두 가지 방법을 제공하겠습니다.    


## Git 브랜치 이름 변경하기 첫 번째 방법
### 1. 프로젝트 루트 폴더에 있는지 확인하기 

먼저 터미널을 연 다음 프로젝트의 루트 폴더로 `cd` (change directory 경로 변경)를 해야 합니다.    

예를 들어 홈 디렉터리에서 바탕 화면에 위치한 프로젝트로 `cd` 경로 이동을 할 경우 사용하는 명령은 다음과 같습니다.


```
cd Desktop/project-name 

```

다음은 디렉터리를 Happy_Messages_Bot라는 프로젝트 폴더로 변경하는 예입니다.    

![프로젝트 폴더로 경로 이동하는 명령](https://www.freecodecamp.org/news/content/images/2021/11/Screen-Shot-2021-11-02-at-10.30.01-PM.png)


### 2. 이름 변경하고 싶은 브랜치로 이동하기 
`git checkout` 명령을 이용해 다른 브랜치로 이동할 수 있습니다. 

```
git checkout branch-name 
```

주어진 예시에서는 필자가 생성한 `test-branch` 브랜치로 전환하려고 합니다.    

![test-branch 브랜치로 전환하는 명령](https://www.freecodecamp.org/news/content/images/2021/11/Screen-Shot-2021-11-02-at-10.39.57-PM.png)    


### 3. `-m` 옵션을 사용해 브랜치 이름 변경하기 

브랜치 이름을 변경하는 명령은 다음과 같습니다:    


```
git branch -m new-branch-name
```


다음 예시에서는 브랜치 이름을 `test-branch`에서 `test-branch2`로 변경하려고 합니다.     

```
git branch -m test-branch2

```

`git status`를 이용해 새로 변경된 브랜치 이름을 확인할 수 있습니다.    


![변경된 브랜치 이름을 확인하는 터미널 스크린샷](https://www.freecodecamp.org/news/content/images/2021/11/Screen-Shot-2021-11-02-at-10.52.02-PM.png)




## Git 브랜치 이름 변경하기 두 번째 방법
`git checkout`을 사용하지 않고도 한 번의 명령으로 로컬 브랜치의 이름을 변경할 수 있습니다.    

### 1. master/main 브랜치에 위치해 있는지 확인하기    
마스터/메인 브랜치에 있는지 확인하려면 `git status`를 실행합니다.    

![git status 실행하는 터미널](https://www.freecodecamp.org/news/content/images/2021/11/Screen-Shot-2021-11-02-at-11.02.20-PM.png)


마스터/메인 브랜치에 없는 경우 `git checkout master` 또는 `git checkout main`을 실행해야 합니다.    

![git checkout 명령으로 마스터 브랜치로 이동하기](https://www.freecodecamp.org/news/content/images/2021/11/Screen-Shot-2021-11-02-at-11.05.28-PM.png)


### 2. -m 옵션을 이용해 브랜치 이름 변경하기 
다음 구문을 사용해 브랜치의 이름을 새로 변경할 수 있습니다. 

```
git branch -m old-branch new-branch

```

브랜치 이름을 `test-branch`에서 `test-branch2`로 변경하는 방법은 다음과 같습니다:     

```
git branch -m test-branch test-branch2

```
새 브랜치 이름을 보려면 모든 브랜치를 나열하는 `git branch`를 실행할 수 있습니다.    


![git branch 명령 실행하는 터미널](https://www.freecodecamp.org/news/content/images/2021/11/Screen-Shot-2021-11-02-at-11.15.52-PM.png)


이렇게 이 기사에서는 Git 로컬 브랜치 이름을 변경하는 방법 두 가지를 짚어봤습니다. 



영어 원문을 읽고 싶으시다면 [Git Rename Branch – How to Change a Local Branch Name](https://www.freecodecamp.org/news/git-rename-branch-how-to-change-a-local-branch-name/) 를 읽어보세요. 
