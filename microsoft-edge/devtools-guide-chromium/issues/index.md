---
title: 查找并修复 Microsoft Edge DevTools 问题工具的相关问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bad9e9d99f0d2f3179784920fc334823289b9f99
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992818"
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

# <span data-ttu-id="0fdeb-103">查找并修复 Microsoft Edge DevTools 问题工具的相关问题</span><span class="sxs-lookup"><span data-stu-id="0fdeb-103">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>  

<span data-ttu-id="0fdeb-104">Microsoft Edge DevTools 中的 " **问题** " 工具减少了 **控制台**的通知 fatigue 和混乱。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-104">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="0fdeb-105">用于查找浏览器检测到的问题的解决方案，例如 cookie 问题和混合内容。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-105">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span></span>  

> [!NOTE]
> <span data-ttu-id="0fdeb-106">在 Microsoft Edge 84 中，" **问题** " 工具支持三种类型的问题：</span><span class="sxs-lookup"><span data-stu-id="0fdeb-106">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span></span>  
> *   [<span data-ttu-id="0fdeb-107">Cookie 问题</span><span class="sxs-lookup"><span data-stu-id="0fdeb-107">Cookie problems</span></span>][MDNSameSiteCookies]  
> *   [<span data-ttu-id="0fdeb-108">混合内容</span><span class="sxs-lookup"><span data-stu-id="0fdeb-108">Mixed content</span></span>][MDNMixedContent]  
> *   [<span data-ttu-id="0fdeb-109">COEP 问题</span><span class="sxs-lookup"><span data-stu-id="0fdeb-109">COEP issues</span></span>][W3CCOEPSpec]
> 
> <span data-ttu-id="0fdeb-110">Microsoft Edge DevTools 团队计划在未来版本的 Microsoft Edge 中支持更多问题类型。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-110">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span></span>  

## <span data-ttu-id="0fdeb-111">打开 DevTools 抽屉中的 "问题" 工具</span><span class="sxs-lookup"><span data-stu-id="0fdeb-111">Open the Issues tool in the DevTools drawer</span></span>  

1.  <span data-ttu-id="0fdeb-112">访问包含要修复的问题的页面（如 [samesite-sandbox.glitch.me][GlitchSamesiteSandbox]）。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-112">Visit a page, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span></span>  
1.  <span data-ttu-id="0fdeb-113">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-113">[Open DevTools][DevtoolsOpen].</span></span>  
1.  :::row:::
       :::column span="":::
          <span data-ttu-id="0fdeb-114">在黄色警告栏中选择 " **转到问题** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-114">Select the **Go to Issues** button in the yellow warning bar.</span></span>  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-open-issues-tab.msft.png":::
             <span data-ttu-id="0fdeb-116">检测到问题时黄色警告栏中的 " **转到问题** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-116">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="0fdeb-117">或者，从 "**更多工具**" 菜单中选择 "**问题**"。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-117">Alternatively, select **Issues** from the **More tools** menu.</span></span>  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media//issues-more-tools-menu.msft.png":::
             <span data-ttu-id="0fdeb-119">"**其他工具**" 菜单中的 "**问题**" 工具</span><span class="sxs-lookup"><span data-stu-id="0fdeb-119">**Issues** tool in **More tools** menu</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="0fdeb-120">如有必要，请选择 " **重新加载页面** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-120">Select the **Reload page** button, if necessary.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-tab-before-refresh.msft.png":::
       <span data-ttu-id="0fdeb-122">带有 "**重新加载页面**" 按钮的 DevTools 抽屉中的**问题**工具</span><span class="sxs-lookup"><span data-stu-id="0fdeb-122">**Issues** tool in the DevTools Drawer with **Reload page** button</span></span>  
    :::image-end:::  

    <span data-ttu-id="0fdeb-123">**控制台**中报告的问题非常难以理解，例如下图中的 cookie 警告。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-123">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span></span>  <span data-ttu-id="0fdeb-124">根据报告的问题，可能不清楚您必须执行的操作。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-124">Based upon the reported issues, it may not be clear what you must do.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-tab-after-refresh.msft.png":::
       <span data-ttu-id="0fdeb-126">DevTools 抽屉中有三个 cookie 问题的**问题**工具</span><span class="sxs-lookup"><span data-stu-id="0fdeb-126">**Issues** tool in the DevTools Drawer with three cookie issues</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0fdeb-127">在 "问题" 工具中查看项目</span><span class="sxs-lookup"><span data-stu-id="0fdeb-127">View items in the Issues tool</span></span>  

<span data-ttu-id="0fdeb-128">DevTools 抽屉中的 " **问题** " 工具以结构化、聚合和可操作的方式表示警告。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-128">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span></span>  

1.  <span data-ttu-id="0fdeb-129">选择 " **问题** " 工具中的项目以获取有关如何解决问题和查找受影响的资源的指南。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-129">Select an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-tab-issue-open.msft.png":::
       <span data-ttu-id="0fdeb-131">将**跨网站 Cookie 标记为安全**问题在 "**问题**" 工具中打开</span><span class="sxs-lookup"><span data-stu-id="0fdeb-131">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="0fdeb-132">每个项都有四个组件：</span><span class="sxs-lookup"><span data-stu-id="0fdeb-132">Each item has four components:</span></span>  
    
    *   <span data-ttu-id="0fdeb-133">描述问题的标题。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-133">A headline describing the issue.</span></span>  
    *   <span data-ttu-id="0fdeb-134">提供上下文和解决方案的说明。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-134">A description providing the context and the solution.</span></span>  
    *   <span data-ttu-id="0fdeb-135">链接到相应 DevTools 上下文（如网络面板）中的资源的 **受影响的资源** 部分。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-135">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span></span>  
    *   <span data-ttu-id="0fdeb-136">链接到更多指南。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-136">Links to further guidance.</span></span>  
    
1.  <span data-ttu-id="0fdeb-137">选择 **受影响的资源** 中的项目以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-137">Select items in **AFFECTED RESOURCES** to view details.</span></span>  <span data-ttu-id="0fdeb-138">在以下示例中，将 **跨网站 Cookie 标记为安全** 问题会影响一个 cookie 和两个请求。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-138">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-tab-affected-resources.msft.png":::
       <span data-ttu-id="0fdeb-140">受影响的资源在 DevTools 抽屉中的 " **问题** " 工具中打开</span><span class="sxs-lookup"><span data-stu-id="0fdeb-140">Affected resources open in the **Issues** tool in the DevTools Drawer</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="0fdeb-141">在上下文中查看问题</span><span class="sxs-lookup"><span data-stu-id="0fdeb-141">View issues in context</span></span>  

1.  <span data-ttu-id="0fdeb-142">选择资源链接以在 DevTools 内的相应上下文中查看项目。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-142">Select a resource link to view the item in the appropriate context within DevTools.</span></span>  <span data-ttu-id="0fdeb-143">在以下示例中，在 `samesite-sandbox.glitch.me` " **请求** " 下选择 "显示附加到该请求的 cookie"。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-143">In the following example, select `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-tab-view-request.msft.png":::
       <span data-ttu-id="0fdeb-145">在 DevTools **网络** 面板中查看受影响的 cookie</span><span class="sxs-lookup"><span data-stu-id="0fdeb-145">View the affected cookie in the DevTools **Network** panel</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="0fdeb-146">滚动查看有问题的项目：对于以下示例，该 `ck02` cookie。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-146">Scroll to view the item with a problem: for the following example, the `ck02` cookie.</span></span>  <span data-ttu-id="0fdeb-147">将鼠标悬停在 **SameSite** 列上，以查看 `None` 检测到的问题的值。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-147">Hover over the **SameSite** column to see the `None` value that the issue detected.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="检测到问题时，在黄色警告栏中的 &quot;转到问题&quot; 按钮" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` <span data-ttu-id="0fdeb-149">**SameSite** `ck02` DevTools**网络**面板中的 cookie 的 SameSite 列中的值</span><span class="sxs-lookup"><span data-stu-id="0fdeb-149">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** panel</span></span>  
    :::image-end:::  

## <span data-ttu-id="0fdeb-150">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="0fdeb-150">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite cookie 测试 |故障"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混合内容 |MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "跨起源 Embedder 策略 |Web Incubator 社区组"  

> [!NOTE]
> <span data-ttu-id="0fdeb-156">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-156">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0fdeb-157">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/issues/index) ，由 [Sam Dutton][SamDutton] (开发人员倡导 \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-157">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>  
[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0fdeb-159">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0fdeb-159">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
