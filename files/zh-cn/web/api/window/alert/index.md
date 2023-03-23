---
title: window.alert
slug: Web/API/Window/alert
---

{{ ApiRef() }}

### 概述

显示一个警告对话框，上面显示有指定的文本内容以及一个"确定"按钮。

### 语法

```
window.alert(message);
```

> **备注：**
>
> ```js
> alert(uid = `${uid}`);
>
> // alert(`desc ${key}`) !== console.log(`desc`, key);
> ```

- `message` 是要显示在对话框中的文本字符串，如果传入其他类型的值，会转换成字符串。

### 示例

```js
window.alert("Hello world!");
```

显示如下 (不同的浏览器下显示不同):

![Image:AlertHelloWorld.png](alerthelloworld.png)

### 附注

警告对话框使用在无需用户确认的情况下，否则应该使用其他类型的对话框，比如[confirm](/zh-CN/DOM/window.confirm), [prompt](/zh-CN/DOM/window.prompt).

The following text is shared between this article, DOM:window\.prompt and DOM:window\.confirm 这里显示的对话框是一个模态窗口，它能阻止用户对浏览器窗口界面的其他部位进行操作，你不应该过多的使用这种模态窗口。

扩展开发者有时候需要使用[nsIPromptService](/zh-CN/nsIPromptService)接口来代替`该 alert`方法。

从 Firefox 4 开始，在网页中弹出的对话框都换成了标签页范围内的模态窗口，即不会影响其他的标签页，同时还能阻止过多次数的弹窗。

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat}}

### 参见

[confirm](/zh-CN/docs/Web/API/Window/confirm), [prompt](/zh-CN/docs/Web/API/Window/prompt)

扩展开发者应该查看[alert()](/zh-CN/nsIPromptService#alert)和[alertCheck()](/zh-CN/nsIPromptService#alert)
