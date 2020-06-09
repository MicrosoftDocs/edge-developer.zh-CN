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
ms.openlocfilehash: a675bede2e1e509f3cfcc7490ac157da3f6d876c
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698488"
---
# <span data-ttu-id="fb1a7-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="fb1a7-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="fb1a7-105">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="fb1a7-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="fb1a7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fb1a7-106">Summary</span></span>

 <span data-ttu-id="fb1a7-107">成员</span><span class="sxs-lookup"><span data-stu-id="fb1a7-107">Members</span></span>                        | <span data-ttu-id="fb1a7-108">描述</span><span class="sxs-lookup"><span data-stu-id="fb1a7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fb1a7-109">调用</span><span class="sxs-lookup"><span data-stu-id="fb1a7-109">Invoke</span></span>](#invoke) | <span data-ttu-id="fb1a7-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="fb1a7-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="fb1a7-111">成员</span><span class="sxs-lookup"><span data-stu-id="fb1a7-111">Members</span></span>

#### <span data-ttu-id="fb1a7-112">调用</span><span class="sxs-lookup"><span data-stu-id="fb1a7-112">Invoke</span></span> 

<span data-ttu-id="fb1a7-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="fb1a7-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="fb1a7-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="fb1a7-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR returnObjectAsJson)</span></span>

