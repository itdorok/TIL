# Rest operator

### **_Spread op와 문법은 같지만 결과는 완전 반대_**

```javascript
// Data needed for first part of the section
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

  orderPasta: function (ing1, ing2, ing3) {
    console.log(`Here is your delicious pasta with ${ing1}, ${ing2}, ${ing3}`);
  },

  orderPizza: function (mainIngredients, ...otherIngredients) {
    console.log(mainIngredients); //mushrooms
    console.log(otherIngredients); // 나머지 값들의 배열
  },
};

// 1) Destructuring
// SPREAD, because on RIGHT side of =
const arr = [1, 2, ...[3, 4]];

//REST, because on LEFT side of =
const [a, b, ...others] = [1, 2, 3, 4, 5];
console.log(a, b, others);

const [pizza, , risotto, ...otherFood] = [
  ...restaurant.mainMenu,
  ...restaurant.starterMenu,
];
console.log(pizza, risotto, otherFood);

//Object
const { sat, ...weekdays } = restaurant.openingHours;
console.log(weekdays);

// 2) Functions
const add = function (...numbers) {
  console.log(numbers);
};

add(2, 3); // [2,3]
add(5, 3, 7, 2);
add(8, 2, 5, 3, 2, 1, 4);

const x = [23, 5, 7];
add(...x); // 23, 5, 7 >>> [23, 5, 7]

restaurant.orderPizza("mushrooms", "onion", "olives", "spinach");
```

<table style="border: 1px solid">
<tr>
  <th>OP</th>
  <th>위치</th>
  <th>기능</th>
  <th>예제</th>
</tr>
<tr>
  <td>Rest</td>
  <td>before =</td>
  <td>pack values into arr/obj</td>
  <td>const [a, ...others] = [1, 2, 3];
    others = [2,3]
  </td>
</tr>
<tr>
  <td>Spread</td>
  <td>after = </td>
  <td>unpack values from arr/obj</td>
  <td>const arr = [1,2, ...[3,4,5]];
  arr = [1,2,3,4,5]</td>
</tr>
</table>
