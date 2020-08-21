---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解可如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器的上下文之外发送用户通知。
title: Web 通知 API - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941799"
---
# <span data-ttu-id="12a63-104">Web 通知 API</span><span class="sxs-lookup"><span data-stu-id="12a63-104">Web Notifications API</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="12a63-105">Web 通知 API 允许网站在 Microsoft Edge 浏览器内网页上下文之外发送用户通知。</span><span class="sxs-lookup"><span data-stu-id="12a63-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span>  <span data-ttu-id="12a63-106">此功能的操作示例将是一个消息应用程序（如 Skype）。</span><span class="sxs-lookup"><span data-stu-id="12a63-106">An example of this feature in action would be with a messaging application like Skype.</span></span>  <span data-ttu-id="12a63-107">当用户收到新消息时，其桌面上会显示通知，通知他们收到消息。</span><span class="sxs-lookup"><span data-stu-id="12a63-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span>  <span data-ttu-id="12a63-108">Web 通知与通知平台及 Windows 10 内的操作中心完全集成。</span><span class="sxs-lookup"><span data-stu-id="12a63-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span>  

## <span data-ttu-id="12a63-109">创建通知</span><span class="sxs-lookup"><span data-stu-id="12a63-109">Creating a notification</span></span>  

<span data-ttu-id="12a63-110">以下代码Pen 可通过将通知对象设置为标题、图标和[正文选项集来创建](https://msdn.microsoft.com/library/mt710811)Mock [icon](https://msdn.microsoft.com/library/mt710814)Skype 通知： [Notification](https://msdn.microsoft.com/library/mt710818) [title](https://msdn.microsoft.com/library/mt710826)</span><span class="sxs-lookup"><span data-stu-id="12a63-110">The CodePen below creates a mock Skype notification by making a [Notification](https://msdn.microsoft.com/library/mt710818) object with the [title](https://msdn.microsoft.com/library/mt710826), [icon](https://msdn.microsoft.com/library/mt710814), and [body](https://msdn.microsoft.com/library/mt710811) options set:</span></span>  

<iframe height='295' scrolling='no' title='<span data-ttu-id="12a63-111">Web 通知</span><span class="sxs-lookup"><span data-stu-id="12a63-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="12a63-112">在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> CodePen 上使用 </a> Microsoft Edge 来 <a href='https://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation </a>) @MicrosoftEdgeDocumentation Pen 来查看 Pen Web <a href='https://codepen.io'> 通知 </a> 。</span><span class="sxs-lookup"><span data-stu-id="12a63-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

<span data-ttu-id="12a63-113">强烈建议为每个 **通知** 指定一个图标。</span><span class="sxs-lookup"><span data-stu-id="12a63-113">It is strongly recommended that an **icon** be specified for each notification.</span></span>  <span data-ttu-id="12a63-114">这不仅仅能改进 UI 点中的通知，还有助于提高通知用户发送通知的位置。</span><span class="sxs-lookup"><span data-stu-id="12a63-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>  

<span data-ttu-id="12a63-115">观看下面的视频，了解创建 Web 通知并查看其在 Windows 10 中行为的演练！</span><span class="sxs-lookup"><span data-stu-id="12a63-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### <span data-ttu-id="12a63-116">通知属性</span><span class="sxs-lookup"><span data-stu-id="12a63-116">Notification properties</span></span>  

<span data-ttu-id="12a63-117">可以使用以下属性设置通知：</span><span class="sxs-lookup"><span data-stu-id="12a63-117">Notifications can be set with the following properties:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-118">正文</span><span class="sxs-lookup"><span data-stu-id="12a63-118">body</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-119">通知的正文文本。</span><span class="sxs-lookup"><span data-stu-id="12a63-119">The body text of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-120">dir</span><span class="sxs-lookup"><span data-stu-id="12a63-120">dir</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-121">通知的文本的方向。</span><span class="sxs-lookup"><span data-stu-id="12a63-121">The direction of the notification's text.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-122">icon</span><span class="sxs-lookup"><span data-stu-id="12a63-122">icon</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-123">通知的 URL 用于其图标。</span><span class="sxs-lookup"><span data-stu-id="12a63-123">The notification's URL that is used for its icon.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-124">lang</span><span class="sxs-lookup"><span data-stu-id="12a63-124">lang</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-125">通知的语言。</span><span class="sxs-lookup"><span data-stu-id="12a63-125">The language of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-126">权限</span><span class="sxs-lookup"><span data-stu-id="12a63-126">permission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-127">向用户授予当前原点的当前通知显示权限。</span><span class="sxs-lookup"><span data-stu-id="12a63-127">The current notification display permission the user has granted for the current origin.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-128">tag</span><span class="sxs-lookup"><span data-stu-id="12a63-128">tag</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-129">通知的标记。</span><span class="sxs-lookup"><span data-stu-id="12a63-129">The tag of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-130">title</span><span class="sxs-lookup"><span data-stu-id="12a63-130">title</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-131">通知的标题。</span><span class="sxs-lookup"><span data-stu-id="12a63-131">The title of the notification.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="12a63-132">通知事件</span><span class="sxs-lookup"><span data-stu-id="12a63-132">Notification events</span></span>  

<span data-ttu-id="12a63-133">以下事件与 Notification 对象一 [起](https://developer.mozilla.org/docs/Web/API/Notification) 使用：</span><span class="sxs-lookup"><span data-stu-id="12a63-133">The following events are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-134">onclick</span><span class="sxs-lookup"><span data-stu-id="12a63-134">onclick</span></span>](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-135">当用户单击某个通知时触发。</span><span class="sxs-lookup"><span data-stu-id="12a63-135">Fires when a notification is clicked by the user.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-136">close</span><span class="sxs-lookup"><span data-stu-id="12a63-136">onclose</span></span>](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-137">当用户关闭通知或自动超时时触发。</span><span class="sxs-lookup"><span data-stu-id="12a63-137">Fires when a notification is closed by the user or an auto timeout.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-138">onerror</span><span class="sxs-lookup"><span data-stu-id="12a63-138">onerror</span></span>](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-139">处理通知时触发错误。</span><span class="sxs-lookup"><span data-stu-id="12a63-139">Fires when an error occurs while handling a notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-140">onshow</span><span class="sxs-lookup"><span data-stu-id="12a63-140">onshow</span></span>](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-141">当通知显示时触发。</span><span class="sxs-lookup"><span data-stu-id="12a63-141">Fires when a notification is displayed.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="12a63-142">通知方法</span><span class="sxs-lookup"><span data-stu-id="12a63-142">Notification methods</span></span>  

<span data-ttu-id="12a63-143">以下方法与 Notification 对象一 [起使用](https://developer.mozilla.org/docs/Web/API/Notification) ：</span><span class="sxs-lookup"><span data-stu-id="12a63-143">The following methods are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-144">close</span><span class="sxs-lookup"><span data-stu-id="12a63-144">close</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-145">关闭显示的通知。</span><span class="sxs-lookup"><span data-stu-id="12a63-145">Closes a displayed notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="12a63-146">requestPermission</span><span class="sxs-lookup"><span data-stu-id="12a63-146">requestPermission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="12a63-147">请求用户的权限，以允许当前来源显示通知。</span><span class="sxs-lookup"><span data-stu-id="12a63-147">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="12a63-148">通知权限</span><span class="sxs-lookup"><span data-stu-id="12a63-148">Notification permissions</span></span>  

<span data-ttu-id="12a63-149">Microsoft Edge 允许用户管理每个特定网站域的通知权限。</span><span class="sxs-lookup"><span data-stu-id="12a63-149">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span>  <span data-ttu-id="12a63-150">如果域要求显示通知，用户可以**选择"** 是"或**No**"否" 以使其显示通知。</span><span class="sxs-lookup"><span data-stu-id="12a63-150">It's up to the user to either select **Yes** or **No** when asked by the domain to let it show notifications.</span></span>  <span data-ttu-id="12a63-151">[requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)方法用于对权限状态进行签名，或者 `granted` `denied` `default` 。</span><span class="sxs-lookup"><span data-stu-id="12a63-151">The [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span>  <span data-ttu-id="12a63-152">一个值，指示用户尚未做出决定，该决策 `default` 被视为相当于等效项 `denied` 。</span><span class="sxs-lookup"><span data-stu-id="12a63-152">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>  

## <span data-ttu-id="12a63-153">API 参考</span><span class="sxs-lookup"><span data-stu-id="12a63-153">API reference</span></span>  

[<span data-ttu-id="12a63-154">Web 通知</span><span class="sxs-lookup"><span data-stu-id="12a63-154">Web Notifications</span></span>](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## <span data-ttu-id="12a63-155">规范</span><span class="sxs-lookup"><span data-stu-id="12a63-155">Specification</span></span>  

[<span data-ttu-id="12a63-156">Web 通知</span><span class="sxs-lookup"><span data-stu-id="12a63-156">Web Notifications</span></span>](https://notifications.spec.whatwg.org)  
