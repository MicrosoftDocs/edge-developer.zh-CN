---
description: 获取开始开发到 Microsoft Edge 扩展的包装的端到端概述。
title: 扩展-入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 5d2bf0ea2236e36b9e6205e13291ffee4118d9d7
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563316"
---
# 扩展入门  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

无论你是想要熟悉扩展的新开发人员，还是想要使用 Chrome 扩展的经验丰富的退伍军人，本指南包含开发、测试、打包和发布 Microsoft Edge 扩展所需的所有信息。 

## 开发扩展

这种旅程的第一步是创建 Microsoft Edge 扩展： 
- 新的分机号？ 有关如何创建你的第一个浏览器扩展的信息，请查看我们的[指南](./guides/creating-an-extension.md)。 
- 已熟悉扩展 Api？ 请查看我们的[api 支持文档](./api-support.md)，获取有关哪些 api 受支持/在开发中的最新信息。 
- 具有你想要移植到 Microsoft Edge 的 Chrome 扩展？ 尝试[Microsoft Edge 扩展工具包](./guides/porting-chrome-extensions.md)！

## 加载和调试

当你拥有在 Microsoft Edge 中正常工作的扩展后，你需要将其加载才能查看它的操作。 执行此操作的第一步是确保已[启用扩展开发人员功能](./guides/adding-and-removing-extensions.md)。 这将允许你在 Microsoft Edge 中加载扩展文件，以便你可以在开发时测试扩展。 如果遇到任何问题，则 F12 开发人员工具允许你[调试扩展的各种上下文](./guides/debugging-extensions.md)，以准确确定正在进行的操作。 仍遇到问题？ 我们的[疑难解答指南](./troubleshooting.md)具有几个常见问题的解决方案。 

## 报告 bug 和获取帮助

认为你在我们的扩展平台中发现了 bug？ 如果问题特定于 Microsoft Edge，请在[Microsoft Edge 问题跟踪](https://developer.microsoft.com/microsoft-edge/platform/issues/)器上搜索它以查看是否已报告。 如果有，很好！ 你可以按 "+ Me/Me" 按钮来投赞成票 bug 和 "请注意更新问题" 按钮，以便收到有关该问题的任何更改的通知。 如果你找不到正在使用的问题，请随时打开新问题并提供尽可能多的信息，以便我们的开发人员可以查看它。 

我们是否缺少你的扩展需要正常工作的 API？ 如果是这样，[我们将始终倾听 UserVoice](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/87962-extensions)。 如果你的 API 已存在，可以免费投赞成票，或者创建新的反馈项目，以便其他开发人员也可以投赞成票它！ 

您是否有问题无法在文档中找到答案？ 我们强烈建议你在堆栈溢出时加入[Microsoft Edge 扩展社区](https://stackoverflow.com/questions/tagged/microsoft-edge-extension)，并向其提问！

## 测试扩展

在 Windows 周年更新中， [Microsoft WebDriver](../dev-guide/tools/webdriver.md)支持在 microsoft Edge 会话中自动加载扩展。 这将允许你编写简单的测试，以确保用于修改页面的任何扩展按预期的方式进行。 您可以在我们的[测试指南](./guides/packaging/creating-and-testing-extension-packages.md#automated-testing-with-webdriver)中找到有关如何执行此操作的详细信息。 此外，我们计划在将来向 Microsoft WebDriver 添加更多扩展特定功能时，请随时关注更新。

## 添加最终接触

因此，你的分机在 Microsoft Edge 中工作。 接下来会发生什么？ 在继续打包你的扩展之前，强烈建议你查看这些指南，以确保你的扩展遵循最佳做法策略： 
- 确保你的扩展图标[大小正确](./guides/design.md)且[易于访问](./guides/accessibility.md)（这意味着它们在 Microsoft Edge 的浅色和深色主题中以及在高对比度模式下可见）。 
- 如果您的扩展需要支持多种语言，请确保您了解我们的[国际化指南](./guides/internationalization.md)。 

## 包装扩展

现在，你的扩展已是 "精美"，可随时打包。 无论您是希望将它打包以准备提交到 Microsoft Store，还是要使其更易于在开发/测试团队中分发，还提供了大量资源来帮助您： 

- 我们推荐的创建扩展程序包的解决方案是遵循我们的[ManifoldJS 打包指南](./guides/packaging/using-manifoldjs-to-package-extensions.md)，该指南将指导你完成使用基于 node.js 的工具的步骤，无论你开发什么平台，都可以轻松地打包你的扩展。 如果您希望更深入、更深入地了解我们的扩展打包格式，请参阅我们的[AppX 程序包创建指南](./guides/packaging/creating-and-testing-extension-packages.md#preparing-the-submission-folder)。 
- 如果你的扩展支持多种语言，你还需要关注我们对[扩展程序包进行本地化](./guides/packaging/localizing-extension-packages.md)的指南，以便在打包后正确注册你的扩展中的语言。 

如果你是企业客户，希望通过内部频道分发打包的扩展，请参阅我们[的企业版扩展指南](./extensions-for-enterprise.md)以了解如何执行此操作。  

## 发布到 Microsoft Store

由于我们的扩展平台仍在 infancy 中，因此我们有意管理向 Microsoft Store 提交的扩展，以便我们可以专注于为我们的用户和开发人员提供优质体验。 也就是说，我们希望让开发人员尽可能轻松地发布其扩展。 因此，我们最近启动了一个新的 "[扩展提交" 表单](https://aka.ms/extension-request)，开发人员可在其中请求向 Microsoft Store 提交其扩展 AppX 的权限。
 

发布过程的第一步是确保你的扩展符合我们的[浏览器扩展策略](./microsoft-browser-extension-policy.md)以及[microsoft Store 策略的 microsoft Edge 扩展部分](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。 

一旦您确认您的扩展遵循这些政策，您将需要[在合作伙伴中心注册一个开发者帐户，并保留您的扩展的名称](./guides/packaging/extensions-in-the-windows-dev-center.md)。 然后，你需要通过我们的 "[扩展提交" 表单](https://aka.ms/extension-request)提交请求，以便请求发布到 Microsoft Store 的权限。 如果您尝试在没有事先获得权限的情况下提交扩展 AppX，您将收到以下错误：

`Package acceptance validation error: com.microsoft.edge.extension is a reserved extension type. Your app does not have permission to use this extension type.`

提交请求后，我们将收到一则通知，并尝试尽快获取你的提交。 这可能需要一些时间，因为我们收到的提交量很大，但我们会通过电子邮件通知您，您已获得批准！ 收到邮件后，您将能够通过合作伙伴中心将扩展版 AppX 提交到 Microsoft Store。 请注意，在提交之前无需签名您的 AppX;Microsoft Store 摄取过程将负责你的参与！
 
> [!NOTE]
> 将扩展发布到 Microsoft Store （无论是全新的扩展还是对现有的更新）的过程最多可能需要72小时才能完成。 为了加速此过程，请确保在提交之前验证这些常见的陷阱，以避免稍后重新提交： 
> - 你的屏幕截图大小正确，并且你的扩展在 Microsoft Edge 中运行 
> - 扩展说明引用了 "Microsoft Edge"，而不是 "Edge" （这是法律要求） 
> - 扩展程序包中的150x150 图标没有[透明背景](./guides/design.md#microsoft-store-icon)（Microsoft Store 客户端不能使用透明背景正确呈现图像） 

除了上述情况外，如果适用，请确保你的网站上的任何平台可用性信息均正确提及你的扩展在 Microsoft Edge 上的可用性。 虽然 Microsoft Store 不允许同时单击 "内联扩展" 安装，但你可以[在 Microsoft store 中深入链接到你的扩展](./tips-and-tricks.md#get-a-direct-link-to-your-extension-in-the-microsoft-store)，以便用户可以轻松获取它。 

Microsoft Store 还允许你[控制你的扩展](https://blogs.windows.com/buildingapps/2015/09/10/managing-hidden-apps-beta-apps-and-visibility-of-in-app-purchases-in-dev-center/)在 Microsoft Store 目录中的可见性。 我们的一些合作伙伴利用此功能来实现以下目的： 
- 在 Microsoft Store 中发布其扩展名的第二个 beta 版本。
- 最初将其扩展名发布为 "隐藏" 以监控初始遥测，然后再将其状态更改为 "在达到一定程度的置信度后立即显示"。

## 就这么简单！

如果你已达到本指南的底部，则说明你已完成为 Microsoft Edge 开发扩展的过程！ 请务必查看我们的[提示和诀窍](./tips-and-tricks.md)页面，了解如何向你的分机推销和与你的用户进行交互的建议。
