---
title: margin-right
slug: Web/CSS/margin-right
---

{{CSSRef}}

**`margin-right`** [CSS](/ko/docs/Web/CSS) 속성은 요소의 오른쪽에 [바깥 여백 영역](/ko/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)margin area을 설정합니다. 양수 값은 인접 요소와 거리를 넓히고, 음수 값은 더 좁힙니다.

{{InteractiveExample("CSS Demo: margin-right")}}

```css interactive-example-choice
margin-right: 1em;
```

```css interactive-example-choice
margin-right: 10%;
```

```css interactive-example-choice
margin-right: 10px;
```

```css interactive-example-choice
margin-right: 0;
```

```html interactive-example
<section id="default-example">
  <div id="container">
    <div class="col"></div>
    <div class="col transition-all" id="example-element"></div>
    <div class="col"></div>
  </div>
</section>
```

```css interactive-example
#container {
  width: 300px;
  height: 200px;
  display: flex;
  align-content: flex-start;
  justify-content: flex-start;
}

.col {
  width: 33.33%;
  border: solid #5b6dcd 10px;
  background-color: rgba(229, 232, 252, 0.6);
  flex-shrink: 0;
}

#example-element {
  border: solid 10px #ffc129;
  background-color: rgba(255, 244, 219, 0.6);
}
```

## 구문

```css
/* <length> 값 */
margin-right: 20px; /* 절대 길이 */
margin-right: 1em; /* 글씨 크기에 상대적 */
margin-right: 5%; /* 가장 가까운 블록 컨테이너의 너비에 상대적 */

/* 키워드 값 */
margin-right: auto;

/* 전역 값 */
margin-right: inherit;
margin-right: initial;
margin-right: unset;
```

`margin-right` 속성은 키워드 `auto`, `<length>`, `<percentage>`를 사용해 설정할 수 있습니다. 값은 양수, 0, 음수가 가능합니다.

### 값

- {{cssxref("&lt;length&gt;")}}
  - : 바깥 여백 크기의 고정 값.
- {{cssxref("&lt;percentage&gt;")}}
  - : 바깥 여백 크기와 블록 컨테이너 너비의 비율.
- `auto`
  - : 사용한 레이아웃 모드에 따라 가로축 미사용 공간 너비의 일부를 바깥 여백에 할당. `margin-left`와 `margin-right`의 값이 모두 `auto`라면 너비를 양 여백에 동일하게 배정합니다. 아래 표가 가능한 여러 경우를 보입니다.

    | {{cssxref("display")}} 값                                                                         | {{cssxref("float")}} 값 | {{cssxref("position")}} 값 | `auto`의 계산 값                                                                                                                                                               | 설명                                                                                                  |
    | ------------------------------------------------------------------------------------------------- | ----------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
    | `inline`, `inline-block`, `inline-table`                                                          | _any_                   | `static` or `relative`     | `0`                                                                                                                                                                            | 인라인 레이아웃 모드                                                                                  |
    | `block`, `inline`, `inline-block`, `block`, `table`, `inline-table`, `list-item`, `table-caption` | _any_                   | `static` or `relative`     | `0`, except if both `margin-left` and `margin-right` are set to `auto`. In this case, it is set to the value centering the element inside its parent.                          | 블록 레이아웃 모드                                                                                    |
    | `block`, `inline`, `inline-block`, `block`, `table`, `inline-table`, `list-item`, `table-caption` | `left` or `right`       | `static` or `relative`     | `0`                                                                                                                                                                            | 블록 레이아웃 모드 (플로팅 요소)                                                                      |
    | _any_ `table-*`_, except_ `table-caption`                                                         | _any_                   | _any_                      | `0`                                                                                                                                                                            | 내부 `table-*` 요소는 바깥 여백을 가지지 않습니다. 대신 {{ cssxref("border-spacing") }}을 사용하세요. |
    | _any, except `flex`,_ `inline-flex`_, or_ `table-*`                                               | _any_                   | _`fixed`_ or `absolute`    | `0`, except if both `margin-left` and `margin-right` are set to `auto`. In this case, it is set to the value centering the border area inside the available `width`, if fixed. | 절대위치 레이아웃 모드                                                                                |
    | `flex`, `inline-flex`                                                                             | _any_                   | _any_                      | `0`, except if there is any positive horizontal free space. In this case, it is evenly distributed to all horizontal `auto` margins.                                           | 플렉스박스 레이아웃 모드                                                                              |

### 형식 구문

{{csssyntax}}

## 예제

```css
.content {
  margin-right: 5%;
}
.sidebox {
  margin-right: 10px;
}
.logo {
  margin-right: -5px;
}
```

## 명세

{{Specifications}}

{{cssinfo}}

## 브라우저 호환성

{{Compat}}
