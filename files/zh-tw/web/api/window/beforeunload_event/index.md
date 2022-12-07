---
title: 'Window: beforeunload event'
slug: Web/API/Window/beforeunload_event
original_slug: Web/API/WindowEventHandlers/onbeforeunload
---

{{APIRef("HTML DOM")}}

**`onbeforeunload`** 事件處理函數包含的代碼將在 [`beforeunload`](/zh-TW/docs/Web/API/Window/beforeunload_event) 發出時被執行。當 window 準備釋放它的資源時，該事件被觸發。此時 document 仍然可見，且事件是仍然可被取消的。

> **備註：** 為了避免不必要的彈出窗口，除非頁面已經有過互動，否則可能不會顯示 beforeunload 創建的詢問窗口。對於特定的瀏覽器列表，請參閱瀏覽器兼容性部分。

## 語法

```plain
window.onbeforeunload = funcRef
```

- `funcRef` 是函數或函數表達式的引用。
- 這個函數應該設置一個字串到事件對象的 returnValue 屬性上，且返回該字串。

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

## 規範

The event was originally introduced by Microsoft in Internet Explorer 4 and standardized in the HTML5 specification.

{{Specifications}}

## 瀏覽器相容性

{{Compat}}

## 參見

- [MSDN: onbeforeunload event](<http://msdn.microsoft.com/en-us/library/ms536907(VS.85).aspx>)
