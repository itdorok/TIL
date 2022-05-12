# **_Smooth scroll_**

## 1. scroll-behavior : smooth

```css
.link:link,
.link:visited {
  scroll-behavior: smooth;
}
```

**_Safari에서 구동이 안됨_**

<br>

---

## 2. javascript heck

```javascript
const allLinks = document.querySelectorAll("a:link");
allLinks.forEach(function (link) {
  link.addEventListener("click", function (e) {
    e.preventDefault();
    const href = link.getAttribute("href");

    // scroll back to top
    if (href === "#")
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    // scroll into specific view point
    if (href !== "#" && href.startsWith("#")) {
      const sectionEl = document.querySelector(href);
      sectionEl.scrollIntoView({ behavior: "smooth" });
    }
  });
});
```

```html
<script
  defer
  src="https://unpkg.com/smoothscroll-polyfill@0.4.4/dist/smoothscroll.min.js"
></script>
```
