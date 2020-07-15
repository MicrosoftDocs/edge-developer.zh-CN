---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
ms.openlocfilehash: c991e9e9520bd696c579fdca379295afe253ba5d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877510"
---
# <span data-ttu-id="47006-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="47006-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="47006-105">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="47006-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="47006-106">摘要</span><span class="sxs-lookup"><span data-stu-id="47006-106">Summary</span></span>

 <span data-ttu-id="47006-107">成员</span><span class="sxs-lookup"><span data-stu-id="47006-107">Members</span></span>                        | <span data-ttu-id="47006-108">描述</span><span class="sxs-lookup"><span data-stu-id="47006-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="47006-109">调用</span><span class="sxs-lookup"><span data-stu-id="47006-109">Invoke</span></span>](#invoke) | <span data-ttu-id="47006-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="47006-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="47006-111">成员</span><span class="sxs-lookup"><span data-stu-id="47006-111">Members</span></span>

#### <span data-ttu-id="47006-112">调用</span><span class="sxs-lookup"><span data-stu-id="47006-112">Invoke</span></span> 

<span data-ttu-id="47006-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="47006-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="47006-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="47006-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR returnObjectAsJson)</span></span>

