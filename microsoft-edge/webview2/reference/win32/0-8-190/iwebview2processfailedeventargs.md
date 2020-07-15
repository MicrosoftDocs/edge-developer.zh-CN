---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 5ceb24d0d20f580e14e0d5af7ec09881c9ab0eb2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878244"
---
# <span data-ttu-id="11318-104">0.8.355-接口 IWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="11318-104">0.8.355 - interface IWebView2ProcessFailedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="11318-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="11318-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="11318-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="11318-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="11318-107">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="11318-107">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="11318-108">摘要</span><span class="sxs-lookup"><span data-stu-id="11318-108">Summary</span></span>

 <span data-ttu-id="11318-109">成员</span><span class="sxs-lookup"><span data-stu-id="11318-109">Members</span></span>                        | <span data-ttu-id="11318-110">描述</span><span class="sxs-lookup"><span data-stu-id="11318-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="11318-111">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="11318-111">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="11318-112">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="11318-112">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="11318-113">成员</span><span class="sxs-lookup"><span data-stu-id="11318-113">Members</span></span>

#### <span data-ttu-id="11318-114">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="11318-114">get_ProcessFailedKind</span></span> 

<span data-ttu-id="11318-115">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="11318-115">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="11318-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（WEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind）</span><span class="sxs-lookup"><span data-stu-id="11318-116">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

