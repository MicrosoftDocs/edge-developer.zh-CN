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
ms.openlocfilehash: 7a4e074d445b4bab11e8e79dc6cfe5346effbb3f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653162"
---
# <span data-ttu-id="0af00-104">interface IWebView2CreateWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="0af00-104">interface IWebView2CreateWebView2EnvironmentCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="0af00-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="0af00-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="0af00-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="0af00-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="0af00-107">调用方实现此接口以接收通过 CreateWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="0af00-107">The caller implements this interface to receive the WebView2Environment created via CreateWebView2Environment.</span></span>

## <span data-ttu-id="0af00-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0af00-108">Summary</span></span>

 <span data-ttu-id="0af00-109">成员</span><span class="sxs-lookup"><span data-stu-id="0af00-109">Members</span></span>                        | <span data-ttu-id="0af00-110">描述</span><span class="sxs-lookup"><span data-stu-id="0af00-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0af00-111">调用</span><span class="sxs-lookup"><span data-stu-id="0af00-111">Invoke</span></span>](#invoke) | <span data-ttu-id="0af00-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0af00-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="0af00-113">成员</span><span class="sxs-lookup"><span data-stu-id="0af00-113">Members</span></span>

#### <span data-ttu-id="0af00-114">调用</span><span class="sxs-lookup"><span data-stu-id="0af00-114">Invoke</span></span> 

<span data-ttu-id="0af00-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0af00-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="0af00-116">公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment）</span><span class="sxs-lookup"><span data-stu-id="0af00-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment)</span></span>

