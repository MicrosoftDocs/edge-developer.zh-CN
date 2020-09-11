---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 0e0735dad942177326127432c151697869dc357e
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011088"
---
# <span data-ttu-id="a1c4a-104">0.9.579-WebView2 的 CoreWebView2AcceleratorKeyPressedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="a1c4a-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2AcceleratorKeyPressedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="a1c4a-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a1c4a-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a1c4a-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a1c4a-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a1c4a-107">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-107">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="a1c4a-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a1c4a-108">Summary</span></span>

 <span data-ttu-id="a1c4a-109">成员</span><span class="sxs-lookup"><span data-stu-id="a1c4a-109">Members</span></span>                        | <span data-ttu-id="a1c4a-110">描述</span><span class="sxs-lookup"><span data-stu-id="a1c4a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a1c4a-111">Handled</span><span class="sxs-lookup"><span data-stu-id="a1c4a-111">Handled</span></span>](#handled) | <span data-ttu-id="a1c4a-112">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-112">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="a1c4a-113">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="a1c4a-113">KeyEventKind</span></span>](#keyeventkind) | <span data-ttu-id="a1c4a-114">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-114">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="a1c4a-115">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="a1c4a-115">KeyEventLParam</span></span>](#keyeventlparam) | <span data-ttu-id="a1c4a-116">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-116">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="a1c4a-117">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="a1c4a-117">PhysicalKeyStatus</span></span>](#physicalkeystatus) | <span data-ttu-id="a1c4a-118">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-118">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="a1c4a-119">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="a1c4a-119">VirtualKey</span></span>](#virtualkey) | <span data-ttu-id="a1c4a-120">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-120">The Win32 virtual key code of the key that was pressed or released.</span></span>

## <span data-ttu-id="a1c4a-121">成员</span><span class="sxs-lookup"><span data-stu-id="a1c4a-121">Members</span></span>

#### <span data-ttu-id="a1c4a-122">Handled</span><span class="sxs-lookup"><span data-stu-id="a1c4a-122">Handled</span></span> 

<span data-ttu-id="a1c4a-123">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-123">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="a1c4a-124">公共 bool 已 [处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="a1c4a-124">public bool [Handled](#handled)</span></span>

<span data-ttu-id="a1c4a-125">如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-125">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="a1c4a-126">否则，Web 视图将对加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-126">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="a1c4a-127">KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="a1c4a-127">KeyEventKind</span></span> 

<span data-ttu-id="a1c4a-128">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-128">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="a1c4a-129">公共 [CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)</span><span class="sxs-lookup"><span data-stu-id="a1c4a-129">public [CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)</span></span>

#### <span data-ttu-id="a1c4a-130">KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="a1c4a-130">KeyEventLParam</span></span> 

<span data-ttu-id="a1c4a-131">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-131">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="a1c4a-132">公共 int [KeyEventLParam](#keyeventlparam)</span><span class="sxs-lookup"><span data-stu-id="a1c4a-132">public int [KeyEventLParam](#keyeventlparam)</span></span>

<span data-ttu-id="a1c4a-133">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-133">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="a1c4a-134">PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="a1c4a-134">PhysicalKeyStatus</span></span> 

<span data-ttu-id="a1c4a-135">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-135">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="a1c4a-136">公共 [CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)</span><span class="sxs-lookup"><span data-stu-id="a1c4a-136">public [CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)</span></span>

#### <span data-ttu-id="a1c4a-137">VirtualKey</span><span class="sxs-lookup"><span data-stu-id="a1c4a-137">VirtualKey</span></span> 

<span data-ttu-id="a1c4a-138">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-138">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="a1c4a-139">公共 uint [VirtualKey](#virtualkey)</span><span class="sxs-lookup"><span data-stu-id="a1c4a-139">public uint [VirtualKey](#virtualkey)</span></span>

<span data-ttu-id="a1c4a-140">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或 (大写) ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-140">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="a1c4a-141">你可以通过调用 GetKeyState (VK_CONTROL) 或 GetKeyState (VK_MENU) 来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="a1c4a-141">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

