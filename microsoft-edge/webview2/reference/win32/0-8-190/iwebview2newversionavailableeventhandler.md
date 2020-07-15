---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NewVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: da17bad643ac7f0a9614754bf57c7d208c265ace
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878356"
---
# <span data-ttu-id="a7db9-104">0.8.355-接口 IWebView2NewVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="a7db9-104">0.8.355 - interface IWebView2NewVersionAvailableEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a7db9-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a7db9-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="a7db9-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a7db9-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NewVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="a7db9-107">调用方实现此接口以接收 NewVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="a7db9-107">The caller implements this interface to receive NewVersionAvailable events.</span></span>

## <span data-ttu-id="a7db9-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a7db9-108">Summary</span></span>

 <span data-ttu-id="a7db9-109">成员</span><span class="sxs-lookup"><span data-stu-id="a7db9-109">Members</span></span>                        | <span data-ttu-id="a7db9-110">描述</span><span class="sxs-lookup"><span data-stu-id="a7db9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a7db9-111">调用</span><span class="sxs-lookup"><span data-stu-id="a7db9-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a7db9-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a7db9-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a7db9-113">使用[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md)的 get_NewVersion 方法获取新的版本号。</span><span class="sxs-lookup"><span data-stu-id="a7db9-113">Use the get_NewVersion method of [IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="a7db9-114">成员</span><span class="sxs-lookup"><span data-stu-id="a7db9-114">Members</span></span>

#### <span data-ttu-id="a7db9-115">调用</span><span class="sxs-lookup"><span data-stu-id="a7db9-115">Invoke</span></span> 

<span data-ttu-id="a7db9-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a7db9-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a7db9-117">public HRESULT [Invoke](#invoke)（[IWebView2Environment](IWebView2Environment.md) \* webviewEnvironment，[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="a7db9-117">public HRESULT [Invoke](#invoke)([IWebView2Environment](IWebView2Environment.md) \* webviewEnvironment,[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* args)</span></span>

