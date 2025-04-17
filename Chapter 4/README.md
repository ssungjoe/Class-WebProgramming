# Chapter 4. CSS3

<br>

## CSS의 구성
- `selector`, `property`, `value`, 주석문(`/* text */`)
  + 대소문자 구분 없음

```css
span {
  color : blue;
  font-size : 20px;
  /* 모든 span 태그에 적용 */
}
```

<br>

## 사용법
- `<style></style>` 태그 생성 후 안에 CSS 코드를 작성한다.
  + `<style>` 태그 안에서 `@import "my_css_code.css";` 를 통해 외부 `.css` 확장자를 가진 문서를 불러올 수도 있다.
```html
<head>
  <style>
    span {
      color : blue;
      font-size : 20px;
    }
  </style>
</head>

<head>
  <style>
    @import "my_css_code.css";
  </style>
</head>
```
- 또는 `.css` 확장자를 가진 파일을 `<link>` 태그를 활용해 불러온다
  + 이 방식을 더 추천한다
```html
<head>
  <link href="my_css_code.css" type="text/css" rel="stylesheet">
</head>
```

<br>

## 상속
- CSS로 부터 지정된 스타일에 대해 child element는 parent element로 부터 상속을 받는다
- 예컨데 parent element인 `<p>`에 대한 CSS 정보도 child element인 `<em>`이 그대로 상속받는다
```html
<p style="color:red">child element는 parent element로부터 스타일을
  <em style="font-size:20px">상속</em>받는다.
</p>
```
> 실행결과
> <br>
> ![Image](https://github.com/user-attachments/assets/ac4e6955-f3f1-484a-8592-9e01db7d5877)

<br>

## 스타일 합치기와 오버라이딩
- cascading (스타일 합치기) : 여러 스타일 시트가 특정 태그에 동시 적용 될 때 합쳐져서 적용
  + 웹 브라우저의 default style
  + `.css` 문서에 작성된 style
  + `<style></style>` 태그에 작성된 style
  + 특정 태그의 `style` 속성에 작성된 style
- overriding (덮어쓰기) : 스타일이 합쳐지면서 특정 태그에 대해 같은 `property`에 대해 서로 다른 `value`를 지정했을 수도 있음
  + 이 때 우선순위가 높은 순으로 나열하면 위에서 언급한 4가지의 역순이다. (`style` 속성에 작성된 style이 가장 우선도가 높다)
 
<br>

## 셀렉터
- 특정 태그의 이름, `class`, `id`를 선택해 차별적으로 스타일을 적용시킴
- 이름 셀렉터로 이름이 `h3`, `li`인 태그만 빨간 글씨로 만드는 예제 :
```css
h3, li { color : red; }
```
```html
<h3>Web Programming</h3>
<hr>
<h4>학습 내용</h4>
<ul>
  <li>HTML5</li>
  <li>CSS3</li>
  <li>Javascript</li>
</ul>
```

> 실행결과
> <br>
> ![Image](https://github.com/user-attachments/assets/91f91234-d05b-41ea-abdd-17b0644d8109)

- class 셀렉터로 class 이름이 `warning`, `subject`인 태그만 변경하는 예제 :
```css
.warning { color : red; }
h3.subject { color : blue; }
```
```html
<h3 class="subject">Web Programming</h3>
<hr>
<h4>학습 내용</h4>
<ul>
  <li>HTML5</li>
  <li>CSS3</li>
  <li class="warning">Javascript</li>
</ul>
```
> 실행결과
> <br>
> ![image](https://github.com/user-attachments/assets/21f2c5c0-a387-4a52-aaaf-31f6d6ec04bc)

- id 셀렉터로 id 이름이 `list`인 태그만 변경하는 예제:
```css
#list { color : red; }
```
```html
<h3>Web Programming</h3>
<hr>
<h4>학습 내용</h4>
<ul id="list">
  <li>HTML5</li>
  <li>CSS3</li>
  <li>Javascript</li>
</ul>
```
> 실행결과
> <br>
> ![image](https://github.com/user-attachments/assets/7b69fbf8-45af-46e8-a1ec-f959e0dd0dcd)

- 전체 셀렉터 : `*`을 사용해 지정
```css
* { color : blue; }
```

- 속성 셀렉터 : 특정 속성에 대해 값이 일치하는 속성만 지정
  + 다음은 `<input type="text">`인 모든 태그를 지정하는 CSS코드이다.
```css
input[type=text] { color : red; }
```

<br>

## 가상 클래스 셀렉터
- 가상 클래스 셀렉터 : 특정 상황에서 발동되는 셀렉터, 띄어쓰기를 해서 쓰면 안되는 점 유의
- `:visited` : 방문했던 링크에 대해 지정
```css
/* 방문했던 링크의 텍스트 색을 초록색으로 지정 */
a:visited { color : green; }
```
- `:hover` : 해당 태그에 마우스가 올라올 시 지정
```css
/* <li> 태그 위에 마우스가 올라갈 시 배경을 노란색으로 지정*/
li:hover { background : yellow; }
```
- `:nth-child(even)`, `:nth-child(-2n+5)`, ...
  + 특정 순서에 있는 child element만 지정 

<br>

## 셀렉터 조합
- child selector (자식 셀렉터) : `>` 사용
- descendent selector (자손 셀렉터) : 띄어쓰기로 나열
```css
/* div의 자식 strong에 적용 */
div > strong { background : dodgerblue; }

/* ul의 자손 strong에 적용 */
ul strong { background : yellow; }
```
```html
<h3>Web Programming</h3>
<hr>
<div>
  <div>1학기 <strong>학습 내용</strong></div>
  <ul id="list">
    <li>HTML5</li>
    <li><strong>CSS3</strong></li>
    <li>Javascript</li>
  </ul>
<div>
```
> 실행결과
> <br>
> ![image](https://github.com/user-attachments/assets/8dc64119-0e5b-4b5b-ae3f-cdb0f523c7c6)

<br>

## 색 사용

- 16진수 코드 `#rrggbb` 사용
```css
div { color : #8A2BE2; }
```
- r, g, b 각 성분을 10진수로 표현
```css
div { color : rgb(130, 43, 226); }
```
- 색 이름 사용
```css
div { color : blueviolet; }
```
- 색 관련 속성
  + `color` : 텍스트 색
  + `background-color` : 배경 색
  + `border-color` : 테두리 색

<br>

## 텍스트 꾸미기
- 들여쓰기
  + `text-indent` : `3em`, `10%`, ...
- 글자 정렬
  + `text-align` : `left`, `right`, `center`, `justify`(양쪽정렬)
- 텍스트 꾸미기
  + `text-decoration` : `none`, `underline`, `overline`, `line-through`
  + `none`을 활용해서 `<a>`태그에서 하이퍼링크 밑줄 안나오게 할 수 있음
 
<br>

## 표준 단위
|단위 |뜻                   |
|-----|--------------------|
|`em` |폰트의 n배           |
|`%`  |폰트의 n%            |
|`px` |n픽셀 크기           |
|`cm` |n센티미터            |
|`mm` |n밀리미터            |
|`in` |n인치                |
|`pt` |n포인트              |
|`pc` |n피카소(1`pc`=12`pt`)|
|`deg`|각도 n도             |

<br>

## 폰트
- 사용할 폰트 선언
  + `font-family` : `Arial`, `"Times New Roman"`, `Serif`
  + `Arial`을 우선적으로 사용, 없으면 `"Times New Roman"` 사용, 없으면 `Serif` 사용
  + 이름에 공백이 있는 경우 입력할 때 `""`를 사용한다
- 폰트 크기
  + `font-size` : `40px`, `medium`, `1.6em`, ...
- 폰트 스타일
  + `font-style` : `normal`, `italic`(필기체), `oblique`(기울임체)
- 폰트 굵기
  + `font-weight` : `300`(100 ~ 900), `normal`(400), `bold`(700)
- 단축 속성 `font`
  + 폰트 스타일, 굵기, 크기, 폰트 종류를 한번에 선언 가능
  + 크기, 종류는 필수 항목
  ```css
  div { font : italic bold 20px consolas, sans-serif; }
  ```
  ```css
  div { font : 20px consolas, sans-serif; }  /* 필수 항목 */
  ```

<br>

## 박스 모델
- 콘텐츠 : 태그 내부 텍스트 또는 이미지
- `padding` : 콘텐츠를 둘러싸고 있는 내부 여백
  + 패딩은 색 없음, 크기만 조절
- `border` : `padding` 외부의 테두리
  + 두께, 색, 테두리 모양 등 조절 가능
- `margin` : 바깥 영역의 영역
  + 마진은 색 없음, 크기만 조절

<br>

![image](https://github.com/user-attachments/assets/514495be-5274-4670-843e-2adb7f7a1fa4)

- 당연히 CSS로 박스 제어 가능
```css
div {
  width: 150px;
  height: 50px;
  /* 패딩, 보더, 마진 제어 */
  margin: 40px;
  border-width: 30px;
  padding: 20px;
}
```
<br>

## 테두리(border) 꾸미기
- `border`의 속성들
  + `border-width` : `3px`, `medium`, ...
  + `border-style` : `none`, `hidden`, `dotted`, `solid`, `double`, ...
  + `border-color` : `blue`, ...
- 특정한 방향에 대해서만 제어 가능
  + `border-left-width` : `3px`, ...
  + `border-left-style` : `dotted`, ...
  + `border-left-color` : `blue`, ...
- 단축 속성 `border`
  ```css
  div { font : 3px dotted blue; }
  ```
- 둥근 모서리 `border`
  + 모든 방향 둥글게 : `border-radius: 50px`
  + 특정 방향 둥글게 : `border-radius: 0px 20px 40px 60px` (아래 사진에서 1, 2, 3 ,4번 순으로 적용됨)
<br>

![image](https://github.com/user-attachments/assets/eb227d81-46ae-4900-af9a-72168192814c)

- 테두리를 특정 이미지로 만들기
  + (주의) `border-width`가 `0`이면 당연히 이미지가 안보이고, `border-style`을 `soild`로 지정해줘야 한다
  + `border-image: url("path/image.png") 30 round`
  + `30`: `30px` 만큼 이미지 모서리를 떼서 `border`의 모서리에 배치
  + `round` : `border`의 edge부분 이미지 반복

<br>

## 배경
- 배경 채우기
  + `background-color` : `skyblue`, ...
  + `background-image` : `url("path/image.png")`
- 배경 이미지 조정(위치, 크기, 반복여부)
  + `background-position` : `left top`(기본), `center center`, ... (`left/center/right` `top/center/bottom` 원하는 대로 조합)
  + `background-size` : `100px 100px`
  + `background-repeat` : `repeat`(기본), `no-repeat`, `repeat-x`, `repeat-y`
- 단축 속성 `background`
```css
div { background : skyblue url("path/image.png") center center/100px 100px repeat-y; }
```

<br>

## 그림자
- 텍스트 그림자 `text-shadow : (h-shadow) (v-shadow) (blur-radius) (color)`
  + `h-shadow`(필수) : `3px` (텍스트, 그림자 수평거리)
  + `v-shadow`(필수) : `3px` (텍스트, 그림자 수직거리)
  + `blur-radius` : `5px` (그림자 번짐 정도)
  + `color` : `red` (색지정)
```css
div#shadow { text-shadow : 3px 3px red; }
div#blur { text-shadow : 3px 3px 5px red; }  /* 번짐 추가 */
div#multiple { text-shadow : 3px 3px 5px black,
                             0px 0px 25px blue,
                             0px 0px 5px darkblue; }  /* 여러 효과 동시 적용 가능 */
```
- 박스모델 그림자 `box-shadow : (h-shadow) (v-shadow) (blur-radius) (spread-radius) (color)`
  + 텍스트 그림자와 이름 같은 속성은 동일한 기능
  + `spread-radius` : 그림자 크기
```css
div#shadow { box-shadow : 10px 10px red; }
div#blur { box-shadow : 10px 10px 5px red; }  /* 번짐 추가 */
div#multiple { box-shadow : 3px 3px 5px black,
                            0px 0px 25px blue,
                            0px 0px 5px darkblue; }  /* 여러 효과 동시 적용 가능 */
```

<br>

## 마우스 커서 모양
- `cursor` (지정한 태그 위에 마우스를 올릴 때의 커서모양 지정)
  + 지정할 수 있는 종류는 아래와 같다
<br>

![image](https://github.com/user-attachments/assets/d2c64eb7-514a-4fdc-8a22-1c9b524e8f46)
