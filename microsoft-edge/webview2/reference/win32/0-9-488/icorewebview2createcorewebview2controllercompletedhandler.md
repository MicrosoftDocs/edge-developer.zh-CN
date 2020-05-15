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
ms.openlocfilehash: 49b2baf825d65b97b4b1fa62d06b2f6d6b7bd26d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653081"
---
# <span data-ttu-id="ba592-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ba592-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ba592-105">调用方实现此接口以接收通过 CreateCoreWebView2Controller 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="ba592-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="ba592-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ba592-106">Summary</span></span>

 <span data-ttu-id="ba592-107">成员</span><span class="sxs-lookup"><span data-stu-id="ba592-107">Members</span></span>                        | <span data-ttu-id="ba592-108">描述</span><span class="sxs-lookup"><span data-stu-id="ba592-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ba592-109">调用</span><span class="sxs-lookup"><span data-stu-id="ba592-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ba592-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="ba592-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="ba592-111">成员</span><span class="sxs-lookup"><span data-stu-id="ba592-111">Members</span></span>

#### <span data-ttu-id="ba592-112">调用</span><span class="sxs-lookup"><span data-stu-id="ba592-112">Invoke</span></span> 

<span data-ttu-id="ba592-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="ba592-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ba592-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Controller](icorewebview2controller.md) \* createdController）</span><span class="sxs-lookup"><span data-stu-id="ba592-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

