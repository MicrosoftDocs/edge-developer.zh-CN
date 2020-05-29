---
title: 远程调试 Windows 10 设备入门
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、远程、调试、windows 10、windows、device portal
ms.openlocfilehash: b944e1f16d4c26f4db83e3eb131f1da8ea938c97
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563562"
---
# 远程调试 Windows 10 设备入门  

Windows 或 macOS 计算机上的 Windows 10 设备上的远程调试实时内容。  本教程将指导你如何：  

*   为远程调试设置 Windows 10 设备，并从开发计算机连接到该设备。  
*   从开发计算机检查和调试 Windows 10 设备上的实时内容。  
*   将 Windows 10 设备中的内容说明截屏视频到开发计算机上的 DevTools 实例。  

## 步骤1：设置主机（调试对象计算机）  

"主机" 或 "调试对象" 计算机是要调试的 Windows 10 设备。  这可能是一个远程设备，很难让你进行物理访问，或者它可能没有键盘和鼠标外围设备，因此很难与该设备上的 Microsoft Edge DevTools 交互。  若要设置宿主（调试对象）计算机，您将需要：  

*   安装和配置[Microsoft Edge （Chromium）](https://www.microsoft.com/edge)  
*   从[Microsoft Store](https://www.microsoft.com/store/apps/windows)安装[Microsoft Edge 远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)  
*   激活[开发人员模式](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development)并启用[Device Portal](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal)  

### 安装和配置 Microsoft Edge （Chromium）  

如果尚未安装，请从此[页面](https://www.microsoft.com/edge)安装 Microsoft Edge （Chromium）。  如果你在主机（调试对象）计算机上使用预安装的 Microsoft Edge 版本，请验证你有 Microsoft Edge （Chromium）而不是 Microsoft Edge （EdgeHTML）。  快速检查的方法是 `edge://settings/help` 在浏览器中加载并确认版本号为75或更高版本。  

现在导航到 `edge://flags` Microsoft Edge （Chromium）。  在 "**搜索" 标志**中，键入 "**通过 Windows Device Portal 启用远程调试**"。  将该标志设置为 "**启用**"。  然后，单击 "**重新启动**" 按钮重启 Microsoft Edge （Chromium）。  

> ##### 图 1  
> 将 "**通过 Windows Device Portal 启用远程调试**" 标志设置为 "**启用**"  
> ![将 "通过 Windows Device Portal 启用远程调试" 标志设置为 "启用"](./windows-media/edge-flags-on-host.png)  

### 安装适用于 Microsoft Edge 的远程工具（Beta）  

从[Microsoft Store](https://www.microsoft.com/store/apps/windows)安装[Microsoft Edge 远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 。  

> [!NOTE]
> 如果你使用的是 Windows 10 版本1809或更早版本，则可能会禁用适用于[Microsoft Edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)的 "**获取**" 按钮。  若要设置宿主（调试对象）计算机，它必须运行 Windows 10 版本1903或更高版本。  更新主机（调试对象）计算机以获取[Microsoft Edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)。  

> ##### 图 2  
> [Microsoft Store](https://www.microsoft.com/store/apps/windows)中的[Microsoft Edge 远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)  
> ![Microsoft Store 中的 Microsoft Edge 远程工具（Beta）](./windows-media/remote-tools-in-store.png)  

启动[适用于 Microsoft Edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) ，如果出现提示，请接受应用中的 "权限" 对话框。 现在，你可以关闭[Microsoft Edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) ，并且无需在将来的远程调试会话中打开它。

### 激活开发人员模式并启用 Device Portal  

如果您使用的是 WiFi 网络，请确保网络已标记为 "**域**" 或 "**专用**"。  你可以通过以下方法验证此情况：打开**Windows 安全**应用，单击 "**防火墙 & 网络保护**"，然后检查您的网络是否列为**域**网络或**专用**网络。  

如果它列为 "**公共**"，请转到 "**设置**  >  **网络 & Internet**  >  **wi-fi**"，单击您的网络并将 "**网络配置文件**" 按钮切换到 "**专用**"。  

现在，打开 "**设置**" 应用。  在 "**查找设置**" 中，输入 "**开发人员设置**" 并选中它。  在**开发人员模式下**切换。  现在，你可以通过将 "**通过局域网连接上的远程诊断**" 设置为 **"打开"** 来启用**Device Portal** 。  然后，你可以选择打开**身份验证**，以便客户端（调试器）设备必须提供正确的凭据才能连接到该设备。  

> [!NOTE]
> 如果**通过局域网连接启用远程诊断。** 以前已启用，您必须禁用它并再次启用它，以便**设备门户**能够使用适用于[Microsoft Edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)。 如果在 "**设置**" 中看不到 "**面向开发人员**" 部分，则可能已启用**Device Portal** ，请尝试重启 Windows 10 设备。

> ##### 图 3  
> 配置了**开发人员模式**和**设备门户**的 "**设置**" 应用  
> ![配置了开发人员模式和设备门户的 "设置" 应用](./windows-media/host-settings.png)  

注意 "**连接时使用：**" 下显示的计算机 IP 地址和连接端口。  下图中的 IP 地址是 `192.168.86.78` 和连接端口 `50080` 。  

> ##### 图 4  
> 记下 "**设置**" 中的 IP 地址和连接端口  
> ![记下 "设置" 中的 IP 地址和连接端口](./windows-media/host-settings-ip-address.png)  

你将在[下一节](#step-2-set-up-the-client-debugger-machine)中的客户端（调试器）设备上输入此信息。  在要从客户端（调试程序）计算机调试的主机（调试对象）计算机上，打开 Microsoft Edge 和[累进 Web Apps （PWAs）](../progressive-web-apps.md)中的选项卡。  

## 步骤2：设置客户端（调试器计算机）  

客户端计算机或调试器计算机是要从中进行调试的设备。  此设备可能是你的每日开发计算机，也可能是你在家工作时的电脑或 MacBook。  

若要设置客户端（调试器）计算机，请从[该页](https://www.microsoft.com/edge)安装 Microsoft Edge （Chromium）（如果尚未安装）。  如果你在主机（调试对象）计算机上使用预安装的 Microsoft Edge 版本，请验证你有 Microsoft Edge （Chromium）而不是 Microsoft Edge （EdgeHTML）。  快速检查的方法是 `edge://settings/help` 在浏览器中加载并确认版本号为75或更高版本。  

现在导航到 `edge://flags` Microsoft Edge （Chromium）。  在 "**搜索" 标记**中，在 edge://inspect 中键入 "**启用远程 Windows 设备调试**"。  将该标志设置为 "**启用**"。  然后，单击 "**重新启动**" 按钮重启 Microsoft Edge （Chromium）。  

> ##### 图 5  
> 将 "**启用远程 Windows 设备调试" edge://inspect**标志设置为 "**启用**"  
> ![将 "启用远程 Windows 设备调试" edge://inspect 标志设置为 "启用"](./windows-media/edge-flags-on-client.png)  

现在导航到 `edge://inspect` Microsoft Edge 中的页面（Chromium）。  默认情况下，您应该位于 "**设备**" 部分。  在 "**连接到远程 Windows 设备**" 下，在此模式下的文本框中输入主机（调试对象）计算机的 IP 地址和连接端口： http:// `IP address` ： `connection port` 。  现在，单击 "**连接到设备**"。  

> ##### 图 6  
> `edge://inspect`客户端上的页面  
> ![客户端上的 edge://inspect 页](./windows-media/edge-inspect.png)  

如果为主机（调试对象）计算机设置身份验证，系统将提示输入客户端（调试器）计算机的**用户名**和**密码**才能成功连接。  

### 使用 https 而不是 http  

如果想要使用而不是连接到宿主（调试对象）计算机 `https` `http` ，则必须在 `http://IP address:50080/config/rootcertificate` 客户端（调试器）计算机上的 Microsoft Edge 中 navgiate。 这将自动下载一个名为的安全证书 `rootcertificate.cer` 。

单击 "打开" `rootcertificate.cer` 。 这将打开 " [Windows 证书管理器" 工具](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in#view-certificates-with-the-certificate-manager-tool)。

单击 "**安装证书 ...**"，确保选中 "**当前用户**"，然后单击 "**下一步**"。 现在，选择 **"将所有证书放入下列存储"** ，然后单击 "**浏览 ...**"。选择 "**受信任的根证书颁发机构**" 存储，然后单击 **"确定"**。 单击**下一步**，然后单击**完成**。 如果出现提示，请确认你想要将此证书安装到**受信任的根证书颁发机构**存储。

现在，从使用页面的客户端（调试程序）计算机连接到主机（调试对象）计算机时， `edge://inspect` 必须使用不同的 `connection port` 值。  默认情况下，对于桌面 Windows，设备门户将 `50080` 用作 `connection port` for `http` 。  对于 `https` ，设备门户使用如下 `50043` 模式： https:// `IP address` ： `50043` 在 `edge://inspect` 页面上。  [阅读有关 Device Portal 使用的默认端口的详细信息](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal#setup)。  

> [!NOTE]
> 的默认端口 `http` 是 `50080` 和的默认端口， `https` 但在 `50043` 桌面机上的设备门户中并不始终是在暂时范围内（>50000）中的设备门户，以防止与设备上的现有端口声明发生冲突。  若要了解详细信息，请参阅 Windows 桌面版 Device Portal 的[端口设置](https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal-desktop#registry-based-configuration-for-device-portal)部分。  

## 步骤3：从客户端调试主机上的内容  

如果客户端（调试器）计算机成功连接到主机（调试对象）计算机， `edge://inspect` 客户端上的页面将立即显示 Microsoft Edge 中的选项卡列表和主机上任何打开的 PWAs。  

> ##### 图 7  
> `edge://inspect`客户端上的页面显示 Microsoft Edge 中的选项卡和主机上的 PWAs  
> ![客户端上的 edge://inspect 页面显示 Microsoft Edge 中的选项卡和主机上的 PWAs](./windows-media/edge-inspect-connected.png)  

确定要调试的内容，然后单击 "**检查**"。  Microsoft Edge DevTools 将在新选项卡中打开，并将宿主（调试对象）计算机中的内容说明截屏视频到客户端（调试器）计算机。  现在，你可以使用客户端上 Microsoft Edge DevTools 的完整功能来运行在主机上运行的内容。  了解有关如何在[此处](../../devtools-guide-chromium.md)使用 Microsoft Edge DevTools 的详细信息。  

> ##### 图 8  
> [Microsoft Edge DevTools](../../devtools-guide-chromium.md)在客户端上调试主机上 microsoft edge 中的选项卡  
> ![Microsoft Edge DevTools 在客户端上调试主机上 Microsoft Edge 中的选项卡](./windows-media/devtools-client.png)  

### 检查元素  

例如，尝试检查元素。  转到客户端上 DevTools 实例的 "**元素**" 面板，将鼠标悬停在某个元素上，将其突出显示在主机设备的视区中。  

您也可以点击主机设备屏幕上的元素，在 "**元素**" 面板中将其选中。  在客户端上单击 DevTools 实例上的 "**选择元素**"，然后点击 "主机设备" 屏幕上的元素。  请注意，第一次触摸后， **Select 元素**已被禁用，因此你需要在每次使用此功能时重新启用它。  

> [!IMPORTANT]
> Windows 10 版本1903上的 "**元素**" 面板中的 "**事件侦听器**" 窗格为空。  这是一个已知问题，我们会将服务更新中的**事件侦听器**窗格修复到 Windows 10 版本1903。  

## 步骤4：将主机屏幕说明截屏视频到客户端设备  

默认情况下，客户端上的 DevTools 实例将 screencasting 切换，这使你能够查看客户端设备上的 DevTools 实例中的主机设备上的内容。  单击 "**切换说明截屏视频**" 以关闭或启用此功能。  

> ##### 图 9  
> 客户端上的 Microsoft Edge DevTools 中的 "**切换说明截屏视频**" 按钮  
> ![客户端上的 Microsoft Edge DevTools 中的 "切换说明截屏视频" 按钮](./windows-media/toggle-screencast.png)  

你可以通过多种方式与说明截屏视频交互：  
*   单击被转换为点击，在设备上触发正确的触摸事件。  
*   将计算机上的击键发送到设备。  
*   若要模拟捏出的手势，请 `Shift` 在拖动时按住。  
*   若要滚动，请使用触控板或鼠标滚轮，或使用鼠标指针投掷。  

Screencasts 上的一些笔记：  
*   Screencasts 仅显示页面内容。  说明截屏视频的透明部分表示设备接口，如 Microsoft Edge 地址栏、Windows 10 任务栏或 Windows 10 键盘。  
*   Screencasts 会对帧速率产生负面影响。  在测量滚动或动画时禁用 screencasting，以便更准确地了解页面性能。  
*   如果你的主机设备屏幕锁定，你的说明截屏视频的内容将消失。  解锁主机设备屏幕以自动恢复说明截屏视频。  

## 已知问题  

Windows 10 版本1903上的 "**元素**" 面板中的 "**事件侦听器**" 窗格为空。  我们会将服务更新中的**事件侦听器**窗格修复到 Windows 10 版本1903。  

Windows 10 版本1903上的 "**应用程序**" 面板中的 " **cookie** " 窗格为空。  我们会将服务更新中的 " **cookie** " 窗格修复为 Windows 10 版本1903。  

"**审核**" 面板、 **3d 视图**面板、"**设置**" 中的 "**模拟设备**" 部分和 "**元素**" 面板中的 "**辅助功能树**" 窗格当前未按预期工作。  我们将在 Microsoft Edge 的未来更新中修复这些工具。  

在远程调试时，文件资源管理器不会从 "**源**" 面板或 "**安全**" 面板中启动 DevTools。  我们将在 Microsoft Edge 的未来更新中修复这些工具。  
