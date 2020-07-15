---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2PermissionRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: d8703ee6bd985d276688901534dadd836aa6c7fc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877782"
---
# <span data-ttu-id="d45ff-104">0.9.430-接口 ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d45ff-104">0.9.430 - interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="d45ff-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d45ff-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="d45ff-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d45ff-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="d45ff-107">调用方实现此接口以接收 Webview.permissionrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="d45ff-107">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="d45ff-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d45ff-108">Summary</span></span>

 <span data-ttu-id="d45ff-109">成员</span><span class="sxs-lookup"><span data-stu-id="d45ff-109">Members</span></span>                        | <span data-ttu-id="d45ff-110">描述</span><span class="sxs-lookup"><span data-stu-id="d45ff-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d45ff-111">调用</span><span class="sxs-lookup"><span data-stu-id="d45ff-111">Invoke</span></span>](#invoke) | <span data-ttu-id="d45ff-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d45ff-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d45ff-113">成员</span><span class="sxs-lookup"><span data-stu-id="d45ff-113">Members</span></span>

#### <span data-ttu-id="d45ff-114">调用</span><span class="sxs-lookup"><span data-stu-id="d45ff-114">Invoke</span></span> 

<span data-ttu-id="d45ff-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d45ff-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d45ff-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2PermissionRequestedEventArgs](ICoreWebView2PermissionRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="d45ff-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2PermissionRequestedEventArgs](ICoreWebView2PermissionRequestedEventArgs.md) \* args)</span></span>

