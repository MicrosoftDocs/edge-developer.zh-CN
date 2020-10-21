---
description: 通过 Microsoft Edge DevTools 动画检查器检查和修改动画。
title: 检查动画
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: fed686c07acd0648ac512dac131d85a317fb64eb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124773"
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

# 检查动画  

通过 Microsoft Edge DevTools 动画检查器检查和修改动画。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-completed.msft.png":::
   动画检查器  
:::image-end:::  

### 摘要  

*   通过打开 "动画检查器" 捕获动画。  动画检查器会自动检测动画并将其排序为多个组。  
*   通过减速、重放每个动画或查看源代码来检查动画。  
*   通过更改计时、延迟、持续时间或关键帧偏移来修改动画。  

## 概述  

Microsoft Edge DevTools 动画检查器有两个主要用途。  

*   检查动画。  你希望减慢、重播或检查动画组的源代码。  
*   修改动画。  要修改动画组的计时、延迟、持续时间或关键帧偏移量。  当前不支持贝塞尔编辑和关键帧编辑。  

动画检查器支持 CSS 动画、CSS 转换和 web 动画。  `requestAnimationFrame` 当前不支持动画。  

### 什么是动画组？  

动画组是可能相互关联的一组动画。  目前，web 没有组动画的真正概念，因此动画设计器和开发人员必须编写和时间单个动画，以便动画呈现为一个连贯的视觉效果。  动画检查器将预测哪些动画基于开始时间 \ (不包括延迟，如此 ) 。  动画检查器还会并排对动画进行分组。  
换句话说，在同一脚本块中同时触发的一组动画将组合在一起。  如果动画是异步的，则将其放置在单独的组中。  

## 开始行动  

可通过两种方式打开 "动画" 检查器：  

*   打开 " **自定义和控制" DevTools** 菜单  
    1.  导航到 " **更多工具** " 子菜单。  
    1.  选择 " **动画**"：  
        
        :::image type="complex" source="../media/inspect-styles-elements-styles-more-tools-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-more-tools-animations.msft.png":::
           使用主菜单的**动画**  
    :::image-end:::  
        
*   打开 " **命令" 菜单**  
    1.  键入 `Drawer: Show Animations`。  

"动画" 检查器将在控制台抽屉旁边的选项卡中打开。  由于动画检查器是一个抽屉选项卡，因此您可以使用任何 DevTools 面板中的动画检查器。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations.msft.png":::
   清空动画检查器  
:::image-end:::  

动画检查器分为四个主要部分，即 " (" 或 "窗格 \ ) "。  本指南按如下方式引用每个窗格：  

| 索引 | 窗格 | 描述 |  
|:--- |:--- |:--- |  
| raid-1 | **控件** | 你可以从此处清除当前捕获的所有动画组，或更改当前所选动画组的速度。 |  
| ppls-2 | **概述** | 在此处选择一个动画组以在 " **详细信息** " 窗格中检查和修改它。 |  
| 三维空间 | **时间线** | 在此处暂停和启动动画，或跳转到动画中的特定点。 |  
| 第 | **详细信息** | 检查和修改当前所选的动画组。 |  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-paused.msft.png":::
   带批注的动画检查器  
:::image-end:::  

若要捕获动画，只需在动画检查器打开的情况下执行触发动画的交互。  如果动画是在页面加载时触发的，请使用动画检查器打开来重新加载页面以检测动画。  

<!--  old link: <video src="animations/capture-animations.mp4" autoplay loop muted controls></video>  -->  

<!--  import the video to ACOM using https://review.docs.microsoft.com/en-us/help/contribute/contribute-video-publish?branch=master  -->  

<!--  > [!VIDEO animations/capture-animations.mp4]  -->  

## 检查动画  

捕获动画后，有几种方法可以重播它：  

*   将鼠标悬停在 " **概述** " 窗格的缩略图上以查看它的预览。  
*   从 " **概述** " 窗格中选择 "动画" 组 \ (，使其显示在 " **详细信息** " 窗格 \ ) 中，然后按 " **重播** \ (![ 重播" 图标 ][ImageReplayButtonIcon] \ ) 图标。  将在视区中重播动画。  单击 " **动画速度** " (![ 动画速度图标 ][ImageAnimationSpeedButtonsIcon] \ ) 图标，以更改当前所选动画组的预览速度。  您可以使用红色垂直条更改您的当前位置。  
*   单击并拖动红色垂直条以擦除视区动画。  
    
### 查看动画详细信息  

捕获动画组后，从 " **概述** " 窗格中单击它以查看详细信息。  在 " **详细信息** " 窗格中，每个单独的动画都分配有一行。  

:::image type="complex" source="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-elements-styles-drawer-animations-selected-completed.msft.png":::
   动画组详细信息  
:::image-end:::  

将鼠标悬停在某个动画上，将其在视区中突出显示。  单击动画以在 " **元素** " 面板中选择它。  

:::image type="complex" source="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-split-elements-styles-drawer-animations-selected-completed.msft.png":::
   将鼠标悬停在动画上以在视区中突出显示  
:::image-end:::  

动画最左边、更暗的部分是定义。  右侧、更淡出的部分表示迭代。  例如，在下图中，第二部分和第三部分表示第一节的迭代。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations-highlight.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-display-animations-highlight.msft.png":::
   动画迭代图表  
:::image-end:::  

如果两个元素应用了相同的动画，则动画检查器会为元素分配相同的颜色。  颜色是随机的，没有任何意义。  例如，下图中，这两个元素 `div.cwccw.earlier` `div.cwccw.later` 具有相同的动画 \ (`spinrightleft` \ ) 应用，就像执行 `div.ccwcw.earlier` 和元素一样 `div.ccwcw.later` 。  

:::image type="complex" source="../media/inspect-styles-glitch-display-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-display-animations.msft.png":::
   颜色编码的动画  
:::image-end:::  

## 修改动画  

你可以通过三种方式使用动画检查器修改动画。  

*   动画持续时间。  
*   关键帧计时。  
*   开始时间延迟。  
    
在下图中，表示原始动画。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations.msft.png":::
   修改前的原始动画  
:::image-end:::  

若要更改动画的持续时间，请单击并拖动第一个或最后一个圆。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-shorter.msft.png":::
   已修改工期  
:::image-end:::  

如果动画定义了任何关键帧规则，则这些规则表示为白色内圆圈。  单击并拖动其中一个以更改关键帧的计时。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-keyframe-modification.msft.png":::
   修改的关键帧  
:::image-end:::  

若要向动画添加延迟，请单击并将其拖动到除圆圈外的任意位置。  

:::image type="complex" source="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png" alt-text="动画检查器" lightbox="../media/inspect-styles-glitch-spin-animations-console-animations-delay.msft.png":::
   修改后的延迟  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAnimationSpeedButtonsIcon]: ../media/animation-speed-buttons-icon.msft.png  
[ImageReplayButtonIcon]: ../media/replay-button-icon.msft.png  

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
