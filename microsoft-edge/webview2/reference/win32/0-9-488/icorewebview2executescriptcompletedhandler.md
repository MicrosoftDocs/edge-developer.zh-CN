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
ms.openlocfilehash: da7b12d382776bb1755e90b0ce1c2728b555c8c8
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653112"
---
# <span data-ttu-id="064d6-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="064d6-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="064d6-105">调用方实现此接口以接收 ExecuteScript 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="064d6-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="064d6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="064d6-106">Summary</span></span>

 <span data-ttu-id="064d6-107">成员</span><span class="sxs-lookup"><span data-stu-id="064d6-107">Members</span></span>                        | <span data-ttu-id="064d6-108">描述</span><span class="sxs-lookup"><span data-stu-id="064d6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="064d6-109">调用</span><span class="sxs-lookup"><span data-stu-id="064d6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="064d6-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="064d6-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="064d6-111">成员</span><span class="sxs-lookup"><span data-stu-id="064d6-111">Members</span></span>

#### <span data-ttu-id="064d6-112">调用</span><span class="sxs-lookup"><span data-stu-id="064d6-112">Invoke</span></span> 

<span data-ttu-id="064d6-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="064d6-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="064d6-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR resultObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="064d6-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

