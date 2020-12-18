---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: 了解如何打包扩展。
title: 扩展 - 打包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ea4d6a4450d47d116164fd8481fdfb0f79bd30b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232616"
---
# 打包 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

因此，你已最终完成了扩展并已准备好打包它。 你可能想知道下一步将执行哪些操作，以将此方法掌握在潜在用户之手。 本指南旨在指导你如何这样做。

扩展打包指南是全面的，它涵盖了你想要了解的有关打包的一切内容，甚至是更精细、最精细的详细信息。 如果你不希望了解打包扩展的一切信息，则你一去不及事。 我们对 ManifoldJS 增加了对扩展的支持，ManifoldJS 是一种Node.js打包工具，可省去大部分打包。

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。 [如果你的请求是](https://aka.ms/extension-request) Microsoft Store 的一部分，请联系我们，我们将考虑你进行将来的更新。


使用下面的流程大纲来规划打包之旅！


## [Windows 开发人员中心扩展](./packaging/extensions-in-the-windows-dev-center.md)

无论你选择哪个程序包创建路由，手动还是 ManifoldJS，第一步是注册 Windows 开发人员帐户，并保留扩展 () 的名称。

完成此操作后，你可以继续创建和测试扩展包以了解如何创建[](./packaging/creating-and-testing-extension-packages.md)AppX 并手动打包扩展，或者转到更简单的路由并跳转到使用[ManifoldJS](./packaging/using-ManifoldJS-to-package-extensions.md)打包扩展。

> [!NOTE]
> Once you've reached to us and have been approved to have your extension in the Microsoft Store， check out the [app submission checklist.](https://docs.microsoft.com/windows/uwp/publish/app-submissions)


## [创建和测试扩展包](./packaging/creating-and-testing-extension-packages.md)

在设置 [Windows ](./packaging/extensions-in-the-windows-Dev-Center.md)开发人员帐户并保留扩展名后，本指南的这一部分将指导你完成手动扩展 (创建) 。 如果你对打包扩展的更详细细节感兴趣，请对此进行阅读。

还包括有关如何测试和解压缩打包 [扩展的信息](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。 此信息是相关的，即使你已经过 ManifoldJS 打包路由。

## [本地化扩展包](./packaging/localizing-extension-packages.md)
包本地化步骤包括创建appxmanifest.xml文件并运行最后一个命令打包扩展。
这允许你指示你的扩展在 Microsoft Store 一览中支持哪些语言，以及你的扩展名在 Windows 中显示的语言。

如果你的扩展不支持多种语言，可以跳转到本指南本部分中 [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 的本地化名称和说明。

## [使用 ManifoldJS 打包扩展](./packaging/using-ManifoldJS-to-package-extensions.md)

用于打包扩展的工具路由，ManifoldJS 会以最少的工作量将扩展打包在一起。 填写完一些 AppXManifest 属性后，提供一些 Windows/Microsoft Store 资产，你的扩展将无需任何时间打包。

打包扩展后，请参阅"创建和测试[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)Microsoft Edge 扩展"的测试部分，了解如何旁加载或解压缩它。


## [运行 Windows 应用认证工具包](./packaging/running-the-windows-app-certification-kit.md)

拥有打包的扩展后，可以通过 Windows 应用认证工具包运行它。 这样做将在扩展程序包上运行大量测试，以确保它已准备好用于 Microsoft Store。
