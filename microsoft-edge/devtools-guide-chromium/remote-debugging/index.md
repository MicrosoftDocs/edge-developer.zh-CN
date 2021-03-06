---
description: 从 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。
title: 远程调试 Android 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 61fad793ca03dbef68a5f769dbfd25e780fd9930
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398257"
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

# <a name="get-started-with-remote-debugging-android-devices"></a><span data-ttu-id="38cb5-104">远程调试 Android 设备入门</span><span class="sxs-lookup"><span data-stu-id="38cb5-104">Get started with remote debugging Android devices</span></span>  

<span data-ttu-id="38cb5-105">从 Windows 或 macOS 计算机在 Android 设备上远程调试实时内容。</span><span class="sxs-lookup"><span data-stu-id="38cb5-105">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="38cb5-106">以下教程页面将指导你如何完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="38cb5-106">The following tutorial page teaches you how to complete the following actions.</span></span>  

*   <span data-ttu-id="38cb5-107">设置 Android 设备进行远程调试，然后从开发计算机中发现它。</span><span class="sxs-lookup"><span data-stu-id="38cb5-107">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="38cb5-108">从开发计算机检查和调试 Android 设备上的实时内容。</span><span class="sxs-lookup"><span data-stu-id="38cb5-108">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="38cb5-109">将 Android 设备中的内容屏蔽到开发计算机上 DevTools 实例。</span><span class="sxs-lookup"><span data-stu-id="38cb5-109">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--  
:::image type="complex" source="../media/remote-debugging--remote-debugging.msft.png" alt-text="Remote Debugging lets you inspect a page running on an Android device from your development machine" lightbox="../media/remote-debugging--remote-debugging.msft.png":::
   old Figure 1.  Remote Debugging lets you inspect a page running on an Android device from your development machine  
:::image-end:::  
-->  

> [!NOTE]
> <span data-ttu-id="38cb5-110">目前不支持在 iOS 设备上远程调试 Microsoft Edge 应用。</span><span class="sxs-lookup"><span data-stu-id="38cb5-110">Remote debugging the Microsoft Edge app on iOS devices is not currently supported.</span></span>  <span data-ttu-id="38cb5-111">以下指南专门侧重于在 Android 设备上远程调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="38cb5-111">The following guide is specifically focused on remote debugging Microsoft Edge on Android devices.</span></span>
> <span data-ttu-id="38cb5-112">如果你有 macOS 设备，请按照 [Brightcove 调试][BrightcoveSupportDebuggingMobileDevices] 指南使用 Safari 在 iOS 设备上远程调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="38cb5-112">If you have a macOS device, follow the [Brightcove Debugging guide][BrightcoveSupportDebuggingMobileDevices] to remotely debug Microsoft Edge on an iOS device using Safari.</span></span>  <span data-ttu-id="38cb5-113">有关 Safari 中的 Web 检查器工具详细信息，请导航到 [Safari Web 开发工具][AppleDeveloperSafariTools]。</span><span class="sxs-lookup"><span data-stu-id="38cb5-113">For more information about the Web Inspector tool in Safari, navigate to [Safari Web Development Tools][AppleDeveloperSafariTools].</span></span>  

## <a name="step-1-discover-your-android-device"></a><span data-ttu-id="38cb5-114">步骤 1：发现 Android 设备</span><span class="sxs-lookup"><span data-stu-id="38cb5-114">Step 1: Discover your Android device</span></span>  

<span data-ttu-id="38cb5-115">下面的工作流适用于大多数用户。</span><span class="sxs-lookup"><span data-stu-id="38cb5-115">The workflow below works for most users.</span></span>  <span data-ttu-id="38cb5-116">若要获得更多帮助，请导航到 ["疑难解答：DevTools](#troubleshooting-devtools-is-not-detecting-the-android-device) 未检测 Android 设备"部分。</span><span class="sxs-lookup"><span data-stu-id="38cb5-116">For more help, navigate to [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) section.</span></span>  

1.  <span data-ttu-id="38cb5-117">在 Android **上** 打开"开发人员选项"屏幕。</span><span class="sxs-lookup"><span data-stu-id="38cb5-117">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="38cb5-118">有关详细信息，请导航到["配置设备上的开发人员选项"。][AndroidDeveloperStudioDevOptions]</span><span class="sxs-lookup"><span data-stu-id="38cb5-118">For more information, navigate to [Configure On-Device Developer Options][AndroidDeveloperStudioDevOptions].</span></span>  
1.  <span data-ttu-id="38cb5-119">选择 **"启用 USB 调试"。**</span><span class="sxs-lookup"><span data-stu-id="38cb5-119">Choose **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="38cb5-120">在开发计算机上，打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="38cb5-120">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="38cb5-121">导航到 `edge://inspect` Microsoft Edge 中的页面。</span><span class="sxs-lookup"><span data-stu-id="38cb5-121">Navigate to the `edge://inspect` page in Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-no-targets.msft.png" alt-text="Microsoft Edge edge://inspect页面" lightbox="../media/remote-debugging-edge-inspect-no-targets.msft.png":::
       <span data-ttu-id="38cb5-123">图 1.</span><span class="sxs-lookup"><span data-stu-id="38cb5-123">Figure 1.</span></span>  <span data-ttu-id="38cb5-124">`edge://inspect`Microsoft Edge 中的页面</span><span class="sxs-lookup"><span data-stu-id="38cb5-124">The `edge://inspect` page in Microsoft Edge</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38cb5-125">使用 USB 电缆将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="38cb5-125">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="38cb5-126">首次尝试连接时，应显示有关 DevTools 检测未知设备的提示。</span><span class="sxs-lookup"><span data-stu-id="38cb5-126">The first time you try to connect, a prompt should be displayed about DevTools detecting an unknown device.</span></span>  <span data-ttu-id="38cb5-127">接受 **Android 设备上的"允许 USB** 调试"权限提示。</span><span class="sxs-lookup"><span data-stu-id="38cb5-127">Accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  
    
    :::image type="complex" source="../media/remote-debugging-android-permissions-prompt.msft.png" alt-text="Android 设备上的"允许 USB 调试"权限提示" lightbox="../media/remote-debugging-android-permissions-prompt.msft.png":::
       <span data-ttu-id="38cb5-129">图 2.</span><span class="sxs-lookup"><span data-stu-id="38cb5-129">Figure 2.</span></span>  <span data-ttu-id="38cb5-130">Android **设备上的"允许 USB** 调试"权限提示</span><span class="sxs-lookup"><span data-stu-id="38cb5-130">The **Allow USB Debugging** permission prompt on an Android device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38cb5-131">如果显示 Android 设备的型号名称，则 Microsoft Edge 已成功建立与设备的连接。</span><span class="sxs-lookup"><span data-stu-id="38cb5-131">If the model name of your Android device is displayed, then Microsoft Edge has successfully established the connection to your device.</span></span>  <span data-ttu-id="38cb5-132">继续步骤 [2](#step-2-debug-content-on-your-android-device-from-your-development-machine) 部分。</span><span class="sxs-lookup"><span data-stu-id="38cb5-132">Continue to the [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine) section.</span></span>  
    
    <!--  
    :::image type="complex" source="../media/remote-debugging--unknown-device.msft.png" alt-text="The Remote Devices tab has successfully detected an unknown device that is pending authorization" lightbox="../media/remote-debugging--unknown-device.msft.png":::
       old Figure 4.  The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    :::image-end:::
    -->  
    
### <a name="troubleshooting-devtools-is-not-detecting-the-android-device"></a><span data-ttu-id="38cb5-133">疑难解答：DevTools 未检测到 Android 设备</span><span class="sxs-lookup"><span data-stu-id="38cb5-133">Troubleshooting: DevTools is not detecting the Android device</span></span>  

<span data-ttu-id="38cb5-134">使用以下提示可帮助你解决硬件的正确设置问题。</span><span class="sxs-lookup"><span data-stu-id="38cb5-134">Use the following tips to help you troubleshoot the correct settings for your hardware.</span></span>  

*   <span data-ttu-id="38cb5-135">如果你使用的是 USB 集线器，请尝试将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="38cb5-135">If you are using a USB hub, try connecting your Android device directly to your development machine.</span></span>  
*   <span data-ttu-id="38cb5-136">请尝试拔下 Android 设备和开发计算机之间的 USB 电缆，然后重新插入 USB 电缆。</span><span class="sxs-lookup"><span data-stu-id="38cb5-136">Try unplugging the USB cable between your Android device and development machine, and then re-plugging your USB cable.</span></span>  <span data-ttu-id="38cb5-137">解锁 Android 屏幕和开发计算机屏幕时完成任务。</span><span class="sxs-lookup"><span data-stu-id="38cb5-137">Complete the task while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="38cb5-138">确保 USB 电缆正常工作。</span><span class="sxs-lookup"><span data-stu-id="38cb5-138">Make sure that your USB cable works.</span></span>  <span data-ttu-id="38cb5-139">你应该能够从开发计算机检查 Android 设备上的文件。</span><span class="sxs-lookup"><span data-stu-id="38cb5-139">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="38cb5-140">使用以下提示可帮助你验证软件是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="38cb5-140">Use the following tips to help you verify that your software is set up correctly.</span></span>  

*   <span data-ttu-id="38cb5-141">如果你的开发计算机正在运行 Windows，请尝试手动为 Android 设备安装 USB 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="38cb5-141">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="38cb5-142">有关详细信息，请导航到["安装 OEM USB 驱动程序"。][AndroidDeveloperToolsOemUsb]</span><span class="sxs-lookup"><span data-stu-id="38cb5-142">For more information, navigate to [Install OEM USB Drivers][AndroidDeveloperToolsOemUsb].</span></span>  
*   <span data-ttu-id="38cb5-143">Windows 和 Android 设备的一些组合 \ (特别是 Samsung\) 需要额外的设置。</span><span class="sxs-lookup"><span data-stu-id="38cb5-143">Some combinations of Windows and Android devices \(especially Samsung\) require additional settings.</span></span>  <span data-ttu-id="38cb5-144">有关详细信息，请导航到 [DevTools 设备在插入时检测设备][Stackoverflow21925992]。</span><span class="sxs-lookup"><span data-stu-id="38cb5-144">For more information, navigate to [DevTools Devices does not detect device when plugged in][Stackoverflow21925992].</span></span>  

<span data-ttu-id="38cb5-145">如果你的 Android 设备上未显示"允许 **USB** 调试"提示，请使用以下提示来帮助你排除故障。</span><span class="sxs-lookup"><span data-stu-id="38cb5-145">Use the following tips to help you troubleshoot if the **Allow USB Debugging** prompt is not displayed on your Android device.</span></span>  

*   <span data-ttu-id="38cb5-146">断开 USB 电缆的连接，然后重新连接 U 盘，同时 DevTools 专注于开发计算机，并且 Android 主屏幕显示。</span><span class="sxs-lookup"><span data-stu-id="38cb5-146">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="38cb5-147">如果 Android 或开发计算机屏幕已锁定，则显示提示。</span><span class="sxs-lookup"><span data-stu-id="38cb5-147">The prompt is displayed if your Android or development machine screens are locked.</span></span>  

*   <span data-ttu-id="38cb5-148">更新 Android 设备和开发计算机显示设置，以便每个设备从不进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="38cb5-148">Updating the display settings for your Android device and development machine so that each never goes to sleep.</span></span>  
*   <span data-ttu-id="38cb5-149">将 Android 的 USB 模式设置为 PTP。</span><span class="sxs-lookup"><span data-stu-id="38cb5-149">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="38cb5-150">有关详细信息，请导航到 ["开发公司 S4"不会显示"授权 USB 调试"对话框][StackexchangeAndroid101933]。</span><span class="sxs-lookup"><span data-stu-id="38cb5-150">For more information, navigate to [Galaxy S4 does not show Authorize USB debugging dialog box][StackexchangeAndroid101933].</span></span>  
*   <span data-ttu-id="38cb5-151">Choose **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span><span class="sxs-lookup"><span data-stu-id="38cb5-151">Choose **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="38cb5-152">如果发现此页或 [DevTools 设备][Stackoverflow21925992] 未在 Stack Overflow 上插入时检测到设备的解决方案，请将你的解决方案添加到 Stack Overflow 问题</span><span class="sxs-lookup"><span data-stu-id="38cb5-152">If you find a solution that is not mentioned on this page or in [DevTools Devices does not detect device when plugged in][Stackoverflow21925992] on Stack Overflow, please add your solution to the Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="38cb5-153">.</span><span class="sxs-lookup"><span data-stu-id="38cb5-153">.</span></span>  

## <a name="step-2-debug-content-on-your-android-device-from-your-development-machine"></a><span data-ttu-id="38cb5-154">步骤 2：从开发计算机调试 Android 设备上的内容</span><span class="sxs-lookup"><span data-stu-id="38cb5-154">Step 2: Debug content on your Android device from your development machine</span></span>  

1.  <span data-ttu-id="38cb5-155">在 Android 设备上打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="38cb5-155">Open Microsoft Edge on your Android device.</span></span>  
1.  <span data-ttu-id="38cb5-156">导航到 ，将显示 Android 设备的型号名称，后 `edge://inspect` 跟设备序列号。</span><span class="sxs-lookup"><span data-stu-id="38cb5-156">Navigate to `edge://inspect`, the model name of your Android device is displayed, followed by the device serial number.</span></span>  <span data-ttu-id="38cb5-157">在下面，应显示设备上运行的 Microsoft Edge 版本，括号中显示版本号。</span><span class="sxs-lookup"><span data-stu-id="38cb5-157">Below that, the version of Microsoft Edge running on the device should be displayed, with the version number in parentheses.</span></span>  <span data-ttu-id="38cb5-158">每个打开的 Microsoft Edge 选项卡获取一个唯一部分。</span><span class="sxs-lookup"><span data-stu-id="38cb5-158">Each open Microsoft Edge tab gets a unique section.</span></span>  <span data-ttu-id="38cb5-159">You may interact with that tab from a section.</span><span class="sxs-lookup"><span data-stu-id="38cb5-159">You may interact with that tab from a section.</span></span>  <!--If there are any apps using WebView, a section for each of those apps should be displayed, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->  
    
    :::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets.msft.png" alt-text="连接的远程设备" lightbox="../media/remote-debugging-edge-inspect-with-targets.msft.png":::
       <span data-ttu-id="38cb5-161">图 3.</span><span class="sxs-lookup"><span data-stu-id="38cb5-161">Figure 3.</span></span>  <span data-ttu-id="38cb5-162">连接的远程设备</span><span class="sxs-lookup"><span data-stu-id="38cb5-162">A connected remote device</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38cb5-163">在**包含 URL 文本框的"打开**"选项卡中，输入 URL，然后选择"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="38cb5-163">In the **Open tab with url** text box, enter a URL and then choose **Open**.</span></span>  <span data-ttu-id="38cb5-164">该页面将在 Android 设备上的新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="38cb5-164">The page opens in a new tab on your Android device.</span></span>  
1.  <span data-ttu-id="38cb5-165">选择 **刚** 打开的 URL 旁边的"检查"。</span><span class="sxs-lookup"><span data-stu-id="38cb5-165">Choose **inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="38cb5-166">将打开一个新的 DevTools 实例。</span><span class="sxs-lookup"><span data-stu-id="38cb5-166">A new DevTools instance opens.</span></span>  

<!-- The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.  
    So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.   -->

### <a name="more-actions-focus-refresh-or-close-a-tab"></a><span data-ttu-id="38cb5-167">更多操作：焦点、刷新或关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="38cb5-167">More actions: focus, refresh, or close a tab</span></span>  

<span data-ttu-id="38cb5-168">选择**焦点选项卡\*\*\*\*、重新加载\*\*\*\*或关闭**要对焦、刷新或关闭的选项卡旁边的选项卡。</span><span class="sxs-lookup"><span data-stu-id="38cb5-168">Choose **focus tab**, **reload**, or **close** next to the tab that you want to focus, refresh, or close.</span></span>  

:::image type="complex" source="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png" alt-text="用于焦点、刷新或关闭选项卡的按钮" lightbox="../media/remote-debugging-edge-inspect-with-targets-buttons.msft.png":::
   <span data-ttu-id="38cb5-170">图 4.</span><span class="sxs-lookup"><span data-stu-id="38cb5-170">Figure 4.</span></span>  <span data-ttu-id="38cb5-171">用于焦点、刷新或关闭选项卡的按钮</span><span class="sxs-lookup"><span data-stu-id="38cb5-171">The buttons for focusing, refreshing, or closing a tab</span></span>  
:::image-end:::  

### <a name="inspect-elements"></a><span data-ttu-id="38cb5-172">检查元素</span><span class="sxs-lookup"><span data-stu-id="38cb5-172">Inspect elements</span></span>  

<span data-ttu-id="38cb5-173">导航到\*\*\*\* DevTools 实例的元素工具，将鼠标悬停在某个元素上以在 Android 设备的视口中突出显示它。</span><span class="sxs-lookup"><span data-stu-id="38cb5-173">Navigate to the **Elements** tool of your DevTools instance, and hover on an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="38cb5-174">还可以在 Android 设备屏幕上选择一个元素，以在"元素"工具 **中选择** 它。</span><span class="sxs-lookup"><span data-stu-id="38cb5-174">You may also select an element on your Android device screen to select it in the **Elements** tool.</span></span>  <span data-ttu-id="38cb5-175">在\*\*\*\* ![ DevTools (选择元素 \) 图标，然后选择 ][ImageSelectElementIcon] Android 设备屏幕上的元素。</span><span class="sxs-lookup"><span data-stu-id="38cb5-175">Choose **Select Element** \(![Select Element][ImageSelectElementIcon]\) icon on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="38cb5-176">**Select 元素** 在首次选择后被禁用，因此每次想要使用该功能时都必须重新启用它。</span><span class="sxs-lookup"><span data-stu-id="38cb5-176">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use the feature.</span></span>  

### <a name="screencast-your-android-screen-to-your-development-machine"></a><span data-ttu-id="38cb5-177">将 Android 屏幕屏蔽到开发计算机</span><span class="sxs-lookup"><span data-stu-id="38cb5-177">Screencast your Android screen to your development machine</span></span>  

<span data-ttu-id="38cb5-178">Choose **Toggle Screencast** \ (![ Toggle Screencast \) icon to view the content of your Android device in your ][ImageToggleScreencastIcon] DevTools instance.</span><span class="sxs-lookup"><span data-stu-id="38cb5-178">Choose **Toggle Screencast** \(![Toggle Screencast][ImageToggleScreencastIcon]\) icon to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="38cb5-179">你能够通过以下方式与屏幕视频进行交互。</span><span class="sxs-lookup"><span data-stu-id="38cb5-179">You are able to interact with the screencast in the following ways.</span></span>  

*   <span data-ttu-id="38cb5-180">选择将转换为点击，在设备上触发正确的触摸事件。</span><span class="sxs-lookup"><span data-stu-id="38cb5-180">Chooses are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="38cb5-181">将计算机上键击发送到设备。</span><span class="sxs-lookup"><span data-stu-id="38cb5-181">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="38cb5-182">若要模拟收缩手势，请按住 `Shift` 拖动。</span><span class="sxs-lookup"><span data-stu-id="38cb5-182">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="38cb5-183">若要滚动，请使用跟踪板或鼠标滚轮，或与鼠标指针一起跳。</span><span class="sxs-lookup"><span data-stu-id="38cb5-183">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

> [!NOTE]
> <span data-ttu-id="38cb5-184">使用以下提示帮助你进行屏幕广播。</span><span class="sxs-lookup"><span data-stu-id="38cb5-184">Use the following tips to help you screencast.</span></span>  
> 
> *   <span data-ttu-id="38cb5-185">屏幕视频仅显示页面内容。</span><span class="sxs-lookup"><span data-stu-id="38cb5-185">Screencasts only display page content.</span></span>  <span data-ttu-id="38cb5-186">屏幕视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。</span><span class="sxs-lookup"><span data-stu-id="38cb5-186">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
> *   <span data-ttu-id="38cb5-187">屏幕视频会对帧速率产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="38cb5-187">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="38cb5-188">在测量滚动或动画时禁用屏幕视频，以获得页面性能的更准确图片。</span><span class="sxs-lookup"><span data-stu-id="38cb5-188">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
> *   <span data-ttu-id="38cb5-189">如果你的 Android 设备屏幕锁定，屏幕视频的内容将消失。</span><span class="sxs-lookup"><span data-stu-id="38cb5-189">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="38cb5-190">解锁 Android 设备屏幕以自动恢复屏幕视频。</span><span class="sxs-lookup"><span data-stu-id="38cb5-190">Unlock your Android device screen to automatically resume the screencast.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="38cb5-191">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="38cb5-191">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!-- links -->  

[AndroidDeveloperStudioDevOptions]: https://developer.android.com/studio/debug/dev-options "配置设备上的开发人员选项|Android 开发人员"  
[AndroidDeveloperToolsOemUsb]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序|Android 开发人员"  

[AppleDeveloperSafariTools]: https://developer.apple.com/safari/tools "Safari Web 开发工具|Apple 开发人员"  

[BrightcoveSupportDebuggingMobileDevices]: https://support.brightcove.com/debugging-mobile-devices "在移动设备上调试|Brightcove 支持"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  

[StackexchangeAndroid101933]: https://android.stackexchange.com/questions/101933 "adb - Android Enthusiast Stack Exchange"  

[Stackoverflow21925992]: https://stackoverflow.com/questions/21925992 "DevTools 设备在插入时不检测设备 - Stack Overflow"  

> [!NOTE]
> <span data-ttu-id="38cb5-198">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="38cb5-198">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="38cb5-199">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="38cb5-199">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="38cb5-201">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="38cb5-201">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
