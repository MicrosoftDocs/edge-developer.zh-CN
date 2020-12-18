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
# <span data-ttu-id="16d1f-104">打包 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="16d1f-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="16d1f-105">因此，你已最终完成了扩展并已准备好打包它。</span><span class="sxs-lookup"><span data-stu-id="16d1f-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="16d1f-106">你可能想知道下一步将执行哪些操作，以将此方法掌握在潜在用户之手。</span><span class="sxs-lookup"><span data-stu-id="16d1f-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="16d1f-107">本指南旨在指导你如何这样做。</span><span class="sxs-lookup"><span data-stu-id="16d1f-107">This guide is intended to teach you how to do just that.</span></span>

<span data-ttu-id="16d1f-108">扩展打包指南是全面的，它涵盖了你想要了解的有关打包的一切内容，甚至是更精细、最精细的详细信息。</span><span class="sxs-lookup"><span data-stu-id="16d1f-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="16d1f-109">如果你不希望了解打包扩展的一切信息，则你一去不及事。</span><span class="sxs-lookup"><span data-stu-id="16d1f-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="16d1f-110">我们对 ManifoldJS 增加了对扩展的支持，ManifoldJS 是一种Node.js打包工具，可省去大部分打包。</span><span class="sxs-lookup"><span data-stu-id="16d1f-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>

> [!NOTE]
> <span data-ttu-id="16d1f-111">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。</span><span class="sxs-lookup"><span data-stu-id="16d1f-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="16d1f-112">[如果你的请求是](https://aka.ms/extension-request) Microsoft Store 的一部分，请联系我们，我们将考虑你进行将来的更新。</span><span class="sxs-lookup"><span data-stu-id="16d1f-112">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>


<span data-ttu-id="16d1f-113">使用下面的流程大纲来规划打包之旅！</span><span class="sxs-lookup"><span data-stu-id="16d1f-113">Use the process outline below to map out your packaging adventure!</span></span>


## [<span data-ttu-id="16d1f-114">Windows 开发人员中心扩展</span><span class="sxs-lookup"><span data-stu-id="16d1f-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)

<span data-ttu-id="16d1f-115">无论你选择哪个程序包创建路由，手动还是 ManifoldJS，第一步是注册 Windows 开发人员帐户，并保留扩展 () 的名称。</span><span class="sxs-lookup"><span data-stu-id="16d1f-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>

<span data-ttu-id="16d1f-116">完成此操作后，你可以继续创建和测试扩展包以了解如何创建[](./packaging/creating-and-testing-extension-packages.md)AppX 并手动打包扩展，或者转到更简单的路由并跳转到使用[ManifoldJS](./packaging/using-ManifoldJS-to-package-extensions.md)打包扩展。</span><span class="sxs-lookup"><span data-stu-id="16d1f-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="16d1f-117">Once you've reached to us and have been approved to have your extension in the Microsoft Store， check out the [app submission checklist.](https://docs.microsoft.com/windows/uwp/publish/app-submissions)</span><span class="sxs-lookup"><span data-stu-id="16d1f-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>


## [<span data-ttu-id="16d1f-118">创建和测试扩展包</span><span class="sxs-lookup"><span data-stu-id="16d1f-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)

<span data-ttu-id="16d1f-119">在设置 [Windows ](./packaging/extensions-in-the-windows-Dev-Center.md)开发人员帐户并保留扩展名后，本指南的这一部分将指导你完成手动扩展 (创建) 。</span><span class="sxs-lookup"><span data-stu-id="16d1f-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="16d1f-120">如果你对打包扩展的更详细细节感兴趣，请对此进行阅读。</span><span class="sxs-lookup"><span data-stu-id="16d1f-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>

<span data-ttu-id="16d1f-121">还包括有关如何测试和解压缩打包 [扩展的信息](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。</span><span class="sxs-lookup"><span data-stu-id="16d1f-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="16d1f-122">此信息是相关的，即使你已经过 ManifoldJS 打包路由。</span><span class="sxs-lookup"><span data-stu-id="16d1f-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>

## [<span data-ttu-id="16d1f-123">本地化扩展包</span><span class="sxs-lookup"><span data-stu-id="16d1f-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)
<span data-ttu-id="16d1f-124">包本地化步骤包括创建appxmanifest.xml文件并运行最后一个命令打包扩展。</span><span class="sxs-lookup"><span data-stu-id="16d1f-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>
<span data-ttu-id="16d1f-125">这允许你指示你的扩展在 Microsoft Store 一览中支持哪些语言，以及你的扩展名在 Windows 中显示的语言。</span><span class="sxs-lookup"><span data-stu-id="16d1f-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>

<span data-ttu-id="16d1f-126">如果你的扩展不支持多种语言，可以跳转到本指南本部分中 [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 的本地化名称和说明。</span><span class="sxs-lookup"><span data-stu-id="16d1f-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>

## [<span data-ttu-id="16d1f-127">使用 ManifoldJS 打包扩展</span><span class="sxs-lookup"><span data-stu-id="16d1f-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)

<span data-ttu-id="16d1f-128">用于打包扩展的工具路由，ManifoldJS 会以最少的工作量将扩展打包在一起。</span><span class="sxs-lookup"><span data-stu-id="16d1f-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="16d1f-129">填写完一些 AppXManifest 属性后，提供一些 Windows/Microsoft Store 资产，你的扩展将无需任何时间打包。</span><span class="sxs-lookup"><span data-stu-id="16d1f-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>

<span data-ttu-id="16d1f-130">打包扩展后，请参阅"创建和测试[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)Microsoft Edge 扩展"的测试部分，了解如何旁加载或解压缩它。</span><span class="sxs-lookup"><span data-stu-id="16d1f-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>


## [<span data-ttu-id="16d1f-131">运行 Windows 应用认证工具包</span><span class="sxs-lookup"><span data-stu-id="16d1f-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)

<span data-ttu-id="16d1f-132">拥有打包的扩展后，可以通过 Windows 应用认证工具包运行它。</span><span class="sxs-lookup"><span data-stu-id="16d1f-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="16d1f-133">这样做将在扩展程序包上运行大量测试，以确保它已准备好用于 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="16d1f-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>
