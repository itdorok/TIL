## **_mobile nav bar_**

```
창의 크기가 줄어들면 상단의 navigation을 토글 형식으로 바꿔주어  layout의 효율을 늘린다.
```

<img src="https://user-images.githubusercontent.com/82014471/167984638-ca9746ae-57aa-49a2-b197-8fabb9158b38.gif" width="70%">

<br>

## **_💡 목표_**

```
창의 크기가 59em 일 때 nav-bar를 토글로 만들기
```

### 1. 토글 버튼 만들기

```html
<button class="btn-mobile-nav">
  <ion-icon class="icon-mobile-nav" name="menu-outline"></ion-icon>
  <ion-icon class="icon-mobile-nav" name="close-outline"></ion-icon>
</button>
```

```css
/* 창의 크기가 59em 이상일 때 토글 버튼 숨겨 놓기; */
.btn-mobile-nav {
  border: none;
  background-color: none;
  cursor: pointer;
  display: none;
}
/* 토글 버튼 보일 때 스타일링 */
.icon-mobile-nav {
  height: 4.8rem;
  width: 4.8rem;
  color: #333;
}
```

<br>

### 2. 모바일 버전 nav-bar 만들기

```css
@media (max-width: 59em) {
  .main-nav {
    background-color: rgba(255, 255, 255, 0.9);
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(5px);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.5s ease-in-out;
  }
}
```

### 3. 모바일 nav bar 숨기기

```css
.main-nav {
  /* view port 밖으로 보내기 */
  transform: translateX(100%);

  /* 눈에 보이지 않게 */
  opacity: 0;

  /* 마우스에 link가 눌리지 않게 */
  pointer-events: none;

  /* screen reader가 읽지 못하게 */
  visibility: hidden;
}
```

<br>

### 4. **_javascript_** 로 class 추가/삭제

```
CSS를 이용하는 interaction은 한계가 있다
js를 이용해서 class를 조작하면 사용자의 action에 따라 효과를 추가/삭제 할 수 있다
```

```javascript
// 토글 버튼을 누르면 .main-nav의 parent에 nav-open class추가
const btnNavEl = document.querySelector(".btn-mobile-nav");
const headerEl = document.querySelector(".header");
btnNavEl.addEventListener("click", function () {
  headerEl.classList.toggle("nav-open");
});
```

```css
/* mobile nav bar 화면 안으로 가져오기 */
.nav-open .main-nav {
  opacity: 1;
  pointer-events: auto;
  visibility: visible;
  transform: translateX(0);
}
```

```
.nav-open .main-nav:
nav-open class 를 가진 부모 element안에
main-nav class를 가진 자식 element를 가리킴

js가 header에 class를 추가하기 전에는 스타일 적용 불가
```

### 5. 토글 버튼 바꾸기

```css
/* 토글 버튼 꺼내기 */
.btn-mobile-nav {
  display: block;
  z-index: 1000;
}

/* 닫기 아이콘 활성화 */
.nav-open .icon-mobile-nav[name="close-outline"] {
  display: block;
}

/* 메뉴 아이콘 사라짐 */
.nav-open .icon-mobile-nav[name="menu-outline"] {
  display: none;
}
```

```
숨겼던 토글 버튼을 display: block으로 꺼내고
js로 nav-open이 추가되면서 mobile nav bar가 열리면

메뉴 버튼은 사라지고 닫기 아이콘만 나타난다.
```

### 6. 메뉴 끄기

```javascript
const allLinks = document.querySelectorAll("a:link");
allLinks.forEach(function (link) {
  if (link.classList.contains("main-nav-link"))
    headerEl.classList.toggle("nav-open");
});
```

---

## Safari issue

```
사파리 브라우저에서는 grid gap만 인정하고 flex gap은 적용되지 않는 이슈가 있다.

아래의 코드를 포함해서 문제를 해결한다.
```

```javascript
function checkFlexGap() {
  var flex = document.createElement("div");
  flex.style.display = "flex";
  flex.style.flexDirection = "column";
  flex.style.rowGap = "1px";

  flex.appendChild(document.createElement("div"));
  flex.appendChild(document.createElement("div"));

  document.body.appendChild(flex);
  var isSupported = flex.scrollHeight === 1;
  flex.parentNode.removeChild(flex);
  console.log(isSupported);

  if (!isSupported) document.body.classList.add("no-flexbox-gap");
}
checkFlexGap();
```

```css
.no-flexbox-gap .main-nav-list li:not(:last-child) {
  margin-right: 4.8rem;
}

.no-flexbox-gap .list-item:not(:last-child) {
  margin-bottom: 1.6rem;
}

.no-flexbox-gap .list-icon:not(:last-child) {
  margin-right: 1.6rem;
}

.no-flexbox-gap .delivered-faces {
  margin-right: 1.6rem;
}

.no-flexbox-gap .meal-attribute:not(:last-child) {
  margin-bottom: 2rem;
}

.no-flexbox-gap .meal-icon {
  margin-right: 1.6rem;
}

.no-flexbox-gap .footer-row div:not(:last-child) {
  margin-right: 6.4rem;
}

.no-flexbox-gap .social-links li:not(:last-child) {
  margin-right: 2.4rem;
}

.no-flexbox-gap .footer-nav li:not(:last-child) {
  margin-bottom: 2.4rem;
}

@media (max-width: 75em) {
  .no-flexbox-gap .main-nav-list li:not(:last-child) {
    margin-right: 3.2rem;
  }
}

@media (max-width: 59em) {
  .no-flexbox-gap .main-nav-list li:not(:last-child) {
    margin-right: 0;
    margin-bottom: 4.8rem;
  }
}
```
