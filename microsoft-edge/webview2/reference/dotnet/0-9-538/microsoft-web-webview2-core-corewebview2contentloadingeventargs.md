---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f6d9abe2ff7f4b4bdafb9eea0842bb500e165886
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698548"
---
# <span data-ttu-id="a7134-104">CoreWebView2ContentLoadingEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a7134-104">Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

<span data-ttu-id="a7134-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a7134-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a7134-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="a7134-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a7134-107">ContentLoading 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a7134-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="a7134-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a7134-108">Summary</span></span>

 <span data-ttu-id="a7134-109">成员</span><span class="sxs-lookup"><span data-stu-id="a7134-109">Members</span></span>                        | <span data-ttu-id="a7134-110">描述</span><span class="sxs-lookup"><span data-stu-id="a7134-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a7134-111">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="a7134-111">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="a7134-112">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a7134-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="a7134-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a7134-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="a7134-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a7134-114">The ID of the navigation.</span></span>

## <span data-ttu-id="a7134-115">成员</span><span class="sxs-lookup"><span data-stu-id="a7134-115">Members</span></span>

#### <span data-ttu-id="a7134-116">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="a7134-116">IsErrorPage</span></span> 

<span data-ttu-id="a7134-117">如果加载的内容是错误页面，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a7134-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="a7134-118">公共 bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="a7134-118">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="a7134-119">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a7134-119">NavigationId</span></span> 

<span data-ttu-id="a7134-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a7134-120">The ID of the navigation.</span></span>

> <span data-ttu-id="a7134-121">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="a7134-121">public ulong [NavigationId](#navigationid)</span></span>

