# Chapter 8. HTML DOM과 Document

<br>

## JS 객체 종류
- 코어 객체
  + JS에서 항상 활용 가능한 기본 객체
  + 7장 내용 참고
- HTML DOM 객체
  + 각 HTML 태그들을 하나의 객체로 만듦, JS에서 HTML 태그 동적 제어
  + `<p></p>` 태그이면 `p` 객체로, `<div></div>`이면 `div` 객체로 생성
- BOM 객체
  + 브라우저에 관한 정보 제공 또는 모양 제어가 가능한 객체
  + 10장 내용 참고

<br>

## HTML DOM
- DOM 트리
  + DOM 객체들을 HTML 태그들의 포함관계에 따라 트리 구조로 분류
```
                   document
                       |
                      html
          ______________|______________
         |                             |
       head                          body
       |         ___________________________________________
   ____|____     |             |              |            |
  |         |  header         main         footer         (etc)
title     meta               ____|____
                          section   section
                          ____|__    ____|____
                         |       |  |        |
                        h1       p h2       ul
                                         ____|____
                                        |    |    |
                                       li   li   li
```

- DOM 트리 특징
  + DOM 트리의 루트는 `document` 객체 (주의 : `document` 객체는 DOM 객체가 아님)
  + DOM 객체의 종류는 HTML 태그 종류만큼 존재
  + HTML 태그 당 DOM 객체가 하나씩 대응해 생성
  + DOM 트리는 HTML 태그 포함관계에 따라 부모 자식 관계로 구성
 
- DOM 객체 구성요소
  + `property` : DOM 객체 내부 변수
  + `method` : DOM 객체 내부 함수
  + `collection` : 특정 정보 표현하는 배열, ex) children collection : 모든 자식 DOM 객체 주소 포함
  + `event listener` : 9장 내용 참고
  + CSS3 스타일
 
- DOM 객체 사이 관계 표현 (`property` 이름 소개)
  + `parentElement` : 부모 객체
  + `children` : 자식 객체들 `collection`
  + `firstElementChild` : 첫번째 자식 객체
  + `lastElementChild` : 마지막 자식 객체
  + `previousElementSibling` : 왼쪽 형제 객체 (없으면 `null`)
  + `nextElementSibling` : 오른쪽 형제 객체 (없으면 `null`)
  + ...
 
<br>

## DOM 객체 구분
- `document.getElementById("name")` : id가 `name`인 DOM 객체 지정
```javascript
let name = document.getElementById("name");
name.style.color = "red";
```
- 기타 CSS3 스타일 동적 변경
  + `style.backgroundColor` : 배경색 지정
  + `style.cssText` : css 문법 문자열로 그대로 작성
  + 기타 `color`, `fontSize`, `display`, `width`, `border`, `margin` 등 아주 다양함
- `tag.innerHTML`
  + `tag` DOM 객체 내부의 HTML 콘텐츠를 얻어내거나 수정할 수 있다
- `this`
  + DOM 객체 자기 자신을 가르킴
```html
<div onclick="this.style.backgroundColor='orange'"></div>
```

<br>

## document 객체 찾기
- `document` 객체를 통해 하위 태그 컬랙션에 접근
- 이벤트 리스너 등록 가능
- `getElementsByTagName()` : 태그 이름으로 DOM 객체 접근
- `getElementsByClassName()` : class 이름으로 DOM 객체 접근

<br>

## 브라우저 텍스트 작성
- `document.write()` : 브라우저에 텍스트 출력
- `document.writeln()` : 줄바꿈까지 붙여서 텍스트 출력
- `document.open()` : 현재 HTML 텍스트 모두 삭제, 새로운 HTML 받아들임
- `document.close()` : HTML 텍스트를 덧붙일 수 없음
```javascript
let newWin = window.open("", "outWin", "");
newWin.document.open();
newWin.document.write
newWin.document.close();
```

<br>

## DOM 객체 동적 생성/추가/삭제
- `document.createElement("TAG_NAME")`
- `setAttribute("id", "TAG_ID")`
- `appendChild(newTag)`
```javascript
let newTag = document.createElement("div");  // div 태그 생성
let parent = document.getElementById("p");  // 원래 문서에 있는 p 태그 찾기
newTag.setAttribute("id", "newDiv");  // 새 div 태그의 id를 newDiv로 설정
parent.appendChild(newTag);  // p 태그의 자식으로 div 태그를 새로 추가
```
- `removeChild(myTag)`
```javascript
let myTag = document.getElementById("awesomeId");
let parent = myTag.parentElement;
parent.removeChild(myTag);
```
