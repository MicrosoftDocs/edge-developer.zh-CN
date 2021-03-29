---
description: 使用 Microsoft Edge DevTools 动画检查器检查和修改动画。
title: 检查动画
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: dba948087ca06015f686d17ba48584199373805a
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439540"
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

# <a name="inspect-animations"></a>检查动画  

使用 Microsoft Edge DevTools 动画检查器检查和修改动画。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   动画检查器  
:::image-end:::  

### <a name="summary"></a>摘要  

*   打开动画检查器捕获动画。  动画检查器自动检测动画并按组排序。  
*   通过减慢动画的速度、重播每个动画或查看源代码来检查动画。  
*   通过更改计时、延迟、持续时间或关键帧偏移来修改动画。  

## <a name="overview"></a>概述  

Microsoft Edge DevTools 动画检查器有两个主要用途。  

*   检查动画。  你可以减慢、重播或检查动画组的源代码。  
*   修改动画。  你可以修改动画组的计时、延迟、持续时间或关键帧偏移。  贝塞尔编辑和关键帧编辑当前不受支持。  

动画检查器支持 CSS 动画、CSS 过渡和 Web 动画。  `requestAnimationFrame` 动画当前不受支持。  

### <a name="what-is-an-animation-group"></a>什么是动画组？  

动画组是一组相互相关的动画。  目前，Web 没有组动画的实际概念，因此动画设计人员和开发人员必须撰写各个动画并设置动画时间，以便动画呈现为一致的视觉效果。  动画检查器根据开始时间 \（等，不包括延迟）来预测哪些动画是相关的。  动画检查器还会将动画并排分组。  
换句话说，在同一脚本块中触发的一组动画会被组合在一起。  如果动画是异步动画，它会被放置在单独的组中。  

## <a name="get-started"></a>入门  

有两种方法可以打开动画检查器：  

*   打开“**自定义和控制 DevTools**”菜单  
    1.  导航到“**更多工具**”子菜单。  
    1.  选择“**动画**”：  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="使用主菜单的动画" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           使用主菜单的**动画**  
    :::image-end:::  
        
*   打开**命令菜单**  
    1.  键入 `Drawer: Show Animations`。  

动画检查器将在控制台工具旁**打开**。  由于动画检查器是一个箱工具，因此你可以从任何 DevTools 面板使用动画检查器。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="空动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   空动画检查器  
:::image-end:::  

动画检查器分为四个主要部分 \(或窗格\)。  本指南按以下方式指代每个窗格：  

| 索引 | 窗格 | 描述 |  
|:--- |:--- |:--- |  
| 1 | **控件** | 你可以在此处清除当前捕获的所有动画组，或更改当前选定的动画组的速度。 |  
| 2 | **概述** | 在此处选择动画组以检查和修改**详细信息**窗格中的动画组。 |  
| 3 | **时间线** | 从此处暂停并启动动画，或跳转到动画中的特定点。 |  
| 4 | **详细信息** | 检查和修改当前选定的动画组。 |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="批注动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   批注动画检查器  
:::image-end:::  

若要捕获动画，只需执行在动画检查器打开时触发动画的交互。  如果在页面加载时触发了动画，请刷新页面，同时打开动画检查器以检测动画。  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## <a name="inspect-animations"></a>检查动画  

捕获动画后，有多种方式可以重播它：  

*   将鼠标悬停在“**概述**”窗格中的缩略图上，查看缩略图的预览。  
*   从“**概述**”窗格选择动画组，\(以便它显示在“**详细信息**”窗格中\) 并选择”**重播**” \(![重播图标](../media/replay-button-icon.msft.png)\) 图标。  动画会在视区中重播。  选择“**动画速度** \(![动画速度图标](../media/animation-speed-buttons-icon.msft.png)\)” 图标可更改当前选定的动画组的预览速度。  可以使用红色竖线更改当前位置。  
*   选择并拖动红色竖线以清理视区动画。  
    
### <a name="view-animation-details"></a>查看动画详细信息  

捕获动画组后，从“**概述**”窗格中选择它以查看详细信息。  在“**详细信息**”窗格中，将为每个单独的动画分配一行。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画组详细信息" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   动画组详细信息  
:::image-end:::  

将鼠标悬停在动画上以在视区中突出显示它。  选择动画以在“**元素**”工具中选择它。  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="将鼠标悬停在动画上以在视区中突出显示它" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   将鼠标悬停在动画上以在视区中突出显示它  
:::image-end:::  

动画最左侧较暗的部分就是定义。  右侧更淡出的部分表示迭代。  例如，在下图中，第二节和第三节表示第一节的迭代。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="动画迭代关系图" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   动画迭代关系图  
:::image-end:::  

如果两个元素应用了相同的动画，则动画检查器会向这些元素分配相同的颜色。  颜色是随机的，没有意义。  例如，在下图中，这两个元素 `div.cwccw.earlier` 和 `div.cwccw.later` 应用了相同的动画 \(`spinrightleft`\)， `div.ccwcw.earlier` 和 `div.ccwcw.later` 元素也是。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="颜色编码动画" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   颜色编码动画  
:::image-end:::  

## <a name="modify-animations"></a>修改动画  

有三种方法可以使用动画检查器修改动画。  

*   动画持续时间。  
*   关键帧计时。  
*   开始时间延迟。  
    
下图中显示了原始动画。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="修改前的原始动画" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   修改前的原始动画  
:::image-end:::  

若要更改动画的持续时间，请选择并拖动第一个或最后一个圆。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="修改持续时间" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   修改持续时间  
:::image-end:::  

如果动画定义任何关键帧规则，则这些规则表示为白色内部圆。  选择并拖动其中一个以更改关键帧的计时。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="修改后的关键帧" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   修改后的关键帧  
:::image-end:::  

若要向动画添加延迟，请选择并将其拖动到除圆形之外的任何位置。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="修改后的延迟" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   修改后的延迟  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

(../media/animation-speed-buttons-icon.msft.png): ../media/animation-speed-buttons-icon.msft.png  
(../media/replay-button-icon.msft.png): ../media/replay-button-icon.msft.png  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/animations)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
