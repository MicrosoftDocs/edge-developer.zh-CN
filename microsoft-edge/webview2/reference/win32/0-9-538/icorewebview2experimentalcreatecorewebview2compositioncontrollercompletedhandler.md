---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
ms.openlocfilehash: 8fc3efa6bf1ba9a9e721dcba67e8350ded38cc62
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011132"
---
# <span data-ttu-id="b7721-104">0.9.579-接口 ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="b7721-104">0.9.579 - interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="b7721-105">调用方实现此接口以接收通过 CreateCoreWebView2CompositionController 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="b7721-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="b7721-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b7721-106">Summary</span></span>

 <span data-ttu-id="b7721-107">成员</span><span class="sxs-lookup"><span data-stu-id="b7721-107">Members</span></span>                        | <span data-ttu-id="b7721-108">描述</span><span class="sxs-lookup"><span data-stu-id="b7721-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b7721-109">调用</span><span class="sxs-lookup"><span data-stu-id="b7721-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b7721-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="b7721-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="b7721-111">成员</span><span class="sxs-lookup"><span data-stu-id="b7721-111">Members</span></span>

#### <span data-ttu-id="b7721-112">调用</span><span class="sxs-lookup"><span data-stu-id="b7721-112">Invoke</span></span> 

<span data-ttu-id="b7721-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="b7721-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="b7721-114">公共 HRESULT [调用](#invoke) (HRESULT 结果， [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* web 视图) </span><span class="sxs-lookup"><span data-stu-id="b7721-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

