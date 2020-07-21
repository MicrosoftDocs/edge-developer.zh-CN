---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2NewBrowserVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 9f56ba33534c76cb1bd60c01a88eedfced45f1fb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884860"
---
# <span data-ttu-id="72548-104">0.9.430-接口 ICoreWebView2NewBrowserVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="72548-104">0.9.430 - interface ICoreWebView2NewBrowserVersionAvailableEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="72548-105">NewBrowserVersionAvailable 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="72548-105">Event args for the NewBrowserVersionAvailable event.</span></span>

## <span data-ttu-id="72548-106">摘要</span><span class="sxs-lookup"><span data-stu-id="72548-106">Summary</span></span>

 <span data-ttu-id="72548-107">成员</span><span class="sxs-lookup"><span data-stu-id="72548-107">Members</span></span>                        | <span data-ttu-id="72548-108">描述</span><span class="sxs-lookup"><span data-stu-id="72548-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="72548-109">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="72548-109">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="72548-110">当前[ICoreWebView2Environment](ICoreWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="72548-110">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

## <span data-ttu-id="72548-111">成员</span><span class="sxs-lookup"><span data-stu-id="72548-111">Members</span></span>

#### <span data-ttu-id="72548-112">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="72548-112">get_NewVersion</span></span> 

<span data-ttu-id="72548-113">当前[ICoreWebView2Environment](ICoreWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="72548-113">The browser version info of the current [ICoreWebView2Environment](ICoreWebView2Environment.md).</span></span>

> <span data-ttu-id="72548-114">公共 HRESULT [get_NewVersion](#get_newversion)（LPWSTR \* 新版）</span><span class="sxs-lookup"><span data-stu-id="72548-114">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

