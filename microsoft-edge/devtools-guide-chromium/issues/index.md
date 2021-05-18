---
description: 使用问题工具查找并修复网站问题。
title: 查找并修复开发人员工具Microsoft Edge工具的问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 64954d632416f7d1353269d04c1550ca7a0652b7
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564180"
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
# <a name="find-and-fix-problems-with-the-microsoft-edge-devtools-issues-tool"></a><span data-ttu-id="15342-104">查找并修复开发人员工具Microsoft Edge工具的问题</span><span class="sxs-lookup"><span data-stu-id="15342-104">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>  

<span data-ttu-id="15342-105">DevTools Microsoft Edge中的问题工具可以减少控制台的通知疲劳和**混乱。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="15342-105">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="15342-106">使用它查找浏览器检测到的问题（如 Cookie 问题和混合内容）的解决方案。</span><span class="sxs-lookup"><span data-stu-id="15342-106">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span></span>  

> [!NOTE]
> <span data-ttu-id="15342-107">在 Microsoft Edge 84 中，**问题**工具支持三种类型的问题：</span><span class="sxs-lookup"><span data-stu-id="15342-107">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span></span>  
> *   [<span data-ttu-id="15342-108">Cookie 问题</span><span class="sxs-lookup"><span data-stu-id="15342-108">Cookie problems</span></span>][MDNSameSiteCookies]  
> *   [<span data-ttu-id="15342-109">混合内容</span><span class="sxs-lookup"><span data-stu-id="15342-109">Mixed content</span></span>][MDNMixedContent]  
> *   [<span data-ttu-id="15342-110">COEP 问题</span><span class="sxs-lookup"><span data-stu-id="15342-110">COEP issues</span></span>][W3CCOEPSpec]
> 
> <span data-ttu-id="15342-111">开发人员Microsoft Edge团队计划在未来版本的开发人员版本中支持更多Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="15342-111">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span></span>  

## <a name="open-the-issues-tool-in-the-devtools-drawer"></a><span data-ttu-id="15342-112">在 DevTools 箱中打开问题工具</span><span class="sxs-lookup"><span data-stu-id="15342-112">Open the Issues tool in the DevTools drawer</span></span>  

1.  <span data-ttu-id="15342-113">导航到包含要修复 [samesite-sandbox.glitch.me][GlitchSamesiteSandbox]的网页，例如 samesite-sandbox.glitch.me 。</span><span class="sxs-lookup"><span data-stu-id="15342-113">Navigate to a webpage, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span></span>  
1.  <span data-ttu-id="15342-114">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="15342-114">[Open DevTools][DevtoolsOpen].</span></span>  
1.  :::row:::
       :::column span="":::
          <span data-ttu-id="15342-115">选择黄色 **警告栏中** 的"转到问题"按钮。</span><span class="sxs-lookup"><span data-stu-id="15342-115">Choose the **Go to Issues** button in the yellow warning bar.</span></span>  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="在检测到问题时转到黄色警告栏中的问题按钮" lightbox="../media/issues-open-issues-tab.msft.png":::
             <span data-ttu-id="15342-117">检测到 **问题时** ，黄色警告栏中的"转到问题"按钮。</span><span class="sxs-lookup"><span data-stu-id="15342-117">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="15342-118">或者，从"更多**工具"\*\*\*\*菜单中选择"问题**"。</span><span class="sxs-lookup"><span data-stu-id="15342-118">Alternatively, choose **Issues** from the **More tools** menu.</span></span>  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="更多工具菜单中的问题工具" lightbox="../media//issues-more-tools-menu.msft.png":::
             <span data-ttu-id="15342-120">**"** 更多工具 **"菜单中的"问题"** 工具</span><span class="sxs-lookup"><span data-stu-id="15342-120">**Issues** tool in **More tools** menu</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="15342-121">如有必要 **，选择"重新加载** 页面"按钮。</span><span class="sxs-lookup"><span data-stu-id="15342-121">Choose the **Reload page** button, if necessary.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="DevTools Drawer 中的问题工具（具有重新加载页面按钮）" lightbox="../media/issues-tab-before-refresh.msft.png":::
       <span data-ttu-id="15342-123">**DevTools** Drawer 中的"问题"工具（ **具有"重新加载"页面按钮** ）</span><span class="sxs-lookup"><span data-stu-id="15342-123">**Issues** tool in the DevTools Drawer with **Reload page** button</span></span>  
    :::image-end:::  

    <span data-ttu-id="15342-124">控制台中报告 **的问题很难** 理解，如下图中的 Cookie 警告。</span><span class="sxs-lookup"><span data-stu-id="15342-124">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span></span>  <span data-ttu-id="15342-125">根据报告的问题，可能不清楚必须执行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="15342-125">Based upon the reported issues, it may not be clear what you must do.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="DevTools 箱中具有三个 Cookie 问题的问题工具" lightbox="../media/issues-tab-after-refresh.msft.png":::
       <span data-ttu-id="15342-127">**DevTools** 箱中具有三个 Cookie 问题的"问题"工具</span><span class="sxs-lookup"><span data-stu-id="15342-127">**Issues** tool in the DevTools Drawer with three cookie issues</span></span>  
    :::image-end:::  
    
## <a name="view-items-in-the-issues-tool"></a><span data-ttu-id="15342-128">查看问题工具中的项目</span><span class="sxs-lookup"><span data-stu-id="15342-128">View items in the Issues tool</span></span>  

<span data-ttu-id="15342-129">DevTools 箱中的"问题"工具以结构化、聚合且可操作的方式显示警告。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="15342-129">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span></span>  

1.  <span data-ttu-id="15342-130">在问题工具 **中选择** 一个项目，获取有关如何修复问题和查找受影响资源的指南。</span><span class="sxs-lookup"><span data-stu-id="15342-130">Choose an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="在问题工具中将跨站点 Cookie 标记为打开安全问题" lightbox="../media/issues-tab-issue-open.msft.png":::
       <span data-ttu-id="15342-132">**在"问题"工具中将** 跨站点 Cookie 标记为"打开 **安全问题** "</span><span class="sxs-lookup"><span data-stu-id="15342-132">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="15342-133">每个项目都有四个组件：</span><span class="sxs-lookup"><span data-stu-id="15342-133">Each item has four components:</span></span>  
    
    *   <span data-ttu-id="15342-134">描述问题的标题。</span><span class="sxs-lookup"><span data-stu-id="15342-134">A headline describing the issue.</span></span>  
    *   <span data-ttu-id="15342-135">提供上下文和解决方案的说明。</span><span class="sxs-lookup"><span data-stu-id="15342-135">A description providing the context and the solution.</span></span>  
    *   <span data-ttu-id="15342-136">链接到 **相应** DevTools 上下文（如网络面板）中的资源的"受影响资源"部分。</span><span class="sxs-lookup"><span data-stu-id="15342-136">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span></span>  
    *   <span data-ttu-id="15342-137">指向进一步指南的链接。</span><span class="sxs-lookup"><span data-stu-id="15342-137">Links to further guidance.</span></span>  
    
1.  <span data-ttu-id="15342-138">选择"受影响 **资源"** 中的项目以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="15342-138">Choose items in **AFFECTED RESOURCES** to view details.</span></span>  <span data-ttu-id="15342-139">在下面的示例中，将跨站点 **Cookie** 标记为安全问题会影响一个 Cookie 和两个请求。</span><span class="sxs-lookup"><span data-stu-id="15342-139">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="受影响的资源在问题工具中打开" lightbox="../media/issues-tab-affected-resources.msft.png":::
       <span data-ttu-id="15342-141">受影响的资源在 DevTools **箱** 的"问题"工具中打开</span><span class="sxs-lookup"><span data-stu-id="15342-141">Affected resources open in the **Issues** tool in the DevTools Drawer</span></span>  
    :::image-end:::  
    
## <a name="view-issues-in-context"></a><span data-ttu-id="15342-142">查看上下文中的问题</span><span class="sxs-lookup"><span data-stu-id="15342-142">View issues in context</span></span>  

1.  <span data-ttu-id="15342-143">选择资源链接以查看 DevTools 中相应上下文中的项目。</span><span class="sxs-lookup"><span data-stu-id="15342-143">Choose a resource link to view the item in the appropriate context within DevTools.</span></span>  <span data-ttu-id="15342-144">在下面的示例中，选择 `samesite-sandbox.glitch.me` "请求 **"** 下的"显示附加到该请求的 Cookie"。</span><span class="sxs-lookup"><span data-stu-id="15342-144">In the following example, choose `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="在 DevTools 网络工具中查看受影响的 Cookie" lightbox="../media/issues-tab-view-request.msft.png":::
       <span data-ttu-id="15342-146">在 DevTools 网络工具中 **查看受影响的** Cookie</span><span class="sxs-lookup"><span data-stu-id="15342-146">View the affected cookie in the DevTools **Network** tool</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="15342-147">滚动以查看存在问题的项：对于以下示例，为 `ck02` cookie。</span><span class="sxs-lookup"><span data-stu-id="15342-147">Scroll to view the item with a problem:  for the following example, the `ck02` cookie.</span></span>  <span data-ttu-id="15342-148">将鼠标悬 **停在 SameSite** 列上 `None` ，查看检测到问题的值。</span><span class="sxs-lookup"><span data-stu-id="15342-148">Hover on the **SameSite** column to review the `None` value that the issue detected.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools 网络工具中 ck02 Cookie 的 SameSite 列中无值" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` <span data-ttu-id="15342-150">DevTools 网络工具中 Cookie 的 **SameSite** `ck02` **列中** 的值</span><span class="sxs-lookup"><span data-stu-id="15342-150">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** tool</span></span>  
    :::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="15342-151">联系 Microsoft Edge 开发人员工具团队</span><span class="sxs-lookup"><span data-stu-id="15342-151">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open/index.md "打开 Microsoft Edge 开发人员工具 | Microsoft Docs"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite Cookie 测试|小故障"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混合内容|MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "跨源嵌入者策略|Web Incubator Community 组"  

> [!NOTE]
> <span data-ttu-id="15342-157">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="15342-157">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="15342-158">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/issues/index) 由 [Sam Dutton][SamDutton] \(Developer Advocate\) 。</span><span class="sxs-lookup"><span data-stu-id="15342-158">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>  
[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="15342-160">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="15342-160">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[SamDutton]: https://developers.google.com/web/resources/contributors#sam-dutton  
