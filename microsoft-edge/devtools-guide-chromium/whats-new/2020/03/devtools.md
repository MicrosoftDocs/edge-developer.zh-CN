---
description: Emulate color vision deficiencies, Dock To Left in the Command Menu, and more.
title: What's new in DevTools (Microsoft Edge 83)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f9eb306ab7b30495c91ff4a70797898459d7e722
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015480"
---
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

# <span data-ttu-id="20ba5-104">DevTools （Microsoft Edge 83）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="20ba5-104">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="20ba5-105">按照更新的 Chromium 计划，我们将调整即将推出的 Microsoft Edge 版本的计划，并取消 Microsoft Edge 82 版本。</span><span class="sxs-lookup"><span data-stu-id="20ba5-105">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="20ba5-106">有关详细信息，请查看我们的 [博客文章][WindowsBlogStableRelease]。</span><span class="sxs-lookup"><span data-stu-id="20ba5-106">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="20ba5-107">下面是 Microsoft Edge 83 的 DevTools 中提供的新功能。</span><span class="sxs-lookup"><span data-stu-id="20ba5-107">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <span data-ttu-id="20ba5-108">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="20ba5-108">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="20ba5-109">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span><span class="sxs-lookup"><span data-stu-id="20ba5-109">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="20ba5-110">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span><span class="sxs-lookup"><span data-stu-id="20ba5-110">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="20ba5-111">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="20ba5-111">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="20ba5-112">在 Windows 10 设备上远程调试 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="20ba5-112">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="20ba5-113">现在，[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 \(Beta\)][RemoteTools] 应用。</span><span class="sxs-lookup"><span data-stu-id="20ba5-113">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="20ba5-114">使用此应用程序扩展了[ Windows 设备门户][WindowsUwpDebugTestPerfDevicePortal]，你可以将开发计算机上运行的 Microsoft Edge 实例连接到远程 Windows 10 设备，请参阅目标列表\（Windows 10 设备上将打开 Microsoft Edge 和[ PWAs ][PprgressiveWebAppsChromiumIndex]中的所有选项卡\），然后针对远程 Windows 10 设备上运行的目标使用开发计算机上的 DevTools。</span><span class="sxs-lookup"><span data-stu-id="20ba5-114">Using this app, which extends the [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, see a list of targets \(all tabs in Microsoft Edge and [PWAs][PprgressiveWebAppsChromiumIndex] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="20ba5-116">The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span><span class="sxs-lookup"><span data-stu-id="20ba5-116">The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-117">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span><span class="sxs-lookup"><span data-stu-id="20ba5-117">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span></span>  <span data-ttu-id="20ba5-118">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-118">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

### <span data-ttu-id="20ba5-119">New ways to access Settings</span><span class="sxs-lookup"><span data-stu-id="20ba5-119">New ways to access Settings</span></span>  

<span data-ttu-id="20ba5-120">你可以自定义大量的 DevTools 设置，以使 DevTools 外观、感觉和工作方式达到你的要求。</span><span class="sxs-lookup"><span data-stu-id="20ba5-120">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="20ba5-121">在 Microsoft Edge 83 中，访问 DevTools 中的 [设置][DevtoolsCustomizeIndexSettings] 现在更为简单。</span><span class="sxs-lookup"><span data-stu-id="20ba5-121">In Microsoft Edge 83, accessing [Settings][DevtoolsCustomizeIndexSettings] in the DevTools is now much easier.</span></span> <span data-ttu-id="20ba5-122">使用 "控制台警报" 和 "主菜单" 旁边的齿轮图标打开 "设置"。</span><span class="sxs-lookup"><span data-stu-id="20ba5-122">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="20ba5-124">The gear icon opens **Settings** in the DevTools</span><span class="sxs-lookup"><span data-stu-id="20ba5-124">The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-125">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span><span class="sxs-lookup"><span data-stu-id="20ba5-125">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="20ba5-127">**Main Menu** > **More tools** > **Settings**</span><span class="sxs-lookup"><span data-stu-id="20ba5-127">**Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-128">Chromium issue [#1050855][CR1050855]</span><span class="sxs-lookup"><span data-stu-id="20ba5-128">Chromium issue [#1050855][CR1050855]</span></span>

### <span data-ttu-id="20ba5-129">新增和改进的 infobars</span><span class="sxs-lookup"><span data-stu-id="20ba5-129">New and improved infobars</span></span>

<span data-ttu-id="20ba5-130">DevTools 中的信息性通知栏 \(infobars\) 现在具有改进的外观和功能。</span><span class="sxs-lookup"><span data-stu-id="20ba5-130">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="20ba5-131">在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="20ba5-131">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="20ba5-133">Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span><span class="sxs-lookup"><span data-stu-id="20ba5-133">Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-134">Chromium issue [#1056348][CR1056348]</span><span class="sxs-lookup"><span data-stu-id="20ba5-134">Chromium issue [#1056348][CR1056348]</span></span>

### <span data-ttu-id="20ba5-135">使用键盘导航颜色选取器</span><span class="sxs-lookup"><span data-stu-id="20ba5-135">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="20ba5-136">[颜色选取器][DevtoolsCssReferenceColorPicker] 是 "[元素][DevtoolsCssIndex]" 面板中的 GUI 用于更改 `color` 和 `background-color` 声明。</span><span class="sxs-lookup"><span data-stu-id="20ba5-136">The [Color Picker][DevtoolsCssReferenceColorPicker] is a GUI in the [Elements panel][DevtoolsCssIndex] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="20ba5-137">在早期版本的 Microsoft Edge 中，无法使用键盘导航 [颜色选取器][DevtoolsCssReferenceColorPicker] 的 **阴影** 部分。</span><span class="sxs-lookup"><span data-stu-id="20ba5-137">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="20ba5-139">You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span><span class="sxs-lookup"><span data-stu-id="20ba5-139">You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-140">在 Microsoft Edge 83 中，你可以使用键盘在颜色选取器的**阴影** 部分移动选取器。</span><span class="sxs-lookup"><span data-stu-id="20ba5-140">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="20ba5-141">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="20ba5-141">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="20ba5-142">现在，刷新页面后将填充“属性”选项卡</span><span class="sxs-lookup"><span data-stu-id="20ba5-142">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="20ba5-143">在 Microsoft Edge 81 及更早版本中，在 "[元素][DevtoolsCssIndex]" 面板中的 **"属性"选项卡**因页面刷新而损坏。</span><span class="sxs-lookup"><span data-stu-id="20ba5-143">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][DevtoolsCssIndex] was broken by page refreshes.</span></span>  <span data-ttu-id="20ba5-144">刷新页面时，**"属性" 选项卡** 未填充当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="20ba5-144">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="20ba5-146">In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span><span class="sxs-lookup"><span data-stu-id="20ba5-146">In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-147">在 Microsoft Edge 83 中，你现在可以在 **"属性" 选项卡**中页面刷新后看到当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="20ba5-147">In Microsoft Edge 83, you are now able to see the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="20ba5-149">In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span><span class="sxs-lookup"><span data-stu-id="20ba5-149">In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-150">Chromium issue [#1050999][CR1050999]</span><span class="sxs-lookup"><span data-stu-id="20ba5-150">Chromium issue [#1050999][CR1050999]</span></span>  

### <span data-ttu-id="20ba5-151">使用箭头键在 "更改" 工具中滚动</span><span class="sxs-lookup"><span data-stu-id="20ba5-151">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="20ba5-152">**"更改" 工具** 跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="20ba5-152">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="20ba5-153">你可使用 **"更改" 工具** 快速查看所有更改，并将其放回编辑器/IDE。</span><span class="sxs-lookup"><span data-stu-id="20ba5-153">You are able to use the **Changes tool** to quickly see all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="20ba5-154">按 DevTools 中的 "`Ctrl`+`Shift`+`P`"，打开 **"更改"工具**，以打开 "[命令菜单][DevToolsCommandMenuIndex]" 并键入 `changes`。</span><span class="sxs-lookup"><span data-stu-id="20ba5-154">Open the **Changes tool** by pressing `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevToolsCommandMenuIndex] and typing `changes`.</span></span>  <span data-ttu-id="20ba5-155">选择并运行 "**显示更改**" 命令以在 DevTools 抽屉中打开 **"更改" 工具**。</span><span class="sxs-lookup"><span data-stu-id="20ba5-155">Select and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="20ba5-156">对缩小文件进行更改后，**"更改" 工具** 可用于水平滚动以查看所有缩小代码。</span><span class="sxs-lookup"><span data-stu-id="20ba5-156">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to see all of your minified code.</span></span>  <span data-ttu-id="20ba5-157">从 Microsoft Edge 83 开始，你现在可以使用键盘上的箭头键水平滚动。</span><span class="sxs-lookup"><span data-stu-id="20ba5-157">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="20ba5-159">In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**</span><span class="sxs-lookup"><span data-stu-id="20ba5-159">In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-160">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-160">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="20ba5-161">Chromium issue [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="20ba5-161">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="20ba5-162">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="20ba5-162">Announcements from the Chromium project</span></span>  

<span data-ttu-id="20ba5-163">以下各部分公布了 Microsoft Edge 83 中提供的其他功能，这些功能是对开源 Chromium 项目的贡献。</span><span class="sxs-lookup"><span data-stu-id="20ba5-163">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="20ba5-164">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="20ba5-164">Emulate vision deficiencies</span></span>  

<span data-ttu-id="20ba5-165">打开["渲染" 选项卡][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ，使用新的"**模拟视觉缺陷**" 功能，更好地了解有不同类型视觉缺陷的人们如何体验你的网站。</span><span class="sxs-lookup"><span data-stu-id="20ba5-165">Open the [Rendering tab][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="20ba5-167">Emulating blurred vision</span><span class="sxs-lookup"><span data-stu-id="20ba5-167">Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-168">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span><span class="sxs-lookup"><span data-stu-id="20ba5-168">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="20ba5-169">颜色视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="20ba5-169">Color Vision Deficiency</span></span> | <span data-ttu-id="20ba5-170">详细信息</span><span class="sxs-lookup"><span data-stu-id="20ba5-170">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="20ba5-171">红色盲</span><span class="sxs-lookup"><span data-stu-id="20ba5-171">Protanopia</span></span> | <span data-ttu-id="20ba5-172">无法感觉任何红色的光线。</span><span class="sxs-lookup"><span data-stu-id="20ba5-172">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="20ba5-173">绿色盲</span><span class="sxs-lookup"><span data-stu-id="20ba5-173">Deuteranopia</span></span> | <span data-ttu-id="20ba5-174">无法感觉任何绿色的光线。</span><span class="sxs-lookup"><span data-stu-id="20ba5-174">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="20ba5-175">黄蓝色盲</span><span class="sxs-lookup"><span data-stu-id="20ba5-175">Tritanopia</span></span> | <span data-ttu-id="20ba5-176">无法感觉任何蓝色的光线。</span><span class="sxs-lookup"><span data-stu-id="20ba5-176">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="20ba5-177">全色盲</span><span class="sxs-lookup"><span data-stu-id="20ba5-177">Achromatopsia</span></span> | <span data-ttu-id="20ba5-178">无法感觉任何颜色，灰色阴影除外\（极少\）。</span><span class="sxs-lookup"><span data-stu-id="20ba5-178">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="20ba5-179">存在这些色觉缺陷的不太极端的版本，实际上它们更为常见。</span><span class="sxs-lookup"><span data-stu-id="20ba5-179">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="20ba5-180">例如，红色弱降低了对红光的敏感性（与红色盲相对，后者完全无法感知红光）。</span><span class="sxs-lookup"><span data-stu-id="20ba5-180">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="20ba5-181">但是，这些异常视力缺陷的定义不是很明确：每个视力缺陷者都不同，并且可能看到的事物都不相同（能够感知更多/更少的相关颜色）。</span><span class="sxs-lookup"><span data-stu-id="20ba5-181">However, these -omaly vision deficiencies are not as clearly defined: every person with such a vision deficiency is different and might see things differently (being able to perceive more/less of the relevant colors).</span></span>  

<span data-ttu-id="20ba5-182">通过在 DevTools 中进行更极端的仿真设计，可以保证红色弱、绿色弱、黄蓝色弱和全色弱的人也可访问你的 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="20ba5-182">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="20ba5-183">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-183">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="20ba5-184">Chromium issue [#1003700][CR1003700]</span><span class="sxs-lookup"><span data-stu-id="20ba5-184">Chromium issue [#1003700][CR1003700]</span></span>  

### <span data-ttu-id="20ba5-185">模拟语言环境</span><span class="sxs-lookup"><span data-stu-id="20ba5-185">Emulate locales</span></span>  

<span data-ttu-id="20ba5-186">通过在**传感器**  >  **位置**中设置位置来模拟语言环境。</span><span class="sxs-lookup"><span data-stu-id="20ba5-186">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="20ba5-187">[打开**命令菜单** ][DevToolsCommandMenuIndex]，然后键入`Sensors`以访问**传感器**选项卡。执行完这些操作后，DevTools 会修改当前的默认语言环境，从而影响以下代码。</span><span class="sxs-lookup"><span data-stu-id="20ba5-187">[Open the **Command Menu**][DevToolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="20ba5-188">例如，API：</span><span class="sxs-lookup"><span data-stu-id="20ba5-188">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="20ba5-189">其他可识别语言环境的 JavaScript API，例如`String.prototype.localeCompare`和`*.prototype.toLocaleString`，例如：</span><span class="sxs-lookup"><span data-stu-id="20ba5-189">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="20ba5-190">DOM APIs such as `navigator.language` and</span><span class="sxs-lookup"><span data-stu-id="20ba5-190">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="20ba5-191">The [Accept-Language][MDNAcceptLanguage] HTTP request header</span><span class="sxs-lookup"><span data-stu-id="20ba5-191">The [Accept-Language][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="20ba5-192">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span><span class="sxs-lookup"><span data-stu-id="20ba5-192">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span></span>  <span data-ttu-id="20ba5-193">只有后续请求才会反映对 `Accept-Language` HTTP 标头的更改。</span><span class="sxs-lookup"><span data-stu-id="20ba5-193">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="20ba5-195">Emulating a locale</span><span class="sxs-lookup"><span data-stu-id="20ba5-195">Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-196">To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].</span><span class="sxs-lookup"><span data-stu-id="20ba5-196">To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="20ba5-197">Chromium 问题 [#1051822][CR1051822]</span><span class="sxs-lookup"><span data-stu-id="20ba5-197">Chromium issue [#1051822][CR1051822]</span></span>

### <span data-ttu-id="20ba5-198">跨域嵌入程序策略 (COEP) 调试</span><span class="sxs-lookup"><span data-stu-id="20ba5-198">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="20ba5-199">"网络" 面板现在提供[跨域嵌入程序策略 (COEP)][COEP] 调试信息。</span><span class="sxs-lookup"><span data-stu-id="20ba5-199">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="20ba5-200">“**状态**”列现在提供有关为何阻止请求的快速说明，以及查看该请求标头以进行进一步调试的链接：</span><span class="sxs-lookup"><span data-stu-id="20ba5-200">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="20ba5-202">Blocked requests in the **Status** column</span><span class="sxs-lookup"><span data-stu-id="20ba5-202">Blocked requests in the **Status** column</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-203">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span><span class="sxs-lookup"><span data-stu-id="20ba5-203">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="20ba5-205">More guidance in the **Response Headers** section</span><span class="sxs-lookup"><span data-stu-id="20ba5-205">More guidance in the **Response Headers** section</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-206">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-206">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="20ba5-207">Chromium issue [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="20ba5-207">Chromium issue [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="20ba5-208">New icons for breakpoints, conditional breakpoints, and logpoints</span><span class="sxs-lookup"><span data-stu-id="20ba5-208">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="20ba5-209">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span><span class="sxs-lookup"><span data-stu-id="20ba5-209">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span></span>  

*   <span data-ttu-id="20ba5-210">Breakpoints \(</span><span class="sxs-lookup"><span data-stu-id="20ba5-210">Breakpoints \(</span></span>![Breakpoint](../../media/2020/03/breakpoint.msft.png)<span data-ttu-id="20ba5-212">\) are represented by red circles.</span><span class="sxs-lookup"><span data-stu-id="20ba5-212">\) are represented by red circles.</span></span>  
*   <span data-ttu-id="20ba5-213">Conditional Breakpoints \(</span><span class="sxs-lookup"><span data-stu-id="20ba5-213">Conditional Breakpoints \(</span></span>![Conditional Breakpoint](../../media/2020/03/conditional.msft.png)<span data-ttu-id="20ba5-215">\) are represented by half-red half-white circles.</span><span class="sxs-lookup"><span data-stu-id="20ba5-215">\) are represented by half-red half-white circles.</span></span>  
*   <span data-ttu-id="20ba5-216">Logpoints \(</span><span class="sxs-lookup"><span data-stu-id="20ba5-216">Logpoints \(</span></span>![Logpoint](../../media/2020/03/logpoint.msft.png)<span data-ttu-id="20ba5-218">\) are represented by red circles with Console icons.</span><span class="sxs-lookup"><span data-stu-id="20ba5-218">\) are represented by red circles with Console icons.</span></span>  

<span data-ttu-id="20ba5-219">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span><span class="sxs-lookup"><span data-stu-id="20ba5-219">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span></span>  

<span data-ttu-id="20ba5-220">Chromium issue [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="20ba5-220">Chromium issue [#1041830][CR1041830]</span></span>  

### <span data-ttu-id="20ba5-221">View network requests that set a specific cookie path</span><span class="sxs-lookup"><span data-stu-id="20ba5-221">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="20ba5-222">在**网络**面板中使用新的`cookie-path`过滤关键字来关注设置了特定[ cookie 路径][MDNCookiePath]的网络请求。</span><span class="sxs-lookup"><span data-stu-id="20ba5-222">Use the new `cookie-path` filter keyword in the **Network** panel to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="20ba5-223">查看[按属性过滤请求][DevtoolsNetworkReferenceFilterRequestsProperties]以发现更多关键词，例如`cookie-path`。</span><span class="sxs-lookup"><span data-stu-id="20ba5-223">Check out [Filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties] to discover more keywords like `cookie-path`.</span></span>

### <span data-ttu-id="20ba5-224">从 "命令" 菜单向左停靠</span><span class="sxs-lookup"><span data-stu-id="20ba5-224">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="20ba5-225">打开 ["命令菜单"][DevToolsCommandMenuIndex]，并运行" `Dock to left` "命令以将 DevTools 移到视线的左侧。</span><span class="sxs-lookup"><span data-stu-id="20ba5-225">Open the [Command Menu][DevToolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="20ba5-227">DevTools docked to the left of the viewport</span><span class="sxs-lookup"><span data-stu-id="20ba5-227">DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="20ba5-228">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [Main Menu][DevtoolsCustomizePlacementsChangeMainMenu].</span><span class="sxs-lookup"><span data-stu-id="20ba5-228">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [Main Menu][DevtoolsCustomizePlacementsChangeMainMenu].</span></span>  <span data-ttu-id="20ba5-229">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span><span class="sxs-lookup"><span data-stu-id="20ba5-229">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="20ba5-230">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-230">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="20ba5-231">Chromium issue [#1011679][CR1011679]</span><span class="sxs-lookup"><span data-stu-id="20ba5-231">Chromium issue [#1011679][CR1011679]</span></span>  

### <span data-ttu-id="20ba5-232">"审核" 面板现在是 "灯塔" 面板</span><span class="sxs-lookup"><span data-stu-id="20ba5-232">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="20ba5-233">DevTools 团队经常从 Web 开发人员那里获得反馈，尽管可以从 DevTools 运行[灯塔][GithubGoogleChromeLighthouse]，但在尝试运行时却找不到“灯塔”面板，因此**审核**面板现在是**灯塔**面板。</span><span class="sxs-lookup"><span data-stu-id="20ba5-233">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="20ba5-235">The Lighthouse panel</span><span class="sxs-lookup"><span data-stu-id="20ba5-235">The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="20ba5-236">The **Lighthouse** panel provides links to content hosted on third-party websites.</span><span class="sxs-lookup"><span data-stu-id="20ba5-236">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="20ba5-237">Microsoft 对这些网站及其可能收集的任何数据的内容不承担任何责任。</span><span class="sxs-lookup"><span data-stu-id="20ba5-237">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <span data-ttu-id="20ba5-238">删除文件夹中的所有本地覆盖</span><span class="sxs-lookup"><span data-stu-id="20ba5-238">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="20ba5-239">设置**本地覆盖**后可右键单击文件夹，然后选择新的 "**删除所有覆盖**" 选项以删除该文件夹中的所有本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="20ba5-239">After setting up **Local Overrides** you may right-click a folder and select the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="20ba5-241">Delete all overrides</span><span class="sxs-lookup"><span data-stu-id="20ba5-241">Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-242">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-242">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="20ba5-243">Chromium issue [#1016501][CR1016501]</span><span class="sxs-lookup"><span data-stu-id="20ba5-243">Chromium issue [#1016501][CR1016501]</span></span>  

### <span data-ttu-id="20ba5-244">更新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="20ba5-244">Updated Long tasks UI</span></span>  

<span data-ttu-id="20ba5-245">**长任务**是长时间垄断了主线程，从而导致网页冻结的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="20ba5-245">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="20ba5-246">你已经能够[在“性能”面板中可视化长任务][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]了一段时间，但是在Microsoft Edge 83中，“性能”面板中的长任务可视化 UI 已更新。</span><span class="sxs-lookup"><span data-stu-id="20ba5-246">You have been able to [visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="20ba5-247">现在，任务的长任务部分的颜色为带条纹红色背景。</span><span class="sxs-lookup"><span data-stu-id="20ba5-247">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="20ba5-249">The new Long Task UI</span><span class="sxs-lookup"><span data-stu-id="20ba5-249">The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="20ba5-250">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span><span class="sxs-lookup"><span data-stu-id="20ba5-250">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="20ba5-251">Chromium issue [#1054447][CR1054447]</span><span class="sxs-lookup"><span data-stu-id="20ba5-251">Chromium issue [#1054447][CR1054447]</span></span>  

### <span data-ttu-id="20ba5-252">"清单" 窗格中的可屏蔽图标支持</span><span class="sxs-lookup"><span data-stu-id="20ba5-252">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="20ba5-253">Android Oreo 引入了自适应图标，可在不同的设备模型之间显示各种形状中的应用图标。</span><span class="sxs-lookup"><span data-stu-id="20ba5-253">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="20ba5-254">**可屏蔽图标**是支持自适应图标的新图标格式，使你可以确保[ PWA ][PprgressiveWebAppsChromiumIndex]图标在支持可屏蔽图标标准的设备上看起来不错。</span><span class="sxs-lookup"><span data-stu-id="20ba5-254">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][PprgressiveWebAppsChromiumIndex] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="20ba5-255">在**清单**窗格中启用新的**仅显示可屏蔽图标的最小安全区域**复选框，以检查可屏蔽图标在 Android Oreo 设备上看起来是否良好。</span><span class="sxs-lookup"><span data-stu-id="20ba5-255">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="The Remote Tools for Microsoft Edge (Beta) app available in the Microsoft Store" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="20ba5-257">The **Show only the minimum safe area for maskable icons** checkbox</span><span class="sxs-lookup"><span data-stu-id="20ba5-257">The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="20ba5-258">This feature launched in Microsoft Edge 81.</span><span class="sxs-lookup"><span data-stu-id="20ba5-258">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="20ba5-259">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span><span class="sxs-lookup"><span data-stu-id="20ba5-259">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <span data-ttu-id="20ba5-260">Download the Microsoft Edge preview channels</span><span class="sxs-lookup"><span data-stu-id="20ba5-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="20ba5-261">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="20ba5-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="20ba5-262">The preview channels give you access to the latest DevTools features.</span><span class="sxs-lookup"><span data-stu-id="20ba5-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="20ba5-263">Getting in touch with Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="20ba5-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "What's New In DevTools (Microsoft Edge 81) | Microsoft Docs"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Run Commands With The Microsoft Edge DevTools Command Menu | Microsoft Docs"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "Change colors with the Color Picker | Microsoft Docs"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "Get Started With Viewing And Changing CSS | Microsoft Docs"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "Change placement from the main menu | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "View main thread activity | Microsoft Docs"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "Analyze rendering performance with the Rendering tab | Microsoft Docs"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Progressive Web Apps on Windows | Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "Get Started with Remote Debugging Windows 10 Devices | Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "Line-of-code breakpoints - How To Pause Your Code With Breakpoints In Microsoft Edge DevTools | Microsoft Docs"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "Filter requests by properties - Network analysis reference | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "Settings - Customize Microsoft Edge DevTools  | Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal overview"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Remote Tools for Microsoft Edge (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview Channels"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "Update on Stable channel releases for Microsoft Edge"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "New Issue - MicrosoftDocs/edge-developer - GitHub"  

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | Post a Tweet"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter account"  
[TheWebWeWant]: https://webwewant.fyi "The Web We Want"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "Types of Colour Blindness"  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "Accept-Language | MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Set-Cookie | MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "Locale-dependent code example"  

[CR963183]: https://crbug.com/963183 "问题 963183：DevTools 不符合 WCAG"  
[CR1003700]: https://crbug.com/1003700 "问题 1003700：添加 DevTools 支持颜色视觉缺陷模拟"  
[CR1011679]: https://crbug.com/1011679 "问题 1011679：使用命令菜单引入 "停靠到左侧""  
[CR1016501]: https://crbug.com/1016501 "问题 1016501：功能请求：用于删除所有本地覆盖的按钮"  
[CR1050999]: https://crbug.com/1050999 "问题 1050999：“属性”选项卡"  
[CR1051466]: https://crbug.com/1051466 "问题 1051466：支持 DevTools 中的 COOP/COEP 调试"  
[CR1054447]: https://crbug.com/1054447 "问题 1054447：更新 DevTools 时间线中的性能指标"  
[CR1051822]: https://crbug.com/1051822 "问题 1051822：DevTools：将 UI 添加到仿真区域设置"
[CR1041830]: https://crbug.com/1041830 "问题 1041830：改进断点颜色"
[ CR1050855]: https://crbug.com/1050855  "问题 1050855：难以发现设置视图"
[CR1050855]: https://crbug.com/1050855 "Issue 1050855: Settings view is difficult to discover"
[CR1056348]: https://crbug.com/1056348 "问题 1056348：信息栏组件刷新"

[ COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn  "COOP 和 COEP 详解——跨域开放者策略"   
[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "COOP and COEP explained - Cross-Origin Opener Policy"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP and COEP explained - Cross-Origin Embedder Policy"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse | GitHub"  

> [!NOTE]
> <span data-ttu-id="20ba5-305">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="20ba5-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="20ba5-306">原始页面位于[此处](https://developers.google.com/web/updates/2020/03/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="20ba5-306">The original page is found [here](https://developers.google.com/web/updates/2020/03/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="20ba5-308">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="20ba5-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
