# 자바스크립트

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

## 자료형
  >값(value)은 프로그램이 조작할 수 있는 데이터를 의미한다. 값에는 여러 가지 종류가 있으며 이런 값의 종류를 자료형(data type)이라고 한다.

  <br/>

### 문자열(String)

- 하나 이상의 문자를 의미한다. 문자열은 반드시 따옴표나 쌍따옴표로 감싸줘야 한다.  
  ex) 'hello world', "how're you?", 'he said "good bye"'  
'how\\'re you?'
- 줄 바꿈은 백틱(\`)을 사용  
  ex) \`line1  
  line2\`