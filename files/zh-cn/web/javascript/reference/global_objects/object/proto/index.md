---
title: Object.prototype.__proto__
slug: Web/JavaScript/Reference/Global_Objects/Object/proto
---

{{JSRef}}{{Deprecated_header}}

> **警告：** 通过现代浏览器的操作属性的便利性，可以改变一个对象的 `[[Prototype]]` 属性，这种行为在每一个 JavaScript 引擎和浏览器中都是一个非常慢且影响性能的操作，使用这种方式来改变和继承属性是对性能影响非常严重的，并且性能消耗的时间也不是简单的花费在 `obj.__proto__ = ...` 语句上，它还会影响到所有继承来自该 `[[Prototype]]` 的对象，如果你关心性能，你就不应该在一个对象中修改它的 \[\[Prototype]]。相反，创建一个新的且可以继承 `[[Prototype]]` 的对象，推荐使用 {{jsxref("Object.create()")}}。

> **警告：** 当 `Object.prototype.__proto__` 已被大多数浏览器厂商所支持的今天，其存在和确切行为仅在 ECMAScript 2015 规范中被标准化为传统功能，以确保 Web 浏览器的兼容性。为了更好的支持，建议只使用 {{jsxref("Object.getPrototypeOf()")}}。

{{jsxref("Object.prototype")}} 的 `__proto__` 属性是一个访问器属性（一个 getter 函数和一个 setter 函数）, 暴露了通过它访问的对象的内部`[[Prototype]]` (一个对象或 {{jsxref("Global_Objects/null", "null")}})。

使用`__proto__` 是有争议的，也不鼓励使用它。因为它从来没有被包括在 EcmaScript 语言规范中，但是现代浏览器都实现了它。`__proto__` 属性已在 ECMAScript 6 语言规范中标准化，用于确保 Web 浏览器的兼容性，因此它未来将被支持。它已被不推荐使用，现在更推荐使用{{jsxref("Object.getPrototypeOf")}}/{{jsxref("Reflect.getPrototypeOf")}} 和{{jsxref("Object.setPrototypeOf")}}/{{jsxref("Reflect.setPrototypeOf")}}（尽管如此，设置对象的 \[\[Prototype]] 是一个缓慢的操作，如果性能是一个问题，应该避免）。

\_\_proto\_\_ 属性也可以在对象文字定义中使用对象 \[\[Prototype]] 来创建，作为{{jsxref("Object.create()")}} 的一个替代。请参阅：[object initializer / literal syntax](/zh-CN/docs/Web/JavaScript/Reference/Operators/Object_initializer).

## 语法

```js
let Circle = function () {};
let shape = {};
let circle = new Circle();

// 设置该对象的原型链引用
// 过时且不推荐使用的。这里只是举个例子，尽量不要在生产环境中这样做。
shape.__proto__ = circle;

// 判断该对象的原型链引用是否属于 circle
console.log(shape.__proto__ === circle); // true
```

```js
let shape = function () {};
let p = {
    a: function () {
        console.log('aaa');
    }
};
shape.prototype.__proto__ = p;

let circle = new shape();
circle.a();//aaa
console.log(shape.prototype === circle.__proto__);//true

//或者
let shape = function () {};
var p = {
    a: function () {
        console.log('a');
    }
};

let circle = new shape();
circle.__proto__ = p;
circle.a(); //  a
console.log(shape.prototype === circle.__proto__);//false

//或者
function test() {}
test.prototype.myname = function () {
    console.log('myname');
}
let a = new test()
console.log(a.__proto__ === test.prototype);//true
a.myname();//myname

//或者
let fn = function () {};
fn.prototype.myname = function () {
    console.log('myname');
}

let obj = {
    __proto__: fn.prototype
};

obj.myname();//myname
```

注意：这是两个下划线，后面是五个字符的“proto”，后面再跟两个下划线。

## 描述

`__proto__` 的读取器 (getter) 暴露了一个对象的内部 `[[Prototype]]` 。对于使用对象字面量创建的对象，这个值是 {{jsxref("Object.prototype")}}。对于使用数组字面量创建的对象，这个值是 {{jsxref("Array.prototype")}}。对于 functions，这个值是{{jsxref("Function.prototype")}}。对于使用 new fun 创建的对象，其中 fun 是由 js 提供的内建构造器函数之一 ({{jsxref("Array")}}, {{jsxref("Boolean")}}, {{jsxref("Date")}}, {{jsxref("Number")}}, {{jsxref("Object")}}, {{jsxref("String")}} 等等），这个值总是 fun.prototype。对于用 JS 定义的其他 JS 构造器函数创建的对象，这个值就是该构造器函数的 prototype 属性。

`__proto__` 的设置器 (setter) 允许对象的 `[[Prototype]]` 被变更。前提是这个对象必须通过 {{jsxref("Object.isExtensible()")}} 判断为是可扩展的，如果不可扩展，则会抛出一个 {{jsxref("Global_Objects/TypeError", "TypeError")}} 错误。要变更的值必须是一个 object 或{{jsxref("Global_Objects/null", "null")}}，提供其他值将不起任何作用。

要理解原型如何被使用，请查看相关文章：[Inheritance and the prototype chain](/zh-CN/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain)。

`__proto__` 属性是 {{jsxref("Object.prototype")}} 一个简单的访问器属性，其中包含了 get（获取）和 set（设置）的方法，任何一个 `__proto__` 的存取属性都继承于 {{jsxref("Object.prototype")}}，但一个访问属性如果不是来源于 {{jsxref("Object.prototype")}} 就不拥有 `__proto__` 属性，譬如一个元素设置了其他的 `__proto__` 属性在 {{jsxref("Object.prototype")}} 之前，将会覆盖原有的 {{jsxref("Object.prototype")}}。

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat}}

## 兼容性注意事项

在 ECMAScript 2015（ES6）的规范要求中，支持 `__proto__` 是各大 Web 浏览器厂商的要求（虽然符合规范），但其他环境下因为历史遗留的问题，也有可能被使用和支持。

## 更多请参考

- {{jsxref("Object.prototype.isPrototypeOf()")}}
- {{jsxref("Object.getPrototypeOf()")}}
- {{jsxref("Object.setPrototypeOf()")}}
