# Chapter 9. 이벤트 기초 및 활용

<br>

## 이벤트
- 이벤트란
  + 사용자의 입력 및 브라우저의 변화를 JS 코드에 알리는 통지
  + 브라우저 화면의 모든 변화는 곧 이벤트
  + ex) 마우스, 키보드 입력, 이미지 및 HTML 문서 로딩 등
- 이벤트 리스너 (EventListener)
  + 발생한 이벤트에 적절히 대처하기 위해 만들어진 코드
- 이벤트 종류
  + 약 70개로 매우 다양함, 이벤트리스너 이름 앞에는 `on`이 붙는다
  + 대표적인 이벤트리스너 : `onclick`, `onmousedown`, `onmouseover`, `onmouseout`, `onkeydown`, ...
<br>

## 이벤트리스너 만들기
- HTML 태그 안에 작성
```html
<p onmouseover="this.style.backgroundColor='yellow'"
   onmouseout="this.style.backgroundColor='white'">마우스 올리면 yellow 색 변경</p>
```
- DOM 객체로 이벤트 리스너 프로퍼티에 리스너 등록
```html
<body onload="init()">
  <p id="p">마우스 올리면 yellow 색 변경</p>
</body>
```
```javascript
let p;
function over() {
  p.style.backgroundColor = "yellow";
}
function out() {
  p.style.backgroundColor = "white";
}
function init() {
  p = document.getElementById("p");
  p.onmouseover = over;
  p.onmouseout = out;
}
```
- 익명 함수로 이벤트 리스너 작성
```html
<body onload="init()">
  <p id="p">마우스 올리면 yellow 색 변경</p>
</body>
```
```javascript
let p;
function init() {
  p = document.getElementById("p");
  p.onmouseover = function () {
    this.style.backgroundColor = "yellow";
  };
  p.addEventListener("mouseout", function () {
    this.style.backgroundColor = "white";
  });
}
```

<br>

## 이벤트 객체
- 이벤트 발생 시 생성되며 이벤트에 관한 정보들 포함, 이벤트 리스너에 전달됨
- 이벤트가 처리되고 나면 소멸
- 이벤트 리스너 실행 중에는 오직 한 개의 이벤트 객체만 존재

<br>

## Event Target
- 이벤트를 발생시킨 객체(태그)
  + ex) 버튼을 눌러 click 이벤트가 발생했다면 target은 button 객체

<br>

