---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2PermissionRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2PermissionRequestedEventHandler
ms.openlocfilehash: 549c7bf780535a889529aa8f7e87a097cae88c3a
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879420"
---
# <span data-ttu-id="59ed5-104">interface ICoreWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="59ed5-104">interface ICoreWebView2PermissionRequestedEventHandler</span></span> 

```
interface ICoreWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="59ed5-105">调用方实现此接口以接收 Webview.permissionrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="59ed5-105">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="59ed5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="59ed5-106">Summary</span></span>

 <span data-ttu-id="59ed5-107">成员</span><span class="sxs-lookup"><span data-stu-id="59ed5-107">Members</span></span>                        | <span data-ttu-id="59ed5-108">描述</span><span class="sxs-lookup"><span data-stu-id="59ed5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="59ed5-109">调用</span><span class="sxs-lookup"><span data-stu-id="59ed5-109">Invoke</span></span>](#invoke) | <span data-ttu-id="59ed5-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="59ed5-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="59ed5-111">成员</span><span class="sxs-lookup"><span data-stu-id="59ed5-111">Members</span></span>

#### <span data-ttu-id="59ed5-112">调用</span><span class="sxs-lookup"><span data-stu-id="59ed5-112">Invoke</span></span> 

<span data-ttu-id="59ed5-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="59ed5-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="59ed5-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="59ed5-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2PermissionRequestedEventArgs](icorewebview2permissionrequestedeventargs.md) \* args)</span></span>

