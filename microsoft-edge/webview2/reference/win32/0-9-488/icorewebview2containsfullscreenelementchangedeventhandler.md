---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 85de243c00364f7fb57d3842b2ddbf78848905f6
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653135"
---
# <span data-ttu-id="05807-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="05807-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="05807-105">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="05807-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="05807-106">摘要</span><span class="sxs-lookup"><span data-stu-id="05807-106">Summary</span></span>

 <span data-ttu-id="05807-107">成员</span><span class="sxs-lookup"><span data-stu-id="05807-107">Members</span></span>                        | <span data-ttu-id="05807-108">描述</span><span class="sxs-lookup"><span data-stu-id="05807-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="05807-109">调用</span><span class="sxs-lookup"><span data-stu-id="05807-109">Invoke</span></span>](#invoke) | <span data-ttu-id="05807-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="05807-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="05807-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="05807-111">There are no event args for this event.</span></span>

## <span data-ttu-id="05807-112">成员</span><span class="sxs-lookup"><span data-stu-id="05807-112">Members</span></span>

#### <span data-ttu-id="05807-113">调用</span><span class="sxs-lookup"><span data-stu-id="05807-113">Invoke</span></span> 

<span data-ttu-id="05807-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="05807-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="05807-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="05807-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="05807-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="05807-116">There are no event args and the args parameter will be null.</span></span>

