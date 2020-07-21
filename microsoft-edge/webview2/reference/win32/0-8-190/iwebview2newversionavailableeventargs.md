---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NewVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 4271cc1002de70db2803a5bd6d4be73748bf5bbb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885868"
---
# <span data-ttu-id="9b253-104">0.8.355-接口 IWebView2NewVersionAvailableEventArgs</span><span class="sxs-lookup"><span data-stu-id="9b253-104">0.8.355 - interface IWebView2NewVersionAvailableEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewVersionAvailableEventArgs
  : public IUnknown
```

<span data-ttu-id="9b253-105">NewVersionAvailable 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9b253-105">Event args for the NewVersionAvailable event.</span></span>

## <span data-ttu-id="9b253-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9b253-106">Summary</span></span>

 <span data-ttu-id="9b253-107">成员</span><span class="sxs-lookup"><span data-stu-id="9b253-107">Members</span></span>                        | <span data-ttu-id="9b253-108">描述</span><span class="sxs-lookup"><span data-stu-id="9b253-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9b253-109">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="9b253-109">get_NewVersion</span></span>](#get_newversion) | <span data-ttu-id="9b253-110">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="9b253-110">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="9b253-111">成员</span><span class="sxs-lookup"><span data-stu-id="9b253-111">Members</span></span>

#### <span data-ttu-id="9b253-112">get_NewVersion</span><span class="sxs-lookup"><span data-stu-id="9b253-112">get_NewVersion</span></span> 

<span data-ttu-id="9b253-113">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="9b253-113">The browser version info of the current [IWebView2Environment](IWebView2Environment.md).</span></span>

> <span data-ttu-id="9b253-114">公共 HRESULT [get_NewVersion](#get_newversion)（LPWSTR \* 新版）</span><span class="sxs-lookup"><span data-stu-id="9b253-114">public HRESULT [get_NewVersion](#get_newversion)(LPWSTR \* newVersion)</span></span>

