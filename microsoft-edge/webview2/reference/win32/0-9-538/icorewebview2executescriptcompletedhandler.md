---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExecuteScriptCompletedHandler
ms.openlocfilehash: ee59ef42852fc8f0b0529b9a3ca08e53972dee1a
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879938"
---
# <span data-ttu-id="0406d-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="0406d-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="0406d-105">调用方实现此接口以接收 ExecuteScript 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="0406d-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="0406d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0406d-106">Summary</span></span>

 <span data-ttu-id="0406d-107">成员</span><span class="sxs-lookup"><span data-stu-id="0406d-107">Members</span></span>                        | <span data-ttu-id="0406d-108">描述</span><span class="sxs-lookup"><span data-stu-id="0406d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0406d-109">调用</span><span class="sxs-lookup"><span data-stu-id="0406d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="0406d-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0406d-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="0406d-111">成员</span><span class="sxs-lookup"><span data-stu-id="0406d-111">Members</span></span>

#### <span data-ttu-id="0406d-112">调用</span><span class="sxs-lookup"><span data-stu-id="0406d-112">Invoke</span></span> 

<span data-ttu-id="0406d-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0406d-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="0406d-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR resultObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="0406d-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

