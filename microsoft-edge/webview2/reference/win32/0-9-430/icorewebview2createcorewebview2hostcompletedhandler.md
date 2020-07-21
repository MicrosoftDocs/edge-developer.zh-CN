---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2HostCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 9c2b5568e6a276b07dc91bd639c730b2009aa9e5
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884279"
---
# <span data-ttu-id="cf897-104">0.9.430-接口 ICoreWebView2CreateCoreWebView2HostCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="cf897-104">0.9.430 - interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2HostCompletedHandler
  : public IUnknown
```

<span data-ttu-id="cf897-105">调用方实现此接口以接收通过 CreateCoreWebView2Host 创建的 CoreWebView2Host。</span><span class="sxs-lookup"><span data-stu-id="cf897-105">The caller implements this interface to receive the CoreWebView2Host created via CreateCoreWebView2Host.</span></span>

## <span data-ttu-id="cf897-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cf897-106">Summary</span></span>

 <span data-ttu-id="cf897-107">成员</span><span class="sxs-lookup"><span data-stu-id="cf897-107">Members</span></span>                        | <span data-ttu-id="cf897-108">描述</span><span class="sxs-lookup"><span data-stu-id="cf897-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cf897-109">调用</span><span class="sxs-lookup"><span data-stu-id="cf897-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cf897-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="cf897-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="cf897-111">成员</span><span class="sxs-lookup"><span data-stu-id="cf897-111">Members</span></span>

#### <span data-ttu-id="cf897-112">调用</span><span class="sxs-lookup"><span data-stu-id="cf897-112">Invoke</span></span> 

<span data-ttu-id="cf897-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="cf897-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="cf897-114">公共 HRESULT[调用](#invoke)（hresult 结果，[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host）</span><span class="sxs-lookup"><span data-stu-id="cf897-114">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span></span>

