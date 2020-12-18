---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: 了解 Microsoft Edge 扩展的企业特定方面，并查看它们如何与 UWP 应用类似。
title: 适用于企业的扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7c23bc24e20b7b00b8779f209dcac8c795067fd5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232715"
---
# 企业扩展  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

与其他企业 UWP 应用相比，Microsoft Edge 扩展具有类似的工作流。 以下信息详细介绍了 Microsoft Edge 扩展的企业特定方面。

## 必备条件
建议开发、打包和部署适用于企业的 Microsoft Edge 扩展项：

+ Windows 开发人员门户帐户，用于对企业专用应用商店的扩展进行签名和发布。 有关 [更多详细信息，请参阅"](/windows/uwp/publish/opening-a-developer-account) 打开开发人员帐户"。
+ 适用于企业或教育的 Microsoft Store，将应用程序分发到企业。 有关更多详细信息 [，请参阅适用于企业和教育的 Microsoft](/microsoft-store/) Store 文档。
+ 确定哪些版本的 Windows 10 将运行 Microsoft Edge 扩展。 有关 [现有 Windows 10](https://www.microsoft.com/itpro/windows-10/release-information) 版本列表，请参阅 Windows 10 版本信息。

> [!NOTE]
> 旁加载可以视为使用 Windows 开发人员门户对扩展版本进行签名的替代方法。 有关详细信息，请参阅以下旁加载扩展的行为。

## Windows 信息保护
Microsoft Edge 扩展当前不沿用 Windows 信息保护 (WIP) 设置。 如果企业关注数据保护，则不应为 Microsoft Edge 启用扩展支持。

若要禁用员工的扩展，请配置组策略和 Microsoft Intune 设置。 有关要配置的策略详细信息，请参阅 Microsoft [Edge 的可用策略](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)。

## 打包扩展
在企业可以将扩展分发给其员工之前，必须先将其打包。 有关打包扩展的说明，请参阅"打包指南["。](./guides/packaging.md)

> [!TIP]
> 请确保在所有版本的 Windows 10 上测试安装并运行扩展，以确保在分发之前它按预期工作。

## 分发扩展
扩展打包后，可以通过 Microsoft Store、适用于 Business 的 Microsoft Store 或旁加载将扩展分发给员工。

通过适用于企业 Microsoft Store 分发的扩展可以分配给员工，也可以添加到所有员工都可以访问的专用应用商店。 这可以通过遵循 LOB 应用"业务线" (LOB) [指南](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) 完成。

若要旁加载扩展， (托管或托管) 必须解锁才能旁加载。 请参阅 [Windows 10 中的](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) 旁加载 LOB 应用，详细了解如何旁加载打包的扩展。

> [!IMPORTANT]
> 如果企业同时在内部开发并分发扩展，则企业将需要适用于企业的 Microsoft Store (或教育) Windows 开发人员门户帐户。

### 旁加载扩展的行为
与通过 Microsoft Store (或适用于企业) 分发的扩展不同，旁加载的扩展在 Microsoft Edge 中的处理方式不同。

第一个差异会影响旁加载扩展在安装后的行为方式。 与 Microsoft Store 中的扩展不同，旁加载的扩展不会立即显示"你有新的扩展"通知，并且需要由用户手动打开。

若要打开扩展，请打开"更多** (...) **菜单，选择"扩展"，你应该会看到已安装**** 扩展列表中的旁加载扩展。 单击扩展并打开它。

第二个差异影响旁加载的扩展在浏览器中的显示方式。 例如，"你有新的扩展"通知和已安装的扩展的列表都包括一条附加警告，指出该扩展来自未知源。

![旁加载警告 1](./media/sideload-permissionflyout.PNG)

![旁加载警告 2](./media/sideload-l1warning.PNG)

第三个和最后一个差异会影响旁加载扩展在浏览器启动时的行为方式。 在已加入域或启用了 MDM 的设备上旁加载的扩展的行为将类似于 Microsoft Store 中的扩展。 但是，未加入域或启用了 MDM 的设备上旁加载的扩展将在浏览器启动期间关闭，并需要用户执行显式操作。

浏览器启动后 (在大约 10 秒的不活动状态) 下面的通知将显示在窗口底部附近。

![旁加载通知](./media/sideload-scareUI.PNG)

每次启动 Microsoft Edge 时，用户都需要选择"继续启用"才能使用扩展。
