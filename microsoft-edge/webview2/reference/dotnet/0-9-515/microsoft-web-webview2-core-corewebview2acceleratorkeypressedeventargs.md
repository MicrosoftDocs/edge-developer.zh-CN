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
ms.openlocfilehash: b0df25ffe3b00267dfff15cd50d1d3db6a7e38bb
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698216"
---
# <span data-ttu-id="1c4af-104">CoreWebView2AcceleratorKeyPressedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="1c4af-104">Microsoft.Web.WebView2.Core.CoreWebView2AcceleratorKeyPressedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="1c4af-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="1c4af-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="1c4af-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="1c4af-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="1c4af-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="1c4af-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="1c4af-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="1c4af-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="1c4af-109">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1c4af-109">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="1c4af-110">摘要</span><span class="sxs-lookup"><span data-stu-id="1c4af-110">Summary</span></span>

 <span data-ttu-id="1c4af-111">成员</span><span class="sxs-lookup"><span data-stu-id="1c4af-111">Members</span></span>                        | <span data-ttu-id="1c4af-112">描述</span><span class="sxs-lookup"><span data-stu-id="1c4af-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1c4af-113">Handled</span><span class="sxs-lookup"><span data-stu-id="1c4af-113">Handled</span></span>](#handled) | <span data-ttu-id="1c4af-114">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="1c4af-114">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="1c4af-115">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="1c4af-115">KeyEventKind</span></span>](#keyeventkind) | <span data-ttu-id="1c4af-116">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="1c4af-116">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="1c4af-117">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="1c4af-117">KeyEventLParam</span></span>](#keyeventlparam) | <span data-ttu-id="1c4af-118">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="1c4af-118">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="1c4af-119">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="1c4af-119">PhysicalKeyStatus</span></span>](#physicalkeystatus) | <span data-ttu-id="1c4af-120">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="1c4af-120">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="1c4af-121">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="1c4af-121">VirtualKey</span></span>](#virtualkey) | <span data-ttu-id="1c4af-122">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="1c4af-122">The Win32 virtual key code of the key that was pressed or released.</span></span>

## <span data-ttu-id="1c4af-123">成员</span><span class="sxs-lookup"><span data-stu-id="1c4af-123">Members</span></span>

#### <span data-ttu-id="1c4af-124">Handled</span><span class="sxs-lookup"><span data-stu-id="1c4af-124">Handled</span></span> 

<span data-ttu-id="1c4af-125">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="1c4af-125">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="1c4af-126">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="1c4af-126">public bool [Handled](#handled)</span></span>

<span data-ttu-id="1c4af-127">如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="1c4af-127">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="1c4af-128">否则，Web 视图将对加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="1c4af-128">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="1c4af-129">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="1c4af-129">KeyEventKind</span></span> 

<span data-ttu-id="1c4af-130">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="1c4af-130">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="1c4af-131">公共[CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)</span><span class="sxs-lookup"><span data-stu-id="1c4af-131">public [CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)</span></span>

#### <span data-ttu-id="1c4af-132">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="1c4af-132">KeyEventLParam</span></span> 

<span data-ttu-id="1c4af-133">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="1c4af-133">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="1c4af-134">公共 int [KeyEventLParam](#keyeventlparam)</span><span class="sxs-lookup"><span data-stu-id="1c4af-134">public int [KeyEventLParam](#keyeventlparam)</span></span>

<span data-ttu-id="1c4af-135">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="1c4af-135">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="1c4af-136">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="1c4af-136">PhysicalKeyStatus</span></span> 

<span data-ttu-id="1c4af-137">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="1c4af-137">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="1c4af-138">公共[CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)</span><span class="sxs-lookup"><span data-stu-id="1c4af-138">public [CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)</span></span>

#### <span data-ttu-id="1c4af-139">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="1c4af-139">VirtualKey</span></span> 

<span data-ttu-id="1c4af-140">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="1c4af-140">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="1c4af-141">公共 uint [VirtualKey](#virtualkey)</span><span class="sxs-lookup"><span data-stu-id="1c4af-141">public uint [VirtualKey](#virtualkey)</span></span>

<span data-ttu-id="1c4af-142">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="1c4af-142">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="1c4af-143">可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="1c4af-143">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

