# Responsive design ingredients

<img src="responsive.jpeg" width="50%">

## ๐ก FLUID LAYOUT

```
- content๊ฐ ํ์ฌ view port์ ๋๋น์ ๋ง์ถฐ์ง๋๋ก ํ๊ธฐ
- px ๋์  % ์ฌ์ฉ
- width ๋์  max-width ์ฌ์ฉ
```

#### + max-width

```
view port width = A
content max-width = B


A > B = B
A < B = A
```

## ๐ก RESPONSIVE UNITS

```
rem = html font-size = by default 16px
```

```css
.container{
  width: 50rem;      (800px)
  padding: 2rem;     (32px)
  font-size: 1rem;   (16px)
}
```

---

#### + Trick 1

```css
html {
  font-size: 10px;
}
```

#### + Trick 2

```css
html {
  (10px / 1rem = 10/16 = 0.625 = 62.5%)
  font-size: 62.5%
}
```

default font-size ๊ฐ ๋ฐ๋์ด๋ %๋ก ์ ๊ธฐ์ ์ธ font-size ์ค์  ๊ฐ๋ฅ

---

## ๐ก FLEXIBL IMAGES

```
px ๋์  % + max-width ๋ก ํฌ๊ธฐ ์ง์ 
```

## ๐ก MEDIA QUERIES
