---
description: 了解如何添加和删除扩展，以及如何移动地址栏旁边的扩展按钮。
title: 添加和删除扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、扩展
ms.custom: seodec18
localization_priority: Priority
ms.openlocfilehash: fdc6950962e7ce7e0a720d0bafa7e2c63ebd7098
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563297"
---
# <span data-ttu-id="3efda-104">添加、移动和删除 Microsoft Edge 的扩展</span><span class="sxs-lookup"><span data-stu-id="3efda-104">Adding, moving, and removing extensions for Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="3efda-105">**Windows 10 周年更新**中引入了 Microsoft Edge 扩展支持。</span><span class="sxs-lookup"><span data-stu-id="3efda-105">Microsoft Edge support for extensions was introduced in the **Windows 10 Anniversary Update**.</span></span> <span data-ttu-id="3efda-106">如果你正在开发 Microsoft Edge 扩展并且想要将其加载，或者你已有且现在想要删除它，请查看下面的步骤。</span><span class="sxs-lookup"><span data-stu-id="3efda-106">If you're developing a Microsoft Edge extension and want to load it up, or if you already have and now want to remove it, check out the steps below.</span></span>
<span data-ttu-id="3efda-107">还包括有关如何在浏览器中更改扩展图标位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efda-107">Also included are details on how to change your extension icon's location in the browser.</span></span>

## <span data-ttu-id="3efda-108">添加扩展</span><span class="sxs-lookup"><span data-stu-id="3efda-108">Adding an extension</span></span>

1. <span data-ttu-id="3efda-109">打开 "Microsoft Edge"，然后在地址栏中键入 "关于：标志"。</span><span class="sxs-lookup"><span data-stu-id="3efda-109">Open Microsoft Edge and type 'about:flags' into the address bar.</span></span>

2. <span data-ttu-id="3efda-110">选中 "**启用扩展开发人员功能**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="3efda-110">Select the **Enable extension developer features** checkbox.</span></span>

   ![关于：标志打开开发人员功能](./../media/sideload-aboutflags.png)
   > [!NOTE]
   > <span data-ttu-id="3efda-112">如果您没有 Windows 10 周年更新或更高版本，此选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="3efda-112">If you don't have the Windows 10 Anniversary Update or later, this option will not be available.</span></span>

3. <span data-ttu-id="3efda-113">选择 "**更多" （...）** 以打开菜单。</span><span class="sxs-lookup"><span data-stu-id="3efda-113">Select **More (...)** to open the menu.</span></span>

   !["更多" 按钮](./../media/morebutton.png)  

4. <span data-ttu-id="3efda-115">从菜单中选择 "**扩展**"。</span><span class="sxs-lookup"><span data-stu-id="3efda-115">Select **Extensions** from the menu.</span></span>

5. <span data-ttu-id="3efda-116">选择 "**加载扩展**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3efda-116">Select the **Load extension** button.</span></span>

   ![选择加载扩展](./../media/sideload-load-extension.png)

6. <span data-ttu-id="3efda-118">导航到您的扩展的文件夹，然后选择 "**选择文件夹**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3efda-118">Navigate to your extension's folder and select the  **Select folder** button.</span></span>
   ![选择要加载的扩展文件夹](./../media/sideload-select-extension.png)
   > [!NOTE]
   > <span data-ttu-id="3efda-120">如果您在加载扩展时遇到错误消息，请参阅[疑难解答](./../troubleshooting.md)页面获取指南。</span><span class="sxs-lookup"><span data-stu-id="3efda-120">If you encounter an error message when loading your extension, refer to the [troubleshooting](./../troubleshooting.md) page for guidance.</span></span>


**<span data-ttu-id="3efda-121">一切就绪！</span><span class="sxs-lookup"><span data-stu-id="3efda-121">You're all set!</span></span> <span data-ttu-id="3efda-122">现在，你应该可以看到 Microsoft Edge 的扩展窗格中列出的扩展。</span><span class="sxs-lookup"><span data-stu-id="3efda-122">You should now see the extension listed in Microsoft Edge's extension pane.</span></span>**

![扩展窗格中的扩展](./../media/sideload-extension-installed.png)

> [!NOTE]
> <span data-ttu-id="3efda-124">在随后启动 Microsoft Edge 时，未签名的扩展将自动关闭。</span><span class="sxs-lookup"><span data-stu-id="3efda-124">Unsigned extensions are automatically turned off on subsequent launches of Microsoft Edge.</span></span> <span data-ttu-id="3efda-125">当浏览器进入空闲状态时（大约10秒钟的非活动时间），你将在窗口底部看到以下通知。</span><span class="sxs-lookup"><span data-stu-id="3efda-125">When the browser enters an idle state (after approximately 10 seconds of inactivity) you will see the following notification at the bottom of the window.</span></span> ![<span data-ttu-id="3efda-126">危险通知](./../media/riskynotification.png)若要打开未签名的扩展，请单击 "仍然启用"。</span><span class="sxs-lookup"><span data-stu-id="3efda-126">risky notification](./../media/riskynotification.png) To turn on the unsigned extensions, click "Turn on anyway".</span></span>



## <span data-ttu-id="3efda-127">移动 "扩展" 按钮</span><span class="sxs-lookup"><span data-stu-id="3efda-127">Moving the extension button</span></span>
<span data-ttu-id="3efda-128">根据扩展的设置，它可能会显示在 "**更多（...）** " 菜单中。</span><span class="sxs-lookup"><span data-stu-id="3efda-128">Depending on your extension's settings, it could appear in the **More (...)** menu.</span></span>

   ![操作菜单](./../media/browseraction.png)  


<span data-ttu-id="3efda-130">如果想要将按钮移出此菜单，以便更轻松地访问：</span><span class="sxs-lookup"><span data-stu-id="3efda-130">If you want to move the button out of this menu for easier access:</span></span>

1. <span data-ttu-id="3efda-131">右键单击 "扩展" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3efda-131">Right-click the extension button.</span></span>

2. <span data-ttu-id="3efda-132">选择 "**地址栏" 旁边**的 "显示" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3efda-132">Select **Show button next to address bar**.</span></span>

   ![操作菜单](./../media/browseraction_contextmenu.png)  

<span data-ttu-id="3efda-134">或者，您也可以从 "扩展详细信息" 页面执行此操作：</span><span class="sxs-lookup"><span data-stu-id="3efda-134">Alternatively, you may do this from the extensions details page:</span></span>

1. <span data-ttu-id="3efda-135">单击 "扩展" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3efda-135">Click on the extension button.</span></span>
2. <span data-ttu-id="3efda-136">将 "**地址栏" 旁边**的 "显示" 按钮切换到 "开"。</span><span class="sxs-lookup"><span data-stu-id="3efda-136">Toggle **Show button next to address bar** to on.</span></span>

   ![显示按钮切换打开](./../media/show-button-toggle.png)

> [!NOTE]
> <span data-ttu-id="3efda-138">您始终可以通过右键单击，然后转到 "**地址栏" 旁边**的 "取消选中"，或者转到 "扩展详细信息" 页面，并转到 "**地址栏" 旁边**的 "显示" 按钮，将按钮移回 "**更多（...）** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="3efda-138">You can always move the button back to the **More (...)** menu by right-clicking it and unselecting **Show next to address bar** or by going to the extension details page and toggling **Show button next to address bar** to off.</span></span>


## <span data-ttu-id="3efda-139">删除扩展</span><span class="sxs-lookup"><span data-stu-id="3efda-139">Removing an extension</span></span>

1. <span data-ttu-id="3efda-140">打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3efda-140">Open Microsoft Edge.</span></span>

2. <span data-ttu-id="3efda-141">选择 "**更多" （...）** 以打开菜单。</span><span class="sxs-lookup"><span data-stu-id="3efda-141">Select **More (...)** to open the menu.</span></span>

3. <span data-ttu-id="3efda-142">从菜单中选择 "**扩展**"。</span><span class="sxs-lookup"><span data-stu-id="3efda-142">Select **Extensions** from the menu.</span></span>

4. <span data-ttu-id="3efda-143">右键单击要删除的扩展名，然后选择 "**删除**"，或选择该扩展名，然后单击 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3efda-143">Right-click the extension you want to remove and select **Remove**, or select the extension and click the **Remove** button.</span></span>

   ![操作菜单](./../media/remove.png)  

**<span data-ttu-id="3efda-145">该扩展将从 Microsoft Edge 中的列表中消失。</span><span class="sxs-lookup"><span data-stu-id="3efda-145">The extension should disappear from the list in Microsoft Edge.</span></span>**
