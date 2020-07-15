---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2DevToolsProtocolEventReceivedEventArgs
ms.openlocfilehash: de10adbfe7e74a1679aa8b77cb96775561d87a17
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880127"
---
# <span data-ttu-id="24395-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="24395-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="24395-105">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="24395-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="24395-106">摘要</span><span class="sxs-lookup"><span data-stu-id="24395-106">Summary</span></span>

 <span data-ttu-id="24395-107">成员</span><span class="sxs-lookup"><span data-stu-id="24395-107">Members</span></span>                        | <span data-ttu-id="24395-108">描述</span><span class="sxs-lookup"><span data-stu-id="24395-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="24395-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="24395-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="24395-110">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="24395-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="24395-111">成员</span><span class="sxs-lookup"><span data-stu-id="24395-111">Members</span></span>

#### <span data-ttu-id="24395-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="24395-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="24395-113">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="24395-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="24395-114">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="24395-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

