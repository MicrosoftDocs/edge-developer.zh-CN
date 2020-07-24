---
description: 流程模型
title: 流程模型
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8548308896815266fbd1e150da979b56cfb268e2
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895537"
---
# 流程模型  

WebView2 使用与 Microsoft Edge 浏览器相同的进程模型。  有关浏览器进程模型的详细信息，请参阅[浏览器体系结构-内部查看新式 web 浏览器][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]。 

一个浏览器进程与该文章中所述的呈现程序进程和其他实用工具进程相关联。  此外，在 WebView2 的情况下，存在使用 WebView2 请求进程的主机应用。  

:::image type="complex" source="../media/process-model-1.png" alt-text="Process 1" lightbox="../media/process-model-1.png":::
   Process 1  
:::image-end:::  

在为任何 WebView2 请求进程的用户会话中为每个用户的数据文件夹指定一个浏览器进程，指定该用户数据文件夹。  这意味着一个浏览器进程可能正在为多个请求进程提供服务，而一个请求进程可能正在使用多个浏览器进程。  

:::image type="complex" source="../media/process-model-2.png" alt-text="过程2" lightbox="../media/process-model-2.png":::
   过程2  
:::image-end:::  

浏览器进程具有一些关联的呈现器进程。  根据需要创建浏览器进程，以便在 WebView2 的不同实例中服务潜在的多个帧。  呈现器进程的数量因网站隔离浏览器功能和在 WebView2 相关联的实例中呈现的唯一断开的来源的数量而异。  以前的内容中介绍了网站隔离浏览器功能。  

`CoreWebView2Environment`表示用户数据文件夹和浏览器进程。  不 `CoreWebView2` 会直接对应于任何一组进程，因为各种呈现程序进程由 WebView2 使用，具体取决于前面所述的网站隔离。  

你可以使用的事件来响应在这些浏览器和呈现器进程中崩溃和挂起 `ProcessFailed` `CoreWebView2` 。  

你可以使用的方法安全地关闭关联浏览器和呈现器进程 `Close` `CoreWebView2Controller` 。  

若要从 WebView2 实例的**DevTools**窗口中打开浏览器任务管理器窗口，您可以选择 `Shift` + `Escape` 或悬停在 DevTools 窗口标题栏上，打开上下文菜单 \ （右键单击 \），然后选择 `Browser task manager` 。  将显示与你的 WebView2 的浏览器进程关联的所有进程，包括相关用途。  

<!-- links -->  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "浏览器体系结构-在新式 web 浏览器中查看（第1部分）"  
