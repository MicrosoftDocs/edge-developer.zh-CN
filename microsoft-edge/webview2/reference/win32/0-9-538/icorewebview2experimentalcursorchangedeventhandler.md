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
ms.openlocfilehash: b44bd47f5352179abcc06ef5fd5b8f613bde455e
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698457"
---
# <span data-ttu-id="cd548-104">interface ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="cd548-104">interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="cd548-105">这是使用预发行 SDK 版本0.9.538 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="cd548-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="cd548-106">调用方实现此接口以接收 CursorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="cd548-106">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="cd548-107">摘要</span><span class="sxs-lookup"><span data-stu-id="cd548-107">Summary</span></span>

 <span data-ttu-id="cd548-108">成员</span><span class="sxs-lookup"><span data-stu-id="cd548-108">Members</span></span>                        | <span data-ttu-id="cd548-109">描述</span><span class="sxs-lookup"><span data-stu-id="cd548-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cd548-110">调用</span><span class="sxs-lookup"><span data-stu-id="cd548-110">Invoke</span></span>](#invoke) | <span data-ttu-id="cd548-111">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="cd548-111">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="cd548-112">使用 Cursor 属性获取新光标。</span><span class="sxs-lookup"><span data-stu-id="cd548-112">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="cd548-113">成员</span><span class="sxs-lookup"><span data-stu-id="cd548-113">Members</span></span>

#### <span data-ttu-id="cd548-114">调用</span><span class="sxs-lookup"><span data-stu-id="cd548-114">Invoke</span></span> 

<span data-ttu-id="cd548-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="cd548-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="cd548-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="cd548-116">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="cd548-117">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="cd548-117">There are no event args and the args parameter will be null.</span></span>

