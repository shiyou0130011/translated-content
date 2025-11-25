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
    一般來說，你只能有一個`auto`的彈出視窗。當你要開啟第二個彈出視窗時，就會關閉第一個。這規則唯一的例外情況是嵌套`auto`的彈出視窗。詳情請參閱《[嵌套彈出視窗](/zh-TW/docs/Web/API/Popover_API/Using#nested_popovers)》。
    > [!NOTE]
    > 當`popover`為空，即`popover`或`popover=""`的狀況，等同於`popover="auto"`。

- `"hint"` {{experimental_inline}}
  - : [`hint`](/zh-tw/docs/Web/API/Popover_API/Using#using_hint_popover_state) popovers do not close `auto` popovers when they are displayed, but will close other hint popovers.
    They can be light dismissed and will respond to close requests.

- `"manual"`
  - : [`manual`](/zh-tw/docs/Web/API/Popover_API/Using#using_manual_popover_state) popovers cannot be "light dismissed" and are not automatically closed. Popovers must explicitly be displayed and closed using declarative show/hide/toggle buttons or JavaScript. Multiple independent `manual` popovers can be shown simultaneously.

## 說明

Popover elements are hidden via `display: none` until opened via an invoking/control element (i.e., a `<button>` or `<input type="button">` with a [`popovertarget`](/zh-tw/docs/Web/HTML/Reference/Elements/button#popovertarget) attribute) or a {{domxref("HTMLElement.showPopover()")}} call.

When open, popover elements will appear above all other elements in the {{glossary("top layer")}}, and won't be influenced by parent elements' {{cssxref('position')}} or {{cssxref('overflow')}} styling.

Popovers that have the [`auto`](/zh-tw/docs/Web/API/Popover_API/Using#auto_state_and_light_dismiss) state can be shown and hidden using associated controls (designated by the [`popovertarget`](/zh-tw/docs/Web/HTML/Reference/Elements/button#popovertarget) attribute) and "light dismissed" by clicking outside the popover area, opening another popover, or pressing browser-specific mechanisms such as the <kbd>Esc</kbd> key.

Generally only one `auto` popover can be displayed on-screen at a time — showing a second popover when one is already shown will hide the first one. The exception to this rule is when you have nested auto popovers. See [Nested popovers](/zh-tw/docs/Web/API/Popover_API/Using#nested_popovers) for more details.

They can also be controlled using JavaScript, for example the {{domxref("HTMLElement.togglePopover()")}} method can be used to toggle a popover between shown and hidden.

By contrast, [`manual`](/zh-tw/docs/Web/API/Popover_API/Using#using_manual_popover_state) popovers must be manually shown and hidden — they don't automatically close other popovers when they are displayed and they can't be light dismissed. This allows for use cases where you want to show multiple popovers at the same time.

[`hint`](/zh-tw/docs/Web/API/Popover_API/Using#using_hint_popover_state) popovers do not close `auto` popovers when they are displayed, but will close other hint popovers. They can be light dismissed and will respond to close requests.

Usually `hint` popovers are shown and hidden in response to non-click JavaScript events such as [`mouseover`](/zh-tw/docs/Web/API/Element/mouseover_event)/[`mouseout`](/zh-tw/docs/Web/API/Element/mouseout_event) and [`focus`](/zh-tw/docs/Web/API/Element/focus_event)/[`blur`](/zh-tw/docs/Web/API/Element/blur_event). Clicking a button to open a `hint` popover would cause an open `auto` popover to light-dismiss.

For detailed information on usage, see the {{domxref("Popover API", "Popover API", "", "nocode")}} landing page.

## 範例

以下範例是一個按鈕，點下後會跳出一個彈出視窗。

```html
<button popovertarget="my-popover">Open Popover</button>

<div popover id="my-popover">Greetings, one and all!</div>
```

{{EmbedLiveSample('Examples', 600, 200)}}

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
