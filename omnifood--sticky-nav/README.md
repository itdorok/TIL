# **_sticky nav bar_**

```javascript
const sectionHeroEl = document.querySelector(".section-hero");

const obs = new IntersectionObserver(
  function (entries) {
    const ent = entries[0];
    if (ent.isIntersecting === false) {
      document.body.classList.add("sticky");
    }
    if (ent.isIntersecting === true) {
      document.body.classList.remove("sticky");
    }
  },
  {
    // In the viewport
    root: null,
    threshold: 0,
    rootMargin: "-80px",
  }
);
obs.observe(sectionHeroEl);
```

```css
.sticky .header {
  background-color: rgba(255, 255, 255, 0.972);
  position: fixed;
  top: 0;
  bottom: 0;
  width: 100%;
  height: 8rem;
  padding-top: 0;
  padding-bottom: 0;
  box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.03);
  z-index: 999;
}

.sticky .section-hero {
  margin-top: 9.6rem;
}
```
