---
title: DevTools （Microsoft Edge 83）中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f1b5d147aac1b8b527cc7365f9f91a2a7974863e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942221"
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

# <span data-ttu-id="c2610-103">DevTools （Microsoft Edge 83）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="c2610-103">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="c2610-104">按照更新的 Chromium 计划，我们将调整即将推出的 Microsoft Edge 版本的计划，并取消 Microsoft Edge 82 版本。</span><span class="sxs-lookup"><span data-stu-id="c2610-104">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="c2610-105">有关详细信息，请查看我们的 [博客文章][WindowsBlogStableRelease]。</span><span class="sxs-lookup"><span data-stu-id="c2610-105">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="c2610-106">下面是 Microsoft Edge 83 的 DevTools 中提供的新功能。</span><span class="sxs-lookup"><span data-stu-id="c2610-106">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <span data-ttu-id="c2610-107">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="c2610-107">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="c2610-108">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="c2610-108">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="c2610-109">请查看这些公告，尝试使用 DevTools 和 VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="c2610-109">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="c2610-110">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="c2610-110">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="c2610-111">在 Windows 10 设备上远程调试 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c2610-111">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="c2610-112">现在，[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 \(Beta\)][RemoteTools] 应用。</span><span class="sxs-lookup"><span data-stu-id="c2610-112">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="c2610-113">使用此应用程序扩展了[ Windows 设备门户][WindowsUwpDebugTestPerfDevicePortal]，你可以将开发计算机上运行的 Microsoft Edge 实例连接到远程 Windows 10 设备，请参阅目标列表\（Windows 10 设备上将打开 Microsoft Edge 和[ PWAs ][PprgressiveWebAppsChromiumIndex]中的所有选项卡\），然后针对远程 Windows 10 设备上运行的目标使用开发计算机上的 DevTools。</span><span class="sxs-lookup"><span data-stu-id="c2610-113">Using this app, which extends the [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, see a list of targets \(all tabs in Microsoft Edge and [PWAs][PprgressiveWebAppsChromiumIndex] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="现在，Microsoft Store 中提供 Microsoft Edge 远程工具 (Beta) 应用" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="c2610-115">图 1：[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 (Beta)][RemoteTools] 应用</span><span class="sxs-lookup"><span data-stu-id="c2610-115">Figure 1:  The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-116">[阅读我们的指南以设置 Windows 10 设备和开发计算机进行远程调试][DevtoolsRemoteDebuggingWindows]。</span><span class="sxs-lookup"><span data-stu-id="c2610-116">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span></span>  <span data-ttu-id="c2610-117">通过调整或单击"发送反馈"图标告知我们你的远程[tweeting][PostTweetEdgeDevTools][调试](#getting-in-touch-with-microsoft-edge-devtools-team)体验！</span><span class="sxs-lookup"><span data-stu-id="c2610-117">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

### <span data-ttu-id="c2610-118">访问设置的新方法</span><span class="sxs-lookup"><span data-stu-id="c2610-118">New ways to access Settings</span></span>  

<span data-ttu-id="c2610-119">你可以自定义大量的 DevTools 设置，以使 DevTools 外观、感觉和工作方式达到你的要求。</span><span class="sxs-lookup"><span data-stu-id="c2610-119">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="c2610-120">在 Microsoft Edge 83 中，访问 DevTools 中的 [设置][DevtoolsCustomizeIndexSettings] 现在更为简单。</span><span class="sxs-lookup"><span data-stu-id="c2610-120">In Microsoft Edge 83, accessing [Settings][DevtoolsCustomizeIndexSettings] in the DevTools is now much easier.</span></span> <span data-ttu-id="c2610-121">使用 "控制台警报" 和 "主菜单" 旁边的齿轮图标打开 "设置"。</span><span class="sxs-lookup"><span data-stu-id="c2610-121">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="齿轮图标会打开 DevTools 中的设置" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="c2610-123">图 2：齿轮图标会打开 DevTools 中的**设置**</span><span class="sxs-lookup"><span data-stu-id="c2610-123">Figure 2:  The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-124">你还可以从**主菜单**下的"**更多工具**"下打开[设置][DevtoolsCustomizeIndexSettings]。</span><span class="sxs-lookup"><span data-stu-id="c2610-124">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="主菜单 > 更多工具 > 设置" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="c2610-126">图 3：**主菜单** > **更多工具** > **设置**</span><span class="sxs-lookup"><span data-stu-id="c2610-126">Figure 3:  **Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-127">Chromium 问题 [#1050855][CR1050855]</span><span class="sxs-lookup"><span data-stu-id="c2610-127">Chromium issue [#1050855][CR1050855]</span></span>

### <span data-ttu-id="c2610-128">新增和改进的 infobars</span><span class="sxs-lookup"><span data-stu-id="c2610-128">New and improved infobars</span></span>

<span data-ttu-id="c2610-129">DevTools 中的信息性通知栏 \(infobars\) 现在具有改进的外观和功能。</span><span class="sxs-lookup"><span data-stu-id="c2610-129">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="c2610-130">在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="c2610-130">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="用于在 Microsoft Edge 83 中整齐打印缩小文件的信息栏" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="c2610-132">图 4：用于在 Microsoft Edge 83 中整齐打印缩小文件的信息栏</span><span class="sxs-lookup"><span data-stu-id="c2610-132">Figure 4:  Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-133">Chromium 问题 [#1056348][CR1056348]</span><span class="sxs-lookup"><span data-stu-id="c2610-133">Chromium issue [#1056348][CR1056348]</span></span>

### <span data-ttu-id="c2610-134">使用键盘导航颜色选取器</span><span class="sxs-lookup"><span data-stu-id="c2610-134">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="c2610-135">[颜色选取器][DevtoolsCssReferenceColorPicker] 是 "[元素][DevtoolsCssIndex]" 面板中的 GUI 用于更改 `color` 和 `background-color` 声明。</span><span class="sxs-lookup"><span data-stu-id="c2610-135">The [Color Picker][DevtoolsCssReferenceColorPicker] is a GUI in the [Elements panel][DevtoolsCssIndex] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="c2610-136">在早期版本的 Microsoft Edge 中，无法使用键盘导航 [颜色选取器][DevtoolsCssReferenceColorPicker] 的 **阴影** 部分。</span><span class="sxs-lookup"><span data-stu-id="c2610-136">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="现在，你可以使用键盘在颜色选取器的 "阴影" 部分移动选取器" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="c2610-138">图 5：现在，你可以使用键盘在 [颜色选取器][DevtoolsCssReferenceColorPicker]的**阴影** 部分移动选取器</span><span class="sxs-lookup"><span data-stu-id="c2610-138">Figure 5:  You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-139">在 Microsoft Edge 83 中，你可以使用键盘在颜色选取器的**阴影** 部分移动选取器。</span><span class="sxs-lookup"><span data-stu-id="c2610-139">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="c2610-140">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="c2610-140">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="c2610-141">现在，刷新页面后将填充“属性”选项卡</span><span class="sxs-lookup"><span data-stu-id="c2610-141">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="c2610-142">在 Microsoft Edge 81 及更早版本中，在 "[元素][DevtoolsCssIndex]" 面板中的 **"属性"选项卡**因页面刷新而损坏。</span><span class="sxs-lookup"><span data-stu-id="c2610-142">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][DevtoolsCssIndex] was broken by page refreshes.</span></span>  <span data-ttu-id="c2610-143">刷新页面时，**"属性" 选项卡** 未填充当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="c2610-143">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="在 Microsoft Edge 81 及更早版本中，页面刷新后，"属性" 选项卡为空白" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="c2610-145">图 6：在 Microsoft Edge 81 及更早版本中，在页面刷新后，**"属性" 选项卡** 是空白的</span><span class="sxs-lookup"><span data-stu-id="c2610-145">Figure 6:  In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-146">在 Microsoft Edge 83 中，你现在可以在 **"属性" 选项卡**中页面刷新后看到当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="c2610-146">In Microsoft Edge 83, you are now able to see the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="在 Microsoft Edge 83 中，"属性" 选项卡显示页面刷新后当前所选元素的属性" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="c2610-148">图 7：在 Microsoft Edge 83 中，**"属性" 选项卡** 显示页面刷新后当前所选元素的属性</span><span class="sxs-lookup"><span data-stu-id="c2610-148">Figure 7:  In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-149">Chromium 问题 [#1050999][CR1050999]</span><span class="sxs-lookup"><span data-stu-id="c2610-149">Chromium issue [#1050999][CR1050999]</span></span>  

### <span data-ttu-id="c2610-150">使用箭头键在 "更改" 工具中滚动</span><span class="sxs-lookup"><span data-stu-id="c2610-150">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="c2610-151">**"更改" 工具** 跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="c2610-151">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="c2610-152">你可使用 **"更改" 工具** 快速查看所有更改，并将其放回编辑器/IDE。</span><span class="sxs-lookup"><span data-stu-id="c2610-152">You are able to use the **Changes tool** to quickly see all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="c2610-153">按 DevTools 中的 "`Ctrl`+`Shift`+`P`"，打开 **"更改"工具**，以打开 "[命令菜单][DevToolsCommandMenuIndex]" 并键入 `changes`。</span><span class="sxs-lookup"><span data-stu-id="c2610-153">Open the **Changes tool** by pressing `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevToolsCommandMenuIndex] and typing `changes`.</span></span>  <span data-ttu-id="c2610-154">选择并运行 "**显示更改**" 命令以在 DevTools 抽屉中打开 **"更改" 工具**。</span><span class="sxs-lookup"><span data-stu-id="c2610-154">Select and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="c2610-155">对缩小文件进行更改后，**"更改" 工具** 可用于水平滚动以查看所有缩小代码。</span><span class="sxs-lookup"><span data-stu-id="c2610-155">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to see all of your minified code.</span></span>  <span data-ttu-id="c2610-156">从 Microsoft Edge 83 开始，你现在可以使用键盘上的箭头键水平滚动。</span><span class="sxs-lookup"><span data-stu-id="c2610-156">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="在 Microsoft Edge 83 中，你可以使用箭头键水平滚动，在 "更改" 工具中查看你的缩小代码" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="c2610-158">图 8：在 Microsoft Edge 83 中，可使用箭头键水平滚动，查看 **"更改" 工具**中对缩小代码所做的更改</span><span class="sxs-lookup"><span data-stu-id="c2610-158">Figure 8:  In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-159">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [tweett 发送][PostTweetEdgeDevTools] 或单击"发送反馈"图标来向我们 [发送你的反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="c2610-159">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c2610-160">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="c2610-160">Chromium issue [#963183][CR963183]</span></span>  

## <span data-ttu-id="c2610-161">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="c2610-161">Announcements from the Chromium project</span></span>  

<span data-ttu-id="c2610-162">以下各部分公布了 Microsoft Edge 83 中提供的其他功能，这些功能是对开源 Chromium 项目的贡献。</span><span class="sxs-lookup"><span data-stu-id="c2610-162">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="c2610-163">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="c2610-163">Emulate vision deficiencies</span></span>  

<span data-ttu-id="c2610-164">打开["渲染" 选项卡][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ，使用新的"**模拟视觉缺陷**" 功能，更好地了解有不同类型视觉缺陷的人们如何体验你的网站。</span><span class="sxs-lookup"><span data-stu-id="c2610-164">Open the [Rendering tab][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="模拟模糊的视觉效果" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="c2610-166">图 9：模拟模糊的视觉效果</span><span class="sxs-lookup"><span data-stu-id="c2610-166">Figure 9:  Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-167">DevTools 能够模拟模糊的视觉和以下[颜色视觉缺陷类型][ColorBlindnessTypes]。</span><span class="sxs-lookup"><span data-stu-id="c2610-167">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="c2610-168">颜色视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="c2610-168">Color Vision Deficiency</span></span> | <span data-ttu-id="c2610-169">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2610-169">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="c2610-170">红色盲</span><span class="sxs-lookup"><span data-stu-id="c2610-170">Protanopia</span></span> | <span data-ttu-id="c2610-171">无法感觉任何红色的光线。</span><span class="sxs-lookup"><span data-stu-id="c2610-171">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="c2610-172">绿色盲</span><span class="sxs-lookup"><span data-stu-id="c2610-172">Deuteranopia</span></span> | <span data-ttu-id="c2610-173">无法感觉任何绿色的光线。</span><span class="sxs-lookup"><span data-stu-id="c2610-173">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="c2610-174">黄蓝色盲</span><span class="sxs-lookup"><span data-stu-id="c2610-174">Tritanopia</span></span> | <span data-ttu-id="c2610-175">无法感觉任何蓝色的光线。</span><span class="sxs-lookup"><span data-stu-id="c2610-175">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="c2610-176">全色盲</span><span class="sxs-lookup"><span data-stu-id="c2610-176">Achromatopsia</span></span> | <span data-ttu-id="c2610-177">无法感觉任何颜色，灰色阴影除外\（极少\）。</span><span class="sxs-lookup"><span data-stu-id="c2610-177">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="c2610-178">存在这些色觉缺陷的不太极端的版本，实际上它们更为常见。</span><span class="sxs-lookup"><span data-stu-id="c2610-178">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="c2610-179">例如，红色弱降低了对红光的敏感性（与红色盲相对，后者完全无法感知红光）。</span><span class="sxs-lookup"><span data-stu-id="c2610-179">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="c2610-180">但是，这些异常视力缺陷的定义不是很明确：每个视力缺陷者都不同，并且可能看到的事物都不相同（能够感知更多/更少的相关颜色）。</span><span class="sxs-lookup"><span data-stu-id="c2610-180">However, these -omaly vision deficiencies are not as clearly defined: every person with such a vision deficiency is different and might see things differently (being able to perceive more/less of the relevant colors).</span></span>  

<span data-ttu-id="c2610-181">通过在 DevTools 中进行更极端的仿真设计，可以保证红色弱、绿色弱、黄蓝色弱和全色弱的人也可访问你的 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="c2610-181">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="c2610-182">通过对"发送 [反馈"或单击"发送][PostTweetEdgeDevTools] 反馈"图标 [发送反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="c2610-182">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c2610-183">Chromium 问题 [#1003700][CR1003700]</span><span class="sxs-lookup"><span data-stu-id="c2610-183">Chromium issue [#1003700][CR1003700]</span></span>  

### <span data-ttu-id="c2610-184">模拟语言环境</span><span class="sxs-lookup"><span data-stu-id="c2610-184">Emulate locales</span></span>  

<span data-ttu-id="c2610-185">通过在**传感器**  >  **位置**中设置位置来模拟语言环境。</span><span class="sxs-lookup"><span data-stu-id="c2610-185">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="c2610-186">[打开**命令菜单** ][DevToolsCommandMenuIndex]，然后键入`Sensors`以访问**传感器**选项卡。执行完这些操作后，DevTools 会修改当前的默认语言环境，从而影响以下代码。</span><span class="sxs-lookup"><span data-stu-id="c2610-186">[Open the **Command Menu**][DevToolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="c2610-187">例如，API：</span><span class="sxs-lookup"><span data-stu-id="c2610-187">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="c2610-188">其他可识别语言环境的 JavaScript API，例如`String.prototype.localeCompare`和`*.prototype.toLocaleString`，例如：</span><span class="sxs-lookup"><span data-stu-id="c2610-188">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="c2610-189">DOM API，如 `navigator.language` 和</span><span class="sxs-lookup"><span data-stu-id="c2610-189">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="c2610-190">[`Accept-Language`][MDNAcceptLanguage] HTTP 请求标头</span><span class="sxs-lookup"><span data-stu-id="c2610-190">The [`Accept-Language`][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="c2610-191">对`navigator.language`和`navigator.languages`的更新不是立即可见的，只有在下一次导航或页面刷新后才可见。</span><span class="sxs-lookup"><span data-stu-id="c2610-191">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span></span>  <span data-ttu-id="c2610-192">只有后续请求才会反映对 `Accept-Language` HTTP 标头的更改。</span><span class="sxs-lookup"><span data-stu-id="c2610-192">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="模拟区域设置" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="c2610-194">图 10：模拟区域设置</span><span class="sxs-lookup"><span data-stu-id="c2610-194">Figure 10:  Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-195">若要尝试演示，请参阅[与区域设置相关的代码示例][MathiasByensLocaleDemo]。</span><span class="sxs-lookup"><span data-stu-id="c2610-195">To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="c2610-196">Chromium 问题 [#1051822][CR1051822]</span><span class="sxs-lookup"><span data-stu-id="c2610-196">Chromium issue [#1051822][CR1051822]</span></span>

### <span data-ttu-id="c2610-197">跨域嵌入程序策略 (COEP) 调试</span><span class="sxs-lookup"><span data-stu-id="c2610-197">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="c2610-198">"网络" 面板现在提供[跨域嵌入程序策略 (COEP)][COEP] 调试信息。</span><span class="sxs-lookup"><span data-stu-id="c2610-198">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="c2610-199">“**状态**”列现在提供有关为何阻止请求的快速说明，以及查看该请求标头以进行进一步调试的链接：</span><span class="sxs-lookup"><span data-stu-id="c2610-199">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**状态**列中的阻止请求" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="c2610-201">图 11：状态列中的已阻止请求</span><span class="sxs-lookup"><span data-stu-id="c2610-201">Figure 11:  Blocked requests in the Status column</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-202">"**标头**" 选项卡上的 "**响应标头**" 部分提供了有关如何解决这些问题的更多指导：</span><span class="sxs-lookup"><span data-stu-id="c2610-202">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="“响应标头”部分中的更多指南" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="c2610-204">图 12：“响应标头”部分中的更多指南</span><span class="sxs-lookup"><span data-stu-id="c2610-204">Figure 12:  More guidance in the Response Headers section</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-205">通过作出 [窗口或单击"发送反馈][PostTweetEdgeDevTools] "图标 [发送反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="c2610-205">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c2610-206">Chromium 问题 [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="c2610-206">Chromium issue [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="c2610-207">断点、条件断点和日志点的新图标</span><span class="sxs-lookup"><span data-stu-id="c2610-207">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="c2610-208">"源"面板具有分组、条件断点和逻辑的新图标：</span><span class="sxs-lookup"><span data-stu-id="c2610-208">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span></span>  

*   <span data-ttu-id="c2610-209">断点 \ (</span><span class="sxs-lookup"><span data-stu-id="c2610-209">Breakpoints \(</span></span>![断点](../../media/2020/03/breakpoint.msft.png)<span data-ttu-id="c2610-211">\) 表示以重复的数据点加。</span><span class="sxs-lookup"><span data-stu-id="c2610-211">\) are represented by red circles.</span></span>  
*   <span data-ttu-id="c2610-212">条件断点 \ (</span><span class="sxs-lookup"><span data-stu-id="c2610-212">Conditional Breakpoints \(</span></span>![条件断点](../../media/2020/03/conditional.msft.png)<span data-ttu-id="c2610-214">\) 表示是由单个 red falf-white crcles 表示的。</span><span class="sxs-lookup"><span data-stu-id="c2610-214">\) are represented by half-red half-white circles.</span></span>  
*   <span data-ttu-id="c2610-215">日志点 \ (</span><span class="sxs-lookup"><span data-stu-id="c2610-215">Logpoints \(</span></span>![徽标](../../media/2020/03/logpoint.msft.png)<span data-ttu-id="c2610-217">\) 表示带有主机图标的复选数据点。</span><span class="sxs-lookup"><span data-stu-id="c2610-217">\) are represented by red circles with Console icons.</span></span>  

<span data-ttu-id="c2610-218">新图标的激活是让 UI 更与其他 GUI 调试工具更加一一体， (这通常是色彩中断点 red\) ，这使得自定义得以一目了然地区分 3 个功能。</span><span class="sxs-lookup"><span data-stu-id="c2610-218">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span></span>  

<span data-ttu-id="c2610-219">Chromium [问题#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="c2610-219">Chromium issue [#1041830][CR1041830]</span></span>  

### <span data-ttu-id="c2610-220">查看设置了特定 cookie 路径的网络请求</span><span class="sxs-lookup"><span data-stu-id="c2610-220">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="c2610-221">在**网络**面板中使用新的`cookie-path`过滤关键字来关注设置了特定[ cookie 路径][MDNCookiePath]的网络请求。</span><span class="sxs-lookup"><span data-stu-id="c2610-221">Use the new `cookie-path` filter keyword in the **Network** panel to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="c2610-222">查看[按属性过滤请求][DevtoolsNetworkReferenceFilterRequestsProperties]以发现更多关键词，例如`cookie-path`。</span><span class="sxs-lookup"><span data-stu-id="c2610-222">Check out [Filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties] to discover more keywords like `cookie-path`.</span></span>

### <span data-ttu-id="c2610-223">从 "命令" 菜单向左停靠</span><span class="sxs-lookup"><span data-stu-id="c2610-223">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="c2610-224">打开 ["命令菜单"][DevToolsCommandMenuIndex]，并运行" `Dock to left` "命令以将 DevTools 移到视线的左侧。</span><span class="sxs-lookup"><span data-stu-id="c2610-224">Open the [Command Menu][DevToolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="DevTools 停靠在视线左侧" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="c2610-226">图 13：停靠在视线左侧的 DevTools</span><span class="sxs-lookup"><span data-stu-id="c2610-226">Figure 13:  DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c2610-227">自 Microsoft Edge 75 以来，**停靠到左侧**功能已可用，但以前只能从[**主菜单**][DevtoolsCustomizePlacementsChangeMainMenu]中进行访问。</span><span class="sxs-lookup"><span data-stu-id="c2610-227">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [**Main Menu**][DevtoolsCustomizePlacementsChangeMainMenu].</span></span>  <span data-ttu-id="c2610-228">Microsoft Edge 83 中的新功能是，你现在可以从 "命令" 菜单中访问此功能。</span><span class="sxs-lookup"><span data-stu-id="c2610-228">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="c2610-229">通过作出 [窗口或单击"发送反馈][PostTweetEdgeDevTools] "图标 [发送反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="c2610-229">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c2610-230">Chromium 问题 [#1011679][CR1011679]</span><span class="sxs-lookup"><span data-stu-id="c2610-230">Chromium issue [#1011679][CR1011679]</span></span>  

### <span data-ttu-id="c2610-231">"审核" 面板现在是 "灯塔" 面板</span><span class="sxs-lookup"><span data-stu-id="c2610-231">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="c2610-232">DevTools 团队经常从 Web 开发人员那里获得反馈，尽管可以从 DevTools 运行[灯塔][GithubGoogleChromeLighthouse]，但在尝试运行时却找不到“灯塔”面板，因此**审核**面板现在是**灯塔**面板。</span><span class="sxs-lookup"><span data-stu-id="c2610-232">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="灯塔面板" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="c2610-234">图 14："灯塔" 面板</span><span class="sxs-lookup"><span data-stu-id="c2610-234">Figure 14:  The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c2610-235">**灯塔** 面板提供了指向第三方网站上托管内容的链接。</span><span class="sxs-lookup"><span data-stu-id="c2610-235">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="c2610-236">Microsoft 对这些网站及其可能收集的任何数据的内容不承担任何责任。</span><span class="sxs-lookup"><span data-stu-id="c2610-236">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <span data-ttu-id="c2610-237">删除文件夹中的所有本地覆盖</span><span class="sxs-lookup"><span data-stu-id="c2610-237">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="c2610-238">设置**本地覆盖**后可右键单击文件夹，然后选择新的 "**删除所有覆盖**" 选项以删除该文件夹中的所有本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="c2610-238">After setting up **Local Overrides** you may right-click a folder and select the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="删除所有覆盖" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="c2610-240">图 15：删除所有覆盖</span><span class="sxs-lookup"><span data-stu-id="c2610-240">Figure 15:  Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-241">通过作出 [窗口或单击"发送反馈][PostTweetEdgeDevTools] "图标 [发送反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="c2610-241">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c2610-242">Chromium 问题 [#1016501][CR1016501]</span><span class="sxs-lookup"><span data-stu-id="c2610-242">Chromium issue [#1016501][CR1016501]</span></span>  

### <span data-ttu-id="c2610-243">更新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="c2610-243">Updated Long tasks UI</span></span>  

<span data-ttu-id="c2610-244">**长任务**是长时间垄断了主线程，从而导致网页冻结的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="c2610-244">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="c2610-245">你已经能够[在“性能”面板中可视化长任务][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]了一段时间，但是在Microsoft Edge 83中，“性能”面板中的长任务可视化 UI 已更新。</span><span class="sxs-lookup"><span data-stu-id="c2610-245">You have been able to [visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="c2610-246">现在，任务的长任务部分的颜色为带条纹红色背景。</span><span class="sxs-lookup"><span data-stu-id="c2610-246">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新的长任务 UI" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="c2610-248">图 16：新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="c2610-248">Figure 16:  The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="c2610-249">通过作出 [窗口或单击"发送反馈][PostTweetEdgeDevTools] "图标 [发送反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="c2610-249">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c2610-250">Chromium 问题 [#1054447][CR1054447]</span><span class="sxs-lookup"><span data-stu-id="c2610-250">Chromium issue [#1054447][CR1054447]</span></span>  

### <span data-ttu-id="c2610-251">"清单" 窗格中的可屏蔽图标支持</span><span class="sxs-lookup"><span data-stu-id="c2610-251">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="c2610-252">Android Oreo 引入了自适应图标，可在不同的设备模型之间显示各种形状中的应用图标。</span><span class="sxs-lookup"><span data-stu-id="c2610-252">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="c2610-253">**可屏蔽图标**是支持自适应图标的新图标格式，使你可以确保[ PWA ][PprgressiveWebAppsChromiumIndex]图标在支持可屏蔽图标标准的设备上看起来不错。</span><span class="sxs-lookup"><span data-stu-id="c2610-253">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][PprgressiveWebAppsChromiumIndex] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="c2610-254">在**清单**窗格中启用新的**仅显示可屏蔽图标的最小安全区域**复选框，以检查可屏蔽图标在 Android Oreo 设备上看起来是否良好。</span><span class="sxs-lookup"><span data-stu-id="c2610-254">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text=""仅显示可屏蔽图标的最小安全区域" 复选框" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="c2610-256">图 17：**仅显示可屏蔽图标的最低安全区域**复选框</span><span class="sxs-lookup"><span data-stu-id="c2610-256">Figure 17:  The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c2610-257">此功能在 Microsoft Edge 81 中发布。</span><span class="sxs-lookup"><span data-stu-id="c2610-257">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="c2610-258">["DevTools （Microsoft Edge 81）"][WhatsNew81]中的新增功能未涵盖 Microsoft Edge 83 中介绍的更新。</span><span class="sxs-lookup"><span data-stu-id="c2610-258">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <span data-ttu-id="c2610-259">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="c2610-259">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="c2610-260">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="c2610-260">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="c2610-261">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="c2610-261">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="c2610-262">使用 Microsoft Edge DevTools 团队和联系</span><span class="sxs-lookup"><span data-stu-id="c2610-262">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/边缘-开发人员 - GitHub"  
[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  
[TheWebWeWant]: https://webwewant.fyi "我们想要的网络"  

[WhatsNew81]: ../01/devtools.md "Microsoft Edge 81 开发人员 (版本中的新增功能) |Microsoft 文档"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "使用 Microsoft Edge DevTools 命令菜单 |Microsoft 文档"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "使用"颜色选取器"更改颜色 |Microsoft 文档"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门 |Microsoft 文档"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "从主菜单更改位置 |Microsoft 文档"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "查看主线程活动 |Microsoft 文档"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用"呈现"选项卡分析呈现性能 |Microsoft 文档"  
[PprgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的进度 Web 应用 |Microsoft 文档"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备 | 入门 |Microsoft 文档"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "代码行会 - 如何在 Microsoft Edge DevTools 中暂停代码和断点 |Microsoft 文档"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "按属性筛选请求 - 网络分析引用 |Microsoft 文档"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge 开发工具 |Microsoft 文档"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows 设备门户概述"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 适用的远程工具 (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "在适用于 Microsoft Edge 的稳定频道版本上更新"

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio代码"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色盲类型"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "接受语言"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "依赖于区域设置的代码示例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

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
[ COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2  "COOP 和 COEP 详解——跨域嵌入程序策略" 
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "COOP and COEP explained - Cross-Origin Embedder Policy"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "灯塔 GitHub 存储库"  

> [!NOTE]
> <span data-ttu-id="c2610-303">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c2610-303">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c2610-304">原始页面位于[此处](https://developers.google.com/web/updates/2020/03/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="c2610-304">The original page is found [here](https://developers.google.com/web/updates/2020/03/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="c2610-306">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c2610-306">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
