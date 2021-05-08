---
description: 所有关于服务工作者改进和如何使用每个改进。
title: 服务工作者改进
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 服务工作者， PWA
ms.openlocfilehash: 2f32155d1d28d1e65ad29abfe58a414f3e3c6ed7
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387279"
---
# <a name="service-worker-improvements"></a>服务工作者改进  

本文将指导你改进开发人员工具，以使用服务工作者，以及[][MdnServiceWorkerApi]通过每个服务工作者的网络请求。  服务**工作线程改进**在**网络**、**应用程序和****源工具中**。  改进简化了以下任务。  

*   根据服务工作者日程表进行调试。  
    *   请求开示和启动持续时间。  
    *   更新到服务工作者注册。  
    *   使用提取事件处理程序 [的请求的][MdnFetchEvent] 运行时。  
    *   用于加载客户端的所有提取事件的运行时。  
*   了解提取事件处理程序、安装事件处理程序和激活事件处理程序的运行时详细信息。  
*   使用页面脚本信息进入和退出提取 [事件处理程序](#sources)。  
    
这些体验跨越三个不同的开发人员工具。  

1.  网络 [工具](#network) 。  选择一个通过服务工作器运行的网络请求，并访问 **计时** 工具中服务工作器的相应时间线。  
1.  应用程序 [工具](#application) 。  若要调试服务工作者，请导航到" **服务工作者"** 工具。  
1.  源 [工具](#sources) 。  单步执行提取事件处理程序时访问页面脚本信息。  
    
## <a name="network"></a>网络  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="网络工具中的服务工作线程时间线" lightbox="../media/sw-network-timeline.msft.png":::
   网络视图  
:::image-end:::  

若要访问网络工具中的服务工作者 **调试功能，** 请完成以下操作之一。  

*   在"网络" **工具中直接访问** 。  
*   在应用程序 **工具中** 启动。  
    
### <a name="request-routing"></a>请求传送  

为了便于可视化请求传送，日程表现在显示服务工作者的启动和 `respondWith` 提取事件。  若要调试并可视化通过服务工作线程传递的网络请求，请完成以下操作。  

1.  选择通过服务工作者发送的网络请求。  
1.  打开 **计时** 工具。  
    
### <a name="fetch-events"></a>Fetch 事件  

若要了解有关 `respondWith` 提取事件更多信息，请选择 左侧的下拉箭头 `respondWith` 。  若要查找有关原始请求 **和** 收到的 **响应**的更多详细信息，请使用相应的下拉箭头。  

## <a name="application"></a>应用程序  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="应用程序视图" lightbox="../media/sw-application-timeline.msft.png":::
   应用程序视图  
:::image-end:::  

### <a name="service-worker-update-timeline"></a>服务工作者更新时间线  

Microsoft Edge DevTools 团队在应用程序工具**** 中添加了时间线，以反映服务工作者的更新生命周期。  它显示安装和激活事件。  每个事件都有相应的下拉箭头，可为您提供更多详细信息。  

### <a name="request-routing-and-fetch-events"></a>请求传送和提取事件  

现在，可以通过控制台箱中的 **"** 网络"工具访问服务工作者日程表。  该功能有利于性能、最大程度地减少 UI 重复，并创建更全面的调试体验。  

1.  打开正在调试的服务工作线程。  
1.  选择 **"网络** "按钮以打开 [请求路由体验](#network)。  
1.  使用 **respondWith** 下拉列表获取事件请求和响应信息。  

**"网络**"工具显示通过正在调试的服务工作者发送的网络请求。  自动筛选器是缩小探索范围的方法。

## <a name="sources"></a>源  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM 视图" lightbox="../media/sw-sources.msft.png":::
   DOM 视图  
:::image-end:::  

若要查找更多堆栈信息，在提取处理程序中设置一个断点。  详细信息将导致在页面脚本中请求资源。  当调试器在提取处理程序内暂停时，合并的堆栈信息将显示在面板右侧。  之后，你可以四处移动堆栈框架。  

### <a name="future-work"></a>未来工作  

Microsoft Edge DevTools 团队计划进一步开发缓存详细信息，并调查更多方法为渐进式 Web 应用程序开发人员改进服务工作 [器调试][MdnProgressiveWebApps] 体验。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps "渐进式 Web (PA) |MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作线程 API |MDN"  
