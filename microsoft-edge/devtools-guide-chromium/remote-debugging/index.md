---
description: Android 设备上从 Windows 或 macOS 计算机远程调试实时内容。
title: 远程调试 Android 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f1ed7c698f588bb4e438d1b85a0cd0d1aba42647
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993497"
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

# <span data-ttu-id="5b4c8-104">远程调试 Android 设备入门</span><span class="sxs-lookup"><span data-stu-id="5b4c8-104">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="5b4c8-105">在 Android 设备上从 Windows 或 macOS 计算机远程调试实时内容。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-105">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="5b4c8-106">以下教程页面教你如何完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-106">The following tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="5b4c8-107">设置 Android 设备以进行远程调试，并从开发计算机中发现它。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-107">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="5b4c8-108">从开发计算机检查和调试 Android 设备上的实时内容。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-108">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="5b4c8-109">将 Android 设备中的内容说明截屏视频到开发计算机上的 DevTools 实例。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-109">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> <span data-ttu-id="5b4c8-110">远程调试目前不支持 iOS 设备上的 Microsoft Edge 应用。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-110">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span></span>  <span data-ttu-id="5b4c8-111">以下指南专门针对 Android 设备上的远程调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-111">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span></span>
> <span data-ttu-id="5b4c8-112">如果你有 macOS 设备，请按照 [Brightcove 调试指南][BrightcoveSupportDebuggingMobileDevices] 操作，以使用 Safari 在 iOS 设备上远程调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-112">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span></span>  <span data-ttu-id="5b4c8-113">有关 Safari 中的 Web 检查器工具的详细信息，请参阅 [Safari Web 开发工具][AppleDeveloperSafariTools]。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-113">For more information about the Web Inspector tool in Safari, see [Safari Web Development Tools][AppleDeveloperSafariTools].</span></span>  

## <span data-ttu-id="5b4c8-114">步骤1：发现 Android 设备</span><span class="sxs-lookup"><span data-stu-id="5b4c8-114">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="5b4c8-115">下面的工作流适用于大多数用户。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-115">The workflow below works for most users.</span></span>  <span data-ttu-id="5b4c8-116">有关更多帮助，请参阅 [疑难解答： DevTools 未检测到 Android 设备](#troubleshooting-devtools-is-not-detecting-the-android-device) 部分。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-116">For more help, see the [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span></span>  

1.  <span data-ttu-id="5b4c8-117">打开 Android 上的 " **开发工具选项** " 屏幕。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-117">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="5b4c8-118">有关详细信息，请参阅 [配置设备上的开发人员选项][AndroidDeveloperStudioDevOptions]。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-118">For more information, see [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span></span>  
1.  <span data-ttu-id="5b4c8-119">选择 " **启用 USB 调试**"。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-119">Select **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="5b4c8-120">在开发计算机上，打开 "Microsoft Edge"。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-120">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="5b4c8-121">导航到 `edge://inspect` Microsoft Edge 中的页面。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-121">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="5b4c8-123">图 1.</span><span class="sxs-lookup"><span data-stu-id="5b4c8-123">Figure 1.</span></span>  <span data-ttu-id="5b4c8-124">`edge://inspect`Microsoft Edge 中的页面</span><span class="sxs-lookup"><span data-stu-id="5b4c8-124">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5b4c8-125">使用 USB 电缆将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-125">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="5b4c8-126">第一次尝试连接时，通常会看到有关检测未知设备的 DevTools 的提示。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-126">The first time you try to connect, you usually see prompt about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="5b4c8-127">接受 Android 设备上的 " **允许 USB 调试** " 权限提示。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-127">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="5b4c8-129">图 2.</span><span class="sxs-lookup"><span data-stu-id="5b4c8-129">Figure 2.</span></span>  <span data-ttu-id="5b4c8-130">Android 设备上的 " **允许 USB 调试** " 权限提示</span><span class="sxs-lookup"><span data-stu-id="5b4c8-130">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5b4c8-131">如果你看到 Android 设备的模型名称，则 Microsoft Edge 已成功建立与你的设备的连接。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-131">If you see the model name of your Android device, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="5b4c8-132">转到 " [步骤 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) " 部分。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-132">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <span data-ttu-id="5b4c8-133">疑难解答： DevTools 未检测到 Android 设备</span><span class="sxs-lookup"><span data-stu-id="5b4c8-133">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="5b4c8-134">使用以下提示来帮助你解决硬件的正确设置。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-134">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="5b4c8-135">如果您使用的是 USB 集线器，请尝试将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-135">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="5b4c8-136">尝试在 Android 设备和开发计算机之间拔出 USB 电缆，然后重新插入 USB 电缆。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-136">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="5b4c8-137">在 Android 和开发计算机屏幕解除锁定时完成任务。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-137">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="5b4c8-138">请确保您的 USB 电缆正常工作。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-138">Make sure that your USB cable works.</span></span>  <span data-ttu-id="5b4c8-139">你应该能够从开发计算机检查 Android 设备上的文件。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-139">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="5b4c8-140">使用以下提示来帮助验证软件是否设置正确。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-140">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="5b4c8-141">如果开发计算机运行的是 Windows，请尝试手动安装 Android 设备的 USB 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-141">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="5b4c8-142">有关详细信息，请参阅 [安装 OEM USB 驱动程序][AndroidDeveloperToolsOemUsb]。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-142">For more information, see [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span></span>  
*   <span data-ttu-id="5b4c8-143">某些 Windows 和 Android 设备的组合 \ (特别是 Samsung \ ) 需要其他设置。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-143">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="5b4c8-144">有关详细信息，请参阅 [DevTools 设备在接通电源时不检测设备][Stackoverflow21925992]。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-144">For more information, see [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span></span>  

<span data-ttu-id="5b4c8-145">使用以下提示可帮助你解决在 Android 设备上不能看到 " **允许 USB 调试** " 提示。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-145">Use the following tips to help you troubleshoot not seeing the **Allow USB Debugging** prompt on your Android device.</span></span>  

*   <span data-ttu-id="5b4c8-146">断开连接并重新连接 USB 电缆的同时，DevTools 将集中在开发计算机上，并且显示 Android 主屏幕。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-146">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5b4c8-147">如果您的 Android 或开发计算机屏幕被锁定，您可能看不到提示。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-147">You may not see the prompt if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="5b4c8-148">更新 Android 设备和开发计算机的显示设置，以便每个设备都不会进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-148">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="5b4c8-149">将 Android 的 USB 模式设置为 PTP。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-149">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="5b4c8-150">有关详细信息，请参阅 [Galaxy S4 不显示 "授权 USB 调试" 对话框][StackexchangeAndroid101933]。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-150">For more information, see [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span></span>  
*   <span data-ttu-id="5b4c8-151">从 Android 设备上的 "**开发工具选项**" 屏幕中选择 "**撤消 USB 调试授权**"，将其重置为新状态。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-151">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="5b4c8-152">如果您发现此页面或 DevTools 设备上未提及的解决方案在堆栈溢出 [时未检测到设备][Stackoverflow21925992] ，请将您的解决方案添加到堆栈溢出问题</span><span class="sxs-lookup"><span data-stu-id="5b4c8-152">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="5b4c8-153">!</span><span class="sxs-lookup"><span data-stu-id="5b4c8-153">!</span></span>  

## <span data-ttu-id="5b4c8-154">步骤2：从开发计算机调试 Android 设备上的内容</span><span class="sxs-lookup"><span data-stu-id="5b4c8-154">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="5b4c8-155">在 Android 设备上打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-155">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="5b4c8-156">在 `edge://inspect` 页面中，你将看到 Android 设备的型号名称，后跟设备序列号。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-156">From the `edge://inspect` page, you see the model name of your Android device, followed by the device serial number.</span></span>  <span data-ttu-id="5b4c8-157">在此下方，你应该看到在设备上运行的 Microsoft Edge 版本，其中版本号位于括号中。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-157">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span></span>  <span data-ttu-id="5b4c8-158">每个打开的 Microsoft Edge 选项卡都将获取一个唯一的分区。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-158">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="5b4c8-159">你可以从分区与该选项卡进行交互。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-159">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="5b4c8-161">图 3.</span><span class="sxs-lookup"><span data-stu-id="5b4c8-161">Figure 3.</span></span>  <span data-ttu-id="5b4c8-162">已连接的远程设备</span><span class="sxs-lookup"><span data-stu-id="5b4c8-162">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5b4c8-163">在 " **打开包含 url 的选项卡** " 框中，输入 url，然后选择 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-163">In the **Open tab with url** text box, enter a URL and then select **Open**.</span></span>  <span data-ttu-id="5b4c8-164">页面将在 Android 设备上的新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-164">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="5b4c8-165">选择您刚刚打开的 URL 旁边的 " **检查** "。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-165">Select **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="5b4c8-166">将打开一个新的 DevTools 实例。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-166">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <span data-ttu-id="5b4c8-167">更多操作：焦点、重新加载或关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="5b4c8-167">More actions: focus, reload, or close a tab</span></span>  

<span data-ttu-id="5b4c8-168">选择要关注、重新加载或关闭的选项卡旁边的 " **焦点" 选项卡**、" **重新加载**" 或 " **关闭** "。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-168">Select **focus tab**, **reload**, or **close** next to the tab that you want to focus, reload, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="5b4c8-170">图 4.</span><span class="sxs-lookup"><span data-stu-id="5b4c8-170">Figure 4.</span></span>  <span data-ttu-id="5b4c8-171">用于聚焦、重新加载或关闭选项卡的按钮</span><span class="sxs-lookup"><span data-stu-id="5b4c8-171">The buttons for focusing, reloading, or closing a tab</span></span>  
:::image-end:::  

### <span data-ttu-id="5b4c8-172">检查元素</span><span class="sxs-lookup"><span data-stu-id="5b4c8-172">Inspect elements</span></span>  

<span data-ttu-id="5b4c8-173">转到 DevTools 实例的 " **元素** " 面板，将鼠标悬停在某个元素上，将其突出显示在 Android 设备的视口中。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-173">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="5b4c8-174">您也可以在 Android 设备屏幕上选择一个元素，以便在 " **元素** " 面板中选择该元素。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-174">You may also select an element on your Android device screen to select it in the **Elements** panel.</span></span>  <span data-ttu-id="5b4c8-175">选择**Select Element** ![ DevTools 实例上的 "选择元素" ][ImageSelectElementIcon] 图标，然后在 Android 设备屏幕上选择该元素。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-175">Select **Select Element** ![Select Element][ImageSelectElementIcon] icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="5b4c8-176">选择第一个选项后，"**选择元素**" 已禁用，因此必须在每次使用该功能时重新启用它。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-176">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <span data-ttu-id="5b4c8-177">将 Android 屏幕说明截屏视频到开发计算机</span><span class="sxs-lookup"><span data-stu-id="5b4c8-177">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="5b4c8-178">选择 " **切换说明截屏视频** ![ 切换 ][ImageToggleScreencastIcon] " 说明截屏视频图标可在 DevTools 实例中查看 Android 设备的内容。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-178">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="5b4c8-179">你可以通过以下方式与说明截屏视频交互。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-179">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="5b4c8-180">单击被转换为点击，在设备上触发正确的触摸事件。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-180">Clicks are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="5b4c8-181">将计算机上的击键发送到设备。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-181">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="5b4c8-182">若要模拟捏出的手势，请 `Shift` 在拖动时按住。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-182">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="5b4c8-183">若要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针投掷。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-183">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="5b4c8-184">使用以下提示可帮助您说明截屏视频。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-184">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="5b4c8-185">Screencasts 仅显示页面内容。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-185">Screencasts only display page content.</span></span>  <span data-ttu-id="5b4c8-186">说明截屏视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-186">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="5b4c8-187">Screencasts 会对帧速率产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-187">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="5b4c8-188">在测量滚动或动画时禁用 screencasting，以便更准确地了解页面性能。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-188">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="5b4c8-189">如果你的 Android 设备屏幕锁定，你的说明截屏视频的内容将消失。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-189">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="5b4c8-190">解锁 Android 设备屏幕以自动恢复说明截屏视频。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-190">Unlock your Android device screen to automatically resume the screencast.</span></span>  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "配置设备上的开发人员选项 |Android 开发人员"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序 |Android 开发人员"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 开发工具 |Apple 开发人员"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "在移动设备上调试 |Brightcove 支持"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb-Android 发烧友式堆栈交换"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "插入堆栈内溢时，DevTools 设备不检测设备"  

> [!NOTE]
> <span data-ttu-id="5b4c8-197">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-197">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5b4c8-198">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-198">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5b4c8-200">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5b4c8-200">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
