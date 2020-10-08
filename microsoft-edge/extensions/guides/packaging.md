---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: 了解如何使用本机消息功能让你的分机与配套的 UWP 应用进行通信。
title: 扩展-打包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 23c97f366db527cae2672d6ad46fa666583f6398
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563258"
---
# 打包 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

您最终已经完成了您的扩展，并准备好将其打包。 您可能会想知道，在潜在用户的手中，接下来的步骤是如何实现的。 本指南旨在教您如何操作。

扩展打包指南非常全面，它涵盖了你希望了解的有关打包的所有内容，甚至是更精细的详细信息。 如果您不想了解有关打包您的扩展的任何信息，您就会很幸运。 我们添加了对 ManifoldJS 的扩展的支持，这是一个开放的源 Node.js 工具，可充分利用大部分包装 woes。

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。 [通过你](https://aka.ms/extension-request) 的请求成为 Microsoft Store 的一部分，我们将考虑你的未来更新。


使用下面的流程大纲来确定您的包装艾德公司！


## [Windows 开发人员中心扩展](./packaging/extensions-in-the-windows-dev-center.md)

无论你选择哪种程序包创建路由，手动或 ManifoldJS，第一步是注册一个 Windows 开发者帐户并保留你的扩展 (s) 的名称。

完成此操作后，你可以继续 [创建和测试扩展程序包](./packaging/creating-and-testing-extension-packages.md) ，了解如何创建 AppXs 以及如何手动打包你的扩展，或者转到更简单的路由并跳转到 [使用 ManifoldJS 打包扩展](./packaging/using-ManifoldJS-to-package-extensions.md)。

> [!NOTE]
> 一旦您达到我们的，并且已被批准在 Microsoft Store 中拥有您的分机号，请查看 [应用提交核对清单](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。


## [创建和测试扩展包](./packaging/creating-and-testing-extension-packages.md)

本指南的此部分将在设置你的 [Windows 开发人员帐户并保留你的分机名称 (s) ](./packaging/extensions-in-the-windows-Dev-Center.md)的情况下，手动创建程序包。 如果您想了解包装扩展的详细信息，请阅读。

还包括有关如何 [测试和解压缩打包的扩展的](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)信息。 即使您已经有了 ManifoldJS 包装路线，此信息仍是相关的。

## [本地化扩展包](./packaging/localizing-extension-packages.md)
程序包本地化步骤介于创建你的 appxmanifest.xml 文件并运行最终命令来打包你的扩展。
这使你可以在 Microsoft Store 中指明你的扩展支持哪些语言，以及你的扩展名称显示在 Windows 中的语言。

如果您的扩展不支持多种语言，您可以跳转到本指南本部分中的 [Microsoft Store 的名称和说明](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 。

## [使用 ManifoldJS 打包扩展](./packaging/using-ManifoldJS-to-package-extensions.md)

ManifoldJS 的工具路线用于包装你的扩展，将在你的快速入门中打包你的扩展，最大努力完成。 填写某些 Package.appxmanifest 属性后，提供一些 Windows/Microsoft Store 资产，并且将不会打包你的扩展。

打包扩展后，请参阅创建和测试 Microsoft Edge 扩展的 " [测试](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) " 部分，了解如何旁加载或解包。


## [运行 Windows 应用认证工具包](./packaging/running-the-windows-app-certification-kit.md)

拥有打包的扩展后，即可通过 Windows 应用认证工具包运行它。 这样做将在扩展程序包上运行大量测试，以确保它可以用于 Microsoft Store。
