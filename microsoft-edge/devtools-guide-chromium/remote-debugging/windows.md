---
description: 远程调试 Windows 10 设备入门
title: 远程调试 Windows 10 设备入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/23/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 远程， 调试， windows 10， windows， 设备门户
ms.openlocfilehash: e3f60f07ba96aaed8cd9d7348eee1b0a846faecf
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519235"
---
# <a name="get-started-with-remote-debugging-windows-10-devices"></a>远程调试 Windows 10 设备入门  

从 Windows 或 macOS 计算机在 Windows 10 设备上远程调试实时内容。  本教程指导你完成以下任务。  

*   设置 Windows 10 设备进行远程调试，然后从开发计算机连接到该设备。  
*   从开发计算机检查和调试 Windows 10 设备上实时内容。  
*   将 Windows 10 设备中的内容屏蔽到开发计算机上 DevTools 实例。  
    
## <a name="step-1-set-up-the-host-debuggee-machine"></a>步骤 1：设置 (调试程序计算机)   

主机或调试程序计算机是你想要调试的 Windows 10 设备。  可能是远程设备难以从物理上访问，或者可能没有键盘和鼠标外设，导致难以与该设备上的 Microsoft Edge DevTools 交互。  若要设置主机 \ (debuggee\) 计算机，需要完成以下操作。  

*   安装和配置 [Microsoft Edge (Chromium) ][MicrosoftEdgeMain]  
*   从 Microsoft [Store 安装适用于 Microsoft Edge (Beta) ][MicrosoftStoreApps9p6cmfv44zlt] 的 [远程工具][MicrosoftStoreAppsWindows]  
*   激活 [开发人员模式][WindowsAppsGetStartedEnableYourDeviceForDevelopment] 并启用 [Device Portal][WindowsUwpDebugTestPerfDevicePortal]  
    
### <a name="install-and-configure-microsoft-edge-chromium"></a>安装和配置 Microsoft Edge (Chromium)   

如果尚未安装，请从此页面安装 Microsoft Edge \ (Chromium\) [Chromium\) 。][MicrosoftEdgeMain]  如果在主机 \ (debuggee\) 计算机上使用预安装的 Microsoft Edge 版本，请验证您是否具有 Microsoft Edge \ (Chromium\) ，而不是 Microsoft Edge \ (EdgeHTML\) 。  检查的一种快速方法就是在浏览器中加载 `edge://settings/help` 并确认版本号是否为 75 或更高。  

现在导航 `edge://flags` 到 Microsoft Edge \ (Chromium\) 。  在 **"搜索标志"** 中，键入 **"通过 Windows Device Portal 启用远程调试"。**  将标志设置为 **已启用**。  然后，选择" **重启"** 按钮以重新启动 Microsoft Edge \ (Chromium\) 。  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-flags-on-host.msft.png" alt-text="将"通过 Windows Device Portal 启用远程调试"标志设置为"已启用"" lightbox="../media/remote-debugging-windows-media-edge-flags-on-host.msft.png":::
   将 **"通过 Windows Device Portal 启用远程调试"标志** 设置为 **"已启用"**  
:::image-end:::  

### <a name="install-the-remote-tools-for-microsoft-edge-beta"></a>安装适用于 Microsoft Edge (Beta)   

从 Microsoft [Store 安装适用于 Microsoft Edge (Beta) ][MicrosoftStoreApps9p6cmfv44zlt] 的 [远程工具][MicrosoftStoreAppsWindows]。  

> [!NOTE]
> 如果你 **使用** Windows 10 版本 1809 或更早版本， ([Microsoft Edge ][MicrosoftStoreApps9p6cmfv44zlt]) 的"获取"按钮可能处于禁用状态。  若要设置主机 \ (debuggee\) 计算机，它必须运行 Windows 10 版本 1903 或更高版本。  更新主机 \ (debuggee\) 计算机以获取 Microsoft Edge [ (Beta ][MicrosoftStoreApps9p6cmfv44zlt]) 。  

:::image type="complex" source="../media/remote-debugging-windows-media-remote-tools-in-store.msft.png" alt-text="Microsoft Store 中的 Microsoft Edge 远程工具 \ (Beta\) " lightbox="../media/remote-debugging-windows-media-remote-tools-in-store.msft.png":::
   Microsoft [Store 中适用于 Microsoft Edge (Beta) ][MicrosoftStoreApps9p6cmfv44zlt] 的 [远程工具][MicrosoftStoreAppsWindows]  
:::image-end:::  

启动适用于 [Microsoft Edge (Beta ][MicrosoftStoreApps9p6cmfv44zlt]) ，如果系统提示，接受应用中的权限对话框。  现在，你能够关闭 [Microsoft Edge ][MicrosoftStoreApps9p6cmfv44zlt] (Beta) 并且无需为将来的远程调试会话打开它。

### <a name="activate-developer-mode-and-enable-device-portal"></a>激活开发人员模式并启用 Device Portal  

如果你使用 WiFi 网络，请确保该网络标记为"域"或"**专用****"。**  你可以打开**Windows**安全应用，选择"防火墙"&**网络保护**并检查你的网络是否列为"域网络"或"专用网络"，以验证**状态。** ****  

如果列为"公用"，请导航到"设置""& **** ****  >  **Internet**  >  **WI-Fi"，** 选择"网络"，将"**网络配置文件**"按钮切换为 **"专用"。**  

现在，打开 **"设置"** 应用。  在 **"查找设置"** 中， `Developer settings` 输入并选择它。  在开发人员 **模式下切换**。  现在，你可以将"打开通过本地网络连接的远程诊断"设置为 **"打开**"**来打开**Device **Portal。**  然后，可以选择打开身份验证，**** 以便客户端 \ (调试器\) 设备必须提供正确的凭据以连接到此设备。  

> [!NOTE]
> 如果 **通过本地网络连接打开远程诊断。** 之前已打开，必须将其关闭并再次打开 **，Device Portal**使用适用于 Microsoft Edge 的远程工具[ (Beta) 。 ][MicrosoftStoreApps9p6cmfv44zlt]  如果" **适用于开发人员** "部分 **未显示在"** 设置"中，则 **Device Portal** 可能已经打开，因此请尝试改为重新启动 Windows 10 设备。

:::image type="complex" source="../media/remote-debugging-windows-media-host-settings.msft.png" alt-text="已配置开发人员模式和设备门户的设置应用" lightbox="../media/remote-debugging-windows-media-host-settings.msft.png":::
   已 **配置** 开发人员 **模式和设备** 门户 **的设置** 应用  
:::image-end:::  

请注意 Connect 下显示计算机 IP 地址和连接 **端口，使用：**。  下图中的 IP 地址为 ， `192.168.86.78` 连接端口为 `50080` 。  

:::image type="complex" source="../media/remote-debugging-windows-media-host-settings-ip-address.msft.png" alt-text="记下"设置"中的 IP 地址和连接端口" lightbox="../media/remote-debugging-windows-media-host-settings-ip-address.msft.png":::
   记下"设置"中的 IP 地址和 **连接端口**  
:::image-end:::  

你将在下面部分中的客户端 \ (\) 设备上 [输入信息](#step-2-set-up-the-client-debugger-machine)。  在主机 \ (debuggee\) 计算机上打开要从客户端 \ (调试器\) 计算机调试的 Microsoft Edge 和渐进 [ (式 Web ][DevtoolsProgressiveWebApps] 应用) 中的选项卡。  

## <a name="step-2-set-up-the-client-debugger-machine"></a>步骤 2：将客户端 (调试器计算机)   

客户端或调试程序计算机是你想要调试的设备。  此设备可能是你的日常开发计算机，也可能只是在家工作时的电脑或 MacBook。  

若要设置客户端 \ (调试器\) 计算机，请从此页安装 Microsoft Edge \ (Chromium\) （如果尚未安装[][MicrosoftEdgeMain]）。  如果在主机 \ (debuggee\) 计算机上使用预安装的 Microsoft Edge 版本，请验证您是否具有 Microsoft Edge \ (Chromium\) ，而不是 Microsoft Edge \ (EdgeHTML\) 。  检查的一种快速方法就是在浏览器中加载 `edge://settings/help` 并确认版本号是否为 75 或更高。  

现在导航 `edge://flags` 到 Microsoft Edge \ (Chromium\) 。  在 **"搜索标志"** 中，键入"启用远程**Windows 设备调试 edge://inspect"。**  将标志设置为 **已启用**。  然后，选择" **重启"** 按钮以重新启动 Microsoft Edge \ (Chromium\) 。  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-flags-on-client.msft.png" alt-text="将"启用远程 Windows 设备调试"edge://inspect 设置为"已启用"" lightbox="../media/remote-debugging-windows-media-edge-flags-on-client.msft.png":::
   将" **启用远程 Windows 设备调试"edge://inspect** 设置为 **"已启用"**  
:::image-end:::  

现在导航到 `edge://inspect` Microsoft Edge \ (Chromium\) 。  默认情况下，你应该位于" **设备"** 部分。  在 **"连接到远程 Windows**设备"下，按照此模式在文本框中输入主机 \ (debuggee\) 计算机 IP 地址和连接端口：http://： `IP address` `connection port` 。  现在，选择 **"连接到设备"。**  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-inspect.msft.png" alt-text="客户端 edge://inspect 页" lightbox="../media/remote-debugging-windows-media-edge-inspect.msft.png":::
   `edge://inspect`客户端上的页面  
:::image-end:::  

如果为主机 \ (debuggee\) 计算机设置了身份验证，系统将提示您输入客户端 \ (debugger\) **** 计算机**** 以成功连接的用户名和密码。  

### <a name="using-https-instead-of-http"></a>使用 https 而不是 http  

如果要使用 而不是 连接到主机 \ (debuggee\) 计算机，则必须在客户端 `https` `http` `http://IP address:50080/config/rootcertificate` \ (debugger\) 计算机上导航到 Microsoft Edge。  这会自动下载名为 的安全证书 `rootcertificate.cer` 。

选择`rootcertificate.cer`。  这将打开 [Windows 证书管理器工具][DotnetFrameworkWcfFeatureDetailsHowToViewCertificatesWithMmcSnapInViewCertificatesWithCertificateManagerTool]。

选择 **"安装证书..."，** 确保"**当前**用户"已打开，然后选择"下一**步"。**  现在，**选择"将所有证书放在以下存储中"，** 然后选择"浏览 **..."。** 选择"**受信任的根证书颁发机构"** 存储，然后选择"确定 **"。**  选择 **"下一**步"，然后选择"**完成"。**  如果系统提示，请确认要安装此证书到受信任的根 **证书颁发机构** 存储。

现在，在使用页面从客户端 \ (debugger\) 计算机连接到主机 \ (debuggee\) 计算机时，必须使用其他值 `edge://inspect` `connection port` 。  默认情况下，对于桌面 Windows，Device Portal `50080` 使用 作为 `connection port` 的 `http` 。  对于 `https` ，Device Portal 使用 `50043` ，因此请遵循以下模式：https:// `IP address` `50043` `edge://inspect` ：。  [阅读有关 Device Portal 使用的默认端口的信息][WindowsUwpDebugTestPerfDevicePortalSetup]。  

> [!NOTE]
> 的默认端口为 ，默认端口为 ，但并非始终如此，因为桌面版上的 Device Portal 声明临时范围 `http` `50080` `https` `50043` \ (\>50，000\) 中的端口以防止与设备上现有的端口声明发生冲突。  若要了解更多信息，请导航到[][WindowsUwpDebugTestPerfDevicePortalDesktopRegistryBasedConfigurationForDevicePortal]Windows 桌面上 Device Portal 的"端口设置"部分。  

## <a name="step-3-debug-content-on-the-host-from-the-client"></a>步骤 3：从客户端调试主机上的内容  

如果客户端 \ (debugger\) 计算机成功连接到主机 \ (debuggee\) 计算机，则客户端上的页面现在会显示 Microsoft Edge 中的选项卡列表和主机上任何打开的 `edge://inspect` PWA。  

:::image type="complex" source="../media/remote-debugging-windows-media-edge-inspect-connected.msft.png" alt-text="客户端上的 edge://inspect 页面在主机上显示 Microsoft Edge 和 PWA 中的选项卡" lightbox="../media/remote-debugging-windows-media-edge-inspect-connected.msft.png":::
   客户端 `edge://inspect` 上的页面在主机上显示 Microsoft Edge 和 PWA 中的选项卡  
:::image-end:::  

确定要调试的内容，然后选择"检查 **"。**  Microsoft Edge DevTools 将在新选项卡中打开，并屏幕将内容从主机 \ (debuggee\) 计算机屏蔽到客户端 \ (debugger\) 计算机。  现在，你可以对主机上运行的内容使用客户端上的 Microsoft Edge DevTools 的全部功能。  在此处了解有关如何使用 Microsoft Edge DevTools [的更多信息][DevtoolsIndex]。  

:::image type="complex" source="../media/remote-debugging-windows-media-devtools-client.msft.png" alt-text="客户端上的 Microsoft Edge DevTools 调试主机上的 Microsoft Edge 中的选项卡" lightbox="../media/remote-debugging-windows-media-devtools-client.msft.png":::
   客户端 [上的 Microsoft Edge DevTools][DevtoolsIndex] 调试主机上的 Microsoft Edge 中的选项卡  
:::image-end:::  

### <a name="inspect-elements"></a>检查元素  

例如，尝试检查元素。  导航到 **客户端** 上的 DevTools 实例的 Elements 工具，将鼠标悬停在某个元素上以在主机设备的视口中突出显示它。  

还可以点击主机设备屏幕上的某个元素，以在"元素"工具 **中选择** 它。  在 **客户端上的** DevTools 实例上选择"选择元素"，然后在主机设备屏幕上点击该元素。  

> [!NOTE]
> **Select Element** is disabled after the first touch， so you need to turn it on again time you want to use this feature.  

> [!IMPORTANT]
> 在**** Windows 10 版本 1903 上 **，"** 元素"工具中的"事件侦听器"窗格为空。  这是一个已知问题，团队计划修复 Windows **** 10 版本 1903 的服务更新中的"事件侦听器"窗格。  

## <a name="step-4-screencast-your-host-screen-to-your-client-device"></a>步骤 4：将主机屏幕屏蔽到客户端设备  

默认情况下，客户端上的 DevTools 实例已打开屏幕视频，这允许你在客户端设备的 DevTools 实例中查看主机设备上的内容。  选择 **"切换屏幕** 视频"以关闭或打开此功能。  

:::image type="complex" source="../media/remote-debugging-windows-media-toggle-screencast.msft.png" alt-text="客户端上的 Microsoft Edge DevTools 中的切换屏幕视频按钮" lightbox="../media/remote-debugging-windows-media-toggle-screencast.msft.png":::
   客户端 **上的** Microsoft Edge DevTools 中的切换屏幕视频按钮  
:::image-end:::  

你能够通过多种方式与屏幕广播交互：  
*   选择将转换为点击，在设备上触发适当的触摸事件。  
*   计算机上的击键会发送到设备。  
*   若要模拟收缩手势，拖动时按住 `Shift`。  
*   如果要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针拖动。  

屏幕广播上的一些注释：  
*   截屏视频仅显示页面内容。  屏幕广播的透明部分表示设备接口，如 Microsoft Edge 地址栏、Windows 10 任务栏或 Windows 10 键盘。  
*   截屏视频会对帧速率产生负面影响。  在测量滚动或动画时禁用截屏视频，以更准确地了解页面性能。  
*   如果主机设备屏幕锁定，屏幕视频的内容将消失。  解锁主机设备屏幕以自动恢复屏幕视频。  

## <a name="known-issues"></a>已知问题  

在**** Windows 10 版本 1903 上 **，"** 元素"工具中的"事件侦听器"窗格为空。  该团队计划修复 Windows **** 10 版本 1903 的服务更新中的"事件侦听器"窗格。  

在**Windows** 10 版本 1903 上，"应用程序"面板中的"Cookie"窗格为空。 ****  该团队计划修复 Windows **** 10 版本 1903 的服务更新中的 Cookie 窗格。  

审核**工具****、3D 视图**工具、"设置"中的"模拟设备"部分**** 以及"元素"**** 工具中的"辅助功能"树**** 窗格当前未按预期工作。 ****  该团队计划在 Microsoft Edge 的未来更新中修复列出的工具。  

当你远程调试时，文件资源管理器不会从源工具中的 DevTools 或**安全**面板中启动。 ****  该团队计划在 Microsoft Edge 的未来更新中修复这些工具。  

<!-- links -->

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具概述|Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "调试渐进式 Web 应用 | Microsoft Docs"  

[DotnetFrameworkWcfFeatureDetailsHowToViewCertificatesWithMmcSnapInViewCertificatesWithCertificateManagerTool]: /dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in#view-certificates-with-the-certificate-manager-tool "使用证书管理器工具查看证书 - 如何：使用 MMC 管理单元查看|Microsoft Docs"  

[WindowsAppsGetStartedEnableYourDeviceForDevelopment]: /windows/apps/get-started/enable-your-device-for-development "启用设备进行开发|Microsoft Docs"  

[WindowsUwpDebugTestPerfDevicePortal]: /windows/uwp/debug-test-perf/device-portal "Windows Device Portal 概述|Microsoft Docs"  
[WindowsUwpDebugTestPerfDevicePortalSetup]: /windows/uwp/debug-test-perf/device-portal#setup "设置 - Windows Device Portal 概述|Microsoft Docs"  
[WindowsUwpDebugTestPerfDevicePortalDesktopRegistryBasedConfigurationForDevicePortal]: /windows/uwp/debug-test-perf/device-portal-desktop#registry-based-configuration-for-device-portal "Device Portal 的基于注册表的配置 - 适用于 Windows 桌面设备的 Device Portal |Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows 应用|Microsoft Store"  

[MicrosoftStoreApps9p6cmfv44zlt]: https://www.microsoft.com/store/apps/9P6CMFV44ZLT "适用于 Microsoft Edge (Beta) |Microsoft Store"  
