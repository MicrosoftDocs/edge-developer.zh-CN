---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NewVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: e8965ebe2e0434d83b4d6e8eabe74466adb7cec6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878342"
---
# <span data-ttu-id="5512f-104">0.8.355-接口 IWebView2NewVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="5512f-104">0.8.355 - interface IWebView2NewVersionAvailableEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="5512f-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="5512f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="5512f-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="5512f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NewVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="5512f-107">NewVersionAvailable 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5512f-107">Event args for the NewVersionAvailable event.</span></span>

## <span data-ttu-id="5512f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5512f-108">Summary</span></span>

 <span data-ttu-id="5512f-109">成员</span><span class="sxs-lookup"><span data-stu-id="5512f-109">Members</span></span>                        | <span data-ttu-id="5512f-110">描述</span><span class="sxs-lookup"><span data-stu-id="5512f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5512f-111">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="5512f-111">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="5512f-112">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="5512f-112">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="5512f-113">成员</span><span class="sxs-lookup"><span data-stu-id="5512f-113">Members</span></span>

#### <span data-ttu-id="5512f-114">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="5512f-114">get_NewVersion</span></span> 

<span data-ttu-id="5512f-115">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="5512f-115">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

> <span data-ttu-id="5512f-116">公共 HRESULT [get_NewVersion](#get_newversion)（LPWSTR \* 新版）</span><span class="sxs-lookup"><span data-stu-id="5512f-116">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

