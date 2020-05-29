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
# <span data-ttu-id="54311-104">打包 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="54311-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="54311-105">您最终已经完成了您的扩展，并准备好将其打包。</span><span class="sxs-lookup"><span data-stu-id="54311-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="54311-106">您可能会想知道，在潜在用户的手中，接下来的步骤是如何实现的。</span><span class="sxs-lookup"><span data-stu-id="54311-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="54311-107">本指南旨在教您如何操作。</span><span class="sxs-lookup"><span data-stu-id="54311-107">This guide is intended to teach you how to do just that.</span></span>

<span data-ttu-id="54311-108">扩展打包指南非常全面，它涵盖了你希望了解的有关打包的所有内容，甚至是更精细的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54311-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="54311-109">如果您不想了解有关打包您的扩展的任何信息，您就会很幸运。</span><span class="sxs-lookup"><span data-stu-id="54311-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="54311-110">我们添加了对 ManifoldJS 扩展的支持，这是一个开放的源 Node .js 工具，可充分利用大部分包装 woes。</span><span class="sxs-lookup"><span data-stu-id="54311-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>

> [!NOTE]
> <span data-ttu-id="54311-111">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。</span><span class="sxs-lookup"><span data-stu-id="54311-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="54311-112">[通过你](https://aka.ms/extension-request)的请求成为 Microsoft Store 的一部分，我们将考虑你的未来更新。</span><span class="sxs-lookup"><span data-stu-id="54311-112">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>


<span data-ttu-id="54311-113">使用下面的流程大纲来确定您的包装艾德公司！</span><span class="sxs-lookup"><span data-stu-id="54311-113">Use the process outline below to map out your packaging adventure!</span></span>


## [<span data-ttu-id="54311-114">Windows 开发人员中心中的扩展</span><span class="sxs-lookup"><span data-stu-id="54311-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)

<span data-ttu-id="54311-115">无论你选择哪种程序包创建路由，手动或 ManifoldJS，第一步是注册一个 Windows 开发者帐户并保留你的扩展的名称。</span><span class="sxs-lookup"><span data-stu-id="54311-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>

<span data-ttu-id="54311-116">完成此操作后，你可以继续[创建和测试扩展程序包](./packaging/creating-and-testing-extension-packages.md)，了解如何创建 AppXs 以及如何手动打包你的扩展，或者转到更简单的路由并跳转到[使用 ManifoldJS 打包扩展](./packaging/using-ManifoldJS-to-package-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="54311-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="54311-117">一旦您达到我们的，并且已被批准在 Microsoft Store 中拥有您的分机号，请查看[应用提交核对清单](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。</span><span class="sxs-lookup"><span data-stu-id="54311-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>


## [<span data-ttu-id="54311-118">创建和测试扩展程序包</span><span class="sxs-lookup"><span data-stu-id="54311-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)

<span data-ttu-id="54311-119">本指南的此部分介绍在设置你的[Windows 开发人员帐户并保留你的扩展名称](./packaging/extensions-in-the-windows-Dev-Center.md)后手动创建程序包。</span><span class="sxs-lookup"><span data-stu-id="54311-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="54311-120">如果您想了解包装扩展的详细信息，请阅读。</span><span class="sxs-lookup"><span data-stu-id="54311-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>

<span data-ttu-id="54311-121">还包括有关如何[测试和解压缩打包的扩展的](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)信息。</span><span class="sxs-lookup"><span data-stu-id="54311-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="54311-122">即使您已经有了 ManifoldJS 包装路线，此信息仍是相关的。</span><span class="sxs-lookup"><span data-stu-id="54311-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>

## [<span data-ttu-id="54311-123">本地化扩展程序包</span><span class="sxs-lookup"><span data-stu-id="54311-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)
<span data-ttu-id="54311-124">程序包本地化步骤介于创建 package.appxmanifest 文件和运行最终命令以打包扩展。</span><span class="sxs-lookup"><span data-stu-id="54311-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>
<span data-ttu-id="54311-125">这使你可以在 Microsoft Store 中指明你的扩展支持哪些语言，以及你的扩展名称显示在 Windows 中的语言。</span><span class="sxs-lookup"><span data-stu-id="54311-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>

<span data-ttu-id="54311-126">如果您的扩展不支持多种语言，您可以跳转到本指南本部分中的[Microsoft Store 的名称和说明](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="54311-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>

## [<span data-ttu-id="54311-127">使用 ManifoldJS 打包扩展名</span><span class="sxs-lookup"><span data-stu-id="54311-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)

<span data-ttu-id="54311-128">ManifoldJS 的工具路线用于包装你的扩展，将在你的快速入门中打包你的扩展，最大努力完成。</span><span class="sxs-lookup"><span data-stu-id="54311-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="54311-129">填写某些 Package.appxmanifest 属性后，提供一些 Windows/Microsoft Store 资产，并且将不会打包你的扩展。</span><span class="sxs-lookup"><span data-stu-id="54311-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>

<span data-ttu-id="54311-130">打包扩展后，请参阅创建和测试 Microsoft Edge 扩展的 "[测试](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)" 部分，了解如何旁加载或解包。</span><span class="sxs-lookup"><span data-stu-id="54311-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>


## [<span data-ttu-id="54311-131">运行 Windows 应用认证工具包</span><span class="sxs-lookup"><span data-stu-id="54311-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)

<span data-ttu-id="54311-132">拥有打包的扩展后，即可通过 Windows 应用认证工具包运行它。</span><span class="sxs-lookup"><span data-stu-id="54311-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="54311-133">这样做将在扩展程序包上运行大量测试，以确保它可以用于 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="54311-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>
