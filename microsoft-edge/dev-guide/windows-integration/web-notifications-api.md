---
ms.assetid: 2ecc762c-11a5-4b16-9aed-22606c1d4994
description: Learn how the Web Notifications API can be used to let websites send users notifications outside the context of the Microsoft Edge browser.
title: Web Notifications API - Dev guide
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: 24b8a7b25fb3e0f0221f6d81b105d5d0374ea423
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941799"
---
# <span data-ttu-id="0eb9b-104">Web Notifications API</span><span class="sxs-lookup"><span data-stu-id="0eb9b-104">Web Notifications API</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="0eb9b-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-105">The Web Notifications API allows websites to send users notifications outside the context of a webpage within the Microsoft Edge browser.</span></span>  <span data-ttu-id="0eb9b-106">An example of this feature in action would be with a messaging application like Skype.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-106">An example of this feature in action would be with a messaging application like Skype.</span></span>  <span data-ttu-id="0eb9b-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-107">When a user would receive a new message, a notification would appear on their desktop, alerting them of the message.</span></span>  <span data-ttu-id="0eb9b-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-108">Web Notifications are fully integrated with the Notification Platform and the Action Center within Windows 10.</span></span>  

## <span data-ttu-id="0eb9b-109">Creating a notification</span><span class="sxs-lookup"><span data-stu-id="0eb9b-109">Creating a notification</span></span>  

<span data-ttu-id="0eb9b-110">The CodePen below creates a mock Skype notification by making a [Notification](https://msdn.microsoft.com/library/mt710818) object with the [title](https://msdn.microsoft.com/library/mt710826), [icon](https://msdn.microsoft.com/library/mt710814), and [body](https://msdn.microsoft.com/library/mt710811) options set:</span><span class="sxs-lookup"><span data-stu-id="0eb9b-110">The CodePen below creates a mock Skype notification by making a [Notification](https://msdn.microsoft.com/library/mt710818) object with the [title](https://msdn.microsoft.com/library/mt710826), [icon](https://msdn.microsoft.com/library/mt710814), and [body](https://msdn.microsoft.com/library/mt710811) options set:</span></span>  

<iframe height='295' scrolling='no' title='<span data-ttu-id="0eb9b-111">Web notifications</span><span class="sxs-lookup"><span data-stu-id="0eb9b-111">Web notifications</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/RGbxWW/?height=295&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="0eb9b-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-112">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/RGbxWW/'>Web notifications</a> by Microsoft Edge Docs (<a href='https://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

<span data-ttu-id="0eb9b-113">It is strongly recommended that an **icon** be specified for each notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-113">It is strongly recommended that an **icon** be specified for each notification.</span></span>  <span data-ttu-id="0eb9b-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-114">This not only improves a notification from a UI point of view, but also helps alert users of where the notification is being sent from.</span></span>  

<span data-ttu-id="0eb9b-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span><span class="sxs-lookup"><span data-stu-id="0eb9b-115">Watch the video below for a walkthrough on creating a web notification and to see it's behavior within Windows 10!</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Implementing-Web-Notifications/player]  

### <span data-ttu-id="0eb9b-116">Notification properties</span><span class="sxs-lookup"><span data-stu-id="0eb9b-116">Notification properties</span></span>  

<span data-ttu-id="0eb9b-117">Notifications can be set with the following properties:</span><span class="sxs-lookup"><span data-stu-id="0eb9b-117">Notifications can be set with the following properties:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-118">body</span><span class="sxs-lookup"><span data-stu-id="0eb9b-118">body</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/body)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-119">The body text of the notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-119">The body text of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-120">dir</span><span class="sxs-lookup"><span data-stu-id="0eb9b-120">dir</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/dir)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-121">The direction of the notification's text.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-121">The direction of the notification's text.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-122">icon</span><span class="sxs-lookup"><span data-stu-id="0eb9b-122">icon</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/icon)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-123">The notification's URL that is used for its icon.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-123">The notification's URL that is used for its icon.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-124">lang</span><span class="sxs-lookup"><span data-stu-id="0eb9b-124">lang</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/lang)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-125">The language of the notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-125">The language of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-126">permission</span><span class="sxs-lookup"><span data-stu-id="0eb9b-126">permission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/permission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-127">The current notification display permission the user has granted for the current origin.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-127">The current notification display permission the user has granted for the current origin.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-128">tag</span><span class="sxs-lookup"><span data-stu-id="0eb9b-128">tag</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/tag)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-129">The tag of the notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-129">The tag of the notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-130">title</span><span class="sxs-lookup"><span data-stu-id="0eb9b-130">title</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/title)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-131">The title of the notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-131">The title of the notification.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="0eb9b-132">Notification events</span><span class="sxs-lookup"><span data-stu-id="0eb9b-132">Notification events</span></span>  

<span data-ttu-id="0eb9b-133">The following events are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span><span class="sxs-lookup"><span data-stu-id="0eb9b-133">The following events are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-134">onclick</span><span class="sxs-lookup"><span data-stu-id="0eb9b-134">onclick</span></span>](https://developer.mozilla.org/docs/Web/API/Element/click_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-135">Fires when a notification is clicked by the user.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-135">Fires when a notification is clicked by the user.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-136">onclose</span><span class="sxs-lookup"><span data-stu-id="0eb9b-136">onclose</span></span>](https://developer.mozilla.org/docs/Archive/Mozilla/XUL/Events/close_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-137">Fires when a notification is closed by the user or an auto timeout.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-137">Fires when a notification is closed by the user or an auto timeout.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-138">onerror</span><span class="sxs-lookup"><span data-stu-id="0eb9b-138">onerror</span></span>](https://developer.mozilla.org/docs/Web/API/Element/error_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-139">Fires when an error occurs while handling a notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-139">Fires when an error occurs while handling a notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-140">onshow</span><span class="sxs-lookup"><span data-stu-id="0eb9b-140">onshow</span></span>](https://developer.mozilla.org/docs/Web/API/Element/show_event)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-141">Fires when a notification is displayed.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-141">Fires when a notification is displayed.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="0eb9b-142">Notification methods</span><span class="sxs-lookup"><span data-stu-id="0eb9b-142">Notification methods</span></span>  

<span data-ttu-id="0eb9b-143">The following methods are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span><span class="sxs-lookup"><span data-stu-id="0eb9b-143">The following methods are used with the [Notification](https://developer.mozilla.org/docs/Web/API/Notification) object:</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-144">close</span><span class="sxs-lookup"><span data-stu-id="0eb9b-144">close</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/close)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-145">Closes a displayed notification.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-145">Closes a displayed notification.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="0eb9b-146">requestPermission</span><span class="sxs-lookup"><span data-stu-id="0eb9b-146">requestPermission</span></span>](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="0eb9b-147">Requests permission from the user to allow notifications to be displayed by the current origin.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-147">Requests permission from the user to allow notifications to be displayed by the current origin.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="0eb9b-148">Notification permissions</span><span class="sxs-lookup"><span data-stu-id="0eb9b-148">Notification permissions</span></span>  

<span data-ttu-id="0eb9b-149">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-149">Microsoft Edge allows users to manage notifications permissions for each specific website domain.</span></span>  <span data-ttu-id="0eb9b-150">It's up to the user to either select **Yes** or **No** when asked by the domain to let it show notifications.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-150">It's up to the user to either select **Yes** or **No** when asked by the domain to let it show notifications.</span></span>  <span data-ttu-id="0eb9b-151">The [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-151">The [requestPermission](https://developer.mozilla.org/docs/Web/API/Notification/requestPermission) method is used to signal the permission state as either `granted`, `denied`, or `default`.</span></span>  <span data-ttu-id="0eb9b-152">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span><span class="sxs-lookup"><span data-stu-id="0eb9b-152">A value of `default` indicates that the user hasn't made a decision, which is seen as the equivalent of `denied`.</span></span>  

## <span data-ttu-id="0eb9b-153">API reference</span><span class="sxs-lookup"><span data-stu-id="0eb9b-153">API reference</span></span>  

[<span data-ttu-id="0eb9b-154">Web Notifications</span><span class="sxs-lookup"><span data-stu-id="0eb9b-154">Web Notifications</span></span>](https://developer.mozilla.org/docs/Web/API/Notifications_API)  

## <span data-ttu-id="0eb9b-155">Specification</span><span class="sxs-lookup"><span data-stu-id="0eb9b-155">Specification</span></span>  

[<span data-ttu-id="0eb9b-156">Web Notifications</span><span class="sxs-lookup"><span data-stu-id="0eb9b-156">Web Notifications</span></span>](https://notifications.spec.whatwg.org)  
