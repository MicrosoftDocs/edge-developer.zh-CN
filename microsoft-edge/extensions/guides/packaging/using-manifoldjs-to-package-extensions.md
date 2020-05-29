---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: 了解如何使用 ManifoldJS （node.js open source）工具将你的 Microsoft Edge 扩展打包到一个 snap 中。
title: 使用 ManifoldJS 打包扩展名
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: cca83a26c9f80eca6454e3b5b329f72a7491b6e2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563240"
---
# <span data-ttu-id="3f1e1-104">使用 ManifoldJS 创建扩展 AppX 程序包</span><span class="sxs-lookup"><span data-stu-id="3f1e1-104">Using ManifoldJS to create extension AppX packages</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="3f1e1-105">ManifoldJS 是一种开放的源节点 .js 工具，可让你快速轻松地创建可用于提交到 Microsoft Store 的程序包。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span></span>

<span data-ttu-id="3f1e1-106">如果你在扩展中使用本机消息，则应跳过此操作，并转到[Microsoft Edge 中](../native-messaging.md#creating-an-extension-with-native-messaging)用于打包说明的本机消息。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-106">If you use native messaging in your extension, you should skip this and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span></span> 

<span data-ttu-id="3f1e1-107">在开始之前，您仍需要阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-107">Before getting started, you will still need to read up on the following articles:</span></span>

- [<span data-ttu-id="3f1e1-108">Windows 开发人员中心中的扩展</span><span class="sxs-lookup"><span data-stu-id="3f1e1-108">Extensions in the Windows Dev Center</span></span>](./extensions-in-the-windows-dev-center.md)
- [<span data-ttu-id="3f1e1-109">本地化扩展程序包</span><span class="sxs-lookup"><span data-stu-id="3f1e1-109">Localizing extension packages</span></span>](./localizing-extension-packages.md)

> [!NOTE]
> <span data-ttu-id="3f1e1-110">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span> <span data-ttu-id="3f1e1-111">创建、打包和测试扩展后，请提交我们的[扩展提交表单](https://aka.ms/extension-request)上的申请。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-111">Once you've created, packaged and tested your extension, please submit a request on our [extension submission form](https://aka.ms/extension-request).</span></span>


## <span data-ttu-id="3f1e1-112">安装 node.js 和 ManifoldJS</span><span class="sxs-lookup"><span data-stu-id="3f1e1-112">Installing Node.js and ManifoldJS</span></span>

<span data-ttu-id="3f1e1-113">您需要做的第一件工作是安装[NODE.JS LTS](https://nodejs.org/en/download/)。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-113">The first things you'll need to do is install [Node.js LTS](https://nodejs.org/en/download/).</span></span>
<span data-ttu-id="3f1e1-114">一旦拥有节点，从命令行（最好是 PowerShell）中，运行以下命令以安装 ManifoldJS：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS:</span></span>

`npm install -g manifoldjs`

<span data-ttu-id="3f1e1-115">若要验证是否已正确安装 ManifoldJS，请 `manifoldjs` 从命令行运行。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-115">To verify that you've correctly installed ManifoldJS, run `manifoldjs` from the command line.</span></span> <span data-ttu-id="3f1e1-116">如果 ManifoldJS 无法识别，请将 `%APPDATA%\npm` 其添加到路径变量。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-116">If ManifoldJS wasn't recognized, add `%APPDATA%\npm` to your PATH variables.</span></span>

## <span data-ttu-id="3f1e1-117">用 ManifoldJS 打包</span><span class="sxs-lookup"><span data-stu-id="3f1e1-117">Packaging with ManifoldJS</span></span>

<span data-ttu-id="3f1e1-118">若要启动打包过程，你需要打开命令行并将目录更改为打包扩展的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-118">To start the packaging process, you'll need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span></span>

<span data-ttu-id="3f1e1-119">例如：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-119">For example:</span></span>

`cd C:\manifoldJSTest`

> [!NOTE]
> <span data-ttu-id="3f1e1-120">ManifoldJS 将输出到当前目录，并且可以覆盖内容。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-120">ManifoldJS will output in the current directory and can overwrite content.</span></span>



<span data-ttu-id="3f1e1-121">现在你位于目标文件夹中，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-121">Now that you're in your destination folder, run the following command:</span></span>

`manifoldjs -l debug -p edgeextension -f edgeextension -m <EXTENSION LOCATION>\manifest.json`


<span data-ttu-id="3f1e1-122">此命令可分为以下部分：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-122">This command can be broken down into the following parts:</span></span>
 -    <span data-ttu-id="3f1e1-123">**-l 调试**：将日志级别更改为 "调试" 以获得完整打印。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-123">**-l debug**: Changes the log level to "debug" to get a full print out.</span></span>
 -    <span data-ttu-id="3f1e1-124">**-p edgeextension**：设置要在 edgeextension 上运行转换的唯一平台。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-124">**-p edgeextension**: Sets the only platform to run the conversion on to edgeextension.</span></span>
 -    <span data-ttu-id="3f1e1-125">**-f edgeextension**：通知程序清单格式为 edgeextension 格式，而不是在验证失败的情况中。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-125">**-f edgeextension**: Tells the program that the format of the manifest is an edgeextension format and not to care if it fails validation.</span></span>
 -    <span data-ttu-id="3f1e1-126">**-m \ < 扩展位置 > \manifest.json**：要转换的扩展清单的路径。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-126">**-m \<EXTENSION LOCATION>\manifest.json**: The path to the extension manifest that you want to convert.</span></span>


<span data-ttu-id="3f1e1-127">在 ManifoldJS 完成运行后，你将拥有一个具有下列内容的文件夹：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-127">After ManifoldJS has finished running, you'll have a folder with the following contents:</span></span>

    My Extension
        edgeextension
            generationInfo.json
            manifest
                   appxmanifest.xml
                Assets
                    Square150x150Logo.png
                    Square44x44Logo.png
                    StoreLogo.png    
                Extension
                    manifest.json
                    popup.html
                    ...
                ...

<span data-ttu-id="3f1e1-128">GenerationInfo 文件是通过运行 ManifoldJS 生成的日志，不会包含在扩展程序包中。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-128">The generationInfo.json file is a log produced by running ManifoldJS and won't be included in your extension package.</span></span> <span data-ttu-id="3f1e1-129">将仅打包**清单**文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-129">Only the contents of the **manifest** folder will be packaged.</span></span> <span data-ttu-id="3f1e1-130">在清单文件夹中，资源文件夹包含将在 Windows 和 Microsoft Store UI 中使用的图像，而扩展文件夹中包含您的扩展的内容。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span></span>


<span data-ttu-id="3f1e1-131">既然你拥有正确的文件，你将需要在**清单**文件夹中编辑生成的 package.appxmanifest 文件。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-131">Now that you have the correct files, you'll need to edit the generated AppXManifest file within the **manifest** folder.</span></span> <span data-ttu-id="3f1e1-132">如果扩展的清单 json 文件具有 "名称" 字段的国际化字符串，则在 ManifoldJS 运行后，最上层文件夹的名称将没有下划线并包含 "MSG"。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span></span>

<span data-ttu-id="3f1e1-133">例如，具有以下字段的清单 json 文件 `"name"` ：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-133">For example, a manifest.json file with the following `"name"` field:</span></span>

`"name" : "__MSG_appName__"`

<span data-ttu-id="3f1e1-134">将拥有一个属于的清单文件夹 `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` 。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span></span>

<span data-ttu-id="3f1e1-135">在 Package.appxmanifest 文件中，你需要：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-135">In the AppXManifest file, you'll need to:</span></span>
 -    <span data-ttu-id="3f1e1-136">按[此处](./creating-and-testing-extension-packages.md#app-identity-template-values)所述替换所需的标识字段和 PublisherDisplayName 字段。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span></span> <span data-ttu-id="3f1e1-137">请注意，如果仅出于测试目的或企业分发进行打包，则可以使用占位符值，而不是注册 Windows 开发人员中心帐户。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-137">Note that if you're only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span></span>
 -    <span data-ttu-id="3f1e1-138">将 "资源" 文件夹中的占位符图标替换为具有相同大小（150x150、50x50、44x44）和名称的扩展名的图标。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span></span> <span data-ttu-id="3f1e1-139">有关这些图标的使用位置的信息，请参阅[设计](./../design.md#icons-for-packaging)指南。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span></span>
 - <span data-ttu-id="3f1e1-140">如果您的扩展已本地化，请遵循整个 "[本地化 Microsoft Edge 扩展](./localizing-extension-packages.md)指南"。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span></span> <span data-ttu-id="3f1e1-141">如果未本地化，请仅阅读[Microsoft Store 部分中的本地化名称和说明](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store)。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-141">If it isn't localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span></span>

<span data-ttu-id="3f1e1-142">Package.appxmanifest 文件被排序后，请运行以下命令创建程序包：</span><span class="sxs-lookup"><span data-stu-id="3f1e1-142">Once your appxmanifest.xml file is sorted out, run the following command to create your package:</span></span>

`manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\`

<span data-ttu-id="3f1e1-143">您的程序包现在将位于 edgeextension 文件夹中的**程序包**文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-143">Your package will now be in the **package** folder located within the edgeextension folder.</span></span> <span data-ttu-id="3f1e1-144">有关如何旁加载新程序包的信息，请参阅创建和测试扩展程序包 "[测试](./creating-and-testing-extension-packages.md#testing-an-appx-package)" 部分。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-144">See Creating and testing extension packages' [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section for info on how to sideload your new package.</span></span>

<span data-ttu-id="3f1e1-145">一旦您的软件包经过测试，就可以在我们的[扩展提交表单](https://aka.ms/extension-request)上提交请求，以便将其提交到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="3f1e1-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span></span>
