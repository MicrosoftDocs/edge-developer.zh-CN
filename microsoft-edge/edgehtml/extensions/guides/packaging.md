---
description: 了解如何打包扩展。
title: 扩展 - 打包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
keywords: edge， Web 开发， html， css， javascript， 开发人员
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62c7858c38cf0c06e24c25938a885b10b391fd8f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398495"
---
# <a name="packaging-microsoft-edge-extensions"></a>打包 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

因此，你已最终完成了扩展并已准备好打包它。 你可能想知道下一步将采取哪些措施来让潜在用户了解这一点。 本指南旨在指导你如何这样做。  

扩展打包指南是全面的，它涵盖了你想要了解的有关打包的一切内容，甚至更精细、最精细的详细信息。 如果不想了解打包扩展的一切信息，则很幸运的是。 我们添加了对 ManifoldJS 的扩展的支持，这是一种Node.js包工具，可省去大部分打包。  

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限功能。 [联系我们，](https://developer.microsoft.com/en-us/microsoft-edge/extensions/requests) 请求成为 Microsoft Store 的一部分，我们将考虑你进行将来的更新。  

使用下面的流程大纲来规划打包体验！  

## [<a name="extensions-in-the-windows-dev-center"></a>Windows 开发人员中心扩展](./packaging/extensions-in-the-windows-dev-center.md)  

无论你选择哪个程序包创建路由，手动或 ManifoldJS，第一步是注册 Windows 开发人员帐户，并保留扩展 () 的名称。  

完成此操作后，你可以继续创建和测试扩展包以了解如何创建[](./packaging/creating-and-testing-extension-packages.md)AppX 并手动打包扩展，或者转到更简单的路由并跳转到使用[ManifoldJS](./packaging/using-ManifoldJS-to-package-extensions.md)打包扩展。  

> [!NOTE]
> 一旦联系我们并获得批准，在 Microsoft Store 中拥有你的扩展，请查看 [应用提交清单](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。  


## [<a name="creating-and-testing-extension-packages"></a>创建和测试扩展包](./packaging/creating-and-testing-extension-packages.md)  

在设置 Windows 开发人员帐户并保留扩展名后，本指南的这一部分将指导你完成手动扩展 ([创建 ](./packaging/extensions-in-the-windows-Dev-Center.md)) 。 如果你对打包扩展的更精细的详细信息感兴趣，请对此进行阅读。  

此外，还包括有关如何测试和解压缩打包 [扩展的信息](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。 此信息是相关的，即使你已经过 ManifoldJS 打包路由。  

## [<a name="localizing-extension-packages"></a>本地化扩展包](./packaging/localizing-extension-packages.md)  

包本地化步骤介于创建appxmanifest.xml文件并运行最后一个命令打包扩展名之间。  
这允许你指示你的扩展在 Microsoft Store 一览中支持哪些语言，以及你的扩展名在 Windows 中显示的语言。  

如果你的扩展不支持多种语言，可以在本指南的本部分跳转到 [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 的本地化名称和说明。  

## [<a name="using-manifoldjs-to-package-extensions"></a>使用 ManifoldJS 打包扩展](./packaging/using-ManifoldJS-to-package-extensions.md)  

用于打包扩展的工具路由，ManifoldJS 会以最少的工作量快速打包扩展。 填写一些 AppXManifest 属性后，提供一些 Windows/Microsoft Store 资产，并且你的扩展将无需任何时间打包。  

打包扩展后，请参阅创建和测试[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)Microsoft Edge 扩展的测试部分，了解如何旁加载或解压缩它。  

## [<a name="running-the-windows-app-certification-kit"></a>运行 Windows 应用认证工具包](./packaging/running-the-windows-app-certification-kit.md)  

拥有打包的扩展后，可以通过 Windows 应用认证工具包运行它。 这样做将在扩展包上运行大量测试，以确保它已准备好使用 Microsoft Store。  
