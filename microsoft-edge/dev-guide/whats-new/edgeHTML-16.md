---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: 本指南概述 Microsoft Edge 中包括的开发人员功能和标准。
title: EdgeHTML 16 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: a15888bc8c1314d61d436759e5d63be942174ea4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941938"
---
# EdgeHTML 16 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web 平台中随之外出现的新功能和更新功能的列表， [作为 Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \ (10/2017（内部版本 16299\) 的一部分）。  有关特定 Windows Insider Preview 版本中的更改，请参阅 [Microsoft Edge 更改日](https://developer.microsoft.com/microsoft-edge/platform/changelog) 志 [和 EdgeHTML 中的新增功能](../whats-new.md)。  

下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) ：。  

## 新增功能和更新功能  

### CSS 网格布局  

Microsoft Edge 现在支持对 CSS 网格 [布局的未前缀实现](https://www.w3.org/TR/css-grid-1)。  [网格布局](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 定义了基于二维网格的布局系统，它比使用浮点或脚本进行定位相比，该系统支持更流畅的布局。  以下示例使用 CSS 网格布局为基本网页创建结构。  

<iframe height='303' scrolling='no' title='CSS 网格布局' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> MSEdgeDev 代码库 (@MSEdgeDev) 笔的 Pen CSS </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> 网格布局 </a> 。</iframe>  

### CSS 对象适合和 object-position  

EdgeHTML 16 引入了对 CSS 属性和的 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) 支持 [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 。  这些属性控制替换内容在内容框中的位置和大小。  

### 开发人员工具  

此版本已经为提升的可靠性和性能重构，我们已经为提升的强大功能和性能重构，并添加了一大段新功能，你可以现在开始在 [Windows 预览](https://insider.windows.com) 体验成员版本上使用。  查看 [Microsoft Edge 开发人员指南，了解](../whats-new.md) 发生变化情况的详细信息！  

### JavaScript  

[EdgeHTML 16 基于以](https://blogs.windows.com/msedgedev/2017/10/31)前版本的性能优化的 Javascript 性能优化的基率，方法是扩展 Chakra 引联程序可延期/re-defer 函数、使用多形式缓存，并使用块 `try` / `finally` 优化函数。  

另外，在 EdgeHTML 15 中预览的功能现在更可排序，默认情况下处于启用状态：  

#### 新增功能  

默认启用  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \ ([demo](https://webassembly.org/demo)\)   
*   [共享内存和原子](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### 付款请求 API  

[付款请求 API 是](../windows-integration/payment-request-api.md)一种开放的跨浏览器标准，允许浏览器在商业、使用者和付款方式 \ (如信用卡\) 客户存储在云中，采用的中介。  已更新 EdgeHTML 16 中的 API，以匹配最新的 W3C [付款请求 API](https://w3c.github.io/payment-request) 规范。  这包括：  

*   对方法 `canMakePayment()` 的支持  
*   对属性 `requestId` 的支持  
*   对属性 `id` 的支持  
*   该方法参数的 `complete()` 默认值从"" `result` 更改为"未知"  

### 服务工作进程  

[服务工作者](https://www.w3.org/TR/service-workers-1) 是在网页后台运行的事件驱动的脚本。  服务工作者现在只能通过本机应用使用功能，如从网络中部起状态、管理和处理后台同步、本地存储以及推送通知等本机应用的请求。  服务工作者的支持仍在开发中，但你可以通过在技术服务工作者支持中启用服务工作者功能，在 Microsoft Edge 中通过实验性服务工作者支持测试你的 `about:flags` PWA。  

### WebVR  

适用于 Microsoft Edge 的 WebVR 已添加 [对运动控制器的支持](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。  这些控制器在空间中具有精确的位置，可让你精细交互虚拟现实。  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="运动控制器" lightbox="../media/MotionControllers.jpg":::
   运动控制器  
:::image-end:::  

WebVR 也经过优化，以支持两种不同类型的体验。  

**Windows 混合现实电脑** - 一台包含集成图形的台式机和笔记本电脑。  插入这些设备后，沉送耳机将以 60 帧每秒的速度运行。  
**Windows 混合现实 Ultra 电脑** - 具有自由图形的台式机和笔记本电脑。  插入这些设备后，沉送耳机将以 90 帧每秒的速度运行。  

这两个设置都支持相同的沉静视频和游戏体验。  

有关即将推出的 Windows Mixed Reality 更新的详细信息，请查看 [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) 更新博客文章。  

有关指南和演示，请转到 [WebVR 开发人员指南](/microsoft-edge/webvr)。  

 > [!NOTE] 
 > 由于 WebVR 规范仍在开发中，所以 Microsoft Edge 的实现可能会在以后更改。  

## EdgeHTML 16 中的新 API  

下面是 EdgeHTML 16 中的新 API 的完整列表。  它们以格式列出 `[interface name].[api name]` 。

> [!NOTE] 
> 尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍在开发中。  若要了解  [功能支持的正](https://developer.microsoft.com/microsoft-edge/platform/status) 式字词，请参考 Microsoft Edge 平台状态。  

---  

<iframe height='559' scrolling='no' title='EdgeHTML 16 中的新 API' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>在 <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> CodePen 上查看 </a> MSEdgeDev 中由 MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> </a> (@MSEdgeDev@MSEdgeDev) <a href='https://codepen.io'> 笔新 </a> API。</iframe>  

---  

## 以前的 EdgeHTML 版本  

[EdgeHTML 12 / Windows 内部版本 10240 (7/2015) ](./edgehtml-12.md)  

[EdgeHTML 13 / Windows 版本 10586 (11/2015 版) ](./edgehtml-13.md)  

[EdgeHTML 14/Windows 内部版本 14393 (，8) ](./edgehtml-14.md)  

[EdgeHTML 15 /Windows 内部版本 15063 (4/2017) ](./edgehtml-15.md)  
