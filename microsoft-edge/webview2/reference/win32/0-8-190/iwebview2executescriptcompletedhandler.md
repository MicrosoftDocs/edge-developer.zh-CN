---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: ecd3215c343925614b81d5da96fbf996350fd5a5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878503"
---
# <span data-ttu-id="11ed0-104">0.8.355-接口 IWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="11ed0-104">0.8.355 - interface IWebView2ExecuteScriptCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="11ed0-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="11ed0-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="11ed0-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="11ed0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="11ed0-107">调用方实现此接口以接收 ExecuteScript 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="11ed0-107">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="11ed0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="11ed0-108">Summary</span></span>

 <span data-ttu-id="11ed0-109">成员</span><span class="sxs-lookup"><span data-stu-id="11ed0-109">Members</span></span>                        | <span data-ttu-id="11ed0-110">描述</span><span class="sxs-lookup"><span data-stu-id="11ed0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="11ed0-111">调用</span><span class="sxs-lookup"><span data-stu-id="11ed0-111">Invoke</span></span>](#invoke) | <span data-ttu-id="11ed0-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="11ed0-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="11ed0-113">成员</span><span class="sxs-lookup"><span data-stu-id="11ed0-113">Members</span></span>

#### <span data-ttu-id="11ed0-114">调用</span><span class="sxs-lookup"><span data-stu-id="11ed0-114">Invoke</span></span> 

<span data-ttu-id="11ed0-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="11ed0-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="11ed0-116">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR resultObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="11ed0-116">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR resultObjectAsJson)</span></span>

