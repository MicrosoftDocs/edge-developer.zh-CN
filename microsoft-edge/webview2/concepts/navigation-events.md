---
description: 导航
title: 导航
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 0df8e12acb11824006515ac711250d776d276e36
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895553"
---
# 导航事件  

导航事件的正常顺序为、、、 `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` 和 `NavigationCompleted` 。  以下事件描述了每个导航期间 WebView2 的状态。  

| 次序 | 事件名称 | 详细信息 |  
|:--- |:--- |:--- |  
| raid-1 | `NavigationStarting`  |  WebView2 将开始导航，并且导航会导致网络请求。  主机能够在事件期间禁止请求。  |  
| ppls-2 | `SourceChanged`  |  WebView2 的源更改为新的 URL。  此事件可能是由不会导致网络请求（如片段导航）的导航导致的。  |  
| 三维空间 | `HistoryChanged`  |  导航的结果 WebView2 更新的历史记录。  |  
| 第 | `ContentLoading`  |  Web 视图开始为新页面加载内容。  |  
| 级 | `NavigationCompleted`  |  WebView2 完成在新页面上加载内容的工作。  |  

`navigations`使用导航 ID \ （\）跟踪到每个新文档 `NavigationId` 。  `NavigationId`每次成功导航到新文档时，Web 视图的更改。

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 导航事件" lightbox="../media/navigation-graph.png":::
   Microsoft Edge WebView2 导航事件  
:::image-end:::  

> [!NOTE]
> 上图表示具有相应事件参数的相同属性的导航事件 `NavigationId` 。  

 `Navigations` 具有不同事件实例的事件 `NavigationId` 可能会重叠。  例如，当您启动导航时，您必须等待相关 `NavigationStarting` 事件。  如果你随后开始另一个导航，你应该看到 `NavigationStarting` 第一个导航的事件，后跟第 `NavigationStarting` 二个导航的事件，然后是 `NavigationCompleted` 第一个导航的事件，然后是第二个导航的所有其余导航事件。  
 
 在错误情况下，可能会有也可能不是 `ContentLoading` 事件，具体取决于导航是否转到错误页面。  
 
 在 HTTP 重定向的情况下，一行中有多个 `NavigationStarting` 事件，后续事件参数 `IsRedirect` 设置了属性，但是保持不变 `NavigationId` 。  
 
 同一文档 `navigations` （例如导航到片段）不会导致 `NavigationStarting` 事件，也不会增加 `NavigationId` 。  

若要 `navigations` 在 Web 视图中的 subframes 内监视或取消，请使用 `FrameNavigationStarting` 与 `FrameNavigationCompleted` 等效的非帧对应事件相同的事件。  

<!-- links -->  
