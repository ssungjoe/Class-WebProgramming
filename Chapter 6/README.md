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
<script>
function over(obj) {
  obj.src = "media/banana.png";
}
function out(obj) {
  obj.src = "media/apple.png";
}
</script>
```
`...`
```html
<img src="media/apple.png" alt="img" onmouseover="over(this)" onmouseout="out(this)">
```