---
description: 导航
title: 导航
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: ac15b9f32a29c64bbdc2a7886fa654a2d71a5453
ms.sourcegitcommit: 4cea8cf99b5f12db9d2daba99bbf48f3ccc537fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314795"
---
# 导航事件  

导航事件的正常顺序是 `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` ，，，然后 `NavigationCompleted` 。  以下事件描述每次导航期间 WebView2 的状态。  

| Sequence | 事件名称 | 详细信息 |  
|:--- |:--- |:--- |  
| 1 | `NavigationStarting`  |  WebView2 开始导航，导航导致网络请求。  主机能够在事件期间禁止请求。  |  
| 2 | `SourceChanged`  |  WebView2 的源将更改到新 URL。  该事件可能由不会引起网络请求（如片段导航）的导航导致。  |  
| 3 | `HistoryChanged`  |  由于导航，WebView2 的历史记录会更新。  |  
| 4 | `ContentLoading`  |  WebView2 开始加载新页面的内容。  |  
| 5 | `NavigationCompleted`  |  WebView2 将完成新页面上的内容加载。  |  

使用 `navigations` 导航 ID \ (`NavigationId` \) 跟踪每个新文档。  每次 `NavigationId` 成功导航到新文档时，WebView 都会更改。

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 导航事件" lightbox="../media/navigation-graph.png":::
   Microsoft Edge WebView2 导航事件  
:::image-end:::  

> [!NOTE]
> 上图表示在各自的事件参数上具有相同的属性 `NavigationId` 的导航事件。  

 `Navigations` 事件实例不同的 `NavigationId` 事件可能会重叠。  例如，启动导航时，必须等待相关 `NavigationStarting` 事件。  如果随后启动另一个导航，则应该会看到第一个导航的事件，后跟第二个导航的事件，然后是第一个导航的事件，然后是第二个导航的所有其他相应导航事件。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`  
 
 在错误情况下，可能会或可能不会发生事件，具体取决于导航 `ContentLoading` 是否继续导航到错误页面。  
 
 对于 HTTP 重定向，一行中有多个事件，其中后续事件参数设置了属性，但 `NavigationStarting` `IsRedirect` 事件参数 `NavigationId` 保持不变。  
 
 相同的 `navigations` 文档（如导航到片段）不会产生 `NavigationStarting` 事件，并且不会增加 `NavigationId` 。  

若要监视或取消 WebView 中的子框架内部，请使用和事件，这些事件的行为与等效的非 `navigations` `FrameNavigationStarting` `FrameNavigationCompleted` 帧对应事件类似。  

<!-- links -->  
