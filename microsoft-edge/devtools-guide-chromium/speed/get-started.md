---
description: 了解如何使用 Microsoft Edge DevTools 来查找更快地加载网站的方法。
title: 使用 Microsoft Edge 开发人员工具优化网站速度
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: dafcb9c4d1194239baed7507e505d74d2b4ce1c8
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993436"
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





# 通过 Microsoft Edge DevTools 优化网站速度   



## 教程目标  

本教程指导你如何使用 Microsoft Edge DevTools 来查找更快地加载网站的方法。  

## 必备条件  

*   你应该具有基本的 web 开发体验，类似于在此 [Web 开发类简介][CourseraIntroductionWebDevelopmentClass]中讲授的内容。  
*   无需了解有关加载性能的任何信息。  您可以在本教程中了解它！  

## 简介   

这是 Tony。  Tony 在猫社会中非常著名。  他已构建了一个网站，使其风扇能够了解他最喜爱的食物。  他的风扇喜欢该站点，但 Tony 会不断听到该站点加载缓慢的投诉。  Tony 已要求您帮助他提高网站的速度。  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony 猫" lightbox="../media/speed-tony.msft.png":::
   Tony 猫  
:::image-end:::  

## 步骤1：审核网站   

无论何时设置以提高网站的负载性能， **都应始终从审核开始**。  
审核具有2个重要功能：  

*   它将为您创建一个 **基线** 来衡量后续更改。  
*   它为你提供了可操作的有关哪些更改最有影响的 **提示** 。  
    
### 设置   

首先，你必须设置网站，以便稍后能够对其进行更改。  

1.  [打开网站的源代码](https://glitch.com/edit/#!/tony)。  此选项卡称为 **编辑器选项卡**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text=""编辑器" 选项卡" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       " **编辑器" 选项卡**  
    :::image-end:::  
    
1.  选择 " **tony**"。  将显示一个菜单。  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="单击 "tony" 后出现的菜单" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       单击 " **tony** " 后出现的菜单  
    :::image-end:::  
    
1.  选择 " **Remix 项目**"。  项目的名称从 **tony** 更改为某个随机生成的名称。  现在，你拥有自己的代码的可编辑副本。  稍后，你可以对此代码进行更改。  
1.  选择 " **显示** "，然后 **在新窗口中**选择。  演示将在新选项卡中打开。 此选项卡称为 " **演示" 选项卡**。 加载网站可能需要一段时间。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text=""演示" 选项卡" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       "演示" 选项卡  
    :::image-end:::  
    
1.  按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 。  Microsoft Edge DevTools 将与演示一起打开。  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="DevTools 和演示" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       DevTools 和演示  
    :::image-end:::  
    
对于本教程中的其余屏幕截图，DevTools 显示在一个单独的窗口中。  按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，键入 `Undock` ，然后选择 "**在单独窗口中取消插入**"。  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="取消停靠 DevTools" lightbox="../media/speed-console.msft.png":::
   取消停靠 DevTools  
:::image-end:::  

### 建立基线   

比较基准是在改进性能方面之前如何执行网站的记录。  

1.  选择 " **审核** " 选项卡。 它可能隐藏在 " **更多面板** " 后面 (![ 更多面板 ][ImageMorePanelsIcon] \ ) 按钮。  此面板上有一个 Lighthouse，因为 Lighthouse "审核" 面板的项目称为 " **Lighthouse**"。  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text=""审核" 面板" lightbox="../media/speed-audits-performance.msft.png":::
       " **审核** " 面板  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  将您的审核配置设置与上图中的设置相匹配。  下面是不同选项的说明：  
    
    *   **设备**。  设置为 " **移动** " 将更改用户代理字符串并模拟移动视区。  设置到 **桌面** 非常简单，只需禁用 **移动** 更改。  
    *   **审核**。  禁用类别可防止 "审核" 面板运行这些审核，并从报表中排除这些审核。  如果想要查看提供的建议类型，请保留启用其他类别。  禁用类别会略微提高审核过程的速度。  
    *   **限制**。  设置为 **模拟慢4G，4X CPU 减速** 模拟在移动设备上浏览的典型条件。  它被命名为 "模拟"，因为审核面板在审核过程中实际上并不会受到限制。  相反，它只是 extrapolates 在移动条件下加载页面所需的时间。  另一方面， **应用的 ...** 设置实际上会限制 CPU 和网络，同时还会权衡较长的审核过程。  
    *   **清除存储空间**。  启用此复选框将在每次审核之前清除与页面关联的所有存储。  如果你想要审核首次访问你的网站时的访问者体验，请保留此设置。  如果需要重复访问体验，请禁用此设置。  
    
1.  选择 " **运行审核**"。  10至30秒后，"审核" 面板将显示有关网站性能的报告。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="网站性能的 "审核" 面板的报表" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       网站性能的 "审核" 面板的报表  
    :::image-end:::  
    
#### 处理报告错误   

如果你在 "审核" 面板报告中遇到错误，请尝试从 **InPrivate** 窗口运行 "演示" 选项卡，并且不会打开任何其他选项卡。  这可确保你从干净状态运行 Microsoft Edge。  Microsoft Edge 扩展通常会干扰审核过程。  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="A report that errored" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### 了解你的报表   

报表顶部的数字是网站的整体绩效分数。  稍后，在对代码进行更改时，您应看到此数字高度。  分数越高表示性能越高。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="整体性能分数" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   整体性能分数  
:::image-end:::  

" **指标** " 部分提供了有关站点性能的量化指标。  每个指标都可以深入了解性能的不同方面。  例如， **第一个 Contentful 画图** 会告诉您，当内容首次绘制到屏幕时，这是用户对页面加载的感觉中的重要里程碑，而是 **交互式** 标记该页面似乎足以处理用户交互的时刻。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text=""指标" 部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   " **指标** " 部分  
:::image-end:::  

选择下图中突出显示的 "切换" 按钮以查看每个指标的说明，然后单击 " **了解详细** 信息" 以阅读有关每个指标的文档。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="选择突出显示的切换按钮以展开指标项目" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   选择突出显示的切换按钮以展开指标项目  
:::image-end:::  

"指标" 下面是屏幕截图的集合，可显示页面的加载方式。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="在加载时如何查看页面的屏幕截图" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   在加载时如何查看页面的屏幕截图  
:::image-end:::  

" **商机** " 部分提供了有关如何提高此特定页面的加载性能的特定提示。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text=""商机" 部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   " **商机** " 部分  
:::image-end:::  

选择一个商机以了解更多相关信息。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="消除呈现阻止资源的机会" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   **消除呈现阻止资源的** 机会  
:::image-end:::  

选择 " **了解详细** 信息"，查看有关商机为什么很重要的文档，以及有关如何解决该问题的特定建议。  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="用于消除呈现阻止资源商机的文档" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   用于 **消除呈现阻止资源** 商机的文档  
:::image-end:::  

**诊断**部分提供有关影响页面加载时间的因素的详细信息。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="诊断部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   **诊断**部分  
:::image-end:::  

"已 **通过审核** " 部分显示网站正确执行的操作。  选择以展开该部分。  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text=""已传递审核" 部分" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   "已 **传递审核** " 部分  
:::image-end:::  

## 步骤2：实验   

审核报告的 "机遇" 部分提供了有关如何提高页面性能的提示。  在此部分中，你将实现对基本代码的建议更改，在每次更改后审核网站，以测量它对网站速度的影响。  

### 启用文本压缩   

你的报告表明，避免巨大的网络负载是改善页面性能的首要机会之一。  启用文本压缩是提高页面性能的机会。  

文本压缩是指在通过网络发送文本文件之前减小或压缩该文件的大小。  类似于通过电子邮件对文件夹进行电子邮件压缩以减小大小。  

启用压缩之前，可通过以下几种方法来手动检查文本资源是否已压缩。  

1.  选择 " **网络** " 选项卡。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="网络面板" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       **网络**面板  
    :::image-end:::  
    
1.  选择 " **网络设置** " 图标。  
1.  选中 " **使用大请求行** " 复选框。  网络请求表中的行的高度增加。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="网络请求表中的较大行数" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       网络请求表中的较大行数  
    :::image-end:::  
    
1.  如果在网络请求表中看不到 " **大小** " 列，请单击表标题，然后选择 " **大小**"。  

每个 " **大小** " 单元格显示两个值。  最大值是已下载资源的大小。  
下限值是未压缩资源的大小。  如果两个值相同，则该资源在通过网络发送时不会被压缩。  例如，在上图中，的上限和下限值为 `bundle.js` `1.2 MB` 和 `1.2 MB` 。  

通过检查资源的 HTTP 标头来检查压缩：  

1.  选择 " **bundle.js**"。  
1.  选择 " **页眉** " 选项卡。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text=""页眉" 选项卡" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       " **页眉** " 选项卡  
    :::image-end:::  
    
1.  在 " **响应标题** " 部分 `content-encoding` 中搜索标题。  你应该看不到，这种情况未 `bundle.js` 压缩。  当资源被压缩时，此页眉通常设置为 `gzip` 、 `deflate` 或 `br` 。  有关这些值的说明，请参阅 [指令][MDNContentEncodingDirectives] 。  

有足够的说明。  进行更改的时间！  通过添加几行代码来启用文本压缩：  

1.  在 "编辑器" 选项卡中，单击 " **server.js**"。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="编辑 server.js" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       编辑 `server.js`  
    :::image-end:::  
    
1.  将以下代码添加到 **server.js**。  请确保放 `app.use(compression())` 在前面 `app.use(express.static('build'))` 。  

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
    > 通常，你必须通过类似的方式安装 `compression` 程序包 `npm i -S compression` ，但已为你执行此操作。  
    
1.  请等待部署新版本的网站。  " **工具** " 旁边的 "别致" 动画意味着该网站将重新构建并重新部署。  当 " **工具** " 旁边的动画消失时，更改即已准备就绪。  再次选择 " **显示** "，然后 **在新窗口中** 再次选择。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="The animation that indicates that the site is getting built" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
使用之前学习的工作流手动检查压缩是否正常工作：  

1.  返回到 "演示" 选项卡，然后重新加载页面。  现在，" **大小** " 列应显示类似于文本资源的2个不同值 `bundle.js` 。  在下面的图中，的最大值 `256 KB` `bundle.js` 是通过网络发送的文件的大小，其最小值 `1.2 MB` 是未压缩的文件大小。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text=""大小" 列现在为文本资源显示2个不同的值" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       " **大小** " 列现在为文本资源显示2个不同的值  
    :::image-end:::  
    
1.  现在，的 " **响应标题** " 部分 `bundle.js` 应包括 `content-encoding: gzip` 标题。
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text=""响应标题" 部分现在包含一个内容编码标题" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       " **响应标题** " 部分现在包含一个内容编码标题  
    :::image-end:::  
    
再次审核页面，以衡量影响文本压缩对页面加载性能有何种影响：  

1.  选择 " **审核** " 选项卡。  
1.  选择 " **执行审核** \ (![ 执行审核 ][ImagePerformIcon] \ ) 。  
1.  保持设置与以前一样。  
1.  选择 " **运行审核**"。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="启用文本压缩后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       启用文本压缩后的审核报告  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  您的整体性能分数应增加，这意味着网站的速度会更快。  

#### 现实世界中的文本压缩   

大多数服务器确实都有简单的修复程序，例如用于启用压缩的修补程序！  只需执行有关如何配置用于压缩文本的任何服务器的搜索。  

### 调整图像大小   

你的报表指示避免大量网络负载是提高页面性能的最高机会之一。  调整图像大小有助于减小网络负载的大小。  如果你的用户在移动设备屏幕上查看你的图像，该屏幕为 500-像素宽度，则在发送1500像素范围的图像时，实际上没有任何意义。  理想情况下，发送500像素宽的图像。  

1.  在报表中，单击 " **避免大量网络负载** " 以查看应调整哪些图像的大小。  它看起来是两个 jpg 文件超过了 2000 KB，这比所需的更大。  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Details about the properly size images opportunity" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  返回到 "编辑器" 选项卡中的 "打开" `src/model.js` 。  
1.  用 `const dir = 'small'` 取代 `const dir = 'big'`。  此目录包含已调整大小的相同图像的副本。  
1.  再次审核页面以查看此更改对加载性能的影响。  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="调整图像大小后的审核报告" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       调整图像大小后的审核报告  
    :::image-end:::  
    
看起来只有更改对整体性能分数有轻微影响。  但是，分数没有明显显示的一项是保存用户的网络数据量。  旧照片的总大小约为 5.3 mb，而现在仅限于0.18 兆字节。  

#### 在现实世界中调整图像大小   

对于小型应用，像这样做时，执行一次性调整大小的方式可能足够好。  但对于大型应用，这显然是不可缩放的。  下面是在大型应用中管理图像的一些策略：  

*   在生成过程中调整图像大小。  
*   在生成过程中创建多个大小的每个图像，然后 `srcset` 在代码中使用。  在运行时，浏览器负责选择最适合设备的大小。  
    <!--See [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   使用图像 CDN，允许你在请求图像时动态调整图像大小。  
*   最起码，优化每个图像。  这可能会带来巨大的节约。  
  优化是指通过可减小图像文件大小的特殊程序运行图像。  有关更多提示，请参阅 [基本图像优化][EssentialImageOptimization] 。  
    
### 消除呈现阻止资源   

您的最新报告表明，消除呈现阻止资源现在是最大的机会。  

呈现阻止资源是浏览器在显示页面之前必须下载、分析和运行的外部 JavaScript 或 CSS 文件。  目标是仅运行正确显示页面所需的核心 CSS 和 JavaScript 代码。  

然后，第一个任务是查找不需要在页面加载时运行的代码。  

1.  选择 " **消除呈现阻止资源** " 以查看阻止的资源：  
    `lodash.js` 和 `jquery.js` 。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="有关消除呈现阻止资源商机的详细信息" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       有关 **消除呈现阻止资源** 商机的详细信息  
    :::image-end:::  
    
1.  按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单，开始键入 `Coverage` ，然后选择 "**显示覆盖率**"。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="从 "审核" 面板中打开 "命令" 菜单" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       从 " **审核** " 面板中打开 "命令" 菜单  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text=""覆盖范围" 选项卡" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       " **覆盖范围** " 选项卡  
    :::image-end:::  
    
1.  选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。  " **覆盖范围** " 选项卡提供了在 `bundle.js` `jquery.js` `lodash.js` 页面加载期间、和运行的代码中的多少概述。  在以下的图中，将不会分别使用76% 和30% 的 jQuery 和 Lodash 文件。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="覆盖范围报告" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       覆盖范围报告  
    :::image-end:::  
    
1.  选择 " **jquery.js** " 行。  DevTools 将在 "源" 面板中打开该文件。  如果它旁边有一个蓝色条，则运行一行代码。  红色条表示它未运行，并且在页面加载时绝对不需要。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="在 "源" 面板中查看 jQuery 文件" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       在 " **源** " 面板中查看 jQuery 文件  
    :::image-end:::  
    
1.  按位滚动 jQuery 代码。  某些显示 "运行" 的行实际上只是批注。  通过 minifier 中的代码运行此代码，可查看批注是减小此文件大小的另一种方法。  

简言之，当你使用自己的代码时，"覆盖率" 选项卡可帮助你逐行分析代码，并仅发送页面加载所需的代码。  

`jquery.js`和文件是否还 `lodash.js` 需要加载页面？  "请求阻止" 选项卡显示资源不可用时发生的情况。  

1.  选择 " **网络** " 选项卡。  
1.  按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) ，再次打开 "命令" 菜单。  
1.  开始键入 `blocking` ，然后选择 " **显示请求阻止**"。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text=""请求阻止" 选项卡" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       " **请求阻止** " 选项卡  
    :::image-end:::  
    
1.  选择 " **添加模式** \ (![ 添加模式 ][ImageAddPatternIcon] \ ) "，键入 `/libs/*` ，然后按 `Enter` 进行确认。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="添加模式以阻止任何对库目录的请求" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       添加模式以阻止对目录的任何请求 `libs`  
    :::image-end:::  
    
1.  刷新页面。  JQuery 和 Lodash 请求是红色的，这意味着请求被阻止。   页面仍在加载，并且是交互式的，因此看起来不需要这些资源！  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text=""网络" 面板显示请求已被阻止" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       " **网络** " 面板显示请求已被阻止  
    :::image-end:::  
    
1.  选择 " **删除所有模式** \ (![ 删除所有模式 ][ImageRemoveIcon] \ ) " 删除 `/libs/*` 阻止模式。  
    
通常情况下，当任何给定资源不可用时，"请求阻止" 选项卡将非常有用，可用于模拟页面的行为方式。  

现在，从代码中删除对这些文件的引用，然后再次审核页面：  

1.  返回到 "编辑器" 选项卡中的 "打开" `template.html` 。  
1.  删除 `<script src="/libs/lodash.js">` 和 `<script src="/libs/jquery.js"></script>`。  
1.  等待网站重新构建和重新部署。  
1.  从 " **审核** " 面板中再次审核页面。  您的整体成绩将再次改进。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="删除 "呈现阻止" 资源后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       删除 "呈现阻止" 资源后的 **审核** 报告  
    :::image-end:::  
    
#### 优化现实世界中的关键呈现路径   

**关键呈现路径**是指加载页面所需的代码。  通常，仅在页面加载期间传输关键代码，然后延缓加载所有其他内容，从而加快页面负载。  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   你可能无法找到能够完全删除的脚本，但你可能会发现在页面加载期间不需要请求的多个脚本，而是可能会异步请求。  <!--See [Using async or defer][async].  -->  
*   如果你使用的是框架，请检查它是否具有生产模式。  此模式可能使用 [树形握手][WebpackTreeShaking] 之类的功能来消除阻止关键呈现的不必要代码。  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### 执行较少的主线程工作   

您的最新报告显示了 "商机" 部分中的一些小的可能节约，但如果您在 "诊断" 部分中向下查看，那么最大的瓶颈似乎是太多的主线程活动。  

主线程是浏览器完成显示页面所需的大部分工作（如分析和运行 HTML、CSS 和 JavaScript）的位置。  

目标是使用 "性能" 面板分析主线程在页面加载期间执行的工作，并查找推迟或删除不必要的工作的方法。  

1.  选择 " **性能** " 选项卡。  
1.  选择 " **捕获设置** \ (![ 捕获设置 ][ImageCaptureIcon] \ ) "。  
1.  将 **网络** 设置为 **慢速 3g** 和 **CPU** **6x 减速**。  移动设备通常比笔记本或桌面具有更多硬件约束，因此这些设置使你可以体验页面加载，就像使用的功能较少的设备一样。  
1.  选择 " **刷新** \ (![ 刷新 ][ImageRefreshIcon] \ ) "。  DevTools 刷新页面，然后生成所有已执行工作的可视化效果，以便加载页面。  此可视化对象称为 **跟踪**。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="页面加载的性能面板跟踪" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       页面加载的 **性能** 面板跟踪  
    :::image-end:::  
    
跟踪按时间顺序从左到右显示活动。  顶部的 FPS、CPU 和网络图概括介绍了每秒帧数、CPU 活动和网络活动。  在下图中看到的黄色所选方块，CPU 与脚本活动完全繁忙。  这是一条提示，您可以通过执行较少的 JavaScript 工作来加快页面负载。  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="跟踪的概述部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   跟踪的概述部分  
:::image-end:::  

调查跟踪以查找执行更少 JavaScript 工作的方法：  

1.  选择 " **计时** " 部分将其展开。  根据可能有一组 [计时][MDNUserTimingApi] 对响应的情况，似乎 Tony 的应用正在使用响应的开发模式。  切换到 "响应生产模式" 可能会产生一些简单的性能获胜。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text=""计时" 部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       " **计时** " 部分  
    :::image-end:::  
    
1.  再次选择 " **计时** " 以折叠该部分。  
1.  浏览 **主** 分区。  此部分显示按时间顺序排列的主线程活动（从左到右）的日志。  Y 轴 ("从上到下") 显示发生事件的原因。  例如，在 figyre 中，在以下情况下，事件导致运行该函数，导致运行，导致运行， `Evaluate Script` `(anonymous)` `(anonymous)` `__webpack__require__` 依此类推。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="主要部分" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       **主要**部分  
    :::image-end:::  
    
1.  向下滚动到 **主** 区域的底部。  使用框架时，大部分较高的活动都是由框架导致的，该框架通常不受控制。  应用引发的活动通常位于底部。  在此应用中，名为的函数似乎 `App` 导致了许多对函数的请求 `mineBitcoin` 。  听起来好像 Tony 可能会使用其风扇的设备来挖掘 cryptocurrency .。。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="悬停在 mineBitcoin 活动上" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       悬停在 `mineBitcoin` 活动上  
    :::image-end:::  
    
    > [!NOTE]
    > 尽管你的框架所提供的请求通常不在你的控件中，但有时你可能会导致框架运行效率较低下的方式构建你的应用。  将你的应用重构为高效使用框架是一种减少主线程工作的方法。  但是，这需要深入了解你的框架的工作原理以及你自己的代码中所做的更改，以便更高效地使用框架。  
    
1.  展开 " **下** " 部分。  此选项卡可分解最长时间的活动。  如果在下图中看不到任何内容，请单击 " **主要** 部分的标签"。  **自下而上**的部分仅显示当前已选择的任何活动或活动组的信息。  例如，如果单击其中一个 `mineBitcoin` 活动，则 " **下移** " 部分将仅显示该活动的信息。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text=""下" 选项卡" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       " **下** " 选项卡  
    :::image-end:::  
    
" **自时间** " 列显示在每个活动中直接花费的时间量。  例如，在下图中，大约63% 的主线程时间被用在该 `mineBitcoin` 函数上。  

了解使用生产模式和减少 JavaScript 活动的时间可能会加速页面加载。  从生产模式开始：  

1.  在 "编辑器" 选项卡中，打开 `webpack.config.js` 。  
1.  将 `"mode":"development"` 更改为 `"mode":"production"`。  
1.  等待部署新版本。  
1.  再次审核该页面。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="将 webpack 配置为使用生产模式后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       将 webpack 配置为使用生产模式后的审核报告  
    :::image-end:::  
    
通过删除以下请求来减少 JavaScript 活动 `mineBitcoin` ：  

1.  在 "编辑器" 选项卡中，打开 `src/App.jsx` 。  
1.  在中将请求注释为 `this.mineBitcoin(1500)` `constructor` 。  
1.  等待部署新版本。  
1.  再次审核该页面。  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="删除不必要的 JavaScript 工作后的审核报告" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       删除不必要的 JavaScript 工作后的审核报告  
    :::image-end:::  
    
看起来，最后一个更改导致性能巨大的跳跃。  

> [!NOTE]
> 本部分提供了 "性能" 面板的简要介绍。  请参阅 [性能分析参考][DevtoolsEvaluatePerformanceReference] ，了解有关如何分析页面性能的详细信息。  

<!--todo: add section when available -->  

#### 在现实世界中执行较少的主线程工作   

通常，" **性能** " 面板是了解你的网站在加载时所执行的活动的最常用方式，并查找删除不必要的活动的方法。  

如果你更喜欢更喜欢的方法 `console.log()` ， [用户计时 API][MDNUserTimingApi] 使你可以任意标记你的应用生命周期的特定阶段，以便跟踪这些阶段所需的时间。  

## 摘要   

*   无论何时设置以优化网站的负载性能，都将始终从审核开始。  审核建立了一个基准，并提供了有关如何改进的提示。  
*   一次更改一个更改，并在每次更改后审核页面，以了解该隔离更改对性能有何影响。  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--  
  


-->  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "性能分析参考 |Microsoft 文档"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Web 开发类简介 |Coursera"  

[EssentialImageOptimization]: https://images.guide "基本图像优化"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "指令-内容编码 |MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "用户计时 API |MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "树形摇动 |webpack"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
