---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 0efc1656b8204b9775002db49e0e4a5734682cc4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652815"
---
# <span data-ttu-id="da411-104">interface ICoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="da411-104">interface ICoreWebView2ProcessFailedEventArgs</span></span> 

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

<span data-ttu-id="da411-105">ProcessFailed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="da411-105">Event args for the ProcessFailed event.</span></span>

## <span data-ttu-id="da411-106">摘要</span><span class="sxs-lookup"><span data-stu-id="da411-106">Summary</span></span>

 <span data-ttu-id="da411-107">成员</span><span class="sxs-lookup"><span data-stu-id="da411-107">Members</span></span>                        | <span data-ttu-id="da411-108">描述</span><span class="sxs-lookup"><span data-stu-id="da411-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="da411-109">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="da411-109">get_ProcessFailedKind</span></span>](#get_processfailedkind) | <span data-ttu-id="da411-110">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="da411-110">The kind of process failure that has occurred.</span></span>

## <span data-ttu-id="da411-111">成员</span><span class="sxs-lookup"><span data-stu-id="da411-111">Members</span></span>

#### <span data-ttu-id="da411-112">get_ProcessFailedKind</span><span class="sxs-lookup"><span data-stu-id="da411-112">get_ProcessFailedKind</span></span> 

<span data-ttu-id="da411-113">已发生的进程失败的类型。</span><span class="sxs-lookup"><span data-stu-id="da411-113">The kind of process failure that has occurred.</span></span>

> <span data-ttu-id="da411-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（COREWEBVIEW2_PROCESS_FAILED_KIND \* ProcessFailedKind）</span><span class="sxs-lookup"><span data-stu-id="da411-114">public HRESULT [get_ProcessFailedKind](#get_processfailedkind)(COREWEBVIEW2_PROCESS_FAILED_KIND \* processFailedKind)</span></span>

