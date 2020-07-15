---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
ms.openlocfilehash: c41da3c6f88c06d0642d00f38a8181acb079a009
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877404"
---
# <span data-ttu-id="0145f-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="0145f-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="0145f-105">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="0145f-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="0145f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0145f-106">Summary</span></span>

 <span data-ttu-id="0145f-107">成员</span><span class="sxs-lookup"><span data-stu-id="0145f-107">Members</span></span>                        | <span data-ttu-id="0145f-108">描述</span><span class="sxs-lookup"><span data-stu-id="0145f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0145f-109">调用</span><span class="sxs-lookup"><span data-stu-id="0145f-109">Invoke</span></span>](#invoke) | <span data-ttu-id="0145f-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0145f-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="0145f-111">成员</span><span class="sxs-lookup"><span data-stu-id="0145f-111">Members</span></span>

#### <span data-ttu-id="0145f-112">调用</span><span class="sxs-lookup"><span data-stu-id="0145f-112">Invoke</span></span> 

<span data-ttu-id="0145f-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0145f-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="0145f-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment）</span><span class="sxs-lookup"><span data-stu-id="0145f-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

