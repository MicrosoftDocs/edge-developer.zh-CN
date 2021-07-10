---
description: IE 模式和 Microsoft Edge (Chromium) DevTools
title: Internet Explorer模式和 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， ie11， Internet Explorer 11， ie 模式
ms.openlocfilehash: 070bf970c784b4f2173ebc52e4494fc6807b4a8e
ms.sourcegitcommit: 7cba715ef71cbac4ee0ebe8f07c0c0e4a2c64221
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643233"
---
# <a name="internet-explorer-mode-and-the-devtools"></a>Internet Explorer模式和 DevTools  

本文介绍如何Internet Explorer \ (IE 模式\) 与 Microsoft Edge \ (Chromium\) DevTools 集成。  

## <a name="understanding-ie-mode"></a>了解 IE 模式  

IE 模式允许企业指定仅在 11 Internet Explorer的网站列表。  当您导航到 Microsoft Edge \ (Chromium\) 中的这些网站时，Internet Explorer 11 的实例将运行并在选项卡中呈现网站。 此功能允许企业管理与当前与任何新式 Web 浏览器不兼容的技术的兼容性。  IE 模式下包含对以下技术的支持。  

*   IE 文档模式  
*   ActiveX 控件  
*   其他旧版组件  

在 IE 模式下，呈现过程基于 Internet Explorer 11。  Microsoft Edge \ (Chromium\) 进程管理器处理呈现过程的生存期。  它受特定网站 \ (app\) 选项卡的生命周期) 。  当选项卡在 IE 模式下呈现时，特定选项卡的地址栏中将显示锁屏提醒。  

:::image type="complex" source="../media/ie-mode-badge.msft.png" alt-text="地址栏中的 IE 模式锁屏提醒" lightbox="../media/ie-mode-badge.msft.png":::
   地址栏中的 IE 模式锁屏提醒  
:::image-end:::  

IE 模式当前适用于 Windows 10 版本 1903 \ (2019 年 5 月 Update\) ，但即将向所有受支持的 Windows 平台提供。  

## <a name="launching-the-devtools-on-a-tab-in-ie-mode"></a>在 IE 模式下的选项卡上启动 DevTools  

如果尝试在 IE 模式下查看网站的文档模式，请选择地址栏中的锁屏提醒。  

:::image type="complex" source="../media/ie-mode-badge-doc-mode.msft.png" alt-text="使用 IE 模式锁屏提醒查看文档模式" lightbox="../media/ie-mode-badge-doc-mode.msft.png":::
   使用 IE 模式锁屏提醒查看文档模式  
:::image-end:::  

如果选项卡使用的是 IE 模式，则 DevTools 将不起作用，并且会出现以下情况。

*   如果选择或 `F12` 选择 `Ctrl` + `Shift` + `I` ，则启动 Microsoft Edge \ (Chromium\) DevTools 的空白实例将显示以下消息。  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   如果打开上下文菜单 \ (右键单击\) 并选择"查看源"，记事本启动****。  
*   如果打开上下文菜单 \ (右键单击\) ， **则 Inspect 元素** 不可见。  

DevTools \ (中的许多工具（如网络和性能工具\) ）不起作用的原因是****，呈现**** 引擎在 IE 模式下从 Chromium 切换到 Internet Explorer 11。  若要提供反馈，请导航到与开发人员[工具团队Microsoft Edge联系](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

:::image type="complex" source="../media/ie-mode-devtools.msft.png" alt-text="在 IE 模式下启动的 DevTools" lightbox="../media/ie-mode-devtools.msft.png":::
   在 IE 模式下启动的 DevTools  
:::image-end:::  

若要在 Internet Explorer 11 和 IE 模式下 (基于 Internet Explorer 11 的网站 \ (或 app\) ，请执行以下步骤。  

1.  打开Internet Explorer 11。  
    *   在Windows 10上，找到 Internet Explorer 11 的快捷方式。
        1.  **"开始"菜单**  > **Windows附件**  > **Internet Explorer 11**.  
    *   在Windows 7 上，找到"Internet Explorer 11"。
        1.  **"开始"菜单**  > **Internet Explorer 11**.  
1.  在 Internet Explorer 11 中，打开同一网页。  
1.  启动 Internet Explorer DevTools。  
    *   选择 `F12`。  
    *   将鼠标悬停在任意位置，打开上下文菜单 \ (右键单击\) ，然后选择 **"检查元素"。**  有关如何使用这些工具的信息，请导航到"[使用 F12 开发人员工具"。][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]  

如果 Internet Explorer 11 不可用，如在 Windows 11 上，可以使用 IEChooser 启动 Internet Explorer DevTools 来调试 IE 模式选项卡的内容。 若要使用 IEChooser，请执行以下步骤。

1.  打开 IEChooser。
    1. 打开“运行”对话框。 例如，按 `Windows logo key`  +  `R` 。
    2. 输入 `%systemroot%\system32\f12\IEChooser.exe` ，然后选择"确定 **"。**
2.  在 IEChooser 中，选择"IE 模式"选项卡的条目。


## <a name="remote-debugging-and-ie-mode"></a>远程调试和 IE 模式  

启动Microsoft Edge \ (Chromium\) ，同时从命令行界面启用远程调试。  Microsoft Visual Studio、Microsoft Visual Studio 代码和其他开发工具通常运行命令以启动Microsoft Edge。  以下命令启动Microsoft Edge将远程调试端口设置为 `9222` 。  

```shell
start msedge --remote-debugging-port=9222
```  

在使用命令行参数Microsoft Edge \ (Chromium\) 后，IE 模式将不可用。  你仍然可以导航到 IE 模式下 (或应用) 或应用\应用。  网站 \ (或 app\) 内容使用 Chromium 呈现，Internet Explorer 11。  预计依赖 IE11 的网页部分（如ActiveX）无法正确呈现。  IE 模式锁屏提醒不会显示在地址栏中。  

在完全关闭并重新启动 \Microsoft Edge \ (Chromium\) 之前，IE 模式仍然不可用。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "使用 F12 开发人员工具|Microsoft Docs"  
