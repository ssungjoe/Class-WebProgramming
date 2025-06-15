# Chapter 6. 자바스크립트 언어

<br>

## 자바스크립트(Javascript)란?

- 1995년 넷스케이프 사에서 개발되고 Netscape Navigator 2.0 브라우저에 최초로 탑재된 언어
- 특징 3가지
  + 자바스크립트는 조각난 소스 코드 형태로 HTML페이지에 저장됨
  + 자바스크립트 소스 코드는 컴파일 과정 없이 브라우저 내부의 인터프리터에 의해 바로 실행됨
  + 자바스크립트는 C언어 구조를 차용하고 단순화시켜 쉽게 배울 수 있음

<br>

## 자바스크립트의 역할
- 사용자의 입력 및 계산
- 웹 페이지 내용 및 모양의 동적 제어
- 브라우저 제어
- 웹 서버와의 통신
- 웹 애플리케이션 작성

<br>

## 자바스크립트 코드의 위치
- HTML 태그의 이벤트 리스너 속성에 자바스크립트 코드 작성
  + `onclick`, `onmouseover`, `onmouseout`
```html
<img src="apple.png" alt="img" onclick="this.src='banana.png'">
```
- `<script></script>` 태그에 자바스크립트 코드 작성
```javascript
function over(obj) {
  obj.src = "media/banana.png";
}
function out(obj) {
  obj.src = "media/apple.png";
}
```
`...`
```html
<img src="media/apple.png" alt="img" onmouseover="over(this)" onmouseout="out(this)">
```
- 자바스크립트 코드를 별도 파일에 작성
```html
<script src="filename.js"></script>
```
- URL 부분에 자바스크립트 코드 작성
```html
<a href="javascript:alert('clicked!')">여기를 클릭</a>
```
<br>

## JS로 HTML 콘텐츠 출력
- `document.write()`, `document.writeln()`
```javascript
document.write("<h3>INNER TEXT</h3>");
```
<br>

## 다이얼로그
- `prompt()` : 사용자로부터 다이얼로그를 통해 문자열 입력받음
```javascript
let res = prompt("이름을 입력", "SJ");
if (res == null) {
  // 취소하거나 닫은 경우
}
else if (res = "") {
  // 입력없이 확인만 누른 경우
}
else {
  // res는 사용자가 입력한 문자열
}
```
- `confirm()` : 다이얼로그로 확인/취소를 선택하도록 함
```javascript
let res = confirm("전송하시겠습니까?");
if (res == true) {
  // 확인을 누른 경우
}
else {
  // 취소하거나 닫은 경우
}
```
- `alert()` : 경고 다이얼로그, 확인버튼만 있음
```javascript
alert("클릭하였습니다);
```
<br>

## 데이터 타입
- 식별자 : 변수, 상수, 함수에 붙이는 이름
  + 첫 글자 : 알파벳, _, $
  + 이후 글자 : 알파벳, _, 0-9, $
  + 대소문자 구분, 예약어 사용불가
- 문장구분 : `;` 사용, 한 줄에 한 문장만 있으면 생략 가능
- 주석문 : 한 줄은 `// text`, 여러 줄은 `/*  text  */` 사용
- 데이터 타입 종류
  + 숫자 : `123`, `-456`, `3.14`
  + 논리 : `true`, `false`
  + 문자열 : `"string1"`, `'String2'`
  + 객체 레퍼런스 : `[object Object]`
  + `null` : 값이 없음을 인위적으로 나타냄

<br>

## 변수
- 선언 방법
  + `var`, `let`, `const`
  + `let`은 2015년 ES6에서 새로 추가됨, 동일한 변수 재선언 불가
- 사용 범위
  + 전역 변수 : 함수 밖에서 선언되거나, `var`, `let` 없이 선언된 변수
  + 지역 변수 : 함수 내에서 `var`, `let`으로 선언된 변수, 함수 종료 시 사라짐
  + 블록 변수 : `let`으로 `if`, `while`, `for` 등의 블록 안에서 선언된 변수, 블록이 끝나면 사라짐
- `this`로 전역 변수 접근
  + 블록 내에서 같은 이름으로 변수가 선언되었다고 해도 `this.x`처럼 `this`를 사용하면 전역변수에 접근 가능하다
```javascript
var x = 10; // 전역변수
function foo() {
  var x; // 지역변수
  x = 1;
  this.x = 100; // 전역변수 x에 100 저장
}
```
- `let`의 특징
  + 코딩 오류를 줄이기 위해 2015년 ES6표준에 새로 도입됨
  + 재선언 불가, 사용범위를 블록 내로 제한
  + `var`보다 `let`의 사용이 권해진다
 
<br>

## 상수
- `const` 키워드 사용
  + 변하지 않는 값
  + 사용범위는 블록 내부
<br>

## 리터럴
- 데이터 값 그 자체
  + 정수, 실수, 논리(`true`, `false`), 문자열, `null`, `NaN`
```javascript
let x = 10;  // 변수 x에 리터럴 10 저장
```
<br>

## JS 제공 전역함수

- `eval()`
  + 수식이나 JS 문장을 문자열로 전달받아 실행
- `parseInt()`
  + 문자열을 숫자로 리턴
- `isNaN()`
  + 숫자가 아니면 `true` (NaN),  맞으면 `false`
