---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Deferral 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: dcefefd37167b6ff78f2d994f84af6c707423bb4
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011708"
---
# <span data-ttu-id="0c686-104">CoreWebView2Deferral 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="0c686-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

<span data-ttu-id="0c686-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="0c686-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="0c686-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="0c686-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="0c686-107">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="0c686-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="0c686-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0c686-108">Summary</span></span>

 <span data-ttu-id="0c686-109">成员</span><span class="sxs-lookup"><span data-stu-id="0c686-109">Members</span></span>                        | <span data-ttu-id="0c686-110">描述</span><span class="sxs-lookup"><span data-stu-id="0c686-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0c686-111">完成</span><span class="sxs-lookup"><span data-stu-id="0c686-111">Complete</span></span>](#complete) | <span data-ttu-id="0c686-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="0c686-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="0c686-113">成员</span><span class="sxs-lookup"><span data-stu-id="0c686-113">Members</span></span>

#### <span data-ttu-id="0c686-114">完成</span><span class="sxs-lookup"><span data-stu-id="0c686-114">Complete</span></span> 

<span data-ttu-id="0c686-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="0c686-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="0c686-116">public void [完整](#complete) ( # A1</span><span class="sxs-lookup"><span data-stu-id="0c686-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="0c686-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="0c686-117">Complete should only be called once for each deferral taken.</span></span>

