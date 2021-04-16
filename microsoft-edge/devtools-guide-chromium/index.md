---
description: 了解 Microsoft Edge \(Chromium\) 开发人员工具。
title: Microsoft Edge （Chromium） 开发人员工具概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 3d91b0754f84579d770940503cf4a252e3926416
ms.sourcegitcommit: fa8bedfc83fbd1c4ce7bda8c69586c4f24007beb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11481393"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a><span data-ttu-id="932be-104">Microsoft Edge （Chromium） 开发人员工具概述</span><span class="sxs-lookup"><span data-stu-id="932be-104">Microsoft Edge (Chromium) Developer Tools overview</span></span>  

<span data-ttu-id="932be-105">安装 Microsoft Edge 时，将获取浏览器。</span><span class="sxs-lookup"><span data-stu-id="932be-105">When you install Microsoft Edge, you get a browser.</span></span> <span data-ttu-id="932be-106">此外，您还可以获得检查、调试甚至创建 Web 项目的强大方法。</span><span class="sxs-lookup"><span data-stu-id="932be-106">Also, you get a powerful way to inspect, debug, and even create web projects.</span></span>  <span data-ttu-id="932be-107">浏览器附带的开发人员工具基于 Chromium 开放源代码项目中的工具，因此您可能已经熟悉这些工具。</span><span class="sxs-lookup"><span data-stu-id="932be-107">The Developer Tools shipped with the browser are based on the tools in the Chromium open-source project, so you may already be familiar with the tools.</span></span>  <span data-ttu-id="932be-108">若要使本文中的说明保持简短， `Microsoft Edge Developer Tools` 现在称为 `DevTools` 。</span><span class="sxs-lookup"><span data-stu-id="932be-108">To keep descriptions shorter in this article, the `Microsoft Edge Developer Tools` are now referred to as `DevTools` .</span></span>  

<span data-ttu-id="932be-109">使用 DevTools 查看并了解有关以下开发任务有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="932be-109">Use DevTools to review and learn more about the following development tasks.</span></span>  

*   <span data-ttu-id="932be-110">[检查并更改浏览器中的当前][DevtoolsGuideDomIndex] 网页。</span><span class="sxs-lookup"><span data-stu-id="932be-110">[Inspect and change the current webpage][DevtoolsGuideDomIndex] live in the browser.</span></span>  
*   <span data-ttu-id="932be-111">[模拟产品在不同设备上的行为方式，][DevtoolsGuideDeviceModeIndex] 并模拟具有不同网络条件的移动环境。</span><span class="sxs-lookup"><span data-stu-id="932be-111">[Emulate how your product behaves on different devices][DevtoolsGuideDeviceModeIndex] and simulate a mobile environment complete with different network conditions.</span></span>  
*   <span data-ttu-id="932be-112">[使用具有可视界面的][DevtoolsGuideInspectStylesEditFonts] 实时工具检查、调整和更改网页中元素的样式。</span><span class="sxs-lookup"><span data-stu-id="932be-112">[Inspect, tweak, and change the styles of elements][DevtoolsGuideInspectStylesEditFonts] in the webpage using live tools with a visual interface.</span></span>  
*   <span data-ttu-id="932be-113">[使用断][DevtoolsGuideJavascriptIndex]点调试和实时控制台 调试[JavaScript。][DevtoolsGuideConsoleIndex]</span><span class="sxs-lookup"><span data-stu-id="932be-113">[Debug your JavaScript][DevtoolsGuideJavascriptIndex] using breakpoint debugging and with the [live console][DevtoolsGuideConsoleIndex].</span></span>  
*   <span data-ttu-id="932be-114">在 [产品中查找][DevtoolsGuideIssuesIndex] 辅助功能、性能、兼容性和安全问题，并了解如何使用 DevTools 修复每个问题。</span><span class="sxs-lookup"><span data-stu-id="932be-114">Find [accessibility, performance, compatibility, and security issues][DevtoolsGuideIssuesIndex] in your products and learn how to use DevTools to fix each.</span></span>  
*   <span data-ttu-id="932be-115">[检查网络流量][DevtoolsGuideNetworkIndex] 并查看问题的位置。</span><span class="sxs-lookup"><span data-stu-id="932be-115">[Inspect the network traffic][DevtoolsGuideNetworkIndex] and review the location of the problems.</span></span>  
*   <span data-ttu-id="932be-116">[检查浏览器以不同格式存储][DevtoolsGuideStorageSessionstorage] 内容的位置。</span><span class="sxs-lookup"><span data-stu-id="932be-116">[Inspect where the browser stored content][DevtoolsGuideStorageSessionstorage] in various formats.</span></span>  
*   <span data-ttu-id="932be-117">[评估产品][DevtoolsGuideEvaluatePerformanceIndex]的性能，以查找[内存问题和][DevtoolsGuideMemoryProblemsIndex][呈现问题][DevtoolsGuideRenderingToolsIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-117">[Evaluate the performance][DevtoolsGuideEvaluatePerformanceIndex] of your product to find [memory problems][DevtoolsGuideMemoryProblemsIndex] and [rendering issues][DevtoolsGuideRenderingToolsIndex].</span></span>  
*   <span data-ttu-id="932be-118">[使用开发环境将][DevtoolsGuideSourcesIndex] [DevTools][DevtoolsGuideWorkspacesIndex] 中的更改与文件系统同步， [并覆盖 Web][DevtoolsGuideJavascriptOverrides] 中的文件。</span><span class="sxs-lookup"><span data-stu-id="932be-118">[Use a development environment][DevtoolsGuideSourcesIndex] to [sync changes in DevTools with the file system][DevtoolsGuideWorkspacesIndex] and [override files][DevtoolsGuideJavascriptOverrides] from the web.</span></span>  
    
<!-- Is the link meant to be local or session storage for "inspect where the browser stored content"? -->  

<span data-ttu-id="932be-119">以及更多功能。</span><span class="sxs-lookup"><span data-stu-id="932be-119">And a lot more.</span></span>  <span data-ttu-id="932be-120">当你打开 DevTools 并根据需要自定义每个工具时，这一切将开始。</span><span class="sxs-lookup"><span data-stu-id="932be-120">It all starts when you open DevTools and customize each tool to your needs.</span></span>  

## <a name="open-the-devtools"></a><span data-ttu-id="932be-121">打开 DevTools</span><span class="sxs-lookup"><span data-stu-id="932be-121">Open the DevTools</span></span>  

<span data-ttu-id="932be-122">若要打开和浏览 DevTools，请使用以下任一操作。</span><span class="sxs-lookup"><span data-stu-id="932be-122">To open and explore the DevTools, use one any of the following actions.</span></span>  

*   <span data-ttu-id="932be-123">将鼠标悬停在网页上的任何元素上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="932be-123">Hover on any element on the webpage, open the contextual menu \(right-click\), and then choose **Inspect**.</span></span>  <span data-ttu-id="932be-124">此操作将打开 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="932be-124">This action opens the **Elements** tool.</span></span>  
*   <span data-ttu-id="932be-125">选择 `F12`。</span><span class="sxs-lookup"><span data-stu-id="932be-125">Select `F12`.</span></span>  
*   <span data-ttu-id="932be-126">在 `Ctrl` + `Shift` + `I` Windows/Linux 或 `Command` + `Option` + `I` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="932be-126">Select `Ctrl`+`Shift`+`I` on Windows/Linux or `Command`+`Option`+`I` on macOS.</span></span>  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect.msft.png" alt-text="从任何元素上的上下文菜单中选择"检查"" lightbox="./media/devtools-intro-inspect.msft.png":::  
         <span data-ttu-id="932be-128">从 **任何元素** 上的上下文菜单中选择"检查"</span><span class="sxs-lookup"><span data-stu-id="932be-128">Choose **Inspect** from the contextual menu on any element</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect-devtools-open.png" alt-text="将打开 DevTools，并突出显示所选元素" lightbox="./media/devtools-intro-inspect-devtools-open.png":::  
         <span data-ttu-id="932be-130">将打开 DevTools，并突出显示所选元素</span><span class="sxs-lookup"><span data-stu-id="932be-130">The DevTools opens with the chosen element highlighted</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

<span data-ttu-id="932be-131">有两种主要方式可以与 DevTools 进行交互。</span><span class="sxs-lookup"><span data-stu-id="932be-131">There are two main ways to interact with the DevTools.</span></span>
*   <span data-ttu-id="932be-132">使用鼠标</span><span class="sxs-lookup"><span data-stu-id="932be-132">Use the mouse</span></span>  
*   <span data-ttu-id="932be-133">[键盘快捷方式][DevtoolsGuideShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-133">[Keyboard shortcuts][DevtoolsGuideShortcutsIndex].</span></span>  <span data-ttu-id="932be-134">键盘快捷方式提供了访问功能的快速方法，辅助功能需要这些快捷方式。</span><span class="sxs-lookup"><span data-stu-id="932be-134">Keyboard shortcuts provide a quick way to access functionality and are needed for accessibility.</span></span>  <span data-ttu-id="932be-135">Microsoft Edge DevTools 团队致力于使用键盘和辅助技术（如屏幕阅读器）提供所有工具。</span><span class="sxs-lookup"><span data-stu-id="932be-135">The Microsoft Edge DevTools team works hard to make all the tools available using the keyboard and assistive technologies such as screen readers.</span></span>  <span data-ttu-id="932be-136">若要详细了解如何在 DevTools 中打开不同功能，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsGuideOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-136">For more information about how to open the different features in the DevTools, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsGuideOpenIndex].</span></span>  

## <a name="dock-the-devtools-in-your-browser"></a><span data-ttu-id="932be-137">在浏览器中停靠 DevTools</span><span class="sxs-lookup"><span data-stu-id="932be-137">Dock the DevTools in your browser</span></span>  

<span data-ttu-id="932be-138">打开 DevTools 时，它停靠在浏览器左侧。</span><span class="sxs-lookup"><span data-stu-id="932be-138">When you open the DevTools, it docks to the left of your browser.</span></span>  <span data-ttu-id="932be-139">若要更改 DevTools 的停靠位置，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="932be-139">To change the docked location of the DevTools, complete the following actions.</span></span>  

1.  <span data-ttu-id="932be-140">选择" **自定义和控制 DevTools** \ (`...` \) "按钮。</span><span class="sxs-lookup"><span data-stu-id="932be-140">Choose the **Customize And Control DevTools** \(`...`\) button.</span></span>  
1.  <span data-ttu-id="932be-141">在相对于页面 \ (**扩展**坞端 \) 的**DevTools**的右侧，选择"扩展**坞端**"选项。</span><span class="sxs-lookup"><span data-stu-id="932be-141">To the right of **Placement of the DevTools relative to the page** \(**Dock side**\), choose a **Dock side** option.</span></span>  
    
<span data-ttu-id="932be-142">有关详细信息，请导航到"更改 Microsoft Edge DevTools [位置（"取消停靠"，"停靠到底部"，"停靠到左侧"）][DevtoolsGuideCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="932be-142">For more information, navigate to [Change Microsoft Edge DevTools placement (Undock, Dock To Bottom, Dock To Left)][DevtoolsGuideCustomizePlacement].</span></span>  

:::image type="complex" source="./media/devtools-intro-docking-menu.msft.png" alt-text="DevTools 中扩展坞侧菜单的屏幕截图" lightbox="./media/devtools-intro-docking-menu.msft.png":::  
   <span data-ttu-id="932be-144">DevTools 中扩展坞侧菜单的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="932be-144">Screenshot of the Dock side menu in DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="932be-145">在 **扩展坞端**中，选择以下任一布局选项。</span><span class="sxs-lookup"><span data-stu-id="932be-145">In **Dock side**, choose any of the following layout options.</span></span>  

*   <span data-ttu-id="932be-146">**取消停靠为单独的窗口**。</span><span class="sxs-lookup"><span data-stu-id="932be-146">**Undock into separate window**.</span></span>   <span data-ttu-id="932be-147">帮助你使用多个监视器，或者如果你需要在全屏应用上工作。</span><span class="sxs-lookup"><span data-stu-id="932be-147">Helps you work with several monitors or if you need to work on a full screen app.</span></span>  
*   <span data-ttu-id="932be-148">**扩展坞向左或\*\*\*\*扩展坞向右**。</span><span class="sxs-lookup"><span data-stu-id="932be-148">**Dock to left** or **Dock to right**.</span></span>  <span data-ttu-id="932be-149">有助于将 DevTools 与 Web 产品并排使用，并且当你模拟移动设备时，它非常出色。</span><span class="sxs-lookup"><span data-stu-id="932be-149">Helps you keep the DevTools side by side with your web product, and is excellent when you emulate mobile devices.</span></span>  <span data-ttu-id="932be-150">**停靠到左侧**，**停靠到右侧**选项与高分辨率显示效果最佳。</span><span class="sxs-lookup"><span data-stu-id="932be-150">The **Dock to left** and **Dock to right** options work best with high-resolution displays.</span></span>  <span data-ttu-id="932be-151">有关放大设备详细信息，请导航到 [Microsoft Edge DevTools 设备中的模拟][DevtoolsGuideDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-151">For more information about emulation devices, navigate to [Emulate mobile devices in Microsoft Edge DevTools][DevtoolsGuideDeviceModeIndex].</span></span>  
*   <span data-ttu-id="932be-152">**停靠到底部**。</span><span class="sxs-lookup"><span data-stu-id="932be-152">**Dock to bottom**.</span></span>  <span data-ttu-id="932be-153">当您没有足够的水平显示空间或想要在DOM或**Console**中调试长文本时，此功能将为您提供帮助。</span><span class="sxs-lookup"><span data-stu-id="932be-153">Helps you when you do not have enough horizontal display space, or you want to debug long text in the DOM or **Console**.</span></span>  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-docking-left.msft.png" alt-text="选择停靠到左侧" lightbox="./media/devtools-intro-docking-left.msft.png":::  
         <span data-ttu-id="932be-155">选择 **停靠到左侧**</span><span class="sxs-lookup"><span data-stu-id="932be-155">Choose **Dock To Left**</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-bottom.msft.png" alt-text="选择停靠到底部" lightbox="media/devtools-intro-docking-bottom.msft.png":::  
         <span data-ttu-id="932be-157">选择 **固定到底部**</span><span class="sxs-lookup"><span data-stu-id="932be-157">Choose **Dock To Bottom**</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  
:::row:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-right.msft.png" alt-text="选择"扩展坞到右侧"" lightbox="media/devtools-intro-docking-right.msft.png":::  
         <span data-ttu-id="932be-159">选择 **"扩展坞到右侧"**</span><span class="sxs-lookup"><span data-stu-id="932be-159">Choose **Dock To Right**</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-own-window.msft.png" alt-text="选择"取消停靠到单独的窗口"" lightbox="media/devtools-intro-docking-own-window.msft.png":::  
         <span data-ttu-id="932be-161">选择 **停靠到单独的窗口位置**</span><span class="sxs-lookup"><span data-stu-id="932be-161">Choose **Undock into separate window**</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="learn-about-the-core-tools"></a><span data-ttu-id="932be-162">了解核心工具</span><span class="sxs-lookup"><span data-stu-id="932be-162">Learn about the core tools</span></span>  

<span data-ttu-id="932be-163">DevTools 为您提供了一项令人惊叹的功能，可以检查、调试和更改浏览器中当前显示的 Web 产品。</span><span class="sxs-lookup"><span data-stu-id="932be-163">DevTools give you an amazing amount of power to inspect, debug, and change the web product currently displayed in the browser.</span></span>  <span data-ttu-id="932be-164">大多数工具实时显示更改。</span><span class="sxs-lookup"><span data-stu-id="932be-164">Most of the tools display the changes live.</span></span>  <span data-ttu-id="932be-165">实时更新使工具非常有用，无需刷新或生成即可优化 Web 项目的外观和导航或功能。</span><span class="sxs-lookup"><span data-stu-id="932be-165">Live updates make the tools incredibly useful to refine the appearance and navigation or functionality of a web project without the need to refresh or build it.</span></span>  <span data-ttu-id="932be-166">DevTools 还允许你更改计算机上基于 Web 的第三方产品。</span><span class="sxs-lookup"><span data-stu-id="932be-166">The DevTools also allow you to change web-based third-party products on your computer.</span></span>  

<span data-ttu-id="932be-167">DevTools 在几年内逐渐增加。</span><span class="sxs-lookup"><span data-stu-id="932be-167">DevTools grew over a period of several years.</span></span>  <span data-ttu-id="932be-168">你可能假设首次打开任何工具时很难了解 DevTools。</span><span class="sxs-lookup"><span data-stu-id="932be-168">You may assume that DevTools are difficult to learn when you first open any of tools.</span></span>  <span data-ttu-id="932be-169">以下文本快速介绍了不同的部分。</span><span class="sxs-lookup"><span data-stu-id="932be-169">The following text quickly introduces the different parts.</span></span>  <span data-ttu-id="932be-170">主工具栏为您提供了一些部分，这些部分按从左到右的顺序排序。</span><span class="sxs-lookup"><span data-stu-id="932be-170">The main toolbar offers you a few sections and the sections are ordered from left to right.</span></span>  

:::image type="complex" source="./media/devtools-intro-menu-bar.msft.png" alt-text="包含说明不同部分的标签的 DevTools 菜单栏的屏幕截图。  顺序：检查工具、设备仿真工具、"工具"选项卡组、JavaScript 错误、问题、设置、反馈、自定义和关闭。" lightbox="./media/devtools-intro-menu-bar.msft.png":::  
   <span data-ttu-id="932be-173">包含说明不同部分的标签的 DevTools 菜单栏的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="932be-173">Screenshot of the menu bar of the DevTools with labels that explain the different sections.</span></span>  <span data-ttu-id="932be-174">顺序：检查工具、设备仿真工具、"工具"选项卡组、JavaScript 错误、问题、设置、反馈、自定义和关闭。</span><span class="sxs-lookup"><span data-stu-id="932be-174">In order: Inspect Tool, Device Emulation tool, Tools tab group, JavaScript Errors, Issues, Settings, Feedback, Customize, and Close.</span></span>  
:::image-end:::  

*   <span data-ttu-id="932be-175">"检查工具"允许您选择当前网页上的某个元素。</span><span class="sxs-lookup"><span data-stu-id="932be-175">The Inspect Tool allows you to choose an element on the current webpage.</span></span>  <span data-ttu-id="932be-176">激活后，你可以将鼠标移动到网页的不同部分，以获取有关元素和颜色覆盖的详细信息以显示尺寸、填充和边距。</span><span class="sxs-lookup"><span data-stu-id="932be-176">After you activate it, you may move your mouse over different parts of the webpage to get detailed information about the element and a color overlay to display dimensions, padding, and margin.</span></span>  
    
    :::image type="complex" source="./media/devtools-intro-inspect-tool.msft.png" alt-text="具有所选文章第一个标题的检查工具的屏幕截图" lightbox="./media/devtools-intro-inspect-tool.msft.png":::  
       <span data-ttu-id="932be-178">具有所选文章第一个标题的检查工具的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="932be-178">Screenshot of the inspect tool with the first headline of this article chosen</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="932be-179">[设备仿真工具][DevtoolsGuideDeviceModeIndex]在仿真设备模式下显示当前 Web 产品。</span><span class="sxs-lookup"><span data-stu-id="932be-179">The [Device Emulation][DevtoolsGuideDeviceModeIndex] tool displays the current web product in an emulated device mode.</span></span>  <span data-ttu-id="932be-180">**设备仿真工具**允许你在调整浏览器大小时运行和测试产品的反应。</span><span class="sxs-lookup"><span data-stu-id="932be-180">The **Device Emulation** tool allows you to run and test how your product reacts when you resize the browser.</span></span>  <span data-ttu-id="932be-181">它还为你提供移动设备上的布局和行为估计。</span><span class="sxs-lookup"><span data-stu-id="932be-181">It also gives you an estimation of the layout and behavior on a mobile device.</span></span>  
    
    :::image type="complex" source="./media/devtools-intro-device-emulation.msft.png" alt-text="本文在仿真移动电话中的 DevTools 显示的屏幕截图" lightbox="./media/devtools-intro-device-emulation.msft.png":::  
       <span data-ttu-id="932be-183">本文在仿真移动电话中的 DevTools 显示的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="932be-183">Screenshot of the DevTools display of this article in an emulated mobile phone</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="932be-184">"工具"选项卡组是一组选项卡，表示在不同方案中使用的不同工具。</span><span class="sxs-lookup"><span data-stu-id="932be-184">The Tools tab group is a group of tabs that represent different tools that are used in different scenarios.</span></span>  <span data-ttu-id="932be-185">你可以自定义每个工具，并且每个工具可能会根据上下文更改。</span><span class="sxs-lookup"><span data-stu-id="932be-185">You may customize each of the tools and each tool may change based on the context.</span></span>  <span data-ttu-id="932be-186">若要打开更多工具的下拉菜单，请选择"更多 **选项卡** \ (`>>` \) "按钮。</span><span class="sxs-lookup"><span data-stu-id="932be-186">To open a dropdown menu of more tools, choose the **More tabs** \(`>>`\) button.</span></span>  <span data-ttu-id="932be-187">以下部分稍后将介绍每一种工具。</span><span class="sxs-lookup"><span data-stu-id="932be-187">Each of the tools is introduced later in the following section.</span></span>  
*   <span data-ttu-id="932be-188">"工具"选项卡组旁边是可选错误和问题快捷方式。</span><span class="sxs-lookup"><span data-stu-id="932be-188">Next to the Tools tab group are optional error and issues shortcuts.</span></span>  <span data-ttu-id="932be-189">在当前网页上出现 JavaScript 错误或问题时，会显示快捷方式。</span><span class="sxs-lookup"><span data-stu-id="932be-189">The shortcuts display when JavaScript errors or issues occur on the current webpage.</span></span>  <span data-ttu-id="932be-190">" **打开控制台以查看 # 错误，# 警告** \ (**JavaScript**错误 \) "按钮显示一个红色圆圈，后跟 `X` JavaScript 错误数。</span><span class="sxs-lookup"><span data-stu-id="932be-190">The **Open Console to view # errors, # warnings** \(**JavaScript Errors**\) button displays a red circle with an `X` followed by the number of JavaScript errors.</span></span>  <span data-ttu-id="932be-191">若要打开 [控制台并了解][DevtoolsGuideConsoleIndex] 错误，请选择 **"JavaScript 错误"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="932be-191">To open the [Console][DevtoolsGuideConsoleIndex] and learn about the error, choose the **JavaScript Errors** button.</span></span>  <span data-ttu-id="932be-192">" **要查看 # 问题的** 打开问题 \ (**问题**\) "按钮是一个蓝色消息图标，后跟问题数。</span><span class="sxs-lookup"><span data-stu-id="932be-192">The **Open Issues to view # issues** \(**Issues**\) button is a blue message icon followed by the number of issues.</span></span>  <span data-ttu-id="932be-193">若要打开"问题 ["][DevtoolsGuideIssuesIndex] 工具，请选择" **问题"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="932be-193">To open the [Issues][DevtoolsGuideIssuesIndex] tool, choose **Issues** button.</span></span>  
*   <span data-ttu-id="932be-194">" **设置** "按钮显示齿轮图标。</span><span class="sxs-lookup"><span data-stu-id="932be-194">The **Settings** button displays a gear icon.</span></span>  <span data-ttu-id="932be-195">若要打开"DevTools **设置"** 网页，请选择"设置 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="932be-195">To open DevTools **Settings** webpage, choose the **Settings** button.</span></span>  <span data-ttu-id="932be-196">" **设置** "网页显示一个菜单，用于更改 **首选项**、打开 **实验**等。</span><span class="sxs-lookup"><span data-stu-id="932be-196">The **Settings** webpage displays a menu to change **Preferences**, turn on **Experiments**, and much more.</span></span>  
*   <span data-ttu-id="932be-197">" **发送反馈** "按钮显示旁边有一个聊天气泡的 torso。</span><span class="sxs-lookup"><span data-stu-id="932be-197">The **Send Feedback** button displays torso with a chat bubble next to it.</span></span>  <span data-ttu-id="932be-198">若要打开" **发送反馈** "对话框，请选择" **发送反馈"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="932be-198">To open the **Send Feedback** dialog, choose the **Send Feedback** button.</span></span>  <span data-ttu-id="932be-199">" **发送反馈** "对话框允许你输入描述所发生情况的信息，并自动包含屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="932be-199">The **Send Feedback** dialog allows you to enter information to describe what happened and automatically includes a screenshot.</span></span>  <span data-ttu-id="932be-200">使用它与 DevTools 团队联系，以报告问题、问题或建议想法。</span><span class="sxs-lookup"><span data-stu-id="932be-200">Use it to connect with the DevTools team to report problems, issues, or suggest ideas.</span></span>  
*   <span data-ttu-id="932be-201">" **自定义和控制 Devtools** \ (`...` \) "按钮将打开一个下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="932be-201">The **Customize and control Devtools** \(`...`\) button opens a dropdown menu.</span></span>  <span data-ttu-id="932be-202">它允许你定义停靠 DevTools、搜索、打开不同工具等位置。</span><span class="sxs-lookup"><span data-stu-id="932be-202">It allows you to define where to dock the DevTools, search, open different tools, and much more.</span></span>  
    
<span data-ttu-id="932be-203">在"工具"选项卡组中，你可以打开 DevTools 中提供的不同工具。</span><span class="sxs-lookup"><span data-stu-id="932be-203">In the Tools tab group, you may open the different tools that are available in the DevTools.</span></span>  <span data-ttu-id="932be-204">以下列表介绍了 DevTools 中最常用的工具。</span><span class="sxs-lookup"><span data-stu-id="932be-204">The following list describes the most commonly used tools in the DevTools.</span></span>  

*   <span data-ttu-id="932be-205">**欢迎**。</span><span class="sxs-lookup"><span data-stu-id="932be-205">**Welcome**.</span></span>  <span data-ttu-id="932be-206">包括有关 DevTools 的新功能、如何联系团队的信息，并提供有关某些功能的信息。</span><span class="sxs-lookup"><span data-stu-id="932be-206">Includes information about the new features of DevTools, how to contact the team, and provides information about certain features.</span></span>  
*   <span data-ttu-id="932be-207">**元素**。</span><span class="sxs-lookup"><span data-stu-id="932be-207">**Elements**.</span></span>  <span data-ttu-id="932be-208">允许您编辑或检查 HTML 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="932be-208">Allows you to edit or inspect HTML and CSS.</span></span>  <span data-ttu-id="932be-209">您可以在工具中编辑这两项操作，在浏览器中实时显示更改。</span><span class="sxs-lookup"><span data-stu-id="932be-209">You may edit both in the tool and display the changes live in the browser.</span></span>  
*   <span data-ttu-id="932be-210">[控制台][DevtoolsGuideConsoleIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-210">[Console][DevtoolsGuideConsoleIndex].</span></span>  <span data-ttu-id="932be-211">允许您显示和筛选日志消息。</span><span class="sxs-lookup"><span data-stu-id="932be-211">Allows you to display and filter log messages.</span></span>  <span data-ttu-id="932be-212">日志消息是浏览器的自动日志，如网络请求和开发人员生成的日志。</span><span class="sxs-lookup"><span data-stu-id="932be-212">Log messages are automated logs of the browser like network requests and developer-generated logs.</span></span>  <span data-ttu-id="932be-213">您也可以在当前窗口或框架的上下文中直接在**控制台**中运行JavaScript。</span><span class="sxs-lookup"><span data-stu-id="932be-213">You may also run JavaScript directly in the **Console** in the context of the current window or frame.</span></span>  
*   <span data-ttu-id="932be-214">[源][DevtoolsGuideSourcesIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-214">[Sources][DevtoolsGuideSourcesIndex].</span></span>  <span data-ttu-id="932be-215">代码编辑器和 JavaScript 调试程序。</span><span class="sxs-lookup"><span data-stu-id="932be-215">A code editor and JavaScript debugger.</span></span>  <span data-ttu-id="932be-216">可以编辑项目、维护代码段和调试当前项目。</span><span class="sxs-lookup"><span data-stu-id="932be-216">You may edit projects, maintain snippets, and debug your current project.</span></span>  
*   <span data-ttu-id="932be-217">[网络][DevtoolsGuideNetworkIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-217">[Network][DevtoolsGuideNetworkIndex].</span></span>  <span data-ttu-id="932be-218">允许从网络和浏览器缓存中监视和检查请求或响应。</span><span class="sxs-lookup"><span data-stu-id="932be-218">Allows you to monitor and inspect requests or responses from the network and browser cache.</span></span>  <span data-ttu-id="932be-219">你可以筛选请求和响应以满足您的需求并模拟不同的网络条件。</span><span class="sxs-lookup"><span data-stu-id="932be-219">You may filter requests and responses to fit your needs and simulate different network conditions.</span></span>  <span data-ttu-id="932be-220">其他专用工具也可用，例如 **性能**、 **内存**、 **应用程序**、 **安全性**和 **审核**。</span><span class="sxs-lookup"><span data-stu-id="932be-220">Other specialized tools are also available, such as **Performance**, **Memory**, **Application**, **Security**, and **Audits**.</span></span>  

## <a name="power-tip-use-the-command-menu"></a><span data-ttu-id="932be-221">电源提示：使用命令菜单</span><span class="sxs-lookup"><span data-stu-id="932be-221">Power tip: Use the command menu</span></span>  

<span data-ttu-id="932be-222">DevTools 提供了许多要用于 Web 产品的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="932be-222">The DevTools provides lots of features and functionality to use with your web product.</span></span>  <span data-ttu-id="932be-223">通过多种方式访问 DevTools 的不同部分，但访问所需的功能的最快方式是使用命令菜单。</span><span class="sxs-lookup"><span data-stu-id="932be-223">Access the different parts of the DevTools in many ways, but the fastest way to access the features you need is to use the command menu.</span></span>  <span data-ttu-id="932be-224">有关详细信息，请导航到 [Microsoft Edge DevTools 命令菜单导航到"运行"][DevtoolsGuideCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-224">For more information, navigate to [Run commands with the Microsoft Edge DevTools Command menu][DevtoolsGuideCommandMenuIndex].</span></span>  <span data-ttu-id="932be-225">若要打开命令菜单，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="932be-225">To open the command menu, complete one of the following actions.</span></span>  

*   <span data-ttu-id="932be-226">选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="932be-226">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  
*   <span data-ttu-id="932be-227">Choose **Customize and Control DevTools** \ (`...` \) ， and then choose **Run Command**.</span><span class="sxs-lookup"><span data-stu-id="932be-227">Choose **Customize And Control DevTools** \(`...`\), and then choose **Run Command**.</span></span>  

:::image type="complex" source="./media/devtools-intro-command-menu.msft.png" alt-text="DevTools 中命令菜单的屏幕截图" lightbox="./media/devtools-intro-command-menu.msft.png":::  
<span data-ttu-id="932be-229">DevTools 中命令菜单的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="932be-229">Screenshot of the command menu in DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="932be-230">命令菜单允许你键入命令以在 DevTools 中显示、隐藏或运行功能。</span><span class="sxs-lookup"><span data-stu-id="932be-230">The command menu allows you to type commands to display, hide, or run features in the DevTools.</span></span>  <span data-ttu-id="932be-231">打开命令菜单后，输入 **"更改"** 一词，然后选择"**箱显示更改"。**</span><span class="sxs-lookup"><span data-stu-id="932be-231">With the command menu open, enter the word **changes**, and then choose **Drawer Show Changes**.</span></span>  <span data-ttu-id="932be-232">" **更改** 工具将在编辑 CSS 时打开，但很难在 DevTools UI 中查找。</span><span class="sxs-lookup"><span data-stu-id="932be-232">The **Changes** tool opens which is useful when you edit CSS, but is difficult to find in the DevTools UI.</span></span>  

:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-command-menu-show-changes.msft.png" alt-text="键入更改后，命令菜单将显示选项" lightbox="./media/devtools-intro-command-menu-show-changes.msft.png":::  
         <span data-ttu-id="932be-234">键入后，命令菜单将显示选项</span><span class="sxs-lookup"><span data-stu-id="932be-234">Command menu displays the options after you type</span></span> `changes`  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-showing-changes.msft.png" alt-text="打开"更改"工具的 DevTools" lightbox="./media/devtools-intro-showing-changes.msft.png":::  
         <span data-ttu-id="932be-236">打开"开发工具 **更改** 工具的 DevTools</span><span class="sxs-lookup"><span data-stu-id="932be-236">DevTools with the **Changes** tool open</span></span>  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="customize-the-devtools"></a><span data-ttu-id="932be-237">自定义 DevTools</span><span class="sxs-lookup"><span data-stu-id="932be-237">Customize the DevTools</span></span>  

<span data-ttu-id="932be-238">可自定义 DevTools 以满足你的需求或工作方式。</span><span class="sxs-lookup"><span data-stu-id="932be-238">DevTools are customizable to meet your needs or the way you work.</span></span>  <span data-ttu-id="932be-239">若要更改设置，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="932be-239">To change settings, complete one of the following actions.</span></span>  

*   <span data-ttu-id="932be-240">选择 **设置** （右上角的齿轮图标\）</span><span class="sxs-lookup"><span data-stu-id="932be-240">Choose **Settings** \(the gear icon on the top right\)</span></span>  
*   <span data-ttu-id="932be-241">选择 `F1` 或 `?`。</span><span class="sxs-lookup"><span data-stu-id="932be-241">Select `F1` or `?`.</span></span>  
    
<span data-ttu-id="932be-242">在 **首选项部分中** ，你可以更改 DevTools 的几个部分。</span><span class="sxs-lookup"><span data-stu-id="932be-242">In the **Preferences** section, you may change several parts of the DevTools.</span></span>  <span data-ttu-id="932be-243">例如，你可能使用" **与浏览器语言** 设置在 DevTools 中使用相同的语言，该语言在浏览器中使用。</span><span class="sxs-lookup"><span data-stu-id="932be-243">For example, you may use the **Match the browser language** setting to use the same language in the DevTools that is use in your browser.</span></span>  <span data-ttu-id="932be-244">有关另一个示例，请使用 **Theme** 设置更改 DevTools 的主题。</span><span class="sxs-lookup"><span data-stu-id="932be-244">For another example, use the **Theme** setting to change the theme of the DevTools.</span></span>  

:::image type="complex" source="media/devtools-intro-all-settings.msft.png" alt-text="DevTools 中所有设置的屏幕截图" lightbox="./media/devtools-intro-all-settings.msft.png":::  
   <span data-ttu-id="932be-246">DevTools 中所有设置的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="932be-246">Screenshot of all the settings in DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="932be-247">还可以更改高级功能的设置，包括以下功能。</span><span class="sxs-lookup"><span data-stu-id="932be-247">You may also change the settings of advanced features including the following features.</span></span>    

*   <span data-ttu-id="932be-248">[工作区][DevtoolsGuideWorkspacesIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-248">[Workspaces][DevtoolsGuideWorkspacesIndex].</span></span>  
*   <span data-ttu-id="932be-249">具有 **"忽略列表"** 的筛选器库代码。</span><span class="sxs-lookup"><span data-stu-id="932be-249">Filter library code with the **Ignore List**.</span></span>  
*   <span data-ttu-id="932be-250">定义 **设备** 模拟和测试模式下要包括的设备。</span><span class="sxs-lookup"><span data-stu-id="932be-250">Define the **Devices** you want to include in the device simulation and test mode.</span></span>  <span data-ttu-id="932be-251">有关详细信息，请导航到 [在Microsoft Edge DevTools中模拟移动设备][DevtoolsGuideDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-251">For more information, navigate to [Emulate mobile devices in Microsoft Edge DevTools][DevtoolsGuideDeviceModeIndex].</span></span>  
*   <span data-ttu-id="932be-252">选择网络 **限制** 配置文件。</span><span class="sxs-lookup"><span data-stu-id="932be-252">Choose a network **Throttling** profile.</span></span>  
*   <span data-ttu-id="932be-253">定义模拟 **位置**。</span><span class="sxs-lookup"><span data-stu-id="932be-253">Define simulated **Locations**.</span></span>  
*   <span data-ttu-id="932be-254">自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="932be-254">Customize keyboard shortcuts.</span></span>  <span data-ttu-id="932be-255">若要在 DevTools 和代码Visual Studio快捷方式，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="932be-255">To use the same shortcuts in the DevTools as Visual Studio Code, complete the following actions.</span></span>  
    1.  <span data-ttu-id="932be-256">从**预设中选择"匹配快捷方式"。**</span><span class="sxs-lookup"><span data-stu-id="932be-256">Choose **Match shortcuts from preset**.</span></span>  
    1.  <span data-ttu-id="932be-257">选择**Visual Studio代码"。**</span><span class="sxs-lookup"><span data-stu-id="932be-257">Choose **Visual Studio Code**.</span></span>  
        
    :::image type="complex" source="./media/devtools-intro-match-keys.msft.png" alt-text="所有键盘快捷方式和菜单的屏幕截图，这些快捷方式与代码中的快捷方式Visual Studio匹配" lightbox="./media/devtools-intro-match-keys.msft.png":::  
       <span data-ttu-id="932be-259">所有键盘快捷方式和菜单的屏幕截图，这些快捷方式与代码中的快捷方式Visual Studio匹配</span><span class="sxs-lookup"><span data-stu-id="932be-259">Screenshot of all the keyboard shortcuts and the menu to match each to the shortcuts in Visual Studio Code</span></span>  
    :::image-end:::  
    
## <a name="try-experimental-features"></a><span data-ttu-id="932be-260">试用实验功能</span><span class="sxs-lookup"><span data-stu-id="932be-260">Try experimental features</span></span>  

<span data-ttu-id="932be-261">DevTools 团队在 DevTools 中提供新功能作为实验。</span><span class="sxs-lookup"><span data-stu-id="932be-261">The DevTools team provides new features as experiments in the DevTools.</span></span>  <span data-ttu-id="932be-262">若要获取完整列表，请导航到 DevTools **设置**，然后选择**实验**。</span><span class="sxs-lookup"><span data-stu-id="932be-262">To get the full list of experiments, navigate to the DevTools **Settings**, and then choose **Experiments**.</span></span>  <span data-ttu-id="932be-263">你可以打开或关闭每个实验。</span><span class="sxs-lookup"><span data-stu-id="932be-263">You may turn each of the experiments on or off.</span></span>  <span data-ttu-id="932be-264">帮助确定哪一个实验对你有价值。</span><span class="sxs-lookup"><span data-stu-id="932be-264">Help decide which one of the experiments is valuable to you.</span></span>  <span data-ttu-id="932be-265">有关详细信息，请导航到[实验功能][DevtoolsGuideExperimentalFeaturesIndex]。</span><span class="sxs-lookup"><span data-stu-id="932be-265">For more information on the experiments, navigate to [Experimental features][DevtoolsGuideExperimentalFeaturesIndex].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="932be-266">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="932be-266">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<span data-ttu-id="932be-267">如果你想要 [预览即将向 DevTools][DevtoolsGuideWhatsNew202102Devtools]提供的最新功能，请下载 [Microsoft Edge Canary][MicrosoftedgeinsiderDownload]，它内部版本为晚上。</span><span class="sxs-lookup"><span data-stu-id="932be-267">If you want to preview the [latest features coming to the DevTools][DevtoolsGuideWhatsNew202102Devtools], download [Microsoft Edge Canary][MicrosoftedgeinsiderDownload], which builds nightly.</span></span>  

## <a name="see-also"></a><span data-ttu-id="932be-268">另请参阅</span><span class="sxs-lookup"><span data-stu-id="932be-268">See also</span></span>  

*   [<span data-ttu-id="932be-269">DevtoolsGuide for Beginners：HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="932be-269">DevtoolsGuide for Beginners: Get Started with HTML and the DOM</span></span>][DevtoolsGuideBeginnersHtml]  
*   [<span data-ttu-id="932be-270">Microsoft Edge (Chromium) DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="932be-270">Microsoft Edge (Chromium) DevTools Protocol</span></span>][DevtoolsProtocolIndex]  
    
<!-- links -->  

[DevtoolsGuideBeginnersHtml]: ./beginners/html.md "适合初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsGuideCommandMenuIndex]: ./command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsGuideConsoleIndex]: ./console/index.md "控制台概述 | Microsoft Docs"  
[DevtoolsGuideCustomizePlacement]: ./customize/placement.md "更改 Microsoft Edge DevTools 位置（撤消停靠、停靠到底部、停靠到左侧）|Microsoft Docs"  
[DevtoolsGuideDeviceModeIndex]: ./device-mode/index.md "在 Microsoft Edge 开发人员工具中模拟移动设备 | Microsoft Docs"  
[DevtoolsGuideDomIndex]: ./dom/index.md "查看和更改 CSS 入门 | Microsoft 文档 | Microsoft Docs"  
[DevtoolsGuideEvaluatePerformanceIndex]: ./evaluate-performance/index.md "开始分析运行时性能|Microsoft Docs"  
[DevtoolsGuideExperimentalFeaturesIndex]: ./experimental-features/index.md "试验功能 | Microsoft Docs"  
[DevtoolsGuideMemoryProblemsIndex]: ./memory-problems/index.md "修复内存问题|Microsoft Docs"  
[DevtoolsGuideInspectStylesEditFonts]: ./inspect-styles/edit-fonts.md "在&quot;样式&quot;窗格中编辑 CSS 字体样式|Microsoft Docs"  
[DevtoolsGuideIssuesIndex]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsGuideJavascriptIndex]: ./javascript/index.md "在 Microsoft Edge 开发人员工具中调试 JavaScript 入门 | Microsoft Docs"  
[DevtoolsGuideJavascriptOverrides]: ./javascript/overrides.md "使用 Microsoft Edge DevTools 应用替代具有本地副本的网页|Microsoft Docs"  
[DevtoolsGuideNetworkIndex]: ./network/index.md "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsGuideOpenIndex]: ./open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsGuideRenderingToolsIndex]: ./rendering-tools/index.md "分析运行时性能|Microsoft Docs"  
[DevtoolsGuideShortcutsIndex]: ./shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  
[DevtoolsGuideSourcesIndex]: ./sources/index.md "源工具概述 | Microsoft Docs"  
[DevtoolsGuideStorageSessionstorage]: ./storage/sessionstorage.md "使用 Microsoft Edge DevTools 工具查看和编辑|Microsoft Docs"  
[DevtoolsGuideWhatsNew202102Devtools]: ./whats-new/2021/02/devtools.md "DevTools （Microsoft Edge 90） 中的新增功能|Microsoft Docs"  
[DevtoolsGuideWorkspacesIndex]: ./workspaces/index.md "使用工作区列表编辑|Microsoft Docs"  
[DevtoolsProtocolIndex]: ../devtools-protocol-chromium/index.md "Microsoft Edge （Chromium） DevTools 协议概述|Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展|Chrome Web Store"  
