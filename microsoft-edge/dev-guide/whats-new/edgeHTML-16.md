---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: 本指南概述了 Microsoft Edge 中包含的开发人员功能和标准。
title: EdgeHTML 16 中的新功能和 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: a15888bc8c1314d61d436759e5d63be942174ea4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941938"
---
# EdgeHTML 16 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web 平台中提供的新增和更新功能的列表，作为 [Windows 10 秋季创建者更新](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \ (10/2017，内部版本 16299 \ ) 的一部分。  有关特定 Windows 预览体验计划预览版中的更改，请参阅 [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是以下更改列表的固定链接：  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) 。  

## 新增功能和更新功能  

### CSS 网格布局  

Microsoft Edge 现在支持不带前缀的 [CSS 网格布局](https://www.w3.org/TR/css-grid-1)实现。  [网格布局](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 定义了一个二维基于网格的布局系统，该布局系统支持更多布局流畅性，使用浮动或脚本进行定位。  下面的示例使用 CSS 网格布局创建基本网页的结构。  

<iframe height='303' scrolling='no' title='CSS 网格布局' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> <a href='https://codepen.io/MSEdgeDev'> 在 CodePen 上通过 MSEdgeDev (@MSEdgeDev) 查看笔 CSS 网格布局 </a> <a href='https://codepen.io'> </a> 。</iframe>  

### CSS 对象适合对象和对象位置  

EdgeHTML 16 引入了对 CSS 属性 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) 和的支持 [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 。  这些属性控制替换内容在 "内容" 框中的位置和大小。  

### 开发人员工具  

在此版本中，我们启动了一个主要的 Microsoft Edge DevTools 重构措施来改进可靠性和性能，还添加了一组新功能，您可以在 [Windows 预览体验计划](https://insider.windows.com) 内部版本上开始使用。  有关更改内容的详细信息，请查看 [Microsoft Edge DevTools 指南](../whats-new.md) ！  

### JavaScript  

[EdgeHTML 16 在](https://blogs.windows.com/msedgedev/2017/10/31)早期版本的 Javascript 性能优化的基础上，通过展开 Chakra 引擎能够延迟/重新延迟函数、使用多态内联缓存以及使用块优化函数来优化早期版本 `try` / `finally` 。  

此外，EdgeHTML 15 中首先预览的功能在默认情况下是稳定和启用的：  

#### 新增功能  

默认启用  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP ([演示](https://webassembly.org/demo)\ )   
*   [共享内存和 Atomics](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### 付款请求 API  

[支付请求 API](../windows-integration/payment-request-api.md)是一种开放、跨浏览器的标准，使浏览器能够充当商家、消费者和付款方式的媒介，例如在使用者已存储在云中的信用卡 )  (。  EdgeHTML 16 中的 API 已更新，以匹配最新的 W3C [付款请求 API](https://w3c.github.io/payment-request) 规范。  这包括：  

*   对方法的支持 `canMakePayment()`  
*   对属性的支持 `requestId`  
*   对属性的支持 `id`  
*   该 `complete()` 方法的参数的默认值 `result` 从 "" 更改为 "unknown"  

### 服务工作进程  

[服务工作人员](https://www.w3.org/TR/service-workers-1) 是在网页的后台运行的事件驱动的脚本。  服务工作人员仅支持以前的应用（如拦截和处理来自网络的请求、管理和处理后台同步、本地存储和推送通知），以前仅提供本机应用功能。  服务工作人员的支持仍在开发中，但你可以通过在中启用服务工作人员功能来在 Microsoft Edge 中测试你的 PWA `about:flags` 。  

### WebVR  

Microsoft Edge 的 WebVR 已添加了对 [运动控制器](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)的支持。  这些控制器在空间中具有精确的位置，允许在虚拟现实中与数字对象进行细微的粒度交互。  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="运动控制器" lightbox="../media/MotionControllers.jpg":::
   运动控制器  
:::image-end:::  

WebVR 也已经过优化，可支持两种不同类型的体验。  

**Windows Mixed Reality 电脑** -具有集成图形的台式机和笔记本电脑。  当插入这些设备时，我们的沉浸式耳机将在每秒60帧运行。  
**Windows Mixed Reality 超 pc** -具有独立图形的台式机和笔记本电脑。  当插入这些设备时，我们的沉浸式耳机将在每秒90帧运行。  

这两个设置将支持相同的沉浸式视频和游戏体验。  

有关即将到来的 Windows Mixed Reality 更新的详细信息，请查看 [Windows Mixed reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) 假日更新博客文章。  

有关指南和演示，请转到 [WebVR 开发人员指南](/microsoft-edge/webvr)。  

 > [!NOTE] 
 > 由于 WebVR 规范仍在开发中，Microsoft Edge 的实现可能会在行的后面更改。  

## EdgeHTML 16 中的新 Api  

下面是 EdgeHTML 16 中新 Api 的完整列表。  它们以的格式列出 `[interface name].[api name]` 。

> [!NOTE] 
> 虽然在 DOM 中公开以下 Api，但某些 Api 的端到端行为可能仍在开发中。  请参阅  [Microsoft Edge 平台状态](https://developer.microsoft.com/microsoft-edge/platform/status) ，了解有关功能支持的官方 word 功能。  

---  

<iframe height='559' scrolling='no' title='EdgeHTML 16 中的新 Api' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>在 </a> CodePen 上的 MSEdgeDev (@MSEdgeDev) 中查看 EdgeHTML 16 中的笔新 api <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。</iframe>  

---  

## 以前的 EdgeHTML 版本  

[EdgeHTML 12/Windows 内部版本 10240 (7/2015) ](./edgehtml-12.md)  

[EdgeHTML 13/Windows 内部版本 10586 (11/2015) ](./edgehtml-13.md)  

[EdgeHTML 14/Windows 内部版本 14393 (8/2016) ](./edgehtml-14.md)  

[EdgeHTML 15/Windows 内部版本 15063 (4/2017) ](./edgehtml-15.md)  
