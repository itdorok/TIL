# Destructuring

    JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

## **_Destructuring Array_**

```javascript
const arr = [2, 3, 4];
const a = arr[0];
const b = arr[1];
const c = arr[2];

//destructuring
const [x, y, z] = arr;
console.log(x, y, z);

//skip the value (we call empty space as hole)
let [main, , secondary] = restaurant.categories;
console.log(main, secondary);

//switch variables
[main, secondary] = [secondary, main];
console.log(main, secondary);

//Nested destructuring
const nested = [2, 4, [5, 6]];
const [i, , [j, k]] = nested;
console.log(i, j, k);

//Intitializing variables
const [l = 1, m = 1, o = 1] = [8, 9];
console.log(l, m, o); // o === undefined
```

## **_Destructuring Object_**

    array와 비슷하지만 다름

```javascript
const restaurant = {
  name: "Classico Italiano",
  location: "Via Angelo Tavanti 23, Firenze, Italy",
  categories: ["Italian", "Pizzeria", "Vegetarian", "Organic"],
  starterMenu: ["Focaccia", "Bruschetta", "Garlic Bread", "Caprese Salad"],
  mainMenu: ["Pizza", "Pasta", "Risotto"],

  order: function (starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  },
  openingHours: {
    thu: {
      open: 12,
      close: 22,
    },
    fri: {
      open: 11,
      close: 23,
    },
    sat: {
      open: 0, // Open 24 hours
      close: 24,
    },
  },

  //인자를 받으면서 바로 destructuring 하기
  orderDelivery: function ({ address, mainIndex, starterIndex, time }) {
    console.log(
      `Oder received! ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}`
    );
  },
};
```

```javascript
restaurant.orderDelivery({
  time: "22:30",
  address: "Via del sole, 21",
  mainIndex: 2,
  starterIndex: 2,
});

// 복사하고싶은 object의 key name을 변수명 설정
const { name, openingHours, categories } = restaurant;
console.log(name, openingHours, categories);

// 변수명을 바꾸고 싶은 경우 keyName : changeName
const {
  name: restaurantName,
  openingHours: hours,
  categories: tags,
} = restaurant;
console.log(restaurantName, hours, tags);

//Initializing Objects
const { menu = [], starterMenu: starters = [] } = restaurant;
console.log(menu, starters);

//Mutating Variables\
let a = 111;
let b = 999;
const obj = { a: 23, b: 7, c: 14 };

({ a, b } = obj);

// //Nested Object
const {
  fri: { open, close },
} = openingHours;

console.log(open, close);
```

### **_✨ 몇가지 포인트_**

    1. object는 변수명 = object의 key name

    2. 변수명 변경
    name: restaurantName 콜론으로 표현

    3. 값의 초기화
    menu = [], starterMenu = [] 이퀄로 표현

    4.{}로 시작하는 코드는 오류, ()로 감싸기
    ({ a, b } = obj);

    5. 함수에 인자로 보낼 때 바로 destructuring 가능
    order: function({arg1, arg2, arg3}){
      console.log(arg1, arg2, arg3);
    }
