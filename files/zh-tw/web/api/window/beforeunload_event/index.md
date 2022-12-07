---
title: 'Window: beforeunload event'
slug: Web/API/Window/beforeunload_event
original_slug: Web/API/WindowEventHandlers/onbeforeunload
---

{{APIRef("HTML DOM")}}

**`onbeforeunload`** 事件會在視窗關閉、DOM或其資源被移除時執行。在事件觸發的時機點，該DOM依舊存在，且事件仍舊可以被取消。

藉由這個事件能使網頁藉由一個對話框來確認是否真的要離開當前頁面。如果使用者確定，瀏覽器就能導向至新的頁面，否則取消。

根據規範定義，事件必須先執行 {{domxref("Event.preventDefault()", "preventDefault()")}} 才能進行上述跳出對話框的動作。

根據HTML的規格書所述，{{domxref("window.alert()")}}、{{domxref("window.confirm()")}}、{{domxref("window.prompt()")}}在此事件執行的過程中有可能被忽略，詳情請參閱[HTML 規格書](https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#user-prompts)原文。

## 語法

在{{domxref("EventTarget.addEventListener", "addEventListener()")}}方法中使用事件名稱，或是直接使用事件處理的屬性

```js
addEventListener('beforeunload', function(event){ });
onbeforeunload = function(event){ };
```

## 事件類型

{{domxref("BeforeUnloadEvent")}}，繼承自{{domxref("Event")}}。

## 範例

```js
window.onbeforeunload = function(e) {
  var dialogText = 'Dialog text here';
  e.returnValue = dialogText;
  return dialogText;
};
```

## 注意

當事件返回了一個非空值時，將需要用戶確認是否 unload 頁面。在大部分瀏覽器中，事件的返回值將在對話框中顯示。在 Firefox 4 及以後，返回值將不會顯示給用戶。作為替代，Firefox 將會顯示"This page is asking you to confirm that you want to leave - data you have entered may not be saved." 請查看{{bug("588292")}}.

Since 25 May 2011, the HTML5 specification states that calls to {{domxref("window.alert()")}}, {{domxref("window.confirm()")}}, and {{domxref("window.prompt()")}} methods may be ignored during this event. See the [HTML5 specification](http://www.w3.org/TR/html5/webappapis.html#user-prompts) for more details.

Note also that various mobile browsers ignore the result of the event (that is, they do not ask the user for confirmation). Firefox has a hidden preference in about:config to do the same. In essence this means the user always confirms that the document may be unloaded.

You _can_ and _should_ handle this event through {{domxref("EventTarget.addEventListener","window.addEventListener()")}} and the [`beforeunload`](/zh-TW/docs/Web/API/Window/beforeunload_event) event. More documentation is available there.

## 規格

The event was originally introduced by Microsoft in Internet Explorer 4 and standardized in the HTML5 specification.

{{Specifications}}

## 瀏覽器相容性

{{Compat}}

## 參見

- [MSDN: onbeforeunload event](<http://msdn.microsoft.com/en-us/library/ms536907(VS.85).aspx>)
