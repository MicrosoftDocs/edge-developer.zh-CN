---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: fec7fd7399222d8223d1022cd1e528bc9ed0d161
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653118"
---
# <span data-ttu-id="20da9-104">CoreWebView2Deferral 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="20da9-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

<span data-ttu-id="20da9-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="20da9-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="20da9-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="20da9-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="20da9-107">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="20da9-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="20da9-108">摘要</span><span class="sxs-lookup"><span data-stu-id="20da9-108">Summary</span></span>

 <span data-ttu-id="20da9-109">成员</span><span class="sxs-lookup"><span data-stu-id="20da9-109">Members</span></span>                        | <span data-ttu-id="20da9-110">描述</span><span class="sxs-lookup"><span data-stu-id="20da9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="20da9-111">完成</span><span class="sxs-lookup"><span data-stu-id="20da9-111">Complete</span></span>](#complete) | <span data-ttu-id="20da9-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="20da9-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="20da9-113">成员</span><span class="sxs-lookup"><span data-stu-id="20da9-113">Members</span></span>

#### <span data-ttu-id="20da9-114">完成</span><span class="sxs-lookup"><span data-stu-id="20da9-114">Complete</span></span> 

<span data-ttu-id="20da9-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="20da9-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="20da9-116">公共失效[完整](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="20da9-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="20da9-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="20da9-117">Complete should only be called once for each deferral taken.</span></span>

