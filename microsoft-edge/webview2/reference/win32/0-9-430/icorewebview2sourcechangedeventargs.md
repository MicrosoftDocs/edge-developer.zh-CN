---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 2eb2749b71cd9be9dfd25bb686b4ea57e728f179
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883979"
---
# <span data-ttu-id="d30cc-104">0.9.430-接口 ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d30cc-104">0.9.430 - interface ICoreWebView2SourceChangedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="d30cc-105">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d30cc-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="d30cc-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d30cc-106">Summary</span></span>

 <span data-ttu-id="d30cc-107">成员</span><span class="sxs-lookup"><span data-stu-id="d30cc-107">Members</span></span>                        | <span data-ttu-id="d30cc-108">描述</span><span class="sxs-lookup"><span data-stu-id="d30cc-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d30cc-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="d30cc-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="d30cc-110">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="d30cc-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="d30cc-111">成员</span><span class="sxs-lookup"><span data-stu-id="d30cc-111">Members</span></span>

#### <span data-ttu-id="d30cc-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="d30cc-112">get_IsNewDocument</span></span> 

<span data-ttu-id="d30cc-113">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="d30cc-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="d30cc-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="d30cc-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

