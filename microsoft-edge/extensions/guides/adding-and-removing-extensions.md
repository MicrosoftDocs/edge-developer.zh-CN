---
description: 了解如何添加和删除扩展，以及如何将扩展的按钮移到地址栏旁边。
title: 添加和删除扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web 开发, html, css, javascript, 开发人员, 扩展
ms.custom: seodec18
ms.localizationpriority: high
ms.openlocfilehash: aeebc0f18d6b4a743c790571b8287a209233e73f
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866076"
---
# 添加、移动和删除 Microsoft Edge 的扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

**Windows 10 周年更新**中引入了 Microsoft Edge 扩展支持。 如果你正在开发 Microsoft Edge 扩展并希望加载它，或者如果你已经拥有扩展并且现在想要删除它，请查看下面的步骤。
还包括有关如何在浏览器中更改扩展图标位置的详细信息。

## 添加扩展

1. 打开 Microsoft Edge，然后在地址栏中键入“about:flags”。

2. 选中“**启用扩展开发人员功能**”复选框。

   ![about:flags 打开开发人员功能](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > 如果你没有 Windows 10 周年更新或更高版本，则此选项将不可用。

3. 选择“**更多 (...)**”以打开菜单。

   ![“更多”按钮](./../media/morebutton.png)  

4. 从菜单中选择“**扩展**”。

5. 选择“**加载扩展**”按钮。

   ![选择择“加载扩展”](./../media/sideload-load-extension.png)

6. 导航到你的扩展的文件夹，然后选择“**选择文件夹**”按钮。
   ![选择要加载的扩展文件夹](./../media/sideload-select-extension.png)
   > [!NOTE]
   > 如果加载扩展时遇到错误消息，请参阅[疑难解答](./../troubleshooting.md)页面获取指导。


**一切就绪！ 现在，你应该会看到 Microsoft Edge 的扩展窗格中列出的扩展。**

![扩展窗格中的扩展](./../media/sideload-extension-installed.png)

> [!NOTE]
> 后续启动 Microsoft Edge 时，未签名的扩展将自动关闭。 当浏览器进入空闲状态时（大约 10 秒钟后处于非活动状态），你将在窗口底部看到以下通知。 ![危险通知](./../media/riskynotification.png) 若要打开未签名的扩展，请单击“仍要启用”。



## 移动扩展按钮
根据扩展的设置，它可能会在“**更多 (...)**”菜单中显示。

   ![操作菜单](./../media/browseraction.png)  


如果想要将按钮移出此菜单以便更轻松地访问：

1. 右键单击扩展按钮。

2. 选择“**在地址栏旁边显示按钮**”。

   ![操作菜单](./../media/browseraction_contextmenu.png)  

或者，也可以从扩展详细信息页面执行此操作：

1. 单击扩展按钮。
2. 将“**在地址栏旁边显示按钮**”切换到开。

   ![显示打开的按钮开关](./../media/show-button-toggle.png)

> [!NOTE]
> 通过右键单击按钮并取消选择“**在地址栏旁边显示**”，或者转到扩展详细信息页面并将“**在地址栏旁边显示按钮**”切换到关，来将按钮移回到“**更多 (...)**”菜单。


## 删除扩展

1. 打开 Microsoft Edge。

2. 选择“**更多 (...)**”以打开菜单。

3. 从菜单中选择“**扩展**”。

4. 右键单击要删除的扩展，然后选择“**删除**”，或者选择该扩展，然后单击“**删除**”按钮。

   ![操作菜单](./../media/remove.png)  

**该扩展将从 Microsoft Edge 中的列表中消失。**
