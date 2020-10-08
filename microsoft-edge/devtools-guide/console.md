---
description: 使用 "控制台" 工具进行交互式调试和临时测试。
title: DevTools-Console
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、console
ms.custom: seodec18
ms.openlocfilehash: f2733cac57ed5f2364747ee64e669fa83aae41f4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563512"
---
# 控制台

Microsoft Edge 中的控制台开发人员工具可记录与网页相关联的信息，例如 JavaScript、网络请求和安全错误。 你可以使用该控制台进行交互式调试和临时测试。 

若要打开 Microsoft Edge 中的控制台工具，请按 F12 键访问开发工具窗口 (或右键单击页面，然后选择 " **检查元素** ") 。 然后，选择窗口顶部的 " **控制台** " 选项卡。 

您也可以使用 "控制台" 工具与正在运行的网页进行通信。 您可以使用该控制台执行以下操作：

- 在代码运行时发布标准 [错误和状态代码](./console/error-and-status-codes.md) 以及信息性消息。
- 从你的代码中包含的 [控制台 API](./console/console-api.md) 调用生成自定义调试日志。
- 提供用于检查关键变量和函数的当前返回值的 [命令行](./console/command-line.md) 和交互式树视图。

## 控制台的部件

下图显示了控制台的关键部分：

![Microsoft Edge DevTools 控制台](./media/console.png)

1. **错误**  / **警告**  / **信息**  / **日志**按钮：按指定类型筛选控制台输出。 您可以通过按住 **Ctrl** 键来选择多个按钮。 " **全部** " 按钮将清除所有筛选器。

2. "**清除**" 按钮 (**Ctrl + L**) ： "**清除**" 按钮将清除当前的控制台显示。

3. "**保留日志**" 复选框：选中 "**保留日志**" 复选框将在页面刷新和关闭并重新打开 DevTools 时保持您的控制台输出。 仅当关闭选项卡或手动清除控制台时，才会清除控制台历史记录。

4. **目标**：使用 " **目标** " 下拉菜单切换到其他执行上下文，例如 `<iframe>` 页面中的页面或运行的扩展。 默认情况下，您的页面的顶级框架处于选中状态。 将鼠标悬停在所选的框架上将显示一个工具提示，显示该资源的完整 URL。

5. **显示控制台**  / **隐藏 "控制台**" 按钮 (**Ctrl** +  **&grave;** ) ：除了 "控制台" 面板之外，还可以通过按 "**显示控制台**  /  **隐藏控制台**" 按钮，使用其他 DevTools 面板底部的控制台。 在将 DevTools 打开到控制台面板时，该按钮不起作用。
 
6.  (**Ctrl + F**) **筛选日志**：还可以使用搜索框中的特定文本字符串筛选日志。

7. **调试器**：选择任何蓝色源链接以打开该特定代码行的 DevTools 调试程序进行进一步检查。

## 快捷方式

操作                                            | 快捷方式               
:-------------------------------------------------| :----------------------
在关注的控制台中启动 DevTools             | **Ctrl**  + **班次**  + **J** 
切换到控制台                                 | **Ctrl**  + **2**           
从另一个 DevTools 选项卡中显示/隐藏控制台       | **Ctrl**  +  Ctrl **&grave;** ("后退" 滴答)   
"执行 (单行" 命令)                      | **Enter**                
不执行 (多行命令的换行符)  | **班次**  + **Enter**或**Ctrl**  +  **enter**      
清除所有邮件的控制台                 | **Ctrl**  + **L**           
筛选日志 (将焦点设置到 "搜索" 框)              | **Ctrl**  + **F**           
在焦点) 时接受自动完成建议 ( | **Enter** 或 **Tab**       
上一个/下一个自动完成建议          | **向上键** /**向下键**   


