---
description: 了解有关 Microsoft Edge 扩展的一些方便提示和技巧
title: 提示和技巧 |扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 扩展
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cd512085f13b76c5a8e474301ef296612eeb0414
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232244"
---
# 提示和技巧  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

无论你当前是使用 Microsoft Edge 扩展还是已经发布了一个，以下提示和技巧都很方便。

## 在 Microsoft Store 中获取指向扩展的直接链接

在 Windows 开发人员中心仪表板中，可以在 Microsoft Store 中查找指向扩展的直接链接。 此链接可用于广告和共享扩展。

登录到 Windows 开发人员中心并通过仪表板导航到扩展后，在应用标识页面上，你将在应用商店协议链接行 **中** 找到链接：

![存储协议链接](./media/store-link.png)
 
## 确保你遵循 Microsoft Store 策略

创建扩展时，请务必记住提交到 Microsoft Store 的指南，该准则在 Microsoft Store 策略 [中突出显示](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)。 
 
Microsoft Edge 扩展还有一组要遵循的其他策略，在此处 [可以看到](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。

## 提高扩展在 Microsoft Store 中的可发现性

你可以向扩展提交添加关键字，以通过搜索提高其可发现性。 例如，"Microsoft Edge Extensions"和"name of my extension"。 

这可以在 Windows 开发人员中心中的扩展说明部分下完成。 需要为扩展支持的每种语言添加这些关键字。

![提交评价回复 - 关键字](./media/keywords.png)

## 自动提交到 Microsoft Store

通过使用新的 Microsoft Store 提交 API，你可以自动完成并简化提交到 Microsoft Store，这允许你更新应用/游戏、加载项 (应用内购买) ，并通过 REST API 打包测试版本。 请查看文档 [和示例或使用](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) 开放源代码提交 API [VSTS 扩展](https://github.com/Microsoft/windows-dev-center-vsts-extension) 开始使用。

## 使用 Windows 反馈中心收集反馈/评论/功能请求

通过嵌入指向扩展的链接，你可以将用户引导到扩展的 Windows 反馈中心子类别。 需要按照以下格式创建此链接： 

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

你将需要替换为 `<PFN>` 扩展的程序包系列名称。 这可以在 Windows 开发人员中心内 **扩展的应用标识** 部分下找到。

## 查看你的评分和评论

定期登录以检查用户评论和评级。 尽管 UWP 应用将仅包含当前用户市场的信息，但登录到 Windows 开发人员中心将显示所有市场的平均评分。

## 回复用户评论

可以通过 Windows 开发人员中心仪表板回复 Microsoft Store 中的用户评论。 导航到扩展，并在"分析"下选择 **"评价"。** 每个评论下方都会显示一个链接，可让你直接回复客户。 通过此通信渠道，你可以提供反馈、解决方案或发送对评价的感谢！

![提交评价回复](./media/reviews.png)
