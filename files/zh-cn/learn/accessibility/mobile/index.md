---
title: 移动端无障碍
slug: Learn/Accessibility/Mobile
---

{{LearnSidebar}}{{PreviousMenuNext("Learn/Accessibility/What_is_Accessibility","Learn/Accessibility/CSS_and_JavaScript", "Learn/Accessibility")}}

随着通过手机设备访问网络越来越受欢迎，例如 iOS 和 Android 等流行的平台都拥有了完善的无障碍工具，在这些平台上考虑你网页的无障碍访问性是一件很重要事情。本文将着重介绍移动端无障碍的注意事项。

<table>
  <tbody>
    <tr>
      <th scope="row">前置条件：</th>
      <td>
        基本的计算机素养，对 Javascript,html,css 有基本的认识，对<a
          href="/zh-CN/docs/Learn/Accessibility"
          >之前的课程</a
        >有一定的理解。
      </td>
    </tr>
    <tr>
      <th scope="row">目标：</th>
      <td>了解移动端上无障碍的存在的问题，即如何解决他们。</td>
    </tr>
  </tbody>
</table>

## 移动设备上的无障碍

现代移动设备对无障碍和大多数 Web 标准有很好的支持。那个因为移动设备和桌面设备使用了完全不同的技术而强制要求开发者根据设备不同将用户分发到不同的域名的时代已经结束了（虽然现在还有一些公司仍然在检测用户移动设备的使用，并为他提供一个独立的手机域名）。

目前，移动设备一般都可以处理“full fat”的网站了，同时，为了能够让盲人成功的使用网站，主流平台甚至还内置了阅读器。移动设备也倾向于对“[WAI-ARIA](/zh-CN/docs/Learn/Accessibility/WAI-ARIA_basics)”有个好的支持。

你只要需要遵守好的 web 设计规范和最佳的无障碍实践，就可以让你的网站在手机上可用且无障碍。

移动设备需要特别考虑一些例外情况; 主要的是：

- 控件交互 - 确保类似于按钮的 UI 控件可以在移动端（主要是触摸屏）和桌面端（主要是鼠标/键盘）无障碍的使用
- 用户输入 - 在移动端尽可能的减少用户输入的要求（例如在表单中，尽量少打字）。
- 响应式设计 - 确保移动端布局正常的情况下，节省需要下载的图片大小，并考虑为高分辨率的屏幕提供图片。

## Android 和 iOS 上的屏幕阅读器测试总结

最常见的移动端平台具有功能全面的屏幕阅读器。这些功能和桌面端屏幕阅读器大致相同，除了移动端屏幕阅读器大量的使用手势操作而不是按键组合操作。

让我们来看看最主要的两个 - Android 上的 TalkBack 和 iOS 上的 VoiceOver。

### Android TalkBack

TalkBack 是运行在 Android 系统上的。

在菜单中选择 设置 > 无障碍 > TalkBack，打开开关即可打开 TalkBack。按照屏幕提示操作即可。

**注意**: 旧版本的 TalkBack 的打开方式有[一点不同](https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback)。

当 TalkBack 打开时，你的 android 设备的基本操作将有一点点不同。举个例子：

1. 点击一个应用将会选择它，同时，你的设备将会告诉你这个 APP 是什么。
2. 如果你按在功能键上向左右滑动，将会在应用、按钮或控件之间切换。设备将会读出每一项。
3. 双击任何地方将会打开某个应用或者选择某个选项。
4. 你也可以“通过触摸来探索” - 将手指按在屏幕上并拖拽，然后你的设备将会读出你移动经过的不同的应用或项目。

如果你想关掉 TalkBack:

1. 通过上面的手势导航到“设置”
2. 导航到 无障碍 > TalkBack
3. 导航到滑动的开关，并激活它将其关闭。

**注意**: 你可以通过向左上方滑动返回桌面，如果你有多个桌面，你可以通过两个手指在屏幕上左右滑动来切换桌面。

**注意**: 关于“TalkBack”的收拾完整列表，查看[使用 TalkBack 手势](https://support.google.com/accessibility/android/answer/6151827)。

#### 解锁手机

当 TalkBack 处于打开状态时，解锁手机有一点点不同。

你可以通过双根手指从底部向上滑动去锁定手机。如果你设置了密码或者手势，你将会进入相关的入口页去输入密码或手势。

你可以通过触摸屏幕的中下部去找到解锁按钮，然后双击它解锁手机。

#### 全局菜单和本地菜单

TalkBack 允许你使用全局和本地菜单，无论你已经导航到哪个位置。前者提供和设备相关的全局选项，后者提供和当前你所在的应用或屏幕相关的选项。

要进入这些菜单：

1. 快速向下然后向右滑动唤起全局菜单。
2. 快速向上然后向右滑动唤起本地菜单。
3. 向左右滑动可以选择不同的菜单。
4. 一旦你选择了你想要的选项，双击它可以直接选择。

想要查看全局和本地上下文菜单的详细选项，请查看[使用全局和本地上下文菜单](https://support.google.com/accessibility/android/answer/6007066)

#### 浏览网页

你可以在浏览器中使用本地上下文菜单来查看仅使用标题，或者表单控件，或者链接，或者逐行浏览的方式浏览网页。

例如，当“TalkBack”处于开启状态：

1. 打开浏览器
2. 激活地址栏
3. 进入一个有一堆标题的网页，就像 bbc.co.uk 的首页。输入网址的文字：

    1. 通过左右滑动来找到地址栏，然后双击它
    2. 手指按在虚拟键盘上，选择你想要的字符，松开手指输入它，重复上述操作输入完所有的字符
    3. 输入完之后，找到 Enter 键并按下

4. 向左右滑动在页面上不同的项目之间切换
5. 向上然后向右滑动进入本地内容菜单
6. 向右滑动直到你找到“标题和标识”选项
7. 双击选择它。现在你就可以通过左右滑动在标题和 ARIA 标识之间切换
8. 向右向上滑动之后，进去本地上下文菜单，选择“默认”，就可以返回默认模式

**注意**: 查看[TalkBack 入门](https://support.google.com/accessibility/android/answer/6283677?hl=en&ref_topic=3529932)获取更完整的文档。

### iOS VoiceOver

它是在 iOS 系统上的一个移动端 VoiceOver。

要打开它，请在设置中选择 常规 > 无障碍 > VoiceOver。按下 VoiceOver 的开关去启动它（你还会在页面中看到很多和 VoiceOver 相关的其他选项）。

一旦开启 VoiceOver，iOS 的基本操作手势将有所不同：

1. 单击将会导致项目被选中，你的设备将会告诉你，你点击的是什么应用。
2. 你也可以通过向左右滑动屏幕来移动屏幕上的项目，或者在屏幕上滑动手指以移动项目（当你找到你想要的项目的时候，把手指离开屏幕来选中它）。
3. 双击屏幕上的任意位置，可以激活选中的项目（例如，打开选中的 App）。
4. 通过三根手指滑动浏览页面。
5. 用两个手指点击来执行上下文相关的操作，例如在相机里拍摄照片。

要再次将其关闭，你必须使用上述手势导航到 设置 > 常规 > 无障碍 > VoiceOver，然后将 VoiceOver 切换回关闭状态。

#### 解锁手机

你需要正常的按下 HOME 键（或划过）就可以解锁手机了。如果你设置了密码，你可以通过滑动来选择每一个数字，然后在找到合适的数字后双击输入每一个数字。

#### 使用转子

当 VoiceOver 打开时，您可以使用一种名为“转子”的导航功能，该功能可让您快速从多种常用选项中进行选择。要使用它：

1. 像转动拨号盘一样在屏幕上扭动两根手指。当你扭动更多的时候，每个选项都会被朗读。你可以来回循环选项。
2. 一旦你找到你想要的选项：

    1. 松开手指来选择它。
    2. 如果这个选项可以调整大小（例如音量或说话频率）的值，则可以通过上下滑动来控制所选项的值。

转子上的提供的选项是上下文相关的，他们会根据你所在的 APP 或者试图不同而不同。（参见下面的例子）

#### 浏览网页

让我们用 VoiceOver 浏览网页：

1. 打开你的浏览器
2. 激活地址栏
3. 进入这一个有一堆标题的网站，就像 bbc.co.uk 的首页。输入网址：

    1. 通过向左右滑动来选择地址栏，找到之后双击它
    2. 对于每一个字符，手指在虚拟键盘上长按，直到找到你想要的字符，然后释放手指来选择他。双击它输入
    3. 完成后，找到 Enter 键并按下

4. 向左右滑动来在页面上切换不同的项目。你可以通过双击来选择他（例如，按住链接）。
5. 默认情况下，被选中的转子选项应该是说话频率，你可以通过上下滑动来增加或减少讲话速率。
6. 现在像拨号盘一样围绕屏幕转动两根手指，以显示转子并在其选项之间移动。以下是可用选项的一些示例：

    1. _说话速率：改变说话速率_
    2. _容器：在页面不同予以的容器间切换_
    3. _标题：在页面上的标题之间切换_
    4. _链接：在页面上的链接之间切换_
    5. _表单控件：在页面上的表单控件之间切换_
    6. 语言：在不同的翻译之间切换，如果可用的话

7. 选择标题，现在你可以通过上下滑动在页面的不同标题中切换

**注意**: 有关 iOS 上可用的 VoiceOver 手势以及有关辅助功能的其他提示的更完整资料可以查看[在你的设备上用 VoiceOver 测试辅助功能](https://developer.apple.com/library/content/technotes/TestingAccessibilityOfiOSApps/TestAccessibilityonYourDevicewithVoiceOver/TestAccessibilityonYourDevicewithVoiceOver.html#//apple_ref/doc/uid/TP40012619-CH3)

## 控制机制

在我们的 CSS 和 JavaScript 无障碍文章中，我们研究了特定于某种控制机制的事件的概念（请参阅[鼠标特定的事件](/zh-CN/docs/Learn/Accessibility/CSS_and_JavaScript#mouse-specific_events)）。回顾一下，因为其他控制机制不能激活相关的功能，将会导致辅助功能的问题。

举例来说，[点击事件](/zh-CN/docs/Web/API/GlobalEventHandlers/onclick)在无障碍方面是好的 - 通过点击处理器设置的元素，选中它并按下回车或返回，或者在触摸屏设备上点击它，可以调用关联的事件处理程序。试试我们的例子[simple-button-example.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/simple-button-example.html)([查看在线例子](https://mdn.github.io/learning-area/accessibility/mobile/simple-button-example.html)) 来看看我们是什么意思。

另一方面，像[mousedown](/zh-CN/docs/Web/API/GlobalEventHandlers/onmousedown)和[mouseup](/zh-CN/docs/Web/API/GlobalEventHandlers/onmouseup)这些特定的鼠标事件会产生一些问题 - 他们的事件处理程序不能使用除了鼠标意外的设备操作。

如果你尝试通过键盘或触摸来试试我们的[simple-box-drag.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/simple-box-drag.html)([查看在线例子](https://mdn.github.io/learning-area/accessibility/mobile/simple-box-drag.html))，你将发现问题。它发生的原因是我们用了下面的代码：

```js
div.onmousedown = function() {
  initialBoxX = div.offsetLeft;
  initialBoxY = div.offsetTop;
  movePanel();
}

document.onmouseup = stopMove;
```

为了能其他表单空间起作用，你需要使用其他同等的事件代替，比如在触屏设备上用 touch 事件：

```js
div.ontouchstart = function(e) {
  initialBoxX = div.offsetLeft;
  initialBoxY = div.offsetTop;
  positionHandler(e);
  movePanel();
}

panel.ontouchend = stopMove;
```

我们提供了一个简单的例子来展示如何使用鼠标和触摸事件 - [multi-control-box-drag.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/multi-control-box-drag.html) ([查看在线例子](https://mdn.github.io/learning-area/accessibility/mobile/multi-control-box-drag.html))

**注意**: 你可以看到一个功能完善的例子，展示如何在实现[游戏控制机制](/zh-CN/docs/Games/Techniques/Control_mechanisms)中实现不同的控制机制。

## 响应式设计

[响应式设计](/zh-CN/docs/Web/Progressive_web_apps/Responsive/responsive_design_building_blocks)是根据屏幕大小和分辨率等因素动态更改您的应用程序的布局和其他功能的做法，因此对于不同设备类型的用户来说，它们是可用和可访问的。

特别是，移动端设备需要解决的最常见的问题是：

- 移动端设备布局的适用性。例如，在窄屏上多列布局不能很好的工作，需要增加文字大小以提高可读性。这些问题可以通过[媒体查询](/zh-CN/docs/Web/CSS/Media_Queries)、[viewport](/zh-CN/docs/Web/HTML/Viewport_meta_tag)、[弹性布局](/zh-CN/docs/Learn/CSS/CSS_layout/Flexbox)来解决。
- 节省下载的图片大小。一般来说，小屏幕设备不需要与桌面设备一样大的图像，而且它们将更可能在慢速网络连接上。因此，适当地缩小屏幕设备以缩小图像是明智的。您可以使用[响应式图像技术](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)处理此问题。
- 考虑高分辨率。许多移动设备具有高分辨率屏幕，因此需要更高分辨率的图像，使得显示器可以继续看起来清晰和锐利。再次，您可以使用响应式图像技术来适当地提供图像。此外，使用 SVG 矢量图像格式可以满足许多图像要求，这些格式在目前的浏览器中得到了很好的支持。SVG 有一个小文件大小，并将保持清晰的大小显示在（请参阅[向网络添加矢量图形](/zh-CN/docs/Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web)一些更多的细节）。

**注意**: 我们不会在这里对响应式设计进行完整的讨论，因为他们在 MDN 其他地方都有涉及（参考上面的链接）。

### 具体的需要注意的点

这里有很多其他重要的需要考虑的点，他们可以让我们通过移动设备访问网站时更无障碍。

#### 不能缩放

我们可以利用[viewport](/zh-CN/docs/Web/HTML/Viewport_meta_tag)来禁止用户缩放，在你的[\<head>](/zh-CN/docs/Web/HTML/Element/head)中加入下列代码即可：

```html
<meta name="viewport" content="user-scalable=no">
```

如果可能的话，你绝对不应该这么做 - 很多人都会依靠缩放来看你网站的内容，所以不使用缩放这个功能是一个很糟糕的主意。在某些情况下缩放会破坏 UI；这种情况下，你觉得你绝对需要缩放，你可以提供一些别的近似的方法。例如增加一个控制文字大小的控件，通过这种方式就不会破坏 UI 了。

#### 保持菜单可用

因为移动设备上的屏幕非常窄，所以使用媒体查询和其他技术使得导航菜单缩小到显示屏顶部的一个小图标，只有在需要的时候才展示菜单，这种方式在移动设备上很常见的。这通常由“三横线”图标表示，并且设计模式因此被称为“汉堡菜单”。

在实现这样的菜单时，需要确保显示控件的控件可以通过适当的控制机制（通常为移动触摸）进行访问，如上面的控制机制中所讨论的，并且页面的其余部分被移开 或在菜单被访问时以某种方式隐藏，以避免与导航混淆。

让我们来看一个很好的“[汉堡包菜单”的例子](http://fritz-weisshart.de/meg_men/)

## 用户输入

在移动设备上，输入数据往往比在台式计算机上的同等体验更令用户恼火。使用桌面或笔记本电脑键盘输入文本到表单输入比触摸屏虚拟键盘或微小的移动物理键盘更方便。

出于这个原因，值得尽量减少所需的输入量。作为一个例子，与其让用户每次使用常规文本输入来填写他们的工作标题，而是可以提供一个\<select>菜单，其中包含最常见的选项（这也有助于数据输入的一致性），并提供一个“其他”选项，显示一个文本字段来输入任何异常值。你可以在[common-job-types.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/common-job-types.html)中看到这个想法的一个简单的例子（查看[在线例子](https://mdn.github.io/learning-area/accessibility/mobile/common-job-types.html)）。

也值得考虑在移动平台上使用 HTML5 格式输入类型（如日期），因为它们可以很好地处理它们 - 例如，Android 和 iOS 都会显示可用于设备体验的可用小部件。有关示例，请参阅[html5-form-examples.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/html5-form-examples.html)（请查看[HTML5 表单示例](https://mdn.github.io/learning-area/accessibility/mobile/html5-form-examples.html)） - 尝试加载这些内容并在移动设备上对其进行操作。例如：

- 在输入数字、电话和邮件时，展示合适的虚拟键盘来输入数字。
- 在输入时间和日期时展示合适的选择器来选择时间和日期。

如果你想为桌面端提供不同的解决方案，则可以使用功能检测为您的移动设备始终提供不同的标记。有关检测不同输入类型的原始信息，请参阅[输入类型](http://diveinto.html5doctor.com/detect.html#input-types)，还可以查看我们的[功能检测文章](/zh-CN/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)获取更多信息。

## 总结

在本文中，我们向您提供了有关常见移动设备无障碍问题的一些细节以及如何克服这些问题。我们还通过使用最常用的屏幕阅读器来帮助您进行无障碍测试。

## 参见

- [移动 Web 开发指南](https://www.smashingmagazine.com/guidelines-for-mobile-web-development/) — “Smashing”杂志的文章列表，涵盖移动网页设计的不同技术。
- [使您的网站在触摸设备上工作](http://www.creativebloq.com/javascript/make-your-site-work-touch-devices-51411644) — 有关使用触摸事件来获得在移动设备上进行交互的有用文章。

{{PreviousMenuNext("Learn/Accessibility/Multimedia","Learn/Accessibility/Accessibility_troubleshooting", "Learn/Accessibility")}}
