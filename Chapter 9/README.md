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

## 이벤트 관련 프로퍼티
- `target` 프로퍼티
  + 이벤트를 발생시킨 객체(태그)
  + ex) 버튼을 눌러 click 이벤트가 발생했다면 target은 button 객체
```html
<p id="p"></p>
<button onclick="f(event)">클릭</button>
```
```javascript
function f(e) {
  let target = e.target;
  let p = document.getElementById("p");
  p.innerHTML = target;
}
```
- `preventDefault()`
  + 태그의 디폴트 행동을 일어나지 않도록 함
```html
<!-- 링크를 클릭해도 이동이 안됨 -->
<a href="..." onclick="event.preventDefault()"></a>
``` 

<br>

## 이벤트 흐름
- 이벤트 흐름이란
  + 이벤트가 타깃에 그냥 전달되고 사라지는게 아님
  + 이벤트는 `window`에서 타겟 객체까지 이벤트 객체를 전파시키는 "캡쳐 단계"를 거침
  + 그리고 "버블 단계"에서 다시 타겟 객체에서 반대 방향으로 이동해 `window` 객체에 도달 후 사라짐
  + 이 과정을 이벤트 흐름이라고 함
- 캡쳐 리스너
  + 캡쳐 단계에서 실행되도록 작성된 리스너
  + `addEventListener`의 3번째 인자를 `true`로 기입
- 버블 리스너
  + 버블 단계에서 실행되도록 작성된 리스너
  + `addEventListener`의 3번째 인자를 `false`로 기입
- `stopPropagation()`
  + 이벤트 흐름을 중단시키는 메소드
 
<br>

## 마우스 이벤트
- `onclick` : 클릭 시 실행되는 이벤트 리스너
- `ondbclick` : 더블 클릭 시 실행되는 이벤트 리스너
- `onmousedown`, `onmouseup` : 각각 마우스 클릭 시작 시, 마우스 버튼 놓았을 시 실행되는 이벤트 리스너
- `onmouseover`, `onmouseout` : 각각 마우스가 HTML 태그 위에 올라올 시, 내려갈 시 실행
- `onwheel` : HTML 태그에 마우스 휠이 돌아갈 시 계속 실행
  + 이벤트 객체로부터 `wheelData`를 통해 휠이 구른 방향 확인가능 (아래쪽은 음수)
- `onmousemove` : 마우스가 움직이는 동안 계속 실행
- `oncontextmenu` : 우클릭 시 뜨는 메뉴에 대한 이벤트 리스너
```javascript
document.oncontextmenu = function () {
  alert("우클릭 금지");
  return false;  // 컨텍스트 메뉴를 뜨지 않도록 설정
};
```

<br>

## 문서 및 이미지 로딩 이벤트
- `onload` : 브라우저 웹 페이지 로딩이 완료되면 실행
```html
<body onload="alert('로딩완료')"></body>
```
또는
```javascript
window.onload = "alert('로딩완료')";
```
- 이미지 출력 과정
  + 이미지 로딩 -> 이미지 출력
- `onload` 활용해 이미지 로딩 후 출력하기
```javascript
let myImg = document.getElementById("myImg");
myImg.onload = function () {  // 이미지 로딩 전 onload 리스너를 먼저 등록
  let width = myImg.width; // 이미지가 로딩이 안돼 폭을 잘못 아는 참사 막을 수 있음
}
myImg.src = "apricot.png";  // 이미지 로딩
```
- `Image` 객체 활용
```javascript
let addImg = new Image();  // Image 객체 사용
addImg.src = "apricot.png";

let myImg = document.getElementById("myImg");
myImg.src = addImg.src; 
```

<br>

## 폼 이벤트
- `onfocus`, `onblur` : 각각 HTML 태그가 포커스를 가지고 있을 때, 잃었을 때 실행
  + ex) 텍스트 창을 누르고 있다가 라디오 버튼을 누르면 텍스트 창은 `onblur` 활성화, 라디오 버튼은 `onfocus` 활성화
- 그룹을 이룬 라디오 버튼은 `name` 속성이 동일
```javascript
// name 속성이 apricot인 radio 버튼들 찾기
let radio = document.getElementsByName("apricot");
```
- `checked` 속성으로 체크박스, 라디오 버튼이 체크되었는지 확인 가능
- `selectedIndex` 속성으로 select 객체(태그)의 선택된 옵션 확인 가능
- `onreset`, `onsubmit` : 각각 reset 버튼, submit 버튼이 클릭되었을 때 실행 

<br>

## 키 이벤트
- `onkeydown`, `onkeyup` : 각각 키가 눌렸을 때, 떼어졌을 때 실행
- `onkeypress` : Enter, Space, Esc, 문자키가 눌렸을 때 실행
- 이벤트 객체를 통해 `key`, `code` 프로퍼티 제공됨
```html
<input type="text" onkeydown="nowKey(event)">
<div id="div"></div>
```
```javascript
function nowKey(e) {
  let  str = "";
  let div = document.getElementById("div");
  div.innerHTML = "";
  str += "Key : " + e.key + "<br>";  // 현재 입력된 키
  str += "Code : " + e.code + "<br>";  // 현재 입력된 키의 코드
  div.innerHTML = str;
}
```
