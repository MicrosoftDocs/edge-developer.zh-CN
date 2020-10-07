---
ms.assetid: f3560505-e01f-47e5-9ad6-7a419f060fc2
description: Learn about how you can use native messaging to have your extension communicate with a companion UWP app.
title: Extensions - Packaging
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: 23c97f366db527cae2672d6ad46fa666583f6398
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563258"
---
# <span data-ttu-id="61963-104">Packaging Microsoft Edge extensions</span><span class="sxs-lookup"><span data-stu-id="61963-104">Packaging Microsoft Edge extensions</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="61963-105">So you've finally completed your extension and are ready to package it up.</span><span class="sxs-lookup"><span data-stu-id="61963-105">So you've finally completed your extension and are ready to package it up.</span></span> <span data-ttu-id="61963-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span><span class="sxs-lookup"><span data-stu-id="61963-106">You might be wondering what the next steps are toward getting this in the hands of potential users.</span></span> <span data-ttu-id="61963-107">This guide is intended to teach you how to do just that.</span><span class="sxs-lookup"><span data-stu-id="61963-107">This guide is intended to teach you how to do just that.</span></span>

<span data-ttu-id="61963-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span><span class="sxs-lookup"><span data-stu-id="61963-108">The extension packaging guide is comprehensive in that it covers everything you'd want to know about packaging, even the finer, nitty gritty details.</span></span> <span data-ttu-id="61963-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span><span class="sxs-lookup"><span data-stu-id="61963-109">If you don't want to learn everything there is to know about packaging your extension, you're in luck.</span></span> <span data-ttu-id="61963-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span><span class="sxs-lookup"><span data-stu-id="61963-110">We've added support for extensions to ManifoldJS, an open source Node.js tool that takes the majority of your packaging woes away.</span></span>

> [!NOTE]
> <span data-ttu-id="61963-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span><span class="sxs-lookup"><span data-stu-id="61963-111">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="61963-112">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span><span class="sxs-lookup"><span data-stu-id="61963-112">[Reach out to us](https://aka.ms/extension-request) with your requests to be a part of the Microsoft Store, and we’ll consider you for a future update.</span></span>


<span data-ttu-id="61963-113">Use the process outline below to map out your packaging adventure!</span><span class="sxs-lookup"><span data-stu-id="61963-113">Use the process outline below to map out your packaging adventure!</span></span>


## [<span data-ttu-id="61963-114">Extensions in the Windows Dev Center</span><span class="sxs-lookup"><span data-stu-id="61963-114">Extensions in the Windows Dev Center</span></span>](./packaging/extensions-in-the-windows-dev-center.md)

<span data-ttu-id="61963-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span><span class="sxs-lookup"><span data-stu-id="61963-115">No matter which package creation route you choose, manual or ManifoldJS, the first step is registering for a Windows Developer account and reserving the name(s) of your extension.</span></span>

<span data-ttu-id="61963-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="61963-116">Once you've done this, you can either move on to [Creating and testing extension packages](./packaging/creating-and-testing-extension-packages.md) to learn how AppXs are created and manually package your extension, or go the easier route and jump to [Using ManifoldJS to package extensions](./packaging/using-ManifoldJS-to-package-extensions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="61963-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span><span class="sxs-lookup"><span data-stu-id="61963-117">Once you've reached out to us and have been approved to have your extension in the Microsoft Store, check out the [app submission checklist](https://docs.microsoft.com/windows/uwp/publish/app-submissions).</span></span>


## [<span data-ttu-id="61963-118">Creating and testing extension packages</span><span class="sxs-lookup"><span data-stu-id="61963-118">Creating and testing extension packages</span></span>](./packaging/creating-and-testing-extension-packages.md)

<span data-ttu-id="61963-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span><span class="sxs-lookup"><span data-stu-id="61963-119">This section of the guide walks through manual extension package creation once [you've set up your Windows Developer account and reserved your extension name(s)](./packaging/extensions-in-the-windows-Dev-Center.md).</span></span> <span data-ttu-id="61963-120">If you're curious about the finer details of packaging an extension, give this a read.</span><span class="sxs-lookup"><span data-stu-id="61963-120">If you're curious about the finer details of packaging an extension, give this a read.</span></span>

<span data-ttu-id="61963-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span><span class="sxs-lookup"><span data-stu-id="61963-121">Also included is info on how to [test and unpack a packaged extension](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package).</span></span> <span data-ttu-id="61963-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span><span class="sxs-lookup"><span data-stu-id="61963-122">This info is relevant even if you've gone the ManifoldJS packaging route.</span></span>

## [<span data-ttu-id="61963-123">Localizing extension packages</span><span class="sxs-lookup"><span data-stu-id="61963-123">Localizing extension packages</span></span>](./packaging/localizing-extension-packages.md)
<span data-ttu-id="61963-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span><span class="sxs-lookup"><span data-stu-id="61963-124">The package localization step falls between creating your appxmanifest.xml file and running the final command to package your extension.</span></span>
<span data-ttu-id="61963-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span><span class="sxs-lookup"><span data-stu-id="61963-125">This allows you to indicate which languages your extensions supports in your Microsoft Store listing, and what language your extension's name appears in Windows.</span></span>

<span data-ttu-id="61963-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span><span class="sxs-lookup"><span data-stu-id="61963-126">You can jump to [Localizing name and description for the Microsoft Store](./packaging/localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) in this section of the guide if your extension doesn't support multiple languages.</span></span>

## [<span data-ttu-id="61963-127">Using ManifoldJS to package extensions</span><span class="sxs-lookup"><span data-stu-id="61963-127">Using ManifoldJS to package extensions</span></span>](./packaging/using-ManifoldJS-to-package-extensions.md)

<span data-ttu-id="61963-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span><span class="sxs-lookup"><span data-stu-id="61963-128">The tool route for packaging your extension, ManifoldJS will package up your extension in a snap with minimal effort on your end.</span></span> <span data-ttu-id="61963-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span><span class="sxs-lookup"><span data-stu-id="61963-129">Provide a few Windows/Microsoft Store assets after filling out some AppXManifest properties and your extension will be packaged in no time.</span></span>

<span data-ttu-id="61963-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span><span class="sxs-lookup"><span data-stu-id="61963-130">Once your extension is packaged, see the [testing](./packaging/creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing your Microsoft Edge extension to learn how to sideload or unpack it.</span></span>


## [<span data-ttu-id="61963-131">Running the Windows App Certification Kit</span><span class="sxs-lookup"><span data-stu-id="61963-131">Running the Windows App Certification Kit</span></span>](./packaging/running-the-windows-app-certification-kit.md)

<span data-ttu-id="61963-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span><span class="sxs-lookup"><span data-stu-id="61963-132">Once you have a packaged extension, you can then run it through the Windows App Certification Kit.</span></span> <span data-ttu-id="61963-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="61963-133">Doing so will run a number of tests on your extension package to ensure that it's ready for the Microsoft Store.</span></span>
