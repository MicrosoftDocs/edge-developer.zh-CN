---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: 本指南概述了 EdgeHTML 16 中的新功能和 API。
title: EdgeHTML 16 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7697114546153555d947903eda6bf8477cca3516
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232363"
---
# EdgeHTML 16 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web 平台中新增和更新的功能列表，作为 [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \ (10/2017 内部版本 16299\) 的一部分。  有关特定 Windows Insider Preview 内部版本的变化，请参阅 [Microsoft Edge 更改日志](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md)  

## 新增和更新的功能  

### CSS 网格布局  

Microsoft Edge 现在支持 CSS 网格布局的无 [前缀实现](https://www.w3.org/TR/css-grid-1)。  [网格布局](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 定义基于网格的二维布局系统，与使用浮点或脚本进行定位时所允许的布局流畅性要高。  下面的示例使用 CSS 网格布局为基本网页创建结构。  

<iframe height='303' scrolling='no' title='CSS 网格布局' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> CSS Grid Layout by </a> MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) on </a> <a href='https://codepen.io'> </a> CodePen.</iframe>  

### CSS 对象调整和对象位置  

EdgeHTML 16 引入了对 CSS 属性和 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) 的支持 [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 。  这些属性控制替换内容在内容框中的位置和大小。  

### 开发人员工具  

此版本我们启动了一项重要的 Microsoft Edge DevTools 重构工作，以提高稳定性和性能，并添加了一些新功能，你可以立即在 Windows 预览体验成员版本 [上开始使用](https://insider.windows.com) 。  查看 [Microsoft Edge DevTools 指南](../whats-new.md) ，详细了解更改了哪些功能！  

### JavaScript  

[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31)通过扩展 Chakra 引擎延迟/重新延迟函数、使用多态内嵌缓存以及使用块优化函数的功能，在以前版本 Javascript 性能优化的基础上构建。 `try` / `finally`  

此外，EdgeHTML 15 中首次预览的功能现在稳定且默认启用：  

#### 新功能  

默认启用  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \ ([demo](https://webassembly.org/demo)\)   
*   [共享内存和原子](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### 付款请求 API  

付款请求 [API](../windows-integration/payment-request-api.md) 是一个开放的跨浏览器标准，使浏览器能够充当商家、消费者和付款方式 \ (（如客户存储在云中的信用卡\) ）之间的中介。  EdgeHTML 16 中的 API 已更新，以匹配最新的 W3C [付款请求 API](https://w3c.github.io/payment-request) 规范。  这包括：  

*   对方法 `canMakePayment()` 的支持  
*   对属性 `requestId` 的支持  
*   对属性 `id` 的支持  
*   方法参数的默认值 `complete()` 从 `result` ""更改为"未知"  

### 服务工作者  

[服务工作人员](https://www.w3.org/TR/service-workers-1) 是事件驱动的脚本，在网页后台运行。  服务工作人员启用以前仅适用于本机应用的功能，例如截获和处理来自网络的请求、管理和处理后台同步、本地存储和推送通知。  对服务工作者的支持仍处于开发阶段，但您可以通过在 中启用服务工作者功能，在 Microsoft Edge 中通过实验性服务工作者支持测试 `about:flags` PWA。  

### WebVR  

Microsoft Edge 的 WebVR 增加了对运动 [控制器的支持](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。  这些控制器在空间中具有精确位置，允许与虚拟现实中的数字对象进行精细交互。  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="运动控制器" lightbox="../media/MotionControllers.jpg":::
   运动控制器  
:::image-end:::  

WebVR 也进行了优化，以支持两种不同类型的体验。  

**Windows Mixed Reality 电脑** - 带集成图形的台式机和笔记本电脑。  当插入这些设备时，我们的沉浸式耳机将以 60 帧/秒的速度运行。  
**Windows Mixed Reality 超电脑** - 具有离散图形的台式机和笔记本电脑。  当插入这些设备时，我们的沉浸式耳机将以 90 帧/秒的速度运行。  

这两种设置将支持相同的沉浸式视频和游戏体验。  

有关即将推出的 Windows Mixed Reality 更新的信息，请查看 [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) 假日更新博客文章。  

有关指南和演示，请前往 [WebVR 开发人员指南](/microsoft-edge/webvr)。  

 > [!NOTE] 
 > 由于 WebVR 规范仍处于开发阶段，因此 Microsoft Edge 的实现可能会稍后发生变化。  

## EdgeHTML 16 中的新 API  

下面是 EdgeHTML 16 中新 API 的完整列表。  它们以 . `[interface name].[api name]`

> [!NOTE] 
> 尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍处于开发阶段。  有关  [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status) 词语，请参阅 Microsoft Edge 平台状态。  

---  

<iframe height='559' scrolling='no' title='EdgeHTML 16 中的新 API' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'>See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> New API in EdgeHTML 16 </a> by MSEdgeDev (@MSEdgeDev <a href='https://codepen.io/MSEdgeDev'>) on </a> <a href='https://codepen.io'> </a> CodePen.</iframe>  

---  

## 以前的 EdgeHTML 版本  

[EdgeHTML 12 /Windows 版本 10240 (2015 年 7 月 7 日) ](./edgehtml-12.md)  

[EdgeHTML 13 /Windows 版本 10586 (2015 年 11 月 11 日) ](./edgehtml-13.md)  

[EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) ](./edgehtml-14.md)  

[EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) ](./edgehtml-15.md)  
