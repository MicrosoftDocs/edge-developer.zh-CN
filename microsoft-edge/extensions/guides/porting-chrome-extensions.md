---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: 了解如何使用 Microsoft Edge 扩展工具包将 Chrome 扩展移植到 Microsoft Edge。
title: 移植 Chrome 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 38bf1324c2e7e6f7754912177ce0e53d6c15a276
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563237"
---
# <span data-ttu-id="e7bdc-104">将扩展程序从 Chrome 移植到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e7bdc-104">Porting an extension from Chrome to Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="e7bdc-105">通过 [Microsoft Edge 扩展工具包](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)的帮助，将 Chrome 中的扩展移植到 microsoft edge 变得非常简单。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-105">Porting an extension from Chrome to Microsoft Edge is made easy with the help of the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span> <span data-ttu-id="e7bdc-106">此开发工具通过桥接 Api 并在文件中呈现任何错误，将解压缩的 Chrome 扩展转换为解包的 Microsoft Edge 扩展 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-106">This developer tool converts an unpacked Chrome extension to an unpacked Microsoft Edge extension by bridging APIs and surfacing any errors in your `manifest.json` file.</span></span>


### <span data-ttu-id="e7bdc-107">API 桥</span><span class="sxs-lookup"><span data-stu-id="e7bdc-107">API bridges</span></span>
<span data-ttu-id="e7bdc-108">为了允许将 Chrome Api 无缝移植到受支持的 Microsoft Edge Api，请将两个脚本添加到扩展的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-108">In order to allow for seamless porting of Chrome APIs to supported Microsoft Edge APIs, two scripts are added to your extension's folder.</span></span> <span data-ttu-id="e7bdc-109">这些脚本桥接 Api (polyfiling （需要) ），这意味着无需担心在后台脚本或内容脚本中更改任何 Chrome 特定的代码。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-109">These scripts bridge APIs (polyfiling where necessary), meaning you won't have to worry about changing any Chrome specific code in your background script or content scripts.</span></span>

<span data-ttu-id="e7bdc-110">转换后，你将看到它们包含在具有以下键的扩展的清单文件中 `"-ms-preload"` ：</span><span class="sxs-lookup"><span data-stu-id="e7bdc-110">After conversion, you will see them included in the manifest file of your extension with the `"-ms-preload"` key:</span></span>

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## <span data-ttu-id="e7bdc-111">使用 Microsoft Edge 扩展工具包</span><span class="sxs-lookup"><span data-stu-id="e7bdc-111">Using the Microsoft Edge Extension Toolkit</span></span>

<span data-ttu-id="e7bdc-112">以下说明详细介绍了如何在 Windows 10 周年更新版本中将 Chrome 扩展转换为在 Microsoft Edge 上运行：</span><span class="sxs-lookup"><span data-stu-id="e7bdc-112">The following instructions detail how to convert your Chrome extension to run on Microsoft Edge in the Windows 10 Anniversary Update edition:</span></span>

1. <span data-ttu-id="e7bdc-113">安装 [Microsoft Edge 扩展工具包](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-113">Install the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span>
2. <span data-ttu-id="e7bdc-114">制作 Chrome 扩展文件夹的副本，以便安全保留。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-114">Make a copy of your Chrome extension's folder for safe keeping.</span></span> <span data-ttu-id="e7bdc-115">转换过程将覆盖代码。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-115">The conversion process will overwrite the code.</span></span> 
3. <span data-ttu-id="e7bdc-116">运行 Microsoft Edge 扩展工具包并加载您的扩展副本。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-116">Run the Microsoft Edge Extension Toolkit and load the copy of your extension.</span></span>  
 !["加载扩展" 按钮](./../media/save-folder.png)
4. <span data-ttu-id="e7bdc-118">更正工具的文本编辑器中报告的所有错误。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-118">Correct all the errors that are reported within the tool's text editor.</span></span> <span data-ttu-id="e7bdc-119">选择 "重新验证" 以在进行更正后检查错误。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-119">Select "Re-validate" to check for errors after making corrections.</span></span>  
 ![扩展-工具包查找错误](./../media/extension-toolkit.png)
5. <span data-ttu-id="e7bdc-121">选择 "保存文件"。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-121">Select "Save files".</span></span>

<span data-ttu-id="e7bdc-122">现在，你可以退出工具包并在 Microsoft Edge 中加载你的扩展！</span><span class="sxs-lookup"><span data-stu-id="e7bdc-122">You can now exit out of the toolkit and load your extension in Microsoft Edge!</span></span> 

<span data-ttu-id="e7bdc-123">你可以在 [EdgeHTML 问题跟踪](http://issues.microsoftedge.com)器中搜索已知的平台问题。</span><span class="sxs-lookup"><span data-stu-id="e7bdc-123">You can search for known platform issues with the [EdgeHTML issue tracker](http://issues.microsoftedge.com).</span></span> <span data-ttu-id="e7bdc-124">如果您认为发现了一些新功能，请 [打开一个问题](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)！</span><span class="sxs-lookup"><span data-stu-id="e7bdc-124">If you think you've found something new, [open an issue](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)!</span></span>
