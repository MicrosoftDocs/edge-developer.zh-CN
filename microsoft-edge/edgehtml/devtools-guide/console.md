---
description: 使用控制台工具进行交互式调试和临时测试。
title: DevTools - 控制台
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 控制台
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 472aafa9e6c6fd98ea952804f0e92ed0b774f59c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232284"
---
# 控制台

Microsoft Edge 中的控制台开发人员工具记录与网页关联的信息，例如 JavaScript、网络请求和安全错误。 可以使用控制台进行交互式调试和临时测试。 

若要在 Microsoft Edge 中打开控制台工具，请按 F12 键以访问开发人员工具窗口 (或右键单击页面，然后选择"检查元素") 。 **** 然后，选择 **窗口** 顶部的"控制台"选项卡。 

您还可以使用控制台工具与正在运行的网页进行通信和从该网页进行通信。 可以使用控制台：

- 在 [代码运行时](./console/error-and-status-codes.md) 发布标准错误和状态代码和信息性消息。
- 通过包括在代码中的控制台 [API](./console/console-api.md) 调用生成自定义调试日志。
- 提供 [用于检查关键](./console/command-line.md) 变量和函数的当前返回值的命令行和交互式树视图。

## 控制台的各个部分

下图显示了控制台的关键部分：

![Microsoft Edge DevTools 控制台](./media/console.png)

1. **错误**  / **警告**  / **信息**  / **日志**按钮：按指定类型筛选控制台输出。 按住 Ctrl 键可以多**选按钮。** " **所有** "按钮清除所有筛选器。

2. **Ctrl+L** (**** 清除按钮) ："清除"按钮可清除**** 当前控制台的显示。

3. **"保留**日志"复选框：选中****"保留日志"复选框可跨页面刷新、关闭和重新打开 DevTools 保留控制台输出。 控制台历史记录仅在关闭选项卡或手动清除控制台时清除。

4. **目标**：使用 **"** 目标"下拉菜单切换到其他执行上下文，如页面中的上下文或 `<iframe>` 正在运行的扩展。 默认情况下，选择页面的顶级框架。 将鼠标悬停在选定框架上将显示一个工具提示，用于显示该资源的完整 URL。

5. **显示控制台**  / **按** **Ctrl** (隐藏控制台) ：除了控制台面板之外，还可以按"显示控制台隐藏控制台"按钮，从任何其他 +  **&grave;** DevTools****  /  **** 面板的底部使用控制台。 当 DevTools 打开到控制台面板时，该按钮不起作用。
 
6. **筛选日志** (**Ctrl+F**) ：您还可以使用搜索框中的特定文本字符串筛选日志。

7. **调试器**：选择任何蓝色源链接，将 DevTools 调试器打开到该特定代码行，以便进一步检查。

## 快捷方式

操作                                            | 快捷方式               
:-------------------------------------------------| :----------------------
在焦点上启动具有控制台的 DevTools             | **Ctrl**  + **Shift**  + **J** 
切换到控制台                                 | **Ctrl**  + **2**           
从另一个"开发工具"选项卡显示/隐藏控制台       | **Ctrl**  +  **&grave;** (刻度线)   
执行 (命令行命令)                      | **Enter**                
无需执行多行 (换行符)  | **Shift**  + **Enter**或**Ctrl**  +  **Enter**      
清除所有邮件的控制台                 | **Ctrl**  + **L**           
筛选器日志 (将焦点设置为搜索框)              | **Ctrl**  + **F**           
当焦点在焦点 (接受自动完成)  | **Enter** 或 **Tab**       
上一个/下一个自动完成建议          | **向上箭头键** /**向下箭头键**   
