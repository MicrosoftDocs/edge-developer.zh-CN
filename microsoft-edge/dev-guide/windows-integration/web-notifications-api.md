---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器上下文之外发送用户通知。
title: Web 通知 API-开发指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941799"
---
# <span data-ttu-id="cb7f9-104">Web 通知 API</span><span class="sxs-lookup"><span data-stu-id="cb7f9-104">Web Notifications API</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="cb7f9-105">Web 通知 API 允许网站在 Microsoft Edge 浏览器内的网页上下文之外发送用户通知。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span>  <span data-ttu-id="cb7f9-106">此功能的一个示例是使用 Skype 等消息应用程序。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-106">An example of this feature in action would be with a messaging application like Skype.</span></span>  <span data-ttu-id="cb7f9-107">当用户收到一条新消息时，将在其桌面上显示一条通知，提醒他们显示消息。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span>  <span data-ttu-id="cb7f9-108">Web 通知与 Windows 10 中的通知平台和操作中心完全集成。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span>  

## <span data-ttu-id="cb7f9-109">创建通知</span><span class="sxs-lookup"><span data-stu-id="cb7f9-109">Creating a notification</span></span>  

<span data-ttu-id="cb7f9-110">以下 CodePen 通过使用 "[标题](https://msdn.microsoft.com/library/mt710826)"、"[图标](https://msdn.microsoft.com/library/mt710814)" 和 "[正文](https://msdn.microsoft.com/library/mt710811)" 选项设置的[通知](https://msdn.microsoft.com/library/mt710818)对象来创建模拟 Skype 通知：</span><span class="sxs-lookup"><span data-stu-id="cb7f9-110">The CodePen below creates a mock Skype notification by making a [Notification](https://msdn.microsoft.com/library/mt710818) object with the [title](https://msdn.microsoft.com/library/mt710826), [icon](https://msdn.microsoft.com/library/mt710814), and [body](https://msdn.microsoft.com/library/mt710811) options set:</span></span>  

<iframe height='295' scrolling='no' title='<span data-ttu-id="cb7f9-111">Web 通知</span><span class="sxs-lookup"><span data-stu-id="cb7f9-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="cb7f9-112"><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> 在 CodePen 上查看 Microsoft Edge 文档 (@MicrosoftEdgeDocumentation) 的 Web 通知 <a href='https://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='https://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

<span data-ttu-id="cb7f9-113">强烈建议为每个通知指定一个 **图标** 。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-113">It is strongly recommended that an **icon** be specified for each notification.</span></span>  <span data-ttu-id="cb7f9-114">这不仅提高了来自用户界面点的通知，还有助于提醒用户发送通知的位置。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>  

<span data-ttu-id="cb7f9-115">观看以下视频，了解有关创建 web 通知和查看它在 Windows 10 中的行为的演练！</span><span class="sxs-lookup"><span data-stu-id="cb7f9-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### <span data-ttu-id="cb7f9-116">通知属性</span><span class="sxs-lookup"><span data-stu-id="cb7f9-116">Notification properties</span></span>  

<span data-ttu-id="cb7f9-117">可通过以下属性设置通知：</span><span class="sxs-lookup"><span data-stu-id="cb7f9-117">Notifications can be set with the following properties:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-118">正文</span><span class="sxs-lookup"><span data-stu-id="cb7f9-118">body</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-119">通知的正文文本。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-119">The body text of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-120">dir</span><span class="sxs-lookup"><span data-stu-id="cb7f9-120">dir</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-121">通知文本的方向。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-121">The direction of the notification's text.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-122">icon</span><span class="sxs-lookup"><span data-stu-id="cb7f9-122">icon</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-123">通知的 URL，用于其图标。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-123">The notification's URL that is used for its icon.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-124">l</span><span class="sxs-lookup"><span data-stu-id="cb7f9-124">lang</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-125">通知的语言。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-125">The language of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-126">权限</span><span class="sxs-lookup"><span data-stu-id="cb7f9-126">permission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-127">用户为当前来源授予的当前通知显示权限。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-127">The current notification display permission the user has granted for the current origin.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-128">tag</span><span class="sxs-lookup"><span data-stu-id="cb7f9-128">tag</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-129">通知的标记。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-129">The tag of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-130">title</span><span class="sxs-lookup"><span data-stu-id="cb7f9-130">title</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-131">通知的标题。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-131">The title of the notification.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="cb7f9-132">通知事件</span><span class="sxs-lookup"><span data-stu-id="cb7f9-132">Notification events</span></span>  

<span data-ttu-id="cb7f9-133">以下事件与 [通知](https://developer.mozilla.org/docs/Web/API/Notification) 对象一起使用：</span><span class="sxs-lookup"><span data-stu-id="cb7f9-133">The following events are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-134">onclick</span><span class="sxs-lookup"><span data-stu-id="cb7f9-134">onclick</span></span>](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-135">当用户单击通知时激发。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-135">Fires when a notification is clicked by the user.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-136">onclose</span><span class="sxs-lookup"><span data-stu-id="cb7f9-136">onclose</span></span>](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-137">当用户关闭通知或自动超时时激发。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-137">Fires when a notification is closed by the user or an auto timeout.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-138">onerror</span><span class="sxs-lookup"><span data-stu-id="cb7f9-138">onerror</span></span>](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-139">在处理通知的过程中发生错误时激发。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-139">Fires when an error occurs while handling a notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-140">onshow</span><span class="sxs-lookup"><span data-stu-id="cb7f9-140">onshow</span></span>](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-141">在显示通知时激发。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-141">Fires when a notification is displayed.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="cb7f9-142">通知方法</span><span class="sxs-lookup"><span data-stu-id="cb7f9-142">Notification methods</span></span>  

<span data-ttu-id="cb7f9-143">将以下方法与 [通知](https://developer.mozilla.org/docs/Web/API/Notification) 对象结合使用：</span><span class="sxs-lookup"><span data-stu-id="cb7f9-143">The following methods are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-144">close</span><span class="sxs-lookup"><span data-stu-id="cb7f9-144">close</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-145">关闭显示的通知。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-145">Closes a displayed notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="cb7f9-146">requestPermission</span><span class="sxs-lookup"><span data-stu-id="cb7f9-146">requestPermission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb7f9-147">请求用户的权限以允许当前来源显示通知。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-147">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="cb7f9-148">通知权限</span><span class="sxs-lookup"><span data-stu-id="cb7f9-148">Notification permissions</span></span>  

<span data-ttu-id="cb7f9-149">Microsoft Edge 允许用户管理每个特定网站域的通知权限。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-149">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span>  <span data-ttu-id="cb7f9-150">当域要求您选择 "是" 或 "否" 以让其显示通知时，由用户选择 **"是" 或 "** **否** "。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-150">It's up to the user to either select **Yes** or **No** when asked by the domain to let it show notifications.</span></span>  <span data-ttu-id="cb7f9-151">[RequestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)方法用于将权限状态指示为 `granted` 、、 `denied` 或 `default` 。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-151">The [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span>  <span data-ttu-id="cb7f9-152">一个值 `default` 表示用户尚未做出决定，该决策被视为等效项 `denied` 。</span><span class="sxs-lookup"><span data-stu-id="cb7f9-152">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>  

## <span data-ttu-id="cb7f9-153">API 参考</span><span class="sxs-lookup"><span data-stu-id="cb7f9-153">API reference</span></span>  

[<span data-ttu-id="cb7f9-154">Web 通知</span><span class="sxs-lookup"><span data-stu-id="cb7f9-154">Web Notifications</span></span>](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## <span data-ttu-id="cb7f9-155">书</span><span class="sxs-lookup"><span data-stu-id="cb7f9-155">Specification</span></span>  

[<span data-ttu-id="cb7f9-156">Web 通知</span><span class="sxs-lookup"><span data-stu-id="cb7f9-156">Web Notifications</span></span>](https://notifications.spec.whatwg.org)  
