# Chapter 2. 기본 문서

## 기본 구성
- HTML5 문서 선언
```html
<!DOCTYPE html>
```

- 주석문
```html
<!-- 내용 -->
```

- 헤드, 바디
```html
<head></head>
```
```html
<body></body>
```

<br>

## 문서 제목
- head 태그 안에 ```<title>``` 사용
```html
<title>제목</title>
```

<br>

## 소제목
- ```<h1>```, ```<h2>```, ..., ```<h6>``` 태그 사용
```html
<h1>Chapter 1</h1>
<h2>1.1 HTML document</h2>
<h3>1.1.1 Web</h3>
<h4>1.1.1.1 Internet</h4>
<h5>Example</h5>
<h6>details in example</h6>
```
- 실행결과
<h1>Chapter 1</h1>
<h2>1.1 HTML document</h2>
<h3>1.1.1 Web</h3>
<h4>1.1.1.1 Internet</h4>
<h5>Example</h5>
<h6>details in example</h6>

<br>

## 툴팁
- 태그 안에 ```title``` 속성 추가
```html
<h1 title="this is tooltip">Chapter 1</h1>
```

<br>

## 단락 나누기
- ```<p>``` 태그 안에 내용 작성
```html
<p>This is First paragraph</p>
<p>This is Second paragraph</p>
```
- 실행결과
<p>This is First paragraph</p>
<p>This is Second paragraph</p>

## 수평선
```html
<hr>
```

## 줄넘김
```html
<br>
```

## 특정 문자의 엔터티 표현
- 주로 쓰이는 표현 3가지만 작성했음

| 문자 | 엔터티 표현 |
|------|-------------|
| `<`  | `&lt;`      |
| `>`  | `&gt;`      |
| 공백  | `&nbsp;`   |

<br>

## 개발자 포맷 그대로 출력
- ```<pre>```태그 활용
```html
<pre>여러 개의 빈 칸은 하나로
      여러 줄은 한 줄에 붙여서 출력된다</pre>
```
- 실행결과
<pre>여러 개의 빈 칸은 하나로
      여러 줄은 한 줄에 붙여서 출력된다</pre>

<br>

## 텍스트 꾸미기 (인라인 태그)
|태그                     |   결과                | 
|-------------------------|-----------------------|
|`<b>진하게</b>`           |<b>진하게</b>          |
|`<strong>중요한</strong>` |<strong>중요한</strong>|
|`<em>just 기울임</em>`    |<em>just 기울임</em>   |
|`<i>italic 기울임</i>`    |<i>italic 기울임</i>   |
|`<small>작게</small>`     |<small>작게</small>    |
|`<del>삭제</del>`         |<del>삭제</del>        |
|`<ins>밑줄</ins>`         |<ins>밑줄</ins>        |
|`문자<sup>윗첨자</sup>`   |문자<sup>윗첨자</sup>   |
|`문자<sub>아래첨자</sub>`  |문자<sub>아래첨자</sub>|
|`<mark>하이라이팅</mark>` |<mark>하이라이팅</mark> |

<br>

## 블록 태그
- 문단을 만들기 위한 태그 `<p></p>`
- 여러 태그들을 하나의 container로 묶는 `<div></div>`
- 텍스트의 특정 부분을 Javascript로 제어하기 위해 사용하는 `<span></span>`

