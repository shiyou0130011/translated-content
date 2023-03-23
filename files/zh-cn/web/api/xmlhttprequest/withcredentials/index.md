---
title: XMLHttpRequest.withCredentials
slug: Web/API/XMLHttpRequest/withCredentials
---

{{APIRef('XMLHttpRequest')}}

**`XMLHttpRequest.withCredentials`** 属性是一个 {{jsxref("Boolean")}} 类型，它指示了是否该使用类似 cookie、Authorization Headers (头部授权) 或者 TLS 客户端证书这一类资格证书来创建一个跨站点访问控制（cross-site `Access-Control`）请求。在同一个站点下使用 `withCredentials` 属性是无效的。

此外，这个标志还用于指示是否需要忽略响应中的 cookie。默认值是 `false`。如果在发送来自其他域的 `XMLHttpRequest` 请求之前，未设置`withCredentials` 为 `true`，那么就不能为它自己的域设置 cookie 值。而通过设置 `withCredentials` 为 true 获得的第三方 cookie，将依旧遵循同源策略，因此不能被发起请求的脚本通过 [document.cookie](/zh-CN/docs/Web/API/Document/cookie) 或者响应标头访问。

> **备注：** 永远不会影响到同源请求

> **备注：** 不同域下的 `XmlHttpRequest` 响应，不论其 `Access-Control-` Header 设置什么值，都无法为它自身站点设置 Cookie 值，除非它在请求之前将 `withCredentials` 设为 true。

## 示例

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', 'http://example.com/', true);
xhr.withCredentials = true;
xhr.send(null);
```

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat}}
