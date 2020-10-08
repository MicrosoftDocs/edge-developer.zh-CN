---
description: 此页面概述了 EdgeHTML 12 中的新增功能。
title: EdgeHTML 12 中的新增功能和 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 51c5c89b8ae4ea0e02de68f6b413c162336661f6
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941959"
---
# EdgeHTML 12 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 介绍了 EdgeHTML，这是一种新的 "动态" 引擎，使用其核心中的互操作性设计，可确保你始终获得最新、最强大的 Windows web 平台。  Microsoft Edge 提供与支持 ActiveX 控件、浏览器帮助程序对象 \ (Bho \ ) 和其他 bygone web 开发做法所需的旧代码的完全中断。  此外，Microsoft Edge 提供本机 PDF 支持。  从 IE11，旧版文档模式已弃用，并且有 Microsoft Edge，支持它们的浏览器基础结构不存在。  有关详细信息，请查看 [IEBlog](/archive/blogs/ie/living-on-the-edge-our-next-step-in-interoperability) 。  

下面是 [Windows 10](https://blogs.windows.com/windowsexperience/2015/07/28/windows-10-free-upgrade-available-in-190-countries) (07/2015 的初始版本，内部版本 10240 \ ) 附带的 EdgeHTML 12 的更改。  有关对整个 Microsoft Edge 浏览器所做更改的概述，请参阅 [过去的中断： Microsoft 新 web 呈现引擎的出生](https://blogs.windows.com/msedgedev/2015/02/26) 和过去的 [中断，第2部分：说出对 ActiveX、VBScript、attachEvent 的再见](https://blogs.windows.com/msedgedev/2015/05/06)。  

下面是以下更改列表的固定链接：  [https://aka.ms/devguide_edgehtml_12](./edgehtml-12.md) 。  

## 新增功能  

### 内容安全策略1。0  

Microsoft Edge 现在实现了内容安全策略 \ (CSP \ ) 1.0。  CSP 安全标准使 web 开发人员能够控制 (脚本、CSS、插件、图像等的资源，) 特定页面可以获取或执行的目标，以防止跨站点脚本 \ (XSS \ ) 、clickjacking 和其他代码注入攻击，这些攻击试图在受信任网页的上下文中执行恶意内容。  有关 Microsoft Edge 中的 CSP 的详细信息，请查看 [内容安全策略](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy) 。  

### 筛选效果  

Microsoft Edge 提供了向元素添加视觉效果的简单方法。  使用该 `filter` 属性，您可以添加模糊、调整亮度、添加投影、更改不透明度以及更多的元素。  使用纯粹的 CSS，你可以将多个滤镜效果应用于一个元素并对滤镜进行动画处理。  有关详细信息，请参阅 [筛选效果](https://developer.mozilla.org/docs/Web/CSS/filter)。  

### JavaScript  

在 Internet Explorer \ (IE11 \ ) 和 Microsoft Edge 的最终版本之间，JavaScript 支持略有不同。  Edge 中的新增功能包括：  

:::row:::
   :::column span="1":::
      **明细表**  
   :::column-end:::
   :::column span="2":::
      [class](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/class) \ (实验 \ ) ， [for .。。的](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **对象**  
   :::column-end:::
   :::column span="2":::
      [承诺](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)、 [代理](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Proxy)、 [符号](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Symbol)、 [WeakSet](/scripting/javascript/reference/weakset-object-javascript)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **函数**  
   :::column-end:::
   :::column span="2":::
      [acosh](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh)、 [codePointAt](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/codepointat)、 [fromCodePoint](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/fromcodepoint)、 [hypot](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot)、 [imul](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/imul)、 [isInteger](/scripting/javascript/reference/number-isinteger-function-number-javascript)、 [isNaN](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number/isnan)、 [raw](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/raw)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **方法**  
   :::column-end:::
   :::column span="2":::
      [包括](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/includes)， [Keys](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/keys) \ (array \ ) ， [重复](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) \ (String \ ) ， [值](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/values) \ (数组 \ )   
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **其他功能**  
   :::column-end:::
   :::column span="2":::
      [函数](https://developer.mozilla.org/docs/Learn/JavaScript/Building_blocks/Functions) \ (实验性 \ ) 、 [生成器](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)、  [迭代](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Iterators_and_generators)器、 [正则表达式 `y` 标志](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/RegExp) \ (实验 \ ) 、 [模板字符串](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Template_literals)、 [Unicode 编码点转义字符](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Lexical_grammar#String_literals)  
   :::column-end:::
:::row-end:::  

有关 Internet Explorer、Microsoft Edge 和 Microsoft Store 应用之间的 JavaScript 支持的比较，请参阅 [JavaScript 版本信息](./javascript-version-information.md)。  

### 媒体捕获和流  

Microsoft Edge 引入了对基于 [W3C 媒体捕获和流](https://w3c.github.io/mediacapture-main/getusermedia.html) 规范的媒体捕获和流 api 的支持。  这些 JavaScript Api 允许网页使用来自用户的权限访问媒体捕获设备（如网络摄像头或麦克风）。  通过使用媒体捕获和流 Api，你可以创建方案，例如使用网络摄像头捕获照片或捕获来自麦克风的语音消息。  阅读有关 microsoft edge [开发人员博客](https://blogs.windows.com/msedgedev/2015/05/13)上的 microsoft edge 中的媒体捕获的详细信息。  

### 新的 HTML 元素和属性  

*   `meter` 元素  
*   `picture` 元素  
*   `template` 元素  
*   `image` 元素： `srcset` 和 `sizes` 属性 \ (Microsoft Edge 开发人员 [博客文章](https://blogs.windows.com/msedgedev/2015/06/08)\ )   
*   `selectionDirection` 属性  
*   `input type=time` and `input type=datetime-local`  

### 对象 RTC API  

对象实时通信 \ (ORTC \ ) 启用媒体 \ (音频和/或视频 \ ) 通过本机 JavaScript Api 直接在 web 浏览器、移动设备和服务器之间通过实时发送和接收 \ (。  有关 Microsoft Edge 中的 ORTC 的详细信息，请参阅开发人员指南主题 [对象 RTC API](https://ortc.org) 。  

### 阅读视图  

Microsoft Edge 为阅读视图提供了一种更简洁的、书籍喜欢的网页阅读体验，不会干扰页面上的不相关或其他辅助内容。  可在 "阅读视图" 中打开或关闭 "阅读视图 \ (簿图标 \ ) " 按钮，或通过 "地址栏" 或 "与" `Ctrl` + `Shift` + `R` 。  有关详细信息，请访问 [阅读视图](../browser-features/reading-view.md) 。  

### 搜索提供程序发现  

丰富的搜索集成内置于 Microsoft Edge 地址栏，包括搜索建议、web 上的结果、你的浏览历史记录和收藏夹。  Microsoft Edge 遵循 [OpenSearch 1.1](https://github.com/dewitt/opensearch/blob/master/opensearch-1-1-draft-6.md) 规范以发现和使用 web 搜索提供程序。  如果你是搜索提供商，请阅读有关如何确保 Microsoft Edge 支持你的服务的 [详细](../browser-features/search-provider-discovery.md) 信息。  

### 支持 WebKit Api  

为了提高兼容性，Microsoft Edge 支持各种带 `-webkit-` 前缀的 api。  有关受支持的 api 的完整列表 `-webkit-` ，请使用 [API 目录](https://developer.microsoft.com/microsoft-edge/platform/catalog/?page=1&q=webkit)。  

### Web 音频  

Microsoft Edge 引入了对 [W3C Web 音频 API](https://webaudio.github.io/web-audio-api) 规范的支持。  Web 音频是用于在 web 应用程序中处理和 synthesizing 音频的高级别 JavaScript API，可提供丰富的音频和音乐体验。  当 HTML5 `audio` 元素允许进行基本音频流播放时，Web 音频 API 提供了一系列 api，允许你通过紧密同步播放多个声音，并在混合音频上应用增益、淡化、过渡和基本效果。  请阅读有关 [Web 音频] ( 的详细信息。。/multimedia/web-audio.md 在开发人员指南和 [Microsoft Edge 开发人员博客](https://blogs.windows.com/msedgedev/2015/05/19)中。  

### Web 驱动程序  

[W3C WEBDRIVER API](https://w3.org/TR/webdriver)是一个平台和语言中立的界面和线路协议，允许程序或脚本控制 web 浏览器的行为。  WebDriver 使开发人员能够创建模拟用户交互的自动测试。  这与 JavaScript 单元测试不同，因为 WebDriver 有权访问 JavaScript 在浏览器中运行的功能和信息，并且可以更准确地模拟用户事件或操作系统级别的事件。  WebDriver 还可以在单个测试会话中跨多个窗口、选项卡和网页管理测试。  有关如何开始使用 Microsoft Edge 的 WebDriver 的详细信息，请参阅 [WebDriver](../../webdriver.md)。  

## EdgeHTML 12 中的新 Api  

下面是 EdgeHTML 12 中新 Api 的完整列表。  它们以的格式列出 `[interface name].[api name]` 。  

 > [!NOTE] 
 > IE11 中提供了许多这些 Api。  下面的 EdgeHTML 12 的数据是将 EdgeHTML 的初始版本与更高版本的初始版本进行比较的基准。  

<iframe height='580' scrolling='no' title='EdgeHTML 12 中的新 Api' src='//codepen.io/MicrosoftEdgeDocumentation/embed/pPOwby/?height=580&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/pPOwby/'> Microsoft Edge 文档中的 EdgeHTML 12 中的笔新 api </a> (<a href='https://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a>) 在 <a href='https://codepen.io'> CodePen 上 </a> 。</iframe>  
