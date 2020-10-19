---
description: '如何使用 Microsoft Edge 的元素 (Chromium 从 VS 代码) '
title: 'Microsoft Edge 的元素 (Chromium 从 VS 代码) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、元素
ms.openlocfilehash: ef516d8364c68b550f889bcad0fe762a73ce5f99
ms.sourcegitcommit: 652009c5cea9e75c22b077f0cbcdc0d96bd337ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10694860"
---
# Microsoft Edge 与代码扩展的元素  

使用 [Microsoft edge][VisualstudioMarketplaceElementsMicrosoftEdgeChromium] 和代码扩展的元素，在 [Visual Studio 代码][VisualstudioCode]中使用 microsoft edge 浏览器的 "元素" 工具。  通过启动或附加，元素工具连接到 Microsoft Edge 实例，显示运行时 HTML 结构，并允许你更改布局或修复样式设置问题。  

:::image type="complex" source="./media/elements-for-edge.gif" alt-text="工作中的边缘与代码扩展的元素":::
   工作中的边缘与代码扩展的元素  
:::image-end:::

<!--![Elements for Edge VS Code extension at work][ImageGifElementsEdge]  -->  

## 从元素扩展启动 Microsoft Edge  

导航到 **活动栏**中的元素。  在它所示的 **Microsoft Edge 元素的** 位置旁边，有一个加号，可为你的应用打开浏览器。  如果选择了 &quot; **关于：空白** &quot; 选项，则必须导航到浏览器中的 web 应用，以使其显示在 &quot;元素&quot; 面板中的 VS 代码中。  

## 从 &quot;调试&quot; 视图启动 Microsoft Edge  

如果你习惯在 Visual Studio 代码中使用 &quot;调试&quot; 视图，请访问该工具中的元素。  导航到 `Ctrl` + `Shift` + `D` Windows 上或 `Command` + `Shift` + `D` macOS \ ) 上的 &quot;调试&quot; 视图 \ (。  

如果 VS 代码中没有任何配置，请按 `F5` Windows 或 macOS 或选择绿色的 &quot; **播放** &quot; 按钮。 在下拉列表中选择 &quot; **边缘** &quot;。 你应该会看到 `launch.json` 具有以下配置的文件。  

```json
{
    &quot;version&quot;: &quot;0.2.0&quot;,
    &quot;configurations&quot;: [
        {
            
            &quot;name&quot;: &quot;Launch Microsoft Edge and open the Elements tool&quot;,
            &quot;request&quot;: &quot;launch&quot;,
            &quot;type&quot;: &quot;vscode-edge-devtools.debug&quot;,
            &quot;url&quot;: &quot;http://localhost:3000&quot;
        
        }
    ]
}
```  

加载正确的配置后，请按 `F5` Windows 或 macOS 或选择绿色的 &quot; **播放** " 按钮。 从 Microsoft Edge 浏览器启动的 VS 代码中，你熟悉的元素工具使你能够访问浏览器的说明截屏视频，并检查页面组件。  

## 附加到 Microsoft Edge  

若要将 VS 代码附加到 Microsoft Edge \ (Chromium \ ) 的实例，必须通过从你的终端运行以下命令来启动浏览器。  

`start msedge --remote-debugging-port=9222`  

应用启动后，将以下配置添加到文件上的 **launch.js** ：  

```json
{
    "type": "vscode-edge-devtools.debug",
    "request": "attach",
    "name": "Attach to Microsoft Edge and open the Elements tool",
    "url": "http://localhost:3000/",
    "webRoot": "${workspaceFolder}/out",
    "port": 9222
}
```  

选择 " **附加到 Microsoft Edge"，然后** 从 "调试器" 下拉菜单中打开 "元素" 工具。  接下来，按 " `F5` Windows" 或 "macOS" 或选择 "绿色 **播放** " 按钮。  VS 代码启动 "元素" 工具，使你可以访问浏览器的说明截屏视频、检查 DOM 以及页面上组件的样式。  

## 与 Microsoft Edge 和代码扩展团队的元素保持联系  

通过针对扩展的[GitHub][GithubMicrosoftVscodeEdgeDevtools]存储库将[问题归档][GithubMicrosoftVscodeEdgeDevtoolsNewIssue]来发送反馈。  

如果你希望帮助使 Microsoft Edge 与代码扩展的元素更好，你的发布是欢迎的！  在扩展的 [GitHub][GithubMicrosoftVscodeEdgeDevtools] 存储库中查找您需要的所有内容。  

<!-- image links -->  

<!--[ImageGifElementsEdge]: ./media/elements-for-edge.gif "Elements for Edge VS Code extension in action"  -->  
[ImagePngElementsEdge]：/media/elements-for-edge.png "操作中的边缘与代码扩展的元素"  

<!--links -->  

[VscodeElementsEdge]: ./elements-for-edge.md "Microsoft Edge 与代码扩展的元素 |Microsoft 文档"  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsNewIssue]: https://github.com/Microsoft/vscode-edge-devtools/issues/new "新问题-microsoft/vscode-devtools |GitHub"

[VisualstudioMarketplaceElementsMicrosoftEdgeChromium]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge 的元素 (Chromium) |Visual Studio Marketplace"  
