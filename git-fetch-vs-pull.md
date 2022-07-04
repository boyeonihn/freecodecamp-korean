# Git Fetch와 Git Pull 명령어의 차이점
#### 인보연 (Bo Yeon Ihn) 번역

![강아지가 물 속에서 막대기를 가져오면서 fetch 놀이하는 모습](https://cdn-media-2.freecodecamp.org/w1280/5f9c9e70740569d1a4ca3d14.jpg)

영어 원문: [Git Fetch vs Pull: What's the Difference Between the Git Fetch and Git Pull Commands?](https://www.freecodecamp.org/news/git-fetch-vs-pull/)

### Git pull and fetch are two commands that are regularly used by Git users. Let’s see the difference between both commands.

For the sake of context, it’s worth remembering that we’re probably working in a clone repo. What’s a clone? It's simply a duplicate of another repository. It is basically getting your own copy of someone else’s source code.

That said, to keep your clone updated with whatever changes may have been applied to the original, you’ll need to bring those to your clone.

이때 `fetch`와 `pull` 기능이 매우 유용합니다. 
That’s where `fetch` and `pull` come in.

`git fetch` is the command that tells your local git to retrieve the latest meta-data info from the original (yet doesn’t do any file transferring. It’s more like just checking to see if there are any changes available).

`git pull` on the other hand does that AND brings (copy) those changes from the remote repository.

For example:

```
git pull origin ankur bugfix
```

The takeaway is to keep in mind that there generally are at least three copies of a project on your workstation.

- One copy is your own repository with your own commit history (the already saved one, so to say).
- The second copy is your working copy where you are editing and building (not committed yet to your repo).
- The third copy is your local “cached” copy of a remote repository (probably the original from where you cloned yours).

You can use `git fetch` to know the changes done in the remote repo/branch since your last pull. This is useful to allow for checking before doing an actual pull, which could change files in your current branch and working copy (and potentially lose your changes, etc).

```
git fetch    
git diff ...origin
```