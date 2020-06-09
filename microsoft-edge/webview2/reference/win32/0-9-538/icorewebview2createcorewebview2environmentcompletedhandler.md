---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: dbc1a3e05f9cdc5b5ced2e0b7d489b06392e6100
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698471"
---
# <span data-ttu-id="e4f36-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="e4f36-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="e4f36-105">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="e4f36-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="e4f36-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e4f36-106">Summary</span></span>

 <span data-ttu-id="e4f36-107">成员</span><span class="sxs-lookup"><span data-stu-id="e4f36-107">Members</span></span>                        | <span data-ttu-id="e4f36-108">描述</span><span class="sxs-lookup"><span data-stu-id="e4f36-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e4f36-109">调用</span><span class="sxs-lookup"><span data-stu-id="e4f36-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e4f36-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="e4f36-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="e4f36-111">成员</span><span class="sxs-lookup"><span data-stu-id="e4f36-111">Members</span></span>

#### <span data-ttu-id="e4f36-112">调用</span><span class="sxs-lookup"><span data-stu-id="e4f36-112">Invoke</span></span> 

<span data-ttu-id="e4f36-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="e4f36-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="e4f36-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment）</span><span class="sxs-lookup"><span data-stu-id="e4f36-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

