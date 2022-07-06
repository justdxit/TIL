# 함수(function)

함수는 일정한 동작을 수행하는 코드를 의미  
함수를 미리 만들어두고 원할 때 실행해 정해진 동작을 수행하게 할 수 있다.

```javascript
function () {}
//또는
() => {}
```

```javascript
function a() {} //함수 선언문
const b = function () {}; //함수 표현식
const c = function () {}; //화살표 함수
```

함수 선언문 뒤에는 보통 세미콜론을 붙이지 않는다.  
if문, for문, while문, 함수 선언문 중괄호 뒤에는 세미콜론이 붙지 않는다.

<br/>

## 함수 호출하기

```javascript
function a() {
  return "반환값";
}

a(); //함수 호출
//return 값을 반환함
```

함수의 return 값을 설정하지 않으면 undefined가 디폴트로 설정된다.

<br/>

return 값을 여러개 설정하고 싶다면?  
배열을 사용하자

```javascript
function a() {
  return [5, 10];
}
```

<br/>

## 매개변수(Parameter)와 인수(Arguement)

```javascript
function a(parameter) {
  console.log(parameter);
}
a("argument");

//결과는 argument 출력
```

함수를 **선언**할 때는 매개변수(Parameter),  
함수를 **호출**할 때는 인수(Argument)!

```javascript
function a(w, x, y, z) {
  console.log(w, x, y, z);
  console.log(arguments);
}
a("가", "나", "다");

//결과
//가 나 다 undefined
//Arguments(3) ['가', '나', '다']
```

매개변수와 인수 개수가 일치하지 않아도 된다.

<br/>

---

## 화살표 함수의 선언

```javascript
//매개변수 지정 방법
() => {...} //매개변수가 없을 경우
x => {...} //매개변수가 한 개인 경우, 소괄호 생략 가능
(x,y) => {...} //매개변수가 여러 개인 경우, 소괄호 생략 불가

//함수 몸체 지정 방법
x => {return x * x } //single line block
x => x * x
//함수 몸체가 한 줄의 구문이라면 중괄호 생략 가능하며 암묵적으로 return 된다.
//위 두 구문은 같은 구문이다.

() => { return {a : 1}; }
() => ({a : 1}) //위 표현과 동일. 객체 반환시 소괄호 사용

//multi line block
() => {
  const x = 10;
  return x * x;
}
```

<br/>

## 화살표 함수의 호출

```javascript
//ES5
var func = funtion(x){return x * x;};
console.log(func(10)); //100

//ES6
// const func = x => {return x * x;};
//"{" 다음에 return이 바로 올 경우 {}와 return 생략 가능
const func = x => x * x;
console.log(func(10)); //100
```

### 콜백 함수로 호출하기

```javascript
//ES5
var arr = [1, 2, 3];
var func = arr.map(function (x) {
  return x * x;
});
console.log(func); //[1,4,9]

//ES6
const arr = [1, 2, 3];
const func = arr.map((x) => x * x);

console.log(func); //[1,4,9]
```
