---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: 了解 Microsoft Edge 扩展的企业特定方面，并了解它们与 UWP 应用的相似之处。
title: 企业版扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 8f50c282fce11d2654f990bf135941e0616af3f3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563320"
---
# <span data-ttu-id="738db-104">企业版扩展</span><span class="sxs-lookup"><span data-stu-id="738db-104">Extensions for Enterprise</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="738db-105">与其他企业的 UWP 应用比较时，Microsoft Edge 扩展具有类似的工作流。</span><span class="sxs-lookup"><span data-stu-id="738db-105">Microsoft Edge extensions have a similar workflow when compared to other enterprise UWP apps.</span></span> <span data-ttu-id="738db-106">下面的信息详细介绍了 Microsoft Edge 扩展的企业特定方面。</span><span class="sxs-lookup"><span data-stu-id="738db-106">The information below details enterprise specific aspects of Microsoft Edge extensions.</span></span>

## <span data-ttu-id="738db-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="738db-107">Prerequisites</span></span>
<span data-ttu-id="738db-108">建议使用以下项目为企业版开发、打包和部署 Microsoft Edge 扩展：</span><span class="sxs-lookup"><span data-stu-id="738db-108">The following items are suggested to develop, package, and deploy a Microsoft Edge extension for enterprise:</span></span>

+ <span data-ttu-id="738db-109">Windows 开发人员门户帐户，用于对企业专用存储进行签名和释放扩展。</span><span class="sxs-lookup"><span data-stu-id="738db-109">Windows Developer Portal account, to sign and release the extension to the enterprise private store.</span></span> <span data-ttu-id="738db-110">有关详细信息，请参阅[打开开发人员帐户](/windows/uwp/publish/opening-a-developer-account)。</span><span class="sxs-lookup"><span data-stu-id="738db-110">See [Opening a developer account](/windows/uwp/publish/opening-a-developer-account) for more details.</span></span>
+ <span data-ttu-id="738db-111">Microsoft Store for Business 或教育版，用于将应用程序分发到企业。</span><span class="sxs-lookup"><span data-stu-id="738db-111">Microsoft Store for Business or Education, to distribute the application to the enterprise.</span></span> <span data-ttu-id="738db-112">有关详细信息，请参阅[Microsoft Store For Business 和教育文档](/microsoft-store/)。</span><span class="sxs-lookup"><span data-stu-id="738db-112">See the [Microsoft Store for Business and Education documentation](/microsoft-store/) for more details.</span></span>
+ <span data-ttu-id="738db-113">确定将运行 Microsoft Edge 扩展的 Windows 10 版本。</span><span class="sxs-lookup"><span data-stu-id="738db-113">Identify which versions of Windows 10 will be running the Microsoft Edge extension.</span></span> <span data-ttu-id="738db-114">有关现有 Windows 10 版本的列表，请参阅[Windows 10 发布信息](https://www.microsoft.com/itpro/windows-10/release-information)。</span><span class="sxs-lookup"><span data-stu-id="738db-114">See [Windows 10 release information](https://www.microsoft.com/itpro/windows-10/release-information) for a listing of existing Windows 10 releases.</span></span>

> [!NOTE]
> <span data-ttu-id="738db-115">可将旁显示为使用 Windows 开发人员门户对扩展发布进行签名的替代方法。</span><span class="sxs-lookup"><span data-stu-id="738db-115">Sideloading can be considered an alternative to using the Windows Developer Portal to sign the release the extension.</span></span> <span data-ttu-id="738db-116">有关详细信息，请参阅下面的旁加载扩展行为。</span><span class="sxs-lookup"><span data-stu-id="738db-116">See the behaviour of sideloading extensions below for more details.</span></span>

## <span data-ttu-id="738db-117">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="738db-117">Windows Information Protection</span></span>
<span data-ttu-id="738db-118">Microsoft Edge 扩展目前不接受 Windows 信息保护（WIP）设置。</span><span class="sxs-lookup"><span data-stu-id="738db-118">Microsoft Edge extensions currently don't honor Windows Information Protection (WIP) settings.</span></span> <span data-ttu-id="738db-119">如果企业担心数据保护，则不应为 Microsoft Edge 启用扩展支持。</span><span class="sxs-lookup"><span data-stu-id="738db-119">If an enterprise is concerned about data protection, extensions support should not be enabled for Microsoft Edge.</span></span>

<span data-ttu-id="738db-120">若要禁用员工的扩展，请配置组策略和 Microsoft Intune 设置。</span><span class="sxs-lookup"><span data-stu-id="738db-120">To disable extensions for employees, configure Group Policy and Microsoft Intune settings.</span></span> <span data-ttu-id="738db-121">有关要配置的策略的详细信息，请参阅[Microsoft Edge 的可用策略](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)。</span><span class="sxs-lookup"><span data-stu-id="738db-121">For more info on which policies to configure, see [Available policies for Microsoft Edge](https://technet.microsoft.com/itpro/microsoft-edge/available-policies).</span></span>

## <span data-ttu-id="738db-122">包装扩展</span><span class="sxs-lookup"><span data-stu-id="738db-122">Packaging Extensions</span></span>
<span data-ttu-id="738db-123">在企业可以向其员工分发扩展之前，必须先将其打包。</span><span class="sxs-lookup"><span data-stu-id="738db-123">Before an enterprise can distribute an extension to its employees, it must first be packaged.</span></span> <span data-ttu-id="738db-124">有关包装扩展的说明，请访问[打包](./guides/packaging.md)指南。</span><span class="sxs-lookup"><span data-stu-id="738db-124">Instructions on packaging extensions are available in the [Packaging](./guides/packaging.md) guide.</span></span>

> [!TIP]
> <span data-ttu-id="738db-125">请务必在 Windows 10 的所有版本上测试安装和运行扩展，以确保它在分发之前将按预期工作。</span><span class="sxs-lookup"><span data-stu-id="738db-125">Be sure to test installing and running your extension on all the versions of Windows 10 to ensure it will work as expected before distributing.</span></span>

## <span data-ttu-id="738db-126">分发扩展</span><span class="sxs-lookup"><span data-stu-id="738db-126">Distributing Extensions</span></span>
<span data-ttu-id="738db-127">扩展已打包后，可以通过 Microsoft Store、Microsoft Store for Business 或通过旁加载将其分发给员工。</span><span class="sxs-lookup"><span data-stu-id="738db-127">Once an extension has been packaged, it can be distributed to employees through the Microsoft Store, Microsoft Store for Business, or by sideloading.</span></span>

<span data-ttu-id="738db-128">分配了 Microsoft Store for Business 的扩展可分配给员工，或添加到所有员工均可访问的私人存储中。</span><span class="sxs-lookup"><span data-stu-id="738db-128">Extensions distributed though the Microsoft Store for Business can either be assigned to employees, or added to a private store where all employees can access them.</span></span> <span data-ttu-id="738db-129">可通过将["业务线" （LOB）应用分布到企业](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)指南来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="738db-129">This can be done by following the [Distribute "Line-of-Business" (LOB) apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) guide.</span></span>

<span data-ttu-id="738db-130">若要旁加载扩展，必须解除设备（非托管或托管）的旁加载。</span><span class="sxs-lookup"><span data-stu-id="738db-130">To sideload extensions, devices (unmanaged or managed) must be unlocked for sideloading.</span></span> <span data-ttu-id="738db-131">有关如何旁加载打包的扩展的详细信息，请参阅[Windows 10 中的旁加载 LOB 应用](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="738db-131">See [Sideload LOB apps in Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) for more info on how to sideload packaged extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="738db-132">如果企业在内部开发和分发扩展，企业将需要 Microsoft Store for Business （或教育版）和 Windows 开发人员门户帐户。</span><span class="sxs-lookup"><span data-stu-id="738db-132">If the enterprise is both developing and distributing the extension internally, the enterprise will require both the Microsoft Store for Business (or Education) and a Windows Developer Portal account.</span></span>

### <span data-ttu-id="738db-133">旁加载扩展的行为</span><span class="sxs-lookup"><span data-stu-id="738db-133">Behavior of Sideloaded Extensions</span></span>
<span data-ttu-id="738db-134">与通过 Microsoft Store （或 Microsoft Store for Business）分发的扩展不同，旁加载扩展在 Microsoft Edge 中的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="738db-134">Unlike extensions distributed through the Microsoft Store (or the Microsoft Store for Business), sideloaded extensions are treated differently in Microsoft Edge.</span></span>

<span data-ttu-id="738db-135">第一个区别影响安装后旁加载扩展的行为方式。</span><span class="sxs-lookup"><span data-stu-id="738db-135">The first difference affects how sideloaded extensions behave after installation.</span></span> <span data-ttu-id="738db-136">与 Microsoft Store 中的扩展不同，旁加载扩展不会立即显示 "你有新的扩展名" 通知，并且需要由用户手动打开。</span><span class="sxs-lookup"><span data-stu-id="738db-136">Unlike extensions from the Microsoft Store, sideloaded extensions do not immediately display the "You have a new extension" notification and need to be manually turned on by the user.</span></span>

<span data-ttu-id="738db-137">若要打开扩展，请打开 "**更多（...）** " 菜单，选择 **"扩展"** ，你应该可以在已安装的扩展列表中看到旁加载扩展。</span><span class="sxs-lookup"><span data-stu-id="738db-137">To turn on the extension, open the **More (...)** menu, select **"Extensions"** and you should see the sideloaded extension in the list of installed extensions.</span></span> <span data-ttu-id="738db-138">单击 "扩展"，然后将其打开。</span><span class="sxs-lookup"><span data-stu-id="738db-138">Click on the extension and turn it on.</span></span>

<span data-ttu-id="738db-139">第二个差异影响旁加载扩展在浏览器中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="738db-139">The second difference affects how sideloaded extensions appear in the browser.</span></span> <span data-ttu-id="738db-140">例如，"你有新的扩展名" 通知和已安装的扩展列表中包含一条附加警告，指出扩展来自未知源。</span><span class="sxs-lookup"><span data-stu-id="738db-140">For example, both the "You have a new extension" notification and the list of installed extensions include an additional warning stating that the extension is from an unknown source.</span></span>

![旁加载警告1](./media/sideload-permissionflyout.PNG)

![旁加载警告2](./media/sideload-l1warning.PNG)

<span data-ttu-id="738db-143">第三种和最终区别影响旁加载扩展在浏览器启动时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="738db-143">The third and final difference affects how sideloaded extensions behave on browser startup.</span></span> <span data-ttu-id="738db-144">在已加入域或启用 MDM 的设备上的旁加载扩展将类似于 Microsoft Store 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="738db-144">Sideloaded extensions on devices that are either domain-joined or MDM enabled will behave like extensions from the Microsoft Store.</span></span> <span data-ttu-id="738db-145">但是，在浏览器启动过程中，将关闭未加入域或启用 MDM 的设备上的旁加载扩展，并要求用户执行显式操作。</span><span class="sxs-lookup"><span data-stu-id="738db-145">However, sideloaded extensions on devices that are not domain-joined or MDM enabled will be turned off during browser startup and require the user to take explicit action.</span></span>

<span data-ttu-id="738db-146">浏览器启动后不久（大约10秒的非活动时间），将在窗口底部附近显示以下通知。</span><span class="sxs-lookup"><span data-stu-id="738db-146">Shortly after browser startup (after ~10 seconds of inactivity) the following notification will appear near the bottom of the window.</span></span>

![旁加载通知](./media/sideload-scareUI.PNG)

<span data-ttu-id="738db-148">每次启动 Microsoft Edge 时，用户都需要选择 "仍启用"，以便使用该扩展名。</span><span class="sxs-lookup"><span data-stu-id="738db-148">Each time Microsoft Edge is launched, users will need to select "Turn on anyway" in order to use the extension.</span></span>
