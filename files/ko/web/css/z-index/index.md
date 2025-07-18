---
title: z-index
slug: Web/CSS/z-index
---

{{CSSRef}}

[CSS](/ko/docs/Web/CSS) **`z-index`** 속성은 [위치 지정 요소](/ko/docs/Web/CSS/position)와, 그 자손 또는 하위 플렉스 아이템의 Z축 순서를 지정합니다. 더 큰 `z-index` 값을 가진 요소가 작은 값의 요소 위를 덮습니다.

{{InteractiveExample("CSS Demo: z-index")}}

```css interactive-example-choice
z-index: auto;
```

```css interactive-example-choice
z-index: 1;
```

```css interactive-example-choice
z-index: 3;
```

```css interactive-example-choice
z-index: 5;
```

```css interactive-example-choice
z-index: 7;
```

```html interactive-example
<section class="default-example container" id="default-example">
  <div id="example-element">Change my z-index</div>
  <div class="block blue position1">z-index: 6</div>
  <div class="block blue position2">z-index: 4</div>
  <div class="block blue position3">z-index: 2</div>
  <div class="block red position4">z-index: auto</div>
  <div class="block red position5">z-index: auto</div>
  <div class="block red position6">z-index: auto</div>
</section>
```

```css interactive-example
#example-element {
  top: 15px;
  left: 15px;
  width: 180px;
  height: 230px;
  position: absolute;
  /* center the text so it is visible even when z-index is set to auto */
  line-height: 215px;
  font-family: monospace;
  background-color: #fcfbe5;
  border: solid 5px #e3e0a1;
  z-index: auto;
  color: black;
}

.container {
  display: inline-block;
  width: 250px;
  position: relative;
}

.block {
  width: 150px;
  height: 50px;
  position: absolute;
  font-family: monospace;
  color: black;
}

.blue {
  background-color: #e5e8fc;
  border: solid 5px #112382;
  /* move text to the bottom of the box */
  line-height: 55px;
}

.red {
  background-color: #fce5e7;
  border: solid 5px #e3a1a7;
}

.position1 {
  top: 0;
  left: 0;
  z-index: 6;
}

.position2 {
  top: 30px;
  left: 30px;
  z-index: 4;
}

.position3 {
  top: 60px;
  left: 60px;
  z-index: 2;
}

.position4 {
  top: 150px;
  left: 0;
  z-index: auto;
}

.position5 {
  top: 180px;
  left: 30px;
  z-index: auto;
}

.position6 {
  top: 210px;
  left: 60px;
  z-index: auto;
}
```

위치 지정 요소(`position`이 `static` 외의 다른 값인 요소)의 박스에 대해, `z-index` 속성은 다음 항목을 지정합니다.

1. 현재 [쌓임 맥락](/ko/docs/Web/CSS/CSS_positioned_layout/Stacking_context)에서 자신의 위치.
2. 자신만의 쌓임 맥락 생성 여부.

## 구문

```css
/* 키워드 값 */
z-index: auto;

/* <integer> 값 */
z-index: 0;
z-index: 3;
z-index: 289;
z-index: -1; /* 음수 값으로 우선순위를 낮출 수 있음 */

/* 전역 값 */
z-index: inherit;
z-index: initial;
z-index: unset;
```

z-index 속성은 [`auto`](#auto) 키워드 또는 [`<integer>`](#integer) 값을 사용해 지정할 수 있습니다.

### 값

- `auto`
  - : 박스가 새로운 쌓임 맥락을 생성하지 않습니다. 현재 쌓임 맥락에서의 위치는 부모 요소와 동일합니다.
- {{cssxref("&lt;integer&gt;")}}
  - : 현재 쌓임 맥락에서의 위치로 이 값을 사용합니다. 또한 자신만의 쌓임 맥락을 생성하고, 해당 맥락에서 자신의 위치를 `0`으로 설정합니다. 이로 인해 자손의 `z-index`를 자기 외의 바깥 요소와 비교하지 않습니다.

### 형식 구문

{{csssyntax}}

## 예제

### HTML

```html
<div class="dashed-box">
  Dashed box
  <span class="gold-box">Gold box</span>
  <span class="green-box">Green box</span>
</div>
```

### CSS

```css
.dashed-box {
  position: relative;
  z-index: 1;
  border: dashed;
  height: 8em;
  margin-bottom: 1em;
  margin-top: 2em;
}
.gold-box {
  position: absolute;
  z-index: 3; /* put .gold-box above .green-box and .dashed-box */
  background: gold;
  width: 80%;
  left: 60px;
  top: 3em;
}
.green-box {
  position: absolute;
  z-index: 2; /* put .green-box above .dashed-box */
  background: lightgreen;
  width: 20%;
  left: 65%;
  top: -25px;
  height: 7em;
  opacity: 0.9;
}
```

### 결과

{{ EmbedLiveSample('예제', '550', '200', '') }}

## 명세

{{Specifications}}

{{cssinfo}}

## 브라우저 호환성

{{Compat}}

## 같이 보기

- CSS {{ Cssxref("position") }} 속성
- [CSS z-index 이해하기](/ko/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index)
