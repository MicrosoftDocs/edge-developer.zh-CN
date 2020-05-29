---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: 了解如何使用 Web 通知 API 让网站在 Microsoft Edge 浏览器上下文之外发送用户通知。
title: 开发人员指南-Web 通知 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/18/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: da563a333491ef699925adec6f97b3c21d3e54a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562971"
---
# <span data-ttu-id="f5861-104">Web 通知 API</span><span class="sxs-lookup"><span data-stu-id="f5861-104">Web Notifications API</span></span>

<span data-ttu-id="f5861-105">Web 通知 API 允许网站在 Microsoft Edge 浏览器内的网页上下文之外发送用户通知。</span><span class="sxs-lookup"><span data-stu-id="f5861-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span> <span data-ttu-id="f5861-106">此功能的一个示例是使用 Skype 等消息应用程序。</span><span class="sxs-lookup"><span data-stu-id="f5861-106">An example of this feature in action would be with a messaging application like Skype.</span></span> <span data-ttu-id="f5861-107">当用户收到一条新消息时，将在其桌面上显示一条通知，提醒他们显示消息。</span><span class="sxs-lookup"><span data-stu-id="f5861-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span> <span data-ttu-id="f5861-108">Web 通知与 Windows 10 中的通知平台和操作中心完全集成。</span><span class="sxs-lookup"><span data-stu-id="f5861-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span> 

## <span data-ttu-id="f5861-109">创建通知</span><span class="sxs-lookup"><span data-stu-id="f5861-109">Creating a notification</span></span>

<span data-ttu-id="f5861-110">以下 CodePen 通过将对象设置为 "，" 和 "和" 选项来创建模拟 Skype 通知 [`Notification`](https://msdn.microsoft.com/library/mt710818) [`title`](https://msdn.microsoft.com/library/mt710826) [`icon`](https://msdn.microsoft.com/library/mt710814) [`body`](https://msdn.microsoft.com/library/mt710811) ：</span><span class="sxs-lookup"><span data-stu-id="f5861-110">The CodePen below creates a mock Skype notification by making a [`Notification`](https://msdn.microsoft.com/library/mt710818) object with the [`title`](https://msdn.microsoft.com/library/mt710826), [`icon`](https://msdn.microsoft.com/library/mt710814), and [`body`](https://msdn.microsoft.com/library/mt710811) options set:</span></span>


<iframe height='295' scrolling='no' title='<span data-ttu-id="f5861-111">Web 通知</span><span class="sxs-lookup"><span data-stu-id="f5861-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="f5861-112"><a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'> </a> 在 CodePen 上的 Microsoft Edge 文档（ <a href='https://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a> ）中查看 <a href='https://codepen.io'> 笔 Web 通知 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f5861-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span>
</iframe>

<span data-ttu-id="f5861-113">强烈建议为 `icon` 每个通知指定一个。</span><span class="sxs-lookup"><span data-stu-id="f5861-113">It is strongly recommended that an `icon` be specified for each notification.</span></span> <span data-ttu-id="f5861-114">这不仅提高了来自用户界面点的通知，还有助于提醒用户发送通知的位置。</span><span class="sxs-lookup"><span data-stu-id="f5861-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>

<span data-ttu-id="f5861-115">观看以下视频，了解有关创建 web 通知和查看它在 Windows 10 中的行为的演练！</span><span class="sxs-lookup"><span data-stu-id="f5861-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>


> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]

### <span data-ttu-id="f5861-116">通知属性</span><span class="sxs-lookup"><span data-stu-id="f5861-116">Notification properties</span></span>

<span data-ttu-id="f5861-117">可通过以下选项设置通知：</span><span class="sxs-lookup"><span data-stu-id="f5861-117">Notifications can be set with the following options:</span></span>

<span data-ttu-id="f5861-118">属性</span><span class="sxs-lookup"><span data-stu-id="f5861-118">Property</span></span> | <span data-ttu-id="f5861-119">描述</span><span class="sxs-lookup"><span data-stu-id="f5861-119">Description</span></span>
:-------- | :----------
[<span data-ttu-id="f5861-120">正文</span><span class="sxs-lookup"><span data-stu-id="f5861-120">body</span></span>](https://msdn.microsoft.com/library/mt710811) | <span data-ttu-id="f5861-121">通知的正文文本。</span><span class="sxs-lookup"><span data-stu-id="f5861-121">The body text of the notification.</span></span>
[<span data-ttu-id="f5861-122">dir</span><span class="sxs-lookup"><span data-stu-id="f5861-122">dir</span></span>](https://msdn.microsoft.com/library/mt710813) | <span data-ttu-id="f5861-123">通知文本的方向。</span><span class="sxs-lookup"><span data-stu-id="f5861-123">The direction of the notification's text.</span></span>
[<span data-ttu-id="f5861-124">icon</span><span class="sxs-lookup"><span data-stu-id="f5861-124">icon</span></span>](https://msdn.microsoft.com/library/mt710814) | <span data-ttu-id="f5861-125">通知的 URL，用于其图标。</span><span class="sxs-lookup"><span data-stu-id="f5861-125">The notification's URL that is used for its icon.</span></span>
[<span data-ttu-id="f5861-126">l</span><span class="sxs-lookup"><span data-stu-id="f5861-126">lang</span></span>](https://msdn.microsoft.com/library/mt710815) | <span data-ttu-id="f5861-127">通知的语言。</span><span class="sxs-lookup"><span data-stu-id="f5861-127">The language of the notification.</span></span>
[<span data-ttu-id="f5861-128">权限</span><span class="sxs-lookup"><span data-stu-id="f5861-128">permission</span></span>](https://msdn.microsoft.com/library/mt670637) | <span data-ttu-id="f5861-129">用户为当前来源授予的当前通知显示权限。</span><span class="sxs-lookup"><span data-stu-id="f5861-129">The current notification display permission the user has granted for the current origin.</span></span>
[<span data-ttu-id="f5861-130">tag</span><span class="sxs-lookup"><span data-stu-id="f5861-130">tag</span></span>](https://msdn.microsoft.com/library/mt710825) | <span data-ttu-id="f5861-131">通知的标记。</span><span class="sxs-lookup"><span data-stu-id="f5861-131">The tag of the notification.</span></span>
[<span data-ttu-id="f5861-132">title</span><span class="sxs-lookup"><span data-stu-id="f5861-132">title</span></span>](https://msdn.microsoft.com/library/mt710826) | <span data-ttu-id="f5861-133">通知的标题。</span><span class="sxs-lookup"><span data-stu-id="f5861-133">The title of the notification.</span></span>

### <span data-ttu-id="f5861-134">通知事件</span><span class="sxs-lookup"><span data-stu-id="f5861-134">Notification events</span></span>

<span data-ttu-id="f5861-135">以下事件与对象一起使用 [`Notification`](https://msdn.microsoft.com/library/mt710818) ：</span><span class="sxs-lookup"><span data-stu-id="f5861-135">The following events are used with the [`Notification`](https://msdn.microsoft.com/library/mt710818) object:</span></span>

<span data-ttu-id="f5861-136">事件</span><span class="sxs-lookup"><span data-stu-id="f5861-136">Event</span></span> | <span data-ttu-id="f5861-137">说明</span><span class="sxs-lookup"><span data-stu-id="f5861-137">Description</span></span>
:-------- | :----------
[<span data-ttu-id="f5861-138">onclick</span><span class="sxs-lookup"><span data-stu-id="f5861-138">onclick</span></span>](https://msdn.microsoft.com/library/mt712180) | <span data-ttu-id="f5861-139">当用户单击通知时激发。</span><span class="sxs-lookup"><span data-stu-id="f5861-139">Fires when a notification is clicked by the user.</span></span>
[<span data-ttu-id="f5861-140">onclose</span><span class="sxs-lookup"><span data-stu-id="f5861-140">onclose</span></span>](https://msdn.microsoft.com/library/mt712178) | <span data-ttu-id="f5861-141">当用户关闭通知或自动超时时激发。</span><span class="sxs-lookup"><span data-stu-id="f5861-141">Fires when a notification is closed by the user or an auto timeout.</span></span>
[<span data-ttu-id="f5861-142">onerror</span><span class="sxs-lookup"><span data-stu-id="f5861-142">onerror</span></span>](https://msdn.microsoft.com/library/mt712181) | <span data-ttu-id="f5861-143">在处理通知的过程中发生错误时激发。</span><span class="sxs-lookup"><span data-stu-id="f5861-143">Fires when an error occurs while handling a notification.</span></span>
[<span data-ttu-id="f5861-144">onshow</span><span class="sxs-lookup"><span data-stu-id="f5861-144">onshow</span></span>](https://msdn.microsoft.com/library/mt712182) | <span data-ttu-id="f5861-145">在显示通知时激发。</span><span class="sxs-lookup"><span data-stu-id="f5861-145">Fires when a notification is displayed.</span></span>

### <span data-ttu-id="f5861-146">通知方法</span><span class="sxs-lookup"><span data-stu-id="f5861-146">Notification methods</span></span>

<span data-ttu-id="f5861-147">将以下方法与对象配合使用 [`Notification`](https://msdn.microsoft.com/library/mt710818) ：</span><span class="sxs-lookup"><span data-stu-id="f5861-147">The following methods are used with the [`Notification`](https://msdn.microsoft.com/library/mt710818) object:</span></span>

<span data-ttu-id="f5861-148">方法</span><span class="sxs-lookup"><span data-stu-id="f5861-148">Method</span></span> | <span data-ttu-id="f5861-149">描述</span><span class="sxs-lookup"><span data-stu-id="f5861-149">Description</span></span>
:-------- | :----------
[<span data-ttu-id="f5861-150">close</span><span class="sxs-lookup"><span data-stu-id="f5861-150">close</span></span>](https://msdn.microsoft.com/library/mt670636) | <span data-ttu-id="f5861-151">关闭显示的通知。</span><span class="sxs-lookup"><span data-stu-id="f5861-151">Closes a displayed notification.</span></span>
[<span data-ttu-id="f5861-152">requestPermission</span><span class="sxs-lookup"><span data-stu-id="f5861-152">requestPermission</span></span>](https://msdn.microsoft.com/library/mt710824) | <span data-ttu-id="f5861-153">请求用户的权限以允许当前来源显示通知。</span><span class="sxs-lookup"><span data-stu-id="f5861-153">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>

## <span data-ttu-id="f5861-154">通知权限</span><span class="sxs-lookup"><span data-stu-id="f5861-154">Notification permissions</span></span>

<span data-ttu-id="f5861-155">Microsoft Edge 允许用户管理每个特定网站域的通知权限。</span><span class="sxs-lookup"><span data-stu-id="f5861-155">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span> <span data-ttu-id="f5861-156">当域要求用户显示通知时，用户可以选择 "是" 或 "否"。</span><span class="sxs-lookup"><span data-stu-id="f5861-156">It's up to the user to either select "Yes" or "No" when asked by the domain to let it show notifications.</span></span> <span data-ttu-id="f5861-157">此 [`requestPermission`](https://msdn.microsoft.com/library/mt710824) 方法用于将权限状态指示为 `granted` 、、 `denied` 或 `default` 。</span><span class="sxs-lookup"><span data-stu-id="f5861-157">The [`requestPermission`](https://msdn.microsoft.com/library/mt710824) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span> <span data-ttu-id="f5861-158">一个值 `default` 表示用户尚未做出决定，该决策被视为等效项 `denied` 。</span><span class="sxs-lookup"><span data-stu-id="f5861-158">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>




## <span data-ttu-id="f5861-159">API 参考</span><span class="sxs-lookup"><span data-stu-id="f5861-159">API reference</span></span>

[<span data-ttu-id="f5861-160">Web 通知</span><span class="sxs-lookup"><span data-stu-id="f5861-160">Web Notifications</span></span>](https://msdn.microsoft.com/library/mt710827)

## <span data-ttu-id="f5861-161">书</span><span class="sxs-lookup"><span data-stu-id="f5861-161">Specification</span></span>

[<span data-ttu-id="f5861-162">Web 通知</span><span class="sxs-lookup"><span data-stu-id="f5861-162">Web Notifications</span></span>](https://notifications.spec.whatwg.org)
