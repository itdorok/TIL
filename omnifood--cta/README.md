# CTA section

```
call-to-action section: 사용자가 어떤 행동을 하도록 만드는 영역
```

## 💡 input element

```
사용자에게 입력을 받을 수 있음
data 전송을 위해 form 태그 action attribute 필수

```

```html
<form action="#">
  <input class="user-name" type="text" required />
</form>
```

### + type

- text
- email
- password ...

### + attributes

- required
- placeholder ...

---

## 💡 select element

```html
<label for="select-where">Where did hear from us?</label>
<select id="select-where" required>
  <option value="">Please choose one option:</option>
  <option value="friends">Friends and family</option>
  <option value="youtube">YouTube video</option>
</select>
```

```
drop down 방식으로 선택지를 제공
```

---

### **_label_**

입력 받는 형식을 정의
<br> 정의하는 형식의 id를 for의 value로 입력
<br> label 클릭시 입력창 활성화

---

### **_value_**

사용자가 입력한 값,
<br>form으로 전송되는 data 이름

```
예) 사용자가 이름 입력 > 김수연 > 'user-name: 김수연'  전송
```
