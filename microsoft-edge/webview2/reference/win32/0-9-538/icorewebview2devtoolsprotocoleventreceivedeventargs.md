---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2DevToolsProtocolEventReceivedEventArgs
ms.openlocfilehash: 79af7b28b8b8ab7e2e2b6612f121208b8d917725
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010267"
---
# <span data-ttu-id="2cd0b-104">0.9.579-接口 ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="2cd0b-104">0.9.579 - interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="2cd0b-105">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2cd0b-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="2cd0b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2cd0b-106">Summary</span></span>

 <span data-ttu-id="2cd0b-107">成员</span><span class="sxs-lookup"><span data-stu-id="2cd0b-107">Members</span></span>                        | <span data-ttu-id="2cd0b-108">描述</span><span class="sxs-lookup"><span data-stu-id="2cd0b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2cd0b-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="2cd0b-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="2cd0b-110">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="2cd0b-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="2cd0b-111">成员</span><span class="sxs-lookup"><span data-stu-id="2cd0b-111">Members</span></span>

#### <span data-ttu-id="2cd0b-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="2cd0b-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="2cd0b-113">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="2cd0b-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="2cd0b-114">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson) (LPWSTR \* ParameterObjectAsJson) </span><span class="sxs-lookup"><span data-stu-id="2cd0b-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

