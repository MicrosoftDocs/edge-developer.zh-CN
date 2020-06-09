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
ms.openlocfilehash: a3dde4581692fb30cada16d9166bda62a0d69179
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698458"
---
# <span data-ttu-id="675e0-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="675e0-104">interface ICoreWebView2ExecuteScriptCompletedHandler</span></span> 

```
interface ICoreWebView2ExecuteScriptCompletedHandler
  : public IUnknown
```

<span data-ttu-id="675e0-105">调用方实现此接口以接收 ExecuteScript 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="675e0-105">The caller implements this interface to receive the result of the ExecuteScript method.</span></span>

## <span data-ttu-id="675e0-106">摘要</span><span class="sxs-lookup"><span data-stu-id="675e0-106">Summary</span></span>

 <span data-ttu-id="675e0-107">成员</span><span class="sxs-lookup"><span data-stu-id="675e0-107">Members</span></span>                        | <span data-ttu-id="675e0-108">描述</span><span class="sxs-lookup"><span data-stu-id="675e0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="675e0-109">调用</span><span class="sxs-lookup"><span data-stu-id="675e0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="675e0-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="675e0-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="675e0-111">成员</span><span class="sxs-lookup"><span data-stu-id="675e0-111">Members</span></span>

#### <span data-ttu-id="675e0-112">调用</span><span class="sxs-lookup"><span data-stu-id="675e0-112">Invoke</span></span> 

<span data-ttu-id="675e0-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="675e0-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="675e0-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR resultObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="675e0-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR resultObjectAsJson)</span></span>

