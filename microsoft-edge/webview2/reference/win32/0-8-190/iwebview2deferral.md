---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: a1c00c29a3e063cd995c9f0eb287d870fd1211dc
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886141"
---
# <span data-ttu-id="39314-104">0.8.355-接口 IWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="39314-104">0.8.355 - interface IWebView2Deferral</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="39314-105">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="39314-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="39314-106">摘要</span><span class="sxs-lookup"><span data-stu-id="39314-106">Summary</span></span>

 <span data-ttu-id="39314-107">成员</span><span class="sxs-lookup"><span data-stu-id="39314-107">Members</span></span>                        | <span data-ttu-id="39314-108">描述</span><span class="sxs-lookup"><span data-stu-id="39314-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="39314-109">完成</span><span class="sxs-lookup"><span data-stu-id="39314-109">Complete</span></span>](#complete) | <span data-ttu-id="39314-110">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="39314-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="39314-111">成员</span><span class="sxs-lookup"><span data-stu-id="39314-111">Members</span></span>

#### <span data-ttu-id="39314-112">完成</span><span class="sxs-lookup"><span data-stu-id="39314-112">Complete</span></span> 

<span data-ttu-id="39314-113">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="39314-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="39314-114">公共 HRESULT[完成](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="39314-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="39314-115">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="39314-115">Complete should only be called once for each deferral taken.</span></span>

