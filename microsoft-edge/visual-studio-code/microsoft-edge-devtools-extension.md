---
description: 如何使用元素从Microsoft Edge (Chromium) Visual Studio Code
title: 用于Microsoft Edge (Chromium) 元素Visual Studio Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， vs code， visual studio code， 元素
ms.openlocfilehash: 83bac187fa2a9b1766a52f3f2cd176f171846e02
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398453"
---
# <a name="microsoft-edge-devtools-for-visual-studio-code-extension"></a>Microsoft Edge用于开发人员扩展Visual Studio Code工具  

用途 <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] -->此扩展用于访问 Microsoft Edge Code[内 Microsoft Visual Studio DevTools。][VisualstudioCode]  你有权访问开发人员**工具****中的元素**Microsoft Edge工具。  可以启动或附加到应用程序实例Microsoft Edge。  连接后，你可能会显示运行时 HTML 结构、更改布局、修复样式设置问题并检查网络流量。  

## <a name="elements-tool"></a>元素工具  

默认情况下，扩展将在唯一窗口中启动浏览器实例，并为你提供 DevTools **** Microsoft Edge功能。  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="Microsoft Edge用于运行Visual Studio Code浏览器窗口运行的 DevTools" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   Microsoft Edge用于运行Visual Studio Code浏览器窗口运行的 DevTools  
:::image-end:::  

在扩展设置中，你可以启用更多功能，如无**头模式和网络**。 ****  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="在 (设置中启用) 无头模式和网络检查" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   在扩展 (启用 \) 或禁用\无头模式和网络检查  
:::image-end:::  

## <a name="headless-mode"></a>无头模式  

在无头模式下，此扩展不会启动完整的浏览器实例进行调试。  它在后台运行实例。  你可能必须停留在编辑器内并与嵌入的浏览器交互。  任务栏中不会显示额外的浏览器图标。  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="Microsoft Edge用于无Visual Studio Code运行的 DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   Microsoft Edge用于使用无Visual Studio Code浏览器运行的 DevTools  
:::image-end:::  

> [!NOTE]
> 在 macOS 上，应打开无头模式作为首选模式。  使用无头模式应该可以解决一个问题，即如果窗口不可见，浏览器窗口将报告它是 `Not Active` 。  

## <a name="network-tool"></a>网络工具  

如果还要检查应用程序的网络流量，请打开设置并打开"网络 **"** 选项卡。  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge开发人员工具中的网络Visual Studio Code" lightbox="./media/edge-devtools-for-vscode-network.png":::
    Microsoft Edge开发人员工具中的网络Visual Studio Code  
:::image-end:::  

## <a name="launching-microsoft-edge-from-the-extension"></a>从Microsoft Edge启动  

导航到Microsoft Edge栏中的"工具 **"。**  旁边显示 **"Microsoft Edge：** 目标"，旁边有一个加号，用于打开应用的浏览器。  如果选择 **"about：blank"** 选项，则必须在浏览器中导航到 Web 应用，这样它将显示在 Visual Studio Code 中的****"元素"面板中。  

## <a name="launching-microsoft-edge-from-the-debug-view"></a>从Microsoft Edge视图启动应用程序  

如果你习惯使用调试视图中的调试Visual Studio Code，请Microsoft Edge访问 DevTools。  

1.  在Visual Studio Code中，导航到"调试"视图 
    *   在 `Ctrl` + `Shift` + `D` macOS\Windows 上的 `Command` + `Shift` + `D` (/Linux \) 上选择。  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  如果配置中没有任何Visual Studio Code，请完成以下操作之一。  
>     *   选择 `F5`。  
>     *   选择" **播放** \ (绿色\) 按钮。  
> 1.  在下拉列表中 **，选择下拉列表** 中的"边缘"。  
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
> 加载正确配置后，请完成以下操作。  

1.  若要从"**元素"Visual Studio Code，** 请完成以下操作之一。 
    *   选择 `F5`。  
    *   选择" **播放** \ (绿色\) 按钮。  
         
现在，您可以执行以下操作。  

*   访问浏览器的屏幕视频。  
*   检查页面上组件的 DOM 和样式。  

## <a name="attaching-to-microsoft-edge"></a>附加到Microsoft Edge  

若要打开浏览器并将实例附加到Visual Studio Code，请完成以下步骤。 

1.  若要打开 \Microsoft Edge \ (Chromium\) 的实例，请复制并运行以下命令。  
    
    ```shell
    start msedge --remote-debugging-port=9222
    ```  
    
1.  实例启动后，将以下代码段复制并粘贴到 `launch.json` 文件中。  
    
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
    
1.  In Visual Studio Code， open the **Debugger** drop-down menu and choose **Attach to Microsoft Edge and open the developer tools**.  
1.  若要从"**元素"Visual Studio Code，** 请完成以下操作之一。 
    *   选择 `F5`。  
    *   选择" **播放** \ (绿色\) 按钮。  
         
现在，您可以执行以下操作。  

*   访问浏览器的屏幕视频。  
*   检查页面上组件的 DOM 和样式。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-for-visual-studio-code-extension-team"></a>与开发人员扩展Microsoft Edge开发人员工具Visual Studio Code联系  

通过针对扩展[的][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]GitHub[提交问题来][GithubMicrosoftVscodeEdgeDevtools]发送反馈。  

如果你需要帮助 <!--the Microsoft Edge DevTools for Visual Studio Code -->此扩展更好，欢迎您做出贡献。  在扩展的 GitHub[查找入门][GithubMicrosoftVscodeEdgeDevtools]所需的一切。  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio Code"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题 - microsoft/vscode-edge-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge工具Visual Studio Code"  
