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

- 


<br/>

# 

### 3. Merge (Recursive)
```
$ git checkout main
$ git merge -s recursive my-branch
```
<br/>

#

### 4. Squash & Merge


<br/>

#

### 5. Reabase & Merge

