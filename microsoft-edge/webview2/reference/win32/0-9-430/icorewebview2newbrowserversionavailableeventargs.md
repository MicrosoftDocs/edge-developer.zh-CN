---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 3ac37f7d90fc03214381b991c8becae602bac738
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653041"
---
# <span data-ttu-id="94573-104">interface ICoreWebView2NewBrowserVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="94573-104">interface ICoreWebView2NewBrowserVersionAvailableEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="94573-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="94573-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="94573-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="94573-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="94573-107">NewBrowserVersionAvailable 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="94573-107">Event args for the NewBrowserVersionAvailable event.</span></span>

## <span data-ttu-id="94573-108">摘要</span><span class="sxs-lookup"><span data-stu-id="94573-108">Summary</span></span>

 <span data-ttu-id="94573-109">成员</span><span class="sxs-lookup"><span data-stu-id="94573-109">Members</span></span>                        | <span data-ttu-id="94573-110">描述</span><span class="sxs-lookup"><span data-stu-id="94573-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="94573-111">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="94573-111">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="94573-112">当前[ICoreWebView2Environment](ICoreWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="94573-112">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

## <span data-ttu-id="94573-113">成员</span><span class="sxs-lookup"><span data-stu-id="94573-113">Members</span></span>

#### <span data-ttu-id="94573-114">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="94573-114">get_NewVersion</span></span> 

<span data-ttu-id="94573-115">当前[ICoreWebView2Environment](ICoreWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="94573-115">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

> <span data-ttu-id="94573-116">公共 HRESULT [get_NewVersion](#get_newversion)（LPWSTR \* 新版）</span><span class="sxs-lookup"><span data-stu-id="94573-116">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

