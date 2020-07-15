---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalNewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalNewWindowRequestedEventArgs
ms.openlocfilehash: 39d52b1231e767739b63b3759cdd08e4c9b26be3
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879987"
---
# <span data-ttu-id="27fe2-104">interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="27fe2-104">interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="27fe2-105">这是使用预发行 SDK 版本0.9.538 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="27fe2-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="27fe2-106">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="27fe2-106">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="27fe2-107">摘要</span><span class="sxs-lookup"><span data-stu-id="27fe2-107">Summary</span></span>

 <span data-ttu-id="27fe2-108">成员</span><span class="sxs-lookup"><span data-stu-id="27fe2-108">Members</span></span>                        | <span data-ttu-id="27fe2-109">描述</span><span class="sxs-lookup"><span data-stu-id="27fe2-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="27fe2-110">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="27fe2-110">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="27fe2-111">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="27fe2-111">Window features specified by the window.open call.</span></span>

<span data-ttu-id="27fe2-112">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="27fe2-112">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="27fe2-113">成员</span><span class="sxs-lookup"><span data-stu-id="27fe2-113">Members</span></span>

#### <span data-ttu-id="27fe2-114">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="27fe2-114">get_WindowFeatures</span></span> 

<span data-ttu-id="27fe2-115">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="27fe2-115">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="27fe2-116">公共 HRESULT [get_WindowFeatures](#get_windowfeatures)（[ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \* \* WindowFeatures）</span><span class="sxs-lookup"><span data-stu-id="27fe2-116">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="27fe2-117">可将这些功能考虑到新的 web 视图窗口的位置和大小调整。</span><span class="sxs-lookup"><span data-stu-id="27fe2-117">These features can be considered for positioning and sizing of new webview windows.</span></span>

