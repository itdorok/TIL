## 💡

# [Git] Github

```
1. fork
2. cloning
3. pull request
```

---

<br>

## 💡 fork

```
forking 한 repository가 내 repository로 복사된다.

단순히 다운로드 받으면 repository 생성 안됨
```

<img src="./img/forking.png" width="50%">

---

## 💡 cloning

```
forking한 repository를 local에 복제하는 것.
```

- terminal에서 clone하기
  <br>
  <img src="./img/terminalClone.png" width="50%" alt="terminal clone">
  <br>
- git clone(생성된 repository 주소 (닉네임: kokoa))
- code kokoa (이때 code command 설정 필수)

## 💡 pull request

```
cloning한 파일을 github에 업로드 한 뒤 원본 repository에 merge 요청 하는 것
```

## 💡 upstream, origin

```
fork해온 베이스 저장소의 마스터 브랜치와 연결되어 있다.

base repository의 최신 수정 사항을 origin branch로 fetch 할 수 있다.
```

<img src="./Git/4.21/img/upstream.png" width="50%">

---

# CLI

> Command Line Interface

```
1. log,commit,push
2. checkout and reset
3. hard/mixed/soft reset
4. checkout branches
5. commit --amend
6. ignoring files
7. origin
```

## 💡 git log

> running record of commits.

```
현재 작업중인 branch나 원격저장소를 알 수 있다.
```

## 💡 reset vs checkout

[checkout과 reset 설명 참조 👀](https://blog.naver.com/codeitofficial/222011693376)

```
<reset>

HEAD가 포인팅하는 브랜치가 가리키는 커밋을 바꾼다
```

```
<checkout>

HEAD가 브랜치에서 떨어져 나와
직접 다른 커밋/브랜치를 가리킨다
: detached branch
```

- git checkout (commit id)
  - git branch (branch's name)<br>
    : 원하는 커밋으로 돌아가서 브랜치 생성
- git checkout (commit id) **-b** (branch's name)

> **b**: 새로운 브랜치 생성 command

---

## 💡 reset 방법

> commit한 파일이 있다고 하자

```
hard : 변경사항 유지 안하고 돌아감
mixed : 파일을 untraked 영역에 둠
soft: 파일을 staging 단계에 둠
```

## 💡 checkout branches

```
현재 작업중인 브랜치를 바꿀 수 있음
```

## 💡 commit --amend

> 깜빡하고 업로드 못한 파일이 있는 경우

```
git add 변경한 파일
git commit --amend -m "" (혹은 --no-edit)
git push origin (branch's name)
```

🚨 **위와 같이 하면 오류 발생**

**--force**<br>

- amend는 전 단계로 돌아감 : 현재 브랜치와 origin의 브랜치의 단계가 달라짐
- reset/checkout처럼 강제 push 해야함

```
git add 변경 파일
git commit --amend -m "Amend commit"
git push origin (branche's name) --force
```

## 💡 Ignore files

```
<.gitignore> 파일안에 숨기고 싶은 파일명을 적으면 파일이 보이지 않는다
```

## 💡 Origin

```
git remote -v : 원격저장소 목록을 확인
git remote add (원격저장소 이름) <repo URL> : 원격저장소 추가
```
