---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1397fb15963cadd508082e39a735a8f0f64a8e91
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698069"
---
# <span data-ttu-id="11487-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="11487-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="11487-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="11487-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="11487-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="11487-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="11487-107">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="11487-107">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="11487-108">摘要</span><span class="sxs-lookup"><span data-stu-id="11487-108">Summary</span></span>

 <span data-ttu-id="11487-109">成员</span><span class="sxs-lookup"><span data-stu-id="11487-109">Members</span></span>                        | <span data-ttu-id="11487-110">描述</span><span class="sxs-lookup"><span data-stu-id="11487-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="11487-111">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="11487-111">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="11487-112">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="11487-112">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="11487-113">成员</span><span class="sxs-lookup"><span data-stu-id="11487-113">Members</span></span>

#### <span data-ttu-id="11487-114">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="11487-114">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="11487-115">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="11487-115">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="11487-116">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="11487-116">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

