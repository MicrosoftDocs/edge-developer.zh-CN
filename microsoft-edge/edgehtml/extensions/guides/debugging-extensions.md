---
description: 使用 F12 开发人员工具，了解如何调试扩展的后台脚本、内容脚本和扩展页。
title: 扩展 - 调试
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， javascript， 开发人员， 调试， 调试
ms.custom: seodec18
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 17da1a2badd99dd57bb8b1e3de063fe045b34333
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232640"
---
# 调试扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

可以使用 F12 开发人员工具在 Microsoft Edge 中调试扩展。

下面的视频将浏览一个缺陷的 Microsoft Edge 扩展，浏览每个调试方案并一直进行修复。 有关详细信息，请参阅下面的分步说明。

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Debugging-Microsoft-Edge-Extensions/player]


> [!NOTE]
> 为了利用 F12 的扩展调试，必须先打开 about：flags 中的开发人员功能。 请参阅 [添加和删除扩展](./adding-and-removing-extensions.md) ，详细了解如何这样做。


## 后台脚本调试
若要开始调试扩展的后台脚本，请执行以下操作：

1. 单击 **"更多 (...) ** 后跟 **"扩展** "转到扩展窗格。  
 ![“更多”按钮](./../media/morebutton.png)
2. 单击要调试的扩展。
3. 单击" **后台"页面** 链接，为后台进程显示 F12。  
 ![具有检查链接的选项的选定扩展视图](./../media/debug-inspect.png)
4. 选择 **F12 中的** "调试器"选项卡。
5. 导航到扩展的后台脚本并选择该脚本。
6. 单击源代码行号的左侧，放置用于调试的断点。  
 ![显示具有断点的背景脚本的 f12 控制台](./../media/debug-f12-background.png)
7. 选择控制台 **选项卡** 并执行命令 `location.reload()` ""。 这将重新执行后台脚本，从而允许您逐步执行代码。  
 ![已输入 location.reload 的控制台](./../media/debug-f12-background-console.png)


## 内容脚本调试
若要开始调试扩展的内容脚本，请执行以下操作：

1. 通过导航到"更多工具 ** (...) ** 按钮并选择 **"F12** 开发人员工具"或按键盘上的 F12 启动 F12。
2. 导航到扩展的内容脚本并选择该脚本。 当前运行的扩展的内容脚本将用每个扩展的不同文件夹进行描述。

    > [!NOTE]
    > 只显示运行的内容脚本。

3. 单击源代码行号的左侧，放置用于调试的断点。  
 ![正在调试内容脚本的 f12](./../media/debug-content-f12.png)
4. 刷新浏览器选项卡以开始逐步执行代码。




## 扩展页调试

有两种方法可用于访问扩展页的源代码进行调试。 一种方法适用于各种页面，另一种方法仅适用于弹出窗口。

### 调试任何扩展页
以下方法适用于所有扩展页，如选项页和弹出窗口：


1. 右键单击页面背景。
2. 选择 **"查看源"。**

   ![使用 f12 进行弹出式调试 - 选择](./../media/debug-popup-select.png)

3. F12 打开后，在要调试的文件中放置断点。

   ![使用 f12 进行弹出式调试](./../media/debug-popup-f12.png)
4. 选择 **控制台选项卡** 并执行命令 `location.reload()` 。 这将重新执行页面脚本，从而允许您逐步执行代码。  

   ![已输入 location.reload 的控制台](./../media/debug-f12-background-console.png)

### 调试弹出窗口扩展页
虽然调试扩展页的方法也适用于弹出扩展页，但以下步骤概述了调试弹出窗口的另一种方法：

1. 右键单击扩展的图标。
2. 选择 **"检查弹出窗口"。**

   ![弹出窗口调试检查](./../media/debug-popup-inspect.png)
3. 按照上面的步骤 3 和 4 放置断点并重新加载弹出窗口。
