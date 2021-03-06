## ๐ก

# [Git] Github

```
1. fork
2. cloning
3. pull request
```

---

<br>

## ๐ก fork

```
forking ํ repository๊ฐ ๋ด repository๋ก ๋ณต์ฌ๋๋ค.

๋จ์ํ ๋ค์ด๋ก๋ ๋ฐ์ผ๋ฉด repository ์์ฑ ์๋จ
```

<img src="./img/forking.png" width="50%">

---

## ๐ก cloning

```
forkingํ repository๋ฅผ local์ ๋ณต์ ํ๋ ๊ฒ.
```

- terminal์์ cloneํ๊ธฐ
  <br>
  <img src="./img/terminalClone.png" width="50%" alt="terminal clone">
  <br>
- git clone(์์ฑ๋ repository ์ฃผ์ (๋๋ค์: kokoa))
- code kokoa (์ด๋ code command ์ค์  ํ์)

## ๐ก pull request

```
cloningํ ํ์ผ์ github์ ์๋ก๋ ํ ๋ค ์๋ณธ repository์ merge ์์ฒญ ํ๋ ๊ฒ
```

## ๐ก upstream, origin

```
forkํด์จ ๋ฒ ์ด์ค ์ ์ฅ์์ ๋ง์คํฐ ๋ธ๋์น์ ์ฐ๊ฒฐ๋์ด ์๋ค.

base repository์ ์ต์  ์์  ์ฌํญ์ origin branch๋ก fetch ํ  ์ ์๋ค.
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

## ๐ก git log

> running record of commits.

```
ํ์ฌ ์์์ค์ธ branch๋ ์๊ฒฉ์ ์ฅ์๋ฅผ ์ ์ ์๋ค.
```

## ๐ก reset vs checkout

[checkout๊ณผ reset ์ค๋ช ์ฐธ์กฐ ๐](https://blog.naver.com/codeitofficial/222011693376)

```
<reset>

HEAD๊ฐ ํฌ์ธํํ๋ ๋ธ๋์น๊ฐ ๊ฐ๋ฆฌํค๋ ์ปค๋ฐ์ ๋ฐ๊พผ๋ค
```

```
<checkout>

HEAD๊ฐ ๋ธ๋์น์์ ๋จ์ด์ ธ ๋์
์ง์  ๋ค๋ฅธ ์ปค๋ฐ/๋ธ๋์น๋ฅผ ๊ฐ๋ฆฌํจ๋ค
: detached branch
```

- git checkout (commit id)
  - git branch (branch's name)<br>
    : ์ํ๋ ์ปค๋ฐ์ผ๋ก ๋์๊ฐ์ ๋ธ๋์น ์์ฑ
- git checkout (commit id) **-b** (branch's name)

> **b**: ์๋ก์ด ๋ธ๋์น ์์ฑ command

---

## ๐ก reset ๋ฐฉ๋ฒ

> commitํ ํ์ผ์ด ์๋ค๊ณ  ํ์

```
hard : ๋ณ๊ฒฝ์ฌํญ ์ ์ง ์ํ๊ณ  ๋์๊ฐ
mixed : ํ์ผ์ untraked ์์ญ์ ๋ 
soft: ํ์ผ์ staging ๋จ๊ณ์ ๋ 
```

## ๐ก checkout branches

```
ํ์ฌ ์์์ค์ธ ๋ธ๋์น๋ฅผ ๋ฐ๊ฟ ์ ์์
```

## ๐ก commit --amend

> ๊น๋นกํ๊ณ  ์๋ก๋ ๋ชปํ ํ์ผ์ด ์๋ ๊ฒฝ์ฐ

```
git add ๋ณ๊ฒฝํ ํ์ผ
git commit --amend -m "" (ํน์ --no-edit)
git push origin (branch's name)
```

๐จ **์์ ๊ฐ์ด ํ๋ฉด ์ค๋ฅ ๋ฐ์**

**--force**<br>

- amend๋ ์  ๋จ๊ณ๋ก ๋์๊ฐ : ํ์ฌ ๋ธ๋์น์ origin์ ๋ธ๋์น์ ๋จ๊ณ๊ฐ ๋ฌ๋ผ์ง
- reset/checkout์ฒ๋ผ ๊ฐ์  push ํด์ผํจ

```
git add ๋ณ๊ฒฝ ํ์ผ
git commit --amend -m "Amend commit"
git push origin (branche's name) --force
```

## ๐ก Ignore files

```
<.gitignore> ํ์ผ์์ ์จ๊ธฐ๊ณ  ์ถ์ ํ์ผ๋ช์ ์ ์ผ๋ฉด ํ์ผ์ด ๋ณด์ด์ง ์๋๋ค
```

## ๐ก Origin

```
git remote -v : ์๊ฒฉ์ ์ฅ์ ๋ชฉ๋ก์ ํ์ธ
git remote add (์๊ฒฉ์ ์ฅ์ ์ด๋ฆ) <repo URL> : ์๊ฒฉ์ ์ฅ์ ์ถ๊ฐ
```
