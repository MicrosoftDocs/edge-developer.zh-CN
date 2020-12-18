---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: 了解如何使用 ManifoldJS（一款开源工具）Node.js Microsoft Edge 扩展。
title: 使用 ManifoldJS 打包扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 151a8b2ababb25e0964a6fbc2696b5fdc059d084
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232593"
---
# <span data-ttu-id="57c04-104">使用 ManifoldJS 创建扩展 AppX 程序包</span><span class="sxs-lookup"><span data-stu-id="57c04-104">Using ManifoldJS to create extension AppX packages</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="57c04-105">ManifoldJS 是一个开源Node.js工具，可让你快速轻松地创建一个程序包，然后可用于提交到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="57c04-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span></span>  

<span data-ttu-id="57c04-106">如果在扩展中使用本机消息传递，应跳过以下文章并转到 [Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) 中的本机消息传递，以打包指令。</span><span class="sxs-lookup"><span data-stu-id="57c04-106">If you use native messaging in your extension, you should skip the following article and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span></span>  

<span data-ttu-id="57c04-107">在开始使用之前，你仍然需要阅读以下文章。</span><span class="sxs-lookup"><span data-stu-id="57c04-107">Before getting started, you will still need to read up on the following articles.</span></span>  

*   [<span data-ttu-id="57c04-108">Windows 开发人员中心扩展</span><span class="sxs-lookup"><span data-stu-id="57c04-108">Extensions in the Windows Dev Center</span></span>](./extensions-in-the-windows-dev-center.md)  
*   [<span data-ttu-id="57c04-109">本地化扩展包</span><span class="sxs-lookup"><span data-stu-id="57c04-109">Localizing extension packages</span></span>](./localizing-extension-packages.md)  

> [!NOTE]
> <span data-ttu-id="57c04-110">将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。</span><span class="sxs-lookup"><span data-stu-id="57c04-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="57c04-111">创建、打包和测试扩展后，请在扩展提交表单上 [提交请求](https://developer.microsoft.com/microsoft-edge/extensions/requests)。</span><span class="sxs-lookup"><span data-stu-id="57c04-111">Once you have created, packaged and tested your extension, please submit a request on our [extension submission form](https://developer.microsoft.com/microsoft-edge/extensions/requests).</span></span>  

## <span data-ttu-id="57c04-112">安装 Node.js 和 ManifoldJS</span><span class="sxs-lookup"><span data-stu-id="57c04-112">Installing Node.js and ManifoldJS</span></span>  

<span data-ttu-id="57c04-113">需要执行的第一个操作是安装[LTSNode.js LTS。](https://nodejs.org/en/download)</span><span class="sxs-lookup"><span data-stu-id="57c04-113">The first things you will need to do is install [Node.js LTS](https://nodejs.org/en/download).</span></span>  
<span data-ttu-id="57c04-114">拥有 Node 后，从命令行 (最好是 PowerShell) ，运行以下命令以安装 ManifoldJS。</span><span class="sxs-lookup"><span data-stu-id="57c04-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS.</span></span>  

```shell
npm install -g manifoldjs
```  

<span data-ttu-id="57c04-115">若要验证是否正确安装了 ManifoldJS，请 `manifoldjs` 从命令行运行。</span><span class="sxs-lookup"><span data-stu-id="57c04-115">To verify that you have correctly installed ManifoldJS, run `manifoldjs` from the command line.</span></span> <span data-ttu-id="57c04-116">如果 ManifoldJS 无法识别，请 `%APPDATA%\npm` 添加到 PATH 变量中。</span><span class="sxs-lookup"><span data-stu-id="57c04-116">If ManifoldJS was not recognized, add `%APPDATA%\npm` to your PATH variables.</span></span>  

## <span data-ttu-id="57c04-117">使用 ManifoldJS 打包</span><span class="sxs-lookup"><span data-stu-id="57c04-117">Packaging with ManifoldJS</span></span>  

<span data-ttu-id="57c04-118">若要开始打包过程，需要打开命令行，将目录更改为将成为打包扩展目标的文件夹。</span><span class="sxs-lookup"><span data-stu-id="57c04-118">To start the packaging process, you will need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span></span>  

<span data-ttu-id="57c04-119">例如：</span><span class="sxs-lookup"><span data-stu-id="57c04-119">For example:</span></span>

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> <span data-ttu-id="57c04-120">`manifoldjs`该命令在当前目录中输出并覆盖内容。</span><span class="sxs-lookup"><span data-stu-id="57c04-120">The `manifoldjs` command outputs in the current directory and overwrites content.</span></span>  

<span data-ttu-id="57c04-121">现在，你已在你的目标文件夹中，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="57c04-121">Now that you are in your destination folder, run the following command.</span></span>  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

<span data-ttu-id="57c04-122">该命令 `mainifoldjs` 可细分为以下部分。</span><span class="sxs-lookup"><span data-stu-id="57c04-122">The `mainifoldjs` command can be broken down into the following parts.</span></span>  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="57c04-123">更改日志级别 `debug` 以完全打印。</span><span class="sxs-lookup"><span data-stu-id="57c04-123">Changes the log level to `debug` to get a full print out.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="57c04-124">将运行转换的唯一平台设置到 `edgeextension` 。</span><span class="sxs-lookup"><span data-stu-id="57c04-124">Sets the only platform to run the conversion on to `edgeextension`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="57c04-125">告知程序清单的格式是一种格式，而不要关心 `edgeextension` 其是否未通过验证。</span><span class="sxs-lookup"><span data-stu-id="57c04-125">Tells the program that the format of the manifest is an `edgeextension` format and not to care if it fails validation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-m \path\to\manifest.json`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="57c04-126">要转换的扩展清单的路径。</span><span class="sxs-lookup"><span data-stu-id="57c04-126">The path to the extension manifest that you want to convert.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="57c04-127">ManifoldJS 运行完成后，你将有一个包含以下内容的文件夹。</span><span class="sxs-lookup"><span data-stu-id="57c04-127">After ManifoldJS has finished running, you will have a folder with the following contents.</span></span>  

```text
┌ My Extension
└┬ edgeextension
 ├- generationInfo.json
 └┬ manifest
  ├- appxmanifest.xml
  ├┬ Assets
  |├- Square150x150Logo.png
  |├- Square44x44Logo.png
  |└- StoreLogo.png    
  └┬ Extension
   ├- manifest.json
   └- popup.html
```  
<!-- 
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
-->  

<span data-ttu-id="57c04-128">文件generationInfo.js是运行 ManifoldJS 生成的日志，不会包含在扩展包中。</span><span class="sxs-lookup"><span data-stu-id="57c04-128">The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package.</span></span> <span data-ttu-id="57c04-129">仅打包文件夹 `manifest` 的内容。</span><span class="sxs-lookup"><span data-stu-id="57c04-129">Only the contents of the `manifest` folder will be packaged.</span></span> <span data-ttu-id="57c04-130">在清单文件夹中，Assets 文件夹包含将在 Windows 和 Microsoft Store UI 中使用的图像，而扩展文件夹包含扩展的内容。</span><span class="sxs-lookup"><span data-stu-id="57c04-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span></span>  

<span data-ttu-id="57c04-131">现在你拥有正确的文件，你将需要编辑文件夹中生成的 AppXManifest `manifest` 文件。</span><span class="sxs-lookup"><span data-stu-id="57c04-131">Now that you have the correct files, you will need to edit the generated AppXManifest file within the `manifest` folder.</span></span> <span data-ttu-id="57c04-132">如果扩展名manifest.js文件上具有"name"字段的国际化字符串，则一旦 ManifoldJS 运行，最顶层文件夹的名称将没有下划线，并包括"MSG"。</span><span class="sxs-lookup"><span data-stu-id="57c04-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span></span>

<span data-ttu-id="57c04-133">例如，在manifest.js字段的文件上创建 `"name"` 一个字段。</span><span class="sxs-lookup"><span data-stu-id="57c04-133">For example, a manifest.json file with the following `"name"` field.</span></span>  

```shell
"name" : "__MSG_appName__"
```  

<span data-ttu-id="57c04-134">将具有一个清单文件夹，该文件夹在 `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` 。</span><span class="sxs-lookup"><span data-stu-id="57c04-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span></span>  

<span data-ttu-id="57c04-135">在 AppXManifest 文件中，将需要：</span><span class="sxs-lookup"><span data-stu-id="57c04-135">In the AppXManifest file, you will need to:</span></span>  

 *   <span data-ttu-id="57c04-136">替换所需的 Identity 字段和 PublisherDisplayName 字段，如此处 [所述](./creating-and-testing-extension-packages.md#app-identity-template-values)。</span><span class="sxs-lookup"><span data-stu-id="57c04-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span></span> <span data-ttu-id="57c04-137">请注意，如果你仅打包用于测试或企业分发，可以使用占位符值，而不是注册 Windows 开发人员中心帐户。</span><span class="sxs-lookup"><span data-stu-id="57c04-137">Note that if you are only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span></span>  
 *   <span data-ttu-id="57c04-138">将"资源"文件夹中的占位符图标替换为扩展的图标，其大小 (150x150、50x50、44x44) 和名称。</span><span class="sxs-lookup"><span data-stu-id="57c04-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span></span> <span data-ttu-id="57c04-139">有关 [使用这些](./../design.md#icons-for-packaging) 图标的信息，请参阅设计指南。</span><span class="sxs-lookup"><span data-stu-id="57c04-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span></span>  
 *   <span data-ttu-id="57c04-140">如果扩展已本地化，请按照整个 [本地化 Microsoft Edge 扩展指南](./localizing-extension-packages.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="57c04-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span></span> <span data-ttu-id="57c04-141">如果未本地化，则只读取 [Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 部分中的本地化名称和说明。</span><span class="sxs-lookup"><span data-stu-id="57c04-141">If it is not localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span></span>  

<span data-ttu-id="57c04-142">整理 `appxmanifest.xml` 文件后，运行以下命令以创建程序包。</span><span class="sxs-lookup"><span data-stu-id="57c04-142">Once your `appxmanifest.xml` file is sorted out, run the following command to create your package.</span></span>  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

<span data-ttu-id="57c04-143">你的程序包现在将位于 edgeextension 文件夹内的程序包文件夹中。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="57c04-143">Your package will now be in the **package** folder located within the edgeextension folder.</span></span> <span data-ttu-id="57c04-144">若要详细了解如何旁加载新程序包，请参阅"创建和测试扩展[](./creating-and-testing-extension-packages.md#testing-an-appx-package)包的测试"部分。</span><span class="sxs-lookup"><span data-stu-id="57c04-144">For more information about how to sideload your new package, see [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing extension packages.</span></span>  

<span data-ttu-id="57c04-145">测试程序包后，请随时在我们的扩展提交表单上提交请求，以考虑将其[](https://aka.ms/extension-request)发布到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="57c04-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span></span>  
