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
```html
<form action="URL"
      enctype="인코딩타입"
      method="GET|POST"
      name="폼이름"
      target="윈도우이름">
      <input type....
</form>
```
