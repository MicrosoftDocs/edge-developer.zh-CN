---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ExecuteScriptCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 9a075cf5e5d3e5222e76b9ba7550636a67e5696a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886008"
---
# <span data-ttu-id="f4270-104">0.8.355-接口 IWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f4270-104">0.8.355 - interface IWebView2ExecuteScriptCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f4270-105">调用方实现此接口以接收 ExecuteScript 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="f4270-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="f4270-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f4270-106">Summary</span></span>

 <span data-ttu-id="f4270-107">成员</span><span class="sxs-lookup"><span data-stu-id="f4270-107">Members</span></span>                        | <span data-ttu-id="f4270-108">描述</span><span class="sxs-lookup"><span data-stu-id="f4270-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f4270-109">调用</span><span class="sxs-lookup"><span data-stu-id="f4270-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f4270-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f4270-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f4270-111">成员</span><span class="sxs-lookup"><span data-stu-id="f4270-111">Members</span></span>

#### <span data-ttu-id="f4270-112">调用</span><span class="sxs-lookup"><span data-stu-id="f4270-112">Invoke</span></span> 

<span data-ttu-id="f4270-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f4270-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f4270-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR resultObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="f4270-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR resultObjectAsJson)</span></span>

