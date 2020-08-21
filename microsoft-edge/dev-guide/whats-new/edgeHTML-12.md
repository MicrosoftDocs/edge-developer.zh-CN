---
description: 此页面概述了 EdgeHTML 12 中的新增功能。
title: EdgeHTML 12 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 51c5c89b8ae4ea0e02de68f6b413c162336661f6
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941959"
---
# EdgeHTML 12 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 引入了 EdgeHTML，EdgeHTML 是一个专门为其本质而设计的新"living"引块，以确保你始终获得最新且功能最高的 Windows Web 平台。  Microsoft Edge 从过来开始大简化分页，可从旧代码中免费提供用于支持 ActiveX 控件、浏览器帮助程序对象 \ (BHOS\ ) 和其他比例 Web 开发实践。  此外，Microsoft Edge 还提供本机 PDF 支持。  从 IE11 开始，旧版文档模式已被弃用，使用 Microsoft Edge 则支持旧内容的浏览器基础结构不存在。  有关详细信息，[请查看 IEBLog。](/archive/blogs/ie/living-on-the-edge-our-next-step-in-interoperability)  

下面是初始版本 Windows 10 / (07/2015（内部 [版本 10240\) ）](https://blogs.windows.com/windowsexperience/2015/07/28/windows-10-free-upgrade-available-in-190-countries) 中发货的更改。  有关整体 Microsoft Edge 浏览器的更改概述，请参阅[过去的部分：Microsoft](https://blogs.windows.com/msedgedev/2015/02/26)新 Web 呈现引引程的鸟摘和过去部分[2：例如略微调到 ActiveX、VBScript、attachEvent...](https://blogs.windows.com/msedgedev/2015/05/06)  

下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_12](./edgehtml-12.md) ：。  

## 新增功能  

### 内容安全策略 1.0  

Microsoft Edge 现在实现内容安全策略 \ (CSP\) 1.0。  CSP 安全标准使 Web 开发人员能够控制资源 \ (脚本、CSS、插件、 图像（等）图像 ) ，特殊页面可能会通过阻止跨站脚本 \ (XSS\) 、clickjacking 以及其他代码注入程序处理受信任网页上下文中的任意内容的情况下，执行或执行特定页面。  请参阅内容 [安全策略，](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy) 了解有关 Microsoft Edge 中的 CSP 的详细信息。  

### 筛选器效果  

Microsoft Edge 提供了一种向元素添加视觉效果的简单方法。  使用 `filter` 可添加模视图、调整亮度、添加拖放功能、更改不明确度等等。  使用单复 CSS 时，你可以将多个筛选效果应用于一个元素并对筛选进行动画处理。  有关详细信息，请参阅" [筛选器"效果](https://developer.mozilla.org/docs/Web/CSS/filter)。  

### JavaScript  

JavaScript 支持在最终版本的 Internet Explorer \ (IE11\) 和 Microsoft Edge 间略有不同。  Microsoft Edge 的新增功能包括：  

:::row:::
   :::column span="1":::
      **明细表**  
   :::column-end:::
   :::column span="2":::
      [class](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/class) \ (experimental\) [for...的](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **对象**  
   :::column-end:::
   :::column span="2":::
      [Promise、](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)[代理](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy)[、符号](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Symbol)[、WeakSet](/scripting/javascript/reference/weakset-object-javascript)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **函数**  
   :::column-end:::
   :::column span="2":::
      [acosh，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh) [codePointAt，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/codepointat) [fromCodePoint，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/fromcodepoint) [hypot，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot) [imul，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/imul) [isInteger，](/scripting/javascript/reference/number-isinteger-function-number-javascript) [isNaN，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number/isnan) [raw](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/raw)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **方法**  
   :::column-end:::
   :::column span="2":::
      [includes，](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/includes) [keys](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) \ (Array\) ， [repeat](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) \ (String\) ， [values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/values) \ (Array\)   
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **其他功能**  
   :::column-end:::
   :::column span="2":::
      [函数](https://developer.mozilla.org/docs/Learn/JavaScript/Building_blocks/Functions)\ (试用性\) 、[生成器](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)、[验证](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)器、[正则表达式 `y` 标](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/RegExp)志 \ (experimental\) ， [Template 字符串](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals)[，Unicode 代码点转置字符](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Lexical_grammar#String_literals)  
   :::column-end:::
:::row-end:::  

有关跨公司、Microsoft Edge Internet Explorer 和 Microsoft的 JavaScript 支持比较，请参阅 [JavaScript 版本信息](./javascript-version-information.md)。  

### 媒体捕获和流  

Microsoft Edge 将基于 [W3C](https://w3c.github.io/mediacapture-main/getusermedia.html) 媒体捕获和流规范为媒体捕获和流 API 引入了支持。  这些 JavaScript API 允许网页通过用户的权限访问媒体捕获设备，如摄像头或麦克风。  通过使用媒体捕获和流 API，你可以创建方案，例如使用摄相头捕获照片或使用麦克风捕获语音消息。  阅读有关 Microsoft Edge 开发人员博客上的 Microsoft Edge 中 [媒体捕获的详细信息](https://blogs.windows.com/msedgedev/2015/05/13)。  

### 新的 HTML 元素和属性  

*   `meter` 元素  
*   `picture` 元素  
*   `template` 元素  
*   `image` 元素： `srcset` `sizes` 和属性 \ (Microsoft Edge 开发 [人员博客文章](https://blogs.windows.com/msedgedev/2015/06/08)\)   
*   `selectionDirection` 属性  
*   `input type=time` and `input type=datetime-local`  

### 对象 RTC API  

对象实时通信 \ (ORTC\) 支持媒体 \ (音频和/或 video\) 在 Web 浏览器、移动设备和服务器之间直接通过本机 JavaScript API 流式传输 \ (已发送和接收\) 。  若要深入了解有关 ORTC 的详细信息，请查看开发者指南主题[对象 RTC API。](https://ortc.org)  

### 阅读视图  

Microsoft Edge 提供了阅读视图，可更简化、更类似于书页的阅读体验，而无需分不像页面中不相关或其他辅助内容的分开度。  可以通过"阅读"视图 \ping \ (book icon\) 按钮打开或关闭阅读视图，也可以通过它来打开或关闭 `Ctrl` + `Shift` + `R` 。  有关详细信息， [请访问阅读](../browser-features/reading-view.md) 视图。  

### 搜索提供程序发现  

丰富搜索集成内置在 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。  Microsoft Edge 遵循 [1.1 规OpenSearch国](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) ，以发现和使用 Web 搜索提供商。  如果你是搜索提供商， [请阅读有关](../browser-features/search-provider-discovery.md) 如何确保 Microsoft Edge 支持你的服务的详细信息。  

### 支持 WebKit API  

为改进的兼容性，Microsoft Edge 支持多种 `-webkit-` 前缀 API。  有关支持的 API `-webkit-` 的完整列表， [请使用 API 目录](https://developer.microsoft.com/microsoft-edge/platform/catalog/?page=1&q=webkit)。  

### Web 音频  

Microsoft Edge 引入了 [对 W3C Web 音频 API 规范](https://webaudio.github.io/web-audio-api) 的支持。  Web 音频是一个高级别 JavaScript API，可用于处理和使 Web 应用程序中的音频合成，从而提供丰富的音频和音乐体验。  尽管 HTML5 `audio` 元素允许执行基本流式播放，但 Web 音频 API 提供的 API 可以提供一系列 API，这些 API 允许你使用紧密同步播放多种声音，以及在混合音频上应用增长、淡化、过渡和基本效果。  阅读有关 [Web 音频] (。[](https://blogs.windows.com/msedgedev/2015/05/19) [Microsoft Edge Developer blog](https://blogs.windows.com/msedgedev/2015/05/19)  

### Web Driver  

[W3C WebDriver API](https://w3.org/TR/webdriver)是一个平台和中不便语言接口，而有线协议允许程序或脚本来控制 Web 浏览器的行为。  WebDriver 使开发人员能够创建模拟用户交互的自动化测试。  这与 JavaScript 单元测试不同，因为 WebDriver 具有对在浏览器中运行的 JavaScript 不具体的功能和信息的访问权限，并且可更准确地模拟用户事件或操作系统级别事件。  WebDriver 还可以在单个测试会话中管理跨多个窗口、选项卡和网页的测试。  有关如何开始使用 WebDriver for Microsoft Edge 的详细信息，请查看[WebDriver。](../../webdriver.md)  

## EdgeHTML 12 中的新 API  

下面是 EdgeHTML 12 中的新 API 的完整列表。  它们以格式列出 `[interface name].[api name]` 。  

 > [!NOTE] 
 > 其中许多 API 都在 IE11 中可用。  对于比较初始版本的 EdgeHTML 和更高版本，以下适用于 EdgeHTML 12 的数据提供了基准。  

<iframe height='580' scrolling='no' title='EdgeHTML 12 中的新 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/pPOwby/?height=580&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/pPOwby/'> CodePen 上查看 Microsoft Edge 的 </a> Microsoft Edge <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> (@MicrosoftEdgeDocumentation) <a href='https://codepen.io'> 笔新 </a> API。</iframe>  
