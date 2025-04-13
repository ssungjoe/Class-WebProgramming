# Chapter 3. 문서 구조화 및 웹 폼

<br>

## 시멘틱 웹
- 웹 문서를 만들 때 구조화를 해야하는 이유 : 검색엔진이 잘 찾도록 하기 위함
- e.g.  `<p>`, `<div>`, `<h1>`, ... 등의 태그 : 태그만 보고 무슨 의도로 내용물을 작성했는지 알기 어려움
- **시멘틱 태그** : `<header>`, `<section>`, `<article>`, `<main>`, `<summary>`, `<mark>`, `<time>`, ...등 문서의 구조의 의미를 표현하는 태그

<br>

## 시멘틱 태그
- `<header>` : 머리말 (문서 제목, 간단한 설명 등)
- `<nav>` : 하이퍼링크 모음 (주로 페이지 내 목차 제작에 쓰임)
- `<section>` : 문서의 장(chapter) 또는 절 구성에 사용
- `<article>` : 보조적인 글 (기사, 댓글 등)을 담는 영역
- `<aside>` : 페이지 왼쪽 혹은 오른쪽에 위치하는 관련기사, 노트 등을 담는 영역
- `<footer>` : 꼬리말 (저자 또는 저작권 정보 표시)

<br>

- 사용 예시

```html
<!DOCTYPE HTML>
<html>
  <head>
    <meta charset="UTF-8">
    <title>시멘틱 태그 활용</title>
  </head>
  <body>
    <header>
      <h1>Homogeneous한 상수 계수의 선형 미분방정식 해법</h1>
      <p>linear한 고차 미분 방정식이 homogeneous한 경우, 이에 대한 모든 해는 지수함수의 변형으로 구성된다.</p>
      <figure>
        <img src="/asset/homogeneous_linear.png">
        <figcaption>
          다음과 같이 linear한 선형 미분 방정식이 있을 때, 이에 대한 해는 y = e<sup>rx<sup>의 형태의 변형으로 이루어진다는 것이 알려져있다.
        </figcaption>
      </figure>
      <section>
        <arcicle id="distinct">
          <h2>Distinct real roots</h2>
          <img src="/asset/homogeneous_distinct.png">
          <p>r 이 서로 다른 실근의 형태일 때 위의 공식을 활용해 일반해 도출이 가능하다.</p>
        </article>
        <arcicle id="repeated">
          <h2>Repeated real roots</h2>
          <img src="/asset/homogeneous_repeated.png">
          <p>r 에 대한 반복되는 실근이 나타날 때 위와 같은 공식을 통해 일반해 도출이 가능하다.</p>
        </article>
        <arcicle id="complex">
          <h2>Complex roots</h2>
          <img src="/asset/homogeneous_complex.png">
          <p>r = a &plusmn; bi의 형태로 복소근이 나타날 때 위와 같은 공식을 통해 일반해를 도출할 수 있다.</p>
        </article>
        <aside id="legend">
          <h3>고계 방정식</h3>
          <p>그러나 r에 대한 해는 위처럼 정해져서 나오는 것이 아닌 아주 다양한 조합으로 나타난다. 이 때는 서로 다른 실근, 중복되는 근, 복소근을 각각 나눠서 위의 공식을 적용 후 더해서 합치면 일반해를 구할 수 있다.</p>
        </aside>
      </section>
      <footer>
        <p>2025.4.13 작성, Advanced Engineering Mathematics 7th edition, Dennis G. Zill</p>
      </footer>
  </body>
</html>
```

> 실행결과
> <header>
>       <h1>Homogeneous한 상수 계수의 선형 미분방정식</h1>
>       <p>linear한 고차 미분 방정식이 homogeneous한 경우, 이에 대한 모든 해는 지수함수의 변형으로 구성된다.</p>
>       <figure>
>         <img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/d6448ae7b70c9d121484836c5f0188b8e977ceef"><br>
>         <figcaption>
>           다음과 같이 linear한 선형 미분 방정식이 있을 때, 이에 대한 해는 y = e<sup>rx</sup> 형태의 변형으로 이루어진다는 것이 알려져있다.
>         </figcaption>
>       </figure>
>       <section>
>         <arcicle id="distinct">
>           <h2>Distinct real roots</h2>
>           <img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/807f878159dc9e297766bb6ff58749fc3d6b7f0d"><br>
>           <p>r 이 서로 다른 실근의 형태일 때 위의 공식을 활용해 일반해 도출이 가능하다.</p>
>         </article>
>         <arcicle id="repeated">
>           <h2>Repeated real roots</h2>
>           <img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/a13c30711e9b8db778130a5e83e0441ec58eb385"><br>
>           <p>r 에 대한 반복되는 실근이 나타날 때 위와 같은 공식을 통해 일반해 도출이 가능하다.</p>
>         </article>
>         <arcicle id="complex">
>           <h2>Complex roots</h2>
>           <img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/2ccc1f6b7404a456879bddfef3a3eed3cf7eec62"><br>
>           <p>r = a &plusmn; bi의 형태로 복소근이 나타날 때 위와 같은 공식을 통해 일반해를 도출할 수 있다.</p>
>         </article>
>         <aside id="legend">
>           <h3>고계 방정식</h3>
>           <p>그러나 r에 대한 해는 위처럼 정해져서 나오는 것이 아닌 아주 다양한 조합으로 나타난다. 이 때는 서로 다른 실근, 중복되는 근, 복소근을 각각 나눠서 위의 공식을 적용 후 더해서 합치면 일반해를 구할 수 있다.</p>
>        </aside>
>       </section>
>       <footer>
>         <p>2025.4.13 작성, Advanced Engineering Mathematics 7th edition, Dennis G. Zill</p>
>       </footer>

<br>

## 시멘틱 블록 태그
- `<figure></figure>` : 본문에 삽입된 그림, 영상, 소스코드 등을 하나로 블록화하는 태그
- `<details></details>` : 상세정보를 담는 태그, 접었다 펼쳤다하는 이점이 있음
  + `<details>` 의 제목을 표현할 때 안에 `<summary></summary>` 태그를 넣는다.
 
```html
<details>
  <summary>제목</summary>
  <p>내용</p>
</details>
```

> 실행결과
> <details>
>   <summary>제목</summary>
>   <p>내용</p>
> </details>

<br>

## 시멘틱 인라인 태그
- `<mark></mark>` : 텍스트 하이라이트
- `<time></time>` : 시간 정보를 나타낼 때 사용
```html
점심시간 <time>13:00</time>
```
- `<meter></meter>` : 데이터 양 표시 (% 또는 범위)
```html
<meter value="0.8" max="1.0">80%</meter>
```
- `<progress></progress>` : 진행 정도 표시
```html
20% <progress value="2" max="10"></progress>
```

<br>

## 웹 폼
- `<form></form>` : 사용자의 입력을 받기 위한 태그
- `<form>` 안에 `<input>` 태그를 넣어 입력을 받음
```html
<form action="URL"
      enctype="인코딩타입"
      method="GET|POST"
      name="폼이름"
      target="윈도우이름">
    <input type....
</form>
```

<br>

## 텍스트 입력
- `<input type="text">` : 텍스트를 입력받음
- `<input type="password">` : 암호를 입력받음
```html
<form>
  <input type="text|password"
         name="요소이름"
         maxlength="최대 입력 개수"
         size="입력창 크기(문자 개수)"
         value="초기 텍스트">
</form>
```

- `<textarea></textarea>` : 여러 줄의 텍스트를 입력받음
```html
<form>
  <textarea col="가로크기(열 개수)"
            rows="세로크기(행 개수)"
            name="요소이름"
            wrap="OFF|HARD|SOFT(자동 줄바꿈)">
      초기 출력 텍스트
  </textarea>
</form>
```

- `<input type="email">` : email 주소만 입력받음 (형식 검사)
```html
<form>
  <input type="email">
  <input type="submit" value="전송">
</form>
```

- 이외에도 `type` 속성값을 `"url"`, `"tel"` 을 사용하면 각각 URL, 전화번호만 입력받는다.

- `placeholder` 속성 사용 시 입력 정보의 힌트를 알려준다
```html
<form>
  <input type="email" placeholder="id@host">
</form>
```

- `<input type="search">` : 검색어 입력창 생성
  + 검색어 입력 시 오른쪽 끝에 x가 생성돼서 입력했던던 값을 한번에 지울 수 있다.

<br>

## 버튼 입력

- `<button></button>` : 버튼 생성
```html
<form>
  <button type="button|reset|submit"
          name="버튼이름"
          value="버튼에 출력되는 텍스트">
  </button>
  
  <button type="button">
    <img src="/asset/button.png" alt="이미지버튼">
  </button>
</form>
```

- `<input type="button">` : 꼭 `<button>` 태그를 사용하지 않아도 버튼을 만들 수 있다

```html
<form>
  <input type="button|reset|submit|image"
          name="버튼이름"
          value="버튼에 출력되는 텍스트"
          src="이미지 URL">
  </button>
</form>
```

<br>

## 선택형 입력
- `<input type="checkbox">` : 선택/해제 가능한 입력 방식
  + `<input type="radio">` : 복수 선택이 안되는 체크박스
  + `checked` 속성이 활성화돼있으면 처음부터 선택된 상태로 출력된다
```html
<form>
  <input type="checkbox|radio"
         name="요소 이름"
         value="선택됐을 때 서버로 전송되는 값"
         checked>
</form>
```
```html
<!-- 예제 -->
<form>
  Apricot <input type="checkbox" value="1"> <br>
  Banana <input type="checkbox value="2" checked> <br>
  Cake <input type="checkbox" value="3">
</form>
```

- `<textarea></textarea>` : 여러 줄의 텍스트를 입력받음
```html
<form>
  <textarea col="가로크기(열 개수)"
            rows="세로크기(행 개수)"
            name="요소이름"
            wrap="OFF|HARD|SOFT(자동 줄바꿈)">
      초기 출력 텍스트
  </textarea>
</form>
```

<br>

## 버튼 입력

- `<button></button>` : 버튼 생성
```html
<button type="button|reset|submit"
        name="버튼이름"
        value="버튼에 출력되는 텍스트">
</button>

<button type="button">
  <img src="/asset/button.png" alt="이미지버튼">
</button>
```

- `<input type="button">` : 꼭 `<button>` 태그를 사용하지 않아도 버튼을 만들 수 있다

```html
<input type="button|reset|submit|image"
        name="버튼이름"
        value="버튼에 출력되는 텍스트"
        src="이미지 URL">
</button>
```

<br>

## 선택형 입력
- `<input type="checkbox">` : 선택/해제 가능한 입력 방식
  + `<input type="radio">` : 복수 선택이 안되는 체크박스
  + `checked` 속성이 활성화돼있으면 처음부터 선택된 상태로 출력된다
```html
<form>
  <input type="checkbox|radio"
         name="요소 이름"
         value="선택됐을 때 서버로 전송되는 값"
         checked>
</form>
```
```html
<!-- 예제 -->
<form>
  Apricot <input type="checkbox" value="1"> <br>
  Banana <input type="checkbox value="2" checked> <br>
  Cake <input type="checkbox" value="3">
</form>
```

- `<select></select>` : 목록 선택
  + `multiple` 속성이 있으면 여러 항목 선택 가능
```html
<form>
  <select name="company">
    <option value="1">Apricot</option>
    <option value="2">Banana</option>
    <option value="3">Cake</option>
  </select>
</form>
```

- `<datalist></datalist>` : 목록 선택
  + `<input>` 태그에 `list` 속성값으로 `<datalist>`의 `id` 속성값을 똑같이 부여하면 된다
  + `<select>` 태그와 차이점 : `<select>` 는 목록에 있는 항목만 선택되지만 `<datalist>` 는 임의의 값을 입력 후 선택 가능
```html
<form>
  <input type="text" list="company">
  <datalist id="company">
    <option value="Apricot">
    <option value="Banana">
    <option value="Cake">
  </datalist>
</form>
```

<br>

## 캡션 만들기
- `<label></label>` : `<label>` 안에 있는 내용을 묶어 하나의 캡션으로 만듦
```html
<form>
  <label>
    ID : <input type="text">
  </label>
</form>
```

- `<label>` 바깥에 있는 폼을 연결할 수도 있다.
  + `for` 속성값을 `<input>` 태그의 `id` 속성값과 같게 하면 된다
```html
<form>
  <label for="loginID">
    ID : 
  </label>
  <input type="text" id="loginID">
</form>
```

- `type` 속성에 관계없이 사용 가능하다

<br>

## 색 입력
- `<input type="color">` : `#rrggbb` 형식을 통해 색을 표현한다
```html
<form>
  <input type="color" value="#FF80FF"
         onchange="document.body.style.color=this.value">
</form>
```

<br>

## 시간 정보 입력
- 시간 정보 속성값 정리표

| 속성값         | 형식             |
|----------------|------------------|
|`month`         |`YYYY-MM`         |
|`week`          |`YYYY-Wnn`        |
|`date`          |`YYYY-MM-DD`      |
|`time`          |`hh:mm`           |
|`datetime-local`|`YYYY-MM-DDThh:mm`|

```html
<form>
  <input type="month" value="2025-04"> <br>
  <input type="week" value="2025-W15"> <br>
  <input type="date" value="2025-04-13"> <br>
  <input type="time" value="15:00"> <br>
  <input type="datetime-local" value="2025-04-13T13:00">
</form>
```

<br>

## 숫자 입력
- `<input type="number">` : 스핀버튼 사용
- `<input type="range">` : 슬라이드바 사용
```html
<form>
  <input type="number"
         min="0.0" max="10.0" step="0.5"> <br>
  <input type="range"
         min="20" max="80" list="tangent">
  <datalist id="tangent">
    <option value="30" label="1/sqrt(3)">
    <option value="45" label="1">
    <option value="60" label="sqrt(3)">
  </datalist>
</form>
```

<br>

## 하나로 묶기 (범례)
- `<fieldset></fieldset>` 태그를 사용하면 범례처럼 하나로 묶을 수 있다.
  + `<fieldset>` 태그 안에 `<legend></legend>` 태그를 넣어 범례의 제목을 정할 수 있다.
```html
<form>
  <fieldset>
    <legend>제목</legend>
    Email : <input type="email"> <br>
    Homepage : <input type="url"> <br>
    Tel : <input type="tel">
  </fieldset>
</form>
```
