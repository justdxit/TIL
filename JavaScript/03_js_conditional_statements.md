# 조건문

## if

```javascript
if (조건식) 동작문;
```

```javascript
let condition = true;
if (condition) {
  console.log("don't forget!");
}
```

<br/>

---

## else

```javascript
if (조건식) {
  동작문;
} else {
  동작문;
}
```

```javascript
if (조건식) {
  동작문;
} else if (조건식2) {
  동작문;
} else if (조건식3) {
  동작문;
}
```

<br/>

---

## 중첩 if 조건문

```javascript
let first = true;
let second = false;
if (first) {
  console.log("조건1 충족");
  if (second) {
    console.log("조건2 충족");
  } else {
    console.log("조건2 불충족");
  }
} else {
  console.log("조건1 불충족");
}
```

중첩이 많아지면 코드가 한눈에 들어오지 않는다.  
위 코드는 아래의 코드로 바꿀 수 있다.

```javascript
let first = true;
let second = false;
if (first && second) {
  console.log("조건1 충족");
  console.log("조건2 충족");
} else if (first) {
  console.log("조건1 충족");
  console.log("조건2 불충족");
} else {
  console.log("조건1 불충족");
}
```

<br/>

---

## Switch

조건식 두 개를 사용

```javascript
let useSwitch = "ABC";
switch (useSwitch) {
  case "ABC":
    console.log("value랑 조건식이 같네! 실행해!");
}
```

```javascript
let value = "A";
switch (value) {
  case "A":
    console.log("A");
  case "B":
    console.log("B");
  case "C":
    console.log("C");
}
```

실행하면 case 'A'의 실행 결과인 A만 출력될 것 같지만,  
참인 case 'A' 이하 모든 구문이 실행된다.  
이를 방지하고 싶다면 어떻게 해야할까?

```javascript
let value = "A";
switch (value) {
  case "A":
    console.log("A");
    break;
  case "B":
    console.log("B");
    break;
  case "C":
    console.log("C");
    break;
}
```

break을 써서 switch문 밖으로 빠져나갈 수 있다.

<br/>

---

## 조건부 연산자(삼항 연산자)

<br/>

> 조건식 ? 참일 때 실행되는 식 : 거짓일 때 실행되는 식

조건부 연산자는 식이기 때문에 결과값이 나온다.  
웹브라우저 콘솔에서 실행해보면

```javascript
> 1 > 0 ? '참이면 실행' : '거짓이면 실행'
< "참입니다"
```

이걸 활용해서

```javascript
> let value = 1 < 0 ? '참이면 실행' : '거짓이면 실행'
< undefined
> value;
< "거짓이면 실행"
```

조건부 연산자의 값이 value에 대입된다.

<br/>

### 조건부 연산자를 if문으로 바꾸기

```javascript
let condition = true;

//조건부 연산자 사용
let value = condition ? "참이다" : "거짓이다";
console.log(value);

//if문으로 변경
if (condition) {
  value = "참이다";
} else {
  value = "거짓이다";
}
console.log(value);
```

### 중첩된 조건부 연산자

<br/>

1.  참인 부분에 중첩

```javascript
let condition1 = true;
let condition2 = false;
let value = condition1
  ? condition2
    ? "둘 다 참이다"
    : "condition1만 참이다"
  : "condition1은 거짓";
console.log(value);
```

2. 거짓인 부분에 중첩

```javascript
let condition1 = true;
let condition2 = false;
let value = condition1
  ? "condition1은 참이다"
  : condition2
  ? "condition2는 참이다"
  : "둘 다 거짓이다";
console.log(value);
```
