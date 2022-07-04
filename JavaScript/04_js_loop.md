# 반복문

## for

```javascript
for (시작; 조건식; 종료식) 동작문;
```

```javascript
for (int i = 0; i< 5; i++) {
  console.log('Hello World!');
}
// 실행결과는 Hello World! 5번 출력
```

<br/>

## while

```javascript
let i = 0;
while (i < 5) {
  console.log(i + 1);
  i++;
}

//1~5까지 한 줄씩 출력된다.
```

<br/>

## break문으로 반복문 멈추기

```javascript
let i = 0;
while (true) {
  //무한반복이지만 break로 탈출
  if (i === 5) break;
  i++;
}
console.log(i);
//결과는 5
```

<br/>

## continue문으로 코드 실행 건너뛰기

```javascript
let i = 0;
while (i < 10) {
  i++;
  if (i % 2 === 0) {
    //i가 2의 배수면(짝수면)
    continue; //다음 코드를 건너뛰어라
  }
  console.log(i);
}
//결과는 1,3,5,7,9
```

<br/>

---

## 중첩된 반복문

```javascript
for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    console.log(i, j);
  }
}
```

실행결과

```javascript
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

```javascript
for (let i = 0; i < 5; i++) {
  if (i % 2 === 0) continue;
  for (let j = 0; j < 5; j++) {
    if (j % 2 === 0) continue;
    for (let k = 0; k < 5; k++) {
      if (k % 2 === 0) continue;
    }
  }
}

//i==0 continue
//i==1, j==0 continue
//i==1, j==1, k==0 continue
//i==1, j==1, k==1 console.log(1,1,1)
//i==1, j==1, k==2 continue
//i==1, j==1, k==3 console.log(1,1,3)
//i==1, j==1, k==4 continue
//i==1, j==1, k==5 조건 불충족
//i==1, j==2 continue
//i==1, j==2, k==0 continue
//i==1, j==3, k==1 console.log(1,3,1)
//                .
//                .
//                .
```

<br/>

### Quiz) 짝수 없는 구구단 만들기

```javascript
for (let i = 2; i < 10; i++) {
  if (i % 2 === 0) continue;
  for (let j = 1; j < 10; j++) {
    if (j % 2 === 0) continue;
    console.log(i + " x " + j + " = " + i * j);
  }
}
```
