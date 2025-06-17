# Chapter 11. HTML5 캔버스 그래픽

<br>

## 캔버스
- 이미지 파일을 `<img>` 태그 또는 기타 플러그인 없이 자유롭게 출력
- `<canvas></canvas>` 태그 사용
```html
<canvas id="CANVAS_ID"
        style="AWESOME_CSS"
        width="300"
        height="300">
  브라우저가 canvas태그를 지원하지 않음
</canvas>
```
- Context : 캔버스에 그림을 그리는 도구
```javascript
let canvas = document.getElementById("myCanvas");
let context = canvas.getContext("2d");  // 컨텍스트 얻어내기
```
- Context 객체를 활용한 캔버스에 그리기
  + 다양한 Context 객체의 프로퍼티, 메소드들이 있음
- 방법 1 : `beginPath()`로 빈 경로를 만들고, 경로에 도형을 모아놓고 한번에 캔버스에 그리기
  + 경로를 그리다가 다시 시작하려면 다시 `beginPath()`를 사용하면 됨
  + `closePath()`는 시작점과 마지막점을 직선으로 연결하는 경로 추가
  + `moveTo()`, `lineTo()`, `rect()`, `arc()`, `fill()`, `stroke()`, `closePath()`...
```javascript
context.beginPath();  // 이전 경로 초기화 및 빈 경로 시작
context.strockStyle = "blue";  // blue 색 선 사용
context.rect(60, 60, 50 ,50);  // (60, 60)에 50 * 50 크기 사각형을 추가
context.stroke();  // 앞서 구성된 도형을 캔버스에 그림
```
- 방법 2 : 경로에 담지 않고 바로 캔버스에 그리기
  + `clearRect()`, `fillRect()`, `strockRect()`, `strokeText()`, `drawImage()`, ...
```javascript
context.font = "20px Gothic";  // 폰트를 20px 크기의 Gothic으로 설정
context.fillStyle = "green";  // 색을 green으로 설정 
context.fillText("Text in Canvas", 100, 50);  //fillText 메소드는 경로 추가가 필요없음
```
- `canvas.width`, `canvas.height` : 캔버스의 크기를 알아냄
- `canvas.style.backgroundColor` : 캔버스의 배경색 제어

<br>

## 선 그리기
- `moveTo(x, y)` : (x, y)로 시작점 설정
- `lineTo(x, y)` : 현재 위치에서 (x, y)까지의 직선을 경로에 추가

<br>

## 도형 그리기
- `rect()`, `strokeRect()`의 차이
  + `rect`는 사각형을 경로 상에 추가하고, `strokeRect`는 캔버스에 바로 그려버린다
```javascript
context.rect(10, 10, 100, 100);
context.stroke();
```
```javascript
context.strokeRect(10, 10, 100, 100);
```
- `fillRect()` : 채워진 사각형 그리기
- `fill()` : 닫힌 경로 내부 칠하기
- `arc(x, y, radius, from, to)` : 원호 그리기
```javascript
context.beginPath();
context.moveTo(20, 20);  // 원호의 중심을 (20, 20)으로 설정
context.arc(20, 20, 50, 0, 1.5 * Math.PI);  // 반지름이 50px, 0 ~ 3PI/2 구간의 원호를 경로에 추가
context.closePath();
context.fillStyle = "green";
context.fill();
```

<br>

## 캔버스 지우기
- `clearRect()`를 활용한다
```javascript
context.clearRect(0, 0, canvas.width, canvas.height);  // 캔버스 초기화
context.beginPath();  // 경로 초기화
```

<br>

## 꾸미기
- `strokeStyle` : 선 색 지정
- `fillStyle` : 채우기 색 지정
- `lineWidth` : 선 굵기 지정

<br>

## 텍스트
- `strokeText` : 외곽선만 있는 텍스트 그리기
- `fillText` : 채워진 텍스트 그리기
- `font` : 텍스트 폰트 지정
- `textAlign` : 텍스트 정렬
