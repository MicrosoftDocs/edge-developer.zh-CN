---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
ms.openlocfilehash: 3ecafb8181b04032bf121a93af3771cfcad8fa91
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011165"
---
# <span data-ttu-id="9b5e8-104">0.9.579-接口 ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="9b5e8-104">0.9.579 - interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="9b5e8-105">调用方实现此接口以接收通过 CreateCoreWebView2Controller 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="9b5e8-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="9b5e8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9b5e8-106">Summary</span></span>

 <span data-ttu-id="9b5e8-107">成员</span><span class="sxs-lookup"><span data-stu-id="9b5e8-107">Members</span></span>                        | <span data-ttu-id="9b5e8-108">描述</span><span class="sxs-lookup"><span data-stu-id="9b5e8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9b5e8-109">调用</span><span class="sxs-lookup"><span data-stu-id="9b5e8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9b5e8-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="9b5e8-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="9b5e8-111">成员</span><span class="sxs-lookup"><span data-stu-id="9b5e8-111">Members</span></span>

#### <span data-ttu-id="9b5e8-112">调用</span><span class="sxs-lookup"><span data-stu-id="9b5e8-112">Invoke</span></span> 

<span data-ttu-id="9b5e8-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="9b5e8-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="9b5e8-114">公共 HRESULT [调用](#invoke) (HRESULT 结果， [ICoreWebView2Controller](icorewebview2controller.md) \* createdController) </span><span class="sxs-lookup"><span data-stu-id="9b5e8-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

