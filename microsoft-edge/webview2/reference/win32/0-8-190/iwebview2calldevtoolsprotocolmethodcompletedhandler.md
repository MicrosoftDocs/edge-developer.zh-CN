---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CallDevToolsProtocolMethodCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: b8501c7287d5160f0fac980752721c83a0f48de7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886232"
---
# <span data-ttu-id="0b77c-104">0.8.355-接口 IWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="0b77c-104">0.8.355 - interface IWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="0b77c-105">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="0b77c-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="0b77c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0b77c-106">Summary</span></span>

 <span data-ttu-id="0b77c-107">成员</span><span class="sxs-lookup"><span data-stu-id="0b77c-107">Members</span></span>                        | <span data-ttu-id="0b77c-108">描述</span><span class="sxs-lookup"><span data-stu-id="0b77c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0b77c-109">调用</span><span class="sxs-lookup"><span data-stu-id="0b77c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="0b77c-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0b77c-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="0b77c-111">成员</span><span class="sxs-lookup"><span data-stu-id="0b77c-111">Members</span></span>

#### <span data-ttu-id="0b77c-112">调用</span><span class="sxs-lookup"><span data-stu-id="0b77c-112">Invoke</span></span> 

<span data-ttu-id="0b77c-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="0b77c-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="0b77c-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="0b77c-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR returnObjectAsJson)</span></span>

