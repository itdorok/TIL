# [Git] Basic Git concepts

## 💡 what is Git and GitHub?

> **`Git`: 버전 관리 시스템 (Version Control System)** > **`GitHub`: 깃 레포지토리 저장소 (cloud-based hosting service)**

<br>

## 💡 repository

> **`.git/ folder inside a project`
> tracking all changes made to files in project**<br><br>
> if delete .git/ folder, you delete your project’s history.

<br>

## 💡 Commit

> **capturing a `snapshot of` the project's currently staged `changes`**

<br>

## 💡 Areas

> **`Working Area (untracked files)`**<br>
> local directory에서 존재하며 delete,edit,create 등의 활동이 일어나는 곳을 의미한다
> 이때 git은 이 파일을 tracking하지 않는다

> **`Staging Area (= index, cache)`**<br>
> 다음 커밋에 포함될 파일이 있는 곳이다.
> git은 최근의 commit과 새로 commit될 파일 간의 차이를 tracking한다.

> **`Repository`**<br>
> commit된 파일의 snapshot을 가지고 있다. working, staging area가 본래 어땠는지 알 수 있다.

<br>

---

## Branches

![Branch image](https://i.stack.imgur.com/83JeN.png "branch image")

> **`has seperate timeline`**

> **`has all the histories of a main brach`**

> **`update main branch's changes to the branch`**

> **`merge branches to main branch`**

<br>

---

## conflicts in Branches

<br><br>

### [Editing same line on two branches]

![Editing main](./img/mainChange.png "line1 editing")
![Editing branch](./img/branchChange.png "line1 editing")

### [conflict occured]

![you can’t continue merge unless solve the conflict](./img/conflictAlert.png "1 conflict")
you can’t continue merge unless solve the conflict

<br>

### [VScode]

![VScode gives you options](./img/vscode.png "vscode page snapshot when solving conflicts")

> **`Solve conflicts` by choosing one option out of four**
