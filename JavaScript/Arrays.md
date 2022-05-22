# Arrays

## **_필요성?_**

```javascript
const friend1 = "Michael";
const friend2 = "Jay";
const friend3 = "Mike";

console.log(friend1);
console.log(friend2);
console.log(friend3);
```

    value를 저장,수정,삭제,불러올 때 반복을 피할 수 없고 버그 가능성이 높아짐

```javascript
const friends = ["Michael", "Steven", "Peter"];

const year = new Array("Michael", "Steven", "Peter");

console.log(friends[0]);
console.log(friends[1]);
console.log(friends[2]);
```

    두 가지 방법으로 만들 수 있고 0부터 index가 매겨짐

## **_push,pop / unshift, shift_**

<br>

### 추가

```javascript
const friends = ["Michael", "Steven", "Peter"];

friends.push("jay");

friends.unshift("john");
```

삭제

```javascript
friends.pop();

friends.shift();
```

    삭제는 value를 지정하지 않아도 자동으로 양끝의 값을 지운다

## **_indexOf, includes_**

```javascript
console.log(friends.indexOf("Steven")); // 0

console.log(friends.includes("Steven")); // true
```

### + includes

    strict equality, no type coercion

```javascript
const num = [23, 108, 2037 - 1997];

console.log(push.includes("23"); // false
```

    === operator처럼 strict equality로서 type이 같아야 한다.
