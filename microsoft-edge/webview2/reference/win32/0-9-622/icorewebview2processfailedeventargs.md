---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ProcessFailedEventArgs
ms.openlocfilehash: 0f4ce5d4922b7a721ce2652fadfa5169a52cb458
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011751"
---
# <span data-ttu-id="ff0c3-104">interface ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ff0c3-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="ff0c3-105">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ff0c3-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="ff0c3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ff0c3-106">Summary</span></span>

 <span data-ttu-id="ff0c3-107">成员</span><span class="sxs-lookup"><span data-stu-id="ff0c3-107">Members</span></span>                        | <span data-ttu-id="ff0c3-108">描述</span><span class="sxs-lookup"><span data-stu-id="ff0c3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ff0c3-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="ff0c3-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="ff0c3-110">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="ff0c3-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="ff0c3-111">成员</span><span class="sxs-lookup"><span data-stu-id="ff0c3-111">Members</span></span>

#### <span data-ttu-id="ff0c3-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="ff0c3-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="ff0c3-113">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="ff0c3-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="ff0c3-114">公共 HRESULT [get_ProcessFailedKind](#get_processfailedkind) (COREWEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind) </span><span class="sxs-lookup"><span data-stu-id="ff0c3-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>
