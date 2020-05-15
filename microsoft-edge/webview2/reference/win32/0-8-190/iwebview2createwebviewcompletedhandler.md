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
ms.openlocfilehash: 2788a18898da1f878520f4c4eb072c1a8b43375b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652819"
---
# <span data-ttu-id="04864-104">interface IWebView2CreateWebViewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="04864-104">interface IWebView2CreateWebViewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="04864-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="04864-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="04864-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="04864-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="04864-107">调用方实现此接口以接收通过 CreateWebView 创建的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="04864-107">The caller implements this interface to receive the WebView created via CreateWebView.</span></span>

## <span data-ttu-id="04864-108">摘要</span><span class="sxs-lookup"><span data-stu-id="04864-108">Summary</span></span>

 <span data-ttu-id="04864-109">成员</span><span class="sxs-lookup"><span data-stu-id="04864-109">Members</span></span>                        | <span data-ttu-id="04864-110">描述</span><span class="sxs-lookup"><span data-stu-id="04864-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="04864-111">调用</span><span class="sxs-lookup"><span data-stu-id="04864-111">Invoke</span></span>](#invoke) | <span data-ttu-id="04864-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="04864-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="04864-113">成员</span><span class="sxs-lookup"><span data-stu-id="04864-113">Members</span></span>

#### <span data-ttu-id="04864-114">调用</span><span class="sxs-lookup"><span data-stu-id="04864-114">Invoke</span></span> 

<span data-ttu-id="04864-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="04864-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="04864-116">公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2WebView](IWebView2WebView.md) \* web 视图）</span><span class="sxs-lookup"><span data-stu-id="04864-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2WebView](IWebView2WebView.md) \* webView)</span></span>

