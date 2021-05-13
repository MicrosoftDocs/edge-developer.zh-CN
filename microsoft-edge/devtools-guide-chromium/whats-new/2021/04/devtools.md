---
description: 波浪下划线突出显示元素工具、服务工作者更新时间线等中的代码问题。
title: 'DevTools (Microsoft Edge 91 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 473b2537b631a77a182c04b6986051a4ce7aae03
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564817"
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
# <a name="whats-new-in-devtools-microsoft-edge-91"></a><span data-ttu-id="e24cd-104">DevTools (Microsoft Edge 91 中的新增) </span><span class="sxs-lookup"><span data-stu-id="e24cd-104">What's New In DevTools (Microsoft Edge 91)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="wavy-underlines-highlight-code-issues-and-improvements-in-elements-tool"></a><span data-ttu-id="e24cd-105">波浪下划线突出显示元素工具中的代码问题和改进</span><span class="sxs-lookup"><span data-stu-id="e24cd-105">Wavy underlines highlight code issues and improvements in Elements tool</span></span>  

<!--  Title: Get code hints in Elements tool  -->  
<!--  Subtitle: Wavy underlines like the ones you see in Visual Studio Code now display in the Elements tool.  Underlines alert you to code issues related to accessibility, compatibility, security, performance, and  so on.  -->  

<span data-ttu-id="e24cd-106">在大多数新式 ID 中，文本下的波浪下划线指示语法错误。</span><span class="sxs-lookup"><span data-stu-id="e24cd-106">In most modern IDEs, wavy underlines under text indicate syntax errors.</span></span>   <span data-ttu-id="e24cd-107">在 Microsoft Edge 91 或更高版本中，在"元素"工具的**DOM**视图中，HTML 下会显示**波浪下划线。**</span><span class="sxs-lookup"><span data-stu-id="e24cd-107">In Microsoft Edge version 91 or later, wavy underlines display under HTML in the **DOM** view of the **Elements** tool.</span></span>  <span data-ttu-id="e24cd-108">波浪下划线表示与辅助功能、兼容性、性能等相关的代码问题和建议。</span><span class="sxs-lookup"><span data-stu-id="e24cd-108">The wavy underlines indicate code issues and suggestions related to accessibility, compatibility, performance, and so on.</span></span>  <span data-ttu-id="e24cd-109">若要详细了解如何查看和编辑问题，请导航到查找并修复开发人员Microsoft Edge[工具中的问题][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="e24cd-109">For more information about how to review and edit issues, navigate to [Find and fix problems with the Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

<span data-ttu-id="e24cd-110">若要打开 **问题** 工具并了解有关该问题以及如何修复它，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="e24cd-110">To open the **Issues** tool and learn more about the issue and how to fix it, complete one of the following actions.</span></span>  

*   <span data-ttu-id="e24cd-111">选择并按住 `Shift` ，然后选择任何波浪下划线。</span><span class="sxs-lookup"><span data-stu-id="e24cd-111">Select and hold `Shift`, and then choose any wavy underline.</span></span>  
*   <span data-ttu-id="e24cd-112">完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="e24cd-112">Complete the following actions.</span></span>  
    1.  <span data-ttu-id="e24cd-113">悬停在任何波浪下划线上。</span><span class="sxs-lookup"><span data-stu-id="e24cd-113">Hover on any wavy underline.</span></span>  
    1.  <span data-ttu-id="e24cd-114">打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="e24cd-114">Open the contextual menu \(right-click\).</span></span>  
    1.  <span data-ttu-id="e24cd-115">选择 **"在问题中显示"。**</span><span class="sxs-lookup"><span data-stu-id="e24cd-115">Choose **Show in Issues**.</span></span>  
        
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues.msft.png" alt-text="在"元素"工具中选择带下划线的错误" lightbox="../../media/2021/04/elements-iframe-highlight-issues.msft.png":::
         <span data-ttu-id="e24cd-117">在"元素"工具中选择 **带下划线** 的错误</span><span class="sxs-lookup"><span data-stu-id="e24cd-117">Choose the underlined error in the **Elements** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png" alt-text="在问题工具中显示错误详细信息" lightbox="../../media/2021/04/elements-iframe-highlight-issues-focus.msft.png":::
         <span data-ttu-id="e24cd-119">在问题工具 **中显示错误** 详细信息</span><span class="sxs-lookup"><span data-stu-id="e24cd-119">Display error details in the **Issues** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a><span data-ttu-id="e24cd-120">通过信息丰富的工具提示了解 DevTools</span><span class="sxs-lookup"><span data-stu-id="e24cd-120">Learn about DevTools with informative tooltips</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<!--  Title: Learn more about DevTools with DevTools Tooltips  -->  
<!--  Subtitle: Informative overlays are now available in the default DevTools interface.  -->  

<span data-ttu-id="e24cd-121">DevTools 工具提示功能可帮助你了解 DevTools 中所有不同的工具和窗格。</span><span class="sxs-lookup"><span data-stu-id="e24cd-121">The DevTools Tooltips feature helps you learn about all the different tools and panes in DevTools.</span></span>  <span data-ttu-id="e24cd-122">若要关闭工具提示，请选择 `Esc` 。</span><span class="sxs-lookup"><span data-stu-id="e24cd-122">To turn off Tooltips, select `Esc`.</span></span>  <span data-ttu-id="e24cd-123">若要打开工具提示，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="e24cd-123">To turn on Tooltips, complete one of the following actions.</span></span>  

*   <span data-ttu-id="e24cd-124">选择 `Ctrl` + `Shift` + `H` \ (Windows/Linux\) `Cmd` + `Shift` + `H` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="e24cd-124">Select `Ctrl`+`Shift`+`H` \(Windows/Linux\) or `Cmd`+`Shift`+`H` \(macOS\).</span></span>  
*   <span data-ttu-id="e24cd-125">[打开命令菜单，][DevtoolsCommandMenuIndexOpenCommandMenu] 然后键入 `tooltips` 。</span><span class="sxs-lookup"><span data-stu-id="e24cd-125">[Open the Command Menu][DevtoolsCommandMenuIndexOpenCommandMenu] and then type `tooltips`.</span></span>  
*   <span data-ttu-id="e24cd-126">Choose **Customize and control DevTools** \ (`...` \) > **Help**Toggle the  >  **DevTools Tooltips**.</span><span class="sxs-lookup"><span data-stu-id="e24cd-126">Choose **Customize and control DevTools** \(`...`\) > **Help** > **Toggle the DevTools Tooltips**.</span></span>  

<span data-ttu-id="e24cd-127">此外，如果你打开焦点模式和 [DevTools][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] 工具提示实验，还可以选择活动栏底部的切换 **DevTools** 工具提示 \ (`?` \) **按钮**。</span><span class="sxs-lookup"><span data-stu-id="e24cd-127">Also, if you turn on the [Focus Mode and DevTools Tooltips][DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode] experiment, you may also choose the **Toggle the DevTools Tooltips** \(`?`\) button at the bottom of the **Activity Bar**.</span></span>  

<span data-ttu-id="e24cd-128">若要显示有关如何使用 DevTools 的信息，请打开工具提示，然后将鼠标悬停在 DevTools 的每个大纲区域上。</span><span class="sxs-lookup"><span data-stu-id="e24cd-128">To display more information about how to use the DevTools, turn on Tooltips, and then hover on each outlined region of the DevTools.</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png" alt-text="将鼠标悬停在"问题"工具突出显示区域中的任何位置，以显示更多详细信息" lightbox="../../media/2021/04/elements-issues-focus-mode-tooltips.msft.png":::
   <span data-ttu-id="e24cd-130">将鼠标悬停在"问题"工具突出显示区域 **中的任何位置，** 以显示更多详细信息</span><span class="sxs-lookup"><span data-stu-id="e24cd-130">Hover on anywhere in the highlighted region of the **Issues** tool to display more details</span></span>  
:::image-end:::  

## <a name="service-worker-update-timeline"></a><span data-ttu-id="e24cd-131">服务工作者更新时间线</span><span class="sxs-lookup"><span data-stu-id="e24cd-131">Service worker update timeline</span></span>  

<!--todo:  Update the linked [Service Worker improvements][DevtoolsServiceWorkerIndex] article.  -->  

<!--  Title: The tasks associated with your Service Worker  -->  
<!--  Subtitle: Debug with Service Worker Update Cycle  -->  

<span data-ttu-id="e24cd-132">在 Microsoft Edge 91 或更高版本中，如果您是渐进式 Web 应用或服务工作者开发人员，您可以在应用程序工具中将服务工作者的更新生命周期显示为**时间线**。</span><span class="sxs-lookup"><span data-stu-id="e24cd-132">In Microsoft Edge version 91 or later, if you are a Progressive Web App or Service Worker developer, you may display the update lifecycle of your Service Workers as a timeline in the **Application** tool.</span></span>  <span data-ttu-id="e24cd-133">此功能可帮助您了解服务工作者在下列每个阶段所花的时间。</span><span class="sxs-lookup"><span data-stu-id="e24cd-133">This feature helps you understand the time your Service Worker spends in each of the following stages.</span></span>  

*   **<span data-ttu-id="e24cd-134">安装</span><span class="sxs-lookup"><span data-stu-id="e24cd-134">Install</span></span>**  
*   **<span data-ttu-id="e24cd-135">Wait</span><span class="sxs-lookup"><span data-stu-id="e24cd-135">Wait</span></span>**  
*   **<span data-ttu-id="e24cd-136">激活</span><span class="sxs-lookup"><span data-stu-id="e24cd-136">Activate</span></span>**  
    
:::image type="complex" source="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png" alt-text="查看服务工作者的更新周期中的时间线" lightbox="../../media/2021/04/application-service-workers-update-cycle-version-73-focus.msft.png":::
   <span data-ttu-id="e24cd-138">查看 **服务** 工作者 **的更新周期** 中的时间线</span><span class="sxs-lookup"><span data-stu-id="e24cd-138">Review the **Timeline** in the **Update Cycle** for your Service Worker</span></span>  
:::image-end:::  

<span data-ttu-id="e24cd-139">有关服务工作者的生命周期详细信息，请导航到"服务工作[线程生命周期"。][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]</span><span class="sxs-lookup"><span data-stu-id="e24cd-139">For more information about the lifecycle of your Service Workers, navigate to [The Service Worker lifecycle][ProgressiveWebAppsServiceworkerServiceWorkerLifecycle].</span></span>  <span data-ttu-id="e24cd-140">有关在 DevTools 中为渐进式 Web 应用和服务工作者调试工具的信息，请导航到"[服务工作器改进"。][DevtoolsServiceWorkerIndex]</span><span class="sxs-lookup"><span data-stu-id="e24cd-140">For more information about debugging tools for Progressive Web Apps and Service Workers in the DevTools, navigate to [Service Worker improvements][DevtoolsServiceWorkerIndex].</span></span>  <span data-ttu-id="e24cd-141">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1066604"。][CR1066604]</span><span class="sxs-lookup"><span data-stu-id="e24cd-141">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1066604][CR1066604].</span></span>  

## <a name="progressive-web-apps-no-longer-display-warnings-for-non-square-icons"></a><span data-ttu-id="e24cd-142">渐进式 Web 应用不再显示非方形图标的警告</span><span class="sxs-lookup"><span data-stu-id="e24cd-142">Progressive Web Apps no longer display warnings for non-square icons</span></span>  

<!--  Title: Non-square icons in app manifest no longer produce warnings  -->  
<!--  Subtitle: As long as square icons are included in the app manifest, non-square icons no longer produce warnings  -->  

<span data-ttu-id="e24cd-143">在 Microsoft Edge 版本[90][DevtoolsWhatsNew202102Devtools]或更早版本中，如果您在 PWA 的 Web 应用清单中包含非方形图标，则应用程序工具中的"清单\*\*\*\*"部分将在"错误和\*\*\*\* 警告"下显示每个非方形图标的警告。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e24cd-143">In [Microsoft Edge version 90][DevtoolsWhatsNew202102Devtools] or earlier, if you included a non-square icon in the Web App Manifest of your PWA, the **Manifest** section in the **Application** tool displayed a warning under **Errors and Warnings** for each non-square icon.</span></span>  <span data-ttu-id="e24cd-144">在Microsoft Edge版本 91 或更高版本中，\*\*\*\* 如果至少提供一\*\*\*\* 个正方形图标，则应用程序工具中的清单部分不会显示警告。</span><span class="sxs-lookup"><span data-stu-id="e24cd-144">In Microsoft Edge version 91 or later, the **Manifest** section in the **Application** tool displays no warnings if you provide at least one square icon.</span></span>  <span data-ttu-id="e24cd-145">如果未提供任何方形图标，则会显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="e24cd-145">If you don't provide any square icons, a warning displays the following message.</span></span>  

```output
Most operating systems require square icons.  Please include at least one square icon in the array.  
```  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png" alt-text="在 Microsoft Edge 版本 90 或更早版本中，对于非正方形的每个图标，将显示错误" lightbox="../../media/2021/04/edge89-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="e24cd-147">在 Microsoft Edge 版本 90 或更早版本中，对于非正方形的每个图标，将显示错误</span><span class="sxs-lookup"><span data-stu-id="e24cd-147">In Microsoft Edge version 90 or earlier, an error displays for each icon that is non-square</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png" alt-text="在 Microsoft Edge 版本 91 或更高版本中，提供至少一个正方形图标时不会显示任何错误" lightbox="../../media/2021/04/edge91-application-manifest-errors-and-warnings.msft.png":::
         <span data-ttu-id="e24cd-149">在 Microsoft Edge 版本 91 或更高版本中，提供至少一个正方形图标时不会显示任何错误</span><span class="sxs-lookup"><span data-stu-id="e24cd-149">In Microsoft Edge version 91 or later, no error displays when you provide at least one square icon</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e24cd-150">若要在 Web 应用程序清单中查看错误和警告，请导航到 **"应用程序"** 工具并选择"清单 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="e24cd-150">To review errors and warnings in your Web App Manifest, navigate to the **Application** tool and choose the **Manifest** section.</span></span>  <span data-ttu-id="e24cd-151">错误和警告列在"错误和警告 **"** 标题下。</span><span class="sxs-lookup"><span data-stu-id="e24cd-151">Errors and warnings are listed under the **Errors and Warnings** heading.</span></span>  <span data-ttu-id="e24cd-152">有关 Web 应用部件清单的信息，请导航到"使用 Web 应用清单"将 [渐进式 Web 应用集成到操作系统中][ProgressiveWebAppsWebappmanifests]。</span><span class="sxs-lookup"><span data-stu-id="e24cd-152">For more information about the Web App Manifest, navigate to [Use the Web App Manifest to integrate your Progressive Web App into the Operating System][ProgressiveWebAppsWebappmanifests].</span></span>  <span data-ttu-id="e24cd-153">若要创建要包括在 Web 应用清单中的图标，请导航到 [PWABuilder Image Generator][PwabuilderImagegenerator]。</span><span class="sxs-lookup"><span data-stu-id="e24cd-153">To create icons to include in your Web App Manifest, navigate to the [PWABuilder Image Generator][PwabuilderImagegenerator].</span></span>  <span data-ttu-id="e24cd-154">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1185945"。][CR1185945]</span><span class="sxs-lookup"><span data-stu-id="e24cd-154">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1185945][CR1185945].</span></span>  

## <a name="localized-devtools-now-supported-in-chromium-based-browsers"></a><span data-ttu-id="e24cd-155">本地化的 DevTools 现在Chromium的浏览器中受支持</span><span class="sxs-lookup"><span data-stu-id="e24cd-155">Localized DevTools now supported in Chromium-based browsers</span></span>  

<!--  Title: Localization for all  -->  
<!--  Subtitle: Match browser language enabled to all Chromium-based browsers  -->  

<span data-ttu-id="e24cd-156">从 Microsoft Edge[版本 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]开始，Microsoft Edge开发人员工具以你自己的语言显示。</span><span class="sxs-lookup"><span data-stu-id="e24cd-156">Starting in [Microsoft Edge version 81][DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages], Microsoft Edge DevTools displays in your own language.</span></span>  <span data-ttu-id="e24cd-157">许多开发人员使用 StackOverflow 等其他开发人员工具，Visual Studio Code语言进行开发，而不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="e24cd-157">Many developers use other developer tools like StackOverflow and Visual Studio Code in their native language, not just in English.</span></span>  <span data-ttu-id="e24cd-158">开发人员Microsoft Edge、Chrome DevTools 团队和 Google Lighthouse 团队协作，在所有基于 Chromium 的浏览器中提供相同的体验。</span><span class="sxs-lookup"><span data-stu-id="e24cd-158">The Microsoft Edge DevTools team, Chrome DevTools team, and the Google Lighthouse team collaborated to provide the same experience in all Chromium-based browsers.</span></span>  <span data-ttu-id="e24cd-159">若要详细了解如何在语言中使用 DevTools，请导航到"[更改 DevTools 语言设置"。][DevtoolsCustomizeLocalization]</span><span class="sxs-lookup"><span data-stu-id="e24cd-159">For more information about how to use DevTools in your language, navigate to [Change DevTools language settings][DevtoolsCustomizeLocalization].</span></span>  <span data-ttu-id="e24cd-160">有关开放源代码项目中有关此功能的协作Chromium，请导航到[1136655。][CR1136655]</span><span class="sxs-lookup"><span data-stu-id="e24cd-160">For more information about the collaboration on this feature in the Chromium open-source project, navigate to [1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png" alt-text="Microsoft Edge浏览器和 DevTools 设置为日语" lightbox="../../media/2021/04/japanese-browser-japanese-navigation-elements-3d-view.msft.png":::
   <span data-ttu-id="e24cd-162">Microsoft Edge浏览器和 DevTools 设置为日语</span><span class="sxs-lookup"><span data-stu-id="e24cd-162">Microsoft Edge browser and DevTools set to Japanese</span></span>  
:::image-end:::  

## <a name="use-the-keyboard-to-navigate-to-css-variables"></a><span data-ttu-id="e24cd-163">使用键盘导航到 CSS 变量</span><span class="sxs-lookup"><span data-stu-id="e24cd-163">Use the keyboard to navigate to CSS variables</span></span>  

<!--  Title: Navigate to CSS variables with the arrow keys  -->  
<!--  Subtitle: In the Styles pane, use the arrow keys to choose CSS variables.  Select `Enter` to see the variable definition.  -->  

<span data-ttu-id="e24cd-164">从[Microsoft Edge版本 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]开始，"\*\*\*\* 样式"窗格将显示 CSS 变量并提供指向每个变量的定义的链接。</span><span class="sxs-lookup"><span data-stu-id="e24cd-164">Starting in [Microsoft Edge version 88][DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane], the **Styles** pane displays CSS variables and provides a link directly to the definition of each variable.</span></span>  <span data-ttu-id="e24cd-165">在 Microsoft Edge 版本 91 或更高版本中，可以使用箭头键轻松导航到 CSS 变量。</span><span class="sxs-lookup"><span data-stu-id="e24cd-165">In Microsoft Edge version 91 or later, you may use the arrow keys to easily navigate to CSS variables.</span></span>  <span data-ttu-id="e24cd-166">若要在"样式 **"窗格中打开** 定义，请将鼠标悬停在变量上，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e24cd-166">To open the definition in the **Styles** pane, hover on a variable, and then select `Enter`.</span></span>  <span data-ttu-id="e24cd-167">有关 CSS 变量详细信息，请导航到使用 CSS 自定义属性 ([变量) 。 ][MdnDocsWebCssUsingCssCustomProperties]</span><span class="sxs-lookup"><span data-stu-id="e24cd-167">For more information about CSS variables, navigate to [Using CSS custom properties (variables)][MdnDocsWebCssUsingCssCustomProperties].</span></span>  <span data-ttu-id="e24cd-168">若要在开放源代码项目中查看此功能Chromium，请导航到"问题[1187735"。][CR1187735]</span><span class="sxs-lookup"><span data-stu-id="e24cd-168">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1187735][CR1187735].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png" alt-text="--theme-body-background CSS 变量在"样式"窗格中突出显示" lightbox="../../media/2021/04/elements-styles-body-background-color-theme-body-background.msft.png":::
   <span data-ttu-id="e24cd-170">" `--theme-body-background` 样式"窗格中突出显示的\*\*\*\* CSS 变量</span><span class="sxs-lookup"><span data-stu-id="e24cd-170">The `--theme-body-background` CSS variable highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="issues-are-automatically-sorted-by-severity"></a><span data-ttu-id="e24cd-171">问题按严重性自动排序</span><span class="sxs-lookup"><span data-stu-id="e24cd-171">Issues are automatically sorted by severity</span></span>  

<!-- Title: Display Issues in severity order  -->  
<!-- Subtitle: Entries in the Issues tool now display in severity order and allow you to focus your updates on the most important issues. -->  

<span data-ttu-id="e24cd-172">问题 **工具** 显示改进网站的建议，包括辅助功能、性能、安全性等。</span><span class="sxs-lookup"><span data-stu-id="e24cd-172">The **Issues** tool displays recommendations to improve your website, including accessibility, performance, security, and so on.</span></span> <span data-ttu-id="e24cd-173">根据你的反馈，现在会自动按严重性对问题进行排序。</span><span class="sxs-lookup"><span data-stu-id="e24cd-173">Based on your feedback, issues are now automatically sorted by severity.</span></span>  <span data-ttu-id="e24cd-174">在每个反馈类别中，每个标记为"错误"的问题\*\*\*\* 首先出现，然后关注标记为"警告"的每个\*\*\*\* 问题，然后每个标记为"提示"**的问题**。</span><span class="sxs-lookup"><span data-stu-id="e24cd-174">In each feedback category, each issue marked as an **Error** appears first, followed each issue marked as a **Warning**, then each issue marked as a **Tip**.</span></span>  <span data-ttu-id="e24cd-175">为了帮助你优化问题，为将来的更新计划了额外的筛选器选项。</span><span class="sxs-lookup"><span data-stu-id="e24cd-175">To help you refine your issues, extra filter options are planned for a future update.</span></span>  <span data-ttu-id="e24cd-176">若要详细了解如何查看问题，请导航到查找并修复开发人员Microsoft Edge[工具中的问题][DevtoolsIssuesIndex]。</span><span class="sxs-lookup"><span data-stu-id="e24cd-176">For more information about how to review issues, navigate to [Find and fix problems with the Microsoft Edge DevTools Issues tool][DevtoolsIssuesIndex].</span></span>  

:::image type="complex" source="../../media/2021/04/elements-issues-ordered-issues.msft.png" alt-text=""问题"工具按严重性显示排序的问题" lightbox="../../media/2021/04/elements-issues-ordered-issues.msft.png":::
   <span data-ttu-id="e24cd-178">" **问题** "工具按严重性显示排序的问题</span><span class="sxs-lookup"><span data-stu-id="e24cd-178">The **Issues** tool displays sorted issues by severity</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-117"></a><span data-ttu-id="e24cd-179">Microsoft Edge开发人员工具Visual Studio Code 1.1.7 版</span><span class="sxs-lookup"><span data-stu-id="e24cd-179">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.7</span></span>  

<!-- Title: Microsoft Edge DevTools for Visual Studio version 1.1.7  -->  
<!-- Subtitle: Increased target closure reliability, automatically update the side panel, new contextual menu for settings and Changelog, and more. -->  

<span data-ttu-id="e24cd-180">Microsoft Edge [Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 提供了来自 Microsoft Edge 版本[88 的][DevtoolsWhatsNew202011Devtools]DevTools。</span><span class="sxs-lookup"><span data-stu-id="e24cd-180">The [Microsoft Edge Tools for Visual Studio Code extension][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] version 1.1.7 provides the DevTools from [Microsoft Edge version 88][DevtoolsWhatsNew202011Devtools].</span></span>  <span data-ttu-id="e24cd-181">此扩展现在ARM设备，不再依赖调试器[进行Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge]扩展。</span><span class="sxs-lookup"><span data-stu-id="e24cd-181">This extension now supports ARM devices and no longer depends on the [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerForEdge] extension.</span></span>  <span data-ttu-id="e24cd-182">版本 1.1.7 包括以下 Bug 修复和改进。</span><span class="sxs-lookup"><span data-stu-id="e24cd-182">Version 1.1.7 includes the following bug fixes and improvements.</span></span>  

*   <span data-ttu-id="e24cd-183">更新了目标关闭的可靠性。</span><span class="sxs-lookup"><span data-stu-id="e24cd-183">Updated the reliability of target closure.</span></span>  
*   <span data-ttu-id="e24cd-184">更新了侧面板，以在调试创建或销毁的目标时自动刷新。</span><span class="sxs-lookup"><span data-stu-id="e24cd-184">Updated the side panel to automatically refreshes when you debug targets that are created or destroyed.</span></span>  
*   <span data-ttu-id="e24cd-185">添加了一个新的上下文菜单，可让你更快地访问扩展设置和最新的 Changelog。</span><span class="sxs-lookup"><span data-stu-id="e24cd-185">Added a new contextual menu that gives you faster access to the extension settings and the latest Changelog.</span></span>  
*   <span data-ttu-id="e24cd-186">更新并简化了扩展文档（包括最新功能）的发布。</span><span class="sxs-lookup"><span data-stu-id="e24cd-186">Updated and simplified the release of extension documentation including the newest features.</span></span>  
    
<span data-ttu-id="e24cd-187">若要手动更新到版本 1.1.7，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]</span><span class="sxs-lookup"><span data-stu-id="e24cd-187">To manually update to version 1.1.7, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  <span data-ttu-id="e24cd-188">你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。</span><span class="sxs-lookup"><span data-stu-id="e24cd-188">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

<!--## Announcements from the Chromium project  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### Ipsum et Chromium  

Lorem al lorem et Chromium  To review the history of this feature in the Chromium open-source project, navigate to Issue [xxxxxxx][CRxxxxxxx].  

:::image type="complex" source="../../media/2021/04/lorem-et-chromium.msft.png" alt-text="Ipsum et Chromium" lightbox="../../media/2021/04/lorem-et-chromium.msft.png":::
   Ipsum et Chromium  
:::image-end:::  -->  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="e24cd-189">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="e24cd-189">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="e24cd-190">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="e24cd-190">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="e24cd-191">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="e24cd-191">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="e24cd-192">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="e24cd-192">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew202001DevtoolsUsingDevtoolsInOtherLanguages]: ../../2020/01/devtools.md#using-the-devtools-in-other-languages "以其他语言使用 DevTools - DevTools (Microsoft Edge 81) |Microsoft Docs"  
[DevtoolsWhatsNew202011Devtools]: ../../2020/11/devtools.md "DevTools (Microsoft Edge 88) |Microsoft Docs"  
[DevtoolsWhatsNew202011DevtoolsCssVariableDefinitionsInStylesPane]: ../../../whats-new/2020/11/devtools.md#css-variable-definitions-in-styles-pane "样式窗格中的 CSS 变量定义 - DevTools (Microsoft Edge 88 中的新增) |Microsoft Docs"  
[DevtoolsWhatsNew202102Devtools]: ../02/devtools.md "DevTools （Microsoft Edge 90） 中的新增功能|Microsoft Docs"  
[DevtoolsWhatsNew202102DevtoolsGroupToolsTogetherInFocusMode]: ../02/devtools.md#group-tools-together-in-focus-mode "在焦点模式下将工具组合在一起 - DevTools (Microsoft Edge 90 中的新增) |Microsoft Docs"  

[DevtoolsCommandMenuIndexOpenCommandMenu]: ../../../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用&quot;开发工具Microsoft Edge菜单运行命令|Microsoft Docs"  
[DevtoolsCustomizeLocalization]: ../../../customize/localization.md "更改 DevTools 语言设置 | Microsoft Docs"  
[DevtoolsIssuesIndex]: ../../../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsServiceWorkerIndex]: ../../../service-workers/index.md "服务工作者改进|Microsoft Docs"  

[ProgressiveWebAppsServiceworkerServiceWorkerLifecycle]: ../../../../progressive-web-apps-chromium/serviceworker.md#the-service-worker-lifecycle "服务工作线程生命周期 - 使用服务工作者管理网络请求和推送通知|Microsoft Docs"  
[ProgressiveWebAppsWebappmanifests]: ../../../../progressive-web-apps-chromium/webappmanifests.md "使用 Web 应用清单将渐进式 Web 应用集成到操作系统|Microsoft Docs"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
<!--[GithubMicrosoftVscodeEdgeDevtoolsPullxxx]: https://github.com/microsoft/vscode-edge-devtools/pull/xxx "Pull xxx: Lorem al Ipsum | GitHub"  -->  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerForEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR1066604]: https://crbug.com/1066604 "问题 1066604：DevTools：查看有关 ServiceWorker 安装和激活事件的详细信息|Chromium Bug"  
[CR1136655]: https://crbug.com/1136655 "问题 1136655：开发工具：本地化 V2 |Chromium Bug"  
[CR1185945]: https://crbug.com/1185945 "问题 1185945：清单警告表示所有图标都必须是方形|Chromium Bug"  
[CR1187735]: https://crbug.com/1187735 "问题 1187735：辅助功能：MAS2.1.1：键盘：无法调用&quot;Var (&quot;。) 键盘的 |Chromium Bug"  

[MdnDocsWebCssUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性（变量）| MDN"  

[PwabuilderImagegenerator]: https://www.pwabuilder.com/imageGenerator "图像生成器|PWABuilder"  

<!--  > [!NOTE]
> Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].  
> The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-91) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).  

[![Creative Commons License][CCby4Image]][CCA4IL]  
This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen
-->
