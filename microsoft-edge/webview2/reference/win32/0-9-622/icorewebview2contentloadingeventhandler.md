---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ContentLoadingEventHandler
ms.openlocfilehash: 305f9fe0071385d2eaf83b26bd3cc2ee553df6df
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011802"
---
# <span data-ttu-id="fa13a-104">interface ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="fa13a-104">interface ICoreWebView2ContentLoadingEventHandler</span></span> 

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="fa13a-105">调用方实现此接口以接收 ContentLoading 事件。</span><span class="sxs-lookup"><span data-stu-id="fa13a-105">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="fa13a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fa13a-106">Summary</span></span>

 <span data-ttu-id="fa13a-107">成员</span><span class="sxs-lookup"><span data-stu-id="fa13a-107">Members</span></span>                        | <span data-ttu-id="fa13a-108">描述</span><span class="sxs-lookup"><span data-stu-id="fa13a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fa13a-109">调用</span><span class="sxs-lookup"><span data-stu-id="fa13a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="fa13a-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fa13a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="fa13a-111">成员</span><span class="sxs-lookup"><span data-stu-id="fa13a-111">Members</span></span>

#### <span data-ttu-id="fa13a-112">调用</span><span class="sxs-lookup"><span data-stu-id="fa13a-112">Invoke</span></span> 

<span data-ttu-id="fa13a-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fa13a-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="fa13a-114">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="fa13a-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span></span>

