---
description: Microsoft Edge 在 Linux 上，改进了 "问题" 工具中的 webhint 提示、新服务工作人员调试功能等。
title: DevTools (Microsoft Edge 88) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 500b64e7b51e0f02c9fcbcb7a83e8273b3a5a0d7
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11205241"
---
# DevTools (Microsoft Edge 88) 中的新增功能  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## Microsoft Edge 和 Microsoft Edge 驱动程序现已在 Linux 上提供  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

Microsoft Edge 开发现在支持 Ubuntu、Debian、Fedora 和 openSUSE 分布。  `.deb` `.rpm` 直接从[Microsoft Edge 预览体验计划网站][MicrosoftinsiderDownloadPlatformLinux]下载并安装 microsoft edge 开发人员或程序包，或使用 Linux 分发版的标准程序包管理工具。  

如果你在持续集成和传递 \ (CI/CD \ ) 解决方案中使用 Linux 环境，则在 Linux 上也可以使用 Microsoft Edge 驱动程序。  若要开始使用 Microsoft Edge 驱动程序自动执行 Microsoft Edge 开发，请导航到 [Microsoft Edge 驱动程序下载页面][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]。  若要获取 Microsoft edge 开发人员和 Microsoft Edge 驱动程序的自动化帮助，请导航到 [使用 WebDriver (Chromium) 进行测试自动化][WebDriverChromiumMain]。  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="DevTools 在 Linux 上的 Microsoft Edge 中" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   DevTools 在 Linux 上的 Microsoft Edge 中  
:::image-end:::  

## 改进了 "问题" 工具中的 webhint 和平台提示  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

开放源代码工具 [webhint][WebhintMain]提供对网站和本地网页的实时反馈。  从 [Microsoft Edge 版本 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]开始，在 " [问题][DevtoolsIssuesIndex] " 工具中查看 webhint 反馈。  通过添加以下类别，" **问题** " 工具中显示的问题现在更易于查看。  

*   [辅助功能][WebhintUserGuideHintsAccessibility]  
*   [兼容性][WebhintUserGuideHintsCompatibility]  
*   [性能][WebhintUserGuideHintsPerformance]  
*   [陷阱][WebhintUserGuideHintsPitfalls]  
*   [PWA][WebhintUserGuideHintsPwa]  
*   [安全性][WebhintUserGuideHintsSecurity]  
    
现在，你可以使用新的复选框筛选出第三方问题。  筛选器功能可帮助你隐藏与第三方库或其他源中的代码相关的问题。  

为了帮助你查看 [webhint][WebhintMain]显示的问题，" **问题** " 工具现在显示以下信息。  

*   改进的代码段。  
*   指向其他相关面板的链接。  
*   指向帮助你解决网站中的问题的文档的链接。  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="问题工具" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   **问题** 工具  
:::image-end:::  

## 复合图层现在位于3D 视图中  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

现在，你可以将 **层** 内容与 z 索引值和文档对象模型（ (DOM \ ) ）可视化。  此功能可帮助你在不切换 [3d 视图][Devtools3dViewIndex] 和 **分层** 工具的情况下进行调试。  为了获得全面的可视化调试体验， [现在组合了3D 视图和复合图层][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="复合图层 窗格"::: lightbox="../../media/2020/11/experiments-layers.msft.png":::
   "**复合图层**" 窗格  
:::image-end:::  

## "样式" 窗格中的 CSS 变量定义  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

在 " **样式** " 窗格中， [CSS 变量][MdnUsingCssCustomProperties] 现在直接链接到每个定义。  选择变量以轻松查看或更改 CSS 变量定义。  在此示例中，DevTools 显示元素的 CSS 属性 `body` 。  若要显示 CSS 变量的变量定义 `--theme-body-background` ，请完成以下操作。  

1.  在 " **样式** " 窗格中，选择 `var(--theme-body-background)` 。  
1.  " **样式** " 窗格现在显示了 `--theme-body-background` CSS 变量的定义。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="链接到样式的 CSS 变量" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         链接到样式的 CSS 变量  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="链接到样式目标的 CSS 变量" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         链接到样式目标的 CSS 变量  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 服务工作人员调试改进  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

[网络](#network-tool)、[应用程序](#application-tool)和[源](#sources-tool)工具中的以下新增功能可帮助你构建[PWA][ProgressiveWebAppsChromiumIndex]。  如果在调试服务工作人员时遇到困难，请使用以下功能。  

请求路由显示 `startup` `fetch` 基于通过服务工作人员运行的网络请求的和事件。  可从 " **应用程序** " 或 " **网络** " 工具访问时间线。  时间线可帮助你在服务工作人员遇到问题时希望查看是否有某些内容出现错误 `startup` `fetch` 。  

### 应用程序工具  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

查看 "新的 **网络请求** " 链接中的所有服务工作人员请求路由信息。  若要在调试服务工作人员时显示其他上下文，请完成以下操作。  

1.  导航到**应用程序**  >  **服务工作人员**。  
1.  选择 " **网络请求**"。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="从 服务工作人员 窗格打开网络工具"::: lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       从 "**服务工作人员**" 窗格打开**网络**工具
    :::image-end:::  
    
1.  **网络**工具将在**抽屉**中打开，并显示与服务工作人员相关的所有网络请求。  将使用筛选网络请求 `is:service-worker-intercepted` 。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="抽屉中的网络工具" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       **抽屉**中的**网络**工具  
    :::image-end:::
    
1. 若要将 **网络** 工具恢复到顶部面板，请关闭 **抽屉**。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="关闭抽屉以返回网络工具" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       关闭 **抽屉** 以返回 **网络** 工具  
    :::image-end:::  
    
### 网络工具  

通过服务工作人员调试运行的网络请求。  您也可以从 " **应用程序** " 工具打开网络请求。  对于每个请求，DevTools 在 [计时][DevtoolsNetworkReferenceViewTimingBreakdownRequest] 窗格中显示以下信息。  

*   请求的开始时间和引导的持续时间。  
*   对服务工作人员注册的更改。  
*   `fetch`事件处理程序的运行时。  
*   `fetch`用于加载客户端的所有事件的运行时。  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="计时窗格" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   **计时** 窗格  
:::image-end:::  

### 源工具  

在早期版本的 Microsoft Edge 中，调用堆栈中的深度级别限制为服务工作人员中的 JavaScript 代码。  在 Microsoft Edge 88 中，调用堆栈现在显示通过您的服务工作者运行的请求的发起者。  

若要找到请求的发起程序，请使用服务工作人员中的 JavaScript 代码的调用堆栈。  下图中的调用堆栈从你的服务工作人员的 JavaScript 代码开始，并将对原始网页请求的引用显示为 `(index):157` 。  在第二个图中，将选择该引用并打开发出请求的发起程序。  第二个图中的发起方是网页。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="service-worker.js 文件和调用堆栈突出显示请求原始发件人" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         `service-worker.js`文件和调用堆栈的突出显示请求原始发件人  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text=" (索引) 网页是请求发起方" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         该 `(index)` 网页是请求发起方  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 复制网络请求的属性值  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

在 " **网络** " 工具中，使用新的 " **复制值** " 选项复制网络请求的属性值。  将该属性值复制为解码后的 JSON 值。  在早期版本的 Microsoft Edge 中，你必须使用下列操作之一复制值。  

*   突出显示整个文本并进行复制。  
*   将值存储为全局变量（如果适用），并从 DevTools [控制台][DevtoolsConsoleIndex]复制它。  
    
若要将属性值复制到剪贴板，请导航到 [剪贴板上的 "将已设置格式的响应 JSON 复制到剪贴板"][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]。  若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1132084][CR1132084]"。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="在 DevTools 中复制属性值" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         在 DevTools 中复制属性值  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="在 Visual Studio 代码中粘贴属性值" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         在 Visual Studio 代码中粘贴属性值  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 自定义多路键盘快捷方式  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

[由于 Microsoft Edge 版本 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]，你可以为 DevTools 中的任何操作自定义键盘快捷方式。  在 Microsoft Edge 版本88中，你现在可以创建多个键盘快捷方式。  若要在 DevTools 中设置操作的快捷方式，请导航到 "[设置][DevtoolsCustomizeIndexSettings]  >  **试验**"，然后选中 "**启用键盘快捷方式编辑器**" 旁边的复选框。  有关自定义和编辑快捷方式的详细信息，请导航以 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

例如，红色突出显示将显示为 " **开始录制事件** " 操作自定义的多点键盘快捷方式。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 " [问题 #174309][CR174309]"。  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="Chords 键盘快捷方式" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   多按键盘快捷方式  
:::image-end:::  

## 来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 新的 CSS 角度可视化工具  

DevTools 现在对 CSS 角度调试有更好的支持。  当页面上的 HTML 元素应用了 CSS 角度时，" **样式** " 工具中的角度旁边将显示一个时钟图标。  若要切换时钟覆盖，请选择时钟图标。  若要更改角度，请选择时钟中的任意位置或拖动 "针"。  若要更改 angle 值，您还可以使用鼠标和键盘快捷方式。  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1126178][CR1126178] 和 [1138633][CR1138633]"。  

<!--todo:  add link when css angle clock section exists.  -->  

此示例使用以下 CSS 角度。  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS 角度" lightbox="../../media/2020/11/css-angle.msft.png":::
   CSS 角度  
:::image-end:::  

### 在 "存储" 窗格中模拟存储配额大小  

您现在可以在 " **存储** " 窗格中覆盖存储配额大小。  此功能允许你模拟不同的设备，并在较少的磁盘可用性方案中测试你的网站或应用的行为。  若要模拟存储配额，请完成以下操作。  

1.  导航到 "**应用程序**  >  **存储**"。  
1.  打开 " **模拟自定义存储配额** " 复选框。  
1.  输入一个有效号码。  
    
有关如何在 DevTools 中模拟移动设备和其他功能的详细信息，请导航以 [模拟 Microsoft Edge DevTools 中的移动设备 ][DevtoolsDeviceModeIndex]。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [945786][CR945786] 和 [1146985][CR1146985]"。  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="模拟存储配额大小" lightbox="../../media/2020/11/storage-quota.msft.png":::
   模拟存储配额大小  
:::image-end:::  

### 报告网络工具中的 CORS 错误  

通过导航到 [CORS 错误演示][GlitchCorsErrors]来试用此功能。  打开 " **网络** " 工具，刷新页面，并观察失败的 CORS 网络请求。  "状态" 列显示 **CORS 错误**。  当您悬停在错误上时，工具提示现在显示错误代码。  在 Microsoft Edge 版本87及更早版本中，DevTools 仅显示的通用 ** (失败) ** CORS 错误的状态。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1141824][CR1141824]"。  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS 错误" lightbox="../../media/2020/11/cors-err.msft.png":::
   CORS 错误  
:::image-end:::  

### 框架详细信息视图更新  

#### "框架详细信息" 视图中的跨源隔离信息  

跨原始隔离状态现在显示在 " **安全 & 隔离** " 部分下方。  新的 **API 可用性** 部分显示 `SharedArrayBuffer` s (SAB \ ) 的可用性，以及是否可以使用共享缓冲区 `postMessage()` 。  如果 SAB 和 `postMessage()` 当前可用，但上下文不是跨原点隔离的，则会显示一个弃用警告。  有关跨源隔离以及其功能（如有必要）的详细信息 `SharedArrayBuffers` ，请导航到 [WindowOrWorkerGlobalScope crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated]。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1139899][CR1139899]"。  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="跨源信息" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   跨源信息  
:::image-end:::  

#### "帧详细信息" 视图中的新 Web 工作人员信息  

DevTools 现在将 web 工作者组织在相关的父框架下。  例如，如果创建了 `someName` 框架 `worker.js` ，则 `worker.js` 会显示在 `someName` " **框架** " 列表中的 "下"。  若要查看 web 工作人员的详细信息，请完成以下操作。  

1.  打开 **应用程序** 工具。  
1.  展开包含 web 工作人员的帧。  
1.  展开 " **辅助进程** " 树。  
1.  选择一个工作人员。  
    
若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1122507][CR1122507] 和 [1051466][CR1051466]"。  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web 工作人员信息" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   Web 工作人员信息  
:::image-end:::  

#### 显示打开的窗口的 opener 帧详细信息  

DevTools 现在将在相关父[框架][MdnWindowFrames]下组织打开的[窗口][MdnWindowConstructors]。  例如，如果 `top` 框架打开 `Window` 到 `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium` ，则显示在 " `Window` `top` **帧** " 列表中的 "下"。  

若要显示负责在 " **元素** " 工具中打开另一个窗口的帧，请完成以下操作。  

1.  打开 " **框架** 树"。  
1.  展开 **打开的窗口** ，然后选择 `Window` 要了解的父框架。  
1.  选择 " **Opener Frame** " 链接。  

显示有关导致打开另一个帧的帧的详细信息 `Window` 。  若要在 " **元素** " 工具中显示 opener，请完成以下操作。  

1.  打开 " **框架** 树"。  
1.  选择打开的窗口以打开 `Window` 详细信息。  
1.  选择 " **Opener Frame** " 链接。  
    
若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1107766][CR1107766]"。  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="打开的帧详细信息" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   打开的帧详细信息  
:::image-end:::  

### 为网络启动器复制 stacktrace  

若要将 stacktrace 复制到剪贴板，请完成以下操作。  

1.  打开上下文菜单 \ (右键单击 \ ) 。  
1.  选择 "**复制**  >  **副本 stacktrace**"。  
    
若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1139615][CR1139615]"。

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="复制 stacktrace" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   复制 stacktrace  
:::image-end:::  

### 在悬停时预览 Wasm 变量值  

使用此功能可在代码暂停时查看 WebAssembly \ (Wasm \ ) 变量的值。  若要显示变量的当前值，请将鼠标悬停在变量上。  若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1058836][CR1058836] 和 [1071432][CR1071432]"。  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="在悬停时预览 Wasm 变量" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   在悬停时预览 Wasm 变量  
:::image-end:::  

### 文件和内存大小的一致度量单位  

DevTools 现在一直用于 `kB` 显示文件和内存的大小。  以前 DevTools 混合 `kB` 和 `KiB` 。

*   `kB` 或 kb \ (10 ^ 3 或1000字节 \ )   
*   `KiB` 或 kibibyte \ (2 ^ 10 或1024字节 \ )   
    
例如，以前在标签中使用的 **网络** 工具 `kB` ，但 `KiB` 在计算中使用。  您的反馈表明这种不一致会造成混淆。  若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1035309][CR1035309]"。  

## 下载 Microsoft Edge 预览频道  

如果你在 Windows、Linux 或 macOS 上，请考虑使用 [Microsoft Edge 预览频道] [MicrosoftEdgePreviewChannels] 作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D 视图 |Microsoft 文档"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "控制台概述 |Microsoft 文档"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器-实验功能 |microsoft 文档"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "在3D 视图中打开合成图-实验功能 |Microsoft 文档"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "将带格式的响应 JSON 复制到剪贴板-网络分析参考 |Microsoft 文档"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "查看请求的计时细目-网络分析参考 |Microsoft 文档"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "使用 WebDriver (Chromium) 进行测试自动化 |Microsoft 文档"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用 |Microsoft 文档"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/10/devtools#customize-keyboard-shortcuts-in-settings "在 "设置" 中自定义键盘快捷方式-DevTools 中的新增功能 (Microsoft Edge 87) |Microsoft 文档"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools#webhint-feedback-in-the-issues-panel ""问题" 面板中的 webhint 反馈-DevTools (Microsoft Edge 85) 中的新增功能 |Microsoft 文档"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver |Microsoft 开发人员"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "下载 Microsoft Edge 预览体验成员频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR174309]: https://crbug.com/174309 "问题174309： DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"  
[CR945786]: https://crbug.com/945786 "问题945786： DevTools：允许替代导航器。估计 ( # A1 |Chromium bug"  
[CR1029427]: https://crbug.com/1029427 "问题1029427：减少了在前端的协议消息调度的性能开销Chromium bug"  
[CR1035309]: https://crbug.com/1035309 "问题1035309： DevTools 应始终使用 MB 来表示兆字节，而不是 mebibyte |Chromium bug"  
[CR1051466]: https://crbug.com/1051466 "问题1051466：在 DevTools | 中的支持合作基金/COEP 调试Chromium bug"  
[CR1058836]: https://crbug.com/1058836 "问题1058836： Wasm 调试方面的 UX 问题 |Chromium bug"  
[CR1071432]: https://crbug.com/1071432 "问题1071432：☂️ Wasm Basic 开发人员体验 |Chromium bug"  
[CR1107766]: https://crbug.com/1107766 "问题1107766：显示 "窗口" 生成的帧的相关信息。在框架树中打开 ( # A1 "|Chromium bug"  
[CR1122507]: https://crbug.com/1122507 "问题1122507：框架树视图中的 Surface worker 信息 |Chromium bug"  
[CR1126178]: https://crbug.com/1126178 "问题1126178：☂ DevTools： CSS <键入> 组件 |Chromium bug"  
[CR1130556]: https://crbug.com/1130556 "问题1130556： DevTools：测试图像回退 (仿真) |Chromium bug"  
[CR1132084]: https://crbug.com/1132084 "问题1132084：无法轻松复制 JSON 请求负载 |Chromium bug"  
[CR1136394]: https://crbug.com/1136394 "问题1136394： Flexbox 工具 |Chromium bug"  
[CR1138633]: https://crbug.com/1138633 "问题1138633： DevTools： CSS <角度> 组件应反映它在时钟背景中的驻留属性外观 |Chromium bug"  
[CR1139615]: https://crbug.com/1139615 "问题1139615：网络启动器可提供复制堆栈跟踪的功能 |Chromium bug"  
[CR1139899]: https://crbug.com/1139899 "问题1139899：在 "帧详细信息" 视图中报告封闭 API 可用性 |Chromium bug"  
[CR1139945]: https://crbug.com/1139945 "问题1139945： "样式" 面板中 flexbox CSS 属性的图标 |Chromium bug"  
[CR1141824]: https://crbug.com/1141824 "问题1141824：在 DevTools | 中改进 CORS 错误报告Chromium bug"  
[CR1144090]: https://crbug.com/1144090 "问题1144090：将弹性样式装饰器添加到元素树 |Chromium bug"  
[CR1146985]: https://crbug.com/1146985 "问题1146985：已清除的文本在 "开发工具" 窗口的 "存储" 部分的文本框中仍然可见 |Chromium bug"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS 错误 |故障"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "跨源资源共享 (CORS) |MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性 (变量) |MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "构造函数-窗口 |MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "窗口。框架 |MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope crossOriginIsolated |MDN"  

[WebhintMain]: https://webhint.io "webhint"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "辅助功能 |webhint"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "兼容性 |webhint"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "性能 |webhint"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "缺陷 |webhint"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA |webhint"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "安全性 |webhint"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/updates/2020/11/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
