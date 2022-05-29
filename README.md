# nomadcoders-css-layout-master-class

노마드코더 CSS 마스터클래스

# SCSS Masterclass

(S)CSS Layout Masterclass: Flexbox & Grid

## Flexbox:

- [x] `flex-direction` - `메인축`의 방향을 결정

  - [x] `flex-direction : row;` - 가로정렬 `(default❗)`
  - [x] `flex-direction : row-reverse;` - 가로정렬(반전)
  - [x] `flex-direction : column;` - 세로정렬
  - [x] `flex-direction : column-reverse;` - 세로정렬(반전)

- [x] `order` - `✅자식요소에사용` 메인축에서의 순서 지정

  - [x] `order : 0;` - `(default❗)`
  - [x] `order : 1;` - 순서를 2번째로 변경

- [x] `justify-content` - (메인축기준) 자식요소의 정렬을 결정 (`flex-direction : row;` 인경우 예시)

  - [x] `justify-content : normal;` - `(default❗)`
  - [x] `justify-content : center;` - 가운데 정렬
  - [x] `justify-content : flex-start;` - 좌측정렬
  - [x] `justify-content : flex-end;` - 우측정렬
  - [x] `justify-content : space-between;` - 고르게 분포(넓게)
  - [x] `justify-content : space-around;` - 고르게 분포(같은간격)

- [x] `align-items` - `교차축`의 방향을 결정 (`flex-direction : row;` 인경우 예시)

  - [x] `align-items : normal;` - `(default❗)`
  - [x] `align-items : flex-start;` - 위쪽 정렬
  - [x] `align-items : flex-end;` - 아래쪽 정렬
  - [x] `align-items : center;` - 가운데 정렬

- [x] `align-self` - `✅자식요소에사용` 교차축에서의 정렬을 지정 (`flex-direction : row;` 인경우 예시)
  - [x] `align-self : auto;` - `(default❗)`
  - [x] `align-self : start;` - 위쪽 정렬
  - [x] `align-self : end;` - 아래쪽 정렬
  - [x] `align-self : center;` - 가운데 정렬
- [x] `flex-wrap` - `메인축`에서 자식요소들의 줄바꿈을 설정

  - [x] `flex-wrap: nowrap;` - `(default❗)` 줄바꿈 하지 않음 (넓이를 강제로 변경함)
  - [x] `flex-wrap: wrap;` - 자식요소의 넓이를 유지하며 줄바꿈

- [x] `align-content` - `메인축`의 `justify-content`와 동일 (단, 교차축에 적용됨)
- [x] `flex-grow` -`✅자식요소에사용` 남은공간을 얼마나 더 많이 차지할지 지정

  - [x] `flex-grow: 0;` - `(default❗)` 기본크기
  - [x] `flex-grow: 1;` - 남을공간을 1x만큼 더 설정
  - [x] `flex-grow: 2;` - 남을공간을 2x만큼 더 설정

- [x] `flex-shrink` -`✅자식요소에사용` flexbox가 작아질때 몇배로 조절할것인지를 지정

  - [x] `flex-shrink: 1;` - `(default❗)` 1배로 줄어듬
  - [x] `flex-shrink: 2;` - (다른 요소들에 비해) 2배 더많이 줄어듬
  - [x] `flex-shrink: 3;` - (다른 요소들에 비해) 3배 더많이 줄어듬

- [x] `flex-basis` - `✅자식요소에사용` `메인축`에서의 초기 넓이를 지정 (`flex-direction : row;`인경우 높이가됨) (width, height로 대신사용 해도됨)
  - [x] `flex-basis: 200px;` - 넓이를 200px로 지정

## Grid:

- [x] `grid-template-columns` - 열(column)의 개수와 크기를 지정

  ```
  .grid {
    display: grid;
    gap: 10px;

    grid-template-columns: 100px 100px 100px 100px; /* px로 크기 지정 */
    grid-template-rows: 100px 100px 100px 100px;

    grid-template-columns: [col_start] 100px [col_2] 100px [col_3] 100px [col_4] 100px [col_end]; /* 이름을 지정 */
    grid-template-rows: 100px 100px 100px 100px;

    grid-template-columns: repeat(4, 100px); /* repeat(반복회수, 크기) */
    grid-template-rows: repeat(4, 100px);

    grid-template-columns: 1fr 1fr 1fr 1fr; /* fr단위 : 비율로 지정*/
    grid-template-rows: 1fr 3fr 3fr 1fr;
  }
  ```

- [x] `grid-template-rows` - 행(row)의 개수와 크기를 지정
  - [x] `grid-template-rows: 50px 50px 100px;`
- [x] `column-gap` : 열(column)간의 여백을 지정
  - [x] `column-gap: 10px;`
- [x] `row-gap` - 행(row)간의 여백을 지정
  - [x] `row-gap: 10px;`
- [x] `gap` - 열(column)과 행(row)간의 여백을 지정
- [x] `grid-template-areas` - 그리드의 형태를 문자열로 지정할수 있음
  ```
   .grid {
        height: 95vh;
        display: grid;
        grid-template-columns: auto 300px;
        grid-template-rows: 100px auto 100px;
        grid-template-areas:
            "header header header header"
            "content content content nav"
            "content content content nav"
            "footer footer footer footer";
    }
    .header {
        background-color: #2ecc71;
        grid-area: header;  /* grid-template-areas에서 사용할 문자열을 지정 */
    }
    .content {
        background-color: #3498db;
        grid-area: content; /* grid-template-areas에서 사용할 문자열을 지정 */
    }
    .nav {
        background-color: #8e44ad;
        grid-area: nav; /* grid-template-areas에서 사용할 문자열을 지정 */
    }
    .footer {
        background-color: #f39c12;
        grid-area: footer; /* grid-template-areas에서 사용할 문자열을 지정 */
    }
  ```
- [x] `grid-column-start` - `(자식요소)` 열(column)이 시작 라인 번호
  ```
  .content {
    background-color: #3498db;
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 2;
    grid-row-end: 4;
  }
  ```
- [x] `grid-column-end` - `(자식요소)` 열(column)이 끝나는 라인 번호
- [x] `grid-row-start` - `(자식요소)` 행(row)이 시작 라인 번호
- [x] `grid-row-end` - `(자식요소)` 행(row)이 끝나는 라인 번호
- [x] `grid-column` - `(자식요소)` 열의 라인번호 (시작 / 끝)
  ```
  .header {
    background-color: #2ecc71;
    grid-column: 1 / 5;  /* 1번줄 ~ 5번줄 */
    grid-column: 1 / -1;  /* 1번줄 ~ 마지막줄 */
    grid-column: 1 / -2;  /* 1번줄 ~ 마지막 -1줄 */
    grid-column: span 4;  /* span : 현재위치에서 상대적으로 몇칸을 더 채울건지 결정 */
  }
  ```
- [x] `grid-row` - `(자식요소)` 행의 라인번호 (시작 / 끝)
- [x] `grid-template` - 행열의 이름과 크기를 한번에 지정할 수 있음 😍

  ```
    .grid {
        height: 50vh;
        display: grid;
        gap: 10px;
        grid-template:
            "header header header header" 1fr /* 열의이름을 지정하며, 해당행의 높이를 1fr로 설정 */
            "content content content nav" 2fr /* 행높이 2fr */
            "footer footer footer footer" 1fr /* 행높이 1fr */
            / 1fr 1fr 1fr 1fr; /* 각 열의 넓이 1fr */
    }
    .header {
        background-color: #2ecc71;
        grid-area: header;
    }

  ```

- [x] `justify-items` - 셀내부 요소의 `수평`정렬 `stretch`, `start`, `center`, `end`
- [x] `align-items` - 셀내부 요소의 `수직`정렬 `stretch`, `start`, `center`, `end`
- [x] `place-items` - 셀내부 요소의 수직 / 수평 단축키 😍
  ```
    .grid {
        display: grid;
        place-items : center center;  /* 가운데정렬 */
        place-items: start end; /* 상단 우측정렬 */
        place-items: end center; /* 하단 중앙정렬 */
    }
  ```
- [x] `justify-content` - 그리드자체 수평 정렬

  ```
    .grid {
        height: 50vh;
        display: grid;
        gap: 10px;
        grid-template-columns: repeat(4, 100px);
        grid-template-rows: repeat(4, 100px);

        justify-content: start;
        justify-content: center;
        justify-content: end;
        justify-content: space-between;
        justify-content: space-around;
    }
  ```

- [x] `align-content` - 그리드자체 수직 정렬
- [x] `place-content` - 그리드자체 수직 / 수평 단축키 😍
  ```
    .grid{
        display : grid;
        place-content: end center;
    }
  ```
- [x] `justify-self` - `✅자식요소에사용` 수평 정렬
- [x] `align-self` - `✅자식요소에사용` 수직 정렬
- [x] `place-self` - `✅자식요소에사용` 수직 정렬 단축키 😍

  ```
    .grid {
        background-color: #0005;
        height: 100vh;
        display: grid;
        gap: 10px;
        grid-template-columns: repeat(4, 100px);
        grid-template-rows: repeat(4, 100px);
    }
    .header {
        background-color: #2ecc71;
        /* justify-self: center; */
        /* align-self: center; */
        place-self: start end;
        place-self: end start;
    }
  ```

- [x] `grid-auto-rows` - row 개수 자동 지정

  ```
  .grid {
    display: grid;
    grid-template-columns: repeat(4, 100px); /* row 개수 4개(수동)*/
    grid-auto-rows: 100px; /* row 개수 자동*/
  }
  ```

- [x] `grid-auto-flow` - grid 행열의 위치변경 (flexbox의 direction과 비슷한 기능) 😍

  ```
  .grid{
      display:flex;
      grid-auto-flow: row; /* 기본값 */
      grid-auto-flow: column; /* 축이 변경됨 - 갤러리 구현시 유용 */
  }

  ```

- [x] `grid-auto-columns` - column 개수 자동 지정

### Keywords & Functions:

- [x] `repeat` - 반복 `repeat(4 100px)`
- [x] `fr` - 분수 단위 (1fr 2fr)
- [x] `minmax` - 최소/최대 크기를 지정

  ```
  .grid{
      display : grid;
      grid-template-columns: repeat(5, minmax(100px, 1fr));
  }
  ```

- [x] `auto-fit` - `셀의 크기를 고정` 행/열의 개수를 자동으로 채움 (repeat와 함께 사용)

  ```
  .grid{
      display : grid;
      grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  }
  ```

- [x] `auto-fill` - `셀의 크기를 늘리며` 행/열의 개수를 자동으로 채움 (repeat와 함께 사용)

  ```
  .grid{
      display : grid;
      grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  }
  ```

- [ ] `min-content` -
- [ ] `max-content` -

## SCSS:

- [x] Variables - 변수

  ```
    // 선언
    // _variables.scss
    // _FILENAME.scss - 언더바(_)로 시작하는 파일은 컴파일되지 않음!

    $bg: #E7473C;
    $title: 32px;
  ```

  ```
    // 사용
    // styles.scss

    @import "_variables";   /* include */

    body{
        background-color: $bg;
    }
    h1{
        color:$bg;
        font-size: $title;
    }
  ```

- [x] Nesting - 중첩문 사용가능

  ```
  .box{
      margin:20px;
      h2{
          color:blue;
      }
      button{
          color: white;
          background-color: black;
          &:hover{
              color:red;
          }
      }
      &:hover{
          background-color: green;

      }
  }
  ```

- [x] Mixins - 함수

  ```
  @mixin link($color:red) {
      color:$color;
      text-decoration: none;
      display: block;
      font-size: 50px;
  }
  a{
      &:nth-child(odd){
          @include link(blue);
      }
      &:nth-child(even){
          @include link(green);
      }
  }


  ```

  ```
  /* 조건문도 가능 */
  @mixin link($word) {
      text-decoration: none;
      display: block;
      font-size: 50px;

      @if $word == "odd"{
          color:blue;
      }
      @else{
          color:red;
      }
  }

  a{
      &:nth-child(odd){
          @include link("odd");
      }
      &:nth-child(even){
          @include link("even");
      }
  }


  ```

- [x] Extend - 코드 재사용 가능 (함수의 축소판?)

  ```
  /* %기호로 extend 정의*/
  %button {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
      border-radius: 7px;
      font-size: 12px;
      text-transform: uppercase;
      padding: 5px 10px;
      background-color: tomato;
      color:white;
      font-weight: 500;
  }

  a{
      @extend %button;  /* @extend %변수명 */
      text-decoration: none
  }
  button{
      @extend %button;
      border: none;
  }
  ```

- [x] Responsive Mixins -

  ```
  $min_iPhone:414px;
  $max_iPhone:896px;

  $min_Tablet:$min_iPhone+1;
  $max_Tablet:1120px;

  @mixin responsive($device) {
      @if $device == 'iphone'{
          @media screen and (min-width:$min_iPhone) and (max-width: $max_iPhone) {
              @content;   /* @mixin 안의 @content는 외부에서 주입 가능 */
          }
      }
      @else if $device == "tablet"{
          @media screen and (min-width:$min_Tablet) and (max-width: $max_iPhone) {
              @content;   /* @mixin 안의 @content는 외부에서 주입 가능 */
          }
      }
      @else if $device == "iphone-l"{
          @media screen and (min-width:$min_iPhone) and (max-width: $max_iPhone) and (orientation:landscape){
              @content;   /* @mixin 안의 @content는 외부에서 주입 가능 */
          }
      }
      @else if $device == "ipad-l"{
          @media screen and (min-width:$min_Tablet) and (max-width: $max_iPhone) and (orientation:landscape){
              @content;   /* @mixin 안의 @content는 외부에서 주입 가능 */
          }
      }
  }

  h1{
      color:red;
      @include responsive("iphone"){
          color:blue;       /* @mixin 내부의 @content 부분으로 CSS 주입 */
      }
      @include responsive("iphone-l"){
          font-size: 100px; /* @mixin 내부의 @content 부분으로 CSS 주입 */
      }
  }
  ```

## To Clone:

- [x] [https://besthorrorscenes.com/](https://besthorrorscenes.com/) ▶ [Clone Result](https://gandol2.github.io/nomadcoders-css-layout-master-class/clone/01.html)
- [x] [https://paint-box.com/](https://paint-box.com/) ▶ [Clone Result](https://gandol2.github.io/nomadcoders-css-layout-master-class/clone/02.html)
- [x] [http://10x19.co/](http://10x19.co/) ▶ [Clone Result](https://gandol2.github.io/nomadcoders-css-layout-master-class/clone/03.html)
- [x] [http://www.z-o-o.fr/](http://www.z-o-o.fr/)
- [x] [https://schwartzmedia.com.au/](https://schwartzmedia.com.au/)
- [ ] [https://tolv.dk/](https://tolv.dk/)
- [ ] [https://rodicdavidson.co.uk/](https://rodicdavidson.co.uk/)
- [ ] [https://beige.de/](https://beige.de/)
- [ ] [http://donicaida.com/](http://donicaida.com/)
- [ ] [https://canalstreet.market/](https://canalstreet.market/)
- [ ] [https://wonhundred.com/](https://wonhundred.com/)

```

```
