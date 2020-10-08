---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: 了解 Microsoft Edge 扩展的企业特定方面，并了解它们与 UWP 应用的相似之处。
title: 适用于企业的扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 8f50c282fce11d2654f990bf135941e0616af3f3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563320"
---
# 企业版扩展  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

与其他企业的 UWP 应用比较时，Microsoft Edge 扩展具有类似的工作流。 下面的信息详细介绍了 Microsoft Edge 扩展的企业特定方面。

## 必备条件
建议使用以下项目为企业版开发、打包和部署 Microsoft Edge 扩展：

+ Windows 开发人员门户帐户，用于对企业专用存储进行签名和释放扩展。 有关详细信息，请参阅 [打开开发人员帐户](/windows/uwp/publish/opening-a-developer-account) 。
+ Microsoft Store for Business 或教育版，用于将应用程序分发到企业。 有关详细信息，请参阅 [Microsoft Store For Business 和教育文档](/microsoft-store/) 。
+ 确定将运行 Microsoft Edge 扩展的 Windows 10 版本。 有关现有 Windows 10 版本的列表，请参阅 [Windows 10 发布信息](https://www.microsoft.com/itpro/windows-10/release-information) 。

> [!NOTE]
> 可将旁显示为使用 Windows 开发人员门户对扩展发布进行签名的替代方法。 有关详细信息，请参阅下面的旁加载扩展行为。

## Windows 信息保护
Microsoft Edge 扩展目前不授予 Windows 信息保护 (WIP) 设置。 如果企业担心数据保护，则不应为 Microsoft Edge 启用扩展支持。

若要禁用员工的扩展，请配置组策略和 Microsoft Intune 设置。 有关要配置的策略的详细信息，请参阅 [Microsoft Edge 的可用策略](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)。

## 包装扩展
在企业可以向其员工分发扩展之前，必须先将其打包。 有关包装扩展的说明，请访问 [打包](./guides/packaging.md) 指南。

> [!TIP]
> 请务必在 Windows 10 的所有版本上测试安装和运行扩展，以确保它在分发之前将按预期工作。

## 分发扩展
扩展已打包后，可以通过 Microsoft Store、Microsoft Store for Business 或通过旁加载将其分发给员工。

分配了 Microsoft Store for Business 的扩展可分配给员工，或添加到所有员工均可访问的私人存储中。 可通过以下方式完成此操作：使用 ["分布于企业的业务线" (LOB) 应用程序](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) 指南 "。

若要旁加载扩展，必须解除 (非托管或托管) 的设备的旁加载。 有关如何旁加载打包的扩展的详细信息，请参阅 [Windows 10 中的旁加载 LOB 应用](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) 。

> [!IMPORTANT]
> 如果企业在内部开发和分发扩展，企业将需要 Microsoft Store for Business (或教育) 和 Windows 开发人员门户帐户。

### 旁加载扩展的行为
与通过 Microsoft Store 分发的扩展不同 (或 Microsoft Store for Business) ，在 Microsoft Edge 中，将以不同的方式处理旁加载扩展。

第一个区别影响安装后旁加载扩展的行为方式。 与 Microsoft Store 中的扩展不同，旁加载扩展不会立即显示 "你有新的扩展名" 通知，并且需要由用户手动打开。

若要打开扩展，请打开 " **更多 ( ..." ) ** 菜单，选择 **"扩展"** ，你应在已安装的扩展列表中看到旁加载扩展。 单击 "扩展"，然后将其打开。

第二个差异影响旁加载扩展在浏览器中的显示方式。 例如，"你有新的扩展名" 通知和已安装的扩展列表中包含一条附加警告，指出扩展来自未知源。

![旁加载警告1](./media/sideload-permissionflyout.PNG)

![旁加载警告2](./media/sideload-l1warning.PNG)

第三种和最终区别影响旁加载扩展在浏览器启动时的行为方式。 在已加入域或启用 MDM 的设备上的旁加载扩展将类似于 Microsoft Store 中的扩展。 但是，在浏览器启动过程中，将关闭未加入域或启用 MDM 的设备上的旁加载扩展，并要求用户执行显式操作。

浏览器启动后不久，将在大约10秒的不活动之后 () 将在窗口底部附近显示以下通知。

![旁加载通知](./media/sideload-scareUI.PNG)

每次启动 Microsoft Edge 时，用户都需要选择 "仍启用"，以便使用该扩展名。
