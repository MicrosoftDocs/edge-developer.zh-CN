---
description: 了解 Windows 应用认证工具包。 这将使您的扩展更好地获得发布。
title: 扩展-运行 Windows 应用认证工具包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 2577d4e5d05dbe55e57b046d001d122a687f87ce
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563246"
---
# <span data-ttu-id="03afb-105">运行 Windows 应用认证工具包</span><span class="sxs-lookup"><span data-stu-id="03afb-105">Running the Windows App Certification Kit</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="03afb-106">若要提高将扩展发布到 Microsoft Store 的可能性，需要安装并运行 [Windows 应用认证工具包](https://go.microsoft.com/fwlink/p/?LinkID=309666)。</span><span class="sxs-lookup"><span data-stu-id="03afb-106">To improve the chances of your extension getting published to the Microsoft Store, you'll need to install and run the [Windows App Certification Kit](https://go.microsoft.com/fwlink/p/?LinkID=309666).</span></span>
<span data-ttu-id="03afb-107">这将在扩展程序包上运行一 [系列测试](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit-tests) ，以确保它可以用于 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="03afb-107">This runs a [series of tests](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit-tests) on your extension package to ensure that it's ready for the Microsoft Store.</span></span>

> [!NOTE]
> <span data-ttu-id="03afb-108">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。</span><span class="sxs-lookup"><span data-stu-id="03afb-108">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="03afb-109">创建、打包和测试扩展后，请提交我们的 [扩展提交表单](https://aka.ms/extension-request)上的申请。</span><span class="sxs-lookup"><span data-stu-id="03afb-109">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>

<span data-ttu-id="03afb-110">了解如何使用工具包之前，请确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="03afb-110">Before learning about how to use the kit, make sure you meet the following prerequisites:</span></span> 

- <span data-ttu-id="03afb-111">必须安装并运行 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="03afb-111">You must install and run Windows 10.</span></span>
- <span data-ttu-id="03afb-112">必须安装 [Windows 应用认证工具包版本 10](https://go.microsoft.com/fwlink/p/?LinkID=309666)，该版本包含在适用于 Windows 10 的 Windows 软件开发工具包 (SDK) 中。</span><span class="sxs-lookup"><span data-stu-id="03afb-112">You must install [Windows App Certification Kit version 10](https://go.microsoft.com/fwlink/p/?LinkID=309666), which is included in the Windows Software Development Kit (SDK) for Windows 10.</span></span>
- <span data-ttu-id="03afb-113">必须[启用设备进行开发](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development)。</span><span class="sxs-lookup"><span data-stu-id="03afb-113">You must [enable your device for development](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development).</span></span>
- <span data-ttu-id="03afb-114">您必须拥有 [打包](../packaging.md) 的扩展。</span><span class="sxs-lookup"><span data-stu-id="03afb-114">You must have a [packaged](../packaging.md) extension.</span></span>


<span data-ttu-id="03afb-115">如果满足先决条件，请参阅 [Windows 应用认证工具包](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit#validate-your-windows-app-using-the-windows-app-certification-kit-interactively) 文档，了解有关如何使用 Windows 应用认证工具包交互或使用命令行测试扩展的信息。</span><span class="sxs-lookup"><span data-stu-id="03afb-115">If you meet the prerequisites, see the [Windows App Certification Kit](https://docs.microsoft.com/windows/uwp/debug-test-perf/windows-app-certification-kit#validate-your-windows-app-using-the-windows-app-certification-kit-interactively) documentation for info on how to use the Windows App Certification Kit either interactively or with the command line to test your extension.</span></span>
