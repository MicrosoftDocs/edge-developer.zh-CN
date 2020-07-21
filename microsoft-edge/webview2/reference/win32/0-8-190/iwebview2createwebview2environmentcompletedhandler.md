---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CreateWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 9937fe08f440ce468f178e4ac17935bbb8a1a8ed
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886169"
---
# <span data-ttu-id="cbf1a-104">0.8.355-接口 IWebView2CreateWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="cbf1a-104">0.8.355 - interface IWebView2CreateWebView2EnvironmentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CreateWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="cbf1a-105">调用方实现此接口以接收通过 CreateWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="cbf1a-105">The caller implements this interface to receive the WebView2Environment created via CreateWebView2Environment.</span></span>

## <span data-ttu-id="cbf1a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cbf1a-106">Summary</span></span>

 <span data-ttu-id="cbf1a-107">成员</span><span class="sxs-lookup"><span data-stu-id="cbf1a-107">Members</span></span>                        | <span data-ttu-id="cbf1a-108">描述</span><span class="sxs-lookup"><span data-stu-id="cbf1a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cbf1a-109">调用</span><span class="sxs-lookup"><span data-stu-id="cbf1a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cbf1a-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="cbf1a-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="cbf1a-111">成员</span><span class="sxs-lookup"><span data-stu-id="cbf1a-111">Members</span></span>

#### <span data-ttu-id="cbf1a-112">调用</span><span class="sxs-lookup"><span data-stu-id="cbf1a-112">Invoke</span></span> 

<span data-ttu-id="cbf1a-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="cbf1a-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="cbf1a-114">公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment）</span><span class="sxs-lookup"><span data-stu-id="cbf1a-114">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment)</span></span>

