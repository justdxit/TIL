# 객체(object)

자료형의 일종으로 다양한 값을 모아둔 값
객체의 종류에는  
배열(array), 함수(function), 배열이나 함수가 아닌 객체로 나눌 수 있음

<br/>

---

## 배열(array)

```javascript
const countries = ["미국", "일본", "영국", "대한민국"];
console.log(countires[0]); //미국
console.log(countries[1]); //일본
console.log(countries[2]); //영국
console.log(countries[3]); //대한민국
```

배열 내부에 들어있는 값을 요소(element)라고 한다.

<br/>

### 배열의 요소 개수 구하기

배열 이름 뒤에 .length를 붙인다.

```javascript
const arrayTest = ["a", "비", "c", "d", "", NaN];
console.log(arrayTest.length); //6
```

<br/>

배열 요소 개수에서 1을 빼면 마지막 요소의 인덱스!

```javascript
const findLastElement = ["a", "b", "c", "d", "e"];
console.log(findLastElement[findLastElement.length - 1]);
//실행결과 e
```

<br/>

### 배열에 요소 추가하기

```javascript
const insOne = ["a", "b", "c", "d", "e"];
insOne[5] = "f"; //ary1[ary.length]='f'
console.log(insOne);

//결과 ["a", "b", "c", "d", "e", "f"]
```

<br/>

### 배열 맨 앞에 요소를 추가하려면? **unshift**

```javascript
const insFirstOne = ["가", "나", "다", "라"];
insFirstOne.unshift("냥");
console.log(insFirstOne);

//결과 ["냥", "가", "나", "다", "라"];
```

<br/>

### 배열 맨 끝에 요소 추가하기 **push**

```javascript
//가장 끝에 추가하기
const insLastOne = ["가", "나", "다", "라"];
insLastOne.push("캬");
console.log(insLastOne);

//결과 ["가", "나", "다", "라", "캬"]
```

<br/>

> const는 상수인데 어떻게 값을 바꿀 수 있을까?
> const에 객체(배열, 함수, 객체 리터럴)가 대입된 경우  
> 객체 내부의 속성이나 배열의 요소는 수정 가능!

<br/>

### 배열에서 마지막 요소 제거하기 **pop**

```javascript
const delLastOne = ["a", "b", "c", "d", "e"];
delLastOne.pop();
console.log(delLastOne);

//결과 ["a", "b", "c", "d"];
```

<br/>

### 배열에서 첫번째 요소 제거하기 **shift**

```javascript
const delFirstOne = ["가", "나", "다", "라"];
delFirstOne.shift();
console.log(delFirstOne);

//결과 ["나", "다", "라"]
```

<br/>

### 배열에서 중간 요소 제거하기 **splice**

```javascript
const delMidOne = ["a", "b", "c", "d", "e"];
delMidOne.splice(1, 1);
//지우고 싶은 인덱스, 인덱스 기준 지울 개수(미기입시 인덱스 이후 전체 삭제)
console.log(delMidOne);

//결과 ["a", "c", "d", "e"]
```

<br/>

### 요소를 제거하고 그 자리에 추가하기

```javascript
const target = ["가", "나", "다", "라", "마"];
target.splice(1, 2, "헉");
console.log(target);

//결과 ["가", "헉", "라", "마"]
```

<br/>

### 배열에서 요소 유무 확인 **includes**

```javascript
const target = ["a", "b", "c", "d", "e"];
const result1 = target.includes("b");
const result2 = target.includes("e");
console.log(result1 + ", " + result2);

//결과 trun, true
```

<br/>

### 배열에서 특정 요소 인덱스 확인 **indexOf, lastIndexOf**

```javascript
const target = ["차", "나", "다", "라", "나"];
const result1 = target.indexOf("나"); //결과 1 (앞에서 부터 확인)
const result2 = target.lastIndexOf("라"); //결과 3 (뒤에서 부터 확인)
const result3 = target.indexOf("엥"); //결과 -1 (결과 없으면 -1)
console.log(result1, result2, result3);
```

<br/>

### 주의) IndexOf를 조건문에 사용할 때!

```javascript
const arr = [1, 2, 3, 4, 5];
arr.indexOf(1); //0
if (arr.indexOf(1)) {
  console.log("1 위치 발견");
} else {
  console.log("1 못찾음");
}

//결과는 "1 못찾음"
```

indexOf의 결과, 1의 인덱스가 0이라 false 처리된다.  
조건문에서는 **if(arr.indexOf(1) > -1)** 을 사용해야 한다.

> false처리 되는 것들!  
> '', 0, false, null, undefined, NaN
