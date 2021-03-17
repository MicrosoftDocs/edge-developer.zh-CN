---
description: 获取从开始开发到打包 Microsoft Edge 扩展的旅程的端到端概述。
title: 扩展 - 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 扩展
ms.date: 03/16/2021
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 52d0aa5c1968518194a4e3b90cb0cc876d0c7f86
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439715"
---
# <a name="getting-started-with-extensions"></a>扩展入门  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

无论你是想要熟悉扩展的新开发人员还是想要移植的 Chrome 扩展的经验丰富的经验丰富的开发人员，本指南都包含开发、测试、打包和发布 Microsoft Edge 扩展所需的全部信息。 

## <a name="developing-an-extension"></a>开发扩展

此旅程的第一步是创建 Microsoft Edge 扩展： 
- 是扩展的新增功能？ 请查看我们的 [指南，了解如何创建扩展](./guides/creating-an-extension.md) ，了解如何生成首个浏览器扩展！ 
- 已熟悉扩展 API？ 请查看我们的 [API 支持](./api-support.md) 文档，了解有关哪些 API 在开发中受支持的最新信息。 
- 是否具有要移植到 Microsoft Edge 的 Chrome 扩展？ 尝试[Microsoft Edge 扩展Toolkit！](./guides/porting-chrome-extensions.md)

## <a name="loading-and-debugging"></a>加载和调试

一旦拥有在 Microsoft Edge 中工作的扩展，你将希望旁加载它以查看其是否有效。 这样做的第一步是确保您已启用扩展 [开发人员功能](./guides/adding-and-removing-extensions.md)。 这将允许你在 Microsoft Edge 中旁加载扩展文件，以便可以在开发扩展时测试扩展。 如果遇到任何问题，F12 开发人员工具将允许你调试扩展的各种上下文[](./guides/debugging-extensions.md)，以确定具体情况。 是否仍有问题？ 我们的 [疑难解答指南](./troubleshooting.md) 提供了针对多个常见链的解决方案。 

## <a name="reporting-bugs-and-getting-help"></a>报告 Bug 并获取帮助

你认为你在我们的扩展平台中发现了 Bug？ 如果问题特定于 Microsoft Edge，请在 [Microsoft Edge](https://developer.microsoft.com/microsoft-edge/platform/issues/) 问题跟踪器上搜索该问题，以查看是否已被报告。 如果有，太好了！ 也可以按"+ 我"按钮对 Bug 进行启动，并按"监视此问题以更新"按钮，以针对问题的任何更改发出警报。 如果找不到正运行的问题，请随时打开新问题并提供尽可能多的信息，以便我们的开发人员可以调查它。 

<!--Are we missing an API that your extension needs to work properly? If so, [we're always listening on UserVoice](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/87962-extensions). Feel free to upvote your API if it already exists, or to create a new feedback item so that other developers can upvote it too! -->  

您是否有在文档中找不到答案的问题？ 我们强烈建议你加入 Stack Overflow 上的 [Microsoft Edge 扩展](https://stackoverflow.com/questions/tagged/microsoft-edge-extension) 社区，然后在那里询问！

## <a name="testing-your-extension"></a>测试扩展

自 Windows 周年更新起 [，Microsoft WebDriver](../webdriver/index.md) 支持在 Microsoft Edge 会话中自动旁加载扩展。 这将允许你编写简单的测试，以确保任何旨在修改页面的扩展都按预期方式完成此操作。 可以在我们的测试指南中查找有关操作 [方法详细信息](./guides/packaging/creating-and-testing-extension-packages.md#automated-testing-with-webdriver)。 此外，请继续关注更新，因为我们计划将来向 Microsoft WebDriver 添加更多特定于扩展的功能。

## <a name="adding-the-final-touches"></a>添加最终接触

因此扩展在 Microsoft Edge 中运行。 接下来会发生什么？ 在继续打包扩展之前，强烈建议你查看这些指南，以确保你的扩展遵循我们的最佳实践策略： 
- 请确保扩展图标的大小正确且[](./guides/design.md)易于[访问 (这意味着](./guides/accessibility.md)它们在 Microsoft Edge 的浅色和深色主题以及高对比度模式下均可) 。 
- 如果你的扩展需要支持多种语言，请确保你已查看我们的 [国际化指南](./guides/internationalization.md)。 

## <a name="packaging-an-extension"></a>打包扩展

现在，你的扩展已最终得到完善并准备打包。 无论是想要打包它以准备提交到 Microsoft Store，还是为了便于在开发/测试团队中分发，都有许多资源可以帮助你： 

- 我们建议的创建扩展包的解决方案是按照 [ManifoldJS](./guides/packaging/using-manifoldjs-to-package-extensions.md) 打包指南操作，该指南将指导你完成使用基于 Node.js 的工具的步骤，无论开发哪个平台，都可以轻松地打包扩展。 如果你想要更手动和深入地查看我们的扩展打包格式，请参阅 [我们的 AppX 程序包创建指南](./guides/packaging/creating-and-testing-extension-packages.md#preparing-the-submission-folder)。 
- 如果你的扩展支持多种语言，你还需要遵循我们的本地化扩展包指南，以便打包[](./guides/packaging/localizing-extension-packages.md)后正确注册扩展中拥有的语言。 

如果你是希望通过内部渠道分发打包扩展的企业客户，请参阅我们的企业扩展指南，了解如何实现此目标。 [](./extensions-for-enterprise.md)  

## <a name="publishing-to-the-microsoft-store"></a>发布到 Microsoft Store

由于我们的扩展平台仍处于发展阶段，我们故意管理向 Microsoft Store 提交的扩展，以便我们可以专注于为用户和开发人员提供优质体验。 也就是说，我们希望让开发人员尽可能轻松地发布其扩展。 因此，我们最近推出了新的扩展提交表单，[](https://aka.ms/extension-request)开发人员可在其中请求将扩展 AppX 提交到 Microsoft Store 的权限。
 
发布过程的第一步是确保你的扩展符合我们的浏览器扩展策略以及 Microsoft **** Store 策略的 Microsoft [Edge 扩展部分](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。  

<!--  The first step of the publishing process is to make sure your extension conforms to our [browser extension policy](./microsoft-browser-extension-policy.md) as well as the [Microsoft Edge extensions section of the Microsoft Store Policies](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).  -->  

确认扩展遵循策略后，你需要在合作伙伴中心注册开发人员帐户并 [保留扩展的名称](./guides/packaging/extensions-in-the-windows-dev-center.md)。 然后，你将需要通过扩展提交表单提交 [请求，以](https://aka.ms/extension-request) 请求发布到 Microsoft Store 的权限。 如果尝试在未先获得权限的情况下提交扩展 AppX，将收到以下错误：

```text
Package acceptance validation error: com.microsoft.edge.extension is a reserved extension type. Your app does not have permission to use this extension type.
```  

提交请求后，我们将收到通知，并尝试尽快提交。 这可能需要一些时间，因为我们已收到大量提交，但我们将在你获得批准时通过电子邮件通知你！ 收到邮件后，你将能够通过合作伙伴中心将扩展 AppX 提交到 Microsoft Store。 请注意，在提交 AppX 之前，不需要对 AppX 进行签名;Microsoft Store 的提供过程将负责这一点！
 
> [!NOTE]
> 将扩展发布到 Microsoft Store 的过程 (无论是全新的扩展，还是现有扩展的更新) 可能需要 72 个小时才能完成。 为了加快此过程，请确保在提交之前已验证这些常见链，以避免以后重新提交： 
> - 你的屏幕截图大小正确，并且你的扩展在 Microsoft Edge 中运行 
> - 你的扩展说明引用"Microsoft Edge"而不是 ("Edge"，这是一项法律要求)  
> - 扩展包中的 150x150 图标没有透明 [背景 (](./guides/design.md#microsoft-store-icon) Microsoft Store 客户端无法正确呈现具有透明背景的图像)  

除上述内容外，如果适用，请确保网站上的任何平台可用性信息正确提及了扩展在 Microsoft Edge 上的可用性。 虽然 Microsoft Store 不允许一键式内嵌扩展安装，但你可以深层链接到 [Microsoft Store](./tips-and-tricks.md#get-a-direct-link-to-your-extension-in-the-microsoft-store) 中的扩展，以便用户可以轻松获取它。 

Microsoft Store 还允许你 [控制](https://blogs.windows.com/buildingapps/2015/09/10/managing-hidden-apps-beta-apps-and-visibility-of-in-app-purchases-in-dev-center/) 扩展在 Microsoft Store 目录中的可见性。 我们的一些合作伙伴已利用此功能来实现以下目标： 
- 发布其扩展的第二个 beta 版本，在 Microsoft Store 中隐藏。
- 最初将扩展发布为隐藏，以在最终将状态更改为在达到某个可信度后可见之前监视初始遥测。

## <a name="thats-it"></a>就这么简单！

如果你已到达本指南底部，则已完成为 Microsoft Edge 开发扩展的过程！ 请务必查看我们的 [提示和技巧](./tips-and-tricks.md) 页面，以了解如何推广你的扩展并与你的用户交互。
