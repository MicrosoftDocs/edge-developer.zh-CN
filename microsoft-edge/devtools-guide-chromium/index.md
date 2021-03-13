---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 29ded7376ab1788998acf059c6677916a52d5d15
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408274"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a>Microsoft Edge (Chromium) 开发人员工具概述  

Microsoft Edge 已采用 Chromium 开放源代码项目。  新的 Microsoft Edge 浏览器可提供更好的 Web 兼容性并减少不同 Web 平台的碎片。  更改应该可以更轻松地在 Microsoft Edge 中生成和测试网页。  新的 Microsoft Edge 应在其他基于 Chromium 的浏览器中打开网页时帮助网页按预期运行。  基于 Chromium 的浏览器包括 Google Chrome、Vivaldi、Opera、Opera 和新的 Microsoft Edge。  

在不断扩展的设备类型数组中，Web 的使用已增长。  测试网页所涉及的复杂性和开销迅速增加。  需要针对许多不同的系统进行测试的 Web 开发人员。  为了确保网页在所有设备类型和浏览器中都运行良好，你可能会发现这几乎不可能，尤其是当你在一家小型公司工作时。  新的 Microsoft Edge 现在基于 Chromium。  Microsoft Edge 团队通过使 Microsoft Edge Web 平台与其他基于 Chromium 的浏览器保持一致来简化矩阵。  新的 Microsoft Edge 提供了一流的开发体验。  体验是在浏览器内以及你日常使用的其他开发人员工具（如 Visual Studio Code）中完成的。  

作为基于 Chromium 的浏览器开发人员，您应该熟悉新的 Microsoft Edge 浏览器。  Microsoft Edge \ (Chromium\) DevTools 与你已了解和使用的开发工具一样工作。  Microsoft Edge \ (Chromium\) 开发人员工具通常称为 Microsoft Edge \ (Chromium\) DevTools 或 DevTools。  有关详细信息，请导航到 Microsoft Edge 中的新增功能[ (Chromium) DevTools。][DevtoolsGuideChromiumWhatsNewIndex]  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

如果你之前为 Microsoft Edge \ (EdgeHTML\) 进行了评估，现在它提供了出色的新工具，方便你更轻松快速地生成和测试网页。  

## <a name="open-the-devtools"></a>打开 DevTools  

Microsoft Edge DevTools 是直接内置于 Microsoft Edge 浏览器的一组工具。  DevTools 允许你直接在浏览器中执行以下所有任务。  

*   检查 HTML 网页并进行更改  
*   编辑 CSS 并立即查看预览网页呈现的方式  
*   查看前端 `console.log()` JavaScript 代码的所有语句  
*   调试脚本、设置断点并逐行调试代码  
    
DevTools 提供的更多功能示例，使你在 Microsoft Edge 中生成和测试网页更轻松、更快。  

打开 DevTools  

*   选择 `F12` 
*   选择 `Ctrl` + `Shift` + `I` \ (Windows/Linux\) `Command` + `Option` + `I` 或 \ (macOS\)   
    
如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素并选择" **检查** "以跳转到 **"元素"** 工具。  若要在 Inspect 元素模式下打开**** DevTools，请选择 `Ctrl` + `Shift` + `C` \ (Windows/Linux\) 或 `Command` + `Option` + `C` \ (macOS\) 。 **使用 Inspect 元素模式**，可以选择网页上的元素，在"元素"工具中显示 HTML**和**CSS。  

如果要从前端 JavaScript 代码查看日志或快速运行某些脚本，请打开 **控制台**。   若要在**** DevTools 中启动控制台工具，请选择 `Ctrl` + `Shift` + `J` \ (Windows/Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  

## <a name="core-tools"></a>核心工具  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools 核心工具" lightbox="./media/devtools-core-tools.png":::
   Microsoft Edge (Chromium) DevTools 核心工具  
:::image-end::: 

Microsoft Edge \ (Chromium\) DevTools 包括以下工具。  

*   用于 **编辑** HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 破坏断点的元素工具  
*   用于 **查看** 和筛选日志消息、检查 JavaScript 对象和 DOM 节点，以及运行选定窗口或框架上下文中的 JavaScript 的控制台  
*   源 **工具** ，用于打开和编辑代码、设置断点、逐步执行代码并显示网页的状态
*   **用于**监视和检查来自网络和浏览器缓存的请求和响应的网络工具   
*   **性能工具**，用于配置文件网站所需的时间和系统资源  
*   内存 **工具** ，用于测量内存资源的使用，并比较代码运行时不同状态中的堆快照  
*   用于 **检查** 、修改和调试 Web 应用清单、服务工作者和服务工作器缓存的应用程序工具。  您还可以从应用程序工具检查和管理存储、数据库 **和** 缓存。  
*   **用于调试**安全问题并确保网页上正确实现 HTTPS 的安全工具。  HTTPS 为您的网站和在站点上提供个人信息的用户提供了关键的安全和数据完整性。  
*   审核 **工具** \ (现在重命名为 **Lighthouse**\) 以运行对网页的审核。  审核结果有助于通过以下方式提高网站质量。  
    *   捕获与使网页可访问性、安全性、性能高等相关的常见错误。  
    *   修复每个错误。  
    *   生成 PWA。  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

发送 [反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

## <a name="extensions"></a>Extensions  

生成网页 \ (或 apps\) 时，你可能会使用扩展访问 DevTools。 Microsoft Edge 扩展从 [Microsoft Edge 加载项获取][MicrosoftEdgeAddonsExtensions]。  在 [Microsoft Edge 加载项上][MicrosoftEdgeAddonsExtensions]，从开发人员工具类别浏览 DevTools **扩展或搜索** 特定扩展。  

还可以从 Chrome Web Store [添加扩展][GoogleChromeWebstoreExtensions]。  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge 中的 Chrome Web Store" lightbox="./media/allow-extensions-from-stores.png":::
   Microsoft Edge 中的 Chrome Web Store  
:::image-end:::  

At the top， choose **Allow extensions from other stores** and then choose **Allow** in the dialog that appears.  

> [!NOTE]
> 从 Microsoft Store 外的其他源安装的扩展未经验证，并且可能会影响浏览器性能。  

选择 **"添加到 Chrome"** 以将 DevTools 扩展添加到 Microsoft Edge。  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="将扩展从 Chrome Web Store 添加到 Microsoft Edge" lightbox="./media/install-extension-from-chrome-store.png":::
   将扩展从 Chrome Web Store 添加到 Microsoft Edge  
:::image-end:::  

## <a name="shortcuts"></a>快捷方式  

以下快捷方式控制主 DevTools 窗口、跨所有工具或同时使用两者。  

| 操作 | Windows/Linux | macOS |  
|:--- |:--- | :--- |  
| 显示/隐藏 DevTools \ (打开到上次查看的工具\)  | `F12` 或 `Ctrl`+`Shift`+`I` | `Command`+`Option`+`I` |  
| 显示控制台 | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 在 Inspect 元素模式下显示**** DevTools，该模式允许你选择元素，在元素工具**中显示**HTML 和 CSS | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| 显示设置 | `?` 或 `Fn`+`F1` | `?` 或 `Fn`+`F1` |  
| 显示下一个面板 | `Ctrl`+`]` | `Command`+`]` |  
| 显示上一个面板 | `Ctrl`+`[` | `Command`+`[` |  
| 将 DevTools 停靠在上次使用的位置。  如果 DevTools 保持整个会话的默认位置，快捷方式将 DevTools 撤消到单独的窗口中 | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| 切换 **设备模式** | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 切换 **检查元素模式** ，允许您选择元素，在"元素"工具 **中显示** HTML 和 CSS | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| 显示命令菜单 | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| 显示/隐藏箱 | `Esc` | `Esc` |  
| 刷新。  使用缓存刷新网页。  | `F5` 或 `Ctrl`+`R` | `Command`+`R` |  
| 硬刷新。  强制 Microsoft Edge 再次下载资源并重新加载。  使用的资源可能来自缓存版本 | `Ctrl`+`F5` 或 `Ctrl`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 在当前面板中搜索文本。  审核、应用程序和安全工具不支持 | `Ctrl`+`F` | `Command`+`F` |  
| 在"箱"中显示搜索工具，可让你搜索所有已加载资源中的文本 | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| 在"源"面板中打开文件 | `Ctrl`+`O` 或 `Ctrl`+`P` | `Command`+`O` 或 `Command`+`P` |  
| 放大 | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 缩小 | `Ctrl`+`-` | `Command`+`-` |  
| 还原默认缩放级别 | `Ctrl`+`0` | `Command`+`0` |  
| 运行代码段 | `Ctrl`+`O``Ctrl` + `P` 或 ， `!` 键入 后跟脚本名称，然后选择 `Enter` | 选择 `Command` + `O` 或 `Command` + `P` ， `!` 键入后跟脚本名称，然后选择 `Enter` |  
| 在新选项卡中显示不可编辑的 HTML 源代码 | `Ctrl`+`U` | 不适用 |  

> [!NOTE]
> 如果你正在调试并暂停在断点，则 **Refresh** 快捷方式将首先恢复运行时。  

## <a name="see-also"></a>另请参阅  

*   [适用于初学者的 DevTools：HTML 和 DOM 入门][DevtoolsGuideChromiumBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools 协议][DevtoolsProtocolChromiumIndex]  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

如果你想要预览 [DevTools][DevtoolsGuideChromiumWhatsNewIndex]中提供的最新功能，请下载 [Microsoft Edge Canary][MicrosoftedgeinsiderDownload]，它在夜间生成。  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "适用于初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2021/02/devtools "Microsoft Edge (DevTools) 中的新增|Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools 协议|Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展|Chrome Web Store"  
