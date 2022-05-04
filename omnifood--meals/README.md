# Featured-in section

<img src="featured-in.png">

```
display publication's logo
```

## 💡 filter

```css
.feature {
  filter: brightness(0);
}
```

```
로고의 다양한 색을 "균일"하게 회색으로 바꿔준다

이외에도
√blur()
√hue-rotate() 등이 있음
```

# How it works section

```
√ z pattern 이용
√ img, text 등이 포함
√ product, sevice 의 자세한 정보 전달
```

## 💡 :: before / :: after

```
element를 html에 직접 만들지 않고 pseudo class 로 만드는 방법

주로 position을 통해 위치 조정
```

```css
.step-img-box::before,
.step-img-box::after {
  display: block;
  content: "";
}
```

```
content가 비어있다면 padding, margin 적용을 위해서 display: block 선언 필수
```

# Meals section

## **_translate_**

## **_transition_**

## **_box-shadow_**

```
√ float card when it's hovered
√ make effect natural using transition
√ add details using box-shadow
```

```css
.meal {
  box-shadow: 0 2.4rem 4.8rem rgba(0, 0, 0, 0.075);
  transition: all 0.4s;
}

.meal:hover {
  transform: translateY(-1.2rem);
  box-shadow: 0 3.2rem 6.4rem rgba(0, 0, 0, 0.06);
}
```

**_🚨 카드가 위로 움직이면_**
<br>

- 그림자는 연하고 더 번지게
- translateY()로 Y축만 움직이게
- transition으로 자연스럽게

---

## 💡 Underline vs Border-bottom

기본 text-decoration: underline은 text와 밑줄 간격을 바꿀 수 없음

```css
span {
  border-bottom: 1px solid #333;
  padding-bottom: 0.4rem;
}
```

#### + currentColor

```
텍스트 색을 바꿀 때마다 border의 색도 수정하는 문제 해결
```

```css
link:link,
link:visited {
  border: 1px solid currentColor;
}
```

#### + transparent

```
:hover 했을 때 border: none 이면 border-width 손실로 페이지 전체가 움직이는 문제 해결
```

```css
link:hover,
link:active {
  border: 1px solid transparent;
}
```

# Testimonials section

```
* figure
* blockquote
* grid template fr unit
* overflow: hidden
```

## 💡 figure

```
self-contained content, like illustrations, diagrams, photos, code listings, etc
```

figure tag에 img와 blockquote를 넣어
개인마다 각각의 figure을 갖도록 함

## 💡 fr unit

```css
grid-template-columns: 40fr 60fr;
```

```
숫자의 크기를 키워서 다양하게 크기조정 가능
```

## 💡 overflow: hidden

```
transform: scale(1.2)로 크기가 커진 element는 주변에 영향을 끼치고 지저분해 보임

img container에 overflow: hidden 설정

사진이 정해진 범위에서 가까이 다가오는 효과
```
