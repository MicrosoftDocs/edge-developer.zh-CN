---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 920d95b737a15926e6de33cfed0ee9a98eeade78
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886150"
---
# <span data-ttu-id="0a9b7-104">0.8.355-接口 IWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="0a9b7-104">0.8.355 - interface IWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="0a9b7-105">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0a9b7-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="0a9b7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0a9b7-106">Summary</span></span>

 <span data-ttu-id="0a9b7-107">成员</span><span class="sxs-lookup"><span data-stu-id="0a9b7-107">Members</span></span>                        | <span data-ttu-id="0a9b7-108">描述</span><span class="sxs-lookup"><span data-stu-id="0a9b7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0a9b7-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="0a9b7-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="0a9b7-110">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="0a9b7-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="0a9b7-111">成员</span><span class="sxs-lookup"><span data-stu-id="0a9b7-111">Members</span></span>

#### <span data-ttu-id="0a9b7-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="0a9b7-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="0a9b7-113">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="0a9b7-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="0a9b7-114">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="0a9b7-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

