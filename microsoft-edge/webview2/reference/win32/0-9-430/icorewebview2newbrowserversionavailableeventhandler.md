---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2NewBrowserVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 04859c0a22e8571a4fe8015a089c9b7d708c1dd3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884869"
---
# <span data-ttu-id="1421e-104">0.9.430-接口 ICoreWebView2NewBrowserVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="1421e-104">0.9.430 - interface ICoreWebView2NewBrowserVersionAvailableEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="1421e-105">调用方实现此接口以接收 NewBrowserVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="1421e-105">The caller implements this interface to receive NewBrowserVersionAvailable events.</span></span>

## <span data-ttu-id="1421e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1421e-106">Summary</span></span>

 <span data-ttu-id="1421e-107">成员</span><span class="sxs-lookup"><span data-stu-id="1421e-107">Members</span></span>                        | <span data-ttu-id="1421e-108">描述</span><span class="sxs-lookup"><span data-stu-id="1421e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1421e-109">调用</span><span class="sxs-lookup"><span data-stu-id="1421e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="1421e-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1421e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="1421e-111">使用[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md)的 get_NewVersion 方法获取新的版本号。</span><span class="sxs-lookup"><span data-stu-id="1421e-111">Use the get_NewVersion method of [ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="1421e-112">成员</span><span class="sxs-lookup"><span data-stu-id="1421e-112">Members</span></span>

#### <span data-ttu-id="1421e-113">调用</span><span class="sxs-lookup"><span data-stu-id="1421e-113">Invoke</span></span> 

<span data-ttu-id="1421e-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1421e-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1421e-115">public HRESULT [Invoke](#invoke)（[ICoreWebView2Environment](ICoreWebView2Environment.md) \* webviewEnvironment，[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="1421e-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Environment](ICoreWebView2Environment.md) \* webviewEnvironment,[ICoreWebView2NewBrowserVersionAvailableEventArgs](ICoreWebView2NewBrowserVersionAvailableEventArgs.md) \* args)</span></span>

