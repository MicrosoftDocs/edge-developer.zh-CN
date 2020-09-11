---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2NavigationStartingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationStartingEventHandler
ms.openlocfilehash: ab4181d8a334ae4263665d964448f67cca965ff5
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011759"
---
# <span data-ttu-id="514f4-104">interface ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="514f4-104">interface ICoreWebView2NavigationStartingEventHandler</span></span> 

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="514f4-105">调用方实现此接口以接收 NavigationStarting 事件。</span><span class="sxs-lookup"><span data-stu-id="514f4-105">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="514f4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="514f4-106">Summary</span></span>

 <span data-ttu-id="514f4-107">成员</span><span class="sxs-lookup"><span data-stu-id="514f4-107">Members</span></span>                        | <span data-ttu-id="514f4-108">描述</span><span class="sxs-lookup"><span data-stu-id="514f4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="514f4-109">调用</span><span class="sxs-lookup"><span data-stu-id="514f4-109">Invoke</span></span>](#invoke) | <span data-ttu-id="514f4-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="514f4-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="514f4-111">成员</span><span class="sxs-lookup"><span data-stu-id="514f4-111">Members</span></span>

#### <span data-ttu-id="514f4-112">调用</span><span class="sxs-lookup"><span data-stu-id="514f4-112">Invoke</span></span> 

<span data-ttu-id="514f4-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="514f4-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="514f4-114">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="514f4-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

