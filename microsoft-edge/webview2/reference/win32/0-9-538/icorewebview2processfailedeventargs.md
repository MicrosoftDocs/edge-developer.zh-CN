---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ProcessFailedEventArgs
ms.openlocfilehash: 70fb6f75594284560cb0d64663fbda47cc7404d6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879343"
---
# <span data-ttu-id="63e53-104">interface ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="63e53-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="63e53-105">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="63e53-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="63e53-106">摘要</span><span class="sxs-lookup"><span data-stu-id="63e53-106">Summary</span></span>

 <span data-ttu-id="63e53-107">成员</span><span class="sxs-lookup"><span data-stu-id="63e53-107">Members</span></span>                        | <span data-ttu-id="63e53-108">描述</span><span class="sxs-lookup"><span data-stu-id="63e53-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="63e53-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="63e53-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="63e53-110">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="63e53-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="63e53-111">成员</span><span class="sxs-lookup"><span data-stu-id="63e53-111">Members</span></span>

#### <span data-ttu-id="63e53-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="63e53-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="63e53-113">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="63e53-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="63e53-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（COREWEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind）</span><span class="sxs-lookup"><span data-stu-id="63e53-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

