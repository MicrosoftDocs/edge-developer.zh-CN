---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: See how to package your Microsoft Edge extension in a snap with ManifoldJS, the Node.js open source tool.
title: Using ManifoldJS to package extensions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.custom: seodec18
ms.openlocfilehash: 83aa57ae0e4ae302b1360be50e5158782b6fbb76
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986204"
---
# <span data-ttu-id="749b8-104">Using ManifoldJS to create extension AppX packages</span><span class="sxs-lookup"><span data-stu-id="749b8-104">Using ManifoldJS to create extension AppX packages</span></span>  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

<span data-ttu-id="749b8-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="749b8-105">ManifoldJS is an open source Node.js tool that allows you to quickly and painlessly create a package that you can then use for submission to the Microsoft Store.</span></span>  

<span data-ttu-id="749b8-106">If you use native messaging in your extension, you should skip the following article and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span><span class="sxs-lookup"><span data-stu-id="749b8-106">If you use native messaging in your extension, you should skip the following article and go to [Native messaging in Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) for packaging instruction.</span></span>  

<span data-ttu-id="749b8-107">Before getting started, you will still need to read up on the following articles.</span><span class="sxs-lookup"><span data-stu-id="749b8-107">Before getting started, you will still need to read up on the following articles.</span></span>  

*   [<span data-ttu-id="749b8-108">Extensions in the Windows Dev Center</span><span class="sxs-lookup"><span data-stu-id="749b8-108">Extensions in the Windows Dev Center</span></span>](./extensions-in-the-windows-dev-center.md)  
*   [<span data-ttu-id="749b8-109">Localizing extension packages</span><span class="sxs-lookup"><span data-stu-id="749b8-109">Localizing extension packages</span></span>](./localizing-extension-packages.md)  

> [!NOTE]
> <span data-ttu-id="749b8-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span><span class="sxs-lookup"><span data-stu-id="749b8-110">Submitting a Microsoft Edge extension to the Microsoft Store is currently a restricted capability.</span></span>  <span data-ttu-id="749b8-111">Once you have created, packaged and tested your extension, please submit a request on our [extension submission form](https://developer.microsoft.com/microsoft-edge/extensions/requests).</span><span class="sxs-lookup"><span data-stu-id="749b8-111">Once you have created, packaged and tested your extension, please submit a request on our [extension submission form](https://developer.microsoft.com/microsoft-edge/extensions/requests).</span></span>  

## <span data-ttu-id="749b8-112">Installing Node.js and ManifoldJS</span><span class="sxs-lookup"><span data-stu-id="749b8-112">Installing Node.js and ManifoldJS</span></span>  

<span data-ttu-id="749b8-113">The first things you will need to do is install [Node.js LTS](https://nodejs.org/en/download).</span><span class="sxs-lookup"><span data-stu-id="749b8-113">The first things you will need to do is install [Node.js LTS](https://nodejs.org/en/download).</span></span>  
<span data-ttu-id="749b8-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS.</span><span class="sxs-lookup"><span data-stu-id="749b8-114">Once you have Node, from a command line (preferably PowerShell), run the following command to install ManifoldJS.</span></span>  

```shell
npm install -g manifoldjs
```  

<span data-ttu-id="749b8-115">To verify that you have correctly installed ManifoldJS, run `manifoldjs` from the command line.</span><span class="sxs-lookup"><span data-stu-id="749b8-115">To verify that you have correctly installed ManifoldJS, run `manifoldjs` from the command line.</span></span> <span data-ttu-id="749b8-116">If ManifoldJS was not recognized, add `%APPDATA%\npm` to your PATH variables.</span><span class="sxs-lookup"><span data-stu-id="749b8-116">If ManifoldJS was not recognized, add `%APPDATA%\npm` to your PATH variables.</span></span>  

## <span data-ttu-id="749b8-117">Packaging with ManifoldJS</span><span class="sxs-lookup"><span data-stu-id="749b8-117">Packaging with ManifoldJS</span></span>  

<span data-ttu-id="749b8-118">To start the packaging process, you will need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span><span class="sxs-lookup"><span data-stu-id="749b8-118">To start the packaging process, you will need to open a command line and change directories to a folder that will be the destination for your packaged extension.</span></span>  

<span data-ttu-id="749b8-119">For example:</span><span class="sxs-lookup"><span data-stu-id="749b8-119">For example:</span></span>

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> <span data-ttu-id="749b8-120">The `manifoldjs` command outputs in the current directory and overwrites content.</span><span class="sxs-lookup"><span data-stu-id="749b8-120">The `manifoldjs` command outputs in the current directory and overwrites content.</span></span>  

<span data-ttu-id="749b8-121">Now that you are in your destination folder, run the following command.</span><span class="sxs-lookup"><span data-stu-id="749b8-121">Now that you are in your destination folder, run the following command.</span></span>  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

<span data-ttu-id="749b8-122">The `mainifoldjs` command can be broken down into the following parts.</span><span class="sxs-lookup"><span data-stu-id="749b8-122">The `mainifoldjs` command can be broken down into the following parts.</span></span>  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="749b8-123">Changes the log level to `debug` to get a full print out.</span><span class="sxs-lookup"><span data-stu-id="749b8-123">Changes the log level to `debug` to get a full print out.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="749b8-124">Sets the only platform to run the conversion on to `edgeextension`.</span><span class="sxs-lookup"><span data-stu-id="749b8-124">Sets the only platform to run the conversion on to `edgeextension`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="749b8-125">Tells the program that the format of the manifest is an `edgeextension` format and not to care if it fails validation.</span><span class="sxs-lookup"><span data-stu-id="749b8-125">Tells the program that the format of the manifest is an `edgeextension` format and not to care if it fails validation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-m \path\to\manifest.json`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="749b8-126">The path to the extension manifest that you want to convert.</span><span class="sxs-lookup"><span data-stu-id="749b8-126">The path to the extension manifest that you want to convert.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="749b8-127">After ManifoldJS has finished running, you will have a folder with the following contents.</span><span class="sxs-lookup"><span data-stu-id="749b8-127">After ManifoldJS has finished running, you will have a folder with the following contents.</span></span>  

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

<span data-ttu-id="749b8-128">The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package.</span><span class="sxs-lookup"><span data-stu-id="749b8-128">The generationInfo.json file is a log produced by running ManifoldJS and will not be included in your extension package.</span></span> <span data-ttu-id="749b8-129">Only the contents of the `manifest` folder will be packaged.</span><span class="sxs-lookup"><span data-stu-id="749b8-129">Only the contents of the `manifest` folder will be packaged.</span></span> <span data-ttu-id="749b8-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span><span class="sxs-lookup"><span data-stu-id="749b8-130">Within the manifest folder, the Assets folder contains the images that will be used in the Windows and Microsoft Store UI, while the Extension folder has the contents of your extension within it.</span></span>  

<span data-ttu-id="749b8-131">Now that you have the correct files, you will need to edit the generated AppXManifest file within the `manifest` folder.</span><span class="sxs-lookup"><span data-stu-id="749b8-131">Now that you have the correct files, you will need to edit the generated AppXManifest file within the `manifest` folder.</span></span> <span data-ttu-id="749b8-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span><span class="sxs-lookup"><span data-stu-id="749b8-132">If the extension’s manifest.json file has an internationalized string for the "name" field, once ManifoldJS is run, the most top layer folder’s name will have no underscores and include "MSG".</span></span>

<span data-ttu-id="749b8-133">For example, a manifest.json file with the following `"name"` field.</span><span class="sxs-lookup"><span data-stu-id="749b8-133">For example, a manifest.json file with the following `"name"` field.</span></span>  

```shell
"name" : "__MSG_appName__"
```  

<span data-ttu-id="749b8-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span><span class="sxs-lookup"><span data-stu-id="749b8-134">will have a manifest folder that lives in `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest`.</span></span>  

<span data-ttu-id="749b8-135">In the AppXManifest file, you will need to:</span><span class="sxs-lookup"><span data-stu-id="749b8-135">In the AppXManifest file, you will need to:</span></span>  

 *   <span data-ttu-id="749b8-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span><span class="sxs-lookup"><span data-stu-id="749b8-136">Replace the required Identity fields and PublisherDisplayName field as outlined [here](./creating-and-testing-extension-packages.md#app-identity-template-values).</span></span> <span data-ttu-id="749b8-137">Note that if you are only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span><span class="sxs-lookup"><span data-stu-id="749b8-137">Note that if you are only packaging for testing purposes or for enterprise distribution, you can use placeholder values instead of registering for a Windows Dev Center account.</span></span>  
 *   <span data-ttu-id="749b8-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span><span class="sxs-lookup"><span data-stu-id="749b8-138">Replace the placeholder icons in the Assets folder with icons for your extension with the same sizes (150x150, 50x50, 44x44) and names.</span></span> <span data-ttu-id="749b8-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span><span class="sxs-lookup"><span data-stu-id="749b8-139">See the [Design](./../design.md#icons-for-packaging) guide for information about where these icons are used.</span></span>  
 *   <span data-ttu-id="749b8-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span><span class="sxs-lookup"><span data-stu-id="749b8-140">If your extension is localized, follow the entire [Localizing Microsoft Edge extensions](./localizing-extension-packages.md) guide.</span></span> <span data-ttu-id="749b8-141">If it is not localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span><span class="sxs-lookup"><span data-stu-id="749b8-141">If it is not localized, only read the [Localizing name and description in the Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) section.</span></span>  

<span data-ttu-id="749b8-142">Once your `appxmanifest.xml` file is sorted out, run the following command to create your package.</span><span class="sxs-lookup"><span data-stu-id="749b8-142">Once your `appxmanifest.xml` file is sorted out, run the following command to create your package.</span></span>  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

<span data-ttu-id="749b8-143">Your package will now be in the **package** folder located within the edgeextension folder.</span><span class="sxs-lookup"><span data-stu-id="749b8-143">Your package will now be in the **package** folder located within the edgeextension folder.</span></span> <span data-ttu-id="749b8-144">For more information about how to sideload your new package, see [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing extension packages.</span><span class="sxs-lookup"><span data-stu-id="749b8-144">For more information about how to sideload your new package, see [testing](./creating-and-testing-extension-packages.md#testing-an-appx-package) section of Creating and testing extension packages.</span></span>  

<span data-ttu-id="749b8-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="749b8-145">Once your package has been tested, feel free to submit a request on our [extension submission form](https://aka.ms/extension-request) in order to be considered for publication to the Microsoft Store.</span></span>  
