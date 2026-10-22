---
title: popover
slug: Web/HTML/Reference/Global_attributes/popover
---

{{HTMLSidebar("Global_attributes")}}

**`popover`** [全域屬性](/zh-tw/docs/Web/HTML/Reference/Global_attributes)是用來使元素標示成彈出視窗元素。

## 參數

`popover`屬性可以填入以下參數:

- `"auto"`
  - : [`auto`](/zh-tw/docs/Web/API/Popover_API/Using#auto_state_and_light_dismiss) 的彈出釋出可以「輕易關閉」——即你只要點擊彈出視窗外、或是按下 <kbd>Esc</kbd> 鍵就可以關閉彈出視窗。
    一般來說，你只能有一個`auto`的彈出視窗。當你要開啟第二個彈出視窗時，就會關閉第一個。唯一的例外情況是嵌套彈出視窗。
    > [!NOTE]
    > 當`popover`為空，即`popover`或`popover=""`的狀況，等同於`popover="auto"`。

- `"hint"` {{experimental_inline}}
  - : [`hint`](/zh-tw/docs/Web/API/Popover_API/Using#using_hint_popover_state) 開啟時，不會影響其他 `auto` 彈出視窗，但會把所有`hint`的彈出視窗關閉。
    它們可以「輕易關閉」，並且也會回應關閉的請求。

- `"manual"`
  - : [`manual`](/zh-tw/docs/Web/API/Popover_API/Using#using_manual_popover_state) popovers cannot be "light dismissed" and are not automatically closed. Popovers must explicitly be displayed and closed using declarative show/hide/toggle buttons or JavaScript. Multiple independent `manual` popovers can be shown simultaneously.

## 說明

Popover 元素默認情況下會有條樣式 `display: none` 將其隱藏，除非由調用或控制元素（例如有 [`popovertarget`](/zh-tw/docs/Web/HTML/Reference/Elements/button#popovertarget) 屬性的`<button>` 或 `<input type="button">`）或是呼叫 {{domxref("HTMLElement.showPopover()")}}來將之開啟。

開啟的 popover 元素會顯示在{{glossary("top layer")}}其他元素之上，並且不會受到父元素的 {{cssxref('position')}} 或是 {{cssxref('overflow')}} 樣式影響。

[`auto`](/zh-tw/docs/Web/API/Popover_API/Using#auto_state_and_light_dismiss) 狀態的彈出視窗，可由對應的控制元素（由 [`popovertarget`](/zh-tw/docs/Web/HTML/Reference/Elements/button#popovertarget) 屬性決定）來顯示或隱藏。另外還能「輕觸關閉」，即點擊彈出視窗區域外、開啟另一個彈出視窗、或使用瀏覽器專屬的機制（例如 <kbd>Esc</kbd> 鍵）來關閉彈出視窗。

 一般來說，一次只會顯示一個 `auto` 的彈出視窗——當要開啟第二個彈出視窗時，原先開啟的就會自動關閉。少數的例外狀況是巢狀彈出視窗，詳細可參閱[巢狀彈出視窗](#巢狀彈出視窗)章節。

彈出視窗可以使用 JavaScript 開控制，舉例來說， {{domxref("HTMLElement.togglePopover()")}} 能顯示、隱藏彈出視窗。

相比之下，[`manual`](/zh-tw/docs/Web/API/Popover_API/Using#using_manual_popover_state) 的彈出視窗得自行處理顯示、隱藏——開啟其他彈出視窗時，原本開啟的不會自動關閉、且不能「輕觸關閉」。這適用於需要顯示多個彈出視窗的情境。

[`hint`](/zh-tw/docs/Web/API/Popover_API/Using#using_hint_popover_state) 彈出視窗不會關閉其他顯示中的 `auto` 彈出視窗，只會關閉其他 `hint` 的彈出視窗。`hint` 的彈出視窗一樣能「輕觸關閉」並提供回饋給關閉請求。

Usually `hint` popovers are shown and hidden in response to non-click JavaScript events such as [`mouseover`](/zh-tw/docs/Web/API/Element/mouseover_event)/[`mouseout`](/zh-tw/docs/Web/API/Element/mouseout_event) and [`focus`](/zh-tw/docs/Web/API/Element/focus_event)/[`blur`](/zh-tw/docs/Web/API/Element/blur_event). Clicking a button to open a `hint` popover would cause an open `auto` popover to light-dismiss.

For detailed information on usage, see the {{domxref("Popover API", "Popover API", "", "nocode")}} landing page.

## 範例

### Making an element a popover

以下範例是一個按鈕，點下後會跳出一個彈出視窗。

```html
<button popovertarget="my-popover">Open Popover</button>

<div popover id="my-popover">Greetings, one and all!</div>
```

{{EmbedLiveSample('Examples', 600, 200)}}

### 巢狀彈出視窗

在以下的範例中，彈出視窗內有個按鈕可以開啟另一個彈出視窗。開啟第二個彈出視窗時，原先的彈出視窗不會被關閉。

#### HTML

在 HTML ，我們先建立一個按鈕 {{htmlElement("button")}} 用來開啟主彈出視窗。該彈出視窗是要放置目錄選項。

```html
<header>
  <button popovertarget="menu">Open Menu</button>
</header>
<main>
  <!--  Page content goes here  -->
</main>
```

接下來建立彈出視窗的內容，該彈出視窗會由上一步驟建立的按鈕開啟。在這彈出視窗中，包含了無序的目錄項目，每個目錄都有一個ⓘ按鈕可以用來開啟巢狀彈出視窗。

目錄項目的 popover 屬性值為 `popover="auto"`，表示巢狀彈出視窗開啟時，主彈出視窗不會關閉。

```html
<!-- menu popover -->
<div id="menu" popover="auto">
  <ul>
    <li>
      <a href="#">New thing</a><button popovertarget="new-info">ⓘ</button>
    </li>
    <li>
      <a href="#">Open thing</a><button popovertarget="open-info">ⓘ</button>
    </li>
    <li>
      <a href="#">Save thing</a><button popovertarget="save-info">ⓘ</button>
    </li>
    <li>
      <a href="#">Close thing</a><button popovertarget="close-info">ⓘ</button>
    </li>
  </ul>
</div>
```

最後，在 HTML 給所有目錄項建立巢狀彈出視窗。每個彈出視窗都有 `popover="hint"` 的屬性，這是用來確保開啟時，不會關掉上一層彈出視窗（但依舊會關閉其他彈出視窗）。

```html
<!-- info popovers -->
<div id="new-info" class="info-popover" popover="hint">
  This is some information about <strong>creating a new</strong> thing.
</div>
<div id="open-info" class="info-popover" popover="hint">
  This is some information about <strong>opening an existing</strong> thing.
</div>
<div id="save-info" class="info-popover" popover="hint">
  This is some information about <strong>saving the current</strong> thing.
</div>
<div id="close-info" class="info-popover" popover="hint">
  This is some information about <strong>closing the current</strong> thing.
</div>
```

#### CSS

```css hidden
header {
  display: flex;
  justify-content: center;
}
header button {
  margin: 0.4rem auto;
}
```

在這裡，我們使用 [anchor positioning](/zh-tw/docs/Web/CSS/Guides/Anchor_positioning) 讓彈出視窗的位置放在 `<button>` 下方；使用 [grid](/zh-tw/docs/Web/CSS/Guides/Grid_layout) 來排版目錄項目與按鈕。

```css
#menu {
  margin: 0;
  margin-top: 0.4rem;
  inset: auto;
  position-area: bottom;
}
#menu ul {
  display: grid;
  grid-template-columns: max-content 1fr;
  gap: 0.4rem;
  padding: 0.4rem;
}
#menu li {
  grid-column: span 2;
  display: grid;
  grid: inherit;
  grid-template-columns: subgrid;
  gap: 1.4rem;
}
li [popovertarget] {
  cursor: pointer;
  font-size: 1.2rem;
}
li button {
  border: none;
  padding: 0;
  background-color: inherit;
}
```

Here, we've used anchor positioning to make the info popovers appear to the right of their respective info buttons.

```css
div.info-popover {
  margin: 2rem;
  inset: auto;
  max-width: 300px;
  position-area: right;
}
```

#### Result

Click the _Open Menu_ button, then click the info icons (ⓘ) next to the menu options to open the info popovers.

{{EmbedLiveSample('popover_hint', 600, 250)}}

> [!NOTE]
> 在我們的 [Popover API 範例集頁](https://mdn.github.io/dom-examples/popover-api/)中可以找到所有 MDN 的 popover 範例。

## 規範

{{Specifications}}

## 瀏覽器相容性

{{Compat}}

## 參見

- {{domxref("Popover API", "Popover API", "", "nocode")}}
- [`popovertarget`](/zh-tw/docs/Web/HTML/Reference/Elements/button#popovertarget) HTML 屬性
- [`popovertargetaction`](/zh-tw/docs/Web/HTML/Reference/Elements/button#popovertargetaction) HTML 屬性
- [`::backdrop`](/zh-tw/docs/Web/CSS/::backdrop) CSS 偽元素
- [`:popover-open`](/zh-tw/docs/Web/CSS/:popover-open) CSS 偽 class
