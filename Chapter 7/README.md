# Chapter 7. 자바스크립트 코어 객체와 배열

<br>

## 객체
- 프로퍼티(property)
  + `{ property : value }`
- 메소드(method)
  + 객체 내부 함수
- 객체 종류
  + 코어 객체
  + HTML DOM 객체
  + 브라우저 관련 객체 (BOM)
- 코어 객체
  + `Array`, `Date`, `String`, `Math`, ...
- HTML DOM 객체
  + HTML 태그들을 모두 객체화, JS에서 이를 통해 HTML 태그 제어 가능
- BOM
  + 브라우저의 종류, 스크린 크기 정보, 새 윈도우 등등의 브라우저 관련 정보

<br>

## 코어 객체
- `new` 생성자로 코어 객체 생성
```javascript
let today = new Date(); // 6월 15일 저녁 8시 59분이라면
console.log(today.getHours()); // 20

let array = new Array(7); // 길이가 7인 빈 배열 선언
```

<br>

## String
- `str.indexOf("abc")`
  + 문자열 `str`에서 `"abc"`가 시작되는 인덱스 리턴
- `str.slice()`, `str.substr()`, `str.substring()`
  + 문자열 잘라내기
- `str.replace("A", "B")`
  + 문자열 `str` 중에서 `"A"`를 모두 `"B"`로 변경
- `str.split("word")`
  + 문자열 `"word"`를 기준으로 문자열 `str`을 분할해 배열로 반환

<br>

## Math
- `Math.sin()`, `Math.cos()`, `Math.exp()`, `Math.sqrt()`
- `Math.pow(a,b)` : a<sup>b</sup>
- `Math.random()` : 0~1 사이 랜덤 실수
- `Math.round()`, `Math.floor()`, `Math.ceil()` : 반올림, 내림, 올림
- `Math.E`, `Math.PI` : 수학 상수

<br>

## 사용자 객체
- `new Object()`
```javascript
let obj = new Object();
obj.name = "객체";
obj["abc"] = 123;

function add() {
  this.abc += 1000;
  alert("obj.fun");
}
obj.fun = add;
```

- `this`
`this.property`를 사용할 시 그 객체의 `property`에 접근하는 것이고, `this` 없이 그냥 `property`를 사용하면 전역변수나 지역변수를 뜻하게 된다

- 리터럴 표기법
```javascript
let obj = {
  name : "객체",
  abc : 123,
  fun : function () {
    this.abc += 1000;
    alert("obj.fun");
  }
}
```

- 프로토타입 만들기
```javascript
function Student(name, score) {
  this.univ = "sejong univ";
  this.name = name;
  this.score = score;
  this.getGrade = function () {
    if(this.score > 80) return "A;
    else if(this.score > 60) return "B";
    else return "F";
  }
}

let std = new Student("ssjoe", 90);
console.log(std.getGrade());  // "A"
```
