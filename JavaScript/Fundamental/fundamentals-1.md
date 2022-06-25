# **_JavaScript fundamentals-1_**

## **_NaN은 invalid number_**

        typeof NaN >> number

---

## **_string calculation_**

```
1 string을 더하면 string으로 취급하고 concatenate
2 string을 빼면 숫자로 coercion
4 + “hi” >> “4hi”
“4” + 3 >> “43”
“4” + “3” >> “43”
“4” - 3 >> 1
“hi”- 3 >> NaN
```

---

## **_falsy values_**

```
0, “ ”, undefined, null, NaN
```

---

## **_Equality type coercion_**

    prompt(“”): 사용자에게 input을 얻을 수 있음
    typeof prompt: string


    1. ==  type coercion 🆗
    2. === strict comparison 🚫

    for clean code don’t use double equal sign

---

## **_Logical Operators_**

<br>

### **_if-else statement_**

    conditon은 const로 선언하기 보단 괄호안에 바로 적는다
    const isIsland = country === “island”;
    if(isIsland) (X)

    if(country === “island”) (O)

---

## **_switch_**

    strict comparison(===)으로 비교후 결과 도출
    √ switch, case “”:, break

```javascript
switch (day) {
  case "monday":
    console.log("plan course structure");
    console.log("Go to coding meetup");
    break;
}
```

    요즘 덜 쓰지만 equality, comparison 기호가 덜 들어가서 보기 편하다

---

## **_statement / expression_**

<br>

### **_statement_**

```javascript
if(true){
  console.log("I'm su yeon");
}

어떤 값도 산출 안함
```

### **_expressions_**

```javascript
"wine"
4 + 2
true && false || true

값을 산출
```

---

## **_conditional operator (ternary)_**

if-else statement를 간결하게 표현

```javascript
age >= 18
  ? console.log("I like to drink wine 🍷")
  : console.log("I like to drink water 💧");
```

    다른 operator와 다르게 세 부분으로 이루어짐

    1.  age >=18

    2.  ? console.log("I like to drink wine 🍷")

    3. : console.log("I like to drink water 💧");

### **_why operator?_**

    operator는 values를 산출한다(= expression)

### **_증거 1._**

```javascript
const drink = age >= 18 ? "wine 🍷" : "water 💧";
console.log(drink);
```

    drink라는 variable에 값으로서 할당할 수 있음

### **_증거 2._**

    √ js는 expression과 statement가 와야하는 자리를 알고 있다 그 자리에 다른 값이 들어오면 오류가 뜸

    √ template literal은 반드시 value만 값으로 사용가능

```javascript
console.log(`I like to drink ${age >= 18 ? "wine 🍷" : "water 💧"}`);
```
