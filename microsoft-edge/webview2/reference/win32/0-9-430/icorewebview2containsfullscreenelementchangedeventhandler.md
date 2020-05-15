---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7c5aece49cf2a3e8e6a65eba3fbb4d46f0ff2997
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652976"
---
# <span data-ttu-id="47155-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="47155-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="47155-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="47155-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="47155-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="47155-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="47155-107">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="47155-107">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="47155-108">摘要</span><span class="sxs-lookup"><span data-stu-id="47155-108">Summary</span></span>

 <span data-ttu-id="47155-109">成员</span><span class="sxs-lookup"><span data-stu-id="47155-109">Members</span></span>                        | <span data-ttu-id="47155-110">描述</span><span class="sxs-lookup"><span data-stu-id="47155-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="47155-111">调用</span><span class="sxs-lookup"><span data-stu-id="47155-111">Invoke</span></span>](#invoke) | <span data-ttu-id="47155-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="47155-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="47155-113">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="47155-113">There are no event args for this event.</span></span>

## <span data-ttu-id="47155-114">成员</span><span class="sxs-lookup"><span data-stu-id="47155-114">Members</span></span>

#### <span data-ttu-id="47155-115">调用</span><span class="sxs-lookup"><span data-stu-id="47155-115">Invoke</span></span> 

<span data-ttu-id="47155-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="47155-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="47155-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="47155-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,IUnknown \* args)</span></span>

<span data-ttu-id="47155-118">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="47155-118">There are no event args and the args parameter will be null.</span></span>

