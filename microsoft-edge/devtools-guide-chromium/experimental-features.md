---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验性功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、实验
ms.openlocfilehash: 731a289f555870eeff9cdc160965b59925b70c4d
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843935"
---
# 实验性功能  

你可以使用 Microsoft Edge DevTools 中仍处于开发阶段的实验功能来测试和[提供反馈](#providing-feedback-on-experimental-features)，然后再广泛发布。  

尽管实验功能可在 Microsoft Edge 的所有信道中使用，但你可能会使用 Microsoft Edge "未完成" 通道获取最新实验功能。  

## 启用实验功能  

使用以下步骤打开 Microsoft Edge 中的 "\" （或 "关闭 \"）实验功能。  

1.  [打开 DevTools][DevtoolsOpen]。  
     *   按 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）。  有关详细信息，请参阅[Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  打开 "**设置**" 窗格。  
    *   按 `Shift` + `?` 。  有关详细信息，请参阅[Microsoft Edge DevTools 键盘快捷方式][DevToolsShortcuts]。  
1.  在 "**设置**" 窗格的左侧，选择 "**实验**" 部分。  
    
    :::image type="complex" source="./media/experiments-devtools.png" alt-text="DevTools 设置中的实验列表" lightbox="./media/experiments-devtools.png":::
       DevTools 设置中的实验列表  
    :::image-end:::  
    
1.  在 "**实验**" 页面上，滚动浏览所有可用实验功能的列表，然后选择要测试的每个功能旁边的复选框。  
1.  关闭并重新打开 Microsoft Edge DevTools。  

> [!NOTE]
> 实验性功能将不断更新，并可能导致性能问题。  若要关闭实验功能，请打开 "**试验**" 页面，然后清除要关闭的实验功能的复选框。  

## 突出显示实验功能  

以下部分介绍 Microsoft Edge 中可用的新实验功能。  

| 实验性功能 | Microsoft Edge 版本 |  
|:--- |:--- |  
| [启用新的 CSS 网格调试功能](#enable-new-css-grid-debugging-features) | 85或更高版本 |  
| [启用支持以在面板之间移动选项卡](#enable-support-to-move-tabs-between-panels) | 85或更高版本 |  
| [启用 webhint](#enable-webhint) | 85或更高版本 |  

### 启用新的 CSS 网格调试功能  

在调试具有 CSS 网格布局的网站时，改善页面上的可视化效果。  你可以在 DevTools 设置中进一步自定义覆盖。  

:::image type="complex" source="./media/experiments-grid.png" alt-text="CSS 网格调试功能" lightbox="./media/experiments-grid.png":::
   CSS 网格调试功能  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用支持以在面板之间移动选项卡  

通常，**元素**和**网络**之类的工具只能在 DevTools 的 main \ （top \）面板中打开。  同样， **3D 视图**和**问题**之类的工具可能仅在 DevTools 的抽屉 \ （底部 \）面板中打开。  选择此实验后，你可以通过在选项卡上悬停，打开上下文菜单 \ （右键单击 \），然后选择 "**移到页首**" 或 "**移至底部**"，在顶部面板和底部面板之间移动工具。   此实验允许你自定义 DevTools 布局。  若要显示或隐藏底部面板，请按 `Escape` 。  

:::image type="complex" source="./media/experiments-move-panels.png" alt-text="在面板之间移动选项卡" lightbox="./media/experiments-move-panels.png":::
   在面板之间移动选项卡  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### 启用 webhint  

[webhint][WebhintMain]是一种开放源工具，可提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWAs 和其他常见 web 开发问题的实时反馈。  此实验将 webhint 反馈带入 "[问题][DevtoolsIssues]" 面板中的 DevTools。  你可以选择该问题以查看有关如何解决该问题的文档和你的网站上受影响的资源列表。  选择资源链接以打开 DevTools 中的相关**网络**、**源**或**元素**窗格。  

:::image type="complex" source="./media/experiments-webhint.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="./media/experiments-webhint.png":::
   "问题" 面板中的 webhint 反馈  
:::image-end:::      

<!--Available in Microsoft Edge version 85 and later.  -->  

## 以前的实验功能  

*   [3D 视图][Devtools3DView]现在可用，在 Microsoft Edge 版本83或更高版本中默认情况下处于打开状态。  

## 提供有关实验功能的反馈  

若要提供有关 Microsoft Edge DevTools 实验的反馈或与 DevTools 相关的任何其他内容，请执行以下操作：  

*   使用 DevTools 中的反馈图标发送反馈  
*   Tweet [@EdgeDevTools][TwitterEdgedevtools]  

:::image type="complex" source="./media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的反馈图标" lightbox="./media/devtools-feedback.png":::
   Microsoft Edge DevTools 中的反馈图标  
:::image-end:::  

<!-- links -->  

[Devtools3DView]: ./3D-view.md "3D 视图 |Microsoft 文档"  
[DevtoolsIssues]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevToolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools 键盘快捷方式-Microsoft 文档"  
[DevtoolsOpen]: ./open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint" 
