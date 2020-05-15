---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 69c569be7e712d0f5cfddbaa180419be8d475ad0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653189"
---
# <span data-ttu-id="19c92-104">interface ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="19c92-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="19c92-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="19c92-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="19c92-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="19c92-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="19c92-107">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="19c92-107">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="19c92-108">摘要</span><span class="sxs-lookup"><span data-stu-id="19c92-108">Summary</span></span>

 <span data-ttu-id="19c92-109">成员</span><span class="sxs-lookup"><span data-stu-id="19c92-109">Members</span></span>                        | <span data-ttu-id="19c92-110">描述</span><span class="sxs-lookup"><span data-stu-id="19c92-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="19c92-111">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="19c92-111">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="19c92-112">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="19c92-112">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="19c92-113">成员</span><span class="sxs-lookup"><span data-stu-id="19c92-113">Members</span></span>

#### <span data-ttu-id="19c92-114">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="19c92-114">get_IsNewDocument</span></span> 

<span data-ttu-id="19c92-115">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="19c92-115">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="19c92-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="19c92-116">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

