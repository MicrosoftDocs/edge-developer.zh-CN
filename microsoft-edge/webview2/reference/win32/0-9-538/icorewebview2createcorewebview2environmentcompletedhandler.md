---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
ms.openlocfilehash: 4cd8f4ab3904bd1a8c2277ba012bb5e6c32cf1d9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011123"
---
# <span data-ttu-id="4ec99-104">0.9.579-接口 ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="4ec99-104">0.9.579 - interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="4ec99-105">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="4ec99-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="4ec99-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4ec99-106">Summary</span></span>

 <span data-ttu-id="4ec99-107">成员</span><span class="sxs-lookup"><span data-stu-id="4ec99-107">Members</span></span>                        | <span data-ttu-id="4ec99-108">描述</span><span class="sxs-lookup"><span data-stu-id="4ec99-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4ec99-109">调用</span><span class="sxs-lookup"><span data-stu-id="4ec99-109">Invoke</span></span>](#invoke) | <span data-ttu-id="4ec99-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="4ec99-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="4ec99-111">成员</span><span class="sxs-lookup"><span data-stu-id="4ec99-111">Members</span></span>

#### <span data-ttu-id="4ec99-112">调用</span><span class="sxs-lookup"><span data-stu-id="4ec99-112">Invoke</span></span> 

<span data-ttu-id="4ec99-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="4ec99-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="4ec99-114">公共 HRESULT [调用](#invoke) (HRESULT 结果， [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment) </span><span class="sxs-lookup"><span data-stu-id="4ec99-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

