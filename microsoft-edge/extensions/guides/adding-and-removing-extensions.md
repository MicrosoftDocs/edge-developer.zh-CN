---
description: 了解如何添加和删除扩展，以及如何移动地址栏旁边的扩展按钮。
title: 添加和删除扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、扩展
ms.custom: seodec18
localization_priority: Priority
ms.openlocfilehash: fdc6950962e7ce7e0a720d0bafa7e2c63ebd7098
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563297"
---
# 添加、移动和删除 Microsoft Edge 的扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

**Windows 10 周年更新**中引入了 Microsoft Edge 扩展支持。 如果你正在开发 Microsoft Edge 扩展并且想要将其加载，或者你已有且现在想要删除它，请查看下面的步骤。
还包括有关如何在浏览器中更改扩展图标位置的详细信息。

## 添加扩展

1. 打开 "Microsoft Edge"，然后在地址栏中键入 "关于：标志"。

2. 选中 "**启用扩展开发人员功能**" 复选框。

   ![关于：标志打开开发人员功能](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > 如果您没有 Windows 10 周年更新或更高版本，此选项将不可用。

3. 选择 "**更多" （...）** 以打开菜单。

   !["更多" 按钮](./../media/morebutton.png)  

4. 从菜单中选择 "**扩展**"。

5. 选择 "**加载扩展**" 按钮。

   ![选择加载扩展](./../media/sideload-load-extension.png)

6. 导航到您的扩展的文件夹，然后选择 "**选择文件夹**" 按钮。
   ![选择要加载的扩展文件夹](./../media/sideload-select-extension.png)
   > [!NOTE]
   > 如果您在加载扩展时遇到错误消息，请参阅[疑难解答](./../troubleshooting.md)页面获取指南。


**一切就绪！ 现在，你应该可以看到 Microsoft Edge 的扩展窗格中列出的扩展。**

![扩展窗格中的扩展](./../media/sideload-extension-installed.png)

> [!NOTE]
> 在随后启动 Microsoft Edge 时，未签名的扩展将自动关闭。 当浏览器进入空闲状态时（大约10秒钟的非活动时间），你将在窗口底部看到以下通知。 ![危险通知 ](./../media/riskynotification.png) 若要打开未签名的扩展，请单击 "仍然启用"。



## 移动 "扩展" 按钮
根据扩展的设置，它可能会显示在 "**更多（...）** " 菜单中。

   ![操作菜单](./../media/browseraction.png)  


如果想要将按钮移出此菜单，以便更轻松地访问：

1. 右键单击 "扩展" 按钮。

2. 选择 "**地址栏" 旁边**的 "显示" 按钮。

   ![操作菜单](./../media/browseraction_contextmenu.png)  

或者，您也可以从 "扩展详细信息" 页面执行此操作：

1. 单击 "扩展" 按钮。
2. 将 "**地址栏" 旁边**的 "显示" 按钮切换到 "开"。

   ![显示按钮切换打开](./../media/show-button-toggle.png)

> [!NOTE]
> 您始终可以通过右键单击，然后转到 "**地址栏" 旁边**的 "取消选中"，或者转到 "扩展详细信息" 页面，并转到 "**地址栏" 旁边**的 "显示" 按钮，将按钮移回 "**更多（...）** " 菜单。


## 删除扩展

1. 打开 Microsoft Edge。

2. 选择 "**更多" （...）** 以打开菜单。

3. 从菜单中选择 "**扩展**"。

4. 右键单击要删除的扩展名，然后选择 "**删除**"，或选择该扩展名，然后单击 "**删除**" 按钮。

   ![操作菜单](./../media/remove.png)  

**该扩展将从 Microsoft Edge 中的列表中消失。**
