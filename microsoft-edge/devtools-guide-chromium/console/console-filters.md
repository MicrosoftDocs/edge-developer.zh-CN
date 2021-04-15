---
description: 了解如何筛选控制台消息
title: 开始在控制台中筛选消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: b493bb790b48bc1c4dca0e6802d2f638099b7644
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483367"
---
# <a name="filter-console-messages"></a><span data-ttu-id="c72f0-104">筛选控制台消息</span><span class="sxs-lookup"><span data-stu-id="c72f0-104">Filter Console messages</span></span>  

<span data-ttu-id="c72f0-105">当您浏览 Web 时，您可能会发现 **控制台** 中会大量显示各种信息。</span><span class="sxs-lookup"><span data-stu-id="c72f0-105">When you surf the web, you may find the **Console** is flooded with all kinds of information.</span></span>  <span data-ttu-id="c72f0-106">通常信息与自己不相关。</span><span class="sxs-lookup"><span data-stu-id="c72f0-106">Often the information isn't relevant to you.</span></span>  <span data-ttu-id="c72f0-107">例如有关另一个开发人员在调试时记录实时项目的信息。</span><span class="sxs-lookup"><span data-stu-id="c72f0-107">Such as information about the live project that another developer logged while you debug.</span></span>  <span data-ttu-id="c72f0-108">有关你无法更改的当前网站性能的违反和警告详细信息。</span><span class="sxs-lookup"><span data-stu-id="c72f0-108">Or more information about violations and warnings about the performance of the current site that you aren't able to change.</span></span>  <span data-ttu-id="c72f0-109">使用控制台的筛选器选项 **减少噪音是** 有意义的。</span><span class="sxs-lookup"><span data-stu-id="c72f0-109">It makes sense to use the filter options of **Console** to reduce the noise.</span></span>  

## <a name="filter-by-log-level"></a><span data-ttu-id="c72f0-110">按记录级别筛选</span><span class="sxs-lookup"><span data-stu-id="c72f0-110">Filter by log level</span></span>  

<span data-ttu-id="c72f0-111">对象的每个 `console` 方法都有一个附加到它的严重级别。</span><span class="sxs-lookup"><span data-stu-id="c72f0-111">Each method of the `console` object has a severity level attached to it.</span></span>  <span data-ttu-id="c72f0-112">严重性级别为 `Verbose` `Info` 、、 `Warning` 或 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="c72f0-112">The severity levels are `Verbose`, `Info`, `Warning`, or `Error`.</span></span>  <span data-ttu-id="c72f0-113">显示 API 文档中的严重性 [级别][DevtoolsConsoleApi]。</span><span class="sxs-lookup"><span data-stu-id="c72f0-113">Display the severity levels in the [API documentation][DevtoolsConsoleApi].</span></span>  <span data-ttu-id="c72f0-114">例如， `console.log()` 是 `Info` -level 邮件，但 `console.error()` `Error` 是 -level 邮件。</span><span class="sxs-lookup"><span data-stu-id="c72f0-114">For example, `console.log()` is an `Info`-level message, but `console.error()` is an `Error`-level message.</span></span>  

<span data-ttu-id="c72f0-115">若要在控制台中 **筛选消息**，请使用" **日志级别"** 下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="c72f0-115">To filter messages in the **Console**, use the **Log Level** dropdown menu.</span></span>  <span data-ttu-id="c72f0-116">你可以切换每个级别的状态。</span><span class="sxs-lookup"><span data-stu-id="c72f0-116">You may toggle the state of each level.</span></span>  <span data-ttu-id="c72f0-117">若要关闭每个级别，请删除每个级别旁边的选中标记。</span><span class="sxs-lookup"><span data-stu-id="c72f0-117">To turn off each level, remove the checkmark next to each.</span></span>  

:::image type="complex" source="../media/console-filter-dropdown.msft.png" alt-text="下拉菜单使用日志级别筛选控制台消息" lightbox="../media/console-filter-dropdown.msft.png":::
    <span data-ttu-id="c72f0-119">下拉菜单使用日志 **级别** 筛选控制台消息</span><span class="sxs-lookup"><span data-stu-id="c72f0-119">The dropdown menu filters **Console** messages using the log level</span></span>  
:::image-end:::  

<span data-ttu-id="c72f0-120">由于未应用筛选器，下图显示数十条消息。</span><span class="sxs-lookup"><span data-stu-id="c72f0-120">Since no filter is applied, the following figure displays dozens of messages.</span></span>  <span data-ttu-id="c72f0-121">接下来，减少和管理邮件数量。</span><span class="sxs-lookup"><span data-stu-id="c72f0-121">Next, reduce and manage the number of messages.</span></span>  

:::image type="complex" source="../media/console-filter-displays-all.msft.png" alt-text="没有筛选器集意味着你可能会显示许多控制台消息" lightbox="../media/console-filter-displays-all.msft.png":::
    <span data-ttu-id="c72f0-123">没有筛选器集意味着你可能会显示许多控制台消息</span><span class="sxs-lookup"><span data-stu-id="c72f0-123">No filter set means you may display many console messages</span></span>  
:::image-end:::  

<span data-ttu-id="c72f0-124">选择隐藏所有警告级别的消息，以减少噪音。</span><span class="sxs-lookup"><span data-stu-id="c72f0-124">Choose to hide all the Warning-level messages to cut down on the noise.</span></span>  <span data-ttu-id="c72f0-125">导航到" **日志级别** "下拉列表并取消选中 `Warnings` 该级别。</span><span class="sxs-lookup"><span data-stu-id="c72f0-125">Navigate to the **Log Levels** dropdown and uncheck the `Warnings` level.</span></span>  

:::image type="complex" source="../media/console-filter-hide-warning.msft.png" alt-text="在控制台中隐藏所有警告级别消息以筛选大部分噪音" lightbox="../media/console-filter-hide-warning.msft.png":::
    <span data-ttu-id="c72f0-127">在控制台中隐藏所有警告级别 **消息** 以筛选大部分噪音</span><span class="sxs-lookup"><span data-stu-id="c72f0-127">Hide all the warning level messages in the **Console** to filter much of the noise</span></span>  
:::image-end:::  

## <a name="filter-by-text"></a><span data-ttu-id="c72f0-128">按文本筛选</span><span class="sxs-lookup"><span data-stu-id="c72f0-128">Filter by text</span></span>  

<span data-ttu-id="c72f0-129">如果要查看更多详细信息，若要使用文本筛选邮件，在"筛选器"文本框 **中** 键入字符串。</span><span class="sxs-lookup"><span data-stu-id="c72f0-129">If you want to review more detail, to filter messages using text, type a string into the **Filter** textbox.</span></span>  <span data-ttu-id="c72f0-130">例如，在框中键入 以仅显示有关浏览器阻止 `block` 资源加载的消息。</span><span class="sxs-lookup"><span data-stu-id="c72f0-130">For example, type `block` into the box to only display your messages about the browser blocking resources from loading.</span></span>

:::image type="complex" source="../media/console-filter-text.msft.png" alt-text="显示包含单词块的邮件" lightbox="../media/console-filter-text.msft.png":::
    <span data-ttu-id="c72f0-132">显示包含单词的消息</span><span class="sxs-lookup"><span data-stu-id="c72f0-132">Displays the messages that contain the word</span></span> `block`  
:::image-end:::  

## <a name="filter-by-regular-expression"></a><span data-ttu-id="c72f0-133">按正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="c72f0-133">Filter by regular expression</span></span>

<span data-ttu-id="c72f0-134">[正则表达式是][MdnDocsWebJavascriptGuideRegularExpressions] 筛选邮件的一种强大方法。</span><span class="sxs-lookup"><span data-stu-id="c72f0-134">[Regular expressions][MdnDocsWebJavascriptGuideRegularExpressions] are a powerful way to filter messages.</span></span>  <span data-ttu-id="c72f0-135">例如，在 `/^Tracking/` **筛选器文本框中** 键入以仅显示以术语 开始的邮件 `Tracking` 。</span><span class="sxs-lookup"><span data-stu-id="c72f0-135">For example, type `/^Tracking/` into the **Filter** textbox to only displays messages that start with the term `Tracking`.</span></span>  <span data-ttu-id="c72f0-136">如果你不熟悉正则表达式 [，RegExr][|::ref1::|Main] 是了解使用正则表达式的一个很好的资源。</span><span class="sxs-lookup"><span data-stu-id="c72f0-136">If you're unfamiliar with regular expressions, [RegExr][|::ref1::|Main] is a great resource to learn about using regular expressions.</span></span>

:::image type="complex" source="../media/console-filter-regex.msft.png" alt-text="使用筛选器文本框中的正则表达式显示以单词筛选器开始的邮件" lightbox="../media/console-filter-regex.msft.png":::
    <span data-ttu-id="c72f0-138">使用"筛选器"文本框 `filter` 中的正则表达式显示以 **单词开始** 的邮件</span><span class="sxs-lookup"><span data-stu-id="c72f0-138">Displays the messages that start with the word `filter` using a regular expression in the **Filter** textbox</span></span>  
:::image-end:::  

## <a name="filter-by-message-source"></a><span data-ttu-id="c72f0-139">按邮件源筛选</span><span class="sxs-lookup"><span data-stu-id="c72f0-139">Filter by message source</span></span>  

<span data-ttu-id="c72f0-140">还可以定义要显示的消息类型以及每个消息的源位置（使用控制台的边**栏**）。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c72f0-140">You may also define what kind of messages you want to display and where each originated using the **Sidebar** of the **Console**.</span></span>  <span data-ttu-id="c72f0-141">为此，请选择"显示 **控制台边栏"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c72f0-141">To do it, choose the **Show console sidebar** button.</span></span>  

:::image type="complex" source="../media/console-filter-sidebar-icon.msft.png" alt-text="若要打开边栏，请选择边栏图标" lightbox="../media/console-filter-sidebar-icon.msft.png":::
    <span data-ttu-id="c72f0-143">若要打开 **边栏**，请选择" **显示控制台边栏"** 按钮</span><span class="sxs-lookup"><span data-stu-id="c72f0-143">To open the **Sidebar**, choose the **Show console sidebar** button</span></span>  
:::image-end:::  

<span data-ttu-id="c72f0-144">当 **边栏** 打开时，可以显示消息的个数以及每个消息的来源。</span><span class="sxs-lookup"><span data-stu-id="c72f0-144">When the **Sidebar** is open, you may display the overall number of messages and where each originated.</span></span>  <span data-ttu-id="c72f0-145">选项包括 `All messages` `User Messages` `Errors` 、、、、 `Warnings` 和 `Info` `Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="c72f0-145">The options are `All messages`, `User Messages`, `Errors`, `Warnings`, `Info`, and `Verbose`.</span></span>  

:::image type="complex" source="../media/console-filter-sidebar-open.msft.png" alt-text="控制台边栏显示源自于的不同源消息" lightbox="../media/console-filter-sidebar-open.msft.png":::
    <span data-ttu-id="c72f0-147">控制台 **边栏** 显示源自于的不同源消息</span><span class="sxs-lookup"><span data-stu-id="c72f0-147">The **Console Sidebar** displays the different sources messages originated from</span></span>  
:::image-end:::  

<span data-ttu-id="c72f0-148">选择任意选项以仅显示该类型的消息。</span><span class="sxs-lookup"><span data-stu-id="c72f0-148">Choose any of the options to display only the messages of that type.</span></span>  <span data-ttu-id="c72f0-149">例如，若要显示用户消息，请选择用户消息选项来显示更少的噪音。</span><span class="sxs-lookup"><span data-stu-id="c72f0-149">For example, to display user messages, choose the user messages option to display less noise.</span></span>

:::image type="complex" source="../media/console-filter-select-user-messages.msft.png" alt-text="选择使用边栏中的筛选器在控制台中仅显示用户消息" lightbox="../media/console-filter-select-user-messages.msft.png":::
    <span data-ttu-id="c72f0-151">选择使用边栏中的筛选器在 **控制台** 中仅显示 **用户消息**</span><span class="sxs-lookup"><span data-stu-id="c72f0-151">Choose to display only user messages in the **Console** using the filter in the **Sidebar**</span></span>  
:::image-end:::  

<span data-ttu-id="c72f0-152">若要筛选更多内容并展开选择，请选择它旁边的三角形图标。</span><span class="sxs-lookup"><span data-stu-id="c72f0-152">To filter more and expand the choice, choose the triangle icon next to it.</span></span>  <span data-ttu-id="c72f0-153">这样，你将获得更多选择来仅显示来自特定源的邮件。</span><span class="sxs-lookup"><span data-stu-id="c72f0-153">That way you get more choices to display only messages that originate from a specific source.</span></span>  

:::image type="complex" source="../media/console-filter-sidebar-open-arrow.msft.png" alt-text="选择箭头图标可展开每个部分" lightbox="../media/console-filter-sidebar-open-arrow.msft.png":::
    <span data-ttu-id="c72f0-155">选择箭头图标可展开每个部分</span><span class="sxs-lookup"><span data-stu-id="c72f0-155">Choose the arrow icon expands each of the sections</span></span>  
:::image-end:::  

:::image type="complex" source="../media/console-filter-user-message-by-source.msft.png" alt-text="选择任何使用类型和源进行筛选的新选项" lightbox="../media/console-filter-user-message-by-source.msft.png":::
    <span data-ttu-id="c72f0-157">选择任何使用类型和源进行筛选的新选项</span><span class="sxs-lookup"><span data-stu-id="c72f0-157">Choose any of the new options to filter using type and source</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c72f0-158">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="c72f0-158">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  

[MdnDocsWebJavascriptGuideRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 | MDN"  

[RegExrMain]: https://regexr.com "RegExr"  
