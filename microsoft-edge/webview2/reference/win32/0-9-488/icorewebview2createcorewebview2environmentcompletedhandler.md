---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: da49c1762ad7b7f3f366754bb9b05b7d16b861b7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653077"
---
# <span data-ttu-id="981a0-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="981a0-104">interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="981a0-105">调用方实现此接口以接收通过 CreateCoreWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="981a0-105">The caller implements this interface to receive the WebView2Environment created via CreateCoreWebView2Environment.</span></span>

## <span data-ttu-id="981a0-106">摘要</span><span class="sxs-lookup"><span data-stu-id="981a0-106">Summary</span></span>

 <span data-ttu-id="981a0-107">成员</span><span class="sxs-lookup"><span data-stu-id="981a0-107">Members</span></span>                        | <span data-ttu-id="981a0-108">描述</span><span class="sxs-lookup"><span data-stu-id="981a0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="981a0-109">调用</span><span class="sxs-lookup"><span data-stu-id="981a0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="981a0-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="981a0-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="981a0-111">成员</span><span class="sxs-lookup"><span data-stu-id="981a0-111">Members</span></span>

#### <span data-ttu-id="981a0-112">调用</span><span class="sxs-lookup"><span data-stu-id="981a0-112">Invoke</span></span> 

<span data-ttu-id="981a0-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="981a0-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="981a0-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment）</span><span class="sxs-lookup"><span data-stu-id="981a0-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Environment](icorewebview2environment.md) \* created_environment)</span></span>

