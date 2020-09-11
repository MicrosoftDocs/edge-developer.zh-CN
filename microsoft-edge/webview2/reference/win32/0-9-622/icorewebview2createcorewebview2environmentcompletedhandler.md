---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
ms.openlocfilehash: 3f6b6b9a2d4df2a450b4589c351c3ea98f7cc28f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011795"
---
# <span data-ttu-id="24efc-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="24efc-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="24efc-105">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="24efc-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="24efc-106">摘要</span><span class="sxs-lookup"><span data-stu-id="24efc-106">Summary</span></span>

 <span data-ttu-id="24efc-107">成员</span><span class="sxs-lookup"><span data-stu-id="24efc-107">Members</span></span>                        | <span data-ttu-id="24efc-108">描述</span><span class="sxs-lookup"><span data-stu-id="24efc-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="24efc-109">调用</span><span class="sxs-lookup"><span data-stu-id="24efc-109">Invoke</span></span>](#invoke) | <span data-ttu-id="24efc-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="24efc-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="24efc-111">成员</span><span class="sxs-lookup"><span data-stu-id="24efc-111">Members</span></span>

#### <span data-ttu-id="24efc-112">调用</span><span class="sxs-lookup"><span data-stu-id="24efc-112">Invoke</span></span> 

<span data-ttu-id="24efc-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="24efc-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="24efc-114">公共 HRESULT [调用](#invoke) (HRESULT ErrorCode， [ICoreWebView2Environment](icorewebview2environment.md) \* createdEnvironment) </span><span class="sxs-lookup"><span data-stu-id="24efc-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, [ICoreWebView2Environment](icorewebview2environment.md) \* createdEnvironment)</span></span>

