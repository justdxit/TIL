# 변수

특정한 값을 저장할 수 있다.

```javascript
let varNumber = 365;
console.log(varNumber);

365

let total = 1000 + 1000 + 2000;
console.log(total);

4000
```

```javascript
let empty;
console.log(empty);

undefined
```

값을 대입하지 않은 변수를 입력하면 undefined 가 출력된다.

<br/>

---

## 변수 명 짓기

<br/>

한글, 한자, 숫자도 가능하지만  
모두가 이해할 수 있는 영어를 사용하자!  
특수문자 중에서도 되는 문자들이 있다. $, \_ 등

> await, break, case, catch, class, const, continue, debugger, delete, do, elase, enum, export, extend, false, finally, for, function, if, import, in, instanceof, new, null, return, super, switch, this, throw, true, try, typeof, var, void, while, with, yield

**예약어**는 기본적으로 변수명 사용이 불가하다.  
예약어이지만 변수명으로 사용할 수 있는 경우도 있고, 예약어가 아님에도 변수명으로 쓰지 못하는 경우도 있다.
예약어를 사용하면 에러가 발생하기 때문에 에러를 확인하자!

<br/>

---

## 변수 수정하기

<br/>

```javascript
let changeVar = 'before change';
changeVar = 'after change'
console.log(changeVar);

after change
```

<br/>

### 변수 값 비우기
undefined 또는 null을 사용하자.
```javascript
let emptyVar = 'before empty';

방법1)
emptyVar = undefined;
undefined

방법2)
emptyVar = null;
null
```
undefined과 null은 다른 값이기 때문에 다른 의미를 부여할 수 있다.  
많은 개발자들은 **null**을 사용하여 값을 의도적으로 지웠다는 의미를 부여한다.

<br/>

### 변수 자신을 자신에게 대입하기
```javascript
let number = 10;

방법1)
number = number + 5;
console.log(number);

15

방법2)
number += 5;
console.log(number);

15
```

<br/>
<br/>


# 상수(const)
const는 상수(constant)의 줄임말  
상수는 '변하지 않는 수'라는 뜻  
상수는 변수와 다르게 처음 선언할 때 꼭 **초기화**를 해줘야 한다.

```javascript
const cst = '상수는 const';
cst = '상수를 바꾸려고 한다면?';

Uncaught TypeError: Assignment to constant variable.

에러 발생!
```

