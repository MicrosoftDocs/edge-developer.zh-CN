---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 6e2925583c4c3e9d207768c880c014ab1db23f7a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885126"
---
# <span data-ttu-id="f9d9f-104">0.9.515-WebView2 的 CoreWebView2ContentLoadingEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="f9d9f-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="f9d9f-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="f9d9f-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f9d9f-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f9d9f-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f9d9f-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f9d9f-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="f9d9f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f9d9f-108">Summary</span></span>

 <span data-ttu-id="f9d9f-109">成员</span><span class="sxs-lookup"><span data-stu-id="f9d9f-109">Members</span></span>                        | <span data-ttu-id="f9d9f-110">描述</span><span class="sxs-lookup"><span data-stu-id="f9d9f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f9d9f-111">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f9d9f-111">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="f9d9f-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f9d9f-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="f9d9f-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="f9d9f-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="f9d9f-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="f9d9f-114">The ID of the navigation.</span></span>

## <span data-ttu-id="f9d9f-115">成员</span><span class="sxs-lookup"><span data-stu-id="f9d9f-115">Members</span></span>

#### <span data-ttu-id="f9d9f-116">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f9d9f-116">IsErrorPage</span></span> 

<span data-ttu-id="f9d9f-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="f9d9f-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="f9d9f-118">公共 bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="f9d9f-118">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="f9d9f-119">NavigationId</span><span class="sxs-lookup"><span data-stu-id="f9d9f-119">NavigationId</span></span> 

<span data-ttu-id="f9d9f-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="f9d9f-120">The ID of the navigation.</span></span>

> <span data-ttu-id="f9d9f-121">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="f9d9f-121">public ulong [NavigationId](#navigationid)</span></span>

