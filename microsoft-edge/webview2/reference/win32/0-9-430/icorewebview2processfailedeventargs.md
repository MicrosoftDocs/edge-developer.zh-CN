---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: a19f8c445d7ff1f6bee24cdd8871c28d41eedebe
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886407"
---
# <span data-ttu-id="e0311-104">0.9.430-接口 ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e0311-104">0.9.430 - interface ICoreWebView2ProcessFailedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="e0311-105">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e0311-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="e0311-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e0311-106">Summary</span></span>

 <span data-ttu-id="e0311-107">成员</span><span class="sxs-lookup"><span data-stu-id="e0311-107">Members</span></span>                        | <span data-ttu-id="e0311-108">描述</span><span class="sxs-lookup"><span data-stu-id="e0311-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e0311-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="e0311-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="e0311-110">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="e0311-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="e0311-111">成员</span><span class="sxs-lookup"><span data-stu-id="e0311-111">Members</span></span>

#### <span data-ttu-id="e0311-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="e0311-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="e0311-113">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="e0311-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="e0311-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（CORE_WEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind）</span><span class="sxs-lookup"><span data-stu-id="e0311-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

