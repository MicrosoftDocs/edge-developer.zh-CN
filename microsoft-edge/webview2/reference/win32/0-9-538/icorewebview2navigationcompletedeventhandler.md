---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationCompletedEventHandler
ms.openlocfilehash: 24651585298998eaa42b2be242785de1bf4d6f84
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879791"
---
# <span data-ttu-id="02972-104">interface ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="02972-104">interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="02972-105">调用方实现此接口以接收 NavigationCompleted 事件。</span><span class="sxs-lookup"><span data-stu-id="02972-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="02972-106">摘要</span><span class="sxs-lookup"><span data-stu-id="02972-106">Summary</span></span>

 <span data-ttu-id="02972-107">成员</span><span class="sxs-lookup"><span data-stu-id="02972-107">Members</span></span>                        | <span data-ttu-id="02972-108">描述</span><span class="sxs-lookup"><span data-stu-id="02972-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="02972-109">调用</span><span class="sxs-lookup"><span data-stu-id="02972-109">Invoke</span></span>](#invoke) | <span data-ttu-id="02972-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="02972-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="02972-111">成员</span><span class="sxs-lookup"><span data-stu-id="02972-111">Members</span></span>

#### <span data-ttu-id="02972-112">调用</span><span class="sxs-lookup"><span data-stu-id="02972-112">Invoke</span></span> 

<span data-ttu-id="02972-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="02972-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="02972-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="02972-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

