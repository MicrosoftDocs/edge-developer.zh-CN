---
description: 了解有关 Microsoft Edge 扩展的一些便捷提示和技巧
title: 扩展-提示和技巧
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: db15aa49649432a6c4400b4e6830501c40485a83
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563226"
---
# 提示和技巧  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

无论您当前正在处理的是 Microsoft Edge 扩展还是已经发布过，以下提示和技巧都可能会很方便。

## 在 Microsoft Store 中获取指向您的扩展的直接链接
在 Windows 开发人员中心仪表板中，你可以在 Microsoft Store 中找到指向你的扩展的直接链接。 此链接对于广告和分享您的分机很有用。


登录到 Windows 开发人员中心并通过仪表板导航到您的扩展后，在 "应用标识" 页面上，您将在 "应用程序标识" 页面上找到 "应用 **商店协议" 链接** 行的链接：

![存储协议链接](./media/store-link.png)
 
## 请确保你关注的是 Microsoft Store 策略
创建扩展时，请务必记住提交到 microsoft [Store 策略](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)中突出显示的 microsoft store 的指南。 
 
Microsoft Edge 扩展还包含一组要[关注的其他策略。](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)

## 改善扩展在 Microsoft Store 中的可发现性

你可以将关键字添加到你的扩展提交，以通过搜索 imporove 它的发现。 例如，"Microsoft Edge 扩展" 和 "我的扩展名的名称"。 

可以在 Windows 开发人员中心中的扩展的 "说明" 部分下执行此操作。 对于扩展支持的每种语言，都需要添加这些关键字。

![提交对审阅的答复](./media/keywords.png)

## 自动提交到 Microsoft Store
你可以使用新的 Microsoft Store 提交 API 自动化和优化 Microsoft Store 的提交，该 API 允许你更新应用/游戏、加载项 (应用内购买) 以及通过 REST API 包装航班。 查看 [文档和示例](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) ，或使用 "打开源 [提交 API VSTS 扩展](https://github.com/Microsoft/windows-dev-center-vsts-extension) " 开始。

## 使用 Windows 反馈中心收集反馈/评论/功能请求

你可以通过嵌入指向扩展的链接来将用户定向到你的扩展的 Windows 反馈中心子类别。 此链接将需要使用以下格式创建： 

`feedback-hub://?tabid=2&appid=<PFN>!App`

你需要替换 `<PFN>` 为你的扩展的程序包系列名称。 这可以在 Windows 开发人员中心中的扩展的 **应用标识** 部分下找到。

## 查看您的评级和评论
定期登录，检查您的用户评论和评价。 虽然 UWP 应用只有当前用户市场的信息，但登录到 Windows 开发人员中心的信息将显示所有市场的平均分级。

## 响应用户评论
你可以通过 Windows 开发人员中心的仪表板来响应 Microsoft Store 中的用户评论。 导航到您的扩展，并在 "分析" 下选择 " **评论**"。 每个评论下将显示一个链接，允许您直接答复客户。 此通信渠道使你能够提供反馈、解决方法或向你发送一则感谢你的评论！

![提交对审阅的答复](./media/reviews.png)
