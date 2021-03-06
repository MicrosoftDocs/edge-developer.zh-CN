---
description: 如何使用 Microsoft Edge 元素 (代码中) Chromium Visual Studio
title: Microsoft Edge 元素 (代码中) Chromium Visual Studio
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
# <a name="microsoft-edge-devtools-for-visual-studio-code-extension"></a>Microsoft Edge DevTools for Visual Studio Code extension  

用途 <!--the [Microsoft Edge DevTools for Visual Studio Code][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] -->此扩展以在 Microsoft Edge DevTools 中访问 Microsoft Visual Studio [Code。][VisualstudioCode]  你有权访问 Microsoft **** Edge DevTools**中的元素**和网络工具。  可以启动或附加到 Microsoft Edge 的实例。  连接后，可以显示运行时 HTML 结构、更改布局、修复样式设置问题以及检查网络流量。  

## <a name="elements-tool"></a>元素工具  

默认情况下，扩展将在唯一窗口中启动浏览器实例，并为你提供 Microsoft Edge **** DevTools 的元素功能。  

:::image type="complex" source="./media/edge-devtools-for-vscode-windowed.png" alt-text="Microsoft Edge DevTools for Visual Studio在完整浏览器窗口中运行的代码" lightbox="./media/edge-devtools-for-vscode-windowed.png":::
   Microsoft Edge DevTools for Visual Studio在完整浏览器窗口中运行的代码  
:::image-end:::  

在扩展设置中，你可以启用更多功能，如无**头模式和网络**。 ****  

:::image type="complex" source="./media/edge-devtools-for-vscode-settings.png" alt-text="在 (设置中启用) 无头模式和网络检查" lightbox="./media/edge-devtools-for-vscode-settings.png":::
   启用 \ (或禁用\) 扩展设置中的无头模式和网络检查  
:::image-end:::  

## <a name="headless-mode"></a>无头模式  

在无头模式下，此扩展不会启动完整的浏览器实例进行调试。  它在后台运行实例。  你可能必须留在编辑器内并与嵌入的浏览器交互。  任务栏中不显示额外的浏览器图标。  

:::image type="complex" source="./media/edge-devtools-for-vscode-headless.png" alt-text="用于无Visual Studio运行的代码的 Microsoft Edge DevTools" lightbox="./media/edge-devtools-for-vscode-headless.png":::
   用于无Visual Studio运行的代码的 Microsoft Edge DevTools  
:::image-end:::  

> [!NOTE]
> 在 macOS 上，应打开无头模式作为首选模式。  使用无头模式应解决一个问题，如果窗口不可见，浏览器窗口将报告它 `Not Active` 。  

## <a name="network-tool"></a>网络工具  

如果还要检查应用程序的网络流量，请打开设置并打开"网络 **"** 选项卡。  

:::image type="complex" source="./media/edge-devtools-for-vscode-network.png" alt-text="Microsoft Edge DevTools for Visual Studio 中的网络检查" lightbox="./media/edge-devtools-for-vscode-network.png":::
    Microsoft Edge DevTools for Visual Studio 中的网络检查  
:::image-end:::  

## <a name="launching-microsoft-edge-from-the-extension"></a>从扩展启动 Microsoft Edge  

导航到活动栏中的 Microsoft Edge **工具**。  旁边显示 **"Microsoft Edge 工具： 目标"，** 旁边有一个为你的应用打开浏览器的加号。  如果选择 **"about：blank"** 选项，则必须在浏览器中导航到 Web 应用，以在"代码"中的"**** 元素"Visual Studio中显示。  

## <a name="launching-microsoft-edge-from-the-debug-view"></a>从调试视图启动 Microsoft Edge  

如果你习惯在代码中使用调试Visual Studio，请从它访问 Microsoft Edge DevTools。  

1.  在Visual Studio中，导航到"调试"视图 
    *   在 `Ctrl` + `Shift` + `D` windows/Linux \ (`Command` + `Shift` + `D` macOS\) 。  

<!--TODO:  Is this section intended to be optional  -->  
> [!NOTE]
> 1.  如果代码中没有任何配置Visual Studio，请完成以下操作之一。  
>     *   选择 `F5`。  
>     *   选择 **"播放** \ (绿色\) 按钮。  
> 1.  在下拉列表中，选择 **下拉列表** 中的"边缘"。  
> 1.  应 `launch.json` 显示包含以下配置的文件。  
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

1.  若要 **从代码Visual Studio** 元素工具，请完成以下操作之一。 
    *   选择 `F5`。  
    *   选择 **"播放** \ (绿色\) 按钮。  
         
现在，您可以执行下列操作。  

*   访问浏览器的屏幕视频。  
*   检查页面上组件的 DOM 和样式。  

## <a name="attaching-to-microsoft-edge"></a>附加到 Microsoft Edge  

若要打开浏览器并将该实例附加到Visual Studio代码，请完成以下步骤。 

1.  若要打开 Microsoft Edge \ (Chromium\) 的实例，请复制并运行以下命令。  
    
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
    
1.  在Visual Studio中，打开 **调试** 器下拉菜单，然后选择"附加到 **Microsoft Edge"，然后打开开发人员工具**。  
1.  若要 **从代码Visual Studio** 元素工具，请完成以下操作之一。 
    *   选择 `F5`。  
    *   选择 **"播放** \ (绿色\) 按钮。  
         
现在，您可以执行下列操作。  

*   访问浏览器的屏幕视频。  
*   检查页面上组件的 DOM 和样式。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-for-visual-studio-code-extension-team"></a>联系 Microsoft Edge 开发人员工具Visual Studio代码扩展团队  

通过针对扩展 [的][GithubMicrosoftVscodeEdgeDevtoolsNewIssue] [GitHub 存储库][GithubMicrosoftVscodeEdgeDevtools] 提交问题来发送反馈。  

如果你想要帮助创建 <!--the Microsoft Edge DevTools for Visual Studio Code -->此扩展效果更好，欢迎你做出贡献。  在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDevtools] 存储库中查找入门所需的一切。  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档|Visual Studio代码"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题 - microsoft/vscode-edge-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code"  
