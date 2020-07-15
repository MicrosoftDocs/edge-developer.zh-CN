---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 52218ddcbecdaf3bdb736af877493c85d4460c10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878041"
---
# <span data-ttu-id="b3ba1-104">0.8.355-接口 IWebView2WebView2</span><span class="sxs-lookup"><span data-stu-id="b3ba1-104">0.8.355 - interface IWebView2WebView2</span></span> 

> [!NOTE]
> <span data-ttu-id="b3ba1-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="b3ba1-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView2
  : public IUnknown
```

<span data-ttu-id="b3ba1-107">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="b3ba1-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b3ba1-108">Summary</span></span>

 <span data-ttu-id="b3ba1-109">成员</span><span class="sxs-lookup"><span data-stu-id="b3ba1-109">Members</span></span>                        | <span data-ttu-id="b3ba1-110">描述</span><span class="sxs-lookup"><span data-stu-id="b3ba1-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b3ba1-111">停止</span><span class="sxs-lookup"><span data-stu-id="b3ba1-111">Stop</span></span>](#stop) | <span data-ttu-id="b3ba1-112">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-112">Stop all navigations and pending resource fetches.</span></span>

<span data-ttu-id="b3ba1-113">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-113">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="b3ba1-114">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-114">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="b3ba1-115">成员</span><span class="sxs-lookup"><span data-stu-id="b3ba1-115">Members</span></span>

#### <span data-ttu-id="b3ba1-116">停止</span><span class="sxs-lookup"><span data-stu-id="b3ba1-116">Stop</span></span> 

<span data-ttu-id="b3ba1-117">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="b3ba1-117">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="b3ba1-118">公共 HRESULT[停止](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="b3ba1-118">public HRESULT [Stop](#stop)()</span></span>

