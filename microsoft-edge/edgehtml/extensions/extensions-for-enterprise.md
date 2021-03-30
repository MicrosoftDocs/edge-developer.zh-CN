---
ms.assetid: 8e2f75c4-fb7f-4892-a6c2-23bac081581a
description: 了解 Microsoft Edge 扩展的企业特定方面，并查看它们如何与 UWP 应用类似。
title: 适用于企业的扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7c23bc24e20b7b00b8779f209dcac8c795067fd5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232715"
---
# <span data-ttu-id="bec7a-104">企业扩展</span><span class="sxs-lookup"><span data-stu-id="bec7a-104">Extensions for Enterprise</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="bec7a-105">与其他企业 UWP 应用相比，Microsoft Edge 扩展具有类似的工作流。</span><span class="sxs-lookup"><span data-stu-id="bec7a-105">Microsoft Edge extensions have a similar workflow when compared to other enterprise UWP apps.</span></span> <span data-ttu-id="bec7a-106">以下信息详细介绍了 Microsoft Edge 扩展的企业特定方面。</span><span class="sxs-lookup"><span data-stu-id="bec7a-106">The information below details enterprise specific aspects of Microsoft Edge extensions.</span></span>

## <span data-ttu-id="bec7a-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="bec7a-107">Prerequisites</span></span>
<span data-ttu-id="bec7a-108">建议开发、打包和部署适用于企业的 Microsoft Edge 扩展项：</span><span class="sxs-lookup"><span data-stu-id="bec7a-108">The following items are suggested to develop, package, and deploy a Microsoft Edge extension for enterprise:</span></span>

+ <span data-ttu-id="bec7a-109">Windows 开发人员门户帐户，用于对企业专用应用商店的扩展进行签名和发布。</span><span class="sxs-lookup"><span data-stu-id="bec7a-109">Windows Developer Portal account, to sign and release the extension to the enterprise private store.</span></span> <span data-ttu-id="bec7a-110">有关 [更多详细信息，请参阅"](/windows/uwp/publish/opening-a-developer-account) 打开开发人员帐户"。</span><span class="sxs-lookup"><span data-stu-id="bec7a-110">See [Opening a developer account](/windows/uwp/publish/opening-a-developer-account) for more details.</span></span>
+ <span data-ttu-id="bec7a-111">适用于企业或教育的 Microsoft Store，将应用程序分发到企业。</span><span class="sxs-lookup"><span data-stu-id="bec7a-111">Microsoft Store for Business or Education, to distribute the application to the enterprise.</span></span> <span data-ttu-id="bec7a-112">有关更多详细信息 [，请参阅适用于企业和教育的 Microsoft](/microsoft-store/) Store 文档。</span><span class="sxs-lookup"><span data-stu-id="bec7a-112">See the [Microsoft Store for Business and Education documentation](/microsoft-store/) for more details.</span></span>
+ <span data-ttu-id="bec7a-113">确定哪些版本的 Windows 10 将运行 Microsoft Edge 扩展。</span><span class="sxs-lookup"><span data-stu-id="bec7a-113">Identify which versions of Windows 10 will be running the Microsoft Edge extension.</span></span> <span data-ttu-id="bec7a-114">有关 [现有 Windows 10](https://www.microsoft.com/itpro/windows-10/release-information) 版本列表，请参阅 Windows 10 版本信息。</span><span class="sxs-lookup"><span data-stu-id="bec7a-114">See [Windows 10 release information](https://www.microsoft.com/itpro/windows-10/release-information) for a listing of existing Windows 10 releases.</span></span>

> [!NOTE]
> <span data-ttu-id="bec7a-115">旁加载可以视为使用 Windows 开发人员门户对扩展版本进行签名的替代方法。</span><span class="sxs-lookup"><span data-stu-id="bec7a-115">Sideloading can be considered an alternative to using the Windows Developer Portal to sign the release the extension.</span></span> <span data-ttu-id="bec7a-116">有关详细信息，请参阅以下旁加载扩展的行为。</span><span class="sxs-lookup"><span data-stu-id="bec7a-116">See the behaviour of sideloading extensions below for more details.</span></span>

## <span data-ttu-id="bec7a-117">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="bec7a-117">Windows Information Protection</span></span>
<span data-ttu-id="bec7a-118">Microsoft Edge 扩展当前不沿用 Windows 信息保护 (WIP) 设置。</span><span class="sxs-lookup"><span data-stu-id="bec7a-118">Microsoft Edge extensions currently don't honor Windows Information Protection (WIP) settings.</span></span> <span data-ttu-id="bec7a-119">如果企业关注数据保护，则不应为 Microsoft Edge 启用扩展支持。</span><span class="sxs-lookup"><span data-stu-id="bec7a-119">If an enterprise is concerned about data protection, extensions support should not be enabled for Microsoft Edge.</span></span>

<span data-ttu-id="bec7a-120">若要禁用员工的扩展，请配置组策略和 Microsoft Intune 设置。</span><span class="sxs-lookup"><span data-stu-id="bec7a-120">To disable extensions for employees, configure Group Policy and Microsoft Intune settings.</span></span> <span data-ttu-id="bec7a-121">有关要配置的策略详细信息，请参阅 Microsoft [Edge 的可用策略](https://technet.microsoft.com/itpro/microsoft-edge/available-policies)。</span><span class="sxs-lookup"><span data-stu-id="bec7a-121">For more info on which policies to configure, see [Available policies for Microsoft Edge](https://technet.microsoft.com/itpro/microsoft-edge/available-policies).</span></span>

## <span data-ttu-id="bec7a-122">打包扩展</span><span class="sxs-lookup"><span data-stu-id="bec7a-122">Packaging Extensions</span></span>
<span data-ttu-id="bec7a-123">在企业可以将扩展分发给其员工之前，必须先将其打包。</span><span class="sxs-lookup"><span data-stu-id="bec7a-123">Before an enterprise can distribute an extension to its employees, it must first be packaged.</span></span> <span data-ttu-id="bec7a-124">有关打包扩展的说明，请参阅"打包指南["。](./guides/packaging.md)</span><span class="sxs-lookup"><span data-stu-id="bec7a-124">Instructions on packaging extensions are available in the [Packaging](./guides/packaging.md) guide.</span></span>

> [!TIP]
> <span data-ttu-id="bec7a-125">请确保在所有版本的 Windows 10 上测试安装并运行扩展，以确保在分发之前它按预期工作。</span><span class="sxs-lookup"><span data-stu-id="bec7a-125">Be sure to test installing and running your extension on all the versions of Windows 10 to ensure it will work as expected before distributing.</span></span>

## <span data-ttu-id="bec7a-126">分发扩展</span><span class="sxs-lookup"><span data-stu-id="bec7a-126">Distributing Extensions</span></span>
<span data-ttu-id="bec7a-127">扩展打包后，可以通过 Microsoft Store、适用于 Business 的 Microsoft Store 或旁加载将扩展分发给员工。</span><span class="sxs-lookup"><span data-stu-id="bec7a-127">Once an extension has been packaged, it can be distributed to employees through the Microsoft Store, Microsoft Store for Business, or by sideloading.</span></span>

<span data-ttu-id="bec7a-128">通过适用于企业 Microsoft Store 分发的扩展可以分配给员工，也可以添加到所有员工都可以访问的专用应用商店。</span><span class="sxs-lookup"><span data-stu-id="bec7a-128">Extensions distributed though the Microsoft Store for Business can either be assigned to employees, or added to a private store where all employees can access them.</span></span> <span data-ttu-id="bec7a-129">这可以通过遵循 LOB 应用"业务线" (LOB) [指南](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) 完成。</span><span class="sxs-lookup"><span data-stu-id="bec7a-129">This can be done by following the [Distribute "Line-of-Business" (LOB) apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises) guide.</span></span>

<span data-ttu-id="bec7a-130">若要旁加载扩展， (托管或托管) 必须解锁才能旁加载。</span><span class="sxs-lookup"><span data-stu-id="bec7a-130">To sideload extensions, devices (unmanaged or managed) must be unlocked for sideloading.</span></span> <span data-ttu-id="bec7a-131">请参阅 [Windows 10 中的](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) 旁加载 LOB 应用，详细了解如何旁加载打包的扩展。</span><span class="sxs-lookup"><span data-stu-id="bec7a-131">See [Sideload LOB apps in Windows 10](https://technet.microsoft.com/itpro/windows/deploy/sideload-apps-in-windows-10) for more info on how to sideload packaged extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bec7a-132">如果企业同时在内部开发并分发扩展，则企业将需要适用于企业的 Microsoft Store (或教育) Windows 开发人员门户帐户。</span><span class="sxs-lookup"><span data-stu-id="bec7a-132">If the enterprise is both developing and distributing the extension internally, the enterprise will require both the Microsoft Store for Business (or Education) and a Windows Developer Portal account.</span></span>

### <span data-ttu-id="bec7a-133">旁加载扩展的行为</span><span class="sxs-lookup"><span data-stu-id="bec7a-133">Behavior of Sideloaded Extensions</span></span>
<span data-ttu-id="bec7a-134">与通过 Microsoft Store (或适用于企业) 分发的扩展不同，旁加载的扩展在 Microsoft Edge 中的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="bec7a-134">Unlike extensions distributed through the Microsoft Store (or the Microsoft Store for Business), sideloaded extensions are treated differently in Microsoft Edge.</span></span>

<span data-ttu-id="bec7a-135">第一个差异会影响旁加载扩展在安装后的行为方式。</span><span class="sxs-lookup"><span data-stu-id="bec7a-135">The first difference affects how sideloaded extensions behave after installation.</span></span> <span data-ttu-id="bec7a-136">与 Microsoft Store 中的扩展不同，旁加载的扩展不会立即显示"你有新的扩展"通知，并且需要由用户手动打开。</span><span class="sxs-lookup"><span data-stu-id="bec7a-136">Unlike extensions from the Microsoft Store, sideloaded extensions do not immediately display the "You have a new extension" notification and need to be manually turned on by the user.</span></span>

<span data-ttu-id="bec7a-137">若要打开扩展，请打开"更多 (...) 菜单，选择"扩展"，你应该会看到已安装 扩展列表中的旁加载扩展。</span><span class="sxs-lookup"><span data-stu-id="bec7a-137">To turn on the extension, open the **More (...)** menu, select **"Extensions"** and you should see the sideloaded extension in the list of installed extensions.</span></span> <span data-ttu-id="bec7a-138">单击扩展并打开它。</span><span class="sxs-lookup"><span data-stu-id="bec7a-138">Click on the extension and turn it on.</span></span>

<span data-ttu-id="bec7a-139">第二个差异影响旁加载的扩展在浏览器中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="bec7a-139">The second difference affects how sideloaded extensions appear in the browser.</span></span> <span data-ttu-id="bec7a-140">例如，"你有新的扩展"通知和已安装的扩展的列表都包括一条附加警告，指出该扩展来自未知源。</span><span class="sxs-lookup"><span data-stu-id="bec7a-140">For example, both the "You have a new extension" notification and the list of installed extensions include an additional warning stating that the extension is from an unknown source.</span></span>

![旁加载警告 1](./media/sideload-permissionflyout.PNG)

![旁加载警告 2](./media/sideload-l1warning.PNG)

<span data-ttu-id="bec7a-143">第三个和最后一个差异会影响旁加载扩展在浏览器启动时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="bec7a-143">The third and final difference affects how sideloaded extensions behave on browser startup.</span></span> <span data-ttu-id="bec7a-144">在已加入域或启用了 MDM 的设备上旁加载的扩展的行为将类似于 Microsoft Store 中的扩展。</span><span class="sxs-lookup"><span data-stu-id="bec7a-144">Sideloaded extensions on devices that are either domain-joined or MDM enabled will behave like extensions from the Microsoft Store.</span></span> <span data-ttu-id="bec7a-145">但是，未加入域或启用了 MDM 的设备上旁加载的扩展将在浏览器启动期间关闭，并需要用户执行显式操作。</span><span class="sxs-lookup"><span data-stu-id="bec7a-145">However, sideloaded extensions on devices that are not domain-joined or MDM enabled will be turned off during browser startup and require the user to take explicit action.</span></span>

<span data-ttu-id="bec7a-146">浏览器启动后 (在大约 10 秒的不活动状态) 下面的通知将显示在窗口底部附近。</span><span class="sxs-lookup"><span data-stu-id="bec7a-146">Shortly after browser startup (after ~10 seconds of inactivity) the following notification will appear near the bottom of the window.</span></span>

![旁加载通知](./media/sideload-scareUI.PNG)

<span data-ttu-id="bec7a-148">每次启动 Microsoft Edge 时，用户都需要选择"继续启用"才能使用扩展。</span><span class="sxs-lookup"><span data-stu-id="bec7a-148">Each time Microsoft Edge is launched, users will need to select "Turn on anyway" in order to use the extension.</span></span>
