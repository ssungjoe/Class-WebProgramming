# Chapter 5. CSS3 고급

<br>

## CSS 프로퍼티 종류
+ `display`
+ `position`
+ `left`, `right`, `top`, `bottom`
+ `float`
+ `z-index`
+ `visibility`
+ `overflow`
<br>

## 블록, 인라인 박스
- `display` : `block`, `inline`, `inline-block`
  + `block` : 한 줄을 독점적으로 차지, 크기 조절 가능
  + `inline` : 연속으로 나열, 새 줄로 변경 불가
  + `inline-block` : `inline`이면서 크기, `margin`, `padding` 조절 가능

  ![image](https://github.com/user-attachments/assets/634a3225-911b-4132-8c37-cdf04126d456)

<br>

## 배치
- `position` : `static`(기본), `relative`, `absolute`, `fixed`
  + `static` : 정적 배치 (`left`, `right`, `top`, `bottom`의 영향을 안받음)
  + `relative` : 상대 배치 (`left`, `right`, `top`, `bottom`의 영향을 받음)
  + `absolute` : 절대 배치 (브라우저의 크기가 변해도 태그 위치가 변하지 않음)
  + `fixed` : 특정 위치에 고정 (스크롤을 내려도 따라서 내려옴)
```css
#static {
  display: inline-block;
  position: static;
}

/* id가 relative인 태그를 원래 위치보다 왼쪽으로 -20, 위로 20만큼 이동 */
#relative {
  display: inline-block;
  position: relative;
  left: 20px;
  top: 20px;
}

/* id가 absolute인 15*20 크기의 태그를 (100, 80) 위치에서 바뀌지 않도록 함 */
#absolute {
  display: inline-block;
  position: absolute;
  height: 20px;
  width: 15px;
  left: 100px;
  top: 80px;
}

/* id가 fixed인 너비가 100인 태그를 브라우저 창에서 오른쪽으로부터 10, 밑로부터 10만큼 떨어진 위치에 고정 */
#fixed {
  position: fixed;
  bottom: 10px;
  right: 10px;
  width: 100px;
}
```

<img src="https://github.com/user-attachments/assets/7af39fcb-5f8a-4470-91b7-6570b7c015c5" width="80%" />
<br><br>

- `float` : `left`, `right`
  + 태그를 항상 오른편이나 왼편에 배치할 수 있음
```css
#right {
  float: right;
  width: 8em;
  padding: 0.25em;
  margin: 1em;
}
```

<img src="https://github.com/user-attachments/assets/07187459-4cca-4b64-a24c-9de776ee44cb" width="30%" />

<br><br>

## 수직방향 우선도
- `z-index` : `-3`, `2`, ... (높은 순으로 위쪽 위치)
```css
div { z-index : 3; }
```

<br>

## 숨기기
- `visibility` : `hidden`, `visible`
  + `hidden` 상태라고 아무것도 없는 `display: none`이랑 같은게 아니라, 태그의 공간은 할당된다
  + 예시로 어떤 단어를 포함하는 `<span>` 태그에 `hidden`을 적용시키면 단어 길이만큼 공백이 생겨있다
```css
span { visibility: hidden; }
```

<br>

## 박스 안 공간이 모자랄 때
- `overflow` : `visible`(기본), `hidden`, `scroll`, `auto`
  + `visible` : 내용이 넘쳐도 박스 영역을 넘어 모두 보여줌
  + `hidden` : 박스 영역을 넘는 부분은 잘림
  + `scroll` : 넘치는 부분을 스크롤 해서 볼 수 있게 해줌 (항상 스크롤바 존재)
  + `auto` : 넘칠 때만 스크롤바를 만듦

<img src="https://github.com/user-attachments/assets/dd5d83f9-1e16-453e-af1b-7a7421c48b9b" width="70%" />

<br>

## 리스트 꾸미기
- `list-style-type` : `square`, `circle`, `none`, `upper-roman`, `decimal`, `lower-alpha`, ...
  + 마커의 종류를 지정
- `list-style-image` : `url("path/marker.png")`
  + 마커를 특정 이미지로 지정
- `list-style-position` : `inside`, `outside`(기본)
  + 마커의 위치를 아이템 안쪽영역에 놓을지 바깥쪽에 놓을지 지정
- 단축 속성 `list-style`
```css
/* marker.png가 없을 시 circle을 사용, 안쪽배치 */
ul { list-style: circle inside url("path/marker.png"); }
```

<br>

## 표 꾸미기
- `border-collapse` : `collapse`
  + 이중으로 나타나는 표의 테두리를 하나로 합침
- `width` : `40px`, `height` : `100px`
  + 셀의 크기를 제어
- 기타 4장 이하에서도 배운 내용
  + 셀 여백 : `padding`
  + 정렬 : `text-align`
  + 배경색 : `background`
  + `border-bottom`(단축 속성) : `1px solid gray`(아래쪽 테두리 회색 1px 실선)
  + `tr:nth-child(even) { background: gray; }` (짝수 번째 행 배경색 회색 지정)

<br>

## 폼 꾸미기
- 속성 셀렉터 활용 : `input[type=submit]` 등
- 가상 셀렉터 `:focus`
  + 입력하기 위해 입력란을 클릭했을 때 발동
```css
input[type=text]:focus {
  /* 입력란 클릭 시 글자크기 120% 증가 */
  font-size: 120%;
}
```
- `:hover`를 이용해 입력창에 마우스를 올리면 변화를 줄 수도 있음

<br>

## CSS만으로 동적변화 주기
- `@keyframes`로 특정 시간별 애니메이션 지정
  + `@keyframes`에서 애니메이션 이름 `awesomeName`을 정한다
  + 애니메이션을 적용할 태그에 `animation-name: awesomeName`을 적용한다
  + 지속시간 `animation-duration`과 반복횟수 `animation-iteration-count`를 정한다
```css
@keyframes awesomeName {
  0% { font-size : 100%; }
  30% { font-size : 200%; }
  100% { font-size : 500%; }
}

span {
  animation-name: awesomeName;
  animation-duration: 3s;
  animation-iteration-count: infinite;
}
```

<br>

## 전환
- `transition : (속성) (시간)`
  + 특정 태그에 대해 `(속성)`이 바뀌면, 바로 바뀌는게 아니라 `(시간)`동안 천천히 전환되도록 해준다
  + 예를 들어 `:hover`를 통해 글자크기가 500% 바뀌도록 하면 원래대로면 마우스를 올리자마자 500%로 바뀐다
  + 그런데 `transition: font-size 5s`를 적용하면 글자크기가 5초동안 천천히 바뀌게 된다
 
```css
span {
  transition: font-size 5s;
}
span:hover {
  font-size: 500%;
}
```

<br>

## 변환
- `transform` : `rotate(20deg)`, `scale(3, 1)`, `skew(0deg, -60deg)`, `translate(30px, 100px)`, ...
  + 특정 태그에 대해 `rotate`(회전), `scale`(확대/축소), `skew`(기울임), `translate`(평행이동)을 적용할 수 있다
  + 동시에도 적용 가능하다
```css
/* 회전 */
#rotate:hover {
  transform: rotate(20deg);
}
/* 확대/축소 */
#scale:hover {
  transform: scale(3, 0.5);
}
/* 기울임 */
#skew:hover {
  transform: skew(0deg, -60deg);
}
/* 평행이동 */
#translate:hover {
  transform: translate(30px, 100px);
}
/* 동시적용 */
#change:hover {
  transform: rotate(20deg) scale(3, 0.5);
}
```
<img src="https://github.com/user-attachments/assets/9f44e336-4a8f-4c3a-b67d-2ed8e165ebc2" width="60%" />
