---
description: 从 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。
title: Android 设备远程调试入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: 2beab5bf6d4b58dc93d883f5114e168213053e84
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439563"
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

# <a name="get-started-with-remote-debugging-android-devices"></a><span data-ttu-id="e9e50-104">Android 设备远程调试入门</span><span class="sxs-lookup"><span data-stu-id="e9e50-104">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="e9e50-105">从你的 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。</span><span class="sxs-lookup"><span data-stu-id="e9e50-105">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="e9e50-106">下面的教程页面指导你如何完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="e9e50-106">The following tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="e9e50-107">设置 Android 设备进行远程调试，然后从开发计算机中发现。</span><span class="sxs-lookup"><span data-stu-id="e9e50-107">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="e9e50-108">在开发设备上检查和调试 Android 设备上的实时内容。</span><span class="sxs-lookup"><span data-stu-id="e9e50-108">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="e9e50-109">将 Android 设备中的内容截屏到开发计算机上的开发工具实例上。</span><span class="sxs-lookup"><span data-stu-id="e9e50-109">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> <span data-ttu-id="e9e50-110">当前不支持在 iOS 设备上远程调试 Microsoft Edge 应用程序。 </span><span class="sxs-lookup"><span data-stu-id="e9e50-110">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span></span>  <span data-ttu-id="e9e50-111">以下指南专门针对 Android 设备上的 Microsoft Edge 进行远程调试。</span><span class="sxs-lookup"><span data-stu-id="e9e50-111">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span></span>
> <span data-ttu-id="e9e50-112">如果使用的是 macOS 设备，请按照 [Brightcove 调试指南][BrightcoveSupportDebuggingMobileDevices]使用 Safari 在 iOS 设备上远程调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e9e50-112">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span></span>  <span data-ttu-id="e9e50-113">有关 Safari 中的 Web 检查器工具的更多信息，请导航至 [Safari Web 开发工具][AppleDeveloperSafariTools]。</span><span class="sxs-lookup"><span data-stu-id="e9e50-113">For more information about the Web Inspector tool in Safari, navigate to [Safari Web Development Tools][AppleDeveloperSafariTools].</span></span>  

## <a name="step-1-discover-your-android-device"></a><span data-ttu-id="e9e50-114">步骤 1：发现 Android 设备</span><span class="sxs-lookup"><span data-stu-id="e9e50-114">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="e9e50-115">下面的工作流适用于大多数用户。</span><span class="sxs-lookup"><span data-stu-id="e9e50-115">The workflow below works for most users.</span></span>  <span data-ttu-id="e9e50-116">有关更多帮助信息，请导航至[疑难解答：DevTools 未检测 Android 设备](#troubleshooting-devtools-is-not-detecting-the-android-device)一节。</span><span class="sxs-lookup"><span data-stu-id="e9e50-116">For more help, navigate to [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span></span>  

1.  <span data-ttu-id="e9e50-117">打开 Android 上的“**开发人员选项**”屏幕。</span><span class="sxs-lookup"><span data-stu-id="e9e50-117">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="e9e50-118">有关更多信息，请导航至[配置设备上开发人员选项][AndroidDeveloperStudioDevOptions]。</span><span class="sxs-lookup"><span data-stu-id="e9e50-118">For more information, navigate to [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span></span>  
1.  <span data-ttu-id="e9e50-119">选择“**启用 USB 调试**”。</span><span class="sxs-lookup"><span data-stu-id="e9e50-119">Choose **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="e9e50-120">在开发计算机上，打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e9e50-120">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="e9e50-121">导航到 Microsoft Edge 中的 `edge://inspect` 页面。</span><span class="sxs-lookup"><span data-stu-id="e9e50-121">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge 中的 edge://inspect 页面" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="e9e50-123">图 1.</span><span class="sxs-lookup"><span data-stu-id="e9e50-123">Figure 1.</span></span>  <span data-ttu-id="e9e50-124">Microsoft Edge 中的 `edge://inspect` 页面</span><span class="sxs-lookup"><span data-stu-id="e9e50-124">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e9e50-125">使用 USB 电缆将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="e9e50-125">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="e9e50-126">首次尝试连接时，将显示有关开发工具检测未知设备的提示。</span><span class="sxs-lookup"><span data-stu-id="e9e50-126">The first time you try to connect, a prompt should be displayed about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="e9e50-127">在 Android 设备上接受“**允许 USB 调试**”权限提示。</span><span class="sxs-lookup"><span data-stu-id="e9e50-127">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android 设备上的“允许 USB 调试”权限提示" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="e9e50-129">图 2.</span><span class="sxs-lookup"><span data-stu-id="e9e50-129">Figure 2.</span></span>  <span data-ttu-id="e9e50-130">Android 设备上的“**允许 USB 调试**”权限提示</span><span class="sxs-lookup"><span data-stu-id="e9e50-130">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e9e50-131">如果显示 Android 设备的型号名称，则 Microsoft Edge 已成功与设备建立连接。</span><span class="sxs-lookup"><span data-stu-id="e9e50-131">If the model name of your Android device is displayed, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="e9e50-132">继续[第 2 步](#step-2-debug-content-on-your-android-device-from-your-development-machine)部分。</span><span class="sxs-lookup"><span data-stu-id="e9e50-132">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <a name="troubleshooting-devtools-is-not-detecting-the-android-device"></a><span data-ttu-id="e9e50-133">疑难解答：DevTools 未检测 Android 设备</span><span class="sxs-lookup"><span data-stu-id="e9e50-133">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="e9e50-134">使用以下提示可帮助你对硬件的正确设置进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="e9e50-134">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="e9e50-135">如果使用 USB 集线器，尝试将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="e9e50-135">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="e9e50-136">尝试拔下 Android 设备与开发机器之间的 USB 电缆，然后重新插入 USB 电缆。</span><span class="sxs-lookup"><span data-stu-id="e9e50-136">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="e9e50-137">解锁 Android 和开发计算机屏幕时完成任务。</span><span class="sxs-lookup"><span data-stu-id="e9e50-137">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="e9e50-138">确保 USB 电缆正常工作。</span><span class="sxs-lookup"><span data-stu-id="e9e50-138">Make sure that your USB cable works.</span></span>  <span data-ttu-id="e9e50-139">应该能够在开发计算机上检查 Android 设备上的文件。</span><span class="sxs-lookup"><span data-stu-id="e9e50-139">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="e9e50-140">使用以下提示可帮助你验证软件是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="e9e50-140">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="e9e50-141">如果你的开发计算机运行的是 Windows，请尝试手动为 Android 设备安装 USB 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e9e50-141">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="e9e50-142">有关详细信息，请导航到[安装 OEM USB 驱动程序][AndroidDeveloperToolsOemUsb]。</span><span class="sxs-lookup"><span data-stu-id="e9e50-142">For more information, navigate to [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span></span>  
*   <span data-ttu-id="e9e50-143">Windows 和 Android 设备\(尤其是 Samsung \)的某些组合需要其他设置。</span><span class="sxs-lookup"><span data-stu-id="e9e50-143">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="e9e50-144">有关详细信息，请导航到[插入时开发工具设备无法检测到设备。][Stackoverflow21925992]</span><span class="sxs-lookup"><span data-stu-id="e9e50-144">For more information, navigate to [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span></span>  

<span data-ttu-id="e9e50-145">如果 Android 设备上未显示“**允许 USB 调试**”提示，请使用以下提示来帮助你排除故障。</span><span class="sxs-lookup"><span data-stu-id="e9e50-145">Use the following tips to help you troubleshoot if the **Allow USB Debugging** prompt is not displayed on your Android device.</span></span>  

*   <span data-ttu-id="e9e50-146">开发工具专注于开发计算机并且显示 Android 主屏幕时，断开 USB 电缆连接，然后重新连接。</span><span class="sxs-lookup"><span data-stu-id="e9e50-146">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e9e50-147">如果 Android 或开发计算机屏幕已锁定，则显示提示。</span><span class="sxs-lookup"><span data-stu-id="e9e50-147">The prompt is displayed if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="e9e50-148">更新 Android 设备和开发机的显示设置，以使每台设备都不会进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="e9e50-148">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="e9e50-149">将 Android 的 USB 模式设置为 PTP。</span><span class="sxs-lookup"><span data-stu-id="e9e50-149">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="e9e50-150">有关更多信息，请导航至 [Galaxy S4 不显示“授权 USB 调试”对话框][StackexchangeAndroid101933]。</span><span class="sxs-lookup"><span data-stu-id="e9e50-150">For more information, navigate to [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span></span>  
*   <span data-ttu-id="e9e50-151">从 Android 设备上的“**开发人员选项**”屏幕上选择“**撤销 USB 调试授权**”，以将其重置为新状态。</span><span class="sxs-lookup"><span data-stu-id="e9e50-151">Choose **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="e9e50-152">如果找到未在本页面或堆栈溢出的[插入时开发工具设备无法检测到设备][Stackoverflow21925992]上提及的解决方案，请将解决方案添加到堆栈溢出问题</span><span class="sxs-lookup"><span data-stu-id="e9e50-152">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="e9e50-153">.</span><span class="sxs-lookup"><span data-stu-id="e9e50-153">.</span></span>  

## <a name="step-2-debug-content-on-your-android-device-from-your-development-machine"></a><span data-ttu-id="e9e50-154">步骤 2：从开发计算机调试 Android 设备上的内容</span><span class="sxs-lookup"><span data-stu-id="e9e50-154">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="e9e50-155">在 Android 设备上打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e9e50-155">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="e9e50-156">导航到 `edge://inspect` ，将显示 Android 设备的型号名称，后跟设备序列号。</span><span class="sxs-lookup"><span data-stu-id="e9e50-156">Navigate to `edge://inspect`, the model name of your Android device is displayed, followed by the device serial number.</span></span>  <span data-ttu-id="e9e50-157">在下面，应显示设备上运行的 Microsoft Edge 版本，括号中会显示版本号。</span><span class="sxs-lookup"><span data-stu-id="e9e50-157">Below that, the version of Microsoft Edge running on the device should be displayed, with the version number in parentheses.</span></span>  <span data-ttu-id="e9e50-158">每个打开的 Microsoft Edge 选项卡获取一个唯一部分。</span><span class="sxs-lookup"><span data-stu-id="e9e50-158">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="e9e50-159">可以从一个部分中与该选项卡进行交互。</span><span class="sxs-lookup"><span data-stu-id="e9e50-159">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="连接的远程设备" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="e9e50-161">图 3.</span><span class="sxs-lookup"><span data-stu-id="e9e50-161">Figure 3.</span></span>  <span data-ttu-id="e9e50-162">连接的远程设备</span><span class="sxs-lookup"><span data-stu-id="e9e50-162">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e9e50-163">在“**使用 URL 打开选项卡 **“文本框中，输入 URL 并选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="e9e50-163">In the **Open tab with url** text box, enter a URL and then choose **Open**.</span></span>  <span data-ttu-id="e9e50-164">该页面将在 Android 设备上的新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="e9e50-164">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="e9e50-165">选择刚打开 URL 旁边的“**检查**”。</span><span class="sxs-lookup"><span data-stu-id="e9e50-165">Choose **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="e9e50-166">新的开发工具实例打开。</span><span class="sxs-lookup"><span data-stu-id="e9e50-166">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <a name="more-actions-focus-refresh-or-close-a-tab"></a><span data-ttu-id="e9e50-167">更多操作：聚焦、刷新或关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="e9e50-167">More actions: focus, refresh, or close a tab</span></span>  

<span data-ttu-id="e9e50-168">在要聚焦、刷新或关闭的选项卡旁边，选择“**聚焦选项卡**”、“**重新加载**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="e9e50-168">Choose **focus tab**, **reload**, or **close** next to the tab that you want to focus, refresh, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="用于聚焦、刷新或关闭选项卡的按钮" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="e9e50-170">图 4.</span><span class="sxs-lookup"><span data-stu-id="e9e50-170">Figure 4.</span></span>  <span data-ttu-id="e9e50-171">用于聚焦、刷新或关闭选项卡的按钮</span><span class="sxs-lookup"><span data-stu-id="e9e50-171">The buttons for focusing, refreshing, or closing a tab</span></span>  
:::image-end:::  

### <a name="inspect-elements"></a><span data-ttu-id="e9e50-172">检查元素</span><span class="sxs-lookup"><span data-stu-id="e9e50-172">Inspect elements</span></span>  

<span data-ttu-id="e9e50-173">导航到开发工具实例的“**元素**”工具，然后将鼠标悬停在某个元素上以在 Android 设备的视口中突出显示。</span><span class="sxs-lookup"><span data-stu-id="e9e50-173">Navigate to the **Elements** tool of your DevTools instance, and hover on an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="e9e50-174">还可以在 Android 设备屏幕上选择一个元素，然后在“元素 ”工具中将其选中。</span><span class="sxs-lookup"><span data-stu-id="e9e50-174">You may also select an element on your Android device screen to select it in the **Elements** tool.</span></span>  <span data-ttu-id="e9e50-175">选择开发工具实例中“**选择元素**” \(![选择元素](../media/select-element-icon.msft.png)\)图标，然后在 Android 设备屏幕上选择元素。</span><span class="sxs-lookup"><span data-stu-id="e9e50-175">Choose **Select Element** \(![Select Element](../media/select-element-icon.msft.png)\) icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="e9e50-176">第一次选择后将禁用“ 选择元素”，因此每次使用功能时都必须重新启用。</span><span class="sxs-lookup"><span data-stu-id="e9e50-176">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <a name="screencast-your-android-screen-to-your-development-machine"></a><span data-ttu-id="e9e50-177">将 Android 屏幕截屏到开发计算机</span><span class="sxs-lookup"><span data-stu-id="e9e50-177">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="e9e50-178">选择“**切换截屏视频**” \(![切换截屏视频](../media/toggle-screencast-icon.msft.png)\) 图标可在开发工具实例中查看 Android 设备的内容。</span><span class="sxs-lookup"><span data-stu-id="e9e50-178">Choose **Toggle Screencast** \(![Toggle Screencast](../media/toggle-screencast-icon.msft.png)\) icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="e9e50-179">可以通过以下方式与截屏视频进行交互。</span><span class="sxs-lookup"><span data-stu-id="e9e50-179">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="e9e50-180">选择将转换为点击，在设备上触发适当的触摸事件。</span><span class="sxs-lookup"><span data-stu-id="e9e50-180">Chooses are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="e9e50-181">计算机上的击键会发送到设备。</span><span class="sxs-lookup"><span data-stu-id="e9e50-181">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="e9e50-182">若要模拟收缩手势，拖动时按住 `Shift`。</span><span class="sxs-lookup"><span data-stu-id="e9e50-182">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="e9e50-183">如果要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针拖动。</span><span class="sxs-lookup"><span data-stu-id="e9e50-183">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="e9e50-184">使用以下提示来帮助你进行截屏。</span><span class="sxs-lookup"><span data-stu-id="e9e50-184">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="e9e50-185">截屏视频仅显示页面内容。</span><span class="sxs-lookup"><span data-stu-id="e9e50-185">Screencasts only display page content.</span></span>  <span data-ttu-id="e9e50-186">截屏视频的透明部分表示设备界面，例如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。</span><span class="sxs-lookup"><span data-stu-id="e9e50-186">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="e9e50-187">截屏视频会对帧速率产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="e9e50-187">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="e9e50-188">在测量滚动或动画时禁用截屏视频，以更准确地了解页面性能。</span><span class="sxs-lookup"><span data-stu-id="e9e50-188">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="e9e50-189">如果 Android 设备屏幕锁定，截屏视频的内容将消失。</span><span class="sxs-lookup"><span data-stu-id="e9e50-189">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="e9e50-190">解锁 Android 设备屏幕以自动恢复截屏视频。</span><span class="sxs-lookup"><span data-stu-id="e9e50-190">Unlock your Android device screen to automatically resume the screencast.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e9e50-191">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="e9e50-191">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "配置设备上开发人员选项 | Android 开发人员"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序 | Android 开发人员"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 开发工具| Apple 开发人员"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "在移动设备上调试 | Brightcove 支持"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android Enthusiast Stack Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "插入时开发工具设备无法检测到设备 - 堆栈溢出"  

> [!NOTE]
> <span data-ttu-id="e9e50-198">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e9e50-198">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e9e50-199">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="e9e50-199">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e9e50-201">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e9e50-201">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
