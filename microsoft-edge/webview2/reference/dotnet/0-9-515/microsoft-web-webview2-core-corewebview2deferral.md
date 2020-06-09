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
ms.openlocfilehash: bf198781d67761e9d6c29ee9c6a274462e92a61d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697670"
---
# <span data-ttu-id="32941-104">CoreWebView2Deferral 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="32941-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

> [!NOTE]
> <span data-ttu-id="32941-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="32941-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="32941-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="32941-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="32941-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="32941-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="32941-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="32941-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="32941-109">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="32941-109">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="32941-110">摘要</span><span class="sxs-lookup"><span data-stu-id="32941-110">Summary</span></span>

 <span data-ttu-id="32941-111">成员</span><span class="sxs-lookup"><span data-stu-id="32941-111">Members</span></span>                        | <span data-ttu-id="32941-112">描述</span><span class="sxs-lookup"><span data-stu-id="32941-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="32941-113">完成</span><span class="sxs-lookup"><span data-stu-id="32941-113">Complete</span></span>](#complete) | <span data-ttu-id="32941-114">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="32941-114">Completes the associated deferred event.</span></span>

## <span data-ttu-id="32941-115">成员</span><span class="sxs-lookup"><span data-stu-id="32941-115">Members</span></span>

#### <span data-ttu-id="32941-116">完成</span><span class="sxs-lookup"><span data-stu-id="32941-116">Complete</span></span> 

<span data-ttu-id="32941-117">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="32941-117">Completes the associated deferred event.</span></span>

> <span data-ttu-id="32941-118">公共失效[完整](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="32941-118">public void [Complete](#complete)()</span></span>

<span data-ttu-id="32941-119">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="32941-119">Complete should only be called once for each deferral taken.</span></span>

