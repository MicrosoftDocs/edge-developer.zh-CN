---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 9aa9a18701621ca78b74b12340ef5132953fbd2b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880666"
---
# <span data-ttu-id="83d9c-104">0.9.515-接口 ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="83d9c-104">0.9.515 - interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="83d9c-105">这是使用预发行 SDK 版本0.9.488 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="83d9c-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="83d9c-106">调用方实现此接口以接收通过 CreateCoreWebView2CompositionController 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="83d9c-106">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="83d9c-107">摘要</span><span class="sxs-lookup"><span data-stu-id="83d9c-107">Summary</span></span>

 <span data-ttu-id="83d9c-108">成员</span><span class="sxs-lookup"><span data-stu-id="83d9c-108">Members</span></span>                        | <span data-ttu-id="83d9c-109">描述</span><span class="sxs-lookup"><span data-stu-id="83d9c-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="83d9c-110">调用</span><span class="sxs-lookup"><span data-stu-id="83d9c-110">Invoke</span></span>](#invoke) | <span data-ttu-id="83d9c-111">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="83d9c-111">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="83d9c-112">成员</span><span class="sxs-lookup"><span data-stu-id="83d9c-112">Members</span></span>

#### <span data-ttu-id="83d9c-113">调用</span><span class="sxs-lookup"><span data-stu-id="83d9c-113">Invoke</span></span> 

<span data-ttu-id="83d9c-114">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="83d9c-114">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="83d9c-115">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* web 视图）</span><span class="sxs-lookup"><span data-stu-id="83d9c-115">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

