---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 6fbcc82409791bc3d2da3bb2f7985732cb344a97
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880624"
---
# <span data-ttu-id="a13e8-104">0.9.515-接口 ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a13e8-104">0.9.515 - interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a13e8-105">这是使用预发行 SDK 版本0.9.488 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="a13e8-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a13e8-106">调用方实现此接口以接收 CursorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="a13e8-106">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="a13e8-107">摘要</span><span class="sxs-lookup"><span data-stu-id="a13e8-107">Summary</span></span>

 <span data-ttu-id="a13e8-108">成员</span><span class="sxs-lookup"><span data-stu-id="a13e8-108">Members</span></span>                        | <span data-ttu-id="a13e8-109">描述</span><span class="sxs-lookup"><span data-stu-id="a13e8-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a13e8-110">调用</span><span class="sxs-lookup"><span data-stu-id="a13e8-110">Invoke</span></span>](#invoke) | <span data-ttu-id="a13e8-111">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a13e8-111">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a13e8-112">使用 Cursor 属性获取新光标。</span><span class="sxs-lookup"><span data-stu-id="a13e8-112">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="a13e8-113">成员</span><span class="sxs-lookup"><span data-stu-id="a13e8-113">Members</span></span>

#### <span data-ttu-id="a13e8-114">调用</span><span class="sxs-lookup"><span data-stu-id="a13e8-114">Invoke</span></span> 

<span data-ttu-id="a13e8-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a13e8-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a13e8-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="a13e8-116">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="a13e8-117">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="a13e8-117">There are no event args and the args parameter will be null.</span></span>

