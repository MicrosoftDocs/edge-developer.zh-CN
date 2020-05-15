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
ms.openlocfilehash: fda3ab31405a7d6353af1a670a2804e973577c8e
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653010"
---
# <span data-ttu-id="9aa34-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="9aa34-104">interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="9aa34-105">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="9aa34-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="9aa34-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9aa34-106">Summary</span></span>

 <span data-ttu-id="9aa34-107">成员</span><span class="sxs-lookup"><span data-stu-id="9aa34-107">Members</span></span>                        | <span data-ttu-id="9aa34-108">描述</span><span class="sxs-lookup"><span data-stu-id="9aa34-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9aa34-109">调用</span><span class="sxs-lookup"><span data-stu-id="9aa34-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9aa34-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="9aa34-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="9aa34-111">成员</span><span class="sxs-lookup"><span data-stu-id="9aa34-111">Members</span></span>

#### <span data-ttu-id="9aa34-112">调用</span><span class="sxs-lookup"><span data-stu-id="9aa34-112">Invoke</span></span> 

<span data-ttu-id="9aa34-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="9aa34-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="9aa34-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="9aa34-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR returnObjectAsJson)</span></span>

