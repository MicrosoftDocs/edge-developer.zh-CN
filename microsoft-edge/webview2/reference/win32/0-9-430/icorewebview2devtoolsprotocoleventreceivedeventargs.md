---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: c42e353c80335b6dccdad49b470e68fa5ae2f559
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884251"
---
# <span data-ttu-id="bcf12-104">0.9.430-接口 ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="bcf12-104">0.9.430 - interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="bcf12-105">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bcf12-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="bcf12-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bcf12-106">Summary</span></span>

 <span data-ttu-id="bcf12-107">成员</span><span class="sxs-lookup"><span data-stu-id="bcf12-107">Members</span></span>                        | <span data-ttu-id="bcf12-108">描述</span><span class="sxs-lookup"><span data-stu-id="bcf12-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bcf12-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="bcf12-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="bcf12-110">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="bcf12-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="bcf12-111">成员</span><span class="sxs-lookup"><span data-stu-id="bcf12-111">Members</span></span>

#### <span data-ttu-id="bcf12-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="bcf12-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="bcf12-113">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="bcf12-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="bcf12-114">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="bcf12-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

