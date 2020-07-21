---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 31fea451b377b86eda0055a1074706ea12d9538e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884020"
---
# <span data-ttu-id="25de6-104">0.9.430-接口 ICoreWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="25de6-104">0.9.430 - interface ICoreWebView2ScriptDialogOpeningEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="25de6-105">调用方实现此接口以接收 ScriptDialogOpening 事件。</span><span class="sxs-lookup"><span data-stu-id="25de6-105">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="25de6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="25de6-106">Summary</span></span>

 <span data-ttu-id="25de6-107">成员</span><span class="sxs-lookup"><span data-stu-id="25de6-107">Members</span></span>                        | <span data-ttu-id="25de6-108">描述</span><span class="sxs-lookup"><span data-stu-id="25de6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="25de6-109">调用</span><span class="sxs-lookup"><span data-stu-id="25de6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="25de6-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="25de6-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="25de6-111">成员</span><span class="sxs-lookup"><span data-stu-id="25de6-111">Members</span></span>

#### <span data-ttu-id="25de6-112">调用</span><span class="sxs-lookup"><span data-stu-id="25de6-112">Invoke</span></span> 

<span data-ttu-id="25de6-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="25de6-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="25de6-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2ScriptDialogOpeningEventArgs](ICoreWebView2ScriptDialogOpeningEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="25de6-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ScriptDialogOpeningEventArgs](ICoreWebView2ScriptDialogOpeningEventArgs.md) \* args)</span></span>

