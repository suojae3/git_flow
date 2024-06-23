출처 링크 <br/>
[https://hudi.blog/git-merge-squash-rebase/](https://hudi.blog/git-merge-squash-rebase/)

<br/>
<br/>

##  Git의 다양한 브랜치 병합 방법

<br/>

### 1. Merge 

```
$ git checkout main
$ git merge my-branch
```

<img src="https://github.com/suojae3/git_study/assets/126137760/edee94c7-84fa-425c-9085-3b277f65c806" width="300">

<br/>
<br/>

- 커밋이력을 모두 남길 때 사용
- Merge는 두가지 종류 (FF, R)가 있음
- 머지 명령어 디폴트는 recursive로 설정되어있음

<br/>

#

### 2. Merge (Fast-Forward)

```
$ git checkout main
$ git merge --ff-only my-branch
```

<img width="450" alt="image" src="https://github.com/suojae3/git_study/assets/126137760/010db95d-b2ca-4da4-bb24-425e9819419c">


<br/>
<br/>

- 메인 브랜치에서 아무작업이 쌓인게 없고, 분기한 브랜치에서만 작업을 이어나간 상태라면 FF를 통해 메인 브랜치에 합쳐줄 수 있다.

<br/>

# 

### 3. Merge (Recursive)
```
$ git checkout main
$ git merge -s recursive my-branch
```

<img width="450" alt="image" src="https://github.com/suojae3/git_study/assets/126137760/f9508b9c-ea80-4db9-bef5-313e7a70e088">

<br/>
<br/>

- 메인에서 분기된 이후에 메인과 분기된 브랜치 모두 커밋기록이 쌓였다면 두부분의 공통분모인 머지커밋을 만들어준다.

<br/>

#

### 4. Squash & Merge
```
$ git checkout main
$ git merge --squash my-branch
$ git commit -m "squash & merge"
```
<img width="450" alt="image" src="https://github.com/suojae3/git_study/assets/126137760/d85e834e-177a-4a5c-886e-c77af5300853">

<br/>
<br/>

-  분기된 브랜치에 커밋이 여러개 쌓인 상태에서 `squash`를 하게되면 분기된 브랜치의 커밋이 하나의 커밋으로 합쳐져 메인에 합쳐진 커밋 하나를 올린다. (모든 이력이 하나의 커밋으로 퉁쳐질 수 있기에 주의하자)

<br/>

#

### 5. Reabase & Merge

```dart
$ git checkout my-branch
$ git rebase main
$ git checkout main
$ git merge my-branch
```

<img width="450" alt="image" src="https://github.com/suojae3/git_study/assets/126137760/5d161e75-d233-416c-aea9-a02ac3a40c09">

<br/>
<br/>

- rebase는 단어 그대로 메인에다 베이스를 다시 두는것, 즉 분기된 브랜치의 커밋들이 메인에 붙고 분기되었었던 브랜치는 사라진다.
- 주의할 점은 브랜치가 사라지기 때문에 커밋해쉬넘버가 사라진다.

<br/>

#

### Merge 팁
- `feature` 에서 `develop` 으로 머지할 대는 `squash`가 유용. 기능개발을 위해 했던 커밋들을 깔끔하게 하나로 정리
- `develop` 에서 `main` 으로 머지할 때는 rebase가 적합 
