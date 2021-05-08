---
description: 模拟命令菜单中的颜色视觉缺陷、停靠到左侧等。
title: DevTools （Microsoft Edge 83）中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: c329dfba980b882b6e538447e52902e4d0cc985b
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514415"
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
# <a name="whats-new-in-devtools-microsoft-edge-83"></a><span data-ttu-id="c0333-104">DevTools （Microsoft Edge 83）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="c0333-104">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="c0333-105">按照更新的 Chromium 计划，我们将调整即将推出的 Microsoft Edge 版本的计划，并取消 Microsoft Edge 82 版本。</span><span class="sxs-lookup"><span data-stu-id="c0333-105">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="c0333-106">有关详细信息，请查看我们的 [博客文章][WindowsBlogStableRelease]。</span><span class="sxs-lookup"><span data-stu-id="c0333-106">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="c0333-107">下面是 Microsoft Edge 83 的 DevTools 中提供的新功能。</span><span class="sxs-lookup"><span data-stu-id="c0333-107">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c0333-108">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="c0333-108">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="c0333-109">以下各节列出了你可能从 DevTools 团队中错过Microsoft Edge通知。</span><span class="sxs-lookup"><span data-stu-id="c0333-109">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="c0333-110">请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="c0333-110">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="c0333-111">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="c0333-111">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="remotely-debug-microsoft-edge-on-windows-10-devices"></a><span data-ttu-id="c0333-112">在 Windows 10 设备上远程调试 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c0333-112">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="c0333-113">现在，[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 \(Beta\)][RemoteTools] 应用。</span><span class="sxs-lookup"><span data-stu-id="c0333-113">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="c0333-114">使用此扩展 Windows Device [Portal][WindowsUwpDebugTestPerfDevicePortal]的应用，你可以从开发计算机上运行的 Microsoft Edge 实例连接到远程 Windows 10 设备，显示目标列表 \ (Microsoft Edge 中所有选项卡，PBA 在 Windows 10 设备上打开\) ，并针对在远程[][ProgressiveWebAppsChromiumIndex]Windows 10 设备上运行的目标使用开发计算机上 DevTools。</span><span class="sxs-lookup"><span data-stu-id="c0333-114">Using this app, which extends the [Windows Device Portal][WindowsUwpDebugTestPerfDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, display a list of targets \(all tabs in Microsoft Edge and [PWAs][ProgressiveWebAppsChromiumIndex] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="现在，Microsoft Store 中提供 Microsoft Edge 远程工具 (Beta) 应用" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="c0333-116">[Microsoft Store][MicrosoftStore] 中提供 [Microsoft Edge 远程工具 (Beta)][RemoteTools] 应用</span><span class="sxs-lookup"><span data-stu-id="c0333-116">The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-117">[阅读我们的指南以设置 Windows 10 设备和开发计算机进行远程调试][DevtoolsRemoteDebuggingWindows]。</span><span class="sxs-lookup"><span data-stu-id="c0333-117">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][DevtoolsRemoteDebuggingWindows].</span></span>  <span data-ttu-id="c0333-118">通过推文或选择发送反馈图标，告诉我们[][PostTweetEdgeDevTools]你的远程[调试](#getting-in-touch-with-microsoft-edge-devtools-team)体验！</span><span class="sxs-lookup"><span data-stu-id="c0333-118">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

### <a name="new-ways-to-access-settings"></a><span data-ttu-id="c0333-119">访问设置的新方法</span><span class="sxs-lookup"><span data-stu-id="c0333-119">New ways to access Settings</span></span>  

<span data-ttu-id="c0333-120">你可以自定义大量的 DevTools 设置，以使 DevTools 外观、感觉和工作方式达到你的要求。</span><span class="sxs-lookup"><span data-stu-id="c0333-120">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="c0333-121">在 Microsoft Edge 83 中，访问 DevTools 中的 [设置][DevtoolsCustomizeIndexSettings] 现在更为简单。</span><span class="sxs-lookup"><span data-stu-id="c0333-121">In Microsoft Edge 83, accessing [Settings][DevtoolsCustomizeIndexSettings] in the DevTools is now much easier.</span></span>  <span data-ttu-id="c0333-122">使用 "控制台警报" 和 "主菜单" 旁边的齿轮图标打开 "设置"。</span><span class="sxs-lookup"><span data-stu-id="c0333-122">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="齿轮图标会打开 DevTools 中的设置" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="c0333-124">齿轮图标将 **打开** DevTools 中的"设置"</span><span class="sxs-lookup"><span data-stu-id="c0333-124">The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-125">你还可以从**主菜单**下的"**更多工具**"下打开[设置][DevtoolsCustomizeIndexSettings]。</span><span class="sxs-lookup"><span data-stu-id="c0333-125">You are also able to open [Settings][DevtoolsCustomizeIndexSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="主菜单 > 更多工具 > 设置" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="c0333-127">**主菜单**  > **更多工具**  > **设置**</span><span class="sxs-lookup"><span data-stu-id="c0333-127">**Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-128">Chromium 问题 [#1050855][CR1050855]</span><span class="sxs-lookup"><span data-stu-id="c0333-128">Chromium issue [#1050855][CR1050855]</span></span>

### <a name="new-and-improved-infobars"></a><span data-ttu-id="c0333-129">新增和改进的 infobars</span><span class="sxs-lookup"><span data-stu-id="c0333-129">New and improved infobars</span></span>

<span data-ttu-id="c0333-130">DevTools 中的信息性通知栏 \(infobars\) 现在具有改进的外观和功能。</span><span class="sxs-lookup"><span data-stu-id="c0333-130">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="c0333-131">在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="c0333-131">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="用于在 Microsoft Edge 83 中整齐打印缩小文件的信息栏" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="c0333-133">用于在 Microsoft Edge 版本 83 中打印缩小文件的信息栏</span><span class="sxs-lookup"><span data-stu-id="c0333-133">Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-134">Chromium 问题 [#1056348][CR1056348]</span><span class="sxs-lookup"><span data-stu-id="c0333-134">Chromium issue [#1056348][CR1056348]</span></span>

### <a name="navigate-the-color-picker-with-your-keyboard"></a><span data-ttu-id="c0333-135">使用键盘导航颜色选取器</span><span class="sxs-lookup"><span data-stu-id="c0333-135">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="c0333-136">[颜色选取器][DevtoolsCssReferenceColorPicker] 是 "[元素][DevtoolsCssIndex]" 面板中的 GUI 用于更改 `color` 和 `background-color` 声明。</span><span class="sxs-lookup"><span data-stu-id="c0333-136">The [Color Picker][DevtoolsCssReferenceColorPicker] is a GUI in the [Elements panel][DevtoolsCssIndex] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="c0333-137">在早期版本的 Microsoft Edge 中，无法使用键盘导航 [颜色选取器][DevtoolsCssReferenceColorPicker] 的 **阴影** 部分。</span><span class="sxs-lookup"><span data-stu-id="c0333-137">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="现在，你可以使用键盘在颜色选取器的 阴影 部分移动选取器" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="c0333-139">现在，你可以使用键盘在 [颜色选取器][DevtoolsCssReferenceColorPicker]的**阴影** 部分移动选取器</span><span class="sxs-lookup"><span data-stu-id="c0333-139">You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][DevtoolsCssReferenceColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-140">在 Microsoft Edge 83 中，你可以使用键盘在颜色选取器的**阴影** 部分移动选取器。</span><span class="sxs-lookup"><span data-stu-id="c0333-140">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="c0333-141">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="c0333-141">Chromium issue [#963183][CR963183]</span></span>  

### <a name="properties-tab-now-populates-after-a-page-refresh"></a><span data-ttu-id="c0333-142">现在，刷新页面后将填充“属性”选项卡</span><span class="sxs-lookup"><span data-stu-id="c0333-142">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="c0333-143">在 Microsoft Edge 81 及更早版本中，在 "[元素][DevtoolsCssIndex]" 面板中的 **"属性"选项卡**因页面刷新而损坏。</span><span class="sxs-lookup"><span data-stu-id="c0333-143">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][DevtoolsCssIndex] was broken by page refreshes.</span></span>  <span data-ttu-id="c0333-144">刷新页面时，**"属性" 选项卡** 未填充当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="c0333-144">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="在 Microsoft Edge 81 及更早版本中，页面刷新后，属性 选项卡为空白" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="c0333-146">在 Microsoft Edge 81 及更早版本中，在页面刷新后，**"属性" 选项卡** 是空白的</span><span class="sxs-lookup"><span data-stu-id="c0333-146">In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-147">在 Microsoft Edge 83 中，现在您可以在"属性"选项卡中刷新页面后显示当前**所选元素的属性**。</span><span class="sxs-lookup"><span data-stu-id="c0333-147">In Microsoft Edge 83, you are now able to display the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="在 Microsoft Edge 83 中，属性 选项卡显示页面刷新后当前所选元素的属性" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="c0333-149">在 Microsoft Edge 83 中，**"属性" 选项卡** 显示页面刷新后当前所选元素的属性</span><span class="sxs-lookup"><span data-stu-id="c0333-149">In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-150">Chromium 问题 [#1050999][CR1050999]</span><span class="sxs-lookup"><span data-stu-id="c0333-150">Chromium issue [#1050999][CR1050999]</span></span>  

### <a name="use-the-arrow-keys-to-scroll-in-the-changes-tool"></a><span data-ttu-id="c0333-151">使用箭头键在 "更改" 工具中滚动</span><span class="sxs-lookup"><span data-stu-id="c0333-151">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="c0333-152">**"更改" 工具** 跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="c0333-152">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="c0333-153">可以使用"更改"工具快速\*\*\*\* 显示所有更改，并返回编辑器/IDE。</span><span class="sxs-lookup"><span data-stu-id="c0333-153">You are able to use the **Changes tool** to quickly display all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="c0333-154">若要打开**更改工具，** 请在 `Ctrl` + `Shift` + `P` DevTools 中选择以打开命令[菜单][DevToolsCommandMenuIndex]并键入 `changes` 。</span><span class="sxs-lookup"><span data-stu-id="c0333-154">To open the **Changes tool**, select `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevToolsCommandMenuIndex] and type `changes`.</span></span>  <span data-ttu-id="c0333-155">选择并运行"**显示更改"** 命令以在\*\*\*\* DevTools 箱中打开"更改"工具。</span><span class="sxs-lookup"><span data-stu-id="c0333-155">choose and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="c0333-156">对缩小文件进行更改后，"更改"工具允许您水平滚动\*\*\*\* 以显示所有缩小代码。</span><span class="sxs-lookup"><span data-stu-id="c0333-156">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to display all of your minified code.</span></span>  <span data-ttu-id="c0333-157">从 Microsoft Edge 83 开始，你现在可以使用键盘上的箭头键水平滚动。</span><span class="sxs-lookup"><span data-stu-id="c0333-157">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="在 Microsoft Edge 83 中，可以使用箭头键水平滚动，以在"更改"工具中显示缩小代码" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="c0333-159">在 Microsoft Edge 83 中，可以使用箭头键水平滚动，以在"更改"工具中显示对缩小代码**所做的更改**</span><span class="sxs-lookup"><span data-stu-id="c0333-159">In Microsoft Edge 83, you may scroll horizontally with the arrow keys to display the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-160">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过向我们发推文或[][PostTweetEdgeDevTools]选择"发送反馈"图标向我们发送[反馈](#getting-in-touch-with-microsoft-edge-devtools-team)！</span><span class="sxs-lookup"><span data-stu-id="c0333-160">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0333-161">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="c0333-161">Chromium issue [#963183][CR963183]</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="c0333-162">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="c0333-162">Announcements from the Chromium project</span></span>  

<span data-ttu-id="c0333-163">以下各部分公布了 Microsoft Edge 83 中提供的其他功能，这些功能是对开源 Chromium 项目的贡献。</span><span class="sxs-lookup"><span data-stu-id="c0333-163">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <a name="emulate-vision-deficiencies"></a><span data-ttu-id="c0333-164">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="c0333-164">Emulate vision deficiencies</span></span>  

<span data-ttu-id="c0333-165">打开["渲染" 选项卡][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] ，使用新的"**模拟视觉缺陷**" 功能，更好地了解有不同类型视觉缺陷的人们如何体验你的网站。</span><span class="sxs-lookup"><span data-stu-id="c0333-165">Open the [Rendering tab][DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="模拟模糊的视觉效果" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="c0333-167">模拟模糊的视觉效果</span><span class="sxs-lookup"><span data-stu-id="c0333-167">Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-168">DevTools 能够模拟模糊的视觉和以下[颜色视觉缺陷类型][ColorBlindnessTypes]。</span><span class="sxs-lookup"><span data-stu-id="c0333-168">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="c0333-169">颜色视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="c0333-169">Color Vision Deficiency</span></span> | <span data-ttu-id="c0333-170">详细信息</span><span class="sxs-lookup"><span data-stu-id="c0333-170">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="c0333-171">红色盲</span><span class="sxs-lookup"><span data-stu-id="c0333-171">Protanopia</span></span> | <span data-ttu-id="c0333-172">无法感觉任何红色的光线。</span><span class="sxs-lookup"><span data-stu-id="c0333-172">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="c0333-173">绿色盲</span><span class="sxs-lookup"><span data-stu-id="c0333-173">Deuteranopia</span></span> | <span data-ttu-id="c0333-174">无法感觉任何绿色的光线。</span><span class="sxs-lookup"><span data-stu-id="c0333-174">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="c0333-175">黄蓝色盲</span><span class="sxs-lookup"><span data-stu-id="c0333-175">Tritanopia</span></span> | <span data-ttu-id="c0333-176">无法感觉任何蓝色的光线。</span><span class="sxs-lookup"><span data-stu-id="c0333-176">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="c0333-177">全色盲</span><span class="sxs-lookup"><span data-stu-id="c0333-177">Achromatopsia</span></span> | <span data-ttu-id="c0333-178">无法感觉任何颜色，灰色阴影除外\（极少\）。</span><span class="sxs-lookup"><span data-stu-id="c0333-178">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="c0333-179">存在这些色觉缺陷的不太极端的版本，实际上它们更为常见。</span><span class="sxs-lookup"><span data-stu-id="c0333-179">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="c0333-180">例如，红色弱降低了对红光的敏感性（与红色盲相对，后者完全无法感知红光）。</span><span class="sxs-lookup"><span data-stu-id="c0333-180">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="c0333-181">但是，这些 **-omaly** 视觉缺陷没有明确定义：每个有这种视觉缺陷的人是不同的，并且可能会看到不同的 \ (能够感知更多/更少的相关颜色\) 。</span><span class="sxs-lookup"><span data-stu-id="c0333-181">However, these **-omaly** vision deficiencies are not as clearly defined:  every person with such a vision deficiency is different and may see things differently \(being able to perceive more/less of the relevant colors\).</span></span>  

<span data-ttu-id="c0333-182">通过在 DevTools 中进行更极端的仿真设计，可以保证红色弱、绿色弱、黄蓝色弱和全色弱的人也可访问你的 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="c0333-182">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="c0333-183">通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！</span><span class="sxs-lookup"><span data-stu-id="c0333-183">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0333-184">Chromium 问题 [#1003700][CR1003700]</span><span class="sxs-lookup"><span data-stu-id="c0333-184">Chromium issue [#1003700][CR1003700]</span></span>  

### <a name="emulate-locales"></a><span data-ttu-id="c0333-185">模拟语言环境</span><span class="sxs-lookup"><span data-stu-id="c0333-185">Emulate locales</span></span>  

<span data-ttu-id="c0333-186">通过在**传感器**  >  **位置**中设置位置来模拟语言环境。</span><span class="sxs-lookup"><span data-stu-id="c0333-186">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="c0333-187">[打开**命令菜单** ][DevToolsCommandMenuIndex]，然后键入`Sensors`以访问**传感器**选项卡。执行完这些操作后，DevTools 会修改当前的默认语言环境，从而影响以下代码。</span><span class="sxs-lookup"><span data-stu-id="c0333-187">[Open the **Command Menu**][DevToolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="c0333-188">例如，API：</span><span class="sxs-lookup"><span data-stu-id="c0333-188">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="c0333-189">其他可识别语言环境的 JavaScript API，例如`String.prototype.localeCompare`和`*.prototype.toLocaleString`，例如：</span><span class="sxs-lookup"><span data-stu-id="c0333-189">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="c0333-190">DOM API，如 `navigator.language` 和</span><span class="sxs-lookup"><span data-stu-id="c0333-190">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="c0333-191">[接受语言][MDNAcceptLanguage]HTTP 请求标头</span><span class="sxs-lookup"><span data-stu-id="c0333-191">The [Accept-Language][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="c0333-192">对`navigator.language`和`navigator.languages`的更新不是立即可见的，只有在下一次导航或页面刷新后才可见。</span><span class="sxs-lookup"><span data-stu-id="c0333-192">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page refresh.</span></span>  <span data-ttu-id="c0333-193">只有后续请求才会反映对 `Accept-Language` HTTP 标头的更改。</span><span class="sxs-lookup"><span data-stu-id="c0333-193">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="模拟区域设置" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="c0333-195">模拟区域设置</span><span class="sxs-lookup"><span data-stu-id="c0333-195">Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-196">若要尝试演示，请导航到与 [区域设置相关的代码示例][MathiasByensLocaleDemo]。</span><span class="sxs-lookup"><span data-stu-id="c0333-196">To try a demo, navigate to [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="c0333-197">Chromium 问题 [#1051822][CR1051822]</span><span class="sxs-lookup"><span data-stu-id="c0333-197">Chromium issue [#1051822][CR1051822]</span></span>

### <a name="cross-origin-embedder-policy-coep-debugging"></a><span data-ttu-id="c0333-198">跨域嵌入程序策略 (COEP) 调试</span><span class="sxs-lookup"><span data-stu-id="c0333-198">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="c0333-199">"网络" 面板现在提供[跨域嵌入程序策略 (COEP)][COEP] 调试信息。</span><span class="sxs-lookup"><span data-stu-id="c0333-199">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="c0333-200">“**状态**”列现在提供有关为何阻止请求的快速说明，以及查看该请求标头以进行进一步调试的链接：</span><span class="sxs-lookup"><span data-stu-id="c0333-200">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="**状态**列中的阻止请求" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="c0333-202">"状态"**列中阻止的请求**</span><span class="sxs-lookup"><span data-stu-id="c0333-202">Blocked requests in the **Status** column</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-203">"**标头**" 选项卡上的 "**响应标头**" 部分提供了有关如何解决这些问题的更多指导：</span><span class="sxs-lookup"><span data-stu-id="c0333-203">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text="“响应标头”部分中的更多指南" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="c0333-205">"响应头" **部分中的更多** 指南</span><span class="sxs-lookup"><span data-stu-id="c0333-205">More guidance in the **Response Headers** section</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-206">通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！</span><span class="sxs-lookup"><span data-stu-id="c0333-206">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0333-207">Chromium 问题 [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="c0333-207">Chromium issue [#1051466][CR1051466]</span></span>  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a><span data-ttu-id="c0333-208">断点、条件断点和登录点的新图标</span><span class="sxs-lookup"><span data-stu-id="c0333-208">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="c0333-209">"源"面板具有用于断点、条件断点和日志点的新图标：</span><span class="sxs-lookup"><span data-stu-id="c0333-209">The Sources panel has new icons for breakpoints, conditional breakpoints, and logpoints:</span></span>  

*   <span data-ttu-id="c0333-210">断点 \(</span><span class="sxs-lookup"><span data-stu-id="c0333-210">Breakpoints \(</span></span>![断点](../../media/2020/03/breakpoint.msft.png)<span data-ttu-id="c0333-212">\) 用红色圆圈表示。</span><span class="sxs-lookup"><span data-stu-id="c0333-212">\) are represented by red circles.</span></span>  
*   <span data-ttu-id="c0333-213">条件断点 \(</span><span class="sxs-lookup"><span data-stu-id="c0333-213">Conditional Breakpoints \(</span></span>![条件断点](../../media/2020/03/conditional.msft.png)<span data-ttu-id="c0333-215">\) 用半红半白圆表示。</span><span class="sxs-lookup"><span data-stu-id="c0333-215">\) are represented by half-red half-white circles.</span></span>  
*   <span data-ttu-id="c0333-216">Logpoints \(</span><span class="sxs-lookup"><span data-stu-id="c0333-216">Logpoints \(</span></span>![Logpoint](../../media/2020/03/logpoint.msft.png)<span data-ttu-id="c0333-218">\) 用带控制台图标的红色圆圈表示。</span><span class="sxs-lookup"><span data-stu-id="c0333-218">\) are represented by red circles with Console icons.</span></span>  

<span data-ttu-id="c0333-219">新图标的动机是使 UI 与其他 GUI 调试工具 \(（通常为红色) 颜色断点\）更加一致，并便于一目了然地区分这 3 个功能。</span><span class="sxs-lookup"><span data-stu-id="c0333-219">The motivation for the new icons was to make the UI more consistent with other GUI debugging tools \(which usually color breakpoints red\) and to make it easier to distinguish between the 3 features at a glance.</span></span>  

<span data-ttu-id="c0333-220">Chromium 问题 [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="c0333-220">Chromium issue [#1041830][CR1041830]</span></span>  

### <a name="view-network-requests-that-set-a-specific-cookie-path"></a><span data-ttu-id="c0333-221">查看设置了特定 cookie 路径的网络请求</span><span class="sxs-lookup"><span data-stu-id="c0333-221">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="c0333-222">使用网络工具中的新筛选器关键字可以专注于设置特定 Cookie `cookie-path` 路径的网络[请求][MDNCookiePath]。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c0333-222">Use the new `cookie-path` filter keyword in the **Network** tool to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="c0333-223">查看[按属性过滤请求][DevtoolsNetworkReferenceFilterRequestsProperties]以发现更多关键词，例如`cookie-path`。</span><span class="sxs-lookup"><span data-stu-id="c0333-223">Check out [Filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties] to discover more keywords like `cookie-path`.</span></span>

### <a name="dock-to-left-from-the-command-menu"></a><span data-ttu-id="c0333-224">从 "命令" 菜单向左停靠</span><span class="sxs-lookup"><span data-stu-id="c0333-224">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="c0333-225">打开 ["命令菜单"][DevToolsCommandMenuIndex]，并运行" `Dock to left` "命令以将 DevTools 移到视线的左侧。</span><span class="sxs-lookup"><span data-stu-id="c0333-225">Open the [Command Menu][DevToolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="DevTools 停靠在视线左侧" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="c0333-227">DevTools 停靠在视线左侧</span><span class="sxs-lookup"><span data-stu-id="c0333-227">DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c0333-228">自 Microsoft Edge 75 以来，**停靠到左侧**功能已可用，但以前只能从[主菜单][DevtoolsCustomizePlacementsChangeMainMenu]中进行访问。</span><span class="sxs-lookup"><span data-stu-id="c0333-228">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [Main Menu][DevtoolsCustomizePlacementsChangeMainMenu].</span></span>  <span data-ttu-id="c0333-229">Microsoft Edge 83 中的新功能是，你现在可以从 "命令" 菜单中访问此功能。</span><span class="sxs-lookup"><span data-stu-id="c0333-229">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="c0333-230">通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！</span><span class="sxs-lookup"><span data-stu-id="c0333-230">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0333-231">Chromium 问题 [#1011679][CR1011679]</span><span class="sxs-lookup"><span data-stu-id="c0333-231">Chromium issue [#1011679][CR1011679]</span></span>  

### <a name="the-audits-panel-is-now-the-lighthouse-panel"></a><span data-ttu-id="c0333-232">"审核" 面板现在是 "灯塔" 面板</span><span class="sxs-lookup"><span data-stu-id="c0333-232">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="c0333-233">DevTools 团队经常从 Web 开发人员那里获得反馈，尽管可以从 DevTools 运行[灯塔][GithubGoogleChromeLighthouse]，但在尝试运行时却找不到“灯塔”面板，因此**审核**面板现在是**灯塔**面板。</span><span class="sxs-lookup"><span data-stu-id="c0333-233">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="灯塔面板" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="c0333-235">灯塔面板</span><span class="sxs-lookup"><span data-stu-id="c0333-235">The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c0333-236">**灯塔** 面板提供了指向第三方网站上托管内容的链接。</span><span class="sxs-lookup"><span data-stu-id="c0333-236">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="c0333-237">Microsoft 对这些网站及其可能收集的任何数据的内容不承担任何责任。</span><span class="sxs-lookup"><span data-stu-id="c0333-237">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <a name="delete-all-local-overrides-in-a-folder"></a><span data-ttu-id="c0333-238">删除文件夹中的所有本地覆盖</span><span class="sxs-lookup"><span data-stu-id="c0333-238">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="c0333-239">设置本地覆盖\*\*\*\* 后，你可以将鼠标悬停在目录上，打开上下文菜单 \ (右键单击\) ，然后选择新的"删除所有覆盖"选项以删除该\*\*\*\* 文件夹中的所有局部覆盖。</span><span class="sxs-lookup"><span data-stu-id="c0333-239">After setting up **Local Overrides** you may hover on a directory, open the contextual menu \(right-click\), and choose the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="删除所有覆盖" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="c0333-241">删除所有覆盖</span><span class="sxs-lookup"><span data-stu-id="c0333-241">Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-242">通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！</span><span class="sxs-lookup"><span data-stu-id="c0333-242">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0333-243">Chromium 问题 [#1016501][CR1016501]</span><span class="sxs-lookup"><span data-stu-id="c0333-243">Chromium issue [#1016501][CR1016501]</span></span>  

### <a name="updated-long-tasks-ui"></a><span data-ttu-id="c0333-244">更新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="c0333-244">Updated Long tasks UI</span></span>  

<span data-ttu-id="c0333-245">**长任务**是长时间垄断了主线程，从而导致网页冻结的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="c0333-245">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="c0333-246">你已经能够[在“性能”面板中可视化长任务][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]了一段时间，但是在Microsoft Edge 83中，“性能”面板中的长任务可视化 UI 已更新。</span><span class="sxs-lookup"><span data-stu-id="c0333-246">You have been able to [visualize Long Tasks in the Performance panel][DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="c0333-247">现在，任务的长任务部分的颜色为带条纹红色背景。</span><span class="sxs-lookup"><span data-stu-id="c0333-247">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新的长任务 UI" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="c0333-249">新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="c0333-249">The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="c0333-250">通过推 [文或][PostTweetEdgeDevTools] 选择"发送反馈"图标 [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ！</span><span class="sxs-lookup"><span data-stu-id="c0333-250">Send your feedback by [tweeting][PostTweetEdgeDevTools] orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="c0333-251">Chromium 问题 [#1054447][CR1054447]</span><span class="sxs-lookup"><span data-stu-id="c0333-251">Chromium issue [#1054447][CR1054447]</span></span>  

### <a name="maskable-icon-support-in-the-manifest-pane"></a><span data-ttu-id="c0333-252">"清单" 窗格中的可屏蔽图标支持</span><span class="sxs-lookup"><span data-stu-id="c0333-252">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="c0333-253">Android Oreo 引入了自适应图标，可在不同的设备模型之间显示各种形状中的应用图标。</span><span class="sxs-lookup"><span data-stu-id="c0333-253">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="c0333-254">**可屏蔽图标**是支持自适应图标的新图标格式，使你可以确保[ PWA ][ProgressiveWebAppsChromiumIndex]图标在支持可屏蔽图标标准的设备上看起来不错。</span><span class="sxs-lookup"><span data-stu-id="c0333-254">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][ProgressiveWebAppsChromiumIndex] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="c0333-255">在**清单**窗格中启用新的**仅显示可屏蔽图标的最小安全区域**复选框，以检查可屏蔽图标在 Android Oreo 设备上看起来是否良好。</span><span class="sxs-lookup"><span data-stu-id="c0333-255">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text="仅显示可屏蔽图标的最小安全区域复选框" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="c0333-257">" **仅显示可屏蔽图标的最小安全区域"** 复选框</span><span class="sxs-lookup"><span data-stu-id="c0333-257">The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c0333-258">此功能在 Microsoft Edge 81 中发布。</span><span class="sxs-lookup"><span data-stu-id="c0333-258">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="c0333-259">["DevTools （Microsoft Edge 81）"][WhatsNew81]中的新增功能未涵盖 Microsoft Edge 83 中介绍的更新。</span><span class="sxs-lookup"><span data-stu-id="c0333-259">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="c0333-260">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="c0333-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="c0333-261">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="c0333-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="c0333-262">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="c0333-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="c0333-263">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="c0333-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[WhatsNew81]: ../01/devtools.md "DevTools 中的新增功能 (Microsoft Edge 81) | Microsoft Docs"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevtoolsCssReferenceColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "使用颜色选取器更改颜色|Microsoft Docs"  
[DevtoolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门 | Microsoft 文档"  
[DevtoolsCustomizePlacementsChangeMainMenu]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "从主菜单菜单更改|Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceViewMainThreadActivity]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "查看主线程活动|Microsoft Docs"  
[DevtoolsEvaluatePreformanceReferenceAnalyzeRenderingTab]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用&quot;呈现&quot;选项卡功能分析|Microsoft Docs"  
[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 应用上的渐进式 Web |Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备|Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLineCode]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "代码行断点 - 如何在 Microsoft Edge DevTools |Microsoft Docs"
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "按属性筛选请求 - 网络分析参考|Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows 设备门户概述"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 适用的远程工具 (Beta)"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20 "在适用于 Microsoft Edge 的稳定频道版本上更新"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer - GitHub"  

[MicrosoftVisualstudio]: https://visualstudio.microsoft.com "Visual Studio"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  
[TheWebWeWant]: https://webwewant.fyi "我们想要的网络"  

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness "色盲类型"  

[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "接受语言|MDN"  
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives "Cookie 设置|MDN"  

[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "依赖于区域设置的代码示例"  

[CR963183]: https://crbug.com/963183 "问题 963183：DevTools 不符合 WCAG"  
[CR1003700]: https://crbug.com/1003700 "问题 1003700：添加 DevTools 支持颜色视觉缺陷模拟"  
[CR1011679]: https://crbug.com/1011679 "问题 1011679：使用命令菜单引入 &quot;停靠到左侧&quot;"  
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

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "灯塔 | GitHub"  

> [!NOTE]
> <span data-ttu-id="c0333-305">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c0333-305">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c0333-306">原始页面位于[此处](https://developer.chrome.com/blog/new-in-devtools-83)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="c0333-306">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-83) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="c0333-308">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c0333-308">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
