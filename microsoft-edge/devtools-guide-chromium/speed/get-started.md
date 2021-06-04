---
description: 了解如何使用 Microsoft Edge 开发人员工具找到加快网站加载速度的方法。
title: 使用 Microsoft Edge 开发人员工具优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 304cf9e36260b8637af38ed0dfe1ba91f3a56504
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564880"
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
# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a>使用 Microsoft Edge 开发人员工具优化网站速度  

## <a name="goal-of-tutorial"></a>教程目标  

本教程将指导你如何使用 Microsoft Edge 开发人员工具找到加快网站加载速度的方法。  

## <a name="prerequisites"></a>必备条件  

*   你应具备基本的 Web 开发体验，类似此[Web 开发类简介][CourseraIntroductionWebDevelopmentClass]中所教授的内容。  
*   你无需了解加载性能的任何信息。  本教程中将帮助你了解。  

## <a name="introduction"></a>简介  

这是 Tony。  Tony 在猫界很有名。  他生成了一个网站，让粉丝能够了解他最喜爱的食物。  虽然粉丝们很喜欢这个网站，但 Tony 不断听到有关网站加载缓慢的抱怨。  Tony 要求你帮忙加快站点速度。  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony 猫" lightbox="../media/speed-tony.msft.png":::
   Tony 猫  
:::image-end:::  

## <a name="step-1-audit-the-site"></a>步骤 1：审核站点  

无论何时开始改进站点的加载性能，**始终都从审核开始**。  
审核包含 2 个重要功能：  

*   创建**基线**，便于参照并测量后续更改。  
*   提供有关哪些更改最具影响的**可操作提示**。  
    
### <a name="set-up"></a>设置  

首先，你必须设置站点，便于之后进行更改。  

1.  [打开站点的源代码](https://glitch.com/edit/#!/tony)。  此选项卡称为**编辑器选项卡**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="编辑器选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       **编辑器选项卡**  
    :::image-end:::  
    
1.  选择 **tony**。  将显示菜单。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="选择 tony 后显示的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       选择**tony**后显示的菜单  
    :::image-end:::  
    
1.  选择**合成项目**。  项目名称从**tony** 更改为随机生成的名称。  现在，你拥有了自己的可编辑代码副本。  稍后，你可以对此代码进行更改。  
1.  选择**显示**，然后选择**在新窗口中**。  演示将在新选项卡中打开。 此选项卡称为**演示选项卡**。 站点加载可能需要一段时间。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="演示选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       演示选项卡  
    :::image-end:::  
    
1.  选择 `Control` + `Shift` + `J` \(Windows、Linux\) 或 `Command` + `Option` + `J` \(macOS\)。  Microsoft Edge 开发人员工具将在演示旁边打开。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="开发人员工具和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       开发人员工具和演示  
    :::image-end:::  
    
对于本教程中的其余屏幕截图，开发人员工具显示在单独窗口中。  选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)，打开“命令菜单”，键入`Undock` ，然后选择**移除进单独窗口**。  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="移除的开发人员工具" lightbox="../media/speed-console.msft.png":::
   移除的开发人员工具  
:::image-end:::  

### <a name="establish-a-baseline"></a>建立基线  

基线是指在改进性能之前有关站点执行情况的记录。  

1.  选择**审核**工具。  它可能隐藏在**更多面板** \(![More Panels](../media/more-panels-icon.msft.png)\) 按钮的后面。  此面板包含"灯塔"，因为支持“审核”面板的项目名为**灯塔**。  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="审核工具" lightbox="../media/speed-audits-performance.msft.png":::
       **审核**工具  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  将审核配置设置与上图中的设置相匹配。  以下是不同选项的说明：  
    
    *   **设备**。  设置为**移动**，更改用户代理字符串并模拟移动视口。  设置为**桌面**，几乎可以关闭**移动**更改。  
    *   **审核**。  关闭类别可以防止**审核**面板运行这些审核，并在报告中相应排除。  如果希望显示提供的建议类型，请保留其他类别为"打开"。  关闭类别可以略微加快审核流程。  
    *   **限制**。  设置为**模拟慢速 4G、4x CPU 减速**，模拟在移动设备上浏览的典型条件。  命名为"模拟"是因为“审核”面板在审核流程中实际上并未进行限制。  相反，它只是推断移动条件下加载页面花费的时间。  另一方面，**应用...** 设置实际上会限制 CPU 和网络，折衷了较长的审核流程。  
    *   **清除存储**。  打开复选框，在每次审核前清除与页面相关的所有存储。  如果希望审核站点首次访问者的体验，请保留此设置。  希望重复访问体验时，请关闭此设置。  
    
1.  选择**运行审核**。  10 到 30 秒后，**审核**面板将显示站点性能报告。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="站点性能审核面板报告" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       站点性能审核面板报告  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a>处理报告错误  

如果你曾在“审核”面板报告中收到错误，请尝试从**InPrivate**窗口运行演示选项卡，且不打开其他选项卡。  这可以确保在干净状态运行 Microsoft Edge。  尤其是，Microsoft Edge 扩展经常会干扰审核流程。  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a>了解报告  

报告顶部的数字是站点的总体性能分数。  稍后，当你对代码进行更改时，显示的数字应上升。  分数越高表示性能越好。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="总体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   总体性能分数  
:::image-end:::  

**指标**部分提供站点性能的定量测量。  每个指标提供对性能不同方面的见解。  例如，**首次内容绘制**会告知内容首次绘制到屏幕的时间，这是用户感知页面加载的重要里程碑，而**可交互时间**则会标记页面似乎准备就绪，足以处理用户交互的时间点。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text="指标部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   **指标**部分  
:::image-end:::  

选择下图中突出显示的切换按钮，显示每个指标的说明，然后选择 **了解更多信息**，阅读相关文档。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮，展开指标项" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   选择突出显示的切换按钮，展开指标项  
:::image-end:::  

以下"指标"是页面加载外观屏幕截图的集合。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="页面加载外观屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   页面加载外观屏幕截图  
:::image-end:::  

**机会**部分提供如何改进此特定页面加载性能的特定提示。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="机会部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   **机会**部分  
:::image-end:::  

选择某个机会，了解更多相关信息。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除阻止渲染资源机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   **消除阻止渲染资源**机会  
:::image-end:::  

选择 **了解更多信息**，显示说明机会为什么重要的文档，以及如何修复机会的特定建议。  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="消除阻止渲染资源机会的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   消除**阻止渲染资源机会**的文档  
:::image-end:::  

**诊断**部分提供影响页面加载时间的因素的详细信息。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="诊断部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   **诊断**部分  
:::image-end:::  

**通过审核**部分显示站点正确执行的内容。  选择并展开此部分。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text="通过审核部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   **通过审核** 部分  
:::image-end:::  

## <a name="step-2-experiment"></a>步骤 2：试验  

审核报告中的机会部分提供如何改进页面性能的提示。  在此部分，你将对基本代码实施建议性更改，并在每次更改后审核站点，从而测量更改对站点速度的影响。  

### <a name="enable-text-compression"></a>启用文本压缩  

你的报告表明，避免大量网络负载是改进页面性能的一个首要机会。  启用文本压缩是改进页面性能的机会。  

文本压缩是指在网络上发送文本文件之前，减少或压缩文本文件的大小。  类似于如何在发送目录前进行存档，从而减少目录大小。  

在启用压缩前，以下是手动检查文本资源是否压缩的几种方法。  

1.  选择**网络**工具。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="网络面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       **网络**工具  
    :::image-end:::  
    
1.  选择**网络设置**图标。  
1.  选择**使用大请求行**复选框。  网络请求表中行的高度将增加。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的大行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       网络请求表中的大行  
    :::image-end:::  
    
1.  如果网络请求表中的**大小**未显示，请选择表头 > **大小**。  

每个**大小** 单元格将显示两个值。  顶部值是已下载资源的大小。  
底部值是未压缩资源的大小。  如果这两个值相同，则表示在网络中发送资源时，资源未被压缩。  例如，在上图中，`bundle.js`顶部和底部的值为`1.2 MB`和`1.2 MB`。  

通过检查资源的 HTTP 标头检查压缩：  

1.  选择`bundle.js`。  
1.  选择**标头**面板。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text="标头面板" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       **标头**面板  
    :::image-end:::  
    
1.  在**响应标头**部分搜索`content-encoding` 标头。  `content-encoding`标头不显示，意味着`bundle.js`未被压缩。  压缩资源时，此标头通常设置为 `gzip`、`deflate`或`br`。  有关这些值的说明，请导航到[指令][MDNContentEncodingDirectives]。  

说明已经足够。  现在开始进行更改。  通过添加几行代码启用文本压缩：  

1.  在编辑器选项卡中，选择**server.js**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑 server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       编辑 `server.js`  
    :::image-end:::  
    
1.  将以下代码添加到**server.js**。  请确保将 `app.use(express.static('build'))`置于`app.use(compression())`之前。  

    ```javascript
    const express = require('express');
    const app = express();
    const fs = require('fs');
    const compression = require('compression');

    app.use(compression());
    app.use(express.static('build'));
    
    const listener = app.listen(process.env.PORT || 1234, function () {
        console.log(`Listening on port ${listener.address().port}`);
    });
    ```  
    
    > [!NOTE]
    > 通常，你必须通过`npm i -S compression`等方式安装`compression`包，但此操作已为你完成。  
    
1.  等待 Glitch 部署站点的新内部版本。  **工具**旁边的奇特动画意味着正在重新生成和部署站点。  当**工具**旁边的动画消失时， 更改已准备就绪。  选择**显示**，然后再次选择**在新窗口中**。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
按照你之前了解的工作流，手动检查压缩是否工作：  

1.  返回到演示选项卡并刷新页面。  现在，**大小**列应显示`bundle.js`等文本资源的 2 个不同值。  在下图中，`bundle.js``256 KB`的顶部值是在网络中发送的文件的大小，而`1.2 MB`的底部值是未压缩文件的大小。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="现在，大小列显示文本资源的 2 个不同值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       现在，**大小**列显示文本资源的 2 个不同值  
    :::image-end:::  
    
1.  现在，`bundle.js`的**响应标头**部分应包含`content-encoding: gzip`标头。
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="现在，响应标头部分包含 content-encoding 标头" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       现在，**响应标头**部分包含 content-encoding 标头  
    :::image-end:::  
    
再次审核页面，测量文本压缩对页面加载性能的影响类型：  

1.  选择**审核**工具。  
1.  选择**执行审核** \(![Perform an audit](../media/perform-icon.msft.png)\)。  
1.  保留设置与之前相同。  
1.  选择**运行审核**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       启用文本压缩后的审核报告  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  总体性能分数应已提高，这意味着站点速度加快。  

#### <a name="text-compression-in-the-real-world"></a>现实世界中的文本压缩  

多数服务器确实包含此类简单修复，用于启用压缩！  只需搜索如何配置所使用的服务器压缩文本即可。  

### <a name="resize-images"></a>调整图像大小  

你的报告表明，避免大量网络负载是改进页面性能的一个首要机会。  调整图像大小有助于减少网络负载的大小。  如果用户在宽度为 500 像素的移动设备上查看图像，则发送宽度为 1500 像素的图像就豪无意义。  理想情况下，最多发送宽度为 500 像素的图像。  

1.  在你的报告中，选择 **避免大量网络负载**，显示应调整大小的图像。  似乎有 2 个 jpg 文件超过 2000 KB，超出所需大小。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  返回到编辑器选项卡，打开`src/model.js`。  
1.  将`const dir = 'big'`替换为`const dir = 'small'`。  此目录包含已调整大小的相同图像的副本。  
1.  再次审核页面，显示更改对加载性能的影响。  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的审核报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       调整图像大小后的审核报告  
    :::image-end:::  
    
更改显示仅对总体性能分数产生了细微影响。  但是，分数并未明确显示你为用户节省的网络数据量。  旧照片的总大小约为 5.3 MB，而现在仅约 0.18 MB。  

#### <a name="resizing-images-in-the-real-world"></a>在现实世界中调整图像大小  

对于小型应用，像这样调整一次大小可能就已足够。  但对于大型应用，这显然不可扩展。  以下是一些在大型应用中管理图像的策略：  

*   在编译流程中调整图像大小。  
*   在编译流程中创建每个图像的多个大小，然后在`srcset`代码中使用。  在运行时，浏览器会负责选择最适合设备的大小。  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   使用图像 CDN，可以在发出请求时动态调整图像大小。  
*   至少，可以优化每个图像。  这可能会节省大量空间。  
  优化是指通过减少图像文件大小的特殊程序运行图像。  有关更多提示，请导航到[基本图像优化][EssentialImageOptimization]。  
    
### <a name="eliminate-render-blocking-resources"></a>消除阻止渲染资源  

你的最新报告显示，现在，消除阻止渲染资源是最大机会。  

阻止渲染资源是外部 JavaScript 或 CSS 文件，浏览器必须在显示页面前下载、分析和运行此文件。  目标是只运行正确显示页面所需的 CSS 和 JavaScript 核心代码。  

然后，首个任务是查找页面加载时无需运行的代码。  

1.  选择**消除阻止渲染资源**，显示阻止资源：  
    `lodash.js` 和`jquery.js`。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除阻止渲染资源机会的详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       有关**消除阻止渲染资源机会**的详细信息  
    :::image-end:::  
    
1.  选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)， 打开“命令菜单”，开始键入 `Coverage` ，然后选择**显示覆盖**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从审核面板打开命令菜单" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       从**审核**面板打开“命令菜单”  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="覆盖工具" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       **覆盖**工具  
    :::image-end:::  
    
1.  选择**刷新** \(![Refresh](../media/reload-icon.msft.png)\)。  **覆盖**工具概述了加载页面时 `bundle.js`、`jquery.js`和`lodash.js`中运行的代码量。  在下图中，约 76% 的 jQuery 文件和 30% 的 Lodash 文件未被使用。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="覆盖报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       覆盖报告  
    :::image-end:::  
    
1.  选择 `jquery.js` 行。  DevTools 在"源" **工具中** 打开文件。  如果代码行运行，则旁边将显示一个蓝色条。  红色栏表示代码行未运行，并且肯定不需要在加载网页时运行。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在源工具中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       在"源"工具 **中查看** jQuery 文件  
    :::image-end:::  
    
1.  滚动浏览 jQuery 代码。  某些运行的行实际上只是注释。  若要去除注释并减少文件大小，请通过微型程序应用或脚本运行代码。  

简言之，当你使用自己的代码时，**覆盖**工具可以帮助你逐行分析代码，并只交付页面加载所需的代码。  

加载页面时是否需要`jquery.js`和`lodash.js`文件？  **请求阻止**工具显示资源不可用时会发生的状况。  

1.  选择**网络**工具。  
1.  选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\) ，再次打开“命令菜单”。  
1.  开始键入`blocking`，然后选择**显示请求阻止**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="请求阻止工具" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       **请求阻止**工具  
    :::image-end:::  
    
1.  选择**添加模式** \(![Add Pattern](../media/add-pattern-icon.msft.png)\)，键入`/libs/*`，然后选择`Enter`进行确认。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式，阻止对库目录的任何请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       添加模式，阻止对`libs`目录的任何请求  
    :::image-end:::  
    
1.  刷新页面。  jQuery 和 Lodash 请求为红色，意味着请求被阻止。   页面仍在加载且为交互式，因此似乎根本不需要这些资源！  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text="网络面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       **网络**工具显示请求已被阻止  
    :::image-end:::  
    
1.  选择**删除所有模式** \(![Remove all patterns](../media/remove-icon.msft.png)\)，删除`/libs/*`阻止模式。  
    
通常，**请求阻止**工具可以用于模拟页面在给定资源不可用时的行为方式。  

现在，从代码中删除这些文件的引用并再次审核页面：  

1.  返回到编辑器选项卡，打开`template.html`。  
1.  删除`<script src="/libs/lodash.js">`和`<script src="/libs/jquery.js"></script>`。  
1.  等待站点重新生成和部署。  
1.  从**审核**工具再次审核页面。  总体分数应再次提高。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除阻止渲染资源后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       删除阻止渲染资源后的**审核**报告  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a>在现实世界优化关键渲染路径  

**关键渲染路径**是指加载页面所需的代码。  通常，在页面加载期间仅交付关键代码，然后延迟加载其他所有内容，可以加快页面加载速度。  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   虽然不太可能找到能够彻底删除的脚本，但可能找到许多在页面加载期间无需请求的脚本，它们可以异步请求。  <!--Navigate to [Using async or defer][async].  -->  
*   如果你使用框架，请检查其是否包含生产模式。  此模式可能使用[摇树优化][WebpackTreeShaking]等功能，从而消除阻止关键渲染不必要的代码。  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a>减少主线程工作  

最新报告的机会部分表明存在一些细微的潜在节省，但如果往下查看"诊断"部分，似乎最大的瓶颈是主线程活动过多。  

在主线程中，浏览器执行显示页面所需的多数工作，例如分析和运行 HTML、CSS 和 JavaScript。  

目标是使用“性能”面板分析页面加载时主线程执行的工作，并找到延迟或删除不必要工作的方法。  

1.  选择**性能**工具。  
1.  单击**捕获设置** \(![Capture Settings](../media/capture-icon.msft.png)\)。  
1.  将**网络**设置为**慢速 3G**，**CPU**设置为**6x 减速**。  移动设备的硬件约束通常比笔记本电脑或台式机多，因此这些设置可以让你就像使用不那么强大的设备一样体验页面加载。  
1.  选择**刷新** \(![Refresh](../media/reload-icon.msft.png)\)。  开发人员工具会刷新页面，然后生成加载页面所执行的所有工作的可视化效果。  此可视化效果称为**跟踪**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载性能工具跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       页面加载**性能**工具跟踪  
    :::image-end:::  
    
跟踪从左到右，按时间顺序显示活动。  顶部的 FPS、CPU 和 NET 图表概述了每秒帧数、CPU 活动以及网络活动。  下图中黄色突出显示的信息块表明，CPU 完全忙于脚本活动。  这表明你可以减少 JavaScript 工作，从而加快页面加载速度。  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的概述部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   跟踪的概述部分  
:::image-end:::  

调查跟踪，查找减少 JavaScript 工作的方法：  

1.  选择并展开**计时** 部分。  基于 React 中可能存在许多[计时][MDNUserTimingApi]测量的事实，Tony 的应用似乎正使用 React 的开发模式。  切换到 React 的生产模式可能会产生一些简单的性能优势。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text="计时部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       **计时**部分  
    :::image-end:::  
    
1.  再次选择**计时**，折叠该部分。  
1.  浏览**主要**部分。  此部分从左到右，按时间顺序显示了主线程活动的记录。  y 轴（从上到下）表示事件发生的原因。  例如，在下图中，`Evaluate Script`事件导致`(anonymous)`函数运行，继而导致`(anonymous)`运行，然后导致`__webpack__require__`运行，以此类推。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="主要部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       **主要**部分  
    :::image-end:::  
    
1.  向下滚动到**主要**部分的底部。  使用框架时，多数上部活动由框架引起，框架通常无法控制。  你的应用引起的活动通常位于底部。  在此应用中，名为`App`的函数似乎引起了对`mineBitcoin`函数的大量请求。  听起来 Tony 可能正使用粉丝的设备挖掘加密货币...  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       悬停在`mineBitcoin`活动上  
    :::image-end:::  
    
    > [!NOTE]
    > 虽然框架提出的请求通常无法控制，但有时你可能以导致框架低效运行的方式构建应用。  重构应用、高效使用框架是减少主线程工作的一种方法。  但是，这要求深入了解框架的工作方式，以及对代码进行哪些更改可以更有效地使用框架。  
    
1.  展开**自上而下**部分。  此选项卡将分解占用时间最多的活动。  如果“自上而下”部分未显示任何内容，请选择**主要**部分的标签。  **自上而下**部分只显示当前选择的活动或活动组的信息。  例如，如果选择`mineBitcoin`中的一个活动，则**自上而下**部将只显示该活动的信息。   
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="自下而上选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       **自上而下**选项卡  
    :::image-end:::  
    
**自我时间**列显示每个活动直接花费的时间。  例如，在下图中，约 63% 的主线程时间用于`mineBitcoin`函数。  

现在开始查看使用生产模式和减少 JavaScript 活动是否可能加快页面加载。  从生产模式开始：  

1.  在编辑器选项卡中，打开`webpack.config.js`。  
1.  将`"mode":"development"`更改为`"mode":"production"`。  
1.  等待新内部版本部署。  
1.  再次审核页面。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="配置 webpack 使用生产模式后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       配置 webpack 使用生产模式后的审核报告  
    :::image-end:::  
    
通过删除对`mineBitcoin`的请求减少 JavaScript 活动：  

1.  在编辑器选项卡中，打开`src/App.jsx`。  
1.  在`constructor`中，为对`this.mineBitcoin(1500)`的请求添加备注。  
1.  等待新内部版本部署。  
1.  再次审核页面。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       删除不必要的 JavaScript 工作后的审核报告  
    :::image-end:::  
    
最后更改似乎大幅提升了性能！  

> [!NOTE]
> 此部分简要介绍了“性能”面板。  若要了解如何分析页面性能的详细信息，请导航到[性能分析参考][DevtoolsEvaluatePerformanceReference]。  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a>在现实世界中减少主线程工作  

通常， **性能**工具作为最常用的方法，可以了解站点在加载时执行哪些活动，以及找到删除不必要活动的方法。  

如果你倾向于更像`console.log()`的方法，则[用户计时 API][MDNUserTimingApi]将允许你任意标记应用生命周期的某些阶段，从而跟踪每个阶段花费的时间。  

## <a name="summary"></a>摘要  

*   无论何时开始优化站点的加载性能，始终都从审核开始。  审核会建立基线，并提供如何改进的提示。  
*   一次进行一个更改，并在每次更改后审核网页，从而显示独立更改对性能的影响。  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考 | Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类简介 | Coursera"  

[EssentialImageOptimization]: https://images.guide "基本图像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令 - Content-Encoding | MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API | MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "摇树优化 | webpack"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
