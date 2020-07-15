---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 3fdbe4d978a6a703576dd1135f7b79efad1befa5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881093"
---
# <span data-ttu-id="51b07-104">0.9.430-接口 ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="51b07-104">0.9.430 - interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="51b07-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="51b07-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="51b07-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="51b07-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="51b07-107">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="51b07-107">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="51b07-108">摘要</span><span class="sxs-lookup"><span data-stu-id="51b07-108">Summary</span></span>

 <span data-ttu-id="51b07-109">成员</span><span class="sxs-lookup"><span data-stu-id="51b07-109">Members</span></span>                        | <span data-ttu-id="51b07-110">描述</span><span class="sxs-lookup"><span data-stu-id="51b07-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="51b07-111">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="51b07-111">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="51b07-112">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="51b07-112">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="51b07-113">成员</span><span class="sxs-lookup"><span data-stu-id="51b07-113">Members</span></span>

#### <span data-ttu-id="51b07-114">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="51b07-114">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="51b07-115">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="51b07-115">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="51b07-116">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="51b07-116">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

