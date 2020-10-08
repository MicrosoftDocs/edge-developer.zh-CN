---
title: EdgeHTML 17 中的新功能和 Api
description: 本指南概述了 EdgeHTML 17 中包含的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 0fc7dda532866e8970003bce2febb7e46fbbc459
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941943"
---
# EdgeHTML 17 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web 平台中随附的新增和更新功能的列表，作为 [Windows 10 2018 年4月的更新](https://blogs.windows.com/windowsexperience/2018/04/27) \ (04/2018，内部版本 17134 \ ) 。  有关特定 Windows 预览 [体验计划](https://insider.windows.com) 预览版中的更改，请参阅 [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) 。  

## 新增功能和更新功能  

### ARIA 1.1 角色、状态和事件  

EdgeHTML 17 为可访问的富 Internet 应用程序中的各种角色、状态和属性添加支持 [ (wai-aria-aria) 1.1 规范](https://w3.org/TR/wai-aria-1.1)，包括 [源](https://www.w3.org/TR/wai-aria-1.1#feed)、 [表单](https://www.w3.org/TR/wai-aria-1.1#form)、 [ARIA haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup)、 [ARIA 占位符](https://w3.org/TR/wai-aria-1.1#aria-placeholder)等; [在 changelog 中查找 ARIA 更新的完整列表](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。  通过此更新，EdgeHTML 17 现在支持 WAI-ARIA-ARIA 1.1 中定义的所有角色和属性。  有关 Microsoft Edge 中的辅助功能的详细信息，请查看 [辅助功能](../../accessibility.md) 文档。  

### CSS 蒙版  

EdgeHTML 17 包含对 [CSS 掩蔽](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)的实验性支持。  部分实现引入了 CSS [掩码-图像](https://developer.mozilla.org/docs/Web/CSS/mask-image) 和 [掩码大小](https://developer.mozilla.org/docs/Web/CSS/mask-size) 属性。  检查 "启用 CSS 掩蔽" 标志：要试验的标志！  

### SVG 元素上的 CSS 转换  

EdgeHTML 17 现在支持 SVG 元素和演示属性上的 CSS 转换。  这使 SVG 元素能够以可视方式进行操作，包括旋转、缩放、移动、倾斜或平移。  

### Extensions  

Microsoft Edge 现在支持显示来自扩展的通知的 [通知 API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) 。  现在，扩展开发人员可以创建不同类型的通知 \ (基本、列表、图像等 \ ) 支持完全用户交互的。  通知也会自动登录到操作中心。  请访问 [通知示例](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) ，了解如何在扩展中使用此 API。  

EdgeHTML 17 现在还支持 `Tabs.reload()` 作为标准选项卡 API 类的一部分的方法。  在 Windows 10 2018 年4月更新中也是新增的，用户现在可以选择允许扩展在 inPrivate 浏览期间运行。  

有关此版本中的扩展更新的更多详细信息，请转到博客文章 [2018 年4月更新的 Windows 10 年4月扩展的新增功能](https://blogs.windows.com/msedgedev/2018/05/24)。  

### DevTools  

此版本的 DevTools 随附两种方式：作为传统的 in 浏览器 (`F12` \ ) Microsoft Edge 的工具，以及从 Microsoft Store 中预览为独立的 [Windows 10 应用](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) ！  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools 应用" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   Microsoft Edge DevTools 应用  
:::image-end:::  

这些工具还更新了许多主要功能，包括对 [远程调试](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \ (的基本支持，包括通过新的 [DevTools 协议](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\ ) 、 [PWA 调试功能](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)、 [IndexedDB 缓存管理](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)、 [垂直停靠](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) 等！ 我们还继续在性能和可靠性方面作为日常投资的一部分，开始上次发布的整体 [重构工作](./edgehtml-16.md) 。  

有关详细信息，请访问 [最新 Windows 10 更新 (EdgeHTML 17) 中的 DevTools ](../../devtools-guide/whats-new/edgehtml-17.md) 。  

### JavaScript  

有了 EdgeHTML 17，Chakra JavaScript 引擎带来了许多关键领域的性能改进：  

:::row:::
   :::column span="1":::
      **更简洁内存占用**  
   :::column-end:::
   :::column span="2":::
      *   \ (重新 ) 对[对象文本](https://github.com/Microsoft/ChakraCore/pull/4136)的[箭头函数](https://github.com/Microsoft/ChakraCore/pull/4105)和方法的延迟分析  
      *   [RegExp 字节码重构](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **更快的 JavaScript 内置**
   :::column-end:::
   :::column span="2":::
      *   [为对象键入共享。创建](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [对象的多态内联缓存。 assign](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [JSON. parse/stringify 优化](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [在 JavaScript 中重写数组迭代器，更快地为 .。。多种](https://github.com/Microsoft/ChakraCore/pull/4095)  
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

查看有关所有详细信息，请参阅 [EdgeHTML 17 中的增强 JavaScript 和 WebAssembly 性能](https://blogs.windows.com/msedgedev/2018/06/19) 。  

### 媒体元素

EdgeHTML 17 包括对 [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 的更新，包括：  

*   `preload`元素上的新属性 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 指示应预加载的数据。
*   添加 [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) 方法和 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) 属性使开发人员可以选择音频输出设备。  
    
    > [!NOTE]
    > 此功能在 RTC 中尚不可用。  
    
### 媒体捕获 API  

Microsoft Edge 现在通过 [媒体捕获 API](https://w3c.github.io/mediacapture-screen-share)在 RTC 中支持屏幕捕获。  此功能允许网页捕获用户的显示设备的输出，通常用于广播桌面，用于插件免费的虚拟会议或演示文稿。  

### 渐进式 Web 应用  

从 EdgeHTML 17 开始，"服务工作人员" 和 "推送通知" 默认情况下处于启用状态 \ (在博客文章服务工作人员中了解有关这些功能的详细信息：在) [之外转到页面](https://blogs.windows.com/msedgedev/2017/12/19) 。  这将完成一套技术 (，包括获取网络和推送和缓存 Api \ ) ，用于在 Windows 10 上为累进 Web Apps (PWAs \ ) 布局技术基础。  

PWAs 是一种 web 应用，可在支持平台和浏览器引擎（如安装/主屏幕启动、脱机支持和推送通知）的情况下 [逐渐增强](https://en.wikipedia.org/wiki/Progressive_enhancement) 。  在使用 Microsoft Edge \ (EdgeHTML \ ) 引擎的 Windows 10 上，PWAs 将独立于浏览器窗口运行的额外优势视为 [通用 Windows 平台](/windows/uwp/get-started/whats-a-uwp) 应用。  

除了 PWAs，服务工作者和缓存 API 使开发人员能够从缓存中截获网络请求和响应。  网站甚至不需要是完整的 web 应用，即可利用服务工作人员缓存实现 tined 页面加载性能和可靠性，以及在没有 internet 或质量连接期间提供脱机体验的功能。  

转到我们 [的 windows 文档上的渐进式 Web 应用](../../progressive-web-apps-edgehtml/index.md) ，了解有关服务工作者的更多信息以及有关 Windows 10 上的 PWAs 的详细信息。  

### Web 安全  

EdgeHTML 17 引入了对子资源完整性 \ (斯里兰卡的支持 \ ) 。  [子资源完整性](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 是一种安全功能，允许浏览器验证提取的资源 \ (（如图像、脚本、字体等）是否在未进行意外操作的情况下传递 ) 。  

添加一个 `integrity` 属性，其中包含你希望在网页上加载的资源的加密哈希表示形式 `<script>` `<link>` ，如下面的示例所示。  然后，Microsoft Edge 会将所请求的资源与属性中定义的哈希进行比较 `integrity` 。  如果它们不匹配，Microsoft Edge 将不会执行资源，并向网络返回一个错误。  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

另外，EdgeHTML 17 中的新增功能是不 [安全的请求](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) 请求标头，允许浏览器请求安全浏览体验。  此标题指示服务器浏览器支持升级任何不安全的请求，并且用户应被重定向到网站的安全版本（如果可用）。  

### 可变字体
对可变字体的完全支持 \ (包括 CSS [字体、变体设置](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) 和 [字体光大小](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\ ) 在 EdgeHTML 17 中可用。  利用可变字体，开发人员可以通过调整各种坐标轴来实现外观不同的字体外观，从而减少对多个字体文件和 bettering 性能的需求。  

加入我们的 [expedition，了解哪些可变字体提供 web 开发人员和设计器](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)，以及如何在您的网站上使用它们。  在博客文章中阅读有关可变字体的详细信息， [使具有可变字体的 Microsoft Edge 具有富于表现力和性能的版式](https://blogs.windows.com/msedgedev/2018/03/13)。  

<iframe height='456' scrolling='no' title='可变 Tides 票证示例' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> CodePen 上的 MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev </a>) 中的 <a href='https://codepen.io'> 笔变量 Tides 票证示例 </a> 。</iframe>  

## EdgeHTML 17 中的新 Api  

下面是 EdgeHTML 17 中新 Api 的完整列表。  它们以的格式列出 `[interface name].[api name]` 。  

> [!NOTE] 
> 虽然在 DOM 中公开以下 Api，但某些 Api 的端到端行为可能仍在开发中。  请参阅  [Microsoft Edge 平台状态](https://developer.microsoft.com/microsoft-edge/platform/status) ，了解有关功能支持的官方 word 功能。  

<iframe height='580' scrolling='no' title='EdgeHTML 17 中的新 Api' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> EdgeHTML 17 MSEdgeDev (中的笔新 api，请参阅 </a> <a href='https://codepen.io/MSEdgeDev'> CodePen 上的 @MSEdgeDev </a>) <a href='https://codepen.io'> </a> 。</iframe>  

> [!TIP]
> 我们已与其他浏览器和 web 社区 [合作](https://blogs.windows.com/msedgedev/2017/10/18) ，采用 [MDN web 文档](https://developer.mozilla.org) 作为针对当前和新兴的基于标准的 web 技术的有用、无偏差、不限浏览器的文档。  你可以直接在 [MDN web 引用库](https://developer.mozilla.org/docs/Web)的每个页面中找到有关 EdgeHTML API 支持的详细信息。  有关 Microsoft Edge 中支持的最新功能，请访问 Microsoft Edge 的 [平台状态](https://developer.microsoft.com/microsoft-edge/status) 。  

## 以前的 EdgeHTML 版本  

[EdgeHTML 13/Windows 内部版本 10586 (11/2015) ](https://aka.ms/devguide_edgehtml_13)  

[EdgeHTML 14/Windows 内部版本 14393 (8/2016) ](https://aka.ms/devguide_edgehtml_14)  

[EdgeHTML 15/Windows 内部版本 15063 (4/2017) ](https://aka.ms/devguide_edgehtml_15)  

[EdgeHTML 16/Windows 内部版本 16299 (10/2017) ](https://aka.ms/devguide_edgehtml_16)  
