# Chapter 5. CSS3 고급

<br>

## 배치
- CSS 프로퍼티 종류
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
<br>

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
<br>

<img src="https://github.com/user-attachments/assets/07187459-4cca-4b64-a24c-9de776ee44cb" width="30%" />

<br>

## 수직방향 우선도
- `z-index` : `-3`, `2`, ... (높은 순으로 위쪽 위치)
```css
div { z-index : 3; }
```

<br>

## 숨기기
- `visibility` : `hidden`, `visible`
  + `hidden` 상태라고 아무것도 없는 거랑 같은게 아니라, 태그의 공간은 할당된다
  + 예시로 어떤 단어를 포함하는 `<span>` 태그에 `hidden`을 적용시키면 단어 길이만큼 공백이 생겨있다
```css
span { visibility: hidden; }
```

<br>

