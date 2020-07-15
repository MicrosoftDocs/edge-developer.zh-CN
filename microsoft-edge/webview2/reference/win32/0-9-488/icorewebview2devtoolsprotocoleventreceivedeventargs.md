---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a6c7acf933192bfe96ac863620d3348eeca41ec7
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880792"
---
# <span data-ttu-id="dd424-104">0.9.515-接口 ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="dd424-104">0.9.515 - interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="dd424-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="dd424-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="dd424-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="dd424-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="dd424-107">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="dd424-107">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="dd424-108">摘要</span><span class="sxs-lookup"><span data-stu-id="dd424-108">Summary</span></span>

 <span data-ttu-id="dd424-109">成员</span><span class="sxs-lookup"><span data-stu-id="dd424-109">Members</span></span>                        | <span data-ttu-id="dd424-110">描述</span><span class="sxs-lookup"><span data-stu-id="dd424-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dd424-111">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="dd424-111">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="dd424-112">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="dd424-112">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="dd424-113">成员</span><span class="sxs-lookup"><span data-stu-id="dd424-113">Members</span></span>

#### <span data-ttu-id="dd424-114">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="dd424-114">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="dd424-115">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="dd424-115">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="dd424-116">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="dd424-116">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

