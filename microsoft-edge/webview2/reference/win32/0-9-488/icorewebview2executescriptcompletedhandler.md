---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: e3618b7dc7b866031709ee276c80ba45ec89512d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698034"
---
# <span data-ttu-id="ff2ef-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ff2ef-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="ff2ef-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="ff2ef-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ff2ef-107">调用方实现此接口以接收 ExecuteScript 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-107">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="ff2ef-108">摘要</span><span class="sxs-lookup"><span data-stu-id="ff2ef-108">Summary</span></span>

 <span data-ttu-id="ff2ef-109">成员</span><span class="sxs-lookup"><span data-stu-id="ff2ef-109">Members</span></span>                        | <span data-ttu-id="ff2ef-110">描述</span><span class="sxs-lookup"><span data-stu-id="ff2ef-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ff2ef-111">调用</span><span class="sxs-lookup"><span data-stu-id="ff2ef-111">Invoke</span></span>](#invoke) | <span data-ttu-id="ff2ef-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="ff2ef-113">成员</span><span class="sxs-lookup"><span data-stu-id="ff2ef-113">Members</span></span>

#### <span data-ttu-id="ff2ef-114">调用</span><span class="sxs-lookup"><span data-stu-id="ff2ef-114">Invoke</span></span> 

<span data-ttu-id="ff2ef-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="ff2ef-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ff2ef-116">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR resultObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="ff2ef-116">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

