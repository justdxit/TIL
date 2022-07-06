# 객체 리터럴

## 객체 선언

```javascript
const obj = {
  name: "홍길동", //속성: 속성값
  year: 1443,
  month: 01,
  date: 23,
  gender: "male",
  //속성명에 숫자, 공백, 특수문자 포함시 따옴표로 감싸준다.
  //마지막 쉼표는 없어도 된다. 다음값 추가를 대비해 찍자.
};
```

## 객체 호출

```javascript
console.log(obj.name);
console.log(obj["name"]);
//접근 방법은 두가지
//따옴표로 감싸준 속성명은 무조건 대괄호 사용
//ex) obj["number010"];
```

## 객체 속성 수정하기

```javascript
obj.gender = "M";
console.log(obj.gender); //결과는 M
```

## 객체 속성 제거하기

delete 변수.속성

```javascript
delete obj.gender;
console.log(obj.gender); //결과는 undefined
```

<br/>

---

## 메서드

객체의 속성 값으로 함수를 넣었을 때
이 속성을 **메서드(method)** 라고 한다.

```javascript
const debug = {
  log: function (value) {
    console.log(value);
  },
};
debug.log("Hello, Method");
```

debug라는 객체안의 속성log: 속성값  
속성값을 함수(function)로 넣었다.  
여기서의 함수를 메서드라고 부른다.

<br/>

---

## 객체 간의 비교

```javascript
{} === {}
//결과는 false
```

객체가 아닌 숫자, 문자열, boolean값, null, undefined는 모두 true 반환

Why? 객체는 모양이 같아도 생성할 때마다 새로운 객체가 생성된다!

```javascript
const obj1 = { name: "홍길동" };
const obj2 = [1, 2, obj1];
console.log(obj1 === obj2[2]);
//만들어 둔 객체를 사용했기 때문에 true
```
