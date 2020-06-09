---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2908ad851a7899d2ea053bfa50616c8b244bca6c
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698467"
---
# <span data-ttu-id="1d7ed-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1d7ed-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="1d7ed-105">调用方实现此接口以接收 DocumentTitleChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="1d7ed-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="1d7ed-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1d7ed-106">Summary</span></span>

 <span data-ttu-id="1d7ed-107">成员</span><span class="sxs-lookup"><span data-stu-id="1d7ed-107">Members</span></span>                        | <span data-ttu-id="1d7ed-108">描述</span><span class="sxs-lookup"><span data-stu-id="1d7ed-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1d7ed-109">调用</span><span class="sxs-lookup"><span data-stu-id="1d7ed-109">Invoke</span></span>](#invoke) | <span data-ttu-id="1d7ed-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1d7ed-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="1d7ed-111">使用 DocumentTitle 属性获取修改后的标题。</span><span class="sxs-lookup"><span data-stu-id="1d7ed-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="1d7ed-112">成员</span><span class="sxs-lookup"><span data-stu-id="1d7ed-112">Members</span></span>

#### <span data-ttu-id="1d7ed-113">调用</span><span class="sxs-lookup"><span data-stu-id="1d7ed-113">Invoke</span></span> 

<span data-ttu-id="1d7ed-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1d7ed-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1d7ed-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="1d7ed-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="1d7ed-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="1d7ed-116">There are no event args and the args parameter will be null.</span></span>

