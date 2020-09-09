---
description: IE 模式和 Microsoft Edge (Chromium) DevTools
title: Internet Explorer 模式和 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、ie11、internet explorer 11、ie 模式
ms.openlocfilehash: b059cae3ff48a45fe92cbf69e37ad692e329b200
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003959"
---
# Internet Explorer 模式和 DevTools  

本文介绍 Internet Explorer 模式 \ (IE 模式 \ ) 与 Microsoft Edge \ (Chromium \ ) DevTools 集成。  

## 了解 IE 模式  

IE 模式允许企业指定仅在 Internet Explorer 11 中工作的网站列表。  当您在 Microsoft Edge \ (Chromium \ ) 中导航到这些网站时，Internet Explorer 11 的一个实例在选项卡中运行并呈现网站。 此功能允许企业管理与当前与任何现代 web 浏览器不兼容的技术的兼容性。  IE 模式中包括对以下技术的支持。  

*   IE 文档模式  
*   ActiveX 控件  
*   其他旧版组件  

在 IE 模式下，呈现过程基于 Internet Explorer 11。  Microsoft Edge \ (Chromium \ ) 进程管理器处理呈现过程的生存期。  它受限于特定网站 \ (或 app \ ) 的选项卡的生命周期。  在 IE 模式下呈现选项卡时，特定选项卡的地址栏中将显示一个标记。  

:::image type="complex" source="./media/ie-mode-badge.msft.png" alt-text="地址栏中的 IE 模式标记" lightbox="./media/ie-mode-badge.msft.png":::
   地址栏中的 IE 模式标记  
:::image-end:::  

IE 模式目前在 Windows 10 版本的 1903 \ 上可用 (可能2019更新 \ ) ，但即将推出所有受支持的 Windows 平台。  

## 在 IE 模式下的选项卡上启动 DevTools  

如果您尝试在 IE 模式下查看网站的文档模式，请选择地址栏中的锁屏提醒。  

:::image type="complex" source="./media/ie-mode-badge-doc-mode.msft.png" alt-text="使用 IE 模式锁屏提醒查看文档模式" lightbox="./media/ie-mode-badge-doc-mode.msft.png":::
   使用 IE 模式锁屏提醒查看文档模式  
:::image-end:::  

如果选项卡使用的是 IE 模式，则 DevTools 不起作用，并且会出现以下情况。

*   如果您选择 `F12` 或选择 `Ctrl` + `Shift` + `I` ""，则会启动 Microsoft Edge \ (Chromium \ ) DevTools 的空实例，并显示以下消息。  
    
    ```text
    Developer Tools are not available in Internet Explorer mode.  To debug the page, open it in Internet Explorer 11.
    ```  
    
*   如果打开上下文菜单 \ (右键单击 \ ) 并选择 " **查看源**"，将启动 "记事本"。  
*   如果打开上下文菜单 \ (右键单击 \ ) ，将看不到 " **检查" 元素** 。  

DevTools (中类似于 **网络** 和 **性能** 工具的许多工具 \ ) 不起作用是呈现引擎在 IE 模式下从 Chromium 切换到 Internet Explorer 11。  若要提供反馈，请导航到 [与 Microsoft Edge DevTools 团队取得联系](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

:::image type="complex" source="./media/ie-mode-devtools.msft.png" alt-text="在 IE 模式下启动的 DevTools" lightbox="./media/ie-mode-devtools.msft.png":::
   在 IE 模式下启动的 DevTools  
:::image-end:::  

要在 Internet Explorer 11 和 IE 模式下测试您的基于 Internet Explorer 11 的网站 \ (或应用 \ ) ，请执行以下步骤。  

1.  打开 Internet Explorer 11。  
    *   在 Windows 10 上，找到 Internet Explorer 11 的快捷方式。
        1.  **开始菜单**  > **Windows 附件**  > **Internet Explorer 11**。  
    *   在 Windows 7 上，找到 "Internet Explorer 11"。
        1.  **开始菜单**  > **Internet Explorer 11**。  
1.  在 Internet Explorer 11 中，打开相同的网页。  
1.  启动 Internet Explorer DevTools。  
    *   选择 `F12` 。  
    *   将鼠标悬停在任意位置，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **检查元素**"。  有关如何使用这些工具的详细信息，请导航到 [使用 F12 开发人员工具][PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]。  

## 远程调试和 IE 模式  

启动 Microsoft Edge \ (Chromium \ ) 从命令行界面打开远程调试。  Visual Studio、Visual Studio 代码和其他开发工具通常运行命令来启动 Microsoft Edge。  以下命令将启动设置为的远程调试端口的 Microsoft Edge `9222` 。  

```shell
start msedge --remote-debugging-port=9222
```  

启动 Microsoft Edge \ (Chromium \ ) 使用命令行参数时，IE 模式不可用。  您仍然可以导航到 "网站 \ (" 或 "应用 \ ) "，否则将在 IE 模式下显示这些应用。 网站 \ (或应用 \ ) 内容使用 Chromium （而不是 Internet Explorer 11）呈现。  希望页面中依赖 IE11 的部分（如 ActiveX 控件）无法正确呈现。  IE 模式标记不会显示在地址栏中。  

在完全关闭并重新启动 Microsoft Edge \ (Chromium \ ) 之前，IE 模式保持不可用。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- links -->  

[PreviousVersionsWindowsInternetExplorerDeveloperSamplesbg182326]: /previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85) "使用 F12 开发人员工具 |Microsoft 文档"  