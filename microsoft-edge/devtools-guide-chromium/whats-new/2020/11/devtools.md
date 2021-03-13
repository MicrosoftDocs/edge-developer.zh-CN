---
description: Linux 上的 Microsoft Edge、”问题“工具中改进的 Webhint 提示、新的服务工作线程调试功能等。
title: DevTools 中的新增功能 (Microsoft Edge 88)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6a36029aa97604b6aea20f232d329ce3805a3144
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408365"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-88"></a>DevTools 中的新增功能 (Microsoft Edge 88)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="microsoft-edge-and-microsoft-edge-driver-now-available-on-linux"></a>Microsoft Edge 和 Microsoft Edge 驱动程序现在可在 Linux 上使用  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

Microsoft Edge Dev 现已在 Ubuntu、Debian、Fedora 和 openSUSE 发行版上受到支持。  直接从 [Microsoft Edge 预览体验成员网站][MicrosoftinsiderDownloadPlatformLinux] 下载并安装 Microsoft Edge Dev `.deb` 或 `.rpm` 程序包，或使用 Linux 发行版的标准程序包管理工具。  

如果你在连续集成和交付\(CI/CD\) 解决方案中使用 Linux 环境，Microsoft Edge 驱动程序也可在 Linux 上使用。  若要开始使用 Microsoft Edge 驱动程序自动执行 Microsoft Edge Dev，请导航至 [Microsoft Edge 驱动程序下载页][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]。  有关自动执行 Microsoft Edge Dev 以及 Microsoft Edge 驱动程序的帮助，请导航到 [使用 WebDriver (Chromium) 测试自动化][WebDriverChromiumMain]。  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="Microsoft Edge Linux 版中的 DevTools" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   Microsoft Edge Linux 版中的 DevTools  
:::image-end:::  

## <a name="improved-webhint-and-platform-tips-in-the-issues-tool"></a>“问题”工具中改进的 Web 提示和平台提示  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

开源工具 [Webhint][WebhintMain] 为网站和本地网页提供实时反馈。  从 [Microsoft Edge 版本 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel] 开始，在 [问题][DevtoolsIssuesIndex] 工具中审阅 Webhint 反馈。  现在，通过添加以下类别，可以更轻松地审阅 **问题** 工具中出现的问题。  

*   [辅助功能][WebhintUserGuideHintsAccessibility]  
*   [兼容性][WebhintUserGuideHintsCompatibility]  
*   [性能][WebhintUserGuideHintsPerformance]  
*   [隐患][WebhintUserGuideHintsPitfalls]  
*   [PWA][WebhintUserGuideHintsPwa]  
*   [安全性][WebhintUserGuideHintsSecurity]  
    
你现在可以使用新复选框筛选出第三方问题。  筛选器功能可帮助你隐藏第三方库或其他源中与代码相关的问题。  

为帮助审阅 [Webhint][WebhintMain] 显示的问题，**问题** 工具现在显示以下信息。  

*   改进的代码段。  
*   指向其他相关面板的链接。  
*   指向文档的链接，可帮助你修复网站中的问题。  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="问题工具" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   **问题** 工具  
:::image-end:::  

## <a name="composited-layers-are-now-in-3d-view"></a>复合层现在采用 3D 视图  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

现在，你可以可视化显示 **Layers** 内容与 z-index 值和文档对象模型\ (DOM\)。  此功能可帮助你进行调试，无需在 [3D 视图][Devtools3dViewIndex] 和 **图层工具** 之间切换。  为获得全面的视觉调试体验， [已将3D 视图和复合层组合到一起][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   **复合层** 窗格  
:::image-end:::  

## <a name="css-variable-definitions-in-styles-pane"></a>“样式”窗格中的 CSS 变量定义  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

在 **样式** 窗格中，[CSS变量][MdnUsingCssCustomProperties] 现在直接链接到每个定义。  选择变量以轻松查看或更改 CSS 变量定义。  在示例中，DevTools 显示 `body` 元素的 CSS 属性。  若要显示 `--theme-body-background` CSS 变量的变量定义，请完成以下操作。  

1.  在 **样式** 窗格中，选择 `var(--theme-body-background)`。  
1.  **样式** 窗格现在显示 `--theme-body-background` CSS 变量的定义。  
    
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

## <a name="service-worker-debugging-improvements"></a>服务工作线程调试改进  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

[网络](#network-tool)、[应用程序](#application-tool) 和 [源](#sources-tool) 工具中的以下新功能可帮助您构建 [PWA][ProgressiveWebAppsIndex]。  在调试服务工作线程遇到困难时，请使用以下功能。  

请求路由显示基于通过服务工作线程运行的网络请求的 `startup` 和 `fetch` 事件。  通过 **应用程序** 或 **网络工具** 访问时间线。  当你遇到服务工作人员的问题，并且想要在 或 事件出错时显示时间线 `startup` `fetch` 帮助。  

### <a name="application-tool"></a>应用程序工具  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

通过新的 **网络请求**链接查看所有服务工作线程请求路由信息。  若要在调试服务工作线程时显示其他上下文，请完成以下操作。  

1.  导航到 **应用程序**  >  **服务工作线程**。  
1.  选择 **网络请求**。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="从“服务工作线程”窗格中打开“网络”工具" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       从 **服务工作线程** 窗格中打开 **网络** 工具
    :::image-end:::  
    
1.  **网络** 工具在 **工具箱** 中打开，并显示所有与服务工作线程相关的网络请求。  使用 `is:service-worker-intercepted` 筛选网络请求。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="工具箱中的网络工具" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       **工具箱** 中的 **网络** 工具  
    :::image-end:::
    
1. 若要将 **网络** 工具恢复到顶部面板，请关闭 **工具箱**。  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="关闭工具箱以返回网络工具" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       关闭 **工具箱** 以返回 **网络** 工具  
    :::image-end:::  
    
### <a name="network-tool"></a>网络工具  

调试通过服务工作线程运行的网络请求。  您还可以从 **应用程序** 工具打开网络请求。  对于每个请求，DevTools 在 [计时][DevtoolsNetworkReferenceViewTimingBreakdownRequest] 窗格中显示以下信息。  

*   请求开示和启动持续时间。  
*   对服务工作线程注册的更改。  
*   `fetch` 事件处理器的运行时。  
*   用于加载客户端的所有 `fetch` 事件的运行时。  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="计时窗格" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   **计时** 窗格  
:::image-end:::  

### <a name="sources-tool"></a>源工具  

在旧版 Microsoft Edge 中，调用堆栈的深度级别仅限于服务工作线程中的 JavaScript 代码。  在 Microsoft Edge 88 中，调用堆栈现在显示通过服务工作线程运行的请求发起程序。  

若要定位请求发起程序，请使用服务工作线程中 JavaScript 代码的调用堆栈。  下图中调用堆栈以服务工作线程中的 JavaScript 代码开头，并将对原始网页请求的引用显示为 `(index):157`。  第二个图中，选择引用并打开提出请求的发起程序。  第二个图中的发起程序是网页。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="此 service-worker.js 文件和调用堆栈突出显示请求原始发起程序。" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         `service-worker.js` 文件和调用堆栈突出显示请求原始发起程序  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text="（索引）网页是请求发起程序" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         `(index)` 网页是请求发起程序  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="copy-property-value-of-a-network-request"></a>复制网络请求的属性值  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

在 **网络** 工具中，使用新的 **复制值** 选项复制网络请求的属性值。  将属性值复制为解码的 JSON 值。  在旧版 Microsoft Edge 中，必须执行下列操作之一复制值。  

*   突出显示并复制整个文本。  
*   将值存储为全局变量（如果适用），然后从 DevTools [控制台][DevtoolsConsoleIndex] 将其复制。  
    
若要将属性值复制到剪贴板，导航至 [复制格式化响应 JSON 到剪贴板][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]。  若要审阅 Chromium 开源项目中此功能的历史记录，请导航至问题[1132084][CR1132084]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="在 DevTools 中复制属性值" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         在 DevTools 中复制属性值  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="将属性值粘贴到 Microsoft Visual Studio Code 中" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         将属性值粘贴到 Microsoft Visual Studio Code 中  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="customize-multi-press-keyboard-shortcuts"></a>自定义多键连发键盘快捷方式  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

[自 Microsoft Edge 版本 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings] 起，可以为 DevTools 中任何操作自定义键盘快捷方式。  在 Microsoft Edge 版本 88 中，现在可以创建多键连发快捷方式。  若要在 DevTools 中为某个操作设置快捷方式，请导航至 [设置][DevtoolsCustomizeIndexSettings] > **实验**，并选中 **启用键盘快捷方式编辑器** 旁边的复选框。  有关自定义和编辑快捷方式详细信息，请导航至 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。  

例如，红色高亮显示的是为 **开始录制事件** 操作而自定义的多键连发键盘快捷方式。  若要在 Chromium 开源项目中查看此功能实时更新，请导航至 [问题 #174309][CR174309]。  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="和弦键盘快捷方式" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   多键连发键盘快捷方式  
:::image-end:::  

## <a name="devtools-now-match-browser-language"></a>DevTools 现已匹配浏览器语言  

在 Microsoft Edge 版本 87 中，如果在 [DevTools 设置][DevtoolsCustomizeIndexSettings] 中打开 **匹配浏览器语言** 设置，则 DevTools 不会匹配浏览器语言。  在 Microsoft Edge 版本 88 中，如果打开 **匹配浏览器语言** 设置，则 DevTools 现在与浏览器语言匹配。  有关 **Match 浏览器语言** DevTools 设置的详细信息，请导航至 [更改 DevTools 语言设置][DevtoolsCustomizeLocalization]。  

:::image type="complex" source="../../media/2020/11/startpage-devtools-settings-japanese.msft.png" alt-text="匹配浏览器语言 DevTools 设置（日语）" lightbox="../../media/2020/11/startpage-devtools-settings-japanese.msft.png":::
   **匹配浏览器语言** DevTools 设置（日语）  
:::image-end:::  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-css-angle-visualization-tools"></a>全新 CSS 角度可视化工具  

现在，DevTools 可以更好地支持 CSS 角度调试。  如果页面上 HTML 元素应用 CSS 角度，**样式** 工具中该角度旁边会显示一个时钟图标。  若要切换时钟覆盖层，请选择时钟图标。  若要更改角度，请选择时钟中的任何位置或拖动指针。  若要更改角度值，还可使用鼠标和键盘快捷方式。  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  若要在 Chromium 开源项目中查看此功能实时更新，请导航到“问题” [1126178][CR1126178] 和 [1138633][CR1138633]。  

<!--todo:  add link when css angle clock section exists.  -->  

示例使用了以下 CSS 角度。  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS 角度" lightbox="../../media/2020/11/css-angle.msft.png":::
   CSS 角度  
:::image-end:::  

### <a name="simulate-storage-quota-size-in-the-storage-pane"></a>模拟存储窗格中的存储配额大小  

现在，可以在 **存储** 窗格中重写存储配额大小。  此功能允许你模拟不同的设备，并测试网站或应用在低磁盘可用性场景中的行为。  若要模拟存储配额，请完成以下操作。  

1.  导航至 **应用程序** > **存储**。  
1.  打开 **模拟自定义存储配额** 复选框。  
1.  输入有效号码。  
    
若要了解如何在 DevTools 中模拟移动设备和其他功能的详细信息，请导航至 [在 Microsoft Edge DevTools 中模拟移动设备移动设备][DevtoolsDeviceModeIndex]。  若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [945786][CR945786] 和 [1146985][CR1146985]。  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="模拟存储配额大小" lightbox="../../media/2020/11/storage-quota.msft.png":::
   模拟存储配额大小  
:::image-end:::  

### <a name="report-cors-errors-in-the-network-tool"></a>报告网络工具中的 CORS 错误  

通过导航至 [CORS 错误演示][GlitchCorsErrors] 尝试此功能。  打开 **网络** 工具，刷新页面，并观察失败的 CORS 网络请求。  状态列显示 **CORS 错误**。  将鼠标悬停在错误上时，工具提示现在将显示错误代码。  在 Microsoft Edge 版本 87 及更早版本中，DevTools 只显示CORS 错误的一般 **（失败）** 状态。  若要审阅 Chromium 开源项目中此功能的实时更新，请导航至问题[1141824][CR1141824]。  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS 错误" lightbox="../../media/2020/11/cors-err.msft.png":::
   CORS 错误  
:::image-end:::  

### <a name="frame-details-view-updates"></a>框架详细信息视图更新  

#### <a name="cross-origin-isolation-information-in-the-frame-details-view"></a>框架详细信息视图中的跨域隔离信息  

现在，跨域隔离状态在 **安全性和隔离** 区域下显示。  新的 **API 可用性** 区域显示 `SharedArrayBuffer` \ (\) 的可用性，以及是否可以使用 `postMessage()` 共享缓冲区。  弃用警告显示 SAB 和 `postMessage()` 当前是否可用，但上下文并非跨域隔离。  有关跨域隔离以及为何需要如 `SharedArrayBuffers` 一样的功能的详细信息 ，请导航至 [WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated]。  若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [1139899][CR1139899]。  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="跨域信息" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   跨域信息  
:::image-end:::  

#### <a name="new-web-workers-information-in-the-frame-details-view"></a>框架详细信息视图中的新 Web 工作线程信息  

现在，DevTools 在相关的父框架下组织 Web 工作线程。  例如，如果 `someName` 框架创建 `worker.js`，则 `worker.js` 出现在 **框架** 列表中的 `someName` 之下。  若要查看 web 工作线程的详细信息，请完成以下操作。  

1.  打开 **应用程序** 工具。  
1.  展开包含 web 工作线程的框架。  
1.  展开 **工作线程** 树。  
1.  选择工作线程。  
    
若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [1122507][CR1122507] 和 [1051466][CR1051466]。  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web 工作线程信息" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   Web 工作线程信息  
:::image-end:::  

#### <a name="display-opener-frame-details-for-opened-windows"></a>显示已打开窗口的原框架详细信息  

现在，DevTools 在相关的父 [框架][MdnWindowFrames] 下组织已打开的 [窗口][MdnWindowConstructors]。  例如，如果 `top` 框架打开 `Window` 到 `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium`， 则框架 `Window` 将显示在 **列表** 中的 `top` 之下。  

若要显示负责在 **元素** 工具中打开另一个窗口的框架，请完成以下操作。  

1.  打开 **框架** 树。  
1.  展开 **已打开窗口**，然后选择 `Window` 选取希望了解 的父框架。  
1.  选择 **原框架** 链接。  

将显示有关哪个框架导致另一个 `Window` 打开的详细信息。  若要在 **元素** 工具中显示原框架，请完成以下操作。  

1.  打开 **框架** 树。  
1.  选择已打开窗口以打开 `Window` 详细信息。  
1.  选择 **原框架** 链接。  
    
若要查看 Chromium 开源项目中此功能的历史记录，请导航到问题 [1107766][CR1107766]。  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="已打开框架的详细信息" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   已打开框架的详细信息  
:::image-end:::  

### <a name="copy-stacktrace-for-network-initiator"></a>复制网络发起程序堆栈跟踪  

若要将堆栈跟踪复制到剪贴板，请完成以下操作。  

1.  打开上下文菜单\（右键单击\）。  
1.  选择 **复制** > **复制堆栈跟踪**。  
    
若要查看 Chromium 开源项目中此功能的历史记录，请导航至问题 [1139615][CR1139615]。

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="复制堆栈跟踪" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   复制堆栈跟踪  
:::image-end:::  

### <a name="preview-wasm-variable-value-on-mouseover"></a>鼠标悬停时预览 Wasm 变量值  

代码暂停时，使用此功能检查 WebAssembly\(Wasm\) 变量的值。  若要显示变量的当前值，请将鼠标悬停在变量上。  若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [1058836][CR1058836] 和 [1071432][CR1071432]。  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="鼠标悬停时预览 Wasm 变量" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   鼠标悬停时预览 Wasm 变量  
:::image-end:::  

### <a name="consistent-units-of-measurement-for-sizes-of-files-and-memory"></a>文件和内存大小的一致度量单位  

现在，DevTools 始终使用 `kB` 显示文件和内存的大小。  以前的 DevTools 混合 `kB` 和 `KiB`。

*   `kB` 或千字节\（10^3 或 1000 字节\）  
*   `KiB` 或 kibibyte \（2^10 或 1024 字节\）  
    
例如，**网络** 工具以前在标签中使用 `kB`，但在计算中使用 `KiB`。  您的反馈表明这种前后矛盾导致混淆。  若要查看 Chromium 开源项目中此功能的历史记录，请导航至问题 [1035309][CR1035309]。  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [Microsoft Edge 预览][MicrosoftEdgePreviewChannels] 通道作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D 视图 | Microsoft Docs"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "控制台概述 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeLocalization]: /microsoft-edge/devtools-guide-chromium/customize/localization "更改 DevTools 语言设置 | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器 - 实验功能 | microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "在 3D 视图中打开复合层 - 实验功能 | Microsoft Docs"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "将格式化的响应 JSON 复制到剪贴板 - 网络分析参考 | Microsoft Docs"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "查看请求的时间分析 - 网络分析参考 | Microsoft Docs"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "使用 WebDriver (Chromium) 测试自动化 | Microsoft Docs"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用 | Microsoft Docs"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: ../10/devtools.md#customize-keyboard-shortcuts-in-settings "在“设置”中自定义键盘快捷方式 - DeVTools 的新增功能 (Microsoft Edge 87)| Microsoft Docs"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: ../06/devtools.md#webhint-feedback-in-the-issues-panel "问题面板中的 webhint 反馈 - DeVTools 的新增功能 (Microsoft Edge 85) | Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver | Microsoft 开发人员"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "问题 174309：DevTools：允许自定义键盘快捷方式/键绑定 | Chromium 漏洞"  
[CR945786]: https://crbug.com/945786 "问题 945786：DevTools：允许替代 navigator.storage.estimate () | Chromium 漏洞"  
[CR1029427]: https://crbug.com/1029427 "问题 1029427：减少前端协议消息调度的性能开销 | Chromium 漏洞"  
[CR1035309]: https://crbug.com/1035309 "问题 1035309：DevTools 应始终使用 MB 而不是 mebibyte 表示兆字节 | Chromium 漏洞"  
[CR1051466]: https://crbug.com/1051466 "问题 1051466：在 DevTools 中支持 COOP/COEP 调试 | Chromium 漏洞"  
[CR1058836]: https://crbug.com/1058836 "问题 1058836：关于 Wasm 调试的 UX 问题 | Chromium 漏洞"  
[CR1071432]: https://crbug.com/1071432 "问题 1071432：☂️ Wasm 基本开发人员体验 | Chromium Bug"  
[CR1107766]: https://crbug.com/1107766 "问题 1107766：显示有关框架树中的 "window.open ()" 生成的框架的信息 |Chromium 漏洞"  
[CR1122507]: https://crbug.com/1122507 "问题 1122507：框架树视图中的 Surface 工作线程信息 | Chromium 漏洞"  
[CR1126178]: https://crbug.com/1126178 "问题 1126178：☂ DevTools：CSS <类型> 组件 | Chromium 漏洞"  
[CR1130556]: https://crbug.com/1130556 "问题 1130556：DevTools：测试映像回退（模拟） | Chromium 漏洞"  
[CR1132084]: https://crbug.com/1132084 "问题 1132084：无法轻松复制 JSON 请求有效负载 | Chromium 漏洞"  
[CR1136394]: https://crbug.com/1136394 "问题 1136394：Flexbox 工具 | Chromium 漏洞"  
[CR1138633]: https://crbug.com/1138633 "问题 1138633：DevTools：CSS <角度> 组件应反映其驻留属性在时钟背景中的外观 | Chromium 漏洞"  
[CR1139615]: https://crbug.com/1139615 "问题 1139615：网络发起程序应提供复制堆栈跟踪的能力 | Chromium 漏洞"  
[CR1139899]: https://crbug.com/1139899 "问题 1139899：在框架详细信息视图中报告封闭的 API 的可用性 | Chromium 漏洞"  
[CR1139945]: https://crbug.com/1139945 "问题 1139945：样式面板中弹性框 CSS 属性的图标 | Chromium 漏洞"  
[CR1141824]: https://crbug.com/1141824 "问题 1141824：改进 DevTools 中的 CORS 错误报告 | Chromium 漏洞"  
[CR1144090]: https://crbug.com/1144090 "问题 1144090：将弹性样式修饰器添加到元素树 |Chromium 漏洞"  
[CR1146985]: https://crbug.com/1146985 "问题 1146985：清除的文本仍显示于 Dev Tools 窗口的“存储”部分文本框中 | Chromium 漏洞"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS 错误 | 小故障"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "跨域资源共享 (CORS) | MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性（变量）| MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "构造函数 - 窗口 | MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "Window.frames | MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope.crossOriginIsolated | MDN"  

[WebhintMain]: https://webhint.io "webhint"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "辅助功能 | webhint"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "兼容性 | webhint"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "性能 | webhint"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "隐患 | webhint"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA | webhint"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "安全 | webhint"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/updates/2020/11/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
