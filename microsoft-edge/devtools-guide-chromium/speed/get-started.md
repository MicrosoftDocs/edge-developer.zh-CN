---
description: 了解如何使用 Microsoft Edge DevTools 查找使网站加载速度更快的方法。
title: 使用 Microsoft Edge DevTools 优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 7de97ab27528e89e2373e0a0d1002e8c86e37613
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398110"
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

# <a name="optimize-website-speed-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 优化网站速度  

## <a name="goal-of-tutorial"></a>教程的目标  

本教程指导你如何使用 Microsoft Edge DevTools 查找使网站加载速度更快的方法。  

## <a name="prerequisites"></a>必备条件  

*   你应该具有基本的 Web 开发体验，类似于本"Web 开发简介" [类中介绍的内容][CourseraIntroductionWebDevelopmentClass]。  
*   无需了解有关加载性能的一切信息。  你将在本教程中了解它。  

## <a name="introduction"></a>简介  

这是 Tony。  Tony 在 cat 2016 中非常有名气。  他构建了一个网站，以便他的粉丝能够了解他最喜爱的粉丝。  他的粉丝喜欢该网站，但 Tony 不断听到有关网站加载缓慢的抱怨。  Tony 已要求你帮助他加快网站速度。  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony the cat" lightbox="../media/speed-tony.msft.png":::
   Tony the cat  
:::image-end:::  

## <a name="step-1-audit-the-site"></a>步骤 1：审核网站  

无论何时开始提高网站的加载性能，始终从 **审核开始**。  
审核有两项重要功能：  

*   它创建一 **个基线** ，用于度量后续更改。  
*   它为你提供 **了有关哪些** 更改影响最大的可操作提示。  
    
### <a name="set-up"></a>设置  

首先，必须设置网站，以便以后能够进行更改。  

1.  [打开网站的源代码](https://glitch.com/edit/#!/tony)。  此选项卡称为编辑器 **选项卡**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="编辑器选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       编辑器 **选项卡**  
    :::image-end:::  
    
1.  选择 **tony**。  将出现一个菜单。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="选择 tony 后出现的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       选择 tony 后出现的 **菜单**  
    :::image-end:::  
    
1.  选择 **"重新混合项目"。**  项目名称从 **tony** 更改为一些随机生成的名称。  现在，您具有自己的代码可编辑副本。  稍后，您可以对此代码进行更改。  
1.  选择 **"显示**"，然后选择 **"新建窗口"。**  将在新选项卡中打开演示。 此选项卡称为演示 **选项卡**。 加载网站可能需要一段时间。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="演示选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       演示选项卡  
    :::image-end:::  
    
1.  选择 `Control` + `Shift` + `J` \ (Windows、Linux\) `Command` + `Option` + `J` 或 \ (macOS\) 。  Microsoft Edge DevTools 将在演示旁边打开。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools 和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       DevTools 和演示  
    :::image-end:::  
    
对于本教程中的其余屏幕截图，DevTools 显示在单独的窗口中。  Select `Control` + `Shift` + `P` \ (Windows， Linux\) or `Command` + `Shift` + `P` \ (macOS\) to open the Command Menu， `Undock` typing， and then selecting **Undock into separate window**.  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="已取消停靠的 DevTools" lightbox="../media/speed-console.msft.png":::
   已取消停靠的 DevTools  
:::image-end:::  

### <a name="establish-a-baseline"></a>建立基线  

基线是网站在做出任何性能改进之前如何执行的记录。  

1.  选择 **"审核"** 工具。  It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.  此面板上有一个 Lighthouse，因为支持审核面板的项目名为**Lighthouse。**  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="审核工具" lightbox="../media/speed-audits-performance.msft.png":::
       **审核**工具  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  将审核配置设置与上图中的设置相匹配。  下面是不同选项的说明：  
    
    *   **设备**。  设置为 **"移动** "将更改用户代理字符串并模拟移动视口。  设置为 **桌面** 几乎只是关闭 **移动** 版更改。  
    *   **审核**。  关闭类别以防止审核面板运行这些**** 审核，并排除报告中的这些审核。  如果要显示提供的建议类型，请保持其他类别为"打开"。  关闭类别可稍微加快审核过程。  
    *   **限制**。  设置为 **模拟慢速 4G 时，4 倍 CPU 速度会** 模拟在移动设备上浏览的典型条件。  它命名为"模拟"，因为审核面板在审核过程中实际上不会限制。  相反，它只是推断页面在移动条件下加载所花的时间。  另 **一** 方面，应用... 设置实际上会限制 CPU 和网络，同时权衡较长的审核过程。  
    *   **清除存储**。  启用复选框，以在每次审核之前清除与页面关联的所有存储。  如果要审核首次访问者对网站的体验，请保留此设置。  在需要重复访问体验时关闭此设置。  
    
1.  选择 **"运行审核"。**  10 到 30 秒后****，审核面板将显示网站性能报告。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="网站性能的审核面板报告" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       网站性能的审核面板报告  
    :::image-end:::  
    
#### <a name="handling-report-errors"></a>处理报告错误  

如果在审核面板报告中收到错误，请尝试在未打开任何其他选项卡的 **InPrivate** 窗口中运行演示选项卡。  这可确保你从干净状态运行 Microsoft Edge。  尤其是 Microsoft Edge 扩展通常干扰审核过程。  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <a name="understand-your-report"></a>了解报告  

报告顶部的数字是网站的总体性能分数。  稍后，当您对代码进行更改时，显示的数量应该会上升。  分数越高表示性能越好。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="总体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   总体性能分数  
:::image-end:::  

" **指标** "部分提供网站性能的量度度量。  每个指标提供对性能不同方面的见解。  例如，"**** 第一个内容绘制"会告知你首次将内容绘制到屏幕的时间，这是用户对页面加载的感知中的一个重要里程碑，而"时间到**** 交互"标记页面显示为足以处理用户交互的点。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text=""指标"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   " **指标"** 部分  
:::image-end:::  

选择下图中突出显示的切换按钮以显示每个指标的说明，然后选择"了解更多 **"来阅读** 有关它的文档。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮以展开指标项" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   选择突出显示的切换按钮以展开指标项  
:::image-end:::  

下面的指标是显示页面加载时的外观的屏幕截图集合。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="页面在加载时的外观的屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   页面在加载时的外观的屏幕截图  
:::image-end:::  

" **机会** "部分提供了有关如何提高此特定页面的加载性能的特定提示。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text=""机会"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   " **机会"** 部分  
:::image-end:::  

选择一个了解它更多信息的机会。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除呈现阻止资源机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   **消除呈现阻止资源** 的机会  
:::image-end:::  

Choose **Learn More** to display documentation about why an opportunity is important， and specific recommendations on how to fix it.  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="有关消除呈现阻止资源机会的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   有关消除 **呈现阻止资源机会** 的文档  
:::image-end:::  

" **诊断"** 部分提供了有关影响页面加载时间的因素详细信息。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text=""诊断"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   " **诊断"** 部分  
:::image-end:::  

" **通过审核"** 部分显示网站正在正确执行哪些操作。  选择展开该部分。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text=""通过审核"部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   " **通过审核"** 部分  
:::image-end:::  

## <a name="step-2-experiment"></a>步骤 2：试验  

审核报告的"机会"部分提供了有关如何提高页面性能的提示。  在此部分中，您将实现对代码库的建议更改，每次更改后审核网站，以测量更改对网站速度的影响。  

### <a name="enable-text-compression"></a>启用文本压缩  

你的报告显示，避免大量网络负载是提升页面性能的一个最大机会。  启用文本压缩是提高页面性能的机会。  

文本压缩是在通过网络发送文本文件之前减小或压缩它的大小时。  类似于在发送目录之前存档目录以减少大小的方式。  

在启用压缩之前，有两种方法可以手动检查文本资源是否压缩。  

1.  选择 **"网络"** 工具。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="“网络”面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       网络**工具**  
    :::image-end:::  
    
1.  选择 **"网络"设置** 图标。  
1.  选中" **使用大型请求行"** 复选框。  网络请求表中行的高度增加。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的大型行" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       网络请求表中的大型行  
    :::image-end:::  
    
1.  如果未 **显示** 网络请求表中的"大小"列，请选择"大小"> **表标题**。  

每个 **Size** 单元格显示两个值。  顶部值是已下载资源的大小。  
底部值是未压缩资源的大小。  如果两个值相同，则当通过网络发送资源时，不会压缩资源。  例如，在上图中，其顶部和底部值为 `bundle.js` `1.2 MB` `1.2 MB` and。  

通过检查资源的 HTTP 标头检查压缩：  

1.  选择 `bundle.js` 。  
1.  选择 **"标题"** 面板。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text=""标题"面板" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       " **标题"** 面板  
    :::image-end:::  
    
1.  在 **"响应标头"** 部分搜索 `content-encoding` 标头。  不显示 `content-encoding` 标题，这意味着 `bundle.js` 未压缩。  压缩资源时，此标头通常设置为 `gzip` ， `deflate` 或 `br` 。  有关这些值的说明，请导航到["指令"。][MDNContentEncodingDirectives]  

与说明一起足够。  进行一些更改的时间。  通过添加几行代码启用文本压缩：  

1.  在编辑器选项卡中 ** ，选择 **server.js。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       编辑 `server.js`  
    :::image-end:::  
    
1.  将以下 ** 代码添加到 **server.js。  请确保放在 `app.use(compression())` 之前 `app.use(express.static('build'))` 。  

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
    > 通常，你必须通过类似内容安装程序包，但已 `compression` `npm i -S compression` 针对你完成此操作。  
    
1.  等待 Glitch 部署网站的新内部版本。  工具旁边的奇特动画**** 意味着正在重建和重新部署网站。  当工具旁边的动画消失 **时，更改** 已准备就绪。  选择 **"显示** "， **然后再次选择"新建窗口** "。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
使用之前了解到的工作流手动检查压缩是否正常工作：  

1.  返回到演示选项卡并刷新页面。  " **大小** "列现在应显示 2 个不同的文本资源值，如 `bundle.js` 。  在下面的图中，其顶部值为通过网络发送的文件的大小，而其底部值是未 `256 KB` `bundle.js` `1.2 MB` 压缩的文件大小。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text=""大小"列现在显示文本资源的 2 个不同值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       " **大小** "列现在显示文本资源的 2 个不同值  
    :::image-end:::  
    
1.  " **响应头"** 部分 `bundle.js` 现在应包含 `content-encoding: gzip` 标头。
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text=""响应头"部分现在包含内容编码标头" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       " **响应头"** 部分现在包含内容编码标头  
    :::image-end:::  
    
再次审核页面以测量文本压缩对页面加载性能的影响类型：  

1.  选择 **"审核"** 工具。  
1.  Choose **Perform an audit** \ (Perform an audit ![ ][ImagePerformIcon] \) .  
1.  保持设置与以前相同。  
1.  选择 **"运行审核"。**  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       启用文本压缩后的审核报告  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  总体性能分数应该已提高，这意味着网站的速度正在加快。  

#### <a name="text-compression-in-the-real-world"></a>现实世界中的文本压缩  

大多数服务器确实具有如下所示的简单修补程序，用于启用压缩！  只需搜索如何配置用于压缩文本的任何服务器。  

### <a name="resize-images"></a>调整图像大小  

你的报告表明，避免大量网络负载是提升页面性能的一个首要机会。  调整图像大小有助于减小网络有效负载的大小。  如果用户在 500 像素宽的移动设备屏幕上查看图像，则发送 1500 像素宽的图像实际上没有意义。  理想情况下，最多发送 500 像素宽的图像。  

1.  在报告中，选择 **"避免大量网络负载"** 以显示应调整大小的图像。  看起来有 2 个 jpg 文件超过 2000 KB，大于必要。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  返回到编辑器选项卡中，打开 `src/model.js` 。  
1.  用 `const dir = 'small'` 取代 `const dir = 'big'`。  此目录包含已调整大小相同的图像的副本。  
1.  再次审核页面以显示更改如何影响加载性能。  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的审核报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       调整图像大小后的审核报告  
    :::image-end:::  
    
更改显示仅对总体性能分数有轻微影响。  但是，该分数未明确显示一点，即保存用户的网络数据数量。  旧照片的总大小约为 5.3 MB，但现在只有约 0.18 MB。  

#### <a name="resizing-images-in-the-real-world"></a>在现实世界中调整图像大小  

对于小型应用，执行一次一次大小调整可能足够好。  但对于大型应用，这显然不可伸缩。  下面是用于管理大型应用中图像的一些策略：  

*   在生成过程中调整图像大小。  
*   在生成过程中创建每个图像的多个大小，然后在 `srcset` 代码中使用。  在运行时，浏览器负责选择最适合设备的大小。  
    <!--Navigate to [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   使用图像 CDN，可让你在请求图像时动态调整其大小。  
*   至少优化每个图像。  这可能会导致大量节省。  
  优化是通过减少图像文件大小的特殊程序运行图像时。  有关更多提示，请导航到["基本图像优化"。][EssentialImageOptimization]  
    
### <a name="eliminate-render-blocking-resources"></a>消除呈现阻止资源  

最新报告显示，消除呈现阻止资源现在是最大机会。  

呈现阻止资源是一个外部 JavaScript 或 CSS 文件，浏览器必须在显示页面之前下载、分析和运行该文件。  目标是仅运行正确显示页面所需的核心 CSS 和 JavaScript 代码。  

然后，第一个任务是查找无需在页面加载时运行的代码。  

1.  选择 **"消除呈现阻止资源** "以显示阻止的资源：  
    `lodash.js` `jquery.js`和 。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除呈现阻止资源机会详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       有关消除 **呈现阻止资源机会** 详细信息  
    :::image-end:::  
    
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) `Coverage` **** 打开命令菜单，开始键入，然后选择"显示覆盖"。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从"审核"面板中打开命令菜单" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       从"审核"面板 **中打开命令** 菜单  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="覆盖工具" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       覆盖**工具**  
    :::image-end:::  
    
1.  Choose **Refresh** \ (![ Refresh ][ImageRefreshIcon] \) .  " **覆盖** "工具概述了在加载页面时 ，和 中运行 `bundle.js` `jquery.js` `lodash.js` 的代码量。  在下图中，分别不分别使用大约 76% 和 30% 的 jQuery 和 Lodash 文件。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="覆盖报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       覆盖报告  
    :::image-end:::  
    
1.  选择jquery.js** 行 ** 。  DevTools 在"源"面板中打开文件。  如果代码行旁边有蓝色条形，代码行将运行。  红色条表示它未运行，并且绝对不需要在页面加载时运行。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在"源"面板中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       在"源"面板 **中查看** jQuery 文件  
    :::image-end:::  
    
1.  在 jQuery 代码中滚动一点。  某些获取"run"的行实际上只是注释。  通过去除注释的小型程序运行此代码是减小此文件大小的另一种方法。  

简而言之，当您使用自己的代码时，"覆盖"工具可帮助**** 你分行分析代码，并仅提供页面加载所需的代码。  

加载 `jquery.js` 页面 `lodash.js` 是否甚至需要文件和文件？  请求 **阻止** 工具显示资源不可用时会发生什么情况。  

1.  选择 **"网络"** 工具。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 以再次打开命令菜单。  
1.  开始键入， `blocking` 然后选择"**显示请求阻止"。**  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="请求阻止工具" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       请求 **阻止** 工具  
    :::image-end:::  
    
1.  Choose **Add Pattern** \ (Add Pattern ![ ][ImageAddPatternIcon] \) ， `/libs/*` type， and then select to `Enter` confirm.  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式以阻止对 libs 目录的任何请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       添加模式以阻止对目录 `libs` 的任何请求  
    :::image-end:::  
    
1.  刷新页面。  jQuery 和 Lodash 请求为红色，表示请求被阻止。   页面仍加载并且是交互式的，因此看起来这些资源不需要！  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text=""网络"面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       网络 **工具** 显示请求已被阻止  
    :::image-end:::  
    
1.  Choose **Remove all patterns** \ (![ Remove all patterns ][ImageRemoveIcon] \) to delete the blocking `/libs/*` pattern.  
    
通常，请求 **阻止** 工具可用于模拟页面在任何给定资源不可用时的行为方式。  

现在，从代码中删除对这些文件的引用，并再次审核页面：  

1.  返回到编辑器选项卡中，打开 `template.html` 。  
1.  删除 `<script src="/libs/lodash.js">` 和 `<script src="/libs/jquery.js"></script>`。  
1.  等待网站重新构建和重新部署。  
1.  从审核工具再次 **审核** 页面。  总体分数应该会再次提高。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除呈现阻止资源后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       删除 **呈现** 阻止资源后的审核报告  
    :::image-end:::  
    
#### <a name="optimizing-the-critical-rendering-path-in-the-real-world"></a>优化实际中的关键呈现路径  

关键 **呈现路径** 是指加载页面所需的代码。  通常，只需在页面加载期间交付关键代码，然后延迟加载其他所有内容，来加快页面加载速度。  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   您不太可能能够找到能够彻底删除的脚本，但您可能会发现许多脚本不需要在页面加载期间请求，而是可能会异步请求。  <!--Navigate to [Using async or defer][async].  -->  
*   如果使用的是框架，请检查其是否具有生产模式。  此模式可能使用树状抖动等[][WebpackTreeShaking]功能，以消除阻止关键呈现的不必要代码。  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <a name="do-less-main-thread-work"></a>减少主线程工作  

你的最新报告在"机会"部分显示了一些小的潜在节省，但如果在"诊断"部分向下看，则看起来最大的瓶颈是主线程活动太多。  

主线程是浏览器执行显示页面所需的大部分工作（如分析和运行 HTML、CSS 和 JavaScript）的地方。  

目标是使用性能面板来分析主线程在页面加载时所执行的工作，并找到延迟或删除不必要的工作的方法。  

1.  选择 **"性能"** 工具。  
1.  Choose **Capture Settings** \ (Capture Settings ![ ][ImageCaptureIcon] \) .  
1.  将**网络设置为****慢速 3G，****将 CPU**速度设置为**慢 6 倍**。  移动设备通常比笔记本电脑或台式机具有更多的硬件约束，因此这些设置使你可以像使用功能更少的设备一样体验页面负载。  
1.  Choose **Refresh** \ (![ Refresh ][ImageRefreshIcon] \) .  DevTools 刷新页面，然后生成为加载页面而执行的所有工作的可视化。  此可视化称为**跟踪。**  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载的性能工具跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       **页面**加载的性能工具跟踪  
    :::image-end:::  
    
跟踪按时间顺序显示活动，从左到右。  顶部的 FPS、CPU 和 NET 图表概述了每秒帧数、CPU 活动和网络活动。  接下来图中突出显示的黄色块，CPU 完全占用脚本活动。  这就是通过减少 JavaScript 工作来加快页面加载速度的线索。  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的"概述"部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   跟踪的"概述"部分  
:::image-end:::  

调查跟踪以查找减少 JavaScript 工作的方法：  

1.  选择 **"计时"** 部分以展开它。  根据 React 中可能有一组 [计时][MDNUserTimingApi] 度量值这一事实，看起来 Tony 的应用正在使用 React 的开发模式。  切换到 React 的生产模式可能会获得一些简单的性能提升。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text=""计时"部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       " **计时"** 部分  
    :::image-end:::  
    
1.  再次 **选择"计时** "以折叠该部分。  
1.  浏览 **"主"** 部分。  本部分显示从左到右的主线程活动的按时间顺序排列的日志。  从上到 (的 y 轴) 显示事件发生的原因。  例如，在下面的图块中，该事件导致函数运行，导致运行，导致运行， `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` 等等。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="主要部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       **主要**部分  
    :::image-end:::  
    
1.  向下滚动到" **主"部分** 的底部。  使用框架时，大部分上层活动由框架导致，这通常在你的控制范围内。  由应用引起的活动通常位于底部。  在此应用中，名为的函数似乎导致 `App` 对函数产生大量 `mineBitcoin` 请求。  看起来 Tony 可能正在使用其粉丝的设备来挖掘加密货币...  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="将鼠标悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       将鼠标悬停在 `mineBitcoin` 活动上  
    :::image-end:::  
    
    > [!NOTE]
    > 尽管框架提出的请求通常在你的控制范围内，但有时你可能以会导致框架运行效率低下的方式构建你的应用。  通过重构应用来高效地使用框架，可以减少主线程工作。  但是，这需要深入了解框架的工作方式，以及为了更有效地使用框架，在您自己的代码中进行哪种更改。  
    
1.  展开 **"下向上"** 部分。  此选项卡将分解哪些活动所花时间最多。  如果未在"主Bottom-Up中显示任何内容，请选择"主" **部分** 的标签。  " **底部向上** "部分只显示当前选择的任何活动或活动组的信息。  例如，如果选择其中一个活动，则"下向上"部分将只显示该 `mineBitcoin` 活动的信息。 ****  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text=""Bottom-Up"选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       " **下向上"** 选项卡  
    :::image-end:::  
    
" **自** 时间"列显示每个活动直接花费的时间。  例如，下图中，大约 63% 的主线程时间用于 `mineBitcoin` 函数。  

查看使用生产模式并减少 JavaScript 活动是否可能加快页面加载的时间。  从生产模式开始：  

1.  在编辑器选项卡中，打开 `webpack.config.js` 。  
1.  将 `"mode":"development"` 更改为 `"mode":"production"`。  
1.  等待新内部版本部署。  
1.  再次审核页面。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="配置 Webpack 以使用生产模式后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       配置 Webpack 以使用生产模式后的审核报告  
    :::image-end:::  
    
通过删除对以下项的请求来减少 JavaScript 活动 `mineBitcoin` ：  

1.  在编辑器选项卡中，打开 `src/App.jsx` 。  
1.  在 中注释掉 `this.mineBitcoin(1500)` 对 `constructor` 的请求。  
1.  等待新内部版本部署。  
1.  再次审核页面。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       删除不必要的 JavaScript 工作后的审核报告  
    :::image-end:::  
    
看起来，最后一次更改导致性能大幅提升！  

> [!NOTE]
> 本节对性能面板提供了一个相当简短的介绍。  若要了解有关如何分析页面性能的信息，请导航到["性能分析参考"。][DevtoolsEvaluatePerformanceReference]  

<!--todo: add section when available -->  

#### <a name="doing-less-main-thread-work-in-the-real-world"></a>在现实世界中减少主线程工作  

通常， **性能** 工具是了解您的网站在加载时执行哪些活动以及查找删除不必要活动的方法的最常见方法。  

如果你更喜欢更像的方法，则用户计时 API 使你能够任意标记应用生命周期的某些阶段，以便跟踪每个阶段所花的时间 `console.log()` 。 [][MDNUserTimingApi]  

## <a name="summary"></a>摘要  

*   无论何时开始优化网站的加载性能，始终从审核开始。  审核会建立基线，并为你提供有关如何改进的提示。  
*   一次进行一次更改，每次更改后审核网页，以显示独立更改对性能的影响。  

<!--
## Next steps  

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考|Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类|Coursera"  

[EssentialImageOptimization]: https://images.guide "基本映像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令 - 内容编码|MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "树状|webpack"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
