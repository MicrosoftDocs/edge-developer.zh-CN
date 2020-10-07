---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: Find out about the enterprise specific aspects of Microsoft Edge Extensions, and see how they're similar to UWP apps.
title: Extensions for enterprise
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.custom: seodec18
ms.openlocfilehash: 8f50c282fce11d2654f990bf135941e0616af3f3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563320"
---
# <span data-ttu-id="a6363-104">Extensions for Enterprise</span><span class="sxs-lookup"><span data-stu-id="a6363-104">Extensions for Enterprise</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="a6363-105">Microsoft Edge extensions have a similar workflow when compared to other enterprise UWP apps.</span><span class="sxs-lookup"><span data-stu-id="a6363-105">Microsoft Edge extensions have a similar workflow when compared to other enterprise UWP apps.</span></span> <span data-ttu-id="a6363-106">The information below details enterprise specific aspects of Microsoft Edge extensions.</span><span class="sxs-lookup"><span data-stu-id="a6363-106">The information below details enterprise specific aspects of Microsoft Edge extensions.</span></span>

## <span data-ttu-id="a6363-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="a6363-107">Prerequisites</span></span>
<span data-ttu-id="a6363-108">The following items are suggested to develop, package, and deploy a Microsoft Edge extension for enterprise:</span><span class="sxs-lookup"><span data-stu-id="a6363-108">The following items are suggested to develop, package, and deploy a Microsoft Edge extension for enterprise:</span></span>

+ <span data-ttu-id="a6363-109">Windows Developer Portal account, to sign and release the extension to the enterprise private store.</span><span class="sxs-lookup"><span data-stu-id="a6363-109">Windows Developer Portal account, to sign and release the extension to the enterprise private store.</span></span> <span data-ttu-id="a6363-110">See [Opening a developer account](/windows/uwp/publish/opening-a-developer-account) for more details.</span><span class="sxs-lookup"><span data-stu-id="a6363-110">See [Opening a developer account](/windows/uwp/publish/opening-a-developer-account) for more details.</span></span>
+ <span data-ttu-id="a6363-111">Microsoft Store for Business or Education, to distribute the application to the enterprise.</span><span class="sxs-lookup"><span data-stu-id="a6363-111">Microsoft Store for Business or Education, to distribute the application to the enterprise.</span></span> <span data-ttu-id="a6363-112">See the [Microsoft Store for Business and Education documentation](/microsoft-store/) for more details.</span><span class="sxs-lookup"><span data-stu-id="a6363-112">See the [Microsoft Store for Business and Education documentation](/microsoft-store/) for more details.</span></span>
+ <span data-ttu-id="a6363-113">Identify which versions of Windows 10 will be running the Microsoft Edge extension.</span><span class="sxs-lookup"><span data-stu-id="a6363-113">Identify which versions of Windows 10 will be running the Microsoft Edge extension.</span></span> <span data-ttu-id="a6363-114">See [Windows 10 release information](https://www.microsoft.com/itpro/windows-10/release-information) for a listing of existing Windows 10 releases.</span><span class="sxs-lookup"><span data-stu-id="a6363-114">See [Windows 10 release information](https://www.microsoft.com/itpro/windows-10/release-information) for a listing of existing Windows 10 releases.</span></span>

> [!NOTE]
> <span data-ttu-id="a6363-115">Sideloading can be considered an alternative to using the Windows Developer Portal to sign the release the extension.</span><span class="sxs-lookup"><span data-stu-id="a6363-115">Sideloading can be considered an alternative to using the Windows Developer Portal to sign the release the extension.</span></span> <span data-ttu-id="a6363-116">See the behaviour of sideloading extensions below for more details.</span><span class="sxs-lookup"><span data-stu-id="a6363-116">See the behaviour of sideloading extensions below for more details.</span></span>

## <span data-ttu-id="a6363-117">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="a6363-117">Windows Information Protection</span></span>
<span data-ttu-id="a6363-118">Microsoft Edge extensions currently don't honor Windows Information Protection (WIP) settings.</span><span class="sxs-lookup"><span data-stu-id="a6363-118">Microsoft Edge extensions currently don't honor Windows Information Protection (WIP) settings.</span></span> <span data-ttu-id="a6363-119">If an enterprise is concerned about data protection, extensions support should not be enabled for Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a6363-119">If an enterprise is concerned about data protection, extensions support should not be enabled for Microsoft Edge.</span></span>

<span data-ttu-id="a6363-120">To disable extensions for employees, configure Group Policy and Microsoft Intune settings.</span><span class="sxs-lookup"><span data-stu-id="a6363-120">To disable extensions for employees, configure Group Policy and Microsoft Intune settings.</span></span> <span data-ttu-id="a6363-121">For more info on which policies to configure, see [Available policies for Microsoft Edge](https://technet.microsoft.com/itpro/microsoft-edge/available-policies).</span><span class="sxs-lookup"><span data-stu-id="a6363-121">For more info on which policies to configure, see [Available policies for Microsoft Edge](https://technet.microsoft.com/itpro/microsoft-edge/available-policies).</span></span>

## <span data-ttu-id="a6363-122">Packaging Extensions</span><span class="sxs-lookup"><span data-stu-id="a6363-122">Packaging Extensions</span></span>
<span data-ttu-id="a6363-123">Before an enterprise can distribute an extension to its employees, it must first be packaged.</span><span class="sxs-lookup"><span data-stu-id="a6363-123">Before an enterprise can distribute an extension to its employees, it must first be packaged.</span></span> <span data-ttu-id="a6363-124">Instructions on packaging extensions are available in the [Packaging](./guides/packaging.md) guide.</span><span class="sxs-lookup"><span data-stu-id="a6363-124">Instructions on packaging extensions are available in the [Packaging](./guides/packaging.md) guide.</span></span>

> [!TIP]
> <span data-ttu-id="a6363-125">Be sure to test installing and running your extension on all the versions of Windows 10 to ensure it will work as expected before distributing.</span><span class="sxs-lookup"><span data-stu-id="a6363-125">Be sure to test installing and running your extension on all the versions of Windows 10 to ensure it will work as expected before distributing.</span></span>

## <span data-ttu-id="a6363-126">Distributing Extensions</span><span class="sxs-lookup"><span data-stu-id="a6363-126">Distributing Extensions</span></span>
<span data-ttu-id="a6363-127">Once an extension has been packaged, it can be distributed to employees through the Microsoft Store, Microsoft Store for Business, or by sideloading.</span><span class="sxs-lookup"><span data-stu-id="a6363-127">Once an extension has been packaged, it can be distributed to employees through the Microsoft Store, Microsoft Store for Business, or by sideloading.</span></span>

<span data-ttu-id="a6363-128">Extensions distributed though the Microsoft Store for Business can either be assigned to employees, or added to a private store where all employees can access them.</span><span class="sxs-lookup"><span data-stu-id="a6363-128">Extensions distributed though the Microsoft Store for Business can either be assigned to employees, or added to a private store where all employees can access them.</span></span> <span data-ttu-id="a6363-129">This can be done by following the [Distribute "Line-of-Business" (LOB) apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) guide.</span><span class="sxs-lookup"><span data-stu-id="a6363-129">This can be done by following the [Distribute "Line-of-Business" (LOB) apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) guide.</span></span>

<span data-ttu-id="a6363-130">To sideload extensions, devices (unmanaged or managed) must be unlocked for sideloading.</span><span class="sxs-lookup"><span data-stu-id="a6363-130">To sideload extensions, devices (unmanaged or managed) must be unlocked for sideloading.</span></span> <span data-ttu-id="a6363-131">See [Sideload LOB apps in Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) for more info on how to sideload packaged extensions.</span><span class="sxs-lookup"><span data-stu-id="a6363-131">See [Sideload LOB apps in Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) for more info on how to sideload packaged extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6363-132">If the enterprise is both developing and distributing the extension internally, the enterprise will require both the Microsoft Store for Business (or Education) and a Windows Developer Portal account.</span><span class="sxs-lookup"><span data-stu-id="a6363-132">If the enterprise is both developing and distributing the extension internally, the enterprise will require both the Microsoft Store for Business (or Education) and a Windows Developer Portal account.</span></span>

### <span data-ttu-id="a6363-133">Behavior of Sideloaded Extensions</span><span class="sxs-lookup"><span data-stu-id="a6363-133">Behavior of Sideloaded Extensions</span></span>
<span data-ttu-id="a6363-134">Unlike extensions distributed through the Microsoft Store (or the Microsoft Store for Business), sideloaded extensions are treated differently in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a6363-134">Unlike extensions distributed through the Microsoft Store (or the Microsoft Store for Business), sideloaded extensions are treated differently in Microsoft Edge.</span></span>

<span data-ttu-id="a6363-135">The first difference affects how sideloaded extensions behave after installation.</span><span class="sxs-lookup"><span data-stu-id="a6363-135">The first difference affects how sideloaded extensions behave after installation.</span></span> <span data-ttu-id="a6363-136">Unlike extensions from the Microsoft Store, sideloaded extensions do not immediately display the "You have a new extension" notification and need to be manually turned on by the user.</span><span class="sxs-lookup"><span data-stu-id="a6363-136">Unlike extensions from the Microsoft Store, sideloaded extensions do not immediately display the "You have a new extension" notification and need to be manually turned on by the user.</span></span>

<span data-ttu-id="a6363-137">To turn on the extension, open the **More (...)** menu, select **"Extensions"** and you should see the sideloaded extension in the list of installed extensions.</span><span class="sxs-lookup"><span data-stu-id="a6363-137">To turn on the extension, open the **More (...)** menu, select **"Extensions"** and you should see the sideloaded extension in the list of installed extensions.</span></span> <span data-ttu-id="a6363-138">Click on the extension and turn it on.</span><span class="sxs-lookup"><span data-stu-id="a6363-138">Click on the extension and turn it on.</span></span>

<span data-ttu-id="a6363-139">The second difference affects how sideloaded extensions appear in the browser.</span><span class="sxs-lookup"><span data-stu-id="a6363-139">The second difference affects how sideloaded extensions appear in the browser.</span></span> <span data-ttu-id="a6363-140">For example, both the "You have a new extension" notification and the list of installed extensions include an additional warning stating that the extension is from an unknown source.</span><span class="sxs-lookup"><span data-stu-id="a6363-140">For example, both the "You have a new extension" notification and the list of installed extensions include an additional warning stating that the extension is from an unknown source.</span></span>

![sideload warning 1](./media/sideload-permissionflyout.PNG)

![sideload warning 2](./media/sideload-l1warning.PNG)

<span data-ttu-id="a6363-143">The third and final difference affects how sideloaded extensions behave on browser startup.</span><span class="sxs-lookup"><span data-stu-id="a6363-143">The third and final difference affects how sideloaded extensions behave on browser startup.</span></span> <span data-ttu-id="a6363-144">Sideloaded extensions on devices that are either domain-joined or MDM enabled will behave like extensions from the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a6363-144">Sideloaded extensions on devices that are either domain-joined or MDM enabled will behave like extensions from the Microsoft Store.</span></span> <span data-ttu-id="a6363-145">However, sideloaded extensions on devices that are not domain-joined or MDM enabled will be turned off during browser startup and require the user to take explicit action.</span><span class="sxs-lookup"><span data-stu-id="a6363-145">However, sideloaded extensions on devices that are not domain-joined or MDM enabled will be turned off during browser startup and require the user to take explicit action.</span></span>

<span data-ttu-id="a6363-146">Shortly after browser startup (after ~10 seconds of inactivity) the following notification will appear near the bottom of the window.</span><span class="sxs-lookup"><span data-stu-id="a6363-146">Shortly after browser startup (after ~10 seconds of inactivity) the following notification will appear near the bottom of the window.</span></span>

![sideload notification](./media/sideload-scareUI.PNG)

<span data-ttu-id="a6363-148">Each time Microsoft Edge is launched, users will need to select "Turn on anyway" in order to use the extension.</span><span class="sxs-lookup"><span data-stu-id="a6363-148">Each time Microsoft Edge is launched, users will need to select "Turn on anyway" in order to use the extension.</span></span>
