# **_javaScript fundametals - 2_**

## **_strict mode_**

```javascript
"use strict";
```

    √ js file 첫번째 줄에 적기
    √ visually alert error
    √ forbid us to do something

---

## **_💡 function_**

    √ similar to variables but complete lines of code

    √ maintainable code

### **_get parameter_**

    √ placeholder to get argument
    √ performs like variables

### **_specify argument_**

    actual value we put in when we call the function

### **_capture value_**

```javascript
const result = function(arg,arg) ;
```

    √ function이 return하는 값을 value에 저장

    √ function이 return하지 않으면
    저장해도 undefined

---

## **_💡 function declaration vs expression_**

<br>

### **_Function declaration_**

```javascript
function calcAge1(birthYear) {
  return 2037 - birthYear;
}
const age1 = calcAge1(1997);
```

    declaration: can call function before
    initialization

### **_Function expression_**

```javascript
const calcAge2 = function (birthYear) {
  return 2037 - birthYear;
};
const age2 = calcAge2(1997);
```

    expression: can’t call function before initialization
