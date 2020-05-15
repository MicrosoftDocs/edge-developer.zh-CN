---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8fba2759ce0e264dcde515ee1191ec819f26eef9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653022"
---
# <span data-ttu-id="beaaa-104">interface ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="beaaa-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="beaaa-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="beaaa-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="beaaa-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="beaaa-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="beaaa-107">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="beaaa-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="beaaa-108">摘要</span><span class="sxs-lookup"><span data-stu-id="beaaa-108">Summary</span></span>

 <span data-ttu-id="beaaa-109">成员</span><span class="sxs-lookup"><span data-stu-id="beaaa-109">Members</span></span>                        | <span data-ttu-id="beaaa-110">描述</span><span class="sxs-lookup"><span data-stu-id="beaaa-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="beaaa-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="beaaa-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="beaaa-112">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="beaaa-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="beaaa-113">成员</span><span class="sxs-lookup"><span data-stu-id="beaaa-113">Members</span></span>

#### <span data-ttu-id="beaaa-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="beaaa-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="beaaa-115">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="beaaa-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="beaaa-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（CORE_WEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind）</span><span class="sxs-lookup"><span data-stu-id="beaaa-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

