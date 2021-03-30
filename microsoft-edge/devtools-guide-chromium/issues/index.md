---
description: 使用问题工具查找并修复网站问题。
title: 查找并修复 Microsoft Edge DevTools 问题工具的问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e16bd926ea5bae35ad82f54ac5d1ae2028e3c59d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398971"
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

# <a name="find-and-fix-problems-with-the-microsoft-edge-devtools-issues-tool"></a><span data-ttu-id="eebac-104">查找并修复 Microsoft Edge DevTools 问题工具的问题</span><span class="sxs-lookup"><span data-stu-id="eebac-104">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>  

<span data-ttu-id="eebac-105">Microsoft **Edge** DevTools 中的"问题"工具可以减少控制台的通知疲劳和**混乱。**</span><span class="sxs-lookup"><span data-stu-id="eebac-105">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="eebac-106">使用它查找浏览器检测到的问题（如 Cookie 问题和混合内容）的解决方案。</span><span class="sxs-lookup"><span data-stu-id="eebac-106">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span></span>  

> [!NOTE]
> <span data-ttu-id="eebac-107">在 Microsoft Edge 84 中， **问题** 工具支持三种类型的问题：</span><span class="sxs-lookup"><span data-stu-id="eebac-107">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span></span>  
> *   [<span data-ttu-id="eebac-108">Cookie 问题</span><span class="sxs-lookup"><span data-stu-id="eebac-108">Cookie problems</span></span>][MDNSameSiteCookies]  
> *   [<span data-ttu-id="eebac-109">混合内容</span><span class="sxs-lookup"><span data-stu-id="eebac-109">Mixed content</span></span>][MDNMixedContent]  
> *   [<span data-ttu-id="eebac-110">COEP 问题</span><span class="sxs-lookup"><span data-stu-id="eebac-110">COEP issues</span></span>][W3CCOEPSpec]
> 
> <span data-ttu-id="eebac-111">Microsoft Edge DevTools 团队计划在未来版本的 Microsoft Edge 中支持更多问题类型。</span><span class="sxs-lookup"><span data-stu-id="eebac-111">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span></span>  

## <a name="open-the-issues-tool-in-the-devtools-drawer"></a><span data-ttu-id="eebac-112">在 DevTools 箱中打开"问题"工具</span><span class="sxs-lookup"><span data-stu-id="eebac-112">Open the Issues tool in the DevTools drawer</span></span>  

1.  <span data-ttu-id="eebac-113">导航到包含要修复samesite-sandbox.glitch.me的网页[][GlitchSamesiteSandbox]，例如 samesite-sandbox.glitch.me。</span><span class="sxs-lookup"><span data-stu-id="eebac-113">Navigate to a webpage, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span></span>  
1.  <span data-ttu-id="eebac-114">[打开 DevTools][DevtoolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="eebac-114">[Open DevTools][DevtoolsOpen].</span></span>  
1.  :::row:::
       :::column span="":::
          <span data-ttu-id="eebac-115">选择黄色 **警告栏中** 的"转到问题"按钮。</span><span class="sxs-lookup"><span data-stu-id="eebac-115">Choose the **Go to Issues** button in the yellow warning bar.</span></span>  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="在检测到问题时，转到黄色警告栏中的问题按钮" lightbox="../media/issues-open-issues-tab.msft.png":::
             <span data-ttu-id="eebac-117">检测到 **问题时** ，黄色警告栏中的"转到问题"按钮。</span><span class="sxs-lookup"><span data-stu-id="eebac-117">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="eebac-118">或者，从"**更多**工具"**菜单中选择"问题"。**</span><span class="sxs-lookup"><span data-stu-id="eebac-118">Alternatively, choose **Issues** from the **More tools** menu.</span></span>  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="更多工具菜单中的问题工具" lightbox="../media//issues-more-tools-menu.msft.png":::
             <span data-ttu-id="eebac-120">**"** 更多工具 **"菜单中的"问题"** 工具</span><span class="sxs-lookup"><span data-stu-id="eebac-120">**Issues** tool in **More tools** menu</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="eebac-121">如有必要 **，选择"重新加载** "页面按钮。</span><span class="sxs-lookup"><span data-stu-id="eebac-121">Choose the **Reload page** button, if necessary.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="DevTools Drawer 中重新加载页面按钮中的问题工具" lightbox="../media/issues-tab-before-refresh.msft.png":::
       <span data-ttu-id="eebac-123">**DevTools** Drawer 中"重新加载"页面 **按钮中的"问题"** 工具</span><span class="sxs-lookup"><span data-stu-id="eebac-123">**Issues** tool in the DevTools Drawer with **Reload page** button</span></span>  
    :::image-end:::  

    <span data-ttu-id="eebac-124">控制台中报告 **的问题很难** 理解，如下图中的 Cookie 警告。</span><span class="sxs-lookup"><span data-stu-id="eebac-124">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span></span>  <span data-ttu-id="eebac-125">根据报告的问题，可能不明确您必须执行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="eebac-125">Based upon the reported issues, it may not be clear what you must do.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="具有三个 Cookie 问题的 DevTools Drawer 中的问题工具" lightbox="../media/issues-tab-after-refresh.msft.png":::
       <span data-ttu-id="eebac-127">**具有** 三个 Cookie 问题的 DevTools Drawer 中的问题工具</span><span class="sxs-lookup"><span data-stu-id="eebac-127">**Issues** tool in the DevTools Drawer with three cookie issues</span></span>  
    :::image-end:::  
    
## <a name="view-items-in-the-issues-tool"></a><span data-ttu-id="eebac-128">查看问题工具中的项目</span><span class="sxs-lookup"><span data-stu-id="eebac-128">View items in the Issues tool</span></span>  

<span data-ttu-id="eebac-129">DevTools Drawer 中的"问题"工具以结构化、聚合且可操作的方式显示警告。 </span><span class="sxs-lookup"><span data-stu-id="eebac-129">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span></span>  

1.  <span data-ttu-id="eebac-130">在"问题"工具 **中选择** 一个项目，获取有关如何解决问题和查找受影响资源的指南。</span><span class="sxs-lookup"><span data-stu-id="eebac-130">Choose an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="将跨站点 Cookie 标记为问题工具中打开的安全问题" lightbox="../media/issues-tab-issue-open.msft.png":::
       <span data-ttu-id="eebac-132">**将跨站点 Cookie 标记为**"问题"工具中打开**的安全问题**</span><span class="sxs-lookup"><span data-stu-id="eebac-132">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="eebac-133">每个项目都有四个组件：</span><span class="sxs-lookup"><span data-stu-id="eebac-133">Each item has four components:</span></span>  
    
    *   <span data-ttu-id="eebac-134">描述问题的标题。</span><span class="sxs-lookup"><span data-stu-id="eebac-134">A headline describing the issue.</span></span>  
    *   <span data-ttu-id="eebac-135">提供上下文和解决方案的说明。</span><span class="sxs-lookup"><span data-stu-id="eebac-135">A description providing the context and the solution.</span></span>  
    *   <span data-ttu-id="eebac-136">链接到 **相应** DevTools 上下文（如网络面板）中的资源的"受影响资源"部分。</span><span class="sxs-lookup"><span data-stu-id="eebac-136">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span></span>  
    *   <span data-ttu-id="eebac-137">指向进一步指南的链接。</span><span class="sxs-lookup"><span data-stu-id="eebac-137">Links to further guidance.</span></span>  
    
1.  <span data-ttu-id="eebac-138">选择受影响 **资源中的项目** 以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="eebac-138">Choose items in **AFFECTED RESOURCES** to view details.</span></span>  <span data-ttu-id="eebac-139">在下面的示例中，将 **跨站点 Cookie** 标记为安全问题会影响一个 Cookie 和两个请求。</span><span class="sxs-lookup"><span data-stu-id="eebac-139">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="受影响的资源在问题工具中打开" lightbox="../media/issues-tab-affected-resources.msft.png":::
       <span data-ttu-id="eebac-141">受影响的资源在 DevTools **的"** 问题"工具中打开</span><span class="sxs-lookup"><span data-stu-id="eebac-141">Affected resources open in the **Issues** tool in the DevTools Drawer</span></span>  
    :::image-end:::  
    
## <a name="view-issues-in-context"></a><span data-ttu-id="eebac-142">查看上下文中的问题</span><span class="sxs-lookup"><span data-stu-id="eebac-142">View issues in context</span></span>  

1.  <span data-ttu-id="eebac-143">选择资源链接以查看 DevTools 中相应上下文中的项目。</span><span class="sxs-lookup"><span data-stu-id="eebac-143">Choose a resource link to view the item in the appropriate context within DevTools.</span></span>  <span data-ttu-id="eebac-144">在下面的示例中，选择 `samesite-sandbox.glitch.me` "请求 **"** 下以显示附加到该请求的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="eebac-144">In the following example, choose `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="在 DevTools 网络工具中查看受影响的 Cookie" lightbox="../media/issues-tab-view-request.msft.png":::
       <span data-ttu-id="eebac-146">在 DevTools 网络工具中 **查看受影响的** Cookie</span><span class="sxs-lookup"><span data-stu-id="eebac-146">View the affected cookie in the DevTools **Network** tool</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="eebac-147">滚动以查看存在问题的项目：对于以下示例 `ck02` ，Cookie。</span><span class="sxs-lookup"><span data-stu-id="eebac-147">Scroll to view the item with a problem:  for the following example, the `ck02` cookie.</span></span>  <span data-ttu-id="eebac-148">将鼠标 **悬停在 SameSite** 列上，查看 `None` 检测到问题的值。</span><span class="sxs-lookup"><span data-stu-id="eebac-148">Hover on the **SameSite** column to review the `None` value that the issue detected.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="DevTools 网络工具中 ck02 Cookie 的 SameSite 列中没有值" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` <span data-ttu-id="eebac-150">DevTools **网络** 工具中 Cookie 的 `ck02` SameSite **列中** 的值</span><span class="sxs-lookup"><span data-stu-id="eebac-150">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** tool</span></span>  
    :::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="eebac-151">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="eebac-151">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite cookie 测试|小故障"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookie |MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "混合内容|MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "跨源嵌入者策略|Web Incubator 社区组"  

> [!NOTE]
> <span data-ttu-id="eebac-157">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="eebac-157">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="eebac-158">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/issues/index) 由 [Sam.T. (\) ][SamDutton] 创作。</span><span class="sxs-lookup"><span data-stu-id="eebac-158">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>  
[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="eebac-160">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="eebac-160">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
