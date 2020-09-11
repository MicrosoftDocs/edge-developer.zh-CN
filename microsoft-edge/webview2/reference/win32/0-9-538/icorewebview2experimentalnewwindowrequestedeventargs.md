---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalNewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalNewWindowRequestedEventArgs
ms.openlocfilehash: 855425e5cbdd594c7a4bca12efe1827035ca2f3a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011102"
---
# <span data-ttu-id="3e066-104">0.9.579-接口 ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="3e066-104">0.9.579 - interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="3e066-105">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3e066-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="3e066-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3e066-106">Summary</span></span>

 <span data-ttu-id="3e066-107">成员</span><span class="sxs-lookup"><span data-stu-id="3e066-107">Members</span></span>                        | <span data-ttu-id="3e066-108">描述</span><span class="sxs-lookup"><span data-stu-id="3e066-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e066-109">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="3e066-109">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="3e066-110">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="3e066-110">Window features specified by the window.open call.</span></span>

<span data-ttu-id="3e066-111">当 web 浏览中请求打开一个新窗口 (通过 window 打开一个新窗口时，将引发此事件。 ) 打开 ( # A2 的内容。</span><span class="sxs-lookup"><span data-stu-id="3e066-111">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="3e066-112">成员</span><span class="sxs-lookup"><span data-stu-id="3e066-112">Members</span></span>

#### <span data-ttu-id="3e066-113">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="3e066-113">get_WindowFeatures</span></span> 

<span data-ttu-id="3e066-114">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="3e066-114">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="3e066-115">公共 HRESULT [get_WindowFeatures](#get_windowfeatures) ([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \* \* WindowFeatures) </span><span class="sxs-lookup"><span data-stu-id="3e066-115">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="3e066-116">可将这些功能考虑到新的 web 视图窗口的位置和大小调整。</span><span class="sxs-lookup"><span data-stu-id="3e066-116">These features can be considered for positioning and sizing of new webview windows.</span></span>

