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
