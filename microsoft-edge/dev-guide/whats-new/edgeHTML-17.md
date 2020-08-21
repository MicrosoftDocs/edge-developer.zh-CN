---
title: EdgeHTML 17 中的新功能和 API
description: 本指南概述了 EdgeHTML 17 中包括的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 0fc7dda532866e8970003bce2febb7e46fbbc459
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941943"
---
# EdgeHTML 17 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) Web 平台中随之外出现的新功能和更新功能列表，作为 [Windows 10 2018 年 4 月更新](https://blogs.windows.com/windowsexperience/2018/04/27) \ (04/2018（内部版本 17134\) 的一部分）。  有关特定 [Windows Insider](https://insider.windows.com) Preview 版本中的更改，请参阅 [Microsoft Edge 更改日](https://developer.microsoft.com/microsoft-edge/platform/changelog) 志 [和 EdgeHTML 中的新增功能](../whats-new.md)。  

下面是下列更改列表的句号 [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) ：。  

## 新增功能和更新功能  

### ARIA 1.1 角色、州和活动  

Microsoft EdgeHTML 17 增加了对可访问富 Internet 应用程序中各种角色[、状态和属性的支持 (WAI-ARIA) 1.1 规](https://w3.org/TR/wai-aria-1.1)范，包括[订阅源](https://www.w3.org/TR/wai-aria-1.1#feed)、[form](https://www.w3.org/TR/wai-aria-1.1#form)表单[aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup)、名单里网页[、aria-占位符](https://w3.org/TR/wai-aria-1.1#aria-placeholder)等;在[更改日程中查找 ARIA 更新的完整列表](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。  通过此更新，EdgeHTML 17 现在支持在 WAI-ARIA 1.1 中定义的所有角色和属性。  查看有关 Microsoft [Edge 辅](../../accessibility.md) 助功能的详细信息，请参阅辅助功能文档。  

### CSS 掩码  

EdgeHTML 17 包含对 [CSS 发表的实际支持](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。  部分实现引入了 CSS [mask 图像](https://developer.mozilla.org/docs/Web/CSS/mask-image)[和屏码大小](https://developer.mozilla.org/docs/Web/CSS/mask-size)属性。  请选中有关：标志的：标志的"启用 CSS 掩码"标志以试用！  

### SVG 元素上的 CSS 转换  

Microsoft EdgeHTML 17 现在支持 SVG 元素和演示属性上的 CSS 转换。  这允许以视觉方式操作 SVG 元素，包括旋转、缩放、移动、换行或翻译。  

### Extensions  

Microsoft Edge 现在支持 [通知 API，](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) 该 API 显示扩展中的通知。  扩展开发人员现在可以创建不同类型的通知 \ (基本、列表、图像等（支持 ) 完整用户交互）。  这些通知还会自动登录到操作中心。  访问关 [于如何在](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) 扩展中使用此 API 的通知示例。  

EdgeHTML 17 现在还支持作为 `Tabs.reload()` 标准选项卡 API 类的一部分的方法。  此外，Windows 10 2018 年 4 月更新中新的版订阅现在用户可以选择允许扩展在 inPrivate 浏览过程中运行。  

有关此版本中的扩展更新的更多详细信息，请转到 [Windows 10 2018 年 4](https://blogs.windows.com/msedgedev/2018/05/24)月更新中的博客文章新功能。  

### DevTools  

这个版本的 DevTools 以两种方式交付：作为 Microsoft Edge 的传统浏览器 \ (`F12` \) 工具，然后作为 Microsoft Store 中的随 [机 Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) 应用进行预览！  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge 开发工具应用" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   Microsoft Edge 开发工具应用  
:::image-end:::  

该工具也会使用许多主要功能进行了更新，其中[包括通过新的](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) [DevTools 协](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)议 \) 、PWA 调试功能[、IndexedDB 缓存管理](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)、垂直[PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)停运来管理等[对远](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge)程调试 \ (的基本支持！ 我们还在持续的性能 [和](./edgehtml-16.md) 可靠性的同时，我们还将延续整体重构工作。我们还在持续改进性能和可靠性方面继续了整体重身协作。  

有关详细信息，[请访问最新 Windows 10 更新 (的 Windows 10 开发工具) 中的 DevTools。](../../devtools-guide/whats-new/edgehtml-17.md)  

### JavaScript  

借助 Microsoft EdgeHTML 17，Chakra JavaScript 引文在许多关键方面引入了性能改进：  

:::row:::
   :::column span="1":::
      **更简单的内存量足**  
   :::column-end:::
   :::column span="2":::
      *   \ (Re-\) ，针对对象[文本上箭头函数](https://github.com/Microsoft/ChakraCore/pull/4105)[和方法进行延迟分析](https://github.com/Microsoft/ChakraCore/pull/4136)  
      *   [RegExp 字节码重造](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **速度更快的 JavaScript**
   :::column-end:::
   :::column span="2":::
      *   [类型共享对象.create](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [Object.assign 的 Polymorphic 以嵌入式缓存](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [JSON.parse/stringify 优化](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [在 JavaScript 中重写数组接标，更快...的](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Web 组编程**
   :::column-end:::
   :::column span="2":::
      *   [Inling 支持](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

查看改 [进的 JavaScript 和 EdgeHTML 17 中改进的 JavaScript 和 WebAssembly 性能](https://blogs.windows.com/msedgedev/2018/06/19) ，了解所有详细信息。  

### 媒体元素

Microsoft EdgeHTML 17 包括 [对 HTMLMediaElement 的更新，](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 包括：  

*   元素 `preload` 上的新 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 属性指示应该预加载哪些数据。
*   添加方法和属性 [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) 将 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) 允许开发人员选择音频输出设备。  
    
    > [!NOTE]
    > 尚未在 RTC 中提供。  
    
### 媒体捕获 API  

Microsoft Edge 现在通过媒体捕获 API 支持 RTC [的屏幕截图屏幕截图](https://w3c.github.io/mediacapture-screen-share)。  此功能允许网页捕获用户的显示设备输出，通常用于针对无触传的虚拟会议或演示广播桌面。  

### 渐进式 Web 应用  

从 EdgeHTML 17 开始，默认启用服务工作者和推送通知，模板将默认启用 \ (了解有关博客文章服务工作者中的以下功能 [的更多信息：除了页面](https://blogs.windows.com/msedgedev/2017/12/19)) 。  这将完成一套技术 \ (，包括获取网络以及 Push 和 Cache API\) （它依循 Windows 10 上的渐进式 Web 应用 \ (PWA\) ）进行技术基付。  

PWA 是仅通过支持平台和浏览器[progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement)引引器上的本机应用（如安装/主屏幕启动、脱机支持和推送通知）上的本机应用功能进行逐步增进的 Web 应用。  在带有 Microsoft Edge \ (EdgeHTML\) 引荐的 Windows 10 上，PWA 享受以通用 Windows 平台应用单独运行浏览器窗口 [的优](/windows/uwp/get-started/whats-a-uwp) 势。  

除 PWA、服务工作者和缓存 API 外，开发人员还可以从缓存中捕获网络请求和从缓存中进行响应。  网站甚至不需要充分利用服务 Worker 缓存进行细化页面加载性能和可靠性，网站在没有 Internet 连接或质量较差的连接期内提供脱机体验的能力。  

访问 Windows 上的渐进 [式 Web 应用，](../../progressive-web-apps-edgehtml/index.md) 了解有关在 Windows 10 中服务工作者和有关 PWA 的详细信息。  

### Web 安全性  

EdgeHTML 17 引入了对子资源完整性 \ (SRI\) 。  [子资源完整性是](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 一项安全功能，允许浏览器验证是否提供了资源 \ (如图像、脚本、字体等\) ，但不预期的操作。  

添加一种包含预期将在网页上加载到或元素的资源 `integrity` 加密哈代表示的 `<script>` `<link>` 属性，如下例所示。  然后，Microsoft Edge 会将请求的资源与该属性中定义的 `integrity` 哈值进行比较。  如果它们不匹配，Microsoft Edge 将不执行该资源，并向网络返回错误。  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

同样在 EdgeHTML 17 中加新增功能， [使用升级-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) 请求标头请求笔记本请求安全浏览体验。  此头注重指示浏览器支持升级任何不安全的请求，应将用户重定向到安全版本的网站（如果可用）。  

### 可变字体
对可变字体的完整支持 \ (包括 CSS [字体变体设置](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) 和 [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) 在 EdgeHTML 17 中可用。  可变字体使开发人员能够通过调整各种语言来实现通过单个字体看起来有所不同字样的外观 - 减少了对多个字体文件的需求并更好地实现性能。  

通过将 [可变字体与我们进行合作，了解哪些](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)字体为 Web 开发人员和设计者提供，以及如何在您的网站上使用这些变量。  阅读有关博客文章中的变量字体的详细信息，将明确 [的版](https://blogs.windows.com/msedgedev/2018/03/13)式呈现给 Microsoft Edge 使用变量字体。  

<iframe height='456' scrolling='no' title='变量 Tides 票面示例' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> MSEdgeDev 在 CodePen 上按 </a> MSEdgeDev 设置 <a href='https://codepen.io/MSEdgeDev'> 的 </a> (@MSEdgeDev) <a href='https://codepen.io'> 笔描述信息 </a> 。</iframe>  

## EdgeHTML 17 中的新 API  

下面是 EdgeHTML 17 中的新 API 的完整列表。  它们以格式列出 `[interface name].[api name]` 。  

> [!NOTE] 
> 尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍在开发中。  若要了解  [功能支持的正](https://developer.microsoft.com/microsoft-edge/platform/status) 式字词，请参考 Microsoft Edge 平台状态。  

<iframe height='580' scrolling='no' title='EdgeHTML 17 中的新 API' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>在 <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> CodePen 上查看 </a> MicrosoftEdgeDev 代码的 MsEdgeDev 函数 <a href='https://codepen.io/MSEdgeDev'> </a> (@MSEdgeDev) <a href='https://codepen.io'> 笔新 </a> API。</iframe>  

> [!TIP]
> 我们已 [与](https://blogs.windows.com/msedgedev/2017/10/18) 其他浏览器和 Web 社区合作，是关于当前和新兴基于 [标准](https://developer.mozilla.org) 的 Web 技术的有用不当安全的、不依自浏览器的常用文档。  可以在 MDN Web 参考库的每个页面中直接找到有关 [EdgeHTML API 支持的详细信息](https://developer.mozilla.org/docs/Web)。  访问 Microsoft Edge 中支持 [的最新](https://developer.microsoft.com/microsoft-edge/status) 功能的 Microsoft Edge 平台状态。  

## 以前的 EdgeHTML 版本  

[EdgeHTML 13 / Windows 版本 10586 (11/2015 版) ](https://aka.ms/devguide_edgehtml_13)  

[EdgeHTML 14/Windows 内部版本 14393 (，8) ](https://aka.ms/devguide_edgehtml_14)  

[EdgeHTML 15 /Windows 内部版本 15063 (4/2017) ](https://aka.ms/devguide_edgehtml_15)  

[EdgeHTML 16 /Windows 版本 16299 (10/2017 年 10 月 10 日) ](https://aka.ms/devguide_edgehtml_16)  
