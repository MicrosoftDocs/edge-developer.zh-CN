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
# <a name="packaging-microsoft-edge-extensions"></a><span data-ttu-id="8d29b-104">打包 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="8d29b-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="8d29b-105">因此，你已最终完成了扩展并已准备好打包它。</span><span class="sxs-lookup"><span data-stu-id="8d29b-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="8d29b-106">你可能想知道下一步将采取哪些措施来让潜在用户了解这一点。</span><span class="sxs-lookup"><span data-stu-id="8d29b-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="8d29b-107">本指南旨在指导你如何这样做。</span><span class="sxs-lookup"><span data-stu-id="8d29b-107">This guide is intended to teach you how to do just that.</span></span>  

<span data-ttu-id="8d29b-108">扩展打包指南是全面的，它涵盖了你想要了解的有关打包的一切内容，甚至更精细、最精细的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8d29b-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="8d29b-109">如果不想了解打包扩展的一切信息，则很幸运的是。</span><span class="sxs-lookup"><span data-stu-id="8d29b-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="8d29b-110">我们添加了对 ManifoldJS 的扩展的支持，这是一种Node.js包工具，可省去大部分打包。</span><span class="sxs-lookup"><span data-stu-id="8d29b-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>  

> [!NOTE]
> <span data-ttu-id="8d29b-111">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限功能。</span><span class="sxs-lookup"><span data-stu-id="8d29b-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="8d29b-112">[联系我们，](https://developer.microsoft.com/en-us/microsoft-edge/extensions/requests) 请求成为 Microsoft Store 的一部分，我们将考虑你进行将来的更新。</span><span class="sxs-lookup"><span data-stu-id="8d29b-112">[Reach out to us](https://developer.microsoft.com/en-us/microsoft-edge/extensions/requests) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>  

<span data-ttu-id="8d29b-113">使用下面的流程大纲来规划打包体验！</span><span class="sxs-lookup"><span data-stu-id="8d29b-113">Use the process outline below to map out your packaging adventure!</span></span>  

## [<a name="extensions-in-the-windows-dev-center"></a><span data-ttu-id="8d29b-114">Windows 开发人员中心扩展</span><span class="sxs-lookup"><span data-stu-id="8d29b-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)  

<span data-ttu-id="8d29b-115">无论你选择哪个程序包创建路由，手动或 ManifoldJS，第一步是注册 Windows 开发人员帐户，并保留扩展 () 的名称。</span><span class="sxs-lookup"><span data-stu-id="8d29b-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>  

<span data-ttu-id="8d29b-116">完成此操作后，你可以继续创建和测试扩展包以了解如何创建[](./packaging/creating-and-testing-extension-packages.md)AppX 并手动打包扩展，或者转到更简单的路由并跳转到使用[ManifoldJS](./packaging/using-ManifoldJS-to-package-extensions.md)打包扩展。</span><span class="sxs-lookup"><span data-stu-id="8d29b-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="8d29b-117">一旦联系我们并获得批准，在 Microsoft Store 中拥有你的扩展，请查看 [应用提交清单](https://docs.microsoft.com/windows/uwp/publish/app-submissions)。</span><span class="sxs-lookup"><span data-stu-id="8d29b-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>  


## [<a name="creating-and-testing-extension-packages"></a><span data-ttu-id="8d29b-118">创建和测试扩展包</span><span class="sxs-lookup"><span data-stu-id="8d29b-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)  

<span data-ttu-id="8d29b-119">在设置 Windows 开发人员帐户并保留扩展名后，本指南的这一部分将指导你完成手动扩展 ([创建 ](./packaging/extensions-in-the-windows-Dev-Center.md)) 。</span><span class="sxs-lookup"><span data-stu-id="8d29b-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="8d29b-120">如果你对打包扩展的更精细的详细信息感兴趣，请对此进行阅读。</span><span class="sxs-lookup"><span data-stu-id="8d29b-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>  

<span data-ttu-id="8d29b-121">此外，还包括有关如何测试和解压缩打包 [扩展的信息](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)。</span><span class="sxs-lookup"><span data-stu-id="8d29b-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="8d29b-122">此信息是相关的，即使你已经过 ManifoldJS 打包路由。</span><span class="sxs-lookup"><span data-stu-id="8d29b-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>  

## [<a name="localizing-extension-packages"></a><span data-ttu-id="8d29b-123">本地化扩展包</span><span class="sxs-lookup"><span data-stu-id="8d29b-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)  

<span data-ttu-id="8d29b-124">包本地化步骤介于创建appxmanifest.xml文件并运行最后一个命令打包扩展名之间。</span><span class="sxs-lookup"><span data-stu-id="8d29b-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>  
<span data-ttu-id="8d29b-125">这允许你指示你的扩展在 Microsoft Store 一览中支持哪些语言，以及你的扩展名在 Windows 中显示的语言。</span><span class="sxs-lookup"><span data-stu-id="8d29b-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>  

<span data-ttu-id="8d29b-126">如果你的扩展不支持多种语言，可以在本指南的本部分跳转到 [Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 的本地化名称和说明。</span><span class="sxs-lookup"><span data-stu-id="8d29b-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>  

## [<a name="using-manifoldjs-to-package-extensions"></a><span data-ttu-id="8d29b-127">使用 ManifoldJS 打包扩展</span><span class="sxs-lookup"><span data-stu-id="8d29b-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)  

<span data-ttu-id="8d29b-128">用于打包扩展的工具路由，ManifoldJS 会以最少的工作量快速打包扩展。</span><span class="sxs-lookup"><span data-stu-id="8d29b-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="8d29b-129">填写一些 AppXManifest 属性后，提供一些 Windows/Microsoft Store 资产，并且你的扩展将无需任何时间打包。</span><span class="sxs-lookup"><span data-stu-id="8d29b-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>  

<span data-ttu-id="8d29b-130">打包扩展后，请参阅创建和测试[](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package)Microsoft Edge 扩展的测试部分，了解如何旁加载或解压缩它。</span><span class="sxs-lookup"><span data-stu-id="8d29b-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>  

## [<a name="running-the-windows-app-certification-kit"></a><span data-ttu-id="8d29b-131">运行 Windows 应用认证工具包</span><span class="sxs-lookup"><span data-stu-id="8d29b-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)  

<span data-ttu-id="8d29b-132">拥有打包的扩展后，可以通过 Windows 应用认证工具包运行它。</span><span class="sxs-lookup"><span data-stu-id="8d29b-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="8d29b-133">这样做将在扩展包上运行大量测试，以确保它已准备好使用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="8d29b-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>  
