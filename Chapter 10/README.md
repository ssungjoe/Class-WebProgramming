# Chapter 10. 윈도우와 브라우저 관련 객체

<br>

## BOM
- 브라우저가 실행되고 있는 환경을 JS 코드로 접근/제어할 수 있도록 설계된 객체
- BOM의 종류
  + `window`
  + `navigator`
  + `history`
  + `location`
  + `screen`
 
<br>

## window 객체
- `window.open()` : 새 윈도우 (새로운 탭) 실행
- 수많은 관련 프로퍼티, 컬렉션, 메소드, 이벤트 리스너 존재
- 바(bar)와 관련된 프로퍼티
  + `menubar` (파일/편집/보기/...), `locationbar` (주소창), `toolbar` (확장프로그램 등), `personalbar` (북마크)
- 위치 및 크기 관련 프로퍼티
  + `screenX`, `screenY` (윈도우가 출력된 좌표), `innerWidth`, `innerHeight` (HTML 영역 크기), `outerWidth`, `outerHeight` (윈도우 전체 크기)
- `window.open()` 사용법
```javascript
window.open("http://www.naver.com", "myNaver", "");
window.open("sample.html", "myWindow", "left=10,top=10,width=300,height=400");
```
- `window.close()` : 자신이 연 윈도우를 닫음
- `window.length` : 브라우저에서 `iframe` 태그로 만들어진 프레임 윈도우 개수
```javascript
window.frames[0];  // 1번째 frame 윈도우
...
window.frames[window.length - 1];  // 마지막 frame 윈도우
```

<br>

## 타이머
- `setTimeout()`, `clearTimeout()` : 타임아웃 코드 단 1회만 호출
```javascript
function myAlert(time) {
  alert(time + "초 경과..");
}
let timer = setTimeout("myAlert(3)", 3000);  // 3초 후 myAlert(3) 함수 호출
clearTimeout(timer);  // 이렇게 setTimeout 값을 저장해놓으면 호출 전에 해제 가능
```
- `setInterval()`, `clearInterval()` : 타임아웃 코드 반복 호출
  + `setTimeout`을 `setInterval`, `clearTimeout`을 `clearInterval`로 바꾸기만 하면 사용법 동일
 
<br>

## 윈도우 위치 및 크기 조절
- `window.moveBy(5, 10)`
  + 윈도우를 오른쪽으로 5px, 아래로 10px 이동
- `window.moveTo(5, 10)`
  + 윈도우를 (5, 10) 위치로 이동
- `window.resizeBy(-5, 10)`
  + 윈도우 크기를 가로 5px 작게, 세로 10px 길게 변경
- `window.resizeTo(200, 300)`
  + 윈도우 크기를 200px * 300px으로 변경
- `window.scrollBy(0, 10)`
  + 윈도우를 위로 10px 스크롤
- `window.scrollTo(0, 200)`
  + 윈도우 좌측상단이 (0, 200)이 되도록 스크롤
 
<br>

## 프린트
- `window.print()`, `print()`
  + 로드된 웹 페이지 프린트
- `onbeforeprint`, `onafterprint` : 각각 프린트가 되기 전, 후에 실행되는 이벤트 리스너

<br>

## location 객체
- 윈도우에 로드된 웹페이지 URL 정보를 갖는 객체
- `window.location`, `location` 으로 사용
  + 다른 URL값 대입 시 그 페이지 로드
```javascript
// location을 사용한 웹 페이지 로드 예제 
window.location = "http://www.naver.com";
window.location.hreg = "http://www.naver.com";
window.location.assign("http://www.naver.com");
window.location.replace("http://www.naver.com");
```

<br>

## navigator 객체
- 브라우저 자체에 대한 정보를 갖는 객체
- `window.navigator`, `navigator`
```javascript
navigator.appCodeName;  // Mozilla
navigator.appName;  // Netscape
navigator.appVersion;  // 5.0 (Windows NT; Win64; x64) ...
navigator.userAgent;  // Mozilla/5.0 (Windows NT; Win64; x64) ...
navigator.vendor;  // Google Inc.
...
```
<br>

## screen 객체
- 브라우저가 실행되고 있는 스크린에 대한 정보를 갖는 객체
- `window.screen`, `screen`
```javascript
screen.availHeight;  // 1392 (작업표시줄 높이 제외)
screen.availWidth;  // 2560
screen.colorDepth;  // 24
screen.pixelDepth;  // 24
...
```
<br>

## history 객체
- 사용자가 방문한 웹 페이지 정보 저장하는 객체
- `window.history`, `history`
- `history.back()`, `history.go(-1)`
  + 이전 페이지로 이동한다
- `history.forward()`, `history.go(1)`
  + 다음 페이지로 이동한다
