---
title: 远程调试 Android 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a9002ca82e6e0dcaf7f174b336e5c640929a561b
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611817"
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




<!--
<style>
.devtools-inline {
  max-height: 1em;
  vertical-align: middle;
}
</style>
-->  
# <span data-ttu-id="f1549-103">远程调试 Android 设备入门</span><span class="sxs-lookup"><span data-stu-id="f1549-103">Get Started with Remote Debugging Android Devices</span></span>   



<span data-ttu-id="f1549-104">在 Android 设备上从 Windows 或 macOS 计算机远程调试实时内容。</span><span class="sxs-lookup"><span data-stu-id="f1549-104">Remote debug live content on an Android device from your Windows or macOS computer.</span></span>  <span data-ttu-id="f1549-105">本教程将指导你如何：</span><span class="sxs-lookup"><span data-stu-id="f1549-105">This tutorial teaches you how to:</span></span>  

*   <span data-ttu-id="f1549-106">设置 Android 设备以进行远程调试，并从开发计算机中发现它。</span><span class="sxs-lookup"><span data-stu-id="f1549-106">Set up your Android device for remote debugging, and discover it from your development machine.</span></span>  
*   <span data-ttu-id="f1549-107">从开发计算机检查和调试 Android 设备上的实时内容。</span><span class="sxs-lookup"><span data-stu-id="f1549-107">Inspect and debug live content on your Android device from your development machine.</span></span>  
*   <span data-ttu-id="f1549-108">将 Android 设备中的内容说明截屏视频到开发计算机上的 DevTools 实例。</span><span class="sxs-lookup"><span data-stu-id="f1549-108">Screencast content from your Android device onto a DevTools instance on your development machine.</span></span>  

<!--
> ##### Figure 1  
> Remote Debugging lets you inspect a page running on an Android device from your development machine  
> ![Remote Debugging lets you inspect a page running on an Android device from your development machine][ImageRemoteDebugging]  -->

## <span data-ttu-id="f1549-109">步骤1：发现 Android 设备</span><span class="sxs-lookup"><span data-stu-id="f1549-109">Step 1: Discover your Android device</span></span>   

<span data-ttu-id="f1549-110">下面的工作流适用于大多数用户。</span><span class="sxs-lookup"><span data-stu-id="f1549-110">The workflow below works for most users.</span></span>  <span data-ttu-id="f1549-111">请参阅[疑难解答： DevTools 未检测到 Android 设备](#troubleshooting-devtools-is-not-detecting-the-android-device)，获取更多帮助。</span><span class="sxs-lookup"><span data-stu-id="f1549-111">See [Troubleshooting: DevTools is not detecting the Android device](#troubleshooting-devtools-is-not-detecting-the-android-device) for more help.</span></span>  

1.  <span data-ttu-id="f1549-112">打开 Android 上的 "**开发工具选项**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="f1549-112">Open the **Developer Options** screen on your Android.</span></span>  <span data-ttu-id="f1549-113">请参阅[配置设备上的开发人员选项](https://developer.android.com/studio/debug/dev-options.html)。</span><span class="sxs-lookup"><span data-stu-id="f1549-113">See [Configure On-Device Developer Options](https://developer.android.com/studio/debug/dev-options.html).</span></span>  
1.  <span data-ttu-id="f1549-114">选择 "**启用 USB 调试**"。</span><span class="sxs-lookup"><span data-stu-id="f1549-114">Select **Enable USB Debugging**.</span></span>  
1.  <span data-ttu-id="f1549-115">在开发计算机上，打开 "Microsoft Edge"。</span><span class="sxs-lookup"><span data-stu-id="f1549-115">On your development machine, open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="f1549-116">[打开 DevTools][DevToolsOpen]。</span><span class="sxs-lookup"><span data-stu-id="f1549-116">[Open DevTools][DevToolsOpen].</span></span>  
1.  <span data-ttu-id="f1549-117">在 DevTools 中，选择**主菜单**， `...` 然后选择 "**更多工具**  >  **远程设备**"。</span><span class="sxs-lookup"><span data-stu-id="f1549-117">In DevTools, select the **Main Menu** `...` then select **More tools** > **Remote devices**.</span></span>  
    
    > ##### <span data-ttu-id="f1549-118">图 1</span><span class="sxs-lookup"><span data-stu-id="f1549-118">Figure 1</span></span>  
    > <span data-ttu-id="f1549-119">通过**主菜单**打开 "**远程设备**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f1549-119">Opening the **Remote Devices** tab via the **Main Menu**</span></span>  
    > <span data-ttu-id="f1549-120">![通过主菜单打开 "远程设备" 选项卡][ImageOpenRemoteDevices]</span><span class="sxs-lookup"><span data-stu-id="f1549-120">![Opening the Remote Devices tab via the Main Menu][ImageOpenRemoteDevices]</span></span>  

1.  <span data-ttu-id="f1549-121">在 DevTools 中，打开 "**设置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f1549-121">In DevTools, open the **Settings** tab.</span></span>  

1.  <span data-ttu-id="f1549-122">请确保 "**发现 USB 设备**" 复选框已启用。</span><span class="sxs-lookup"><span data-stu-id="f1549-122">Make sure that the **Discover USB devices** checkbox is enabled.</span></span>  
    
    > ##### <span data-ttu-id="f1549-123">图 2</span><span class="sxs-lookup"><span data-stu-id="f1549-123">Figure 2</span></span>  
    > <span data-ttu-id="f1549-124">"**发现 USB 设备**" 复选框已启用</span><span class="sxs-lookup"><span data-stu-id="f1549-124">The **Discover USB Devices** checkbox is enabled</span></span>  
    > <span data-ttu-id="f1549-125">![已启用 "发现 USB 设备" 复选框][ImageDiscoverUSBDevices]</span><span class="sxs-lookup"><span data-stu-id="f1549-125">![The Discover USB Devices checkbox is enabled][ImageDiscoverUSBDevices]</span></span>  

1.  <span data-ttu-id="f1549-126">使用 USB 电缆将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="f1549-126">Connect your Android device directly to your development machine using a USB cable.</span></span>  <span data-ttu-id="f1549-127">第一次执行此操作时，通常会看到 DevTools 检测到未知设备。</span><span class="sxs-lookup"><span data-stu-id="f1549-127">The first time you do this, you usually see that DevTools has detected an unknown device.</span></span>  <span data-ttu-id="f1549-128">如果你看到一个绿点和**连接**到 Android 设备的模型名称下方的文本，则 DevTools 已成功建立与你的设备的连接。</span><span class="sxs-lookup"><span data-stu-id="f1549-128">If you see a green dot and the text **Connected** below the model name of your Android device, then DevTools has successfully established the connection to your device.</span></span>  <span data-ttu-id="f1549-129">继续执行[步骤 2](#step-2-debug-content-on-your-android-device-from-your-development-machine)。</span><span class="sxs-lookup"><span data-stu-id="f1549-129">Continue to [Step 2](#step-2-debug-content-on-your-android-device-from-your-development-machine).</span></span>  
    <!--
    > ##### Figure 4  
    > The **Remote Devices** tab has successfully detected an unknown device that is pending authorization  
    > ![The Remote Devices tab has successfully detected an unknown device that is pending authorization][ImageUnknownDevice]  -->

1.  <span data-ttu-id="f1549-130">如果你的设备显示为 "**未知**"，请在 Android 设备上接受 "**允许 USB 调试**" 权限提示。</span><span class="sxs-lookup"><span data-stu-id="f1549-130">If your device is showing up as **Unknown**, accept the **Allow USB Debugging** permission prompt on your Android device.</span></span>  

### <span data-ttu-id="f1549-131">疑难解答： DevTools 未检测到 Android 设备</span><span class="sxs-lookup"><span data-stu-id="f1549-131">Troubleshooting: DevTools is not detecting the Android device</span></span>   

<span data-ttu-id="f1549-132">请确保您的硬件设置正确：</span><span class="sxs-lookup"><span data-stu-id="f1549-132">Make sure that your hardware is set up correctly:</span></span>  

*   <span data-ttu-id="f1549-133">如果您使用的是 USB 集线器，请尝试将 Android 设备直接连接到开发计算机。</span><span class="sxs-lookup"><span data-stu-id="f1549-133">If you are using a USB hub, try connecting your Android device directly to your development machine instead.</span></span>  
*   <span data-ttu-id="f1549-134">尝试在 Android 设备和开发计算机之间拔出 USB 电缆，然后重新插入。</span><span class="sxs-lookup"><span data-stu-id="f1549-134">Try unplugging the USB cable between your Android device and development machine, and then plugging it back in.</span></span>  <span data-ttu-id="f1549-135">在 Android 和开发计算机屏幕解锁时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f1549-135">Do it while your Android and development machine screens are unlocked.</span></span>  
*   <span data-ttu-id="f1549-136">请确保您的 USB 电缆正常工作。</span><span class="sxs-lookup"><span data-stu-id="f1549-136">Make sure that your USB cable works.</span></span>  <span data-ttu-id="f1549-137">你应该能够从开发计算机检查 Android 设备上的文件。</span><span class="sxs-lookup"><span data-stu-id="f1549-137">You should be able to inspect files on your Android device from your development machine.</span></span>  

<span data-ttu-id="f1549-138">请确保您的软件设置正确：</span><span class="sxs-lookup"><span data-stu-id="f1549-138">Make sure that your software is set up correctly:</span></span>  

*   <span data-ttu-id="f1549-139">如果开发计算机运行的是 Windows，请尝试手动安装 Android 设备的 USB 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="f1549-139">If your development machine is running Windows, try manually installing the USB drivers for your Android device.</span></span>  <span data-ttu-id="f1549-140">请参阅[安装 OEM USB 驱动程序][AndroidUSBDrivers]。</span><span class="sxs-lookup"><span data-stu-id="f1549-140">See [Install OEM USB Drivers][AndroidUSBDrivers].</span></span>  
    
*   <span data-ttu-id="f1549-141">某些 Windows 和 Android 设备（特别是 Samsung）的组合需要额外设置。</span><span class="sxs-lookup"><span data-stu-id="f1549-141">Some combinations of Windows and Android devices (especially Samsung) require extra set up.</span></span>  <span data-ttu-id="f1549-142">请参阅 [DevTools 设备插入时不检测设备] [StackOverflowDevicesNotDetected]。</span><span class="sxs-lookup"><span data-stu-id="f1549-142">See [DevTools Devices does not detect device when plugged in][StackOverflowDevicesNotDetected].</span></span>  
    
<span data-ttu-id="f1549-143">如果您在 Android 设备上看不到 "**允许 USB 调试**" 提示，请尝试：</span><span class="sxs-lookup"><span data-stu-id="f1549-143">If you do not see the **Allow USB Debugging** prompt on your Android device try:</span></span>  

*   <span data-ttu-id="f1549-144">断开连接并重新连接 USB 电缆的同时，DevTools 将集中在开发计算机上，并且显示 Android 主屏幕。</span><span class="sxs-lookup"><span data-stu-id="f1549-144">Disconnecting and then re-connecting the USB cable while DevTools is in focus on your development machine and your Android homescreen is showing.</span></span>  <span data-ttu-id="f1549-145">换句话说，有时当 Android 或开发计算机屏幕锁定时，不会显示提示。</span><span class="sxs-lookup"><span data-stu-id="f1549-145">In other words, sometimes the prompt does not show up when your Android or development machine screens are locked.</span></span>
*   <span data-ttu-id="f1549-146">更新 Android 设备和开发计算机的显示设置，使其永不进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="f1549-146">Updating the display settings for your Android device and development machine so that they never go to sleep.</span></span>  
*   <span data-ttu-id="f1549-147">将 Android 的 USB 模式设置为 PTP。</span><span class="sxs-lookup"><span data-stu-id="f1549-147">Setting the USB mode for Android to PTP.</span></span>  <span data-ttu-id="f1549-148">请参阅[Galaxy S4 不显示 "授权 USB 调试" 对话框][StackExchangeGalaxyS4DoesNotShowDialogBox]。</span><span class="sxs-lookup"><span data-stu-id="f1549-148">See [Galaxy S4 does not show Authorize USB debugging dialog box][StackExchangeGalaxyS4DoesNotShowDialogBox].</span></span>  
*   <span data-ttu-id="f1549-149">从 Android 设备上的 "**开发工具选项**" 屏幕中选择 "**撤消 USB 调试授权**"，将其重置为新状态。</span><span class="sxs-lookup"><span data-stu-id="f1549-149">Select **Revoke USB Debugging Authorizations** from the **Developer Options** screen on your Android device to reset it to a fresh state.</span></span>  

<span data-ttu-id="f1549-150">如果你发现本部分中未提及的解决方案或 "DevTools 设备" 在插入时未检测到设备 "[StackOverflowDevicesNotDetected]，或者请添加该堆栈溢出问题的答案</span><span class="sxs-lookup"><span data-stu-id="f1549-150">If you find a solution that is not mentioned in this section or in [DevTools Devices does not detect device when plugged in][StackOverflowDevicesNotDetected] or please add an answer to that Stack Overflow question</span></span><!--, or [open an issue in the webfundamentals repository][GitHubWebFundamentalsNewIssue]--><span data-ttu-id="f1549-151">!</span><span class="sxs-lookup"><span data-stu-id="f1549-151">!</span></span>  

## <span data-ttu-id="f1549-152">步骤2：从开发计算机调试 Android 设备上的内容</span><span class="sxs-lookup"><span data-stu-id="f1549-152">Step 2: Debug content on your Android device from your development machine</span></span>   

1.  <span data-ttu-id="f1549-153">在 Android 设备上打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="f1549-153">Open Microsoft Edge on your Android device.</span></span>  

1.  <span data-ttu-id="f1549-154">在 "**远程设备**" 选项卡中，选择与你的 Android 设备模型名称相匹配的选项卡。</span><span class="sxs-lookup"><span data-stu-id="f1549-154">In the **Remote Devices** tab, select the tab that matches your Android device model name.</span></span>  
    <span data-ttu-id="f1549-155">在此页的顶部，你可以看到 Android 设备的模型名称，后跟其序列号。</span><span class="sxs-lookup"><span data-stu-id="f1549-155">At the top of this page, you see the model name of your Android device, followed by its serial number.</span></span>  <span data-ttu-id="f1549-156">在此下方，你应该看到在设备上运行的 Microsoft Edge 版本，其中版本号位于括号中。</span><span class="sxs-lookup"><span data-stu-id="f1549-156">Below that, you should see the version of Microsoft Edge running on the device, with the version number in parentheses.</span></span>  <span data-ttu-id="f1549-157">每个打开的 Microsoft Edge 选项卡都将获取其自己的分区。</span><span class="sxs-lookup"><span data-stu-id="f1549-157">Each open Microsoft Edge tab gets its own section.</span></span>  <span data-ttu-id="f1549-158">您可以从此部分与该选项卡进行交互。</span><span class="sxs-lookup"><span data-stu-id="f1549-158">You may interact with that tab from this section.</span></span>  <!--If there are any apps using WebView, you see a section for each of those apps, too.  --><!--In [**Figure 5**](#figure-5) there are no tabs or WebViews open.  -->
    <!--
    > ##### Figure 5  
    > A connected remote device  
    > ![A connected remote device][ImageConnectedRemoteDevice]  -->

1.  <span data-ttu-id="f1549-159">在 "**新建选项卡**" 文本框中，输入 URL，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="f1549-159">In the **New tab** text box, enter a URL and then select **Open**.</span></span>  <span data-ttu-id="f1549-160">页面将在 Android 设备上的新选项卡中打开。</span><span class="sxs-lookup"><span data-stu-id="f1549-160">The page opens in a new tab on your Android device.</span></span>  

1.  <span data-ttu-id="f1549-161">选择您刚刚打开的 URL 旁边的 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="f1549-161">Select **Inspect** next to the URL that you just opened.</span></span>  <span data-ttu-id="f1549-162">将打开一个新的 DevTools 实例。</span><span class="sxs-lookup"><span data-stu-id="f1549-162">A new DevTools instance opens.</span></span>  <span data-ttu-id="f1549-163">在 Android 设备上运行的 Microsoft Edge 版本决定了在开发计算机上打开的 DevTools 版本。</span><span class="sxs-lookup"><span data-stu-id="f1549-163">The version of Microsoft Edge running on your Android device determines the version of DevTools that opens on your development machine.</span></span>  
    <span data-ttu-id="f1549-164">因此，如果 Android 设备运行的是较旧版本的 Microsoft Edge，则 DevTools 实例可能看起来与你使用的版本有所不同。</span><span class="sxs-lookup"><span data-stu-id="f1549-164">So, if your Android device is running a very old version of Microsoft Edge, the DevTools instance may look very different than what you are used to.</span></span>  

### <span data-ttu-id="f1549-165">更多操作：重新加载、焦点或关闭选项卡</span><span class="sxs-lookup"><span data-stu-id="f1549-165">More actions: reload, focus, or close a tab</span></span>   

<span data-ttu-id="f1549-166">选择**More Options** `...` 要重新加载、焦点或关闭的选项卡旁边的 "更多选项"。</span><span class="sxs-lookup"><span data-stu-id="f1549-166">Select **More Options** `...` next to the tab that you want to reload, focus, or close.</span></span>  
<!--
> ##### Figure 6  
> The menu for reloading, focusing, or closing a tab  
> ![The menu for reloading, focusing, or closing a tab][ImageReload]  -->

### <span data-ttu-id="f1549-167">检查元素</span><span class="sxs-lookup"><span data-stu-id="f1549-167">Inspect elements</span></span>   

<span data-ttu-id="f1549-168">转到 DevTools 实例的 "**元素**" 面板，将鼠标悬停在某个元素上，将其突出显示在 Android 设备的视口中。</span><span class="sxs-lookup"><span data-stu-id="f1549-168">Go to the **Elements** panel of your DevTools instance, and hover over an element to highlight it in the viewport of your Android device.</span></span>  

<span data-ttu-id="f1549-169">您也可以在 Android 设备屏幕上选择一个元素，以便在 "**元素**" 面板中选择该元素。</span><span class="sxs-lookup"><span data-stu-id="f1549-169">You may also select an element on your Android device screen to select it in the **Elements** panel.</span></span>  <span data-ttu-id="f1549-170">在 DevTools 实例上选择 "**选择元素**"，然后在 ![ ][ImageSelectElementIcon] Android 设备屏幕上选择该元素。</span><span class="sxs-lookup"><span data-stu-id="f1549-170">Select **Select Element** ![Select Element][ImageSelectElementIcon] on your DevTools instance, and then select the element on your Android device screen.</span></span>  

> [!NOTE]
> <span data-ttu-id="f1549-171">选择第一个选项后，"**选择元素**" 已禁用，因此必须在每次使用此功能时重新启用它。</span><span class="sxs-lookup"><span data-stu-id="f1549-171">**Select Element** is disabled after the first selection, so you must re-enable it every time you want to use this feature.</span></span>  

### <span data-ttu-id="f1549-172">将 Android 屏幕说明截屏视频到开发计算机</span><span class="sxs-lookup"><span data-stu-id="f1549-172">Screencast your Android screen to your development machine</span></span>   

<span data-ttu-id="f1549-173">选择 "**切换说明截屏视频** ![ 切换 ][ImageToggleScreencastIcon] " 说明截屏视频可在 DevTools 实例中查看 Android 设备的内容。</span><span class="sxs-lookup"><span data-stu-id="f1549-173">Select **Toggle Screencast** ![Toggle Screencast][ImageToggleScreencastIcon] to view the content of your Android device in your DevTools instance.</span></span>  

<span data-ttu-id="f1549-174">你可以通过多种方式与说明截屏视频交互：</span><span class="sxs-lookup"><span data-stu-id="f1549-174">You are able to interact with the screencast in multiple ways:</span></span>  

*   <span data-ttu-id="f1549-175">单击被转换为点击，在设备上触发正确的触摸事件。</span><span class="sxs-lookup"><span data-stu-id="f1549-175">Clicks are translated into taps, firing proper touch events on the device.</span></span>  
*   <span data-ttu-id="f1549-176">将计算机上的击键发送到设备。</span><span class="sxs-lookup"><span data-stu-id="f1549-176">Keystrokes on your computer are sent to the device.</span></span>  
*   <span data-ttu-id="f1549-177">若要模拟捏出的手势，请 `Shift` 在拖动时按住。</span><span class="sxs-lookup"><span data-stu-id="f1549-177">To simulate a pinch gesture, hold `Shift` while dragging.</span></span>  
*   <span data-ttu-id="f1549-178">若要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针投掷。</span><span class="sxs-lookup"><span data-stu-id="f1549-178">To scroll, use your trackpad or mouse wheel, or fling with your mouse pointer.</span></span>

<span data-ttu-id="f1549-179">Screencasts 上的一些笔记：</span><span class="sxs-lookup"><span data-stu-id="f1549-179">Some notes on screencasts:</span></span>  

*   <span data-ttu-id="f1549-180">Screencasts 仅显示页面内容。</span><span class="sxs-lookup"><span data-stu-id="f1549-180">Screencasts only display page content.</span></span>  <span data-ttu-id="f1549-181">说明截屏视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Android 状态栏或 Android 键盘。</span><span class="sxs-lookup"><span data-stu-id="f1549-181">Transparent portions of the screencast represent device interfaces, such as the Microsoft Edge address bar, the Android status bar, or the Android keyboard.</span></span>  
*   <span data-ttu-id="f1549-182">Screencasts 会对帧速率产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="f1549-182">Screencasts negatively affect frame rates.</span></span>  <span data-ttu-id="f1549-183">在测量滚动或动画时禁用 screencasting，以便更准确地了解页面性能。</span><span class="sxs-lookup"><span data-stu-id="f1549-183">Disable screencasting while measuring scrolls or animations to get a more accurate picture of the performance of your page.</span></span>  
*   <span data-ttu-id="f1549-184">如果你的 Android 设备屏幕锁定，你的说明截屏视频的内容将消失。</span><span class="sxs-lookup"><span data-stu-id="f1549-184">If your Android device screen locks, the content of your screencast disappears.</span></span>  <span data-ttu-id="f1549-185">解锁 Android 设备屏幕以自动恢复说明截屏视频。</span><span class="sxs-lookup"><span data-stu-id="f1549-185">Unlock your Android device screen to automatically resume the screencast.</span></span>  





<!-- image links -->  

[ImageSelectElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-element-icon.msft.png  
[ImageToggleScreencastIcon]: /microsoft-edge/devtools-guide-chromium/media/toggle-screencast-icon.msft.png  

<!--[ImageRemoteDebugging]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--remote-debugging.msft.png "old Figure 1:  Remote Debugging lets you inspect a page running on an Android device from your development machine"  -->  
<span data-ttu-id="f1549-186">[ImageOpenRemoteDevices]：/microsoft-edge/devtools-guide-chromium/media/remote-debugging-more-tools-remote-devices.msft.png "图1：通过主菜单打开" 远程设备 "选项卡</span><span class="sxs-lookup"><span data-stu-id="f1549-186">[ImageOpenRemoteDevices]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-more-tools-remote-devices.msft.png "Figure 1: Opening the Remote Devices tab via the Main Menu"</span></span>  
<span data-ttu-id="f1549-187">[ImageDiscoverUSBDevices]：/microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-tab.msft.png "图2：已启用" 发现 USB 设备 "复选框</span><span class="sxs-lookup"><span data-stu-id="f1549-187">[ImageDiscoverUSBDevices]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging-remote-devices-tab.msft.png "Figure 2:  The Discover USB Devices checkbox is enabled"</span></span>  
<!--[ImageUnknownDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--unknown-device.msft.png "old Figure 4:  The Remote Devices tab has successfully detected an unknown device that is pending authorization"  -->  
<!--[ImageConnectedRemoteDevice]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--connected-remote-device.msft.png "old Figure 5:  A connected remote device"  -->
<!--[ImageReload]: /microsoft-edge/devtools-guide-chromium/media/remote-debugging--reload.msft.png "old Figure 6: The menu for reloading, focusing, or closing a tab"  -->

<!-- links -->  

[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  

[AndroidUSBDrivers]: https://developer.android.com/tools/extras/oem-usb.html "安装 OEM USB 驱动程序 |Android 开发人员"  

<!-- [GitHubWebFundamentalsNewIssue]: https://github.com/Alphabet/webfundamentals/issues/new?title=[Remote%20Debugging] "GitHub - Web Fundamentals - New Issue"  -->  
<span data-ttu-id="f1549-190">[StackOverflowDevicesNotDetected]： https://stackoverflow.com/questions/21925992 "当插入堆栈内溢时，DevTools 设备不检测设备"</span><span class="sxs-lookup"><span data-stu-id="f1549-190">[StackOverflowDevicesNotDetected]: https://stackoverflow.com/questions/21925992 "DevTools Devices does not detect device when plugged in - Stack Overflow"</span></span>  

[StackExchangeGalaxyS4DoesNotShowDialogBox]: https://android.stackexchange.com/questions/101933 "adb-Android 发烧友式堆栈交换"  

> [!NOTE]
> <span data-ttu-id="f1549-192">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f1549-192">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f1549-193">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="f1549-193">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/remote-debugging/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="f1549-195">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f1549-195">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
