---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NewVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 3a9af31477e7b4155bece55ec2faef85efccbd0d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884979"
---
# <span data-ttu-id="aff16-104">0.8.355-接口 IWebView2NewVersionAvailableEventHandler</span><span class="sxs-lookup"><span data-stu-id="aff16-104">0.8.355 - interface IWebView2NewVersionAvailableEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewVersionAvailableEventHandler
  : public IUnknown
```

<span data-ttu-id="aff16-105">调用方实现此接口以接收 NewVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="aff16-105">The caller implements this interface to receive NewVersionAvailable events.</span></span>

## <span data-ttu-id="aff16-106">摘要</span><span class="sxs-lookup"><span data-stu-id="aff16-106">Summary</span></span>

 <span data-ttu-id="aff16-107">成员</span><span class="sxs-lookup"><span data-stu-id="aff16-107">Members</span></span>                        | <span data-ttu-id="aff16-108">描述</span><span class="sxs-lookup"><span data-stu-id="aff16-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aff16-109">调用</span><span class="sxs-lookup"><span data-stu-id="aff16-109">Invoke</span></span>](#invoke) | <span data-ttu-id="aff16-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="aff16-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="aff16-111">使用[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md)的 get_NewVersion 方法获取新的版本号。</span><span class="sxs-lookup"><span data-stu-id="aff16-111">Use the get_NewVersion method of [IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) to get the new version number.</span></span>

## <span data-ttu-id="aff16-112">成员</span><span class="sxs-lookup"><span data-stu-id="aff16-112">Members</span></span>

#### <span data-ttu-id="aff16-113">调用</span><span class="sxs-lookup"><span data-stu-id="aff16-113">Invoke</span></span> 

<span data-ttu-id="aff16-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="aff16-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="aff16-115">public HRESULT [Invoke](#invoke)（[IWebView2Environment](IWebView2Environment.md) \* webviewEnvironment，[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="aff16-115">public HRESULT [Invoke](#invoke)([IWebView2Environment](IWebView2Environment.md) \* webviewEnvironment,[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) \* args)</span></span>

