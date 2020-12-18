---
title: EdgeHTML 17 中的新功能和 API
description: 本指南概述了 EdgeHTML 17 中包含的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 75429528fd814963a8c78e27f85564223fb2d3c8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232169"
---
# EdgeHTML 17 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) Web 平台中新增和更新的功能列表，作为 [Windows 10 2018](https://blogs.windows.com/windowsexperience/2018/04/27) 年 4 月更新 \ (04/2018 内部版本 17134\) 的一部分。  有关特定 [Windows Insider](https://insider.windows.com) Preview 内部版本的变化，请参阅 Microsoft [Edge 更改日志](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md)  

## 新增和更新的功能  

### ARIA 1.1 角色、状态和事件  

EdgeHTML 17 增加了对可访问的富 Internet 应用程序[ (一) .1](https://w3.org/TR/wai-aria-1.1)规范中各种角色、状态和属性的支持，包括源、表单[、aria-haspopup、aria](https://w3.org/TR/wai-aria-1.1#aria-haspopup)[](https://www.w3.org/TR/wai-aria-1.1#feed)[占位符](https://w3.org/TR/wai-aria-1.1#aria-placeholder)等; [](https://www.w3.org/TR/wai-aria-1.1#form)在[更改日志中查找 ARIA 更新的完整列表](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。  通过此更新，EdgeHTML 17 现在支持在一个功能区 1.1 中定义的所有角色和属性。  <!--  Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.  -->  

### CSS 屏蔽  

EdgeHTML 17 包括对 [CSS 屏蔽的实验性支持](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。  部分实现引入了 CSS[掩码图像和](https://developer.mozilla.org/docs/Web/CSS/mask-image)[掩码大小](https://developer.mozilla.org/docs/Web/CSS/mask-size)属性。  检查 about：flags 中的"启用 CSS 屏蔽"标志以进行试验！  

### SVG 元素上的 CSS 转换  

EdgeHTML 17 现在支持对 SVG 元素和演示文稿属性进行 CSS 转换。  这使 SVG 元素可以直观地操作，包括旋转、缩放、移动、扭曲或转换。  

### Extensions  

Microsoft Edge 现在支持显示来自扩展的通知[的通知 API。](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications)  扩展开发人员现在可以创建不同类型的通知\ (基本、列表、图像等\) 支持完全用户交互。  通知还会自动登录到操作中心。  访问 [有关如何在](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) 扩展中使用此 API 的通知示例。  

EdgeHTML 17 现在还支持将该方法作为标准选项卡 `Tabs.reload()` API 类的一部分。  同样是 Windows 10 2018 年 4 月更新中的新增功能，用户现在可以选择允许在 inPrivate 浏览期间运行扩展。  

有关此版本中的扩展更新的更多详细信息，请前往博客文章 [2018](https://blogs.windows.com/msedgedev/2018/05/24)年 4 月 10 日更新中扩展的新功能。  

### 开发工具  

此版本的 DevTools 以两种方式提供：作为 Microsoft Edge 的传统浏览器内 \ (\) 工具，以及从 Microsoft Store 预览为独立 `F12` [Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) 应用！  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools 应用" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   Microsoft Edge DevTools 应用  
:::image-end:::  

这些工具还更新了一些主要功能，包括通过我们新的[](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) [DevTools 协议](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\ (、PWA 调试功能[](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)[、IndexedDB](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)缓存管理、[](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)垂直停靠等对远程调试 \)  (的基本支持！ 作为对性能和可靠性的持续[](./edgehtml-16.md)投资一部分，我们还继续进行上一版本开始的整体重构工作。  

有关详细信息[，请访问 EdgeHTML 17 (Windows 10) 中的 DevTools。](../../devtools-guide/whats-new/edgehtml-17.md)  

### JavaScript  

借助 EdgeHTML 17，Chakra JavaScript 引擎在一些关键方面引入了性能改进：  

:::row:::
   :::column span="1":::
      **更精简的内存占用**  
   :::column-end:::
   :::column span="2":::
      *   \ (对象) 的 [箭头](https://github.com/Microsoft/ChakraCore/pull/4105) 函数和方法的 Re-\) [延迟分析](https://github.com/Microsoft/ChakraCore/pull/4136)  
      *   [RegExp 字节码重构](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **更快的 JavaScript 内置**
   :::column-end:::
   :::column span="2":::
      *   [Object.create 的类型共享](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [Object.assign 的多态内嵌缓存](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [JSON.parse/stringify 优化](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [在 JavaScript 中重写数组 Iterator，并更快...of](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Web 程序集**
   :::column-end:::
   :::column span="2":::
      *   [Inling 支持](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

查看 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) 中改进的 JavaScript 和 WebAssembly 性能，了解所有详细信息。  

### 媒体元素

EdgeHTML 17 包括 [HTMLMediaElement 更新](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) ，其中包括：  

*   元素 `preload` 上的新 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 属性指示应预加载哪些数据。
*   添加方法和 [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) 属性后 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) ，开发人员可以选择音频输出设备。  
    
    > [!NOTE]
    > 这尚未在 RTC 中提供。  
    
### 媒体捕获 API  

Microsoft Edge 现在通过媒体捕获 API 支持 RTC [中的屏幕捕获](https://w3c.github.io/mediacapture-screen-share)。  此功能允许网页捕获用户显示设备的输出，通常用于为无插件虚拟会议或演示文稿广播桌面。  

### 渐进式 Web 应用  

从 EdgeHTML 17 开始，默认情况下启用服务工作者和推送通知 \ (在博客文章 ["](https://blogs.windows.com/msedgedev/2017/12/19) 服务工作者：超出页面范围"中了解有关这些功能) 。  这将完成一套技术 \ (包括提取网络和推送和缓存 API\) ，这些技术为 Windows 10 上的渐进 Web 应用 \ (PWA\) 提供技术基础。  

PWA 只是一些 Web[](https://en.wikipedia.org/wiki/Progressive_enhancement)应用，通过支持平台和浏览器引擎上的本机类似应用功能（如安装/主屏幕启动、脱机支持和推送通知）逐步增强。  在具有 Microsoft Edge \ (EdgeHTML\) 引擎的 Windows 10 上，PWA 享受独立于浏览器窗口作为通用 [Windows 平台应用运行的附加](/windows/uwp/get-started/whats-a-uwp) 优势。  

除了 PWA 之外，服务工作者和缓存 API 还允许开发人员截获网络请求和从缓存进行响应。  网站甚至不需要是一个全面的 Web 应用，以利用服务工作器缓存实现精细的页面加载性能和可靠性，以及能够在没有 Internet 或质量较差的连接期间提供脱机体验。  

前往 Windows 上的 [渐进式 Web 应用](../../progressive-web-apps/index.md) 文档，了解有关服务工作者的详细信息，以及 Windows 10 上的 PWA 的详细信息。  

### Web 安全性  

EdgeHTML 17 引入了对子资源完整性 \ (SRE\) 。  [子资源](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 完整性是一项安全功能，允许浏览器验证提取的资源 \ (如图像、脚本、字体等\) 是否交付，而无需意外操作。  

添加一个属性，其中包含您预期在网页上加载到某个或元素中的资源的加密哈希表示形式， `integrity` `<script>` `<link>` 如以下示例所示。  然后，Microsoft Edge 将请求的资源与属性中定义的哈希 `integrity` 进行比较。  如果不匹配，Microsoft Edge 将不会执行资源，并且会向网络返回错误。  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

也是 EdgeHTML 17 中的新增功能 [，Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) 请求标头允许浏览器请求安全浏览体验。  此标头告知服务器，浏览器支持升级任何不安全的请求，并且用户应重定向到网站的安全版本（如果可用）。  

### 变量字体
EdgeHTML 17 中完全支持变量字体 \ (包括 [CSS](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) 字体变体设置和字体光学 [大小调整](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) 。  变量字体使开发人员通过调整各种轴来实现看起来不同的字样外观，从而通过调整各种轴实现看起来不同的字样，从而减少对多个字体文件以及提高性能的需要。  

加入我们 [，了解](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)哪些变量字体为 Web 开发人员和设计人员提供，以及如何在你的网站上使用它们。  在博客文章阅读有关变量字体的更多内容，使用变量字体为 Microsoft Edge 带来具有表现力、性能高明 [的版式](https://blogs.windows.com/msedgedev/2018/03/13)。  

<iframe height='456' scrolling='no' title='变量变量票证示例' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> MsEdgeDev 在 <a href='https://codepen.io/MSEdgeDev'> CodePen 上 (@MSEdgeDev) </a> 的笔变量变量票证 <a href='https://codepen.io'> 示例 </a> 。</iframe>  

## EdgeHTML 17 中的新 API  

以下是 EdgeHTML 17 中新 API 的完整列表。  它们以 . `[interface name].[api name]`  

> [!NOTE] 
> 尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍处于开发阶段。  有关  [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status) 词语，请参阅 Microsoft Edge 平台状态。  

<iframe height='580' scrolling='no' title='EdgeHTML 17 中的新 API' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> New API in EdgeHTML 17 </a> by MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) </a> on <a href='https://codepen.io'> CodePen </a> .</iframe>  

> [!TIP]
> 我们已与其他浏览器[](https://blogs.windows.com/msedgedev/2017/10/18)和 Web 社区合作，采用[MDN Web 文档](https://developer.mozilla.org)作为针对当前和新出现的基于标准的 Web 技术的有用、无偏不的浏览器不可知文档的最终位置。  可以直接在 MDN Web 引用库的每个页面中找到有关 EdgeHTML API [支持的详细信息](https://developer.mozilla.org/docs/Web)。  访问 Microsoft Edge [的平台状态，](https://developer.microsoft.com/microsoft-edge/status) 了解 Microsoft Edge 中支持的最新功能。  

## 以前的 EdgeHTML 版本  

[EdgeHTML 13 /Windows 版本 10586 (2015 年 11 月 11 日) ](https://aka.ms/devguide_edgehtml_13)  

[EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) ](https://aka.ms/devguide_edgehtml_14)  

[EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) ](https://aka.ms/devguide_edgehtml_15)  

[EdgeHTML 16 /Windows 版本 16299 (2017 年 10 月 10 日) ](https://aka.ms/devguide_edgehtml_16)  
