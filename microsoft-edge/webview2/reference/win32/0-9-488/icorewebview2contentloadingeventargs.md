---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 32b0f46b00195a265238541f8715ec21ca3757a1
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883873"
---
# <span data-ttu-id="51a71-104">0.9.515-接口 ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="51a71-104">0.9.515 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="51a71-105">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="51a71-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="51a71-106">摘要</span><span class="sxs-lookup"><span data-stu-id="51a71-106">Summary</span></span>

 <span data-ttu-id="51a71-107">成员</span><span class="sxs-lookup"><span data-stu-id="51a71-107">Members</span></span>                        | <span data-ttu-id="51a71-108">描述</span><span class="sxs-lookup"><span data-stu-id="51a71-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="51a71-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="51a71-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="51a71-110">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="51a71-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="51a71-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="51a71-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="51a71-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="51a71-112">The ID of the navigation.</span></span>

## <span data-ttu-id="51a71-113">成员</span><span class="sxs-lookup"><span data-stu-id="51a71-113">Members</span></span>

#### <span data-ttu-id="51a71-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="51a71-114">get_IsErrorPage</span></span> 

<span data-ttu-id="51a71-115">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="51a71-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="51a71-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL \* IsErrorPage）</span><span class="sxs-lookup"><span data-stu-id="51a71-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="51a71-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="51a71-117">get_NavigationId</span></span> 

<span data-ttu-id="51a71-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="51a71-118">The ID of the navigation.</span></span>

> <span data-ttu-id="51a71-119">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="51a71-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

