---
title: scroll-snap-points-x
slug: Web/CSS/scroll-snap-points-x
---

{{CSSRef}}{{SeeCompatTable}}{{deprecated_header}}

## 摘要

**`scroll-snap-points-x`** [CSS](/zh-CN/docs/Web/CSS)属性定义滚动容器中内容的 snap 点的水平位置。

{{cssinfo}}

## 语法

```css
/* 关键值 */
scroll-snap-points-x: none;

/* 重复的 snap 点 */
scroll-snap-points-x: repeat(400px);

/* 全局值 */
scroll-snap-points-x: inherit;
scroll-snap-points-x: initial;
scroll-snap-points-x: unset;
```

### 取值

- `none`
  - : 滚动容器没有定义任何 snap 点。Elements within the scroll container may still define snap points of behalf of the scroll container.（i don't understand this statement）
- `repeat(<长度>)`
  - : 定义 snap 点的一个间隔，从容器相关的边缘开始。仅允许正数长度。

### 形式语法

{{csssyntax}}

## 示例

### HTML

```html
<div id="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

### CSS

```css
#container {
  width: 200px;
  overflow: auto;
  white-space: nowrap;
  scroll-snap-points-x: repeat(100%);
  scroll-snap-type: mandatory;
  font-size: 0;
}

#container > div {
  width: 200px;
  height: 200px;
  display: inline-block;
  line-height: 200px;
  text-align: center;
  font-size: 100px;
}

#container > div:nth-child(even) {
  background-color: #87ea87;
}

#container > div:nth-child(odd) {
  background-color: #87ccea;
}
```

{{EmbedLiveSample("示例", 220, 220)}}

## 规范

此属性曾定义在[early draft of CSS Scroll Snap Points Module](http://www.w3.org/TR/2015/WD-css-snappoints-1-20150326/#scroll-snap-points)中，但是后来在[in favor of element-based snapping](https://lists.w3.org/Archives/Public/www-style/2015Nov/0266.html)规范中被[移除](https://github.com/w3c/csswg-drafts/commit/922af86be789222b8490c92038d1a5142e1c1198)。

## 浏览器兼容性

{{Compat}}
