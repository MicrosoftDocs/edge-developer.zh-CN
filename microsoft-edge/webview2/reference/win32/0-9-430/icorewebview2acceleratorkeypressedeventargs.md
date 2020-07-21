---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 280df2816696ce4abce118976b3eb9abf76267e3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884412"
---
# <span data-ttu-id="e38b7-104">0.9.430-接口 ICoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e38b7-104">0.9.430 - interface ICoreWebView2AcceleratorKeyPressedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

<span data-ttu-id="e38b7-105">AcceleratorKeyPressed 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e38b7-105">Event args for the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="e38b7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e38b7-106">Summary</span></span>

 <span data-ttu-id="e38b7-107">成员</span><span class="sxs-lookup"><span data-stu-id="e38b7-107">Members</span></span>                        | <span data-ttu-id="e38b7-108">描述</span><span class="sxs-lookup"><span data-stu-id="e38b7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e38b7-109">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="e38b7-109">get_KeyEventKind</span></span>](#get_keyeventkind) | <span data-ttu-id="e38b7-110">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="e38b7-110">The key event type that caused the event to be fired.</span></span>
[<span data-ttu-id="e38b7-111">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="e38b7-111">get_VirtualKey</span></span>](#get_virtualkey) | <span data-ttu-id="e38b7-112">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="e38b7-112">The Win32 virtual key code of the key that was pressed or released.</span></span>
[<span data-ttu-id="e38b7-113">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="e38b7-113">get_KeyEventLParam</span></span>](#get_keyeventlparam) | <span data-ttu-id="e38b7-114">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="e38b7-114">The LPARAM value that accompanied the window message.</span></span>
[<span data-ttu-id="e38b7-115">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="e38b7-115">get_PhysicalKeyStatus</span></span>](#get_physicalkeystatus) | <span data-ttu-id="e38b7-116">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="e38b7-116">A structure representing the information passed in the LPARAM of the window message.</span></span>
[<span data-ttu-id="e38b7-117">get_Handled</span><span class="sxs-lookup"><span data-stu-id="e38b7-117">get_Handled</span></span>](#get_handled) | <span data-ttu-id="e38b7-118">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="e38b7-118">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>
[<span data-ttu-id="e38b7-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="e38b7-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="e38b7-120">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="e38b7-120">Sets the Handled property.</span></span>

## <span data-ttu-id="e38b7-121">成员</span><span class="sxs-lookup"><span data-stu-id="e38b7-121">Members</span></span>

#### <span data-ttu-id="e38b7-122">get_KeyEventKind</span><span class="sxs-lookup"><span data-stu-id="e38b7-122">get_KeyEventKind</span></span> 

<span data-ttu-id="e38b7-123">导致引发事件的键事件类型。</span><span class="sxs-lookup"><span data-stu-id="e38b7-123">The key event type that caused the event to be fired.</span></span>

> <span data-ttu-id="e38b7-124">public HRESULT [get_KeyEventKind](#get_keyeventkind)（CORE_WEBVIEW2_KEY_EVENT_KIND \* KeyEventKind）</span><span class="sxs-lookup"><span data-stu-id="e38b7-124">public HRESULT [get_KeyEventKind](#get_keyeventkind)(CORE_WEBVIEW2_KEY_EVENT_KIND \* keyEventKind)</span></span>

#### <span data-ttu-id="e38b7-125">get_VirtualKey</span><span class="sxs-lookup"><span data-stu-id="e38b7-125">get_VirtualKey</span></span> 

<span data-ttu-id="e38b7-126">已按下或释放的键的 Win32 虚拟键代码。</span><span class="sxs-lookup"><span data-stu-id="e38b7-126">The Win32 virtual key code of the key that was pressed or released.</span></span>

> <span data-ttu-id="e38b7-127">public HRESULT [get_VirtualKey](#get_virtualkey)（UINT \* VirtualKey）</span><span class="sxs-lookup"><span data-stu-id="e38b7-127">public HRESULT [get_VirtualKey](#get_virtualkey)(UINT \* virtualKey)</span></span>

<span data-ttu-id="e38b7-128">这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。</span><span class="sxs-lookup"><span data-stu-id="e38b7-128">This will be one of the Win32 virtual key constants such as VK_RETURN or an (uppercase) ASCII value such as 'A'.</span></span> <span data-ttu-id="e38b7-129">可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。</span><span class="sxs-lookup"><span data-stu-id="e38b7-129">You can check whether Ctrl or Alt are pressed by calling GetKeyState(VK_CONTROL) or GetKeyState(VK_MENU).</span></span>

#### <span data-ttu-id="e38b7-130">get_KeyEventLParam</span><span class="sxs-lookup"><span data-stu-id="e38b7-130">get_KeyEventLParam</span></span> 

<span data-ttu-id="e38b7-131">窗口消息附带的 LPARAM 值。</span><span class="sxs-lookup"><span data-stu-id="e38b7-131">The LPARAM value that accompanied the window message.</span></span>

> <span data-ttu-id="e38b7-132">公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT \* lParam）</span><span class="sxs-lookup"><span data-stu-id="e38b7-132">public HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT \* lParam)</span></span>

<span data-ttu-id="e38b7-133">请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。</span><span class="sxs-lookup"><span data-stu-id="e38b7-133">See the documentation for the WM_KEYDOWN and WM_KEYUP messages.</span></span>

#### <span data-ttu-id="e38b7-134">get_PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="e38b7-134">get_PhysicalKeyStatus</span></span> 

<span data-ttu-id="e38b7-135">表示在窗口消息的 LPARAM 中传递的信息的结构。</span><span class="sxs-lookup"><span data-stu-id="e38b7-135">A structure representing the information passed in the LPARAM of the window message.</span></span>

> <span data-ttu-id="e38b7-136">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* PhysicalKeyStatus）</span><span class="sxs-lookup"><span data-stu-id="e38b7-136">public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(CORE_WEBVIEW2_PHYSICAL_KEY_STATUS \* physicalKeyStatus)</span></span>

#### <span data-ttu-id="e38b7-137">get_Handled</span><span class="sxs-lookup"><span data-stu-id="e38b7-137">get_Handled</span></span> 

<span data-ttu-id="e38b7-138">在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。</span><span class="sxs-lookup"><span data-stu-id="e38b7-138">During AcceleratorKeyPressedEvent handler invocation the WebView is blocked waiting for the decision of if the accelerator will be handled by the host or not.</span></span>

> <span data-ttu-id="e38b7-139">公共 HRESULT [get_Handled](#get_handled)（BOOL \* 已处理）</span><span class="sxs-lookup"><span data-stu-id="e38b7-139">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

<span data-ttu-id="e38b7-140">如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="e38b7-140">If the Handled property is set to TRUE then this will prevent the WebView from performing the default action for this accelerator key.</span></span> <span data-ttu-id="e38b7-141">否则，Web 视图将对加速键执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="e38b7-141">Otherwise the WebView will perform the default action for the accelerator key.</span></span>

#### <span data-ttu-id="e38b7-142">put_Handled</span><span class="sxs-lookup"><span data-stu-id="e38b7-142">put_Handled</span></span> 

<span data-ttu-id="e38b7-143">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="e38b7-143">Sets the Handled property.</span></span>

> <span data-ttu-id="e38b7-144">公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）</span><span class="sxs-lookup"><span data-stu-id="e38b7-144">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

