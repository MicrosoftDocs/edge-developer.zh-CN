---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 5cc3ca23dcababc35a73b44a81c54439d0dbe1a3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884307"
---
# <span data-ttu-id="cc5c9-104">0.9.430-接口 ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="cc5c9-104">0.9.430 - interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="cc5c9-105">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="cc5c9-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="cc5c9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cc5c9-106">Summary</span></span>

 <span data-ttu-id="cc5c9-107">成员</span><span class="sxs-lookup"><span data-stu-id="cc5c9-107">Members</span></span>                        | <span data-ttu-id="cc5c9-108">描述</span><span class="sxs-lookup"><span data-stu-id="cc5c9-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cc5c9-109">调用</span><span class="sxs-lookup"><span data-stu-id="cc5c9-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cc5c9-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="cc5c9-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="cc5c9-111">成员</span><span class="sxs-lookup"><span data-stu-id="cc5c9-111">Members</span></span>

#### <span data-ttu-id="cc5c9-112">调用</span><span class="sxs-lookup"><span data-stu-id="cc5c9-112">Invoke</span></span> 

<span data-ttu-id="cc5c9-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="cc5c9-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="cc5c9-114">公共 HRESULT[调用](#invoke)（hresult 结果，[ICoreWebView2Environment](ICoreWebView2Environment.md) \* created_environment）</span><span class="sxs-lookup"><span data-stu-id="cc5c9-114">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Environment](ICoreWebView2Environment.md) \* created_environment)</span></span>

