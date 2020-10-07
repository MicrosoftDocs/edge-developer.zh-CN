---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: Learn how to port your Chrome extension to Microsoft Edge using the Microsoft Edge Extension Toolkit.
title: Porting Chrome extensions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.custom: seodec18
ms.openlocfilehash: 38bf1324c2e7e6f7754912177ce0e53d6c15a276
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563237"
---
# <span data-ttu-id="0aecb-104">Porting an extension from Chrome to Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0aecb-104">Porting an extension from Chrome to Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="0aecb-105">Porting an extension from Chrome to Microsoft Edge is made easy with the help of the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span><span class="sxs-lookup"><span data-stu-id="0aecb-105">Porting an extension from Chrome to Microsoft Edge is made easy with the help of the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span> <span data-ttu-id="0aecb-106">This developer tool converts an unpacked Chrome extension to an unpacked Microsoft Edge extension by bridging APIs and surfacing any errors in your `manifest.json` file.</span><span class="sxs-lookup"><span data-stu-id="0aecb-106">This developer tool converts an unpacked Chrome extension to an unpacked Microsoft Edge extension by bridging APIs and surfacing any errors in your `manifest.json` file.</span></span>


### <span data-ttu-id="0aecb-107">API bridges</span><span class="sxs-lookup"><span data-stu-id="0aecb-107">API bridges</span></span>
<span data-ttu-id="0aecb-108">In order to allow for seamless porting of Chrome APIs to supported Microsoft Edge APIs, two scripts are added to your extension's folder.</span><span class="sxs-lookup"><span data-stu-id="0aecb-108">In order to allow for seamless porting of Chrome APIs to supported Microsoft Edge APIs, two scripts are added to your extension's folder.</span></span> <span data-ttu-id="0aecb-109">These scripts bridge APIs (polyfiling where necessary), meaning you won't have to worry about changing any Chrome specific code in your background script or content scripts.</span><span class="sxs-lookup"><span data-stu-id="0aecb-109">These scripts bridge APIs (polyfiling where necessary), meaning you won't have to worry about changing any Chrome specific code in your background script or content scripts.</span></span>

<span data-ttu-id="0aecb-110">After conversion, you will see them included in the manifest file of your extension with the `"-ms-preload"` key:</span><span class="sxs-lookup"><span data-stu-id="0aecb-110">After conversion, you will see them included in the manifest file of your extension with the `"-ms-preload"` key:</span></span>

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## <span data-ttu-id="0aecb-111">Using the Microsoft Edge Extension Toolkit</span><span class="sxs-lookup"><span data-stu-id="0aecb-111">Using the Microsoft Edge Extension Toolkit</span></span>

<span data-ttu-id="0aecb-112">The following instructions detail how to convert your Chrome extension to run on Microsoft Edge in the Windows 10 Anniversary Update edition:</span><span class="sxs-lookup"><span data-stu-id="0aecb-112">The following instructions detail how to convert your Chrome extension to run on Microsoft Edge in the Windows 10 Anniversary Update edition:</span></span>

1. <span data-ttu-id="0aecb-113">Install the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span><span class="sxs-lookup"><span data-stu-id="0aecb-113">Install the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span>
2. <span data-ttu-id="0aecb-114">Make a copy of your Chrome extension's folder for safe keeping.</span><span class="sxs-lookup"><span data-stu-id="0aecb-114">Make a copy of your Chrome extension's folder for safe keeping.</span></span> <span data-ttu-id="0aecb-115">The conversion process will overwrite the code.</span><span class="sxs-lookup"><span data-stu-id="0aecb-115">The conversion process will overwrite the code.</span></span> 
3. <span data-ttu-id="0aecb-116">Run the Microsoft Edge Extension Toolkit and load the copy of your extension.</span><span class="sxs-lookup"><span data-stu-id="0aecb-116">Run the Microsoft Edge Extension Toolkit and load the copy of your extension.</span></span>  
 ![load extension button](./../media/save-folder.png)
4. <span data-ttu-id="0aecb-118">Correct all the errors that are reported within the tool's text editor.</span><span class="sxs-lookup"><span data-stu-id="0aecb-118">Correct all the errors that are reported within the tool's text editor.</span></span> <span data-ttu-id="0aecb-119">Select "Re-validate" to check for errors after making corrections.</span><span class="sxs-lookup"><span data-stu-id="0aecb-119">Select "Re-validate" to check for errors after making corrections.</span></span>  
 ![extension-toolkit finding errors](./../media/extension-toolkit.png)
5. <span data-ttu-id="0aecb-121">Select "Save files".</span><span class="sxs-lookup"><span data-stu-id="0aecb-121">Select "Save files".</span></span>

<span data-ttu-id="0aecb-122">You can now exit out of the toolkit and load your extension in Microsoft Edge!</span><span class="sxs-lookup"><span data-stu-id="0aecb-122">You can now exit out of the toolkit and load your extension in Microsoft Edge!</span></span> 

<span data-ttu-id="0aecb-123">You can search for known platform issues with the [EdgeHTML issue tracker](http://issues.microsoftedge.com).</span><span class="sxs-lookup"><span data-stu-id="0aecb-123">You can search for known platform issues with the [EdgeHTML issue tracker](http://issues.microsoftedge.com).</span></span> <span data-ttu-id="0aecb-124">If you think you've found something new, [open an issue](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)!</span><span class="sxs-lookup"><span data-stu-id="0aecb-124">If you think you've found something new, [open an issue](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)!</span></span>
