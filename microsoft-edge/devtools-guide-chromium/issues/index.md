---
description: 使用问题工具识别和修复当前网页的问题。
title: 使用问题工具查找和修复问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/24/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 86277c509aa4b67635661ba3a316fb5b1e3b9d14
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624687"
---
<!-- Copyright Sam Dutton

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="find-and-fix-problems-using-the-issues-tool"></a><span data-ttu-id="cb2f9-104">使用问题工具查找和修复问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-104">Find and fix problems using the Issues tool</span></span>

<span data-ttu-id="cb2f9-105">在 Microsoft Edge工具中，问题工具自动分析当前\*\*\*\* 网页，报告按类型分组的问题，并提供文档来帮助解释和解决问题。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-105">In Microsoft Edge DevTools, the **Issues** tool automatically analyzes the current webpage, reports issues grouped by type, and provides documentation to help explain and resolve the issues.</span></span>

<span data-ttu-id="cb2f9-106">问题 **工具** 提供以下类别的反馈：</span><span class="sxs-lookup"><span data-stu-id="cb2f9-106">The **Issues** tool provides feedback in the following categories:</span></span>
*  <span data-ttu-id="cb2f9-107">辅助功能。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-107">Accessibility.</span></span>
*  <span data-ttu-id="cb2f9-108">跨浏览器的兼容性。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-108">Compatibility across browsers.</span></span>
*  <span data-ttu-id="cb2f9-109">性能。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-109">Performance.</span></span>
*  <span data-ttu-id="cb2f9-110">渐进式 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-110">Progressive Web Apps.</span></span>
*  <span data-ttu-id="cb2f9-111">安全性。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-111">Security.</span></span>
*  <span data-ttu-id="cb2f9-112">其他。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-112">Other.</span></span>

<span data-ttu-id="cb2f9-113">问题工具**中**的反馈由多个源提供，包括 Chromium 平台、Deque 轴、MDN 浏览器兼容性数据和 webhint。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-113">Feedback in the **Issues** tool is provided by several sources, including the Chromium platform, Deque axe, MDN browser compatibility data, and webhint.</span></span>  <span data-ttu-id="cb2f9-114">有关填充问题工具的这些反馈 **源的信息，** 请导航到：</span><span class="sxs-lookup"><span data-stu-id="cb2f9-114">For information about these sources of feedback that populate the **Issues** tool, navigate to:</span></span>
*  [<span data-ttu-id="cb2f9-115">axe 工具概述</span><span class="sxs-lookup"><span data-stu-id="cb2f9-115">axe Tools Overview</span></span>][DequeAxe]
*  [<span data-ttu-id="cb2f9-116">browser-compat-data 存储库</span><span class="sxs-lookup"><span data-stu-id="cb2f9-116">browser-compat-data repo</span></span>][MDNCompat]
*  [<span data-ttu-id="cb2f9-117">webhint</span><span class="sxs-lookup"><span data-stu-id="cb2f9-117">webhint</span></span>][webhintIo]


## <a name="open-the-issues-tool"></a><span data-ttu-id="cb2f9-118">打开问题工具</span><span class="sxs-lookup"><span data-stu-id="cb2f9-118">Open the Issues tool</span></span>

<span data-ttu-id="cb2f9-119">执行以下步骤以使用演示 **页面打开** 问题工具。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-119">Perform the following steps to open the **Issues** tool using a demo page.</span></span>


1.  <span data-ttu-id="cb2f9-120">导航到包含要修复的问题的网页。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-120">Navigate to a webpage that contains issues to fix.</span></span>  <span data-ttu-id="cb2f9-121">例如，在一 [个新选项卡或窗口中][A11ytestingPagewitherrors] 打开辅助功能测试演示页面。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-121">For example, open the [accessibility-testing demo page][A11ytestingPagewitherrors] in a new tab or window.</span></span>

1.  <span data-ttu-id="cb2f9-122">打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-122">Open DevTools.</span></span>  <span data-ttu-id="cb2f9-123">几秒钟后，"问题"计数器 **\ (** ![ Issues 计数器 \) 显示在 ](../media/issues-counter-icon.msft.png) DevTools 的右上角。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-123">After a few seconds, the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\) appears, in the upper right corner of DevTools.</span></span>  <span data-ttu-id="cb2f9-124">问题计数器中的问题数可能不同。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-124">The number of issues in your Issues counter might be different.</span></span>

1.  <span data-ttu-id="cb2f9-125">选择" **问题"计数器**。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-125">Select the **Issues counter**.</span></span>  <span data-ttu-id="cb2f9-126">" **问题** "工具将打开，并分组为不同类别的问题。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-126">The **Issues** tool opens with issues grouped into different categories.</span></span>

    :::image type="complex" source="../media/issues-tool-categories.msft.png" alt-text="演示页上的"问题"工具中的问题类别" lightbox="../media/issues-tool-categories.msft.png":::
       <span data-ttu-id="cb2f9-128">演示页上的"问题"工具中的问题类别</span><span class="sxs-lookup"><span data-stu-id="cb2f9-128">Categories of issues in the Issues tool on the demo page</span></span>
    :::image-end:::

### <a name="other-ways-to-open-the-issues-tool"></a><span data-ttu-id="cb2f9-129">打开问题工具的其他方法</span><span class="sxs-lookup"><span data-stu-id="cb2f9-129">Other ways to open the Issues tool</span></span>

<span data-ttu-id="cb2f9-130">有几种其他方法可以打开 **问题** 工具：</span><span class="sxs-lookup"><span data-stu-id="cb2f9-130">There are several additional ways to open the **Issues** tool:</span></span>
*  <span data-ttu-id="cb2f9-131">在主**面板或**" () 选择"更多工具"菜单，然后选择 **+** "问题 **"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb2f9-131">Select the **More Tools** (**+**) menu in the main panel or the **Drawer**, and then select **Issues**.</span></span>
*  <span data-ttu-id="cb2f9-132">选择 **"自定义和控制 DevTools**  >  **更多工具问题**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="cb2f9-132">Select **Customize and control DevTools** > **More tools** > **Issues**.</span></span>
*  <span data-ttu-id="cb2f9-133">在"元素"工具的 DOM **树中，** 选择并单击带 `Shift` 波浪下划线的元素名称。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-133">In the DOM tree in the **Elements** tool, select `Shift` and then click a wavy-underlined element name.</span></span>  <span data-ttu-id="cb2f9-134">或者，打开带波浪线下划线的元素上的上下文菜单，然后选择查看 **问题**。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-134">Or, open the context menu on a wavy-underlined element and then select **View issues**.</span></span>

### <a name="issues-are-automatically-ordered-by-severity"></a><span data-ttu-id="cb2f9-135">问题按严重性自动排序</span><span class="sxs-lookup"><span data-stu-id="cb2f9-135">Issues are automatically ordered by severity</span></span>

<span data-ttu-id="cb2f9-136">在每个问题类别中，首先列出错误，然后列出警告，然后列出提示。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-136">Within each category of issues, first the errors are listed, then warnings, and then tips.</span></span>

:::image type="complex" source="../media/issues-ordered-by-severity.msft.png" alt-text=""问题"工具显示按严重性排序的性能问题" lightbox="../media/issues-ordered-by-severity.msft.png":::
   <span data-ttu-id="cb2f9-138">" **问题** "工具显示按严重性排序的性能问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-138">The **Issues** tool displays Performance issues sorted by severity</span></span>
:::image-end:::

### <a name="include-third-party-issues"></a><span data-ttu-id="cb2f9-139">包括第三方问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-139">Include third-party issues</span></span>

<span data-ttu-id="cb2f9-140">若要包含由第三方网站导致的问题，请在"问题"工具顶部，选中\*\*\*\*"包括第**三**方问题"复选框。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-140">To include issues that are caused by third-party sites, at the top of the **Issues** tool, select the **Include third-party issues** checkbox.</span></span>


## <a name="expand-entries-in-the-issues-tool"></a><span data-ttu-id="cb2f9-141">展开问题工具中的条目</span><span class="sxs-lookup"><span data-stu-id="cb2f9-141">Expand entries in the Issues tool</span></span>

<span data-ttu-id="cb2f9-142">问题 **工具** 提供了适用于每个问题的其他文档和推荐的修补程序。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-142">The **Issues** tool presents additional documentation and recommended fixes to apply to each issue.</span></span>  <span data-ttu-id="cb2f9-143">若要展开问题以获取此附加信息，请选择问题，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-143">To expand an issue to get this additional information, select an issue, as follows.</span></span>

1.  <span data-ttu-id="cb2f9-144">打开新 [窗口或][A11ytestingPagewitherrors] 选项卡中的演示页面，然后打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-144">Open the [demo page][A11ytestingPagewitherrors] in a new window or tab, and then open DevTools.</span></span>

1.  <span data-ttu-id="cb2f9-145">通过选择 **问题** 计数器 **\ (** 问题计数器 \) ![ 打开问题 ](../media/issues-counter-icon.msft.png) 工具。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-145">Open the **Issues** tool by selecting the **Issues counter** \(![Issues counter](../media/issues-counter-icon.msft.png)\).</span></span>

1.  <span data-ttu-id="cb2f9-146">选择问题以展开问题。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-146">Select an issue to expand the issue.</span></span>

    :::image type="complex" source="../media/issues-tool-initial-view-accessibility-page.msft.png" alt-text=""问题"工具显示有关如何修复该问题的其他信息" lightbox="../media/issues-tool-initial-view-accessibility-page.msft.png":::
       <span data-ttu-id="cb2f9-148">" **问题** "工具显示有关如何修复该问题的其他信息</span><span class="sxs-lookup"><span data-stu-id="cb2f9-148">The **Issues** tool displaying additional information on how to fix the issue</span></span>
    :::image-end:::

<span data-ttu-id="cb2f9-149">每个显示的问题都具有以下组件：</span><span class="sxs-lookup"><span data-stu-id="cb2f9-149">Each displayed issue has the following components:</span></span>
*   <span data-ttu-id="cb2f9-150">描述问题的标题。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-150">A headline describing the issue.</span></span>
*   <span data-ttu-id="cb2f9-151">提供更多上下文和建议的解决方案的说明。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-151">A description providing more context and proposed solutions.</span></span>
*   <span data-ttu-id="cb2f9-152">链接到\*\*\*\* DevTools 中的资源的受影响的资源部分，如**元素**、**源**或**网络**工具。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-152">An **AFFECTED RESOURCES** section that links to resources in DevTools, such as the **Elements**, **Sources**, or **Network** tool.</span></span>
*   <span data-ttu-id="cb2f9-153">指向更多文档的链接。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-153">Links to further documentation.</span></span>


## <a name="view-issues-in-context-of-an-associated-tool"></a><span data-ttu-id="cb2f9-154">查看关联工具上下文中的问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-154">View issues in context of an associated tool</span></span>

<span data-ttu-id="cb2f9-155">问题工具**中**的问题可能包括打开不同工具（如元素、源或网络工具）**的一**个或多个\*\*\*\* 链接。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb2f9-155">An issue in the **Issues** tool may include one or more links that open different tools, such as the **Elements**, **Sources**, or **Network** tool.</span></span> <span data-ttu-id="cb2f9-156">可以打开其中一个工具来执行其他疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-156">You can open one of these tools to perform additional troubleshooting steps.</span></span> <span data-ttu-id="cb2f9-157">若要从问题工具打开 **链接的工具，** 请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-157">To open a linked tool from the **Issues** tool, perform the following steps.</span></span>

1.  <span data-ttu-id="cb2f9-158">如上一部分所述，打开演示页面，然后在问题工具 **中展开问题** 。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-158">As described in the previous section, open the demo page and then expand an issue in the **Issues** tool.</span></span>

1.  <span data-ttu-id="cb2f9-159">在 **"受影响的资源**  >  **打开"中**，选择工具名称。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-159">In **AFFECTED RESOURCES** > **Open in**, select the tool name.</span></span>  <span data-ttu-id="cb2f9-160">受影响的资源将显示在所选工具中。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-160">The affected resource is displayed in the selected tool.</span></span>

    :::image type="complex" source="../media/issues-tool-affected-resource-opens-elements-tool.msft.png" alt-text="从"问题"工具中选择打开受影响资源的工具" lightbox="../media/issues-tool-affected-resource-opens-elements-tool.msft.png":::
       <span data-ttu-id="cb2f9-162">从"问题"工具中选择打开受影响资源的工具</span><span class="sxs-lookup"><span data-stu-id="cb2f9-162">Select a tool to open an affected resource from within the Issues tool</span></span>
    :::image-end:::

    <span data-ttu-id="cb2f9-163">展开的问题可能有"网络 **"** 链接，以在"网络"工具中 **显示受影响的** 资源。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-163">An expanded issue may have a **Network** link, to display the affected resource in the **Network** tool.</span></span>

    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="选择网络资源链接时，将打开"网络"工具" lightbox="../media/issues-tab-view-issue.msft.png":::
    <span data-ttu-id="cb2f9-165">选择 **网络** 资源链接时， **将打开"网络"** 工具</span><span class="sxs-lookup"><span data-stu-id="cb2f9-165">The **Network** tool opens when you select a **Network** resource link</span></span>
    :::image-end:::


## <a name="open-issues-from-the-dom-tree"></a><span data-ttu-id="cb2f9-166">打开 DOM 树中的问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-166">Open issues from the DOM tree</span></span>

<span data-ttu-id="cb2f9-167">如果元素具有关联问题，则 **"** 元素"工具中的 DOM 树在元素名称下显示波浪下划线。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-167">If an element has an associated issue, the DOM tree in the **Elements** tool shows a wavy underline under the element name.</span></span>  <span data-ttu-id="cb2f9-168">可以打开上下文菜单 (右键单击) ，然后选择查看问题，或者选择并左键单击带波浪\*\*\*\* 下划线 `Shift` 的元素。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-168">You can open the context menu (right-click) on the element and then select **View issues**, or select `Shift` and left-click the element with the wavy underline.</span></span>

<span data-ttu-id="cb2f9-169">若要对 DOM 树中带波浪下划线的元素显示问题，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-169">To display an issue for elements with wavy underlines in the DOM tree, perform the following steps.</span></span>

1.  <span data-ttu-id="cb2f9-170">在一个新选项卡或窗口中 [打开一个页面][A11ytestingPagewitherrors]，如演示页面。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-170">Open a page, such as the [demo page][A11ytestingPagewitherrors], in a new tab or window.</span></span>

1.  <span data-ttu-id="cb2f9-171">打开 DevTools，然后选择" **元素"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-171">Open DevTools and then select the **Elements** tab.</span></span>

1.  <span data-ttu-id="cb2f9-172">在 DOM 树中，展开 `<body>`  >  `<header>`  >  `<form>` 。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-172">In the DOM tree, expand `<body>` > `<header>` > `<form>`.</span></span>  <span data-ttu-id="cb2f9-173">请注意， `<input>` 元素具有波浪下划线。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-173">Notice that the `<input>` element has a wavy underline.</span></span>

    :::image type="complex" source="../media/issues-wavy-underlines-dom-tree.msft.png" alt-text="元素工具中 DOM 树中带波浪下划线的问题" lightbox="../media/issues-wavy-underlines-dom-tree.msft.png":::
       <span data-ttu-id="cb2f9-175">元素工具中 **DOM 树中带** 波浪 **下划线** 的问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-175">Wavy-underlined issues in the **DOM tree** in the **Elements** tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="cb2f9-176">将鼠标悬停在 `<input>` 元素上。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-176">Hover over the `<input>` element.</span></span>  <span data-ttu-id="cb2f9-177">工具提示显示有关该问题的信息。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-177">A tooltip displays information about the issue.</span></span>

1.  <span data-ttu-id="cb2f9-178">打开带波浪下划线的元素上的上下文菜单，然后选择"**查看问题"。**</span><span class="sxs-lookup"><span data-stu-id="cb2f9-178">Open the context menu on the element with the wavy underline, and then select **View issues**.</span></span>  <span data-ttu-id="cb2f9-179">" **问题** "工具将打开并显示与该元素关联的问题。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-179">The **Issues** tool opens and displays the issue that's associated with that element.</span></span>

    :::image type="complex" source="../media/issues-opened-from-dom-tree-wavy-underline.msft.png" alt-text="有关 DOM 树中带波浪线下划线的元素的问题的详细信息" lightbox="../media/issues-opened-from-dom-tree-wavy-underline.msft.png":::
       <span data-ttu-id="cb2f9-181">有关**DOM**树中带波浪线下划线的元素的问题的详细信息</span><span class="sxs-lookup"><span data-stu-id="cb2f9-181">Details about issues on a wavy-underlined element in the **DOM tree**</span></span>
    :::image-end:::


## <a name="see-also"></a><span data-ttu-id="cb2f9-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb2f9-182">See also</span></span>

* [<span data-ttu-id="cb2f9-183">自动测试网页中的辅助功能问题</span><span class="sxs-lookup"><span data-stu-id="cb2f9-183">Automatically test a webpage for accessibility issues</span></span>](../accessibility/test-issues-tool.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="cb2f9-184">联系 Microsoft Edge 开发人员工具团队</span><span class="sxs-lookup"><span data-stu-id="cb2f9-184">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]

<!-- links -->
[DevtoolsOpenIndex]: ../open/index.md "打开 Microsoft Edge 开发人员工具 | Microsoft Docs"
<!-- external links -->
[A11ytestingPagewitherrors]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示页面|Microsoft Docs"
[DequeAxe]: https://www.deque.com/axe "axe 工具|Deque"
[MDNCompat]: https://github.com/mdn/browser-compat-data "MDN 浏览器兼容性|GitHub"
[webhintIo]: https://webhint.io "webhint.io"

> [!NOTE]
> <span data-ttu-id="cb2f9-190">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-190">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>
> <span data-ttu-id="cb2f9-191">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/issues/index) 由 [Sam Dutton][SamDutton] \ (Developer Advocate\) 。</span><span class="sxs-lookup"><span data-stu-id="cb2f9-191">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>
<span data-ttu-id="cb2f9-192">[ ![ Creative Commons License][CCby4Image]][CCA4IL] This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span><span class="sxs-lookup"><span data-stu-id="cb2f9-192">[![Creative Commons License][CCby4Image]][CCA4IL] This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>

[CCA4IL]: https://creativecommons.org/licenses/by/4.0
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques
[SamDutton]: https://developers.google.com/web/resources/contributors#sam-dutton
