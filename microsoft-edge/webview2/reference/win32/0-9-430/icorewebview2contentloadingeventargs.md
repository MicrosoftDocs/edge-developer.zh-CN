---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7bccd93aeec2c5cfbc181ce5ab1cf58e29da48ce
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884293"
---
# <span data-ttu-id="e4888-104">0.9.430-接口 ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="e4888-104">0.9.430 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="e4888-105">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e4888-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="e4888-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e4888-106">Summary</span></span>

 <span data-ttu-id="e4888-107">成员</span><span class="sxs-lookup"><span data-stu-id="e4888-107">Members</span></span>                        | <span data-ttu-id="e4888-108">描述</span><span class="sxs-lookup"><span data-stu-id="e4888-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e4888-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="e4888-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="e4888-110">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e4888-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="e4888-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="e4888-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="e4888-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="e4888-112">The ID of the navigation.</span></span>

## <span data-ttu-id="e4888-113">成员</span><span class="sxs-lookup"><span data-stu-id="e4888-113">Members</span></span>

#### <span data-ttu-id="e4888-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="e4888-114">get_IsErrorPage</span></span> 

<span data-ttu-id="e4888-115">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e4888-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="e4888-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="e4888-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="e4888-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="e4888-117">get_NavigationId</span></span> 

<span data-ttu-id="e4888-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="e4888-118">The ID of the navigation.</span></span>

> <span data-ttu-id="e4888-119">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="e4888-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

