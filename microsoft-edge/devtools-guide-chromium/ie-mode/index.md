---
description: IE 模式和 Microsoft Edge (Chromium) DevTools
title: Internet Explorer模式和 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， ie11， Internet explorer 11， ie 模式
ms.openlocfilehash: e65869cd88b449dcde0aec25c77df27f99b78f8d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398600"
---
# <a name="internet-explorer-mode-and-the-devtools"></a>Internet Explorer模式和 DevTools  

本文介绍如何Internet Explorer模式 \ (IE 模式\) 与 Microsoft Edge \ (Chromium\) DevTools 集成。  

## <a name="understanding-ie-mode"></a>了解 IE 模式  

IE 模式允许企业指定仅在 11 Internet Explorer的网站列表。  在 Microsoft Edge \ (Chromium\) 中导航到这些网站时，Internet Explorer 11 的实例将运行并在选项卡中呈现网站。 此功能允许企业管理与当前与任何新式 Web 浏览器不兼容的技术的兼容性。  IE 模式下包含对以下技术的支持。  

*   IE 文档模式  
*   ActiveX 控件  
*   其他旧版组件  

在 IE 模式下，呈现过程基于 Internet Explorer 11。  Microsoft Edge \ (Chromium\) 进程管理器处理呈现过程的生存期。  它受特定网站 \ (app\) 选项卡的生存期限制。  当选项卡以 IE 模式呈现时，特定选项卡的地址栏中会显示锁屏提醒。  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="地址栏中的 IE 模式锁屏提醒" lightbox="../media/ie-mode-badge.msft.png":::
   地址栏中的 IE 模式锁屏提醒  
:::image-end:::  

IE 模式目前可用于 Windows 10 版本 1903 \ (2019 年 5 月更新\) ，但即将推出到所有受支持的 Windows 平台。  

## <a name="launching-the-devtools-on-a-tab-in-ie-mode"></a>在 IE 模式下的选项卡上启动 DevTools  

如果尝试在 IE 模式下查看网站的文档模式，请选择地址栏中的锁屏提醒。  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="使用 IE 模式锁屏提醒查看文档模式" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   使用 IE 模式锁屏提醒查看文档模式  
:::image-end:::  

如果选项卡使用的是 IE 模式，DevTools 将不起作用，并且会出现以下情况。

*   如果选择或 `F12` 选择，将启动 `Ctrl` + `Shift` + `I` Microsoft Edge \ (Chromium\) DevTools 的空白实例将显示以下消息。  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   如果打开上下文菜单 \ (右键单击\) 并选择 **"** 查看源"，将启动记事本。  
*   如果打开上下文菜单 \ (右键单击\) ， **则 Inspect 元素** 不可见。  

DevTools \ (中的许多工具（如**网络**和性能工具\) ）不起作用的原因是呈现**** 引擎在 IE 模式下从 Chromium 切换到 Internet Explorer 11。  若要提供反馈，请导航到 [与 Microsoft Edge DevTools](#getting-in-touch-with-the-microsoft-edge-devtools-team)团队联系。  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="在 IE 模式下启动的 DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   在 IE 模式下启动的 DevTools  
:::image-end:::  

若要在 Internet Explorer 11 和 IE 模式下测试基于 Internet Explorer 11 的网站 \ (或 app\) ，请执行以下步骤。  

1.  打开Internet Explorer 11。  
    *   在 Windows 10 上，找到 Internet Explorer 11 的快捷方式。
        1.  **"开始"菜单**  > **Windows 附件**  > **Internet Explorer 11**.  
    *   在 Windows 7 上，找到 Internet Explorer 11。
        1.  **"开始"菜单**  > **Internet Explorer 11**.  
1.  在 Internet Explorer 11 中，打开同一网页。  
1.  启动 Internet Explorer DevTools。  
    *   选择 `F12`。  
    *   将鼠标悬停在任意位置，打开上下文菜单 \ (右键单击\) ，然后选择 **"检查"元素**。  若要详细了解如何使用这些工具，请导航到["使用 F12 开发人员工具"。][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]  

## <a name="remote-debugging-and-ie-mode"></a>远程调试和 IE 模式  

启动 Microsoft Edge \ (Chromium\) ，同时从命令行界面打开远程调试。  Microsoft Visual Studio、Microsoft Visual Studio Code 和其他开发工具通常会运行命令来启动 Microsoft Edge。  以下命令启动 Microsoft Edge，远程调试端口设置为 `9222` 。  

```shell
start msedge --remote-debugging-port=9222
```  

使用命令行参数启动 Microsoft Edge \ (Chromium\) 后，IE 模式将不可用。  你仍可以导航到以 iE 模式 (或应用) 或应用\应用。  网站 \ (或 app\) 内容使用 Chromium 而不是 Internet Explorer 11 呈现。  预计依赖 IE11 的网页部分（如ActiveX控件）无法正确呈现。  IE 模式锁屏提醒不会显示在地址栏中。  

IE 模式仍然不可用，直到你完全关闭并重新启动 Microsoft Edge \ (Chromium\) 。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "使用 F12 开发人员工具|Microsoft Docs"  
