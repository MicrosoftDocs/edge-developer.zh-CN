---
description: 所有关于服务工作人员的改进以及如何使用每一个。
title: 服务工作人员改进
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、服务工作人员、PWA
ms.openlocfilehash: 4e1b43235ccd7b108d2aadd1c803aa3276fa1265
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190024"
---
# 服务工作人员改进  

本文介绍对 [服务工作人员][MdnServiceWorkerApi] 的改进，以及传递每个服务工作请求的网络请求。  **服务工作人员改进**位于 "**网络**"、"**应用程序**" 和 "**源**" 工具中。  改进包括以下任务。  

*   基于服务工作时间日程表进行调试。  
    *   请求的开始时间和引导的持续时间。  
    *   更新到服务工作人员注册。  
    *   使用 [fetch 事件][MdnFetchEvent] 处理程序的请求的运行时。  
    *   用于加载客户端的所有获取事件的运行时。  
*   了解提取事件处理程序、安装事件处理程序和激活事件处理程序的运行时详细信息。  
*   通过 [页面脚本信息](#sources)单步执行和退出获取事件处理程序。  

经验涉及三个不同的开发人员工具。  

1.  " [网络](#network) " 工具。  选择通过服务工作人员运行的网络请求，并在 **计时** 工具中访问服务工作人员的相应时间线。  
1.  [应用程序](#application)工具。  若要调试服务工作人员，请导航到 " **服务工作人员** " 工具。  
1.  " [源](#sources) " 工具。  在单步执行提取事件处理程序时访问页面脚本信息。  

## 网络  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="网络工具中的服务工作时间线" lightbox="../media/sw-network-timeline.msft.png":::
   网络视图  
:::image-end:::  

若要访问 **网络** 工具中的服务工作人员调试功能，请完成以下操作之一。  

*   直接在 **网络** 工具中访问。  
*   在 **应用程序** 工具中启动。  
    
### 请求路由  

为了使请求路由更易于可视化，日程表现在显示服务工作人员启动和 `respondWith` 获取事件。  若要调试和可视化通过服务工作人员传递的网络请求，请完成以下操作。  

1.  选择通过服务工作人员进行的网络请求。  
1.  打开 **计时** 工具。  
    
### 获取事件  

若要了解有关提取事件的详细信息 `respondWith` ，请选择左侧的下拉箭头 `respondWith` 。  若要查找有关**已收到**的**原始请求**和响应的更多详细信息，请使用相应的下拉箭头。  

## 应用程序  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="应用程序视图" lightbox="../media/sw-application-timeline.msft.png":::
   应用程序视图  
:::image-end:::  

### 服务工作人员更新日程表  

Microsoft Edge DevTools 团队在 **应用程序** 工具中添加了一个日程表，以反映服务工作人员的更新生命周期。  它显示安装和激活事件。  每个事件都有一个对应的下拉箭头，可提供更多详细信息。  

### 请求路由和提取事件  

您现在可以通过 console 抽屉中的 " **网络** " 工具访问服务工作人员日程表。  该功能可提高性能、最小化 UI 复制，并创建更全面的调试体验。  

1.  打开正在调试的服务工作人员。  
1.  选择 " **网络** " 按钮以打开 " [请求路由体验](#network)"。  
1.  使用 **respondWith** 下拉菜单获取获取事件请求和响应信息。  

**网络**工具显示通过正在调试的服务工作人员进行的网络请求。  自动筛选器是缩小您的勘探范围的一种方法。

## 源  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM 视图" lightbox="../media/sw-sources.msft.png":::
   DOM 视图  
:::image-end:::  

若要查找更多堆栈信息，请在 fetch 处理程序中设置断点。  详细信息将导致在页面脚本中请求资源的位置。  当调试器在提取处理程序中暂停时，将在右侧的面板中显示组合的堆栈信息。  在此之后，你可以在堆栈帧中四处移动。  

### 未来工作  

Microsoft Edge DevTools 团队计划可进一步开发缓存详细信息，并正在研究更多提高 [Web 应用程序][MdnProgressiveWebApps] 开发人员的服务工作人员调试体验的方法。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps " (PWAs) | 的渐进式 web 应用MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
