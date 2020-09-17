---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ProcessFailedEventHandler
ms.openlocfilehash: 98f3f092bc1feb75ea2f94857c31dd80bcb907ee
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011749"
---
# <span data-ttu-id="077fe-104">interface ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="077fe-104">interface ICoreWebView2ProcessFailedEventHandler</span></span> 

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="077fe-105">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="077fe-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="077fe-106">摘要</span><span class="sxs-lookup"><span data-stu-id="077fe-106">Summary</span></span>

 <span data-ttu-id="077fe-107">成员</span><span class="sxs-lookup"><span data-stu-id="077fe-107">Members</span></span>                        | <span data-ttu-id="077fe-108">描述</span><span class="sxs-lookup"><span data-stu-id="077fe-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="077fe-109">调用</span><span class="sxs-lookup"><span data-stu-id="077fe-109">Invoke</span></span>](#invoke) | <span data-ttu-id="077fe-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="077fe-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="077fe-111">成员</span><span class="sxs-lookup"><span data-stu-id="077fe-111">Members</span></span>

#### <span data-ttu-id="077fe-112">调用</span><span class="sxs-lookup"><span data-stu-id="077fe-112">Invoke</span></span> 

<span data-ttu-id="077fe-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="077fe-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="077fe-114">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="077fe-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span></span>
