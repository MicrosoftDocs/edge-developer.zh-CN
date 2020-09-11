---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ContentLoadingEventArgs
ms.openlocfilehash: d70673714e3641e19f5c3d6367278c0c7bd2729b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010297"
---
# <span data-ttu-id="f1054-104">0.9.579-接口 ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="f1054-104">0.9.579 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="f1054-105">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f1054-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="f1054-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f1054-106">Summary</span></span>

 <span data-ttu-id="f1054-107">成员</span><span class="sxs-lookup"><span data-stu-id="f1054-107">Members</span></span>                        | <span data-ttu-id="f1054-108">描述</span><span class="sxs-lookup"><span data-stu-id="f1054-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f1054-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f1054-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="f1054-110">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f1054-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="f1054-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="f1054-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="f1054-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="f1054-112">The ID of the navigation.</span></span>

## <span data-ttu-id="f1054-113">成员</span><span class="sxs-lookup"><span data-stu-id="f1054-113">Members</span></span>

#### <span data-ttu-id="f1054-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f1054-114">get_IsErrorPage</span></span> 

<span data-ttu-id="f1054-115">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f1054-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="f1054-116">公共 HRESULT [get_IsErrorPage](#get_iserrorpage) (BOOL \* IsErrorPage) </span><span class="sxs-lookup"><span data-stu-id="f1054-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="f1054-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="f1054-117">get_NavigationId</span></span> 

<span data-ttu-id="f1054-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="f1054-118">The ID of the navigation.</span></span>

> <span data-ttu-id="f1054-119">公共 HRESULT [get_NavigationId](#get_navigationid) (UINT64 \* navigation_id) </span><span class="sxs-lookup"><span data-stu-id="f1054-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

