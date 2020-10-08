---
description: 使用 F12 开发人员工具，了解如何调试扩展的后台脚本、内容脚本和扩展页。
title: 扩展-调试
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、javascript、开发人员、调试、调试
ms.custom: seodec18
ms.openlocfilehash: 34488870cb4e4a92a9d57859509ce7d1176cf284
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563301"
---
# 调试扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

你可以使用 F12 开发人员工具在 Microsoft Edge 中调试你的扩展。

下面的视频介绍了一个有问题的 Microsoft Edge 扩展，并浏览每个调试方案并按方式进行修复。 有关详细信息，请参阅下面的分步说明。

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]


> [!NOTE]
> 为了利用对 F12 的扩展调试，您必须首先打开关于：标志的开发人员功能。 有关如何执行此操作的详细信息，请参阅 [添加和删除扩展](./adding-and-removing-extensions.md) 。


## 后台脚本调试
若要开始调试你的扩展的后台脚本，请执行以下操作：

1. 单击 " **更多 ( ..." ) ** ，然后单击 " **扩展** "，转到 "扩展" 窗格中。  
 ![“更多”按钮](./../media/morebutton.png)
2. 单击要调试的扩展。
3. 单击 " **背景页** " 链接以弹出后台进程的 F12。  
 !["检查链接" 选项的选定扩展视图](./../media/debug-inspect.png)
4. 选择 F12 中的 " **调试器** " 选项卡。
5. 导航到并选择您的扩展的后台脚本。
6. 通过单击源代码行号的左侧，放置用于调试的断点。  
 ![显示带中断点的后台脚本的 f12 控制台](./../media/debug-f12-background.png)
7. 选择 " **控制台** " 选项卡，然后执行命令 " `location.reload()` "。 这将重新执行后台脚本，使你可以逐句通过代码。  
 ![带有位置的控制台。已输入重新加载](./../media/debug-f12-background-console.png)


## 内容脚本调试
要开始调试您的扩展的内容脚本，请执行以下操作：

1. 通过导航到 " **更多 ( ) ... ** " 按钮，然后选择 **"F12 开发工具"** ，或按键盘上的 F12，启动 F12。
2. 导航到您的扩展内容脚本，然后选择它。 当前正在运行的扩展的内容脚本将由每个扩展名的不同文件夹进行描绘。

    > [!NOTE]
    > 将仅显示运行的内容脚本。

3. 通过单击源代码行号的左侧，放置用于调试的断点。  
 ![正在调试的内容脚本的 f12](./../media/debug-content-f12.png)
4. 刷新浏览器选项卡，通过代码开始单步执行。




## 扩展页面调试

可使用两种方法来访问用于调试的扩展页面的源代码。 一种方法适用于各种页面，而另一种方法仅适用于弹出式页面。

### 调试任何扩展页
以下方法适用于所有扩展名页面，例如 "选项" 页面和弹出窗口：


1. 右键单击您的页面的背景。
2. 选择 **"查看源"**。

   ![带 f12 的弹出调试](./../media/debug-popup-select.png)

3. 打开 F12 后，在要调试的文件中放置断点。

   ![带 f12 的弹出调试](./../media/debug-popup-f12.png)
4. 选择 " **控制台** " 选项卡，然后执行命令 `location.reload()` 。 这将重新执行页面脚本，使你可以逐句通过代码。  

   ![带有位置的控制台。已输入重新加载](./../media/debug-f12-background-console.png)

### 调试弹出窗口扩展页
虽然调试扩展页的方法也适用于弹出窗口扩展页面，但以下步骤概括了调试弹出窗口的另一种方法：

1. 右键单击您的扩展名图标。
2. 选择 **"检查弹出窗口"**。

   ![弹出调试检查](./../media/debug-popup-inspect.png)
3. 按照上面的步骤3和4操作，放置断点并重新加载弹出窗口。
