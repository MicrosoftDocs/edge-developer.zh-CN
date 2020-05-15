---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 4cac9892e150f64b02b0a08c1164dcaa0aac4b7c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652972"
---
# <span data-ttu-id="a488d-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a488d-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a488d-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a488d-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="a488d-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a488d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a488d-107">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="a488d-107">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="a488d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a488d-108">Summary</span></span>

 <span data-ttu-id="a488d-109">成员</span><span class="sxs-lookup"><span data-stu-id="a488d-109">Members</span></span>                        | <span data-ttu-id="a488d-110">描述</span><span class="sxs-lookup"><span data-stu-id="a488d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a488d-111">调用</span><span class="sxs-lookup"><span data-stu-id="a488d-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a488d-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="a488d-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a488d-113">成员</span><span class="sxs-lookup"><span data-stu-id="a488d-113">Members</span></span>

#### <span data-ttu-id="a488d-114">调用</span><span class="sxs-lookup"><span data-stu-id="a488d-114">Invoke</span></span> 

<span data-ttu-id="a488d-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="a488d-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a488d-116">公共 HRESULT[调用](#invoke)（hresult 结果，[ICoreWebView2Environment](ICoreWebView2Environment.md) \* created_environment）</span><span class="sxs-lookup"><span data-stu-id="a488d-116">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Environment](ICoreWebView2Environment.md) \* created_environment)</span></span>

