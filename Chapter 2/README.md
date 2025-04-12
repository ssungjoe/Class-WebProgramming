# Chapter 2. 기본 문서

<br>

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
> 실행결과
> <h1>Chapter 1</h1>
> <h2>1.1 HTML document</h2>
> <h3>1.1.1 Web</h3>
> <h4>1.1.1.1 Internet</h4>
> <h5>Example</h5>
> <h6>details in example</h6>

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
> 실행결과
> <p>This is First paragraph</p>
> <p>This is Second paragraph</p>

<br>

## 수평선
```html
<hr>
```

<br>

## 줄넘김
```html
<br>
```

<br>

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
>  실행결과
> <pre>여러 개의 빈 칸은 하나로
>       여러 줄은 한 줄에 붙여서 출력된다</pre>

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

<br>

## 메타 정보 표현
- 웹페이지의 기본 URL 지정 : `<base>`
```html
<head>
      <base href="http://www.example.com/score/">
</head>
```
> 이때의 `href` 속성은 `<a></a>`로도 특정 웹페이지 URL을 표시하는데 사용 가능
> ```html
> <a href="math.html"></a>
> ```

- 메타 데이터 (웹페이지 제작자, 인코딩 방식, 문서내용 등등) 표현 : `<meta>`
```html
<meta name="author" content="ssungjoe">
```
```html
<meta name="description" content="information of this website">
```
```html
<meta name="keywords" content="HTML, CSS, JS">
```
```html
<meta charset="UTF-8">
```
-  이외에도 `<link>`, `<script>`, `<style>`, `<title>` 등의 태그 존재

<br>

## 이미지 삽입
- `<img>` 태그 활용
```html
<img src="URL(필수)"
     alt="이미지가 없을 때 표시되는 문자열(필수)"
     width="폭"
     height="높이">
```
<br>

## 리스트
- 순서 있는 리스트 : `<ol></ol>`
  + `type` : 마커 지정 속성 (`1`, `A`, `a`, `I`, `i` 등)
  + `start` : 마커의 시작값 속성 (기본값 : `"value"`)
```html
<ol type="1" start="3"> 
      <li>아이템1</li>
      <li>아이템2</li>
      <li>아이템3</li>
</ol>
```
> 실행결과
> <ol type="1" start="3">
>       <li>아이템1</li>
>       <li>아이템2</li>
>       <li>아이템3</li>
> </ol>

- 순서 없는 리스트 : `<ul></ul>`
```html
<ul> 
      <li>아이템1</li>
      <li>아이템2</li>
      <li>아이템3</li>
</ul>
```
> 실행결과
> <ul> 
>       <li>아이템1</li>
>       <li>아이템2</li>
>       <li>아이템3</li>
> </ul>

- 용어 정의 리스트 : `<dl></dl>`
  + 용어 이름 : `<dt></dt>`
  + 용어 설명 : `<dd></dd>`
```html
<dl>
      <dt>용어</dt>
      <dd>설명</dd>
</dl>
```
> 실행결과
> <dl>
>       <dt>용어</dt>
>       <dd>설명</dd>
> </dl>

<br>

## 표 만들기
- 기본적으로 `<table></table>` 태그를 활용해 만든다.
  + 표 제목 : <caption></caption>`
  + 헤딩 셀 : `<thead></thead>`
  + 데이터 셀 : `<tbody></tbody>`
  + 바닥 셀 : `<tfoot></tfoot>`
  + 행 : `<tr></tr>`, 여러 개의 `<td></td>`, `<th></th>`를 포함
  + 열(헤딩, 바닥 셀) : `<th></th>`
  + 열(데이터 셀) : `<td></td>`

- 예제
```html
<table>
      <caption>표 제목</caption>
      <thead>
            <tr>
                  <th>이름</th>
                  <th>HTML</th>
                  <th>CSS</th>
            </tr>
      </thead>
      <tbody>
            <tr>
                  <td>Apricot</td>
                  <td>80점</td>
                  <td>70점</td>
            </tr>
            <tr>
                  <td>Banana</td>
                  <td>95점</td>
                  <td>99점</td>
            </tr>
            <tr>
                  <td>Cake</td>
                  <td>40점</td>
                  <td>61점</td>
            </tr>
      </tbody>
      <tfoot>
            <tr>
                  <th>합계</th>
                  <th>225점</th>
                  <th>230점</th>
            </tr>
      </tfoot>
</table>
```
> 실행결과
> <table>
>       <caption>표 제목</caption>
>       <thead>
>             <tr><th>이름</th><th>HTML</th><th>CSS</th></tr>
>       </thead>
>       <tbody>
>             <tr><td>Apricot</td><td>80점</td><td>70점</td></tr>
>             <tr><td>Banana</td><td>95점</td><td>99점</td></tr>
>             <tr><td>Cake</td><td>40점</td><td>61점</td></tr>
>       </tbody>
>       <tfoot>
>             <tr><th>합계</th><th>225점</th><th>230점</th></tr>
>       </tfoot>
> </table>

- `<td></td>`에 `<img>` 태그를 활용해 이미지를 삽입할 수도 있다.

<br>

## 하이퍼링크
- `<a></a>` 태그를 활용한다.
  + 이동할 URL 또는 앵커 속성 (`"URL"`, `"#앵커이름"`) : `href`
  + 페이지가 출력될 윈도우 이름 지정 속성 : `target`
  + 다운로드 여부 속성 : `download`
```html
<a href="http://www.google.co.kr">구글</a>
```
```html
<a href="http://www.naver.com" alt="네이버">
      <img src="/asset/2025_naver_logo.png">
</a>
```

> 실행결과
> <br>
> <a href="http://www.google.co.kr">구글</a>
> <br>
> <a href="http://www.naver.com" alt="네이버">
>       <img src="https://github.com/ssungjoe/Class-WebProgramming/blob/main/Chapter%202/asset/2025_naver_logo.png?raw=true" width="15%">
> </a>

- `target` 속성 사용법
  + `"_blank"`, `"_self"`, `"_parent"`, `"_top"`, `"윈도우 이름"`

<br>

## 앵커 만들기 (id 속성)
- 앵커란? 문서의 특정 위치
- 태그에 `id`를 `"앵커이름"`지정하고, `href` 속성으로 호출을 할 때 `"#앵커이름"`으로 호출하면 된다.
- 이렇게 하면 하이퍼링크를 통해 이동 시 `id`를 지정했던 태그의 위치로 이동된다.
```html
<h2>Full table of contents</h2>
<a href="#intro">1 Introduction</a>
<ol>
      <li>1.1 Where does this specification fit?</li>
      <li>1.2 Is this HTML5?</li>
      <li>1.3 Background</li>
      <li>1.4 Audience</li>
      <li>and more...</li>
</ol>

<hr>

<h3 id="intro">1 Introduction</h3>
<h3>1.1 Where does this specification fit?</h3>
This specification defines a big part of the web platform, in lots of detail. Its ......
```

> 실행결과
> <h2>Full table of contents</h2>
> <a href="#intro">1 Introduction</a>
> <ol>
>       <li>1.1 Where does this specification fit?</li>
>       <li>1.2 Is this HTML5?</li>
>       <li>1.3 Background</li>
>       <li>1.4 Audience</li>
>       <li>and more...</li>
> </ol>
> 
> <hr>
> 
> <h3 id="intro">1 Introduction</h3>
> <h3>1.1 Where does this specification fit?</h3>
> This specification defines a big part of the web platform, in lots of detail. Its ......

<br>

## 인라인 프레임 (웹 페이지 안에 웹 페이지)
- `<iframe></iframe>` 태그 활용
```html
<iframe src="http://www.etnews.com" width="300" height="300">
      ifram 태그를 지원하지 않는 브라우저일 시 해당 텍스트 출력
</iframe>
```

<br>

## 미디어 삽입
- 비디오 삽입 : `<video></video>` 태그 활용
  + 재생, 재생시간, 중단, 음소거 등의 버튼 표시 속성 : `controls`
  + 비디오 로딩 즉시 재생 속성 : `autoplay`
  + 반복 재생 속성 : `loop`
  + 음소거 속성 : `muted`
```html
<video src="apricot.mp4" width="320" height="240" controls>
</video>
```
- 재생 가능한 비디오 1개 재생하기 (빠른 순 우선)
```html
<video width="320" height="240" controls>
      <source src="apricot.mp4" type="video/mp4">
      <source src="apricot.webm" type="video/webm">
      <source src="apricot.ogg" type="video/ogg">
      video 태그를 지원하지 않는 브라우저일 시 해당 텍스트 출력
</video>
```
- 오디오 삽입 : `<audio></audio>` 태그 활용
  + `controls`, `autoplay`, `loop` 의 속성이 있음
```html
<audio src="banana.mp3" controls loop>
</audio>
```
- 재생 가능한 오디오 1개 재생하기 (빠른 순 우선)
  + `mp3`는 `source`내 `type`값이 `mpeg`임을 주의한다.
```html
<audio controls>
      <source src="banana.mp3" type="audio/mpeg">
      <source src="banana.wav" type="audio/wav">
      <source src="banana.ogg" type="audio/ogg">
      audio 태그를 지원하지 않는 브라우저일 시 해당 텍스트 출력
</audio>
```
