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
ms.openlocfilehash: 22de463a0b0a6b279ffab6549526b11cbabafa51
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697222"
---
# <span data-ttu-id="89385-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="89385-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="89385-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="89385-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="89385-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="89385-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="89385-107">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="89385-107">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="89385-108">摘要</span><span class="sxs-lookup"><span data-stu-id="89385-108">Summary</span></span>

 <span data-ttu-id="89385-109">成员</span><span class="sxs-lookup"><span data-stu-id="89385-109">Members</span></span>                        | <span data-ttu-id="89385-110">描述</span><span class="sxs-lookup"><span data-stu-id="89385-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="89385-111">调用</span><span class="sxs-lookup"><span data-stu-id="89385-111">Invoke</span></span>](#invoke) | <span data-ttu-id="89385-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="89385-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="89385-113">成员</span><span class="sxs-lookup"><span data-stu-id="89385-113">Members</span></span>

#### <span data-ttu-id="89385-114">调用</span><span class="sxs-lookup"><span data-stu-id="89385-114">Invoke</span></span> 

<span data-ttu-id="89385-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="89385-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="89385-116">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="89385-116">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR returnObjectAsJson)</span></span>

