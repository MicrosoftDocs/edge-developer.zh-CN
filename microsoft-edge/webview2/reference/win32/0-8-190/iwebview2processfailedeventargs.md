---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 748c4affa73001270e2cf97b3d19db8c8ed23686
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653191"
---
# <span data-ttu-id="4c5fa-104">interface IWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4c5fa-104">interface IWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="4c5fa-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="4c5fa-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="4c5fa-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="4c5fa-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="4c5fa-107">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="4c5fa-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="4c5fa-108">摘要</span><span class="sxs-lookup"><span data-stu-id="4c5fa-108">Summary</span></span>

 <span data-ttu-id="4c5fa-109">成员</span><span class="sxs-lookup"><span data-stu-id="4c5fa-109">Members</span></span>                        | <span data-ttu-id="4c5fa-110">描述</span><span class="sxs-lookup"><span data-stu-id="4c5fa-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4c5fa-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="4c5fa-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="4c5fa-112">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="4c5fa-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="4c5fa-113">成员</span><span class="sxs-lookup"><span data-stu-id="4c5fa-113">Members</span></span>

#### <span data-ttu-id="4c5fa-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="4c5fa-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="4c5fa-115">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="4c5fa-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="4c5fa-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（WEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind）</span><span class="sxs-lookup"><span data-stu-id="4c5fa-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

