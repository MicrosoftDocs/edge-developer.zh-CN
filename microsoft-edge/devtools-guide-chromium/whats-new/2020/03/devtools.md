---
title: DevTools 中的新增功能（Microsoft Edge 83）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 7651430c581346d1f140f0a5974b8aa9bb809204
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708986"
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

# <span data-ttu-id="79a75-103">DevTools 中的新增功能（Microsoft Edge 83）</span><span class="sxs-lookup"><span data-stu-id="79a75-103">What's New In DevTools (Microsoft Edge 83)</span></span>  

<span data-ttu-id="79a75-104">按照更新后的 Chromium 计划，我们将调整即将开始的 Microsoft Edge 发布和取消 Microsoft Edge 82 版本的计划。</span><span class="sxs-lookup"><span data-stu-id="79a75-104">Following the updated Chromium schedule, we are adjusting our schedule for upcoming Microsoft Edge releases and cancelling the Microsoft Edge 82 release.</span></span> <span data-ttu-id="79a75-105">有关详细信息，请查看我们的[博客文章][WindowsBlogStableRelease]。</span><span class="sxs-lookup"><span data-stu-id="79a75-105">Check out our [blog post][WindowsBlogStableRelease] for more info.</span></span>  

<span data-ttu-id="79a75-106">下面是 Microsoft Edge 83 的 DevTools 中可用的新功能。</span><span class="sxs-lookup"><span data-stu-id="79a75-106">Here are the new features available in the DevTools in Microsoft Edge 83.</span></span>  

## <span data-ttu-id="79a75-107">Microsoft Edge DevTools 团队的公告</span><span class="sxs-lookup"><span data-stu-id="79a75-107">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="79a75-108">以下部分是您可能已错过的 Microsoft Edge DevTools 团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="79a75-108">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="79a75-109">请查看这些功能，尝试 DevTools、VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="79a75-109">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="79a75-110">若要随时了解开发人员工具中的所有最新功能和最新功能，请下载[Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="79a75-110">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="79a75-111">在 Windows 10 设备上远程调试 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="79a75-111">Remotely debug Microsoft Edge on Windows 10 Devices</span></span>  

<span data-ttu-id="79a75-112">Microsoft [Edge 的远程工具 \ （Beta \）][RemoteTools]应用现已在[microsoft Store][MicrosoftStore]中提供。</span><span class="sxs-lookup"><span data-stu-id="79a75-112">The [Remote Tools for Microsoft Edge \(Beta\)][RemoteTools] app is now available in the [Microsoft Store][MicrosoftStore].</span></span>  <span data-ttu-id="79a75-113">使用此应用（扩展[Windows Device Portal][WindowsDevicePortal]），你可以从你的开发计算机上运行的 Microsoft Edge 实例连接到远程 windows 10 设备，查看目标列表 \ （Microsoft Edge 中的所有选项卡和[PWAs][PWADoc]在 Windows 10 设备 \），并针对在远程 Windows 10 设备上运行的目标使用你的开发计算机上的 DevTools。</span><span class="sxs-lookup"><span data-stu-id="79a75-113">Using this app, which extends the [Windows Device Portal][WindowsDevicePortal], you are able to connect from the instance of Microsoft Edge running on your development machine to a remote Windows 10 device, see a list of targets \(all tabs in Microsoft Edge and [PWAs][PWADoc] open on the Windows 10 device\), and use the DevTools on your development machine against a target running on the remote Windows 10 device.</span></span>  

:::image type="complex" source="../../media/2020/03/remote-tools.msft.png" alt-text="Microsoft Store 中可用的 Microsoft Edge 远程工具（Beta）应用" lightbox="../../media/2020/03/remote-tools.msft.png":::
   <span data-ttu-id="79a75-115">图1： [Microsoft Store][MicrosoftStore]中可用的[Microsoft Edge 远程工具（Beta）][RemoteTools]应用</span><span class="sxs-lookup"><span data-stu-id="79a75-115">Figure 1:  The [Remote Tools for Microsoft Edge (Beta)][RemoteTools] app available in the [Microsoft Store][MicrosoftStore]</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-116">[阅读有关设置 Windows 10 设备和开发计算机以进行远程调试的指南][RemoteDebuggingWin10]。</span><span class="sxs-lookup"><span data-stu-id="79a75-116">[Read our guide for setting up your Windows 10 device and your development machine for remote debugging][RemoteDebuggingWin10].</span></span>  <span data-ttu-id="79a75-117">通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标，让我们了解你的远程调试体验！</span><span class="sxs-lookup"><span data-stu-id="79a75-117">Let us know about your remote debugging experience by [tweeting][PostTweetEdgeDevTools] or clicking the [Feedback](#feedback) icon!</span></span>  

### <span data-ttu-id="79a75-118">访问设置的新方法</span><span class="sxs-lookup"><span data-stu-id="79a75-118">New ways to access Settings</span></span>  

<span data-ttu-id="79a75-119">你可以自定义的 DevTools 设置有很多种，以使 DevTools 外观、感觉和工作方式符合你的需求。</span><span class="sxs-lookup"><span data-stu-id="79a75-119">There are tons of settings for the DevTools that you are able to customize to make the DevTools look, feel, and work the way you need.</span></span> <span data-ttu-id="79a75-120">在 Microsoft Edge 83 中，访问 DevTools 中的[设置][OverviewSettings]现在更加轻松。</span><span class="sxs-lookup"><span data-stu-id="79a75-120">In Microsoft Edge 83, accessing [Settings][OverviewSettings] in the DevTools is now much easier.</span></span> <span data-ttu-id="79a75-121">打开设置，"控制台通知" 和 "主菜单" 旁边的齿轮图标。</span><span class="sxs-lookup"><span data-stu-id="79a75-121">Open Settings with the gear icon next to Console alerts and the main menu.</span></span>  

:::image type="complex" source="../../media/2020/03/settings.msft.png" alt-text="齿轮图标将在 DevTools 中打开 "设置"" lightbox="../../media/2020/03/settings.msft.png":::
   <span data-ttu-id="79a75-123">图2： "齿轮" 图标在 DevTools 中打开 "**设置**"</span><span class="sxs-lookup"><span data-stu-id="79a75-123">Figure 2:  The gear icon opens **Settings** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-124">您还可以在 "**更多工具**" 下的**主菜单**中打开 "[设置][OverviewSettings]"。</span><span class="sxs-lookup"><span data-stu-id="79a75-124">You are also able to open [Settings][OverviewSettings] from the **Main Menu** under **More tools**.</span></span>

:::image type="complex" source="../../media/2020/03/settings2.msft.png" alt-text="主菜单 > 更多工具 > 设置" lightbox="../../media/2020/03/settings2.msft.png":::
   <span data-ttu-id="79a75-126">图3：**主菜单**  >  **更多工具**  >  **设置**</span><span class="sxs-lookup"><span data-stu-id="79a75-126">Figure 3:  **Main Menu** > **More tools** > **Settings**</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-127">Chromium 问题[#1050855][crbug1050855]</span><span class="sxs-lookup"><span data-stu-id="79a75-127">Chromium issue [#1050855][crbug1050855]</span></span>

### <span data-ttu-id="79a75-128">新增功能和改进的 infobars</span><span class="sxs-lookup"><span data-stu-id="79a75-128">New and improved infobars</span></span>

<span data-ttu-id="79a75-129">DevTools 中的信息性通知条 \ （infobars \）现在具有改进的外观和更多功能。</span><span class="sxs-lookup"><span data-stu-id="79a75-129">Informational notification bars \(infobars\) in DevTools now have an improved look and more functionality.</span></span> <span data-ttu-id="79a75-130">在 Microsoft Edge 83 中，infobars 更易于阅读和提供按钮，以便你能够立即执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="79a75-130">In Microsoft Edge 83, infobars are easier to read and provide buttons so you are able to take the relevant action right away.</span></span>  

:::image type="complex" source="../../media/2020/03/infobar.msft.png" alt-text="在 Microsoft Edge 83 中美观打印 minified 文件的信息栏" lightbox="../../media/2020/03/infobar.msft.png":::
   <span data-ttu-id="79a75-132">图4：在 Microsoft Edge 版本83中美观打印 minified 文件的信息栏</span><span class="sxs-lookup"><span data-stu-id="79a75-132">Figure 4:  Infobar for pretty-printing a minified file in Microsoft Edge Version 83</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-133">Chromium 问题[#1056348][crbug1056348]</span><span class="sxs-lookup"><span data-stu-id="79a75-133">Chromium issue [#1056348][crbug1056348]</span></span>

### <span data-ttu-id="79a75-134">通过键盘导航拾色器</span><span class="sxs-lookup"><span data-stu-id="79a75-134">Navigate the Color Picker with your keyboard</span></span>  

<span data-ttu-id="79a75-135">[颜色选取器][ColorPicker]是 "[元素" 面板][ElementsDoc]中用于更改 `color` 和声明的 GUI `background-color` 。</span><span class="sxs-lookup"><span data-stu-id="79a75-135">The [Color Picker][ColorPicker] is a GUI in the [Elements panel][ElementsDoc] for changing `color` and `background-color` declarations.</span></span>  <span data-ttu-id="79a75-136">在早期版本的 Microsoft Edge 中，无法通过键盘导航[拾色器][ColorPicker]的 "**底纹**" 部分。</span><span class="sxs-lookup"><span data-stu-id="79a75-136">In previous versions of Microsoft Edge, you were not able to navigate the **Shades** section of the [Color Picker][ColorPicker] with the keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/color-picker.msft.png" alt-text="现在，你可以使用键盘移动颜色选取器的 "底纹" 部分中的选择器" lightbox="../../media/2020/03/color-picker.msft.png":::
   <span data-ttu-id="79a75-138">图5：您现在可以使用键盘在[拾色器][ColorPicker]的 "**底纹**" 部分移动选择器</span><span class="sxs-lookup"><span data-stu-id="79a75-138">Figure 5:  You are now able to use your keyboard to move the selector in the **Shades** section of the [Color Picker][ColorPicker]</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-139">在 Microsoft Edge 83 中，你现在可以使用键盘在拾色器的 "**底纹**" 部分移动选择器。</span><span class="sxs-lookup"><span data-stu-id="79a75-139">In Microsoft Edge 83, you are now able to use the keyboard to move the selector in the **Shades** section of the Color Picker.</span></span>  

<span data-ttu-id="79a75-140">Chromium 问题[#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="79a75-140">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="79a75-141">"属性" 选项卡现在将在页面刷新后填充</span><span class="sxs-lookup"><span data-stu-id="79a75-141">Properties tab now populates after a page refresh</span></span>  

<span data-ttu-id="79a75-142">在 Microsoft Edge 81 及更早版本中，"[元素" 面板][ElementsDoc]中的 "**属性" 选项卡**因页面刷新而损坏。</span><span class="sxs-lookup"><span data-stu-id="79a75-142">In Microsoft Edge 81 and earlier, the **Properties tab** in the [Elements panel][ElementsDoc] was broken by page refreshes.</span></span>  <span data-ttu-id="79a75-143">刷新页面后，"属性"**选项卡**不会填充当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="79a75-143">When you refreshed the page, the **Properties tab** did not populate the properties of the currently-selected element.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-81.msft.png" alt-text="在 Microsoft Edge 81 及更早版本中，在页面刷新后，"属性" 选项卡为空" lightbox="../../media/2020/03/properties-in-81.msft.png":::
   <span data-ttu-id="79a75-145">图6：在 Microsoft Edge 81 及更早版本中，在页面刷新后，"**属性" 选项卡**为空</span><span class="sxs-lookup"><span data-stu-id="79a75-145">Figure 6:  In Microsoft Edge 81 and earlier, the **Properties tab** was blank after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-146">在 Microsoft Edge 83 中，你现在可以在 "**属性" 选项卡**中的页面刷新后查看当前所选元素的属性。</span><span class="sxs-lookup"><span data-stu-id="79a75-146">In Microsoft Edge 83, you are now able to see the properties of the currently-selected element after a page refresh in the **Properties tab**.</span></span>  

:::image type="complex" source="../../media/2020/03/properties-in-82.msft.png" alt-text="在 Microsoft Edge 83 中，在页面刷新后，"属性" 选项卡显示当前选定元素的属性" lightbox="../../media/2020/03/properties-in-82.msft.png":::
   <span data-ttu-id="79a75-148">图7：在 Microsoft Edge 83 中，在页面刷新后，"**属性" 选项卡**显示当前选定元素的属性</span><span class="sxs-lookup"><span data-stu-id="79a75-148">Figure 7:  In Microsoft Edge 83, the **Properties tab** displays the properties of the currently-selected element after a page refresh</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-149">Chromium 问题[#1050999][crbug1050999]</span><span class="sxs-lookup"><span data-stu-id="79a75-149">Chromium issue [#1050999][crbug1050999]</span></span>  

### <span data-ttu-id="79a75-150">使用箭头键在 "更改" 工具中滚动</span><span class="sxs-lookup"><span data-stu-id="79a75-150">Use the arrow keys to scroll in the Changes tool</span></span>  

<span data-ttu-id="79a75-151">"**更改" 工具**跟踪你对 DevTools 中的 CSS 或 JavaScript 所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="79a75-151">The **Changes tool** tracks any changes you have made to CSS or JavaScript in the DevTools.</span></span>  <span data-ttu-id="79a75-152">你可以使用 "更改"**工具**快速查看所有更改并将这些更改恢复到编辑器/IDE。</span><span class="sxs-lookup"><span data-stu-id="79a75-152">You are able to use the **Changes tool** to quickly see all your changes and take those back to your editor/IDE.</span></span>  

<span data-ttu-id="79a75-153">通过**Changes tool** `Ctrl` + `Shift` + `P` 在 DevTools 中按下以打开 "[命令" 菜单][DevToolsCommandMenuIndex]并键入， `changes` 打开 "更改" 工具。</span><span class="sxs-lookup"><span data-stu-id="79a75-153">Open the **Changes tool** by pressing `Ctrl`+`Shift`+`P` in the DevTools to open the [Command Menu][DevToolsCommandMenuIndex] and typing `changes`.</span></span>  <span data-ttu-id="79a75-154">选择并运行 "**显示更改**" 命令以打开 DevTools 抽屉中的 "**更改" 工具**。</span><span class="sxs-lookup"><span data-stu-id="79a75-154">Select and run the **Show Changes** command to open the **Changes tool** in the DevTools drawer.</span></span>  

<span data-ttu-id="79a75-155">对 minified 文件进行更改后，"**更改" 工具**使您能够水平滚动查看所有 minified 代码。</span><span class="sxs-lookup"><span data-stu-id="79a75-155">When you have made a change to a minified file, the **Changes tool** enables you to scroll horizontally to see all of your minified code.</span></span>  <span data-ttu-id="79a75-156">从 Microsoft Edge 83 开始，您现在可以使用键盘上的箭头键水平滚动。</span><span class="sxs-lookup"><span data-stu-id="79a75-156">Starting in Microsoft Edge 83, you may now scroll horizontally using the arrow keys on your keyboard.</span></span>  

:::image type="complex" source="../../media/2020/03/changes.msft.png" alt-text="在 Microsoft Edge 83 中，你可以通过箭头键水平滚动以在 "更改" 工具中查看你的 minified 代码" lightbox="../../media/2020/03/changes.msft.png":::
   <span data-ttu-id="79a75-158">图8：在 Microsoft Edge 83 中，你可以通过箭头键水平滚动，以在 "**更改" 工具**中看到你对 minified 代码所做的更改</span><span class="sxs-lookup"><span data-stu-id="79a75-158">Figure 8:  In Microsoft Edge 83, you may scroll horizontally with the arrow keys to see the changes you made to your minified code in the **Changes tool**</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-159">如果您使用屏幕阅读器或键盘在 DevTools 中导航，请向我们发送您的反馈[发推至][PostTweetEdgeDevTools]，或单击 "[反馈](#feedback)" 图标！</span><span class="sxs-lookup"><span data-stu-id="79a75-159">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="79a75-160">Chromium 问题[#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="79a75-160">Chromium issue [#963183][crbug963183]</span></span>  

## <span data-ttu-id="79a75-161">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="79a75-161">Announcements from the Chromium project</span></span>  

<span data-ttu-id="79a75-162">以下各节宣布了在 Microsoft Edge 83 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="79a75-162">The following sections announce additional features available in Microsoft Edge 83 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="79a75-163">模仿视觉缺陷</span><span class="sxs-lookup"><span data-stu-id="79a75-163">Emulate vision deficiencies</span></span>  

<span data-ttu-id="79a75-164">打开 "[呈现" 选项卡][RenderingDoc]，并使用新的 "**模拟视觉缺陷**" 功能来更好地了解具有不同类型的视觉缺陷的人如何体验您的网站。</span><span class="sxs-lookup"><span data-stu-id="79a75-164">Open the [Rendering tab][RenderingDoc] and use the new **Emulate vision deficiencies** feature to get a better idea of how people with different types of vision deficiencies experience your site.</span></span>  

:::image type="complex" source="../../media/2020/03/vision.msft.png" alt-text="模拟模糊的视觉效果" lightbox="../../media/2020/03/vision.msft.png":::
   <span data-ttu-id="79a75-166">图9：模拟模糊的视觉效果</span><span class="sxs-lookup"><span data-stu-id="79a75-166">Figure 9:  Emulating blurred vision</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-167">DevTools 可以模拟模糊的视觉效果和以下[类型的颜色视觉缺陷][ColorBlindnessTypes]。</span><span class="sxs-lookup"><span data-stu-id="79a75-167">DevTools is able to emulate blurred vision and the following [types of color vision deficiencies][ColorBlindnessTypes].</span></span>  

| <span data-ttu-id="79a75-168">颜色远景缺陷</span><span class="sxs-lookup"><span data-stu-id="79a75-168">Color Vision Deficiency</span></span> | <span data-ttu-id="79a75-169">详细信息</span><span class="sxs-lookup"><span data-stu-id="79a75-169">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="79a75-170">Protanopia</span><span class="sxs-lookup"><span data-stu-id="79a75-170">Protanopia</span></span> | <span data-ttu-id="79a75-171">无法感觉任何红光。</span><span class="sxs-lookup"><span data-stu-id="79a75-171">The inability to perceive any red light.</span></span> |  
| <span data-ttu-id="79a75-172">Deuteranopia</span><span class="sxs-lookup"><span data-stu-id="79a75-172">Deuteranopia</span></span> | <span data-ttu-id="79a75-173">无法感觉任何绿色光。</span><span class="sxs-lookup"><span data-stu-id="79a75-173">The inability to perceive any green light.</span></span> |  
| <span data-ttu-id="79a75-174">Tritanopia</span><span class="sxs-lookup"><span data-stu-id="79a75-174">Tritanopia</span></span> | <span data-ttu-id="79a75-175">无法感觉任何蓝色光线。</span><span class="sxs-lookup"><span data-stu-id="79a75-175">The inability to perceive any blue light.</span></span> |  
| <span data-ttu-id="79a75-176">Achromatopsia</span><span class="sxs-lookup"><span data-stu-id="79a75-176">Achromatopsia</span></span> | <span data-ttu-id="79a75-177">除了灰色阴影的情况外，无法感知任何颜色（非常少见）。</span><span class="sxs-lookup"><span data-stu-id="79a75-177">The inability to perceive any color, except for shades of grey \(extremely rare\).</span></span> |  

<span data-ttu-id="79a75-178">这些颜色视觉缺陷的极端版本较少，并且事实上它们更为常见。</span><span class="sxs-lookup"><span data-stu-id="79a75-178">Less extreme versions of these color vision deficiencies exist, and in fact they are more common.</span></span>  
<span data-ttu-id="79a75-179">例如，protanomaly 缩小了红灯的灵敏度（相对于 protanopia，这是完全无法感知红灯的功能）。</span><span class="sxs-lookup"><span data-stu-id="79a75-179">For example, protanomaly is a reduced sensitivity to red light (as opposed to protanopia, which is the complete inability to perceive red light).</span></span> <span data-ttu-id="79a75-180">但是，这些 omaly 的视觉缺陷不是明确定义的：每个具有此类远景缺陷的人不同，并且可能会以不同的方式查看内容（能够感知更多/更少的相关颜色）。</span><span class="sxs-lookup"><span data-stu-id="79a75-180">However, these -omaly vision deficiencies are not as clearly defined: every person with such a vision deficiency is different and might see things differently (being able to perceive more/less of the relevant colors).</span></span>  

<span data-ttu-id="79a75-181">通过针对 DevTools 中更极端的模拟进行设计，你的 web 应用可保证可供具有 protanomaly、deuteranomaly、tritanomaly 和 achromatomaly 的用户访问。</span><span class="sxs-lookup"><span data-stu-id="79a75-181">By designing for the more extreme simulations in DevTools, your web apps are guaranteed to be accessible to people with protanomaly, deuteranomaly, tritanomaly, and achromatomaly as well.</span></span>  

<span data-ttu-id="79a75-182">通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="79a75-182">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="79a75-183">Chromium 问题[#1003700][crbug1003700]</span><span class="sxs-lookup"><span data-stu-id="79a75-183">Chromium issue [#1003700][crbug1003700]</span></span>  

### <span data-ttu-id="79a75-184">模拟区域设置</span><span class="sxs-lookup"><span data-stu-id="79a75-184">Emulate locales</span></span>  

<span data-ttu-id="79a75-185">通过在**传感器**位置设置位置来模拟语言环境  >  **Location**。</span><span class="sxs-lookup"><span data-stu-id="79a75-185">Emulate locales by setting a location in **Sensors** > **Location**.</span></span> <span data-ttu-id="79a75-186">[打开 "**命令" 菜单**][DevToolsCommandMenuIndex]并键入 `Sensors` 以访问 "**传感器**" 选项卡。 执行这些操作后，DevTools 将修改当前默认区域设置，从而影响以下代码。</span><span class="sxs-lookup"><span data-stu-id="79a75-186">[Open the **Command Menu**][DevToolsCommandMenuIndex] and type `Sensors` to access the **Sensors** tab.  After performing these actions, DevTools modifies the current default locale, affecting the following code.</span></span>  

*   `Intl.*` <span data-ttu-id="79a75-187">Api，例如：</span><span class="sxs-lookup"><span data-stu-id="79a75-187">APIs, for example:</span></span> `new Intl.NumberFormat().resolvedOptions().locale`  
*   <span data-ttu-id="79a75-188">其他与区域设置兼容的 JavaScript Api `String.prototype.localeCompare` `*.prototype.toLocaleString` ，例如和和：</span><span class="sxs-lookup"><span data-stu-id="79a75-188">Other locale-aware JavaScript APIs such as `String.prototype.localeCompare` and `*.prototype.toLocaleString`, for example:</span></span> `123_456..toLocaleString()`  
*   <span data-ttu-id="79a75-189">DOM Api，如 `navigator.language` 和</span><span class="sxs-lookup"><span data-stu-id="79a75-189">DOM APIs such as `navigator.language` and</span></span> `navigator.languages`  
*   <span data-ttu-id="79a75-190">[`Accept-Language`][MDNAcceptLanguage]HTTP 请求标头</span><span class="sxs-lookup"><span data-stu-id="79a75-190">The [`Accept-Language`][MDNAcceptLanguage] HTTP request header</span></span>  

> [!NOTE]
> <span data-ttu-id="79a75-191">对 `navigator.language` 和 `navigator.languages` 的更新立即可见，但仅在下一个导航或页面重新加载后出现。</span><span class="sxs-lookup"><span data-stu-id="79a75-191">Updates to `navigator.language` and `navigator.languages` are not visible immediately, but only after the next navigation or page reload.</span></span>  <span data-ttu-id="79a75-192">对 `Accept-Language` HTTP 标头的更改仅反映后续请求。</span><span class="sxs-lookup"><span data-stu-id="79a75-192">Changes to the `Accept-Language` HTTP header are only reflected for subsequent requests.</span></span>  

:::image type="complex" source="../../media/2020/03/locale.msft.png" alt-text="模拟区域设置" lightbox="../../media/2020/03/locale.msft.png":::
   <span data-ttu-id="79a75-194">图10：模拟区域设置</span><span class="sxs-lookup"><span data-stu-id="79a75-194">Figure 10:  Emulating a locale</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-195">若要尝试演示，请参阅与[区域设置相关的代码示例][MathiasByensLocaleDemo]。</span><span class="sxs-lookup"><span data-stu-id="79a75-195">To try a demo, see [Locale-dependent code example][MathiasByensLocaleDemo].</span></span>

<span data-ttu-id="79a75-196">Chromium 问题[#1051822][crbug1051822]</span><span class="sxs-lookup"><span data-stu-id="79a75-196">Chromium issue [#1051822][crbug1051822]</span></span>

### <span data-ttu-id="79a75-197">跨起源 Embedder 策略（COEP）调试</span><span class="sxs-lookup"><span data-stu-id="79a75-197">Cross-Origin Embedder Policy (COEP) debugging</span></span>  

<span data-ttu-id="79a75-198">现在，网络面板提供了[跨起源 Embedder 策略][COEP]调试信息。</span><span class="sxs-lookup"><span data-stu-id="79a75-198">The Network panel now provides [Cross-Origin Embedder Policy][COEP] debugging information.</span></span>  

<span data-ttu-id="79a75-199">"**状态**" 列现在提供了有关阻止请求的原因的快速说明，以及用于查看该请求的标题以进行进一步调试的链接：</span><span class="sxs-lookup"><span data-stu-id="79a75-199">The **Status** column now provides a quick explanation of why a request was blocked as well as a link to view the headers of that request for further debugging:</span></span>  

:::image type="complex" source="../../media/2020/03/status.msft.png" alt-text="\* \* 状态 \* \* 列中的被阻止的请求" lightbox="../../media/2020/03/status.msft.png":::
   <span data-ttu-id="79a75-201">图11： "状态" 列中的被阻止的请求</span><span class="sxs-lookup"><span data-stu-id="79a75-201">Figure 11:  Blocked requests in the Status column</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-202">"**页眉**" 选项卡的 "**响应标题**" 部分提供了有关如何解决这些问题的更多指导：</span><span class="sxs-lookup"><span data-stu-id="79a75-202">The **Response Headers** section of the **Headers** tab provides more guidance on how to resolve the issues:</span></span>  

:::image type="complex" source="../../media/2020/03/guidance.msft.png" alt-text=""响应标题" 部分中的更多指导" lightbox="../../media/2020/03/guidance.msft.png":::
   <span data-ttu-id="79a75-204">图12： "响应标题" 部分中的更多指导</span><span class="sxs-lookup"><span data-stu-id="79a75-204">Figure 12:  More guidance in the Response Headers section</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-205">通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="79a75-205">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="79a75-206">Chromium 问题[#1051466][crbug1051466]</span><span class="sxs-lookup"><span data-stu-id="79a75-206">Chromium issue [#1051466][crbug1051466]</span></span>  

### <span data-ttu-id="79a75-207">查看设置特定 cookie 路径的网络请求</span><span class="sxs-lookup"><span data-stu-id="79a75-207">View network requests that set a specific cookie path</span></span>  

<span data-ttu-id="79a75-208">使用 " `cookie-path` **网络**" 面板中的新筛选器关键字来集中关注设置特定[cookie 路径][MDNCookiePath]的网络请求。</span><span class="sxs-lookup"><span data-stu-id="79a75-208">Use the new `cookie-path` filter keyword in the **Network** panel to focus on the network requests that set a specific [cookie path][MDNCookiePath].</span></span>  

<span data-ttu-id="79a75-209">[通过属性查看筛选器请求][NetworkProperties]以发现更多类似 `cookie-path` 的关键字。</span><span class="sxs-lookup"><span data-stu-id="79a75-209">Check out [Filter requests by properties][NetworkProperties] to discover more keywords like `cookie-path`.</span></span>

### <span data-ttu-id="79a75-210">从 "命令" 菜单停靠到左侧</span><span class="sxs-lookup"><span data-stu-id="79a75-210">Dock to left from the Command Menu</span></span>  

<span data-ttu-id="79a75-211">打开 "[命令" 菜单][DevToolsCommandMenuIndex]并运行 `Dock to left` 命令，将 DevTools 移到视区左侧。</span><span class="sxs-lookup"><span data-stu-id="79a75-211">Open the [Command Menu][DevToolsCommandMenuIndex] and run the `Dock to left` command to move DevTools to the left of your viewport.</span></span>  

:::image type="complex" source="../../media/2020/03/dock-to-left.msft.png" alt-text="停靠在视区左侧的 DevTools" lightbox="../../media/2020/03/dock-to-left.msft.png":::
   <span data-ttu-id="79a75-213">图13：停靠在视区左侧的 DevTools</span><span class="sxs-lookup"><span data-stu-id="79a75-213">Figure 13:  DevTools docked to the left of the viewport</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="79a75-214">自 Microsoft Edge 75 后，"**停靠到左侧**" 功能可用，但以前只能从[**主菜单**][MainMenuDoc]访问它。</span><span class="sxs-lookup"><span data-stu-id="79a75-214">The **Dock to left** feature has been available since Microsoft Edge 75, but it was previously only accessible from the [**Main Menu**][MainMenuDoc].</span></span>  <span data-ttu-id="79a75-215">Microsoft Edge 83 中的新功能是您现在可以从 "命令" 菜单访问此功能。</span><span class="sxs-lookup"><span data-stu-id="79a75-215">The new feature in Microsoft Edge 83 is that you may now access this feature from the Command Menu.</span></span>  

<span data-ttu-id="79a75-216">通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="79a75-216">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="79a75-217">Chromium 问题[#1011679][crbug1011679]</span><span class="sxs-lookup"><span data-stu-id="79a75-217">Chromium issue [#1011679][crbug1011679]</span></span>  

### <span data-ttu-id="79a75-218">"审核" 面板现在是 Lighthouse 面板</span><span class="sxs-lookup"><span data-stu-id="79a75-218">The Audits panel is now the Lighthouse panel</span></span>  

<span data-ttu-id="79a75-219">DevTools 团队经常获得来自 web 开发人员的反馈，尽管可以从 DevTools 运行[Lighthouse][GithubGoogleChromeLighthouse] ，但他们尝试了无法找到 "Lighthouse" 面板，因此 "**审核**" 面板现在是 " **Lighthouse** " 面板。</span><span class="sxs-lookup"><span data-stu-id="79a75-219">The DevTools team frequently got feedback from web developers that while it was possible to run [Lighthouse][GithubGoogleChromeLighthouse] from DevTools, when they tried it out they were not able to find the "Lighthouse" panel, so the **Audits** panel is now the **Lighthouse** panel.</span></span>  

:::image type="complex" source="../../media/2020/03/lighthouse.msft.png" alt-text="Lighthouse 面板" lightbox="../../media/2020/03/lighthouse.msft.png":::
   <span data-ttu-id="79a75-221">图14： Lighthouse 面板</span><span class="sxs-lookup"><span data-stu-id="79a75-221">Figure 14:  The Lighthouse panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="79a75-222">**Lighthouse**面板提供了指向第三方网站上托管内容的链接。</span><span class="sxs-lookup"><span data-stu-id="79a75-222">The **Lighthouse** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="79a75-223">Microsoft 不承担任何责任，也不能控制这些网站的内容和他们可能收集的任何数据。</span><span class="sxs-lookup"><span data-stu-id="79a75-223">Microsoft is not responsible for and has no control over the content of these sites and any data they may collect.</span></span>  

### <span data-ttu-id="79a75-224">删除文件夹中的所有本地覆盖</span><span class="sxs-lookup"><span data-stu-id="79a75-224">Delete all Local Overrides in a folder</span></span>  

<span data-ttu-id="79a75-225">设置**本地替代**后，您可以右键单击某个文件夹，然后选择 "新建**删除全部替代**" 选项以删除该文件夹中的所有本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="79a75-225">After setting up **Local Overrides** you may right-click a folder and select the new **Delete all overrides** option to delete all Local Overrides in that folder.</span></span>  

:::image type="complex" source="../../media/2020/03/overrides.msft.png" alt-text="删除所有替代" lightbox="../../media/2020/03/overrides.msft.png":::
   <span data-ttu-id="79a75-227">图15：删除所有替代</span><span class="sxs-lookup"><span data-stu-id="79a75-227">Figure 15:  Delete all overrides</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-228">通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="79a75-228">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="79a75-229">Chromium 问题[#1016501][crbug1016501]</span><span class="sxs-lookup"><span data-stu-id="79a75-229">Chromium issue [#1016501][crbug1016501]</span></span>  

### <span data-ttu-id="79a75-230">更新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="79a75-230">Updated Long tasks UI</span></span>  

<span data-ttu-id="79a75-231">较**长任务**是 monopolizes 主线程长时间的 JavaScript 代码，导致网页冻结。</span><span class="sxs-lookup"><span data-stu-id="79a75-231">A **Long Task** is JavaScript code that monopolizes the main thread for a long time, causing a web page to freeze.</span></span>  

<span data-ttu-id="79a75-232">现在，你可以在[性能面板中可视化长任务][LongTasksInPerformancePanel]，但在 Microsoft Edge 83 中，"性能" 面板中的长任务可视化用户界面已更新。</span><span class="sxs-lookup"><span data-stu-id="79a75-232">You have been able to [visualize Long Tasks in the Performance panel][LongTasksInPerformancePanel] for a while now, but in Microsoft Edge 83 the Long Task visualization UI in the Performance panel has been updated.</span></span>  <span data-ttu-id="79a75-233">现在，任务的长任务部分使用带条纹红色背景进行着色。</span><span class="sxs-lookup"><span data-stu-id="79a75-233">The Long Task portion of a task is now colored with a striped red background.</span></span>  

:::image type="complex" source="../../media/2020/03/long-task.msft.png" alt-text="新的长任务 UI" lightbox="../../media/2020/03/long-task.msft.png":::
   <span data-ttu-id="79a75-235">图16：新的长任务 UI</span><span class="sxs-lookup"><span data-stu-id="79a75-235">Figure 16:  The new Long Task UI</span></span>  
:::image-end:::  

<span data-ttu-id="79a75-236">通过[发推至][PostTweetEdgeDevTools]或单击 "[反馈](#feedback)" 图标发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="79a75-236">Send your feedback by [tweeting][PostTweetEdgeDevTools] or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="79a75-237">Chromium 问题[#1054447][crbug1054447]</span><span class="sxs-lookup"><span data-stu-id="79a75-237">Chromium issue [#1054447][crbug1054447]</span></span>  

### <span data-ttu-id="79a75-238">清单窗格中的屏蔽图标支持</span><span class="sxs-lookup"><span data-stu-id="79a75-238">Maskable icon support in the Manifest pane</span></span>  

<span data-ttu-id="79a75-239">Android Oreo 引入了自适应图标，可在不同的设备模型中显示各种形状的应用图标。</span><span class="sxs-lookup"><span data-stu-id="79a75-239">Android Oreo introduced adaptive icons, which display app icons in a variety of shapes across different device models.</span></span>  <span data-ttu-id="79a75-240">**屏蔽图标**是支持自适应图标的新图标格式，使你能够确保[PWA][PWADoc]图标在支持可屏蔽图标标准的设备上看起来更美观。</span><span class="sxs-lookup"><span data-stu-id="79a75-240">**Maskable icons** are a new icon format that support adaptive icons, which enable you to ensure that your [PWA][PWADoc] icon looks good on devices that support the maskable icons standard.</span></span>  

<span data-ttu-id="79a75-241">启用 "新建" 仅显示**清单**窗格中的 **"屏蔽图标的最小安全区域"** 复选框，以检查 Android Oreo 设备上的可屏蔽图标是否正常显示。</span><span class="sxs-lookup"><span data-stu-id="79a75-241">Enable the new **Show only the minimum safe area for maskable icons** checkbox in the **Manifest** pane to check that your maskable icon looks good on Android Oreo devices.</span></span>  

<!-- Check out [Are my current icons ready?] to learn more.  -->  

:::image type="complex" source="../../media/2020/03/maskable-icons.msft.png" alt-text=""仅显示屏蔽图标的最小安全区域" 复选框" lightbox="../../media/2020/03/maskable-icons.msft.png":::
   <span data-ttu-id="79a75-243">图17： "**仅显示屏蔽图标的最小安全区域"** 复选框</span><span class="sxs-lookup"><span data-stu-id="79a75-243">Figure 17:  The **Show only the minimum safe area for maskable icons** checkbox</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="79a75-244">此功能在 Microsoft Edge 81 中启动。</span><span class="sxs-lookup"><span data-stu-id="79a75-244">This feature launched in Microsoft Edge 81.</span></span>  <span data-ttu-id="79a75-245">Microsoft Edge 83 中介绍的更新未在[DevTools （Microsoft Edge 81）中的新增功能][WhatsNew81]中介绍。</span><span class="sxs-lookup"><span data-stu-id="79a75-245">The updates covered here in Microsoft Edge 83 were not covered in [What's New In DevTools (Microsoft Edge 81)][WhatsNew81].</span></span>  

## <span data-ttu-id="79a75-246">反馈</span><span class="sxs-lookup"><span data-stu-id="79a75-246">Feedback</span></span>  

<span data-ttu-id="79a75-247">若要讨论此文章中的新功能和更改，或与 DevTools 相关的任何其他内容，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="79a75-247">To discuss the new features and changes in this post, or anything else related to DevTools:</span></span>  

*   <span data-ttu-id="79a75-248">使用 DevTools 中的**反馈**图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="79a75-248">Send your feedback using the **Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="79a75-249">Tweet [@EdgeDevTools][PostTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="79a75-249">Tweet at [@EdgeDevTools][PostTweetEdgeDevTools]</span></span>  
*   <span data-ttu-id="79a75-250">向[我们需要的网站][TheWebWeWant]提交建议</span><span class="sxs-lookup"><span data-stu-id="79a75-250">Submit a suggestion to [The Web We Want][TheWebWeWant]</span></span>  
*   <span data-ttu-id="79a75-251">此文档在[edge-开发人员][GitHubMicrosoftDocsEdgeDeveloperNewIssue]存储库中的文件错误</span><span class="sxs-lookup"><span data-stu-id="79a75-251">File bugs on this document in the [edge-developer][GitHubMicrosoftDocsEdgeDeveloperNewIssue] repository</span></span>  

:::image type="complex" source="../../media/2020/03/feedback-icon.msft.png" alt-text="Microsoft Edge DevTools 中的 \* \* 反馈 \* \* 图标" lightbox="../../media/2020/03/feedback-icon.msft.png":::
   <span data-ttu-id="79a75-253">图18： Microsoft Edge DevTools 中的 "**反馈**" 图标</span><span class="sxs-lookup"><span data-stu-id="79a75-253">Figure 18:  The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

## <span data-ttu-id="79a75-254">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="79a75-254">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="79a75-255">如果你使用的是 Windows 或 macOS，请考虑将[Microsoft Edge 预览通道][MicrosoftEdgePreviewChannels]用作默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="79a75-255">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="79a75-256">预览频道使您可以访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="79a75-256">The preview channels give you access to the latest DevTools features.</span></span>  

<!-- links -->  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |发布 Tweet"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题-MicrosoftDocs/edge-开发人员"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[TheWebWeWant]: https://aka.ms/webwewant "我们需要的网站"  

[WhatsNew81]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/01/devtools "DevTools 中的新增功能（Microsoft Edge 81）"  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[ColorPicker]: /microsoft-edge/devtools-guide-chromium/css/reference#change-colors-with-the-color-picker "通过拾色器更改颜色"  
[ElementsDoc]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  
[MainMenuDoc]: /microsoft-edge/devtools-guide-chromium/customize/placement#change-placement-from-the-main-menu "从主菜单更改位置"  
[LongTasksInPerformancePanel]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#view-main-thread-activity "查看主线程活动"  
[RenderingDoc]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "通过 "渲染" 选项卡分析渲染性能"  
[PWADoc]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用"  
[RemoteDebuggingWin10]: /microsoft-edge/devtools-guide-chromium/remote-debugging/windows "远程调试 Windows 10 设备入门"  
[LineOfCodeBreakpoints]: /microsoft-edge/devtools-guide-chromium/javascript/breakpoints#line-of-code-breakpoints "代码行断点"
[NetworkProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties
[OverviewSettings]: /microsoft-edge/devtools-guide-chromium/customize/#settings

[WindowsDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal 概述"  

[RemoteTools]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "Microsoft Edge 远程工具（Beta 版）"  
[MicrosoftStore]: https://www.microsoft.com/store/apps/windows "Microsoft Store"  
[WindowsBlogStableRelease]: https://blogs.windows.com/msedgedev/2020/03/20/update-stable-channel-releases/ "在适用于 Microsoft Edge 的稳定信道版本上更新"

[ColorBlindnessTypes]: http://www.colourblindawareness.org/colour-blindness/types-of-colour-blindness/ "色盲的类型"  
[MDNAcceptLanguage]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Accept-Language "接受语言"
[MathiasByensLocaleDemo]: https://mathiasbynens.be/demo/locale "与区域设置相关的代码示例"
[MDNCookiePath]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie#Directives

[crbug963183]: https://crbug.com/963183 "问题963183： DevTools 不符合 WCAG"  
[crbug1003700]: https://crbug.com/1003700 "问题1003700：为颜色远景缺陷模拟添加 DevTools 支持"  
[crbug1011679]: https://crbug.com/1011679 "问题1011679：使用 "命令" 菜单引入 "停靠到左侧""  
[crbug1016501]: https://crbug.com/1016501 "问题1016501：功能请求：用于删除所有本地替代的按钮"  
[crbug1050999]: https://crbug.com/1050999 "问题1050999： "属性" 选项卡"  
[crbug1051466]: https://crbug.com/1051466 "问题1051466：在 DevTools 中支持合作基金/COEP 调试"  
[crbug1054447]: https://crbug.com/1054447 "问题1054447：在 DevTools 时间线中更新性能指标"  
[crbug1051822]: https://crbug.com/1051822 "问题1051822： DevTools：将 UI 添加到仿真区域设置"
[crbug1041830]: https://crbug.com/1041830 "问题1041830：改善断点颜色"
[crbug1050855]: https://crbug.com/1050855 "问题1050855：设置视图难以发现"
[crbug1056348]: https://crbug.com/1056348 "问题1056348：信息栏组件刷新"

[COOP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.tu4hyy6v12wn "合作基金和 COEP 解释-跨起源 Opener 政策"  
[COEP]: https://docs.google.com/document/d/1zDlfvfTJ_9e8Jdc8ehuV4zMEu9ySMCiTGMS9y0GU92k/edit#bookmark=id.uo6kivyh0ge2 "合作基金和 COEP 解释-跨起源 Embedder 政策"  

[GithubGoogleChromeLighthouse]: https://github.com/GoogleChrome/lighthouse "Lighthouse GitHub 存储库"  

> [!NOTE]
> <span data-ttu-id="79a75-293">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="79a75-293">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="79a75-294">原始页面位于[此处](https://developers.google.com/web/updates/2020/03/devtools/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="79a75-294">The original page is found [here](https://developers.google.com/web/updates/2020/03/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="79a75-296">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="79a75-296">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
