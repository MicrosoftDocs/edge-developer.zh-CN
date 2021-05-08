---
description: 如果发现自己在控制台中重复键入相同的JavaScript表达式，请尝试使用动态表达式。
title: 使用 Live Expressions 实时观看 JavaScript 表达式值
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 51b7aa5119775f43861a84c1055ac9149a626d8a
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483119"
---
# <a name="monitor-changes-in-javascript-using-live-expressions"></a><span data-ttu-id="12a71-104">使用 Live Expressions 监视 JavaScript 中的更改</span><span class="sxs-lookup"><span data-stu-id="12a71-104">Monitor changes in JavaScript using Live Expressions</span></span>  

<span data-ttu-id="12a71-105">**实时表达式** 是监视进行大量更改的 JavaScript 表达式的一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="12a71-105">**Live Expressions** are an excellent way to monitor JavaScript expressions that change a lot.</span></span>    <span data-ttu-id="12a71-106">你可以将特定 JavaScript 表达式固定到控制台的顶部，而不是使许多控制台消息阅读和 **导航**。</span><span class="sxs-lookup"><span data-stu-id="12a71-106">Instead of having many Console messages to read and navigate, you may pin your specific JavaScript expressions to the top of the **Console**.</span></span>  

## <a name="add-a-new-live-expression"></a><span data-ttu-id="12a71-107">添加新实时表达式</span><span class="sxs-lookup"><span data-stu-id="12a71-107">Add a new live expression</span></span>  

<span data-ttu-id="12a71-108">To start， choose the **Create live expression** \ (eye\) button next to the **Filter** textbox.</span><span class="sxs-lookup"><span data-stu-id="12a71-108">To start, choose the **Create live expression** \(eye\) button next to the **Filter** textbox.</span></span>  <span data-ttu-id="12a71-109">选择它后，将显示一个文本框，供您在文本框中输入新表达式。</span><span class="sxs-lookup"><span data-stu-id="12a71-109">After you choose it, a textbox is displayed for you to enter your new expression in it.</span></span>  

:::image type="complex" source="../media/console-live-expressions-new.msft.png" alt-text="选择"新建实时表达式"按钮以打开文本框以键入表达式" lightbox="../media/console-live-expressions-new.msft.png":::
    <span data-ttu-id="12a71-111">选择 `New live expression` 按钮以打开文本框以键入表达式</span><span class="sxs-lookup"><span data-stu-id="12a71-111">Choose the `New live expression` button to open a textbox to type an expression</span></span>  
:::image-end:::  

<span data-ttu-id="12a71-112">**Live Expressions** 可能是任何有效的 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="12a71-112">**Live Expressions** may be any valid JavaScript expression.</span></span>  <span data-ttu-id="12a71-113">若要尝试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="12a71-113">To try it, complete the following actions.</span></span>  

1.  <span data-ttu-id="12a71-114">打开 **Live Expression** 文本框。</span><span class="sxs-lookup"><span data-stu-id="12a71-114">Open the **Live Expression** textbox.</span></span>  
1.  <span data-ttu-id="12a71-115">键入 `document.activeElement`。</span><span class="sxs-lookup"><span data-stu-id="12a71-115">Type `document.activeElement`.</span></span>  
1.  <span data-ttu-id="12a71-116">若要保存表达式，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="12a71-116">To save the expression, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="12a71-117">选择 `Control`+`Enter`（Windows、Linux）或 `Command`+`Enter` (macOS)。</span><span class="sxs-lookup"><span data-stu-id="12a71-117">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\).</span></span>  
    *   <span data-ttu-id="12a71-118">在 **"Live Expression"文本框之外** 选择。</span><span class="sxs-lookup"><span data-stu-id="12a71-118">Choose outside the **Live Expression** textbox.</span></span>  
        
<span data-ttu-id="12a71-119">表达式现在为活动表达式， `body` 并显示为结果。</span><span class="sxs-lookup"><span data-stu-id="12a71-119">The expression is now live and displays `body` as the result.</span></span>  

:::image type="complex" source="../media/console-live-expressions-document-active-element.msft.png" alt-text="document.activeElement 实时表达式将正文显示为结果" lightbox="../media/console-live-expressions-document-active-element.msft.png":::
    <span data-ttu-id="12a71-121">结果中 `document.activeElement` 显示正文的 Live 表达式</span><span class="sxs-lookup"><span data-stu-id="12a71-121">Live expression for `document.activeElement` displays body as the result</span></span>  
:::image-end:::  

<span data-ttu-id="12a71-122">如果在网页中导航，值将发生更改。</span><span class="sxs-lookup"><span data-stu-id="12a71-122">If you navigate around the webpage, the value changes.</span></span>  <span data-ttu-id="12a71-123">例如，在下图中，在网页中打开搜索菜单，表达式现在 `button.nav-bar-button.focus-visible` 显示为值。</span><span class="sxs-lookup"><span data-stu-id="12a71-123">For example, in the following figure you open the search menu in the webpage and the expression now displays `button.nav-bar-button.focus-visible` as the value.</span></span>  

:::image type="complex" source="../media/console-live-expressions-document-active-element-nav-button.msft.png" alt-text="若要更改 Live Expression 的值，请与网页上的不同元素交互" lightbox="../media/console-live-expressions-document-active-element-nav-button.msft.png":::
    <span data-ttu-id="12a71-125">若要更改 **Live Expression 的值，** 请与网页上的不同元素交互</span><span class="sxs-lookup"><span data-stu-id="12a71-125">To change the value of the **Live Expression**, interact with different elements on the webpage</span></span>  
:::image-end:::  

<span data-ttu-id="12a71-126">若要再次更改该值，请打开并选择网页上的"搜索"文本框。</span><span class="sxs-lookup"><span data-stu-id="12a71-126">To change the value again, open and choose the Search textbox on the webpage.</span></span>  

:::image type="complex" source="../media/console-live-expressions-document-active-element-search.msft.png" alt-text="导航到网页中的不同元素以更新 Live Expression" lightbox="../media/console-live-expressions-document-active-element-search.msft.png":::
    <span data-ttu-id="12a71-128">导航到网页中的不同元素以更新 Live **Expression**</span><span class="sxs-lookup"><span data-stu-id="12a71-128">Navigate to a different element in the webpage to update the **Live Expression**</span></span>  
:::image-end:::  

## <a name="remove-live-expressions"></a><span data-ttu-id="12a71-129">删除 Live Expressions</span><span class="sxs-lookup"><span data-stu-id="12a71-129">Remove Live Expressions</span></span>  

<span data-ttu-id="12a71-130">只要 **使 Live Expression** 保持活动状态，该表达式就可用。</span><span class="sxs-lookup"><span data-stu-id="12a71-130">A **Live Expression** is available as long as you keep it active.</span></span>  <span data-ttu-id="12a71-131">若要删除 Live **Expression，** 请选择它的 `x` 旁边。</span><span class="sxs-lookup"><span data-stu-id="12a71-131">To get rid of a **Live Expression**, choose the `x` next to it.</span></span>  

:::image type="complex" source="../media/console-live-expressions-remove.msft.png" alt-text="若要删除 Live Expressions，请选择其旁边的 x" lightbox="../media/console-live-expressions-remove.msft.png":::
    <span data-ttu-id="12a71-133">若要删除 **Live Expressions，** 请选择 `x` 其旁边的</span><span class="sxs-lookup"><span data-stu-id="12a71-133">To remove **Live Expressions**, choose the `x` next to it</span></span>  
:::image-end:::  

## <a name="replace-console-logging-with-live-expressions"></a><span data-ttu-id="12a71-134">将控制台日志记录替换为 Live Expressions</span><span class="sxs-lookup"><span data-stu-id="12a71-134">Replace Console logging with Live Expressions</span></span>  

<span data-ttu-id="12a71-135">您可以创建多个表达式，并跨浏览器会话和窗口保留每个表达式。</span><span class="sxs-lookup"><span data-stu-id="12a71-135">You may create as many expressions as you want and persist each across browser sessions and windows.</span></span>  <span data-ttu-id="12a71-136">**实时** 表达式是一种减少调试工作流中的噪音的方法。</span><span class="sxs-lookup"><span data-stu-id="12a71-136">**Live Expressions** are a way to cut down on noise in your debugging workflow.</span></span>  

<span data-ttu-id="12a71-137">例如，您希望监视当前网页中的鼠标移动。</span><span class="sxs-lookup"><span data-stu-id="12a71-137">For example, you want to monitor the mouse movement in the current webpage.</span></span>  <span data-ttu-id="12a71-138">导航到 ["记录鼠标移动][GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]"演示，打开 **控制台**，并四处移动鼠标以显示包含大量信息的日志。</span><span class="sxs-lookup"><span data-stu-id="12a71-138">Navigate to [Logging Mouse Movement demo][GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml], open the **Console**, and move your mouse around to display the logs with a lot of information.</span></span>  

:::image type="complex" source="../media/console-live-expression-mouse-logging.msft.png" alt-text="控制台显示有关鼠标位置的很多信息" lightbox="../media/console-live-expression-mouse-logging.msft.png":::
    <span data-ttu-id="12a71-140">**控制台** 显示有关鼠标位置的很多信息</span><span class="sxs-lookup"><span data-stu-id="12a71-140">**Console** displays much information on mouse position</span></span>  
:::image-end:::  

<span data-ttu-id="12a71-141">大量信息不仅会减慢调试过程，还易于错过想要查看的更改。</span><span class="sxs-lookup"><span data-stu-id="12a71-141">The large amount of information not only slows your debug process, but also makes it easy to miss the changes you want to review.</span></span>  <span data-ttu-id="12a71-142">当 **控制台** 显示更多消息并移动鼠标时，你想要查看的值将滚动到屏幕上。</span><span class="sxs-lookup"><span data-stu-id="12a71-142">As the **Console** displays more messages and you move your mouse, the values you want to review scroll off the screen.</span></span>  

<span data-ttu-id="12a71-143">若要尝试 **Live Expressions** 作为替代方法，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="12a71-143">To try **Live Expressions** as an alternative, complete the following actions.</span></span>  

1.  <span data-ttu-id="12a71-144">导航到鼠标 [移动而不记录演示][GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]。</span><span class="sxs-lookup"><span data-stu-id="12a71-144">Navigate to the [Mouse movement without logging demo][GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml].</span></span>  
1.  <span data-ttu-id="12a71-145">为 和 创建 **Live** `x` `y` Expressions。</span><span class="sxs-lookup"><span data-stu-id="12a71-145">Create **Live Expressions** for `x` and `y`.</span></span>  
    
<span data-ttu-id="12a71-146">使用**Live Expressions 时**，始终在屏幕的相同部分获取信息，并保留控制台\*\*\*\* 日志，查看不会更改太多值。</span><span class="sxs-lookup"><span data-stu-id="12a71-146">When you use **Live Expressions**, you always get the information on the same part of your screen and keep **Console** logs for values that don't change as much.</span></span>

:::image type="complex" source="../media/console-live-expressions-x-and-y.msft.png" alt-text="将鼠标的 x 和 y 位置显示为 Live Expressions" lightbox="../media/console-live-expressions-x-and-y.msft.png":::
    <span data-ttu-id="12a71-148">将 `x` 鼠标 `y` 的 和 位置显示为 Live **Expressions**</span><span class="sxs-lookup"><span data-stu-id="12a71-148">Display the `x` and `y` position of the mouse as **Live Expressions**</span></span>  
:::image-end:::  

<span data-ttu-id="12a71-149">**Live Expressions** 以独占方式在计算机上运行，无需更改代码中要显示任何内容。</span><span class="sxs-lookup"><span data-stu-id="12a71-149">**Live Expressions** run exclusively on your computer and you don't need to change anything in your code to display.</span></span>  <span data-ttu-id="12a71-150">**实时** 表达式是确保您仅显示要调试的信息的一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="12a71-150">**Live Expressions** are a great way to ensure that you only display the information you want to debug.</span></span>  <span data-ttu-id="12a71-151">此外 **，Live Expressions** 还可帮助您限制用户计算机上的噪音。</span><span class="sxs-lookup"><span data-stu-id="12a71-151">Also, **Live Expressions** help you limit the noise on your users' computers.</span></span>

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="12a71-152">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="12a71-152">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove.html "控制台消息示例：使用表|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove-no-log.html "无需日志记录即可移动鼠标|GitHub"  
