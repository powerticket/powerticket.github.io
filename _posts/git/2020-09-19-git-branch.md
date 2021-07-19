---
layout: post
title: "Git branch"
date: 2020-09-19 17:00:00 +0900
categories: [Git, branch]
tags: [git, github]
---





[Git 기초](../git)에서 git을 통해 버전을 관리하는 방법에 대해서 알아보았다. 이번에는 master가 아닌 branch를 통해서 세부적인 기능, 버전에 따라서 관리할 수 있는 방법에 대해서 알아보자. 



![img](https://blog.kakaocdn.net/dn/cRPkVU/btquUBRb7GK/bGy8lytovCtjsoP9SZKTJ0/img.jpg)



## Master & Branch

Master는 프로젝트의 가장 중요한 중심 프로그램이다. Branch는 Git에서 협업하기 위한 코드의 분기를 의미한다.



### Command

`git branch`: 지금까지 생성된 branch의 목록을 확인할 수 있다.

`git branch branch_name`: 새로운 branch를 생성한다. 프로젝트에 규정에 따라 다르지만 일반적으로 기능, 또는 버전별로 작성한다.

`git switch branch_name`: 해당 branch로 이동한다.

`git checkout -b branch_name`: 새로운 branch를 생성하고 바로 해당 branch로 이동한다.

`git branch -d branch_name`: 해당 branch를 삭제한다. 해당 branch로 이동된 상태에서는 불가능하다.
`git log --oneline --all --graph`: commit log를 한 줄로 확인할 수 있는 명령어로, `--all` 옵션을 통해 해당 branch가 coomit된 시점 이후의 다른 branch commit 기록을 확인할 수 있고, `--graph` 옵션을 통해 보다 시각적으로 확인이 가능하다.



## Merge

`git merge branch_name`: 해당 branch의 내용을 병합하는 명령어이다. 병합해서 완전한 코드를 만들고자하는 branch의 위치(주로 master)에서 실행한다. 단순 하나의 branch를 합칠 경우, Fast-forward 방식으로 병합되게 된다. 병합 후, 필요없는 branch는 삭제한다.



### Merge condition

1. branch 분기 이후 master의 commit이 없을 때, Fast-forward 방식으로 merging 한다.
2. branch 분기 이후 master의 commit이 있지만 code의 충돌이 없을 때, recursive 방식으로 Auto-merging 한다.
3. branch 분기 이후 master의 commit이 있고, code의 충돌이 있을 때, 충돌된 부분을 보여주고 직접 수정하여 merging 한다. 자동으로 병합되지 않으므로 수정 후, 다시 commit 한다.

![image-20200918103638842](C:\Users\jeon\git\powerticket.github.io\_posts\git\2020-09-19-git-branch.assets\image-20200918103638842.png)
