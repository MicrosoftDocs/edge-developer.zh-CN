---
description: '如何使用 Microsoft Edge 的元素 (Chromium Visual Studio 代码中的) '
title: 'Microsoft Edge 的元素 (Chromium 从 Visual Studio 代码中) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、元素
ms.openlocfilehash: 81488c08a76a16b80a415cbd17cd0617df916f54
ms.sourcegitcommit: 1cfcf2c8970a6c2221cfbf09a23d36b08bd60690
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135478"
---
# 适用于 Visual Studio 代码扩展的 Microsoft Edge DevTools  

用途 <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] -->此扩展可在 Microsoft Edge DevTools 中访问 [Visual Studio 代码][VisualstudioCode]内部。  你有权访问 Microsoft Edge DevTools 中的 **元素** 和 **网络** 工具。  你可以启动或附加到 Microsoft Edge 实例。  连接后，你可能会显示运行时 HTML 结构、更改布局、修复样式设置问题以及检查网络流量。  

## 元素工具  

默认情况下，扩展在唯一窗口中启动浏览器实例，并向你提供 Microsoft Edge DevTools 的 **元素** 功能。  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码  
:::image-end:::  

在扩展设置中，你可以启用多个功能，如无 **外设模式** 和 **网络**。  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   在扩展设置中启用 \ (或禁用 \ ) 无外设模式和网络检查  
:::image-end:::  

## 无外设模式  

在无外设模式下，此扩展不启动要调试的完整浏览器实例。  它在后台运行实例。  您可能必须在编辑器内，并与嵌入的浏览器交互。  额外的浏览器图标不会显示在任务栏中。  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   Microsoft Edge DevTools 用于使用无外设浏览器运行的 Visual Studio 代码  
:::image-end:::  

> [!NOTE]
> 在 macOS 上，你应将无外设模式启用为你的首选模式。  使用无外设模式应解决以下问题：如果窗口不可见，浏览器窗口会报告它 `Not Active` 。  

## 网络工具  

如果你还想要检查你的应用程序的网络流量，请打开 "设置"，然后打开 " **网络** " 选项卡。  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools 适用于使用完整浏览器窗口运行的 Visual Studio 代码" lightbox="./media/edge-devtools-for-vscode-network.png":::
    Microsoft Edge DevTools 中用于 Visual Studio 代码的网络检查  
:::image-end:::  

## 从扩展启动 Microsoft Edge  

导航到 **活动栏**中的 "Microsoft Edge 工具"。  在它所显示的 **Microsoft Edge 工具：目标** 的位置旁边有一个加号，用于为你的应用打开浏览器。  如果选择 " **关于：空白** " 选项，则必须导航到浏览器中的 web 应用，以使其显示在 Visual Studio 代码的 " **元素** " 面板中。  

## 从 "调试" 视图启动 Microsoft Edge  

如果你习惯在 Visual Studio 代码中使用 "调试" 视图，请访问 Microsoft Edge DevTools。  

1.  在 Visual Studio 代码中，导航到 "调试" 视图 
    *   在 `Ctrl` + `Shift` + `D` `Command` + `Shift` + `D` macOS \ ) 上选择 "在 Windows/Linux \ (上"。  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  如果 Visual Studio 代码中没有任何配置，请完成以下操作之一。  
>     *   选择 `F5` 。  
>     *   选择 " **播放** \ (绿色 \ ) " 按钮。  
> 1.  在下拉列表中，选择下拉列表中的 " **边缘** "。  
> 1.  `launch.json`应显示包含以下配置的文件。  
>     
>     ```json
>     {
>       "version": "0.2.0",
>       "configurations": [
>         {
>           "name": "Launch Microsoft Edge and open the Edge DevTools",
>           "request": "launch",
>           "type": "vscode-edge-devtools.debug",
>           "url": "http://localhost:8080"
>         }
>       ]
>     }
>     ```  
>     
> 加载正确的配置后，请完成以下操作。  

1.  若要从 Visual Studio 代码启动 **元素** 工具，请完成以下操作之一。 
    *   选择 `F5` 。  
    *   选择 " **播放** \ (绿色 \ ) " 按钮。  
         
现在，你可以执行以下操作。  

*   访问浏览器的说明截屏视频。  
*   检查页面上组件的 DOM 和样式。  

## 附加到 Microsoft Edge  

若要打开浏览器并将实例附加到 Visual Studio 代码，请完成以下步骤。 

1.  若要打开 Microsoft Edge \ (Chromium \ ) 的实例，请复制并运行以下命令。  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  实例启动后，将以下代码片段复制并粘贴到您的 `launch.json` 文件中。  
    
    ```json
    {
        "type": "vscode-edge-devtools.debug",
        "request": "attach",
        "name": "Attach to Microsoft Edge and open the developer tools",
        "url": "http://localhost:3000/",
        "webRoot": "${workspaceFolder}/out",
        "port": 9222
    }
    ```  
    
1.  在 Visual Studio 代码中，打开 " **调试器** " 下拉菜单，然后选择 **"附加到 Microsoft Edge" 并打开 "开发工具工具"**。  
1.  若要从 Visual Studio 代码启动 **元素** 工具，请完成以下操作之一。 
    *   选择 `F5` 。  
    *   选择 " **播放** \ (绿色 \ ) " 按钮。  
         
现在，你可以执行以下操作。  

*   访问浏览器的说明截屏视频。  
*   检查页面上组件的 DOM 和样式。  
    
## 与 Microsoft Edge DevTools for Visual Studio 代码扩展团队取得联系  

通过针对扩展的[GitHub][GithubMicrosoftVscodeEdgeDevtools]存储库将[问题归档][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]来发送反馈。  

如果您希望帮助实现 <!--the Microsoft Edge DevTools for Visual Studio Code -->此扩展更好，您的发布内容是欢迎。  在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDevtools] 存储库中查找您需要的所有内容。  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题-microsoft/vscode-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "适用于 VS 代码的 Microsoft Edge 工具"  
