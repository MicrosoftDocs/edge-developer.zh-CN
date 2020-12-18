---
description: 此页面概述了 EdgeHTML 12 中的新增功能。
title: EdgeHTML 12 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8a96d75ff7decf2c6efdfee3be94736707fea5a6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232367"
---
# EdgeHTML 12 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 引入了 EdgeHTML，这是一种新的"活动"引擎，它的核心是互操作性，以确保你始终获得最新、最全面的 Windows Web 平台。  Microsoft Edge 从支持 ActiveX 控件、浏览器帮助程序对象 \ (BHOs\) 和其他经过的 Web 开发实践所需的旧代码中彻底打破过去。  此外，Microsoft Edge 还提供本机 PDF 支持。  自 IE11 起，旧版文档模式已弃用，并且对于 Microsoft Edge，支持这些模式的浏览器基础结构不存在。  有关详细信息，请查看[IEBlog。](/archive/blogs/ie/living-on-the-edge-our-next-step-in-interoperability)  

下面是 EdgeHTML 12 在 [Windows 10](https://blogs.windows.com/windowsexperience/2015/07/28/windows-10-free-upgrade-available-in-190-countries) \ (07/2015 内部版本 10240\) 中附带的更改。  有关整个 Microsoft Edge 浏览器更改的概述，请参阅"从过去开始"的中断[：Microsoft](https://blogs.windows.com/msedgedev/2015/02/26)新 Web 呈现引擎的创建和与过去的中断，第 2 部分：与[ActiveX、VBScript、attachEvent.](https://blogs.windows.com/msedgedev/2015/05/06)  

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_12](./edgehtml-12.md)  

## 新功能  

### 内容安全策略 1.0  

Microsoft Edge 现在实现内容安全策略 \ (CSP\) 1.0。  CSP 安全标准使 Web 开发人员能够控制资源 \ (脚本、CSS、插件、图像等\) 特定页面可以提取或执行这些资源，目的是防止跨网站脚本 \ (XSS\) 、点击劫持和其他试图在受信任网页上下文中执行恶意内容的代码注入攻击。  查看 [内容安全策略，](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy) 详细了解 Microsoft Edge 中的云解决方案提供商。  

### 筛选器效果  

Microsoft Edge 提供了一种向元素添加视觉效果的简便方法。  使用该属性可以添加模糊、调整亮度、添加投影、更改不透明度等内容到 `filter` 元素。  使用纯 CSS，你可以对一个元素应用多个筛选器效果，并设置筛选器的动画。  有关详细信息，请参阅筛选器 [效果](https://developer.mozilla.org/docs/Web/CSS/filter)。  

### JavaScript  

JavaScript 支持在最终版本的 Internet Explorer \ (IE11\) 和 Microsoft Edge 之间略有不同。  Edge 中的新功能包括：  

:::row:::
   :::column span="1":::
      **明细表**  
   :::column-end:::
   :::column span="2":::
      [class](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/class) \ (experimental\) [for...of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **对象**  
   :::column-end:::
   :::column span="2":::
      [Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)、 [Proxy](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy)、 [Symbol](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Symbol)、 [WeakSet](/scripting/javascript/reference/weakset-object-javascript)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **函数**  
   :::column-end:::
   :::column span="2":::
      [acosh](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh)， [codePointAt](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/codepointat)， [fromCodePoint](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/fromcodepoint) [，osht](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot)， [imul](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/imul)， [isInteger](/scripting/javascript/reference/number-isinteger-function-number-javascript)， [isNaN](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number/isnan)， [raw](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/raw)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **方法**  
   :::column-end:::
   :::column span="2":::
      [includes](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/includes)， [keys](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) \ (Array\) ， [repeat](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) \ (String\) ， [values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/values) \ (Array\)   
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **其他功能**  
   :::column-end:::
   :::column span="2":::
      [Functions](https://developer.mozilla.org/docs/Learn/JavaScript/Building_blocks/Functions) \ (experimental\) ， [Generators，](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)  [Iterators，](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators) [Regular Expression `y` flag](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/RegExp) \ (experimental\) ， Template [strings，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals) [Unicode code point escape characters](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Lexical_grammar#String_literals)  
   :::column-end:::
:::row-end:::  

有关跨 Internet Explorer、Microsoft Edge 和 Microsoft Store 应用的 JavaScript 支持的比较，请参阅 [JavaScript 版本信息](./javascript-version-information.md)。  

### 媒体捕获和流  

Microsoft Edge 引入了对基于 [W3C](https://w3c.github.io/mediacapture-main/getusermedia.html) 媒体捕获和流规范的媒体捕获和流 API 的支持。  这些 JavaScript API 允许网页在用户许可下访问媒体捕获设备，如网络摄像机或麦克风。  通过使用媒体捕获和流 API，可以创建使用网络摄像机捕获照片或从麦克风捕获语音邮件等方案。  在 Microsoft Edge 开发人员博客上阅读有关 Microsoft Edge 中的[媒体捕获功能。](https://blogs.windows.com/msedgedev/2015/05/13)  

### 新的 HTML 元素和属性  

*   `meter` 元素  
*   `picture` 元素  
*   `template` 元素  
*   `image` element： `srcset` and `sizes` attributes \ (Microsoft Edge Developer [blog post](https://blogs.windows.com/msedgedev/2015/06/08)\)   
*   `selectionDirection` 属性  
*   `input type=time` and `input type=datetime-local`  

### 对象 RTC API  

对象 Real-Time Communications \ (ORTC\) 使媒体 \ (audio and/or video\) 可通过本机 JavaScript API 在 Web 浏览器、移动设备和服务器之间实时流式传输 \ (发送和接收\) 。  有关 Microsoft Edge 中的 ORTC 的详细信息，请查看开发人员指南主题[Object RTC API。](https://ortc.org)  

### 阅读视图  

Microsoft Edge 提供了一个阅读视图，使网页的阅读体验更简洁、更像书籍一样，而不会分散页面上无关内容或其他辅助内容的干扰。  阅读视图可以从阅读视图 \ (书籍图标\) 按钮或与中 `Ctrl` + `Shift` + `R` 切换。  有关详细信息 [，请访问](../browser-features/reading-view.md) 阅读视图。  

### 搜索提供程序发现  

丰富的搜索集成内置于 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。  Microsoft Edge 遵循 [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范来发现和使用 Web 搜索提供程序。  如果你是搜索提供程序， [请](../browser-features/search-provider-discovery.md) 详细了解如何确保 Microsoft Edge 支持你的服务。  

### 对 WebKit API 的支持  

为了改进兼容性，Microsoft Edge 支持各种 `-webkit-` 前缀 API。  有关受支持的 API 的完整 `-webkit-` 列表，请使用 [API 目录](https://developer.microsoft.com/microsoft-edge/platform/catalog/?page=1&q=webkit)。  

### Web 音频  

Microsoft Edge 引入了对 [W3C Web 音频 API 规范](https://webaudio.github.io/web-audio-api) 的支持。  Web 音频是一种高级 JavaScript API，用于处理和合成 Web 应用程序中的音频，以提供丰富的音频和音乐体验。  虽然 HTML5 元素允许基本流式音频播放，但 Web 音频 API 提供了一系列 API，允许你通过紧密同步播放多个声音，对混合音频应用增益、淡化、转换和基本 `audio` 效果。  阅读有关 [Web 音频] (。开发人员指南和 [Microsoft Edge](https://blogs.windows.com/msedgedev/2015/05/19)开发人员博客中的 /multimedia/web-audio.md。  

### Web 驱动程序  

[W3C WebDriver API](https://w3.org/TR/webdriver)是一个平台和中性语言接口以及线路协议，允许程序或脚本控制 Web 浏览器的行为。  WebDriver 使开发人员能够创建模拟用户交互的自动化测试。  这不同于 JavaScript 单元测试，因为 WebDriver 可以访问浏览器中运行的 JavaScript 所没有的功能和信息，并且它可以更加准确地模拟用户事件或操作系统级事件。  WebDriver 还可以在单个测试会话中跨多个窗口、选项卡和网页管理测试。  若要详细了解如何开始使用适用于 Microsoft Edge 的 WebDriver，请查看[WebDriver。](../../webdriver/index.md)  

## EdgeHTML 12 中的新 API  

以下是 EdgeHTML 12 中新 API 的完整列表。  它们以 . `[interface name].[api name]`  

 > [!NOTE] 
 > 许多 API 在 IE11 中可用。  以下 EdgeHTML 12 数据作为比较 EdgeHTML 初始版本与更高版本的基线。  

<iframe height='580' scrolling='no' title='EdgeHTML 12 中的新 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/pPOwby/?height=580&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 EdgeHTML 12 中的笔新 API（由 Microsoft Edge 文档 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/pPOwby/'> </a> <a href='https://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) </a> <a href='https://codepen.io'> CodePen 上 </a> ）。</iframe>  
