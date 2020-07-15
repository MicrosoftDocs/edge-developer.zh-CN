---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2NewBrowserVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NewBrowserVersionAvailableEventHandler
ms.openlocfilehash: 82a5e73b8b928897e5c0af1610631c9e7d636337
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879742"
---
# <span data-ttu-id="4e7ef-104">interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="4e7ef-104">interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="4e7ef-105">调用方实现此接口以接收 NewBrowserVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="4e7ef-105">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="4e7ef-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4e7ef-106">Summary</span></span>

 <span data-ttu-id="4e7ef-107">成员</span><span class="sxs-lookup"><span data-stu-id="4e7ef-107">Members</span></span>                        | <span data-ttu-id="4e7ef-108">描述</span><span class="sxs-lookup"><span data-stu-id="4e7ef-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4e7ef-109">调用</span><span class="sxs-lookup"><span data-stu-id="4e7ef-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4e7ef-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="4e7ef-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="4e7ef-111">成员</span><span class="sxs-lookup"><span data-stu-id="4e7ef-111">Members</span></span>

#### <span data-ttu-id="4e7ef-112">调用</span><span class="sxs-lookup"><span data-stu-id="4e7ef-112">Invoke</span></span> 

<span data-ttu-id="4e7ef-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="4e7ef-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="4e7ef-114">public HRESULT [Invoke](#invoke)（[ICoreWebView2Environment](icorewebview2environment.md) \* webviewEnvironment，IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="4e7ef-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) \* webviewEnvironment, IUnknown \* args)</span></span>

