# 자바스크립트 기초

```javascript
console.log('Hello, world!')
```
<br/>

### 흔하게 발생하는 에러
- **Uncaught ReferenceError: @@@@ is not defined console** 입력 중에 오타가 있을 경우 발생하는 에러
- **Uncaught TypeError: @@@@.lg is not a function console** 함수 명을 찾을 수 없는 경우 발생
- **Uncaught SyntaxError: missing ) after argument list** 따옴표나 괄호 등을 빠트렸을 때 발생하는 에러
- **Uncaught SyntaxError: Invalid or unexpected token** 따옴표(혹은 쌍따옴표)의 짝을 맞추지 않았을 때 발생하는 에러

<br/>

### REPL
- 브라우저의 콘솔은 코드를 한 줄 씩 입력받고  (Read), 받은 입력을 평가(Evaluate)한 후 결과를 출력(Print)한다. 그 후 다시 프롬프트가 나타나 새로운 입력을 기다린다(Loop). 이러한 특성 때문에 콘솔을 REPL이라고 한다.

<br/>

### 세미콜론 
 - 자바스크립트는 하나의 명령이 끝날 때 세미콜론(;)을 불여도 되고 불이지 않아도 된다. 하지만 명령의 끝을 확실히 표시하기 위해 붙이는 것을 권장한다.

<br/>

---
## 자료형
  >값(value)은 프로그램이 조작할 수 있는 데이터를 의미한다. 값에는 여러 가지 종류가 있으며 이런 값의 종류를 자료형(data type)이라고 한다.

  <br/>

## 문자열(String)

- 하나 이상의 문자를 의미한다. 문자열은 반드시 따옴표나 쌍따옴표로 감싸줘야 한다.  
  ```javascript
  'hello world', "how're you?", 'he said "good bye"', 'how\'re you?'
  ```
- 줄 바꿈은 백틱(\`)을 사용
  ```javascript
  `line1  
  line2`
  ```
---

<br/>

## 숫자
1. parseInt: 문자열을 정수로 타입 변환  
   ex) parseInt('3월') -> 3
2. parseFloat: 문자열을 소수로 타입 변환
3. parseInt(prompt()): 입력 받을 수 있는 창을 띄운다.

<br/>

  **NaN**
```javascript  
> parseInt(prompt());  
("abc" 입력)
< NaN
```

NaN은 Not a Number의 약어
typeof NaN을 실행해보면 "number"라는 값이 출력됨

---
<br/>

## 연산자

<br/>

제곱: **  
```javascript
> 2 ** 3  
< 8
```
<br/>
무한대: Infinity

```javascript
> 2 / 0  
< Infinity

> -2 / 0  
< -Infinity
```

<br/>

자바스크립트는 정수뿐만 아니라 실수도 계산 가능
```javascript
> 0.5 + 0.5;
< 1
```

```javascript
> 0.1 + 0.2;
< 0.30000000000000004
```
컴퓨터는 이진법으로 사용하기 때문에 정확한 소수를 표현하기 어렵다.  
컴퓨터의 부동 소수점 계산문제!
```javascript
> (0.1 * 10 + 0.2 * 10) / 10;
< 0.3
```
실수를 정수로 바꿔서 계산한 뒤 다시 실수로 바꾸면 계산이 가능하다.  

---
<br/>

## 논리연산자

<br/>

```javascript
> &&: 그리고
> ||: 또는
> !: boolean 값을 반대로 바꿔줌
```
다른 자료형 앞에 !!를 붙이면 boolean 자료형으로 형 변환이 된다.
대부분의 값은 불 값으로 형 변환했을 때 true가 된다.

<br/>

***예외(꼭 알아두자!)***
```javascript
> !!false
< false
> !!''
< false
> !!0
< false
> !!NaN
< false
```
>false, ''(빈 문자열), 0, NaN, undefined, null, document.all

이렇게 형 변환 루 false가 되는 값들을 거짓인 값(falsy value)이라고 하고,  
true가 되는 값들은 참인 값(truthy value)이라고 한다.

- ! 연산자의 우선순위는 < 연산자보다 높음  
---  
  <br/>

## undefined & null
빈 값을 표현

<br/>

### undefined
반환할 결과값이 없을 때 출력됨.
```javascript
> console.log("hello");
hello
< undefined
```
콘솔에는 출력하지만, 그 자체로는 결과값이 없기 때문에 undefined

```javascript
> typeof undefined;
< "undefined"
```
```javascript
> !!undefined;
< false
```
undefined는 boolean으로 형 변환했을 때 false가 나온다.  

undefined와 false는 다르다.
```javascript
> undefined == false;
< false
> undefined == 0;
< false
> undefined == '';
< false
```

<br/>

### null
```javascript
> undefined == null;
< true
```
빈 값이라는 점에서 같지만 자료형을 비교해보면 다르다.
```javascript
> undefined === null;
< false
```
```javascript
> !!null;
< false
```
undefined 처럼 null도 boolean 값으로 형 변환할 때 false가 된다.

```javascript
> null == false;
< false
> null == 0;
< false
> null == '';
< false
```

null을 typeof로 확인하면
```javascript
> typeof null;
< "object"
```
null이 아니라 object!  
자바스크립트에서 유명한 버그!