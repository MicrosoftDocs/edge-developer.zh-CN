---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2PermissionRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: aeb6e2e25ca9f8c454f5dff891f2c488591d2a48
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884930"
---
# <span data-ttu-id="d55f6-104">0.8.355-接口 IWebView2PermissionRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d55f6-104">0.8.355 - interface IWebView2PermissionRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2PermissionRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="d55f6-105">调用方实现此接口以接收 Webview.permissionrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="d55f6-105">The caller implements this interface to receive the PermissionRequested event.</span></span>

## <span data-ttu-id="d55f6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d55f6-106">Summary</span></span>

 <span data-ttu-id="d55f6-107">成员</span><span class="sxs-lookup"><span data-stu-id="d55f6-107">Members</span></span>                        | <span data-ttu-id="d55f6-108">描述</span><span class="sxs-lookup"><span data-stu-id="d55f6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d55f6-109">调用</span><span class="sxs-lookup"><span data-stu-id="d55f6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d55f6-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d55f6-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d55f6-111">成员</span><span class="sxs-lookup"><span data-stu-id="d55f6-111">Members</span></span>

#### <span data-ttu-id="d55f6-112">调用</span><span class="sxs-lookup"><span data-stu-id="d55f6-112">Invoke</span></span> 

<span data-ttu-id="d55f6-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d55f6-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d55f6-114">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2PermissionRequestedEventArgs](IWebView2PermissionRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="d55f6-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2PermissionRequestedEventArgs](IWebView2PermissionRequestedEventArgs.md) \* args)</span></span>

