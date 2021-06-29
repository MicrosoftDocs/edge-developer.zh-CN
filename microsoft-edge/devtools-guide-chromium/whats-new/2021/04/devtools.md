---
description: 波浪下划线突出显示元素工具、服务工作者更新时间线等中的代码问题。
title: 'DevTools (Microsoft Edge 91 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 69fcd29f9b4cae9ec290798b767fbe54793cb2fd
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624778"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-91"></a><span data-ttu-id="2ead5-104">DevTools (Microsoft Edge 91 中的新增) </span><span class="sxs-lookup"><span data-stu-id="2ead5-104">What's New In DevTools (Microsoft Edge 91)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="wavy-underlines-highlight-code-issues-and-improvements-in-elements-tool"></a><span data-ttu-id="2ead5-105">波浪下划线突出显示元素工具中的代码问题和改进</span><span class="sxs-lookup"><span data-stu-id="2ead5-105">Wavy underlines highlight code issues and improvements in Elements tool</span></span>  

<!--  Title: Get code hints in Elements tool  -->  
<!--  Subtitle: Wavy underlines like the ones you see in Visual Studio Code now display in the Elements tool.  Underlines alert you to code issues related to accessibility, compatibility, security, performance, and  so on.  -->  

<span data-ttu-id="2ead5-106">在大多数新式 ID 中，文本下的波浪下划线指示语法错误。</span><span class="sxs-lookup"><span data-stu-id="2ead5-106">In most modern IDEs, wavy underlines under text indicate syntax errors.</span></span>   <span data-ttu-id="2ead5-107">在 Microsoft Edge 91 或更高版本中，在"元素"工具的**DOM**视图中，HTML 下会显示**波浪下划线。**</span><span class="sxs-lookup"><span data-stu-id="2ead5-107">In Microsoft Edge version 91 or later, wavy underlines display under HTML in the **DOM** view of the **Elements** tool.</span></span>  <span data-ttu-id="2ead5-108">波浪下划线表示与辅助功能、兼容性、性能等相关的代码问题和建议。</span><span class="sxs-lookup"><span data-stu-id="2ead5-108">The wavy underlines indicate code issues and suggestions related to accessibility, compatibility, performance, and so on.</span></span>  <span data-ttu-id="2ead5-109">若要详细了解如何查看和编辑问题，请导航到使用问题工具查找和 [修复问题][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-109">For more information about how to review and edit issues, navigate to [Find and fix problems using the Issues tool][DevtoolsIssuesIndex].</span></span>  

<span data-ttu-id="2ead5-110">若要打开 **问题** 工具并了解有关该问题以及如何修复它，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="2ead5-110">To open the **Issues** tool and learn more about the issue and how to fix it, complete one of the following actions.</span></span>  

*   <span data-ttu-id="2ead5-111">选择并按住 `Shift` ，然后选择任何波浪下划线。</span><span class="sxs-lookup"><span data-stu-id="2ead5-111">Select and hold `Shift`, and then choose any wavy underline.</span></span>  
*   <span data-ttu-id="2ead5-112">完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-112">Complete the following actions.</span></span>  
    1.  <span data-ttu-id="2ead5-113">悬停在任何波浪下划线上。</span><span class="sxs-lookup"><span data-stu-id="2ead5-113">Hover on any wavy underline.</span></span>  
    1.  <span data-ttu-id="2ead5-114">打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="2ead5-114">Open the contextual menu \(right-click\).</span></span>  
    1.  <span data-ttu-id="2ead5-115">选择 **"在问题中显示"。**</span><span class="sxs-lookup"><span data-stu-id="2ead5-115">Choose **Show in Issues**.</span></span>  
        
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues.msft.png" alt-text="在"元素"工具中选择带下划线的错误" lightbox="../../media/2021/04/elements-iframe-highlight-issues.msft.png":::
         <span data-ttu-id="2ead5-117">在"元素"工具中选择 **带下划线** 的错误</span><span class="sxs-lookup"><span data-stu-id="2ead5-117">Choose the underlined error in the **Elements** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png" alt-text="在问题工具中显示错误详细信息" lightbox="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png":::
         <span data-ttu-id="2ead5-119">在问题工具 **中显示错误** 详细信息</span><span class="sxs-lookup"><span data-stu-id="2ead5-119">Display error details in the **Issues** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a><span data-ttu-id="2ead5-120">通过信息丰富的工具提示了解 DevTools</span><span class="sxs-lookup"><span data-stu-id="2ead5-120">Learn about DevTools with informative tooltips</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<!--  Title: Learn more about DevTools with DevTools Tooltips  -->  
<!--  Subtitle: Informative overlays are now available in the default DevTools interface.  -->  

<span data-ttu-id="2ead5-121">DevTools 工具提示功能可帮助你了解 DevTools 中所有不同的工具和窗格。</span><span class="sxs-lookup"><span data-stu-id="2ead5-121">The DevTools Tooltips feature helps you learn about all the different tools and panes in DevTools.</span></span>  <span data-ttu-id="2ead5-122">若要关闭工具提示，请选择 `Esc` 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-122">To turn off Tooltips, select `Esc`.</span></span>  <span data-ttu-id="2ead5-123">若要打开工具提示，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="2ead5-123">To turn on Tooltips, complete one of the following actions.</span></span>  

*   <span data-ttu-id="2ead5-124">选择 `Ctrl` + `Shift` + `H` \ (Windows/Linux\) `Cmd` + `Shift` + `H` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-124">Select `Ctrl`+`Shift`+`H` \(Windows/Linux\) or `Cmd`+`Shift`+`H` \(macOS\).</span></span>  
*   <span data-ttu-id="2ead5-125">[打开命令菜单，][DevtoolsCommandMenuIndexOpenCommandMenu] 然后键入 `tooltips` 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-125">[Open the Command Menu][DevtoolsCommandMenuIndexOpenCommandMenu] and then type `tooltips`.</span></span>  
*   <span data-ttu-id="2ead5-126">Choose **Customize and control DevTools** \ (`...` \) > **Help**Toggle the  >  **DevTools Tooltips**.</span><span class="sxs-lookup"><span data-stu-id="2ead5-126">Choose **Customize and control DevTools** \(`...`\) > **Help** > **Toggle the DevTools Tooltips**.</span></span>  

<span data-ttu-id="2ead5-127">此外，如果你打开焦点模式和 [DevTools][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] 工具提示实验，还可以选择活动栏底部的切换 **DevTools** 工具提示 \ (`?` \) **按钮**。</span><span class="sxs-lookup"><span data-stu-id="2ead5-127">Also, if you turn on the [Focus Mode and DevTools Tooltips][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] experiment, you may also choose the **Toggle the DevTools Tooltips** \(`?`\) button at the bottom of the **Activity Bar**.</span></span>  

<span data-ttu-id="2ead5-128">若要显示有关如何使用 DevTools 的信息，请打开工具提示，然后将鼠标悬停在 DevTools 的每个大纲区域上。</span><span class="sxs-lookup"><span data-stu-id="2ead5-128">To display more information about how to use the DevTools, turn on Tooltips, and then hover on each outlined region of the DevTools.</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png" alt-text="将鼠标悬停在"问题"工具突出显示区域中的任何位置，以显示更多详细信息" lightbox="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png":::
   <span data-ttu-id="2ead5-130">将鼠标悬停在"问题"工具突出显示区域 **中的任何位置，** 以显示更多详细信息</span><span class="sxs-lookup"><span data-stu-id="2ead5-130">Hover on anywhere in the highlighted region of the **Issues** tool to display more details</span></span>  
:::image-end:::  

## <a name="service-worker-update-timeline"></a><span data-ttu-id="2ead5-131">服务工作者更新时间线</span><span class="sxs-lookup"><span data-stu-id="2ead5-131">Service worker update timeline</span></span>  

<!--todo:  Update the linked [Service Worker improvements][DevtoolsServiceWorkerIndex] article.  -->  

<!--  Title: The tasks associated with your Service Worker  -->  
<!--  Subtitle: Debug with Service Worker Update Cycle  -->  

<span data-ttu-id="2ead5-132">在 Microsoft Edge 91 或更高版本中，如果您是渐进式 Web 应用开发人员或服务工作者开发人员，则使用 Application 工具将服务工作者的更新生命周期显示为**时间线**。</span><span class="sxs-lookup"><span data-stu-id="2ead5-132">In Microsoft Edge version 91 or later, if you're a Progressive Web App or Service Worker developer, display the update lifecycle of your Service Workers as a timeline in the **Application** tool.</span></span>  <span data-ttu-id="2ead5-133">此功能可帮助您了解服务工作者在下列每个阶段所花的时间。</span><span class="sxs-lookup"><span data-stu-id="2ead5-133">This feature helps you understand the time your Service Worker spends in each of the following stages.</span></span>  

*   **<span data-ttu-id="2ead5-134">安装</span><span class="sxs-lookup"><span data-stu-id="2ead5-134">Install</span></span>**  
*   **<span data-ttu-id="2ead5-135">Wait</span><span class="sxs-lookup"><span data-stu-id="2ead5-135">Wait</span></span>**  
*   **<span data-ttu-id="2ead5-136">激活</span><span class="sxs-lookup"><span data-stu-id="2ead5-136">Activate</span></span>**  
    
:::image type="complex" source="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png" alt-text="查看服务工作者的更新周期中的时间线" lightbox="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png":::
   <span data-ttu-id="2ead5-138">查看 **服务** 工作者 **的更新周期** 中的时间线</span><span class="sxs-lookup"><span data-stu-id="2ead5-138">Review the **Timeline** in the **Update Cycle** for your Service Worker</span></span>  
:::image-end:::  

<span data-ttu-id="2ead5-139">有关服务工作者的生命周期详细信息，请导航到"服务工作[线程生命周期"。][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]</span><span class="sxs-lookup"><span data-stu-id="2ead5-139">For more information about the lifecycle of your Service Workers, navigate to [The Service Worker lifecycle][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle].</span></span>  <span data-ttu-id="2ead5-140">有关在 DevTools 中为渐进式 Web 应用和服务工作者调试工具的信息，请导航到"[服务工作器改进"。][DevtoolsServiceWorkerIndex]</span><span class="sxs-lookup"><span data-stu-id="2ead5-140">For more information about debugging tools for Progressive Web Apps and Service Workers in the DevTools, navigate to [Service Worker improvements][DevtoolsServiceWorkerIndex].</span></span>  <span data-ttu-id="2ead5-141">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1066604"。][CR1066604]</span><span class="sxs-lookup"><span data-stu-id="2ead5-141">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1066604][CR1066604].</span></span>  

## <a name="progressive-web-apps-no-longer-display-warnings-for-non-square-icons"></a><span data-ttu-id="2ead5-142">渐进式 Web 应用不再显示非方形图标的警告</span><span class="sxs-lookup"><span data-stu-id="2ead5-142">Progressive Web Apps no longer display warnings for non-square icons</span></span>  

<!--  Title: Non-square icons in app manifest no longer produce warnings  -->  
<!--  Subtitle: As long as square icons are included in the app manifest, non-square icons no longer produce warnings  -->  

<span data-ttu-id="2ead5-143">在[Microsoft Edge 版本 90][DevtoolsWhatsNew202102Devtools]或更早版本中，如果 PWA 的 Web App 清单包含非方形图标，则每个非方形图标\*\*\*\* 的"错误和警告"部分会显示警告。</span><span class="sxs-lookup"><span data-stu-id="2ead5-143">In [Microsoft Edge version 90][DevtoolsWhatsNew202102Devtools] or earlier, if the Web App Manifest of your PWA included a non-square icon, a warning was displayed in the **Errors and Warnings**  section for each non-square icon.</span></span>  <span data-ttu-id="2ead5-144">在Microsoft Edge版本 91 或更高版本中，\*\*\*\* 如果至少提供一\*\*\*\* 个正方形图标，则应用程序工具中的清单部分不会显示警告。</span><span class="sxs-lookup"><span data-stu-id="2ead5-144">In Microsoft Edge version 91 or later, the **Manifest** section in the **Application** tool displays no warnings if you provide at least one square icon.</span></span>  <span data-ttu-id="2ead5-145">如果未提供任何方形图标，则会显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="2ead5-145">If you don't provide any square icons, a warning displays the following message.</span></span>  

```output
Most operating systems require square icons.  Please include at least one square icon in the array.  
```  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png" alt-text="在 Microsoft Edge 版本 90 或更早版本中，对于非正方形的每个图标，将显示错误" lightbox="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="2ead5-147">在 Microsoft Edge 版本 90 或更早版本中，对于非正方形的每个图标，将显示错误</span><span class="sxs-lookup"><span data-stu-id="2ead5-147">In Microsoft Edge version 90 or earlier, an error displays for each icon that is non-square</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png" alt-text="在 Microsoft Edge 版本 91 或更高版本中，提供至少一个正方形图标时不会显示任何错误" lightbox="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="2ead5-149">在 Microsoft Edge 版本 91 或更高版本中，提供至少一个正方形图标时不会显示任何错误</span><span class="sxs-lookup"><span data-stu-id="2ead5-149">In Microsoft Edge version 91 or later, no error displays when you provide at least one square icon</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2ead5-150">若要在 Web 应用程序清单中查看错误和警告，请导航到 **"应用程序"** 工具并选择"清单 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="2ead5-150">To review errors and warnings in your Web App Manifest, navigate to the **Application** tool and choose the **Manifest** section.</span></span>  <span data-ttu-id="2ead5-151">错误和警告列在"错误和警告 **"** 标题下。</span><span class="sxs-lookup"><span data-stu-id="2ead5-151">Errors and warnings are listed under the **Errors and Warnings** heading.</span></span>  <span data-ttu-id="2ead5-152">有关 Web 应用部件清单的信息，请导航到"使用 Web 应用清单"将 [渐进式 Web 应用集成到操作系统中][ProgressiveWebAppsWebappmanifests]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-152">For more information about the Web App Manifest, navigate to [Use the Web App Manifest to integrate your Progressive Web App into the Operating System][ProgressiveWebAppsWebappmanifests].</span></span>  <span data-ttu-id="2ead5-153">若要创建要包括在 Web 应用清单中的图标，请导航到 [PWABuilder Image Generator][PwabuilderImagegenerator]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-153">To create icons to include in your Web App Manifest, navigate to the [PWABuilder Image Generator][PwabuilderImagegenerator].</span></span>  <span data-ttu-id="2ead5-154">若要在开放源代码项目中查看此功能Chromium，请导航到"问题 "[1185945][CR1185945]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-154">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1185945][CR1185945].</span></span>  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a><span data-ttu-id="2ead5-155">本地化的 DevTools 现在Chromium的浏览器中受支持</span><span class="sxs-lookup"><span data-stu-id="2ead5-155">Localized DevTools now supported in Chromium-based browsers</span></span>  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

<span data-ttu-id="2ead5-156">从 Microsoft Edge[版本 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]开始，Microsoft Edge开发人员工具以你自己的语言显示。</span><span class="sxs-lookup"><span data-stu-id="2ead5-156">Starting in [Microsoft Edge version 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages], Microsoft Edge DevTools displays in your own language.</span></span>  <span data-ttu-id="2ead5-157">许多开发人员使用 StackOverflow 等其他开发人员工具，Visual Studio Code语言进行开发，而不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="2ead5-157">Many developers use other developer tools like StackOverflow and Visual Studio Code in their native language, not just in English.</span></span>  <span data-ttu-id="2ead5-158">开发人员Microsoft Edge、Chrome DevTools 团队和 Google Lighthouse 团队协作，在所有基于 Chromium 的浏览器中提供相同的体验。</span><span class="sxs-lookup"><span data-stu-id="2ead5-158">The Microsoft Edge DevTools team, Chrome DevTools team, and the Google Lighthouse team collaborated to provide the same experience in all Chromium-based browsers.</span></span>  <span data-ttu-id="2ead5-159">若要详细了解如何在语言中使用 DevTools，请导航到"[更改 DevTools 语言设置"。][DevtoolsCustomizeLocalization]</span><span class="sxs-lookup"><span data-stu-id="2ead5-159">For more information about how to use DevTools in your language, navigate to [Change DevTools language settings][DevtoolsCustomizeLocalization].</span></span>  <span data-ttu-id="2ead5-160">有关开放源代码项目中有关此功能的协作Chromium，请导航到 [1136655][CR1136655]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-160">For more information about the collaboration on this feature in the Chromium open-source project, navigate to [1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edge浏览器和 DevTools 设置为日语" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   <span data-ttu-id="2ead5-162">Microsoft Edge浏览器和 DevTools 设置为日语</span><span class="sxs-lookup"><span data-stu-id="2ead5-162">Microsoft Edge browser and DevTools set to Japanese</span></span>  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a><span data-ttu-id="2ead5-163">使用键盘导航到 CSS 变量</span><span class="sxs-lookup"><span data-stu-id="2ead5-163">Use the keyboard to navigate to CSS variables</span></span>  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

<span data-ttu-id="2ead5-164">从[Microsoft Edge版本 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]开始，"\*\*\*\* 样式"窗格将显示 CSS 变量并提供指向每个变量的定义的链接。</span><span class="sxs-lookup"><span data-stu-id="2ead5-164">Starting in [Microsoft Edge version 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane], the **Styles** pane displays CSS variables and provides a link directly to the definition of each variable.</span></span>  <span data-ttu-id="2ead5-165">在 Microsoft Edge 版本 91 或更高版本中，可以使用箭头键轻松导航到 CSS 变量。</span><span class="sxs-lookup"><span data-stu-id="2ead5-165">In Microsoft Edge version 91 or later, you may use the arrow keys to easily navigate to CSS variables.</span></span>  <span data-ttu-id="2ead5-166">若要在"样式 **"窗格中打开** 定义，请将鼠标悬停在变量上，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-166">To open the definition in the **Styles** pane, hover on a variable, and then select `Enter`.</span></span>  <span data-ttu-id="2ead5-167">有关 CSS 变量详细信息，请导航到使用 CSS 自定义属性 ([变量) 。 ][MdnDocsWebCssUsingCssCustomProperties]</span><span class="sxs-lookup"><span data-stu-id="2ead5-167">For more information about CSS variables, navigate to [Using CSS custom properties (variables)][MdnDocsWebCssUsingCssCustomProperties].</span></span>  <span data-ttu-id="2ead5-168">若要在开放源代码项目中查看此功能Chromium，请导航到"问题 "[1187735][CR1187735]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-168">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1187735][CR1187735].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="--theme-body-background CSS 变量在"样式"窗格中突出显示" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   <span data-ttu-id="2ead5-170">" `--theme-body-background` 样式"窗格中突出显示的\*\*\*\* CSS 变量</span><span class="sxs-lookup"><span data-stu-id="2ead5-170">The `--theme-body-background` CSS variable highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a><span data-ttu-id="2ead5-171">问题按严重性自动排序</span><span class="sxs-lookup"><span data-stu-id="2ead5-171">Issues are automatically sorted by severity</span></span>  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

<span data-ttu-id="2ead5-172">问题 **工具** 显示改进网站的建议，包括辅助功能、性能、安全性等。</span><span class="sxs-lookup"><span data-stu-id="2ead5-172">The **Issues** tool displays recommendations to improve your website, including accessibility, performance, security, and so on.</span></span> <span data-ttu-id="2ead5-173">根据你的反馈，现在会自动按严重性对问题进行排序。</span><span class="sxs-lookup"><span data-stu-id="2ead5-173">Based on your feedback, issues are now automatically sorted by severity.</span></span>  <span data-ttu-id="2ead5-174">在每个反馈类别中，每个标记为"错误"的问题\*\*\*\* 首先出现，然后关注标记为"警告"的每个\*\*\*\* 问题，然后每个标记为"提示"**的问题**。</span><span class="sxs-lookup"><span data-stu-id="2ead5-174">In each feedback category, each issue marked as an **Error** appears first, followed each issue marked as a **Warning**, then each issue marked as a **Tip**.</span></span>  <span data-ttu-id="2ead5-175">为了帮助你优化问题，为将来的更新计划了额外的筛选器选项。</span><span class="sxs-lookup"><span data-stu-id="2ead5-175">To help you refine your issues, extra filter options are planned for a future update.</span></span>  <span data-ttu-id="2ead5-176">若要详细了解如何查看问题，请导航到使用 [问题工具查找和修复问题][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-176">For more information about how to review issues, navigate to [Find and fix problems using the Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-ordered-issues.msft.png" alt-text=""问题"工具按严重性显示排序的问题" lightbox="../../media/2021/04/elements-issues-ordered-issues.msft.png":::
   <span data-ttu-id="2ead5-178">" **问题** "工具按严重性显示排序的问题</span><span class="sxs-lookup"><span data-stu-id="2ead5-178">The **Issues** tool displays sorted issues by severity</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-117"></a><span data-ttu-id="2ead5-179">Microsoft Edge开发人员工具Visual Studio Code 1.1.7 版</span><span class="sxs-lookup"><span data-stu-id="2ead5-179">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.7</span></span>  

<!-- Title: Microsoft Edge DevTools for Visual Studio version 1.1.7  -->  
<!-- Subtitle: Increased target closure reliability, automatically update the side panel, new contextual menu for settings and Changelog, and more. -->  

<span data-ttu-id="2ead5-180">Microsoft Edge [Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 提供了来自 Microsoft Edge 版本[88 的][DevtoolsWhatsNew202011Devtools]DevTools。</span><span class="sxs-lookup"><span data-stu-id="2ead5-180">The [Microsoft Edge Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 provides the DevTools from [Microsoft Edge version 88][DevtoolsWhatsNew202011Devtools].</span></span>  <span data-ttu-id="2ead5-181">此扩展现在ARM设备，不再依赖调试器[进行Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge]扩展。</span><span class="sxs-lookup"><span data-stu-id="2ead5-181">This extension now supports ARM devices and no longer depends on the [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge] extension.</span></span>  <span data-ttu-id="2ead5-182">版本 1.1.7 包括以下 Bug 修复和改进。</span><span class="sxs-lookup"><span data-stu-id="2ead5-182">Version 1.1.7 includes the following bug fixes and improvements.</span></span>  

*   <span data-ttu-id="2ead5-183">更新了目标关闭的可靠性。</span><span class="sxs-lookup"><span data-stu-id="2ead5-183">Updated the reliability of target closure.</span></span>  
*   <span data-ttu-id="2ead5-184">更新了侧面板，以在调试创建或销毁的目标时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="2ead5-184">Updated the side panel to automatically refreshes when you debug targets that are created or destroyed.</span></span>  
*   <span data-ttu-id="2ead5-185">添加了一个新的上下文菜单，可让你更快地访问扩展设置和最新的 Changelog。</span><span class="sxs-lookup"><span data-stu-id="2ead5-185">Added a new contextual menu that gives you faster access to the extension settings and the latest Changelog.</span></span>  
*   <span data-ttu-id="2ead5-186">更新并简化了扩展文档（包括最新功能）的发布。</span><span class="sxs-lookup"><span data-stu-id="2ead5-186">Updated and simplified the release of extension documentation including the newest features.</span></span>  
    
<span data-ttu-id="2ead5-187">若要手动更新到版本 1.1.7，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]</span><span class="sxs-lookup"><span data-stu-id="2ead5-187">To manually update to version 1.1.7, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  <span data-ttu-id="2ead5-188">你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。</span><span class="sxs-lookup"><span data-stu-id="2ead5-188">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="2ead5-189">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="2ead5-189">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="visualize-css-scroll-snap"></a><span data-ttu-id="2ead5-190">可视化 CSS 滚动贴靠</span><span class="sxs-lookup"><span data-stu-id="2ead5-190">Visualize CSS scroll-snap</span></span>  

<span data-ttu-id="2ead5-191">现在，可以在"元素 `scroll-snap` "工具中\*\*\*\* 切换锁屏提醒，以检查 CSS 滚动对齐方式。</span><span class="sxs-lookup"><span data-stu-id="2ead5-191">You may now toggle the `scroll-snap` badge in the **Elements** tool to inspect the CSS scroll-snap alignment.</span></span>  <span data-ttu-id="2ead5-192">当网页上的 HTML 元素应用于该元素时，会在"元素"工具中旁边 `scroll-snap-type` `scroll-snap` **显示锁** 屏提醒。</span><span class="sxs-lookup"><span data-stu-id="2ead5-192">When an HTML element on your webpage has `scroll-snap-type` applied to it, a `scroll-snap` badge displays next to it in the **Elements** tool.</span></span>  <span data-ttu-id="2ead5-193">选择锁屏提醒以在网页上 (或关闭\) 滚动贴贴显示。</span><span class="sxs-lookup"><span data-stu-id="2ead5-193">Choose the badge to turn on \(or off\) the display of a scroll-snap overlay on the webpage.</span></span>  <span data-ttu-id="2ead5-194">To review an example webpage， navigate to [Scroll Snap Demo][GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml].</span><span class="sxs-lookup"><span data-stu-id="2ead5-194">To review an example webpage, navigate to [Scroll Snap Demo][GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml].</span></span>  <span data-ttu-id="2ead5-195">在示例中，点显示在对齐边缘上。</span><span class="sxs-lookup"><span data-stu-id="2ead5-195">In the example, dots display on snap edges.</span></span>  <span data-ttu-id="2ead5-196">滚动端口具有纯色轮廓，而贴靠项具有短划线轮廓。</span><span class="sxs-lookup"><span data-stu-id="2ead5-196">The scroll port has a solid outline while the snap items have dash outlines.</span></span>  <span data-ttu-id="2ead5-197">滚动填充填充为绿色，而滚动边距填充为橙色。</span><span class="sxs-lookup"><span data-stu-id="2ead5-197">The scroll padding is filled in green while the scroll margin is filled in orange.</span></span>  <span data-ttu-id="2ead5-198">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[862450"。][CR862450]</span><span class="sxs-lookup"><span data-stu-id="2ead5-198">To review the history of this feature in the Chromium open-source project, navigate to Issue [862450][CR862450].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-scroll-snap-highlight.msft.png" alt-text="CSS 滚动对齐" lightbox="../../media/2021/04/elements-scroll-snap-highlight.msft.png":::
   <span data-ttu-id="2ead5-200">CSS 滚动对齐</span><span class="sxs-lookup"><span data-stu-id="2ead5-200">CSS scroll-snap</span></span>  
:::image-end:::  

### <a name="new-memory-inspector-tool"></a><span data-ttu-id="2ead5-201">新内存检查器工具</span><span class="sxs-lookup"><span data-stu-id="2ead5-201">New Memory Inspector tool</span></span>  

<span data-ttu-id="2ead5-202">使用新的 **内存检查器** 工具检查 `ArrayBuffer` JavaScript 和 Wasm 内存中的 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-202">Use the new **Memory Inspector** tool to inspect an `ArrayBuffer` in JavaScript and Wasm memory.</span></span>  <span data-ttu-id="2ead5-203">打开 [JS 演示网页中的][GlitchMemoryInspectorDemoJsHtml] 内存。</span><span class="sxs-lookup"><span data-stu-id="2ead5-203">Open the [Memory in JS][GlitchMemoryInspectorDemoJsHtml] demo webpage.</span></span>  <span data-ttu-id="2ead5-204">在 **"源** "工具中， `memory-write-wasm` 打开文件，在行 处设置断点 `0x03c` 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-204">In the **Sources** tool, open the `memory-write-wasm` file, and set a breakpoint at line `0x03c`.</span></span>  <span data-ttu-id="2ead5-205">刷新网页。</span><span class="sxs-lookup"><span data-stu-id="2ead5-205">Refresh the webpage.</span></span>  <span data-ttu-id="2ead5-206">展开调试 **器** 窗格中的"范围"部分。</span><span class="sxs-lookup"><span data-stu-id="2ead5-206">Expand the **Scope** section in the debugger pane.</span></span>  <span data-ttu-id="2ead5-207">新图标显示在缓冲区值 **旁边** 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-207">The new icon is displayed next to the **buffer** value.</span></span>  <span data-ttu-id="2ead5-208">选择它以打开新的 **内存检查器** 工具。</span><span class="sxs-lookup"><span data-stu-id="2ead5-208">Choose it to open the new **Memory Inspector** tool.</span></span>  

<span data-ttu-id="2ead5-209">若要了解有关"源"工具中的调试 **的详细信息** ，请导航到"使用调试器"窗格 [调试 JavaScript 代码][DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-209">To learn more about debugging in the **Sources** tool, navigate to [Using the Debugger pane to debug JavaScript code][DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode].</span></span>  <span data-ttu-id="2ead5-210">若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1166577][CR1166577]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-210">To review the history of this feature in the Chromium open-source project, navigate to Issue [1166577][CR1166577].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png" alt-text="内存检查器工具" lightbox="../../media/2021/04/sources-memory-write-wasm-breakpoint-scope-reveal-in-memory-inspector-panel.msft.png":::
   <span data-ttu-id="2ead5-212">**内存检查器** 工具</span><span class="sxs-lookup"><span data-stu-id="2ead5-212">**Memory inspector** tool</span></span>  
:::image-end:::  

### <a name="new-badge-settings-pane-in-the-elements-tool"></a><span data-ttu-id="2ead5-213">"元素"工具中的"新建锁屏提醒设置"窗格</span><span class="sxs-lookup"><span data-stu-id="2ead5-213">New Badge settings pane in the Elements tool</span></span>  

<span data-ttu-id="2ead5-214">现在，使用"元素 **"** 工具中的\*\*\*\* 锁屏提醒设置打开 \ (或 off\) 单个锁屏提醒。</span><span class="sxs-lookup"><span data-stu-id="2ead5-214">Now, use the **Badge settings** in the **Elements** tool to turn on \(or off\) individual badges.</span></span>  <span data-ttu-id="2ead5-215">使用此功能在检查网页时自定义重要锁屏提醒并专注于重要锁屏提醒。</span><span class="sxs-lookup"><span data-stu-id="2ead5-215">Use this feature to customize and stay focused on important badges while you inspect webpages.</span></span>  <span data-ttu-id="2ead5-216">若要在"元素"工具顶部显示 **锁屏提醒** 设置窗格，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-216">To display the badge settings pane at the top of the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="2ead5-217">将鼠标悬停在任何元素上。</span><span class="sxs-lookup"><span data-stu-id="2ead5-217">Hover on any element.</span></span>  
1.  <span data-ttu-id="2ead5-218">打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="2ead5-218">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="2ead5-219">选择**锁屏提醒设置...**</span><span class="sxs-lookup"><span data-stu-id="2ead5-219">Choose **Badge settings...**.</span></span>  
    
<span data-ttu-id="2ead5-220">若要显示 \ (或隐藏\) 锁屏提醒，请选择 "\ ("或删除) 锁屏提醒名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="2ead5-220">To display \(or hide\) the badges, choose \(or remove\) the checkbox next to the badge name.</span></span>  

<!--  To review the history of this feature in the Chromium open-source project, navigate to Issue [1066772][CR1066772].  -->  

:::image type="complex" source="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png" alt-text=""元素"工具中的锁屏提醒设置窗格" lightbox="../../media/2021/04/elements-contextual-menu-badge-settings.msft.png":::
   <span data-ttu-id="2ead5-222">**"元素"** 工具中的锁屏提醒 **设置** 窗格</span><span class="sxs-lookup"><span data-stu-id="2ead5-222">**Badge settings** pane in the **Elements** tool</span></span>  
:::image-end:::  

### <a name="enhanced-image-preview-with-aspect-ratio-information"></a><span data-ttu-id="2ead5-223">具有纵横比信息的增强图像预览</span><span class="sxs-lookup"><span data-stu-id="2ead5-223">Enhanced image preview with aspect ratio information</span></span>  

<span data-ttu-id="2ead5-224">DevTools 中的图像预览已增强，可显示更多信息，包括以下详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ead5-224">Image previews in the DevTools have been enhanced to display more information, including the following details.</span></span>  

*   <span data-ttu-id="2ead5-225">呈现的大小</span><span class="sxs-lookup"><span data-stu-id="2ead5-225">Rendered size</span></span>  
*   <span data-ttu-id="2ead5-226">呈现的纵横比</span><span class="sxs-lookup"><span data-stu-id="2ead5-226">Rendered aspect ratio</span></span>  
*   <span data-ttu-id="2ead5-227">固有大小</span><span class="sxs-lookup"><span data-stu-id="2ead5-227">Intrinsic size</span></span>  
*   <span data-ttu-id="2ead5-228">固有纵横比</span><span class="sxs-lookup"><span data-stu-id="2ead5-228">Intrinsic aspect ratio</span></span>  
*   <span data-ttu-id="2ead5-229">文件大小</span><span class="sxs-lookup"><span data-stu-id="2ead5-229">File size</span></span>  
    
<span data-ttu-id="2ead5-230">该信息可帮助你更好地了解图像和应用优化。</span><span class="sxs-lookup"><span data-stu-id="2ead5-230">The  information helps you better understand your images and apply optimization.</span></span>  <span data-ttu-id="2ead5-231">当你选择图像预览时，网络工具中也\*\*\*\* 提供图像纵横比信息。</span><span class="sxs-lookup"><span data-stu-id="2ead5-231">The image aspect ratio information is also available in the **Network** tool, when you choose an image preview.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="2ead5-232">在 **"元素** "工具中，图像预览现在显示有关图像的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ead5-232">In the **Elements** tool, image preview now displays more information about the image.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2ead5-233">此外，当你选择图像预览时，网络工具中\*\*\*\* 还会提供图像纵横比信息。</span><span class="sxs-lookup"><span data-stu-id="2ead5-233">Also, the image aspect ratio information is available in the **Network** tool, when you choose an image preview.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png" alt-text="元素工具中的纵横比信息的图像预览" lightbox="../../media/2021/04/elements-inspect-image-src-hover-preview.msft.png":::
         <span data-ttu-id="2ead5-235">元素工具中的纵横比信息 **的图像** 预览</span><span class="sxs-lookup"><span data-stu-id="2ead5-235">Image preview with aspect ratio information in the **Element** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/network-img-name-filters-preview.msft.png" alt-text="网络工具中的图像纵横比信息" lightbox="../../media/2021/04/network-img-name-filters-preview.msft.png":::
         <span data-ttu-id="2ead5-237">网络工具中的图像纵 **横比** 信息</span><span class="sxs-lookup"><span data-stu-id="2ead5-237">Image aspect ratio information in the **Network** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2ead5-238">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1149832][CR1149832]和 [1170656][CR1170656]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-238">To review the history of this feature in the Chromium open-source project, navigate to Issues [1149832][CR1149832] and [1170656][CR1170656].</span></span>  

### <a name="new-options-to-configure-content-encodings-in-the-network-conditions-tool"></a><span data-ttu-id="2ead5-239">在网络条件工具中配置内容编码的新选项</span><span class="sxs-lookup"><span data-stu-id="2ead5-239">New options to configure Content-Encodings in the Network conditions tool</span></span> 

<span data-ttu-id="2ead5-240">在 **"网络**"工具中，选择"限制"下拉菜单旁边的"更多网络\*\*\*\* 条件 **..."** 按钮以打开 **"网络条件"** 工具。</span><span class="sxs-lookup"><span data-stu-id="2ead5-240">In the **Network** tool, choose the new **More network conditions...** button next to the **Throttling** dropdown menu to open the **Network conditions** tool.</span></span>  <span data-ttu-id="2ead5-241">若要测试服务器响应是否针对不支持[gzip、brotli][GnuSoftwareGzipManual]或其他将来的浏览器进行了正确编码[][|::ref1::|Main]，请完成 `Content-Encoding` 以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-241">To test if server responses are correctly encoded for browsers that don't support [gzip][GnuSoftwareGzipManual], [brotli][|::ref1::|Main], or another future `Content-Encoding`, complete the following actions.</span></span>  

1.  <span data-ttu-id="2ead5-242">打开 **"网络条件"** 工具</span><span class="sxs-lookup"><span data-stu-id="2ead5-242">Open the **Network conditions** tool</span></span>
1.  <span data-ttu-id="2ead5-243">导航到 **接受的内容编码**。</span><span class="sxs-lookup"><span data-stu-id="2ead5-243">Navigate to **Accepted Content-Encodings**.</span></span> 
1.  <span data-ttu-id="2ead5-244">删除要测试的 `Content-Encoding` 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="2ead5-244">Remove the checkbox next to the `Content-Encoding` you want to test.</span></span>  
    
<span data-ttu-id="2ead5-245">若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1162042][CR1162042]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-245">To review the history of this feature in the Chromium open-source project, navigate to Issue [1162042][CR1162042].</span></span>  

:::image type="complex" source="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png" alt-text="新增更多网络条件...按钮将打开"网络条件"工具以配置内容编码" lightbox="../../media/2021/04/network-more-network-conditions-accepted-content-encodings.msft.png":::
   <span data-ttu-id="2ead5-247">新建 **更多网络条件...** 按钮将打开 **网络条件** 工具进行配置</span><span class="sxs-lookup"><span data-stu-id="2ead5-247">New **More network conditions...** button opens the **Network conditions** tool to configure</span></span> `Content-Encoding`  
:::image-end:::  

### <a name="styles-pane-enhancements"></a><span data-ttu-id="2ead5-248">样式窗格增强功能</span><span class="sxs-lookup"><span data-stu-id="2ead5-248">Styles pane enhancements</span></span>  

#### <a name="new-shortcut-to-display-computed-value-in-the-styles-pane"></a><span data-ttu-id="2ead5-249">在"样式"窗格中显示计算值的新快捷方式</span><span class="sxs-lookup"><span data-stu-id="2ead5-249">New shortcut to display computed value in the Styles pane</span></span>  

<span data-ttu-id="2ead5-250">现在，若要在"样式"窗格中显示计算出的 CSS **值，** 请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-250">Now, to display the computed CSS value in the **Styles** pane, complete the following actions.</span></span>  

1.  <span data-ttu-id="2ead5-251">将鼠标悬停在 CSS 属性上。</span><span class="sxs-lookup"><span data-stu-id="2ead5-251">Hover on a CSS property.</span></span>  
1.  <span data-ttu-id="2ead5-252">打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="2ead5-252">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="2ead5-253">选择 **"查看计算值"。**</span><span class="sxs-lookup"><span data-stu-id="2ead5-253">Choose **View computed value**.</span></span>  
    
<span data-ttu-id="2ead5-254">若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1076198][CR1076198]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-254">To review the history of this feature in the Chromium open-source project, navigate to Issue [1076198][CR1076198].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png" alt-text="显示计算值的新快捷方式" lightbox="../../media/2021/04/elements-styles-highlight-view-computed-value.msft.png":::
   <span data-ttu-id="2ead5-256">显示计算值的新快捷方式</span><span class="sxs-lookup"><span data-stu-id="2ead5-256">New shortcut to display computed value</span></span>  
:::image-end:::  

#### <a name="support-for-the-accent-color-keyword"></a><span data-ttu-id="2ead5-257">支持主题色关键字</span><span class="sxs-lookup"><span data-stu-id="2ead5-257">Support for the accent-color keyword</span></span>  

<span data-ttu-id="2ead5-258">"样式"窗格的自动完成\*\*\*\* UI 现在检测到 CSS 关键字，这允许您指定元素生成的 `accent-color` UI 控件的强调文字颜色。</span><span class="sxs-lookup"><span data-stu-id="2ead5-258">The autocomplete UI of the **Styles** pane now detects the `accent-color` CSS keyword, which allows you to specify the accent color for UI controls generated by the element.</span></span>  <span data-ttu-id="2ead5-259">元素生成的 UI 控件示例包括复选框或单选按钮。</span><span class="sxs-lookup"><span data-stu-id="2ead5-259">Examples of UI controls that are generated by an element include checkboxes or radio buttons.</span></span> <span data-ttu-id="2ead5-260">有关实现实现状态Chromium导航到[功能：主题色 CSS 属性][ChromestatusFeature4752739957473280]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-260">For more information about the status of the Chromium implementation, navigate to [Feature: accent-color CSS property][ChromestatusFeature4752739957473280].</span></span>  <span data-ttu-id="2ead5-261">若要启用此功能，请导航到 `edge://flags#enable-experimental-web-platform-features` ，将复选框设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="2ead5-261">To turn on this feature, navigate to `edge://flags#enable-experimental-web-platform-features` and set the checkbox to **Enabled**.</span></span>  <span data-ttu-id="2ead5-262">若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1092093][CR1092093]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-262">To review the history of this feature in the Chromium open-source project, navigate to Issue [1092093][CR1092093].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-accent-color.msft.png" alt-text="强调文字颜色 CSS 关键字" lightbox="../../media/2021/04/elements-styles-accent-color.msft.png":::
   `accent-color` <span data-ttu-id="2ead5-264">CSS 关键字</span><span class="sxs-lookup"><span data-stu-id="2ead5-264">CSS keyword</span></span>
:::image-end:::  

### <a name="display-details-about-blocked-features-in-the-frame-details-view"></a><span data-ttu-id="2ead5-265">在"框架详细信息"视图中显示有关阻止的功能的详细信息</span><span class="sxs-lookup"><span data-stu-id="2ead5-265">Display details about blocked features in the Frame details view</span></span>  

<span data-ttu-id="2ead5-266">权限策略是一个 Web 平台 API，它使网站能够允许或阻止在单个框架或它所嵌入的 `iframe` 中使用浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="2ead5-266">Permissions Policy is a web platform API that gives a website the ability to allow or block the use of browser features in an individual frame or in an `iframe` that it embeds.</span></span> <span data-ttu-id="2ead5-267">有关详细信息，请导航到["权限策略解释器"。][GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]</span><span class="sxs-lookup"><span data-stu-id="2ead5-267">For more information, navigate to [Permissions Policy Explainer][GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd].</span></span>  <span data-ttu-id="2ead5-268">若要显示有关阻止功能的原因的详细信息，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-268">To display the details on why a feature is blocked, complete the following actions.</span></span>  

1.  <span data-ttu-id="2ead5-269">导航到 [OOPIF 权限策略][GlitchPermissionPolicyDemoMain]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-269">Navigate to [OOPIF Permissions Policy][GlitchPermissionPolicyDemoMain].</span></span>  
1.  <span data-ttu-id="2ead5-270">导航到 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="2ead5-270">Navigate to the **Application** tool.</span></span>  
1.  <span data-ttu-id="2ead5-271">选择一个帧。</span><span class="sxs-lookup"><span data-stu-id="2ead5-271">Choose a frame.</span></span>  
1.  <span data-ttu-id="2ead5-272">导航到 **"权限策略"** 部分。</span><span class="sxs-lookup"><span data-stu-id="2ead5-272">Navigate to the **Permissions Policy** section.</span></span>  
1.  <span data-ttu-id="2ead5-273">导航到 **Disabled Features** 属性。</span><span class="sxs-lookup"><span data-stu-id="2ead5-273">Navigate to the **Disabled Features** property.</span></span>  
1.  <span data-ttu-id="2ead5-274">选择 **"显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="2ead5-274">Choose **Show details**.</span></span>  
1.  <span data-ttu-id="2ead5-275">选择每个策略旁边的图标以导航到阻止该功能的 或 `iframe` 网络请求。</span><span class="sxs-lookup"><span data-stu-id="2ead5-275">Choose the icon next to each policy to navigate to the `iframe` or network request that blocked the feature.</span></span>  
    
<span data-ttu-id="2ead5-276">若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1158827][CR1158827]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-276">To review the history of this feature in the Chromium open-source project, navigate to Issue [1158827][CR1158827].</span></span>  

:::image type="complex" source="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png" alt-text="框架详细信息视图中阻止的功能" lightbox="../../media/2021/04/application-frames-top-permission-policy-disabled-features-show-details-highlight.msft.png":::
   <span data-ttu-id="2ead5-278">框架详细信息视图中阻止的功能</span><span class="sxs-lookup"><span data-stu-id="2ead5-278">Blocked features in the Frame details view</span></span>  
:::image-end:::  

### <a name="filter-experiments-in-the-experiments-setting"></a><span data-ttu-id="2ead5-279">在实验设置中筛选实验</span><span class="sxs-lookup"><span data-stu-id="2ead5-279">Filter experiments in the Experiments setting</span></span>  

<span data-ttu-id="2ead5-280">使用新的实验筛选器更快地查找实验。</span><span class="sxs-lookup"><span data-stu-id="2ead5-280">Find experiments quicker with the new experiment filter.</span></span>  <span data-ttu-id="2ead5-281">例如，若要打开代码问题的新实验，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-281">For example, to turn on new experiments for code issues, complete the following actions.</span></span>
``

1.  <span data-ttu-id="2ead5-282">导航到**设置**  >  **实验。**</span><span class="sxs-lookup"><span data-stu-id="2ead5-282">Navigate to **Settings** > **Experiments**.</span></span>  
1.  <span data-ttu-id="2ead5-283">导航到 **"筛选器** "文本框。</span><span class="sxs-lookup"><span data-stu-id="2ead5-283">Navigate to the **Filter** textbox.</span></span>  
1.  <span data-ttu-id="2ead5-284">键入 `issues`。</span><span class="sxs-lookup"><span data-stu-id="2ead5-284">Type `issues`.</span></span>  
    
:::image type="complex" source="../../media/2021/04/settings-experiments-filter-by-issues.msft.png" alt-text="在实验设置中筛选实验" lightbox="../../media/2021/04/settings-experiments-filter-by-issues.msft.png":::
   <span data-ttu-id="2ead5-286">在实验设置 **中筛选** 实验</span><span class="sxs-lookup"><span data-stu-id="2ead5-286">Filter experiments in the **Experiments** setting</span></span>  
:::image-end:::  

### <a name="new-vary-header-column-in-the-cache-storage-pane"></a><span data-ttu-id="2ead5-287">"缓存"存储窗格中的"新建 Vary Header"列</span><span class="sxs-lookup"><span data-stu-id="2ead5-287">New Vary Header column in the Cache storage pane</span></span>  

<span data-ttu-id="2ead5-288">使用" `Vary Header` 缓存地址"窗格中**的新存储**显示["不同][HttpwgSpecsRfc7231HtmlHeaderVary]HTTP 响应头"值。</span><span class="sxs-lookup"><span data-stu-id="2ead5-288">Use the new `Vary Header` column in the **Cache Storage** pane to display the [Vary][HttpwgSpecsRfc7231HtmlHeaderVary] HTTP response header values.</span></span>  <span data-ttu-id="2ead5-289">若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1186049][CR1186049]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-289">To review the history of this feature in the Chromium open-source project, navigate to Issue [1186049][CR1186049].</span></span>  

:::image type="complex" source="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png" alt-text="Vary Header 列" lightbox="../../media/2021/04/application-cache-cache-storage-highlighted-vary-header.msft.png":::
   <span data-ttu-id="2ead5-291">Vary Header 列</span><span class="sxs-lookup"><span data-stu-id="2ead5-291">Vary Header column</span></span>  
:::image-end:::  

### <a name="sources-tool-improvements"></a><span data-ttu-id="2ead5-292">源工具改进</span><span class="sxs-lookup"><span data-stu-id="2ead5-292">Sources tool improvements</span></span>  

#### <a name="support-for-new-javascript-features"></a><span data-ttu-id="2ead5-293">支持新的 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="2ead5-293">Support for new JavaScript features</span></span>  

<span data-ttu-id="2ead5-294">DevTools 现在支持新的专用品牌检查，即#foo [javaScript][V8DevFeaturesPrivateBrandChecks] 语言功能。</span><span class="sxs-lookup"><span data-stu-id="2ead5-294">DevTools now support the new [Private brand checks a.k.a. #foo in obj][V8DevFeaturesPrivateBrandChecks] JavaScript language feature.</span></span>  <span data-ttu-id="2ead5-295">专用品牌检查功能扩展了 [in 运算符][MdnDocsWebJavascriptReferenceOperatorsIn] ，以支持特定对象的 [Private][V8DevFeaturesClassFieldsPrivateClassFields] 类字段。</span><span class="sxs-lookup"><span data-stu-id="2ead5-295">The private brand checks feature extends the [in operator][MdnDocsWebJavascriptReferenceOperatorsIn] to support [Private class fields][V8DevFeaturesClassFieldsPrivateClassFields] on a specific object.</span></span>  <span data-ttu-id="2ead5-296">在控制台和**源工具\*\*\*\*中试用**它。</span><span class="sxs-lookup"><span data-stu-id="2ead5-296">Try it in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="2ead5-297">此外，若要检查私有字段，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-297">Also, to inspect the private fields, complete the following actions.</span></span>  

1.  <span data-ttu-id="2ead5-298">导航到 **调试器** 窗格。</span><span class="sxs-lookup"><span data-stu-id="2ead5-298">Navigate to **debugger** pane.</span></span>  
1.  <span data-ttu-id="2ead5-299">导航到" **范围"** 部分。</span><span class="sxs-lookup"><span data-stu-id="2ead5-299">Navigate to the **Scope** section.</span></span>  
    
<span data-ttu-id="2ead5-300">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[11374"。][CR11374]</span><span class="sxs-lookup"><span data-stu-id="2ead5-300">To review the history of this feature in the Chromium open-source project, navigate to Issue [11374][CR11374].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png" alt-text="JavaScript 专用品牌检查" lightbox="../../media/2021/04/sources-page-pen-js-breakpoint-scope-script-dog.msft.png":::
   <span data-ttu-id="2ead5-302">JavaScript 专用品牌检查</span><span class="sxs-lookup"><span data-stu-id="2ead5-302">JavaScript private brand checks</span></span>  
:::image-end:::  

#### <a name="enhanced-support-for-breakpoints-debugging"></a><span data-ttu-id="2ead5-303">增强了对断点调试的支持</span><span class="sxs-lookup"><span data-stu-id="2ead5-303">Enhanced support for breakpoints debugging</span></span>  

<span data-ttu-id="2ead5-304">Webpack 和[Rollup][RollupjsMain]等新式 JavaScript 捆绑程序支持代码拆分。 [][WebpackJsMain]</span><span class="sxs-lookup"><span data-stu-id="2ead5-304">Modern JavaScript bundlers like [Webpack][WebpackJsMain], and [Rollup][RollupjsMain] support code splitting.</span></span>  <span data-ttu-id="2ead5-305">若要了解有关代码拆分的更多信息，请导航到"[代码拆分"。][JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]</span><span class="sxs-lookup"><span data-stu-id="2ead5-305">To learn more about code splitting, navigate to [Code splitting][JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules].</span></span>  <span data-ttu-id="2ead5-306">在 Microsoft Edge 90 或更早版本中，DevTools 仅在单个捆绑包中设置断点。</span><span class="sxs-lookup"><span data-stu-id="2ead5-306">In Microsoft Edge version 90 or earlier, DevTools only set breakpoints in a single bundle.</span></span>  <span data-ttu-id="2ead5-307">在 Microsoft Edge版本 91 或更高版本中，调试共享组件时，DevTools 会正确设置多个捆绑包中的断点。</span><span class="sxs-lookup"><span data-stu-id="2ead5-307">In Microsoft Edge version 91 or later, DevTools properly sets breakpoints in multiple bundles when you debug a shared component.</span></span>  <span data-ttu-id="2ead5-308">若要在 Chromium 开放源代码项目中查看此功能的历史记录，请导航到问题 [1142705][CR1142705]、979000 和 [1180794][CR1180794]。 [][CR979000]</span><span class="sxs-lookup"><span data-stu-id="2ead5-308">To review the history of this feature in the Chromium open-source project, navigate to Issues [1142705][CR1142705], [979000][CR979000], and [1180794][CR1180794].</span></span>  

#### <a name="support-hover-preview-with-bracket-notation"></a><span data-ttu-id="2ead5-309">使用方括号表示法支持悬停预览</span><span class="sxs-lookup"><span data-stu-id="2ead5-309">Support hover preview with bracket notation</span></span>  

<span data-ttu-id="2ead5-310">DevTools 现在支持在使用源工具中的表示法的 JavaScript 成员表达式上 `[]` 悬停预览。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2ead5-310">DevTools now support hover preview on JavaScript member expressions that use the `[]` notation in the **Sources** tool.</span></span>  <span data-ttu-id="2ead5-311">若要查看开放源代码项目中此功能的历史记录，Chromium问题 [1178305][CR1178305]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-311">To review the history of this feature in the Chromium open-source project, navigate to Issue [1178305][CR1178305].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png" alt-text="使用 [] 表示法支持悬停预览" lightbox="../../media/2021/04/sources-page-pen.js-breakpoint-arr-i-a.msft.png":::
   <span data-ttu-id="2ead5-313">使用表示法支持 `[]` 悬停预览</span><span class="sxs-lookup"><span data-stu-id="2ead5-313">Support hover preview with `[]` notation</span></span>  
:::image-end:::  

#### <a name="improved-outline-of-html-files"></a><span data-ttu-id="2ead5-314">改进了 HTML 文件的大纲</span><span class="sxs-lookup"><span data-stu-id="2ead5-314">Improved outline of HTML files</span></span>  

<span data-ttu-id="2ead5-315">DevTools 现在具有对文件的更好的大纲 `.html` 支持。</span><span class="sxs-lookup"><span data-stu-id="2ead5-315">DevTools now has better outline support for `.html` files.</span></span>  <span data-ttu-id="2ead5-316">在 **"源** "工具中，打开 `.html` 文件。</span><span class="sxs-lookup"><span data-stu-id="2ead5-316">In the **Sources** tool, open the `.html` file.</span></span>  <span data-ttu-id="2ead5-317">若要打开 \ (或关闭\) 代码大纲，请在 `Ctrl` + `Shift` + `O` Windows/Linux 或 `Cmd` + `Shift` + `O` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="2ead5-317">To turn on \(or off\) the code outline, select `Ctrl`+`Shift`+`O` on Windows/Linux or `Cmd`+`Shift`+`O` on macOS.</span></span>  <span data-ttu-id="2ead5-318">在下图中，DevTools 现在正确列出了大纲中的所有函数。</span><span class="sxs-lookup"><span data-stu-id="2ead5-318">In the following figure, DevTools now correctly list all functions in the outline.</span></span>  <span data-ttu-id="2ead5-319">以前，DevTools 只显示一些函数。</span><span class="sxs-lookup"><span data-stu-id="2ead5-319">Previously, DevTools only displayed some of the functions.</span></span>  <span data-ttu-id="2ead5-320">若要在开放源代码项目中查看此功能的历史记录，Chromium问题[761019][CR761019]和 [1191465][CR1191465]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-320">To review the history of this feature in the Chromium open-source project, navigate to Issues [761019][CR761019] and [1191465][CR1191465].</span></span>  

:::image type="complex" source="../../media/2021/04/sources-page-jobobbx-at.msft.png" alt-text=" 改进了 HTML 文件的大纲" lightbox="../../media/2021/04/sources-page-jobobbx-at.msft.png":::
   <span data-ttu-id="2ead5-322">改进了 HTML 文件的大纲</span><span class="sxs-lookup"><span data-stu-id="2ead5-322">Improved outline of HTML files</span></span>  
:::image-end:::  

#### <a name="proper-error-stack-traces-for-wasm-debugging"></a><span data-ttu-id="2ead5-323">Wasm 调试的正确错误堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="2ead5-323">Proper error stack traces for Wasm debugging</span></span>  

<span data-ttu-id="2ead5-324">在 Microsoft Edge 90 或更早版本中，DevTools 仅在错误堆栈跟踪中显示常规 Wasm 引用。</span><span class="sxs-lookup"><span data-stu-id="2ead5-324">In Microsoft Edge version 90 or earlier, DevTools only displayed generic Wasm references in Error stack traces.</span></span>  <span data-ttu-id="2ead5-325">在 Microsoft Edge 91 或更高版本中，DevTools 解析内联函数请求，并显示 Wasm 调试的错误堆栈跟踪中的源位置。</span><span class="sxs-lookup"><span data-stu-id="2ead5-325">In Microsoft Edge version 91 or later, DevTools resolves inline function requests and displays the source location in Error stack traces for Wasm debugging.</span></span>  <span data-ttu-id="2ead5-326">若要了解有关控制台中的错误堆栈跟踪的详细信息 **，请导航**到 [错误][DevtoolsConsoleApiError]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-326">To learn more about Error stack traces in the **Console**, navigate to [error][DevtoolsConsoleApiError].</span></span>  

<span data-ttu-id="2ead5-327">在 Microsoft Edge 91 或更高版本中，DevTools 解析内联函数请求并显示 Wasm 调试的正确错误堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="2ead5-327">In Microsoft Edge version 91 or later, DevTools resolves inline function requests and displays proper error stack traces for Wasm debugging.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="2ead5-328">在Microsoft Edge版本 90 及更早版本中，源位置不会显示在错误堆栈跟踪中。</span><span class="sxs-lookup"><span data-stu-id="2ead5-328">In Microsoft Edge version 90 and earlier, the source location doesn't display in the Error stack traces.</span></span>  <span data-ttu-id="2ead5-329">源位置包括 `dsquare` 。</span><span class="sxs-lookup"><span data-stu-id="2ead5-329">Source locations include `dsquare`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2ead5-330">在Microsoft Edge版本 91 及更高版本中，源位置显示在错误堆栈跟踪中。</span><span class="sxs-lookup"><span data-stu-id="2ead5-330">In Microsoft Edge version 91 and later, the source location displays in the Error stack traces.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png" alt-text="Wasm 调试以前的错误堆栈跟踪" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error-old.msft.png":::
         <span data-ttu-id="2ead5-332">Wasm 调试的正确错误堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="2ead5-332">Proper error stack traces for Wasm debugging</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png" alt-text="Wasm 调试的正确错误堆栈跟踪" lightbox="../../media/2021/04/sources-page-inlining-dwarf-wasm-breakpoint-console-new-error.msft.png":::
         <span data-ttu-id="2ead5-334">Wasm 调试的正确错误堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="2ead5-334">Proper error stack traces for Wasm debugging</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2ead5-335">若要在开放源代码项目中查看此功能的历史记录，Chromium问题 [1189161][CR1189161]。</span><span class="sxs-lookup"><span data-stu-id="2ead5-335">To review the history of this feature in the Chromium open-source project, navigate to Issue [1189161][CR1189161].</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="2ead5-336">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="2ead5-336">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="2ead5-337">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="2ead5-337">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="2ead5-338">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="2ead5-338">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="2ead5-339">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="2ead5-339">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]: ../../2020/01/devtools.md#using-the-devtools-in-other-languages "以其他语言使用 DevTools - DevTools (Microsoft Edge 81) |Microsoft Docs"  
[DevtoolsWhatsNew202011Devtools]: ../../2020/11/devtools.md "DevTools (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]: ../../2020/11/devtools.md#css-variable-definitions-in-styles-pane "样式窗格中的 CSS 变量定义 - DevTools (Microsoft Edge 88 中的新增) |Microsoft Docs"  
[DevtoolsWhatsNew202102Devtools]: ../02/devtools.md "DevTools （Microsoft Edge 90） 中的新增功能|Microsoft Docs"  
[DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode]: ../02/devtools.md#group-tools-together-in-focus-mode "在焦点模式下将工具组合在一起 - DevTools (Microsoft Edge 90 中的新增) |Microsoft Docs"  

[DevtoolsCommandMenuIndexOpenCommandMenu]: ../../../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用&quot;开发工具Microsoft Edge菜单运行命令|Microsoft Docs"  
[DevtoolsConsoleApiError]: ../../../console/api.md#error "error - 控制台 API |Microsoft Docs"  
[DevtoolsCustomizeLocalization]: ../../../customize/localization.md "更改 DevTools 语言设置 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "使用问题工具查找并修复|Microsoft Docs"  
[DevtoolsServiceWorkerIndex]: ../../../service-workers/index.md "服务工作者改进|Microsoft Docs"  
[DevtoolsSourcesUsingDebuggerPaneToDebugJavascriptCode]: ../../../sources/index.md#using-the-debugger-pane-to-debug-javascript-code "使用调试器窗格调试 JavaScript 代码 - 源工具概述|Microsoft Docs"  

[ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]: ../../../../progressive-web-apps-chromium/serviceworker.md#the-service-worker-lifecycle "服务工作线程生命周期 - 使用服务工作者管理网络请求和推送通知|Microsoft Docs"  
[ProgressiveWebAppsWebappmanifests]: ../../../../progressive-web-apps-chromium/webappmanifests.md "使用 Web 应用清单将渐进式 Web 应用集成到操作系统|Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
<!--[GithubMicrosoftVscodeEdgeDevtoolsPullxxx]: https://github.com/microsoft/vscode-edge-devtools/pull/xxx "Pull xxx: Lorem al Ipsum | GitHub"  -->  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerForEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  

[BrotliMain]: https://www.brotli.org "Brotli"  

[ChromestatusFeature4752739957473280]: https://chromestatus.com/feature/4752739957473280 "功能：强调文字颜色 CSS |Chrome 平台状态"  

[CsswgDraftsCssUi4WidgetAccent]: https://drafts.csswg.org/css-ui-4/#widget-accent "小组件主题色：主题色属性 - CSS 基本用户界面模块级别 4 |CSS 工作组编辑器草稿"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR11374]: https://crbug.com/v8/11374 "问题 11374：对私有字段实施品牌打造检查"  
[CR761019]: https://crbug.com/761019 "问题 761019：&quot;转到符号&quot;会错过第一个函数，并且如果它包含所有键入的字符，则首选一个更糟的匹配"  
[CR862450]: https://crbug.com/862450 "问题 862450：[css-scroll-snap] 考虑为 css 滚动贴靠添加 Devtools 功能"  
[CR979000]: https://crbug.com/979000 "问题 979000：具有碰撞源路径的源映射不起作用。"  
[CR1066604]: https://crbug.com/1066604 "问题 1066604：DevTools：查看有关 ServiceWorker 安装和激活事件的详细信息|Chromium Bug"  
<!--  [CR1066772]: https://crbug.com/1066772 "Issue 1066772: "  locked  -->  
<span data-ttu-id="2ead5-367">[CR1076198]：" https://crbug.com/1076198 问题 1076198：[功能请求] 从选项卡跳转到计算 `styles` 属性"</span><span class="sxs-lookup"><span data-stu-id="2ead5-367">[CR1076198]: https://crbug.com/1076198 "Issue 1076198: [Feature Request] Jump to computed property from `styles` tab"</span></span>  
<span data-ttu-id="2ead5-368">[CR1092093]：" https://crbug.com/1092093 问题 1092093：通过支持"accent-color"CSS 属性，使窗体控件的颜色更可样式化"</span><span class="sxs-lookup"><span data-stu-id="2ead5-368">[CR1092093]: https://crbug.com/1092093 "Issue 1092093: Make form controls more color-stylable by supporting the 'accent-color' CSS property"</span></span>  
<span data-ttu-id="2ead5-369">[CR1136655]：" https://crbug.com/1136655 问题 1136655：Devtools：本地化 V2 |Chromium Bug"</span><span class="sxs-lookup"><span data-stu-id="2ead5-369">[CR1136655]: https://crbug.com/1136655 "Issue 1136655: Devtools: Localization V2 | Chromium bugs"</span></span>  
<span data-ttu-id="2ead5-370">[CR1142705]："问题 1142705：使用 webpack 时，两个源映射指向同一虚拟文件时断点停止 https://crbug.com/1142705 工作"</span><span class="sxs-lookup"><span data-stu-id="2ead5-370">[CR1142705]: https://crbug.com/1142705 "Issue 1142705: breakpoints stop working when 2 sourcemaps point to the same virtual file when using webpack"</span></span>  
<span data-ttu-id="2ead5-371">[CR1149832]：" https://crbug.com/1149832 问题 1149832：功能请求：图像预览还应显示文件大小"</span><span class="sxs-lookup"><span data-stu-id="2ead5-371">[CR1149832]: https://crbug.com/1149832 "Issue 1149832: Feature request: image preview should also show file size"</span></span>  
<span data-ttu-id="2ead5-372">[CR1158827]：" https://crbug.com/1158827 问题 1158827：[权限策略] 实现权限策略的开发人员支持"</span><span class="sxs-lookup"><span data-stu-id="2ead5-372">[CR1158827]: https://crbug.com/1158827 "Issue 1158827: [Permissions Policy] Implement devtool support for permissions policy"</span></span>  
<span data-ttu-id="2ead5-373">[CR1162042]： https://crbug.com/1162042 "问题 1162042：DevTools：支持禁用 gzip/brotli/jxl 内容编码"</span><span class="sxs-lookup"><span data-stu-id="2ead5-373">[CR1162042]: https://crbug.com/1162042 "Issue 1162042: DevTools: support disabling gzip/brotli/jxl content-encoding"</span></span>  
<span data-ttu-id="2ead5-374">[CR1166577]：" https://crbug.com/1166577 问题 1166577：☂️线性内存检查器 1.0"</span><span class="sxs-lookup"><span data-stu-id="2ead5-374">[CR1166577]: https://crbug.com/1166577 "Issue 1166577: ☂️ Linear Memory Inspector 1.0"</span></span>  
<span data-ttu-id="2ead5-375">[CR1170656]：" https://crbug.com/1170656 问题 1170656：显示固有纵横比"</span><span class="sxs-lookup"><span data-stu-id="2ead5-375">[CR1170656]: https://crbug.com/1170656 "Issue 1170656: Show intrinsic aspect-ratio"</span></span>  
<span data-ttu-id="2ead5-376">[CR1178305]："问题 1178305：调试器在悬停时不会显示已编制索引的元素 https://crbug.com/1178305 的属性值"</span><span class="sxs-lookup"><span data-stu-id="2ead5-376">[CR1178305]: https://crbug.com/1178305 "Issue 1178305: Debugger doesn't show an indexed element's property value when it's hovered"</span></span>  
<span data-ttu-id="2ead5-377">[CR1180794]：" https://crbug.com/1180794 问题 1180794：断点不能与关闭编译器内线优化一起运行"</span><span class="sxs-lookup"><span data-stu-id="2ead5-377">[CR1180794]: https://crbug.com/1180794 "Issue 1180794: Breakpoints don't work with Closure Compiler inlining optimization"</span></span>  
<span data-ttu-id="2ead5-378">[CR1185945]：" https://crbug.com/1185945 问题 1185945：清单警告表示所有图标都必须是方形|Chromium Bug"</span><span class="sxs-lookup"><span data-stu-id="2ead5-378">[CR1185945]: https://crbug.com/1185945 "Issue 1185945: Manifest warning implies all icons must be square | Chromium bugs"</span></span>  
<span data-ttu-id="2ead5-379">[CR1186049]：" https://crbug.com/1186049 问题 1186049：不同列：缓存查看器中的存储标题"</span><span class="sxs-lookup"><span data-stu-id="2ead5-379">[CR1186049]: https://crbug.com/1186049 "Issue 1186049: Column for Vary: header in Cache Storage viewer"</span></span>  
<span data-ttu-id="2ead5-380">[CR1187735]："问题 https://crbug.com/1187735 1187735：辅助功能：MAS2.1.1：键盘：无法调用'Var (。。) 键盘的 |Chromium Bug"</span><span class="sxs-lookup"><span data-stu-id="2ead5-380">[CR1187735]: https://crbug.com/1187735 "Issue 1187735: Accessibility: MAS2.1.1: Keyboard: Unable to invoke the 'Var(..)' function using keyboard | Chromium bugs"</span></span>  
<span data-ttu-id="2ead5-381">[CR1189161]： https://crbug.com/1189161 "问题 1189161：堆栈跟踪不是 `new Error` 通过功能区转换的"</span><span class="sxs-lookup"><span data-stu-id="2ead5-381">[CR1189161]: https://crbug.com/1189161 "Issue 1189161: `new Error` stacktraces are not transformed via DWARF"</span></span>  
<span data-ttu-id="2ead5-382">[CR1191465]：" https://crbug.com/1191465 问题 1191465：Ctrl+Shift+O 断开 HTML"</span><span class="sxs-lookup"><span data-stu-id="2ead5-382">[CR1191465]: https://crbug.com/1191465 "Issue 1191465: Ctrl+Shift+O broken on HTML"</span></span>  

[GithubW3cWebappsecPermissionsPolicyPermissionsPolicyExplainerMd]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "权限策略解释器 | GitHub"  

[GlitchMemoryInspectorDemoJsHtml]: https://memory-inspector.glitch.me/demo-js.html "JS |小故障"  
[GlitchMemoryInspectorDemoWasmHtml]: https://memory-inspector.glitch.me/demo-wasm.html "Wasm 内存|小故障"  

[GlitchMicrosoftEdgeChromiumDevtoolsCssDbgStoriesCssScrollSnapHtml]: https://microsoft-edge-chromium-devtools.glitch.me/css-dbg-stories/css-scroll-snap.html "滚动贴靠演示|小故障"  

[GlitchPermissionPolicyDemoMain]: http://permission-policy-demo.glitch.me "OOPIF 权限策略|小故障"  

[GnuSoftwareGzipManual]: https://www.gnu.org/software/gzip/manual "gzip：数据压缩程序|省/市/市/省/市/市"  

[HttpwgSpecsRfc7231HtmlHeaderVary]: https://httpwg.org/specs/rfc7231.html#header.vary "Vary - HTTP/1.1 (超文本传输协议) ：语义和内容|IETF HTTP 工作组"  

[JsWebpackGuidesCodeSplittingTextThereAreThreeGeneralApproachesToCodeSplittingSplitCodeViaInlineFunctionCallsWithinModules]: https://webpack.js.org/guides/code-splitting/#:~:text=There%20are%20three%20general%20approaches%20to%20code%20splitting,Split%20code%20via%20inline%20function%20calls%20within%20modules. "可以使用三种常规方法拆分代码：入口点：使用条目配置手动拆分代码。 防止重复：使用条目依赖关系或 SplitChunksPlugin 进行重复数据读取和拆分块。 动态导入：通过模块中的内嵌函数调用拆分代码。- 代码拆分|webpack"  

[MdnDocsWebCssUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性（变量）| MDN"  

[MdnDocsWebJavascriptReferenceOperatorsIn]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators/in "in 运算符|MDN"  

[PwabuilderImagegenerator]: https://www.pwabuilder.com/imageGenerator "图像生成器|PWABuilder"  

[RollupjsMain]: https://rollupjs.org "rollup.js"  

[V8DevFeaturesPrivateBrandChecks]: https://v8.dev/features/private-brand-checks "私有品牌检查 obj #foo中的品牌|V8"  
[V8DevFeaturesClassFieldsPrivateClassFields]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共和私有类|V8"  

[WebpackJsMain]: https://webpack.js.org "webpack"  

> [!NOTE]
> <span data-ttu-id="2ead5-398">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2ead5-398">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2ead5-399">原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-91)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="2ead5-399">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-91) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2ead5-401">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2ead5-401">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
