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
ms.openlocfilehash: e7fbc952a44bdd38e6e59c46adafb8e71b7904b6
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653075"
---
# <span data-ttu-id="e0983-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e0983-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="e0983-105">DevToolsProtocolEventReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e0983-105">Event args for the DevToolsProtocolEventReceived event.</span></span>

## <span data-ttu-id="e0983-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e0983-106">Summary</span></span>

 <span data-ttu-id="e0983-107">成员</span><span class="sxs-lookup"><span data-stu-id="e0983-107">Members</span></span>                        | <span data-ttu-id="e0983-108">描述</span><span class="sxs-lookup"><span data-stu-id="e0983-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e0983-109">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="e0983-109">get_ParameterObjectAsJson</span></span>](#get_parameterobjectasjson) | <span data-ttu-id="e0983-110">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="e0983-110">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

## <span data-ttu-id="e0983-111">成员</span><span class="sxs-lookup"><span data-stu-id="e0983-111">Members</span></span>

#### <span data-ttu-id="e0983-112">get_ParameterObjectAsJson</span><span class="sxs-lookup"><span data-stu-id="e0983-112">get_ParameterObjectAsJson</span></span> 

<span data-ttu-id="e0983-113">以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。</span><span class="sxs-lookup"><span data-stu-id="e0983-113">The parameter object of the corresponding DevToolsProtocol event represented as a JSON string.</span></span>

> <span data-ttu-id="e0983-114">公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR \* ParameterObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="e0983-114">public HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR \* parameterObjectAsJson)</span></span>

