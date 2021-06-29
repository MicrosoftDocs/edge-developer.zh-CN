---
description: 在 DevTools 内使用 Lighthouse 测试辅助功能。
title: 使用 Lighthouse 测试辅助功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 822c25240ba30df31416ca783bf48d6d9ba52ed2
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624631"
---
<!-- this article was created on 05/11/2021 by moving a section out from the "Accessibility reference" article (reference.md) -->
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <a name="test-accessibility-using-lighthouse"></a><span data-ttu-id="a7313-104">使用 Lighthouse 测试辅助功能</span><span class="sxs-lookup"><span data-stu-id="a7313-104">Test accessibility using Lighthouse</span></span>

<span data-ttu-id="a7313-105">可以在 DevTools 内使用 Lighthouse 审核页面的辅助功能并生成报告。</span><span class="sxs-lookup"><span data-stu-id="a7313-105">You can use Lighthouse from within DevTools to audit the accessibility of a page and generate a report.</span></span> <span data-ttu-id="a7313-106">可以使用 Lighthouse 工具确定：</span><span class="sxs-lookup"><span data-stu-id="a7313-106">You can use the Lighthouse tool to determine:</span></span>

*   <span data-ttu-id="a7313-107">是否已为屏幕阅读器正确标记页面。</span><span class="sxs-lookup"><span data-stu-id="a7313-107">Whether a page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="a7313-108">页面上的文本元素是否具有足够的对比率（使用颜色选取器）。</span><span class="sxs-lookup"><span data-stu-id="a7313-108">Whether the text elements on a page have sufficient contrast ratios using the Color Picker.</span></span> <span data-ttu-id="a7313-109">有关详细信息，请导航到使用颜色选取器 [测试文本颜色对比度](color-picker.md)。</span><span class="sxs-lookup"><span data-stu-id="a7313-109">For more information, navigate to [Test text-color contrast using the Color Picker](color-picker.md).</span></span>   

> [!NOTE]
> <span data-ttu-id="a7313-110">**Lighthouse**工具提供指向第三方网站上承载的内容的链接。</span><span class="sxs-lookup"><span data-stu-id="a7313-110">The **Lighthouse** tool provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="a7313-111">Microsoft 不负责也不控制这些网站的内容，并且可能会收集任何数据。</span><span class="sxs-lookup"><span data-stu-id="a7313-111">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="a7313-112">若要使用 Lighthouse 工具审核页面，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a7313-112">To audit a page using the Lighthouse tool, perform the following steps.</span></span>

1.  <span data-ttu-id="a7313-113">导航到要审核的 URL。</span><span class="sxs-lookup"><span data-stu-id="a7313-113">Navigate to the URL that you want to audit.</span></span>
1.  <span data-ttu-id="a7313-114">在 DevTools 中，选择 **"Lighthouse"** 工具。</span><span class="sxs-lookup"><span data-stu-id="a7313-114">In DevTools, select the **Lighthouse** tool.</span></span>  <span data-ttu-id="a7313-115">将显示配置选项。</span><span class="sxs-lookup"><span data-stu-id="a7313-115">Configuration options are displayed.</span></span>
    
    :::image type="complex" source="../media/accessibility-lighthouse.msft.png" alt-text="浅色配置选项" lightbox="../media/accessibility-lighthouse.msft.png":::
       <span data-ttu-id="a7313-117">浅色配置选项</span><span class="sxs-lookup"><span data-stu-id="a7313-117">Lighthouse configuration options</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="a7313-118">对于 **"** 设备 **"，** 如果要模拟移动设备，请选择"移动"。</span><span class="sxs-lookup"><span data-stu-id="a7313-118">For **Device**, select **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="a7313-119">此选项将更改用户代理字符串并调整视口的大小。</span><span class="sxs-lookup"><span data-stu-id="a7313-119">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="a7313-120">此选项可能会影响审核结果。</span><span class="sxs-lookup"><span data-stu-id="a7313-120">This option can affect the audit results.</span></span>
1.  <span data-ttu-id="a7313-121">在"**类别"** 部分，选择 **"辅助功能"。**</span><span class="sxs-lookup"><span data-stu-id="a7313-121">In the **Categories** section, select **Accessibility**.</span></span>
1.  <span data-ttu-id="a7313-122">选择 **"生成报告"。**</span><span class="sxs-lookup"><span data-stu-id="a7313-122">Select **Generate report**.</span></span> <span data-ttu-id="a7313-123">10 到 30 秒后，DevTools 将显示一个报告。</span><span class="sxs-lookup"><span data-stu-id="a7313-123">After 10 to 30 seconds, DevTools displays a report.</span></span>  <span data-ttu-id="a7313-124">该报告提供了有关如何提高页面辅助功能的提示。</span><span class="sxs-lookup"><span data-stu-id="a7313-124">The report gives tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-lighthouse-result.msft.png" alt-text="辅助功能类别的 Lighthouse 报告" lightbox="../media/accessibility-lighthouse-result.msft.png":::
       <span data-ttu-id="a7313-126">辅助功能类别的 Lighthouse**报告**</span><span class="sxs-lookup"><span data-stu-id="a7313-126">A Lighthouse report for the **Accessibility** category</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="a7313-127">选择报告中的某个项目以了解有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7313-127">Select an item in the report to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-lighthouse-result-issue-expanded.msft.png" alt-text="Lighthouse 报告中的扩展问题" lightbox="../media/accessibility-lighthouse-result-issue-expanded.msft.png":::
       <span data-ttu-id="a7313-129">Lighthouse 报告中的扩展问题</span><span class="sxs-lookup"><span data-stu-id="a7313-129">An expanded issue in a Lighthouse report</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="a7313-130">选择 **"了解更多** "链接以查看问题的文档。</span><span class="sxs-lookup"><span data-stu-id="a7313-130">Select the **Learn more** link to view the documentation of the issue.</span></span>
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="查看问题的文档" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="a7313-132">查看问题的文档</span><span class="sxs-lookup"><span data-stu-id="a7313-132">View the documentation of an issue</span></span>
    :::image-end:::  

1.  <span data-ttu-id="a7313-133">若要返回到配置选项，请在 DevTools 中选择"\*\*\*\* 执行审核 `+` () "</span><span class="sxs-lookup"><span data-stu-id="a7313-133">To return to the configuration options, in DevTools, select **Perform an audit** (`+`).</span></span>    


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="a7313-134">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="a7313-134">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


> [!NOTE]
> <span data-ttu-id="a7313-135">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a7313-135">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a7313-136">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="a7313-136">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="a7313-138">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a7313-138">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- links -->  
[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd "axe - Web 辅助功能测试 - Chrome Web Store"  
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
