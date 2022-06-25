# object

### **_Arrays_**

     다른 특징의 값이 모인 경우 구분하기 힘듦

```javascript
const friends = ["Michael", "Steven", "Jay"];

const me = ["suyeon", 26, "none", "Incheon"];
//어떤 값인지 알기 어려움
```

### **_Object_**

    Object는 key:value로 property를 작성하여 값의 이름을 특정할 수 있다.

```javascript
const jonas = {
  firstName: "jonas",
  lastName: "suyeon",
  age: 2022 - 1997,
  job: "none",
  friend: ["gaeul", "myself", "none"],
};
```

## **_Dot, Bracket notation_**

```javascript
object내의 값을 불러오는 방법

jonas.lastName // suyeon
jonas["friend"][0] //gaeul

```

    dot notation은 value의 이름을 바로 쓸 때 사용하고
    bracket은 값을 넣어서 사용할 때 쓴다
