---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: 了解如何使用 Microsoft Edge 扩展服务将 Chrome 扩展移植到 Microsoft Edge Toolkit。
title: 移植 Chrome 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f226d79dbc9efdc43eb68bfb353fa12748198371
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232588"
---
# <span data-ttu-id="315fb-104">将扩展从 Chrome 移植到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="315fb-104">Porting an extension from Chrome to Microsoft Edge</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="315fb-105">借助 Microsoft Edge 扩展服务，可轻松将扩展从 Chrome 移植到 [Microsoft Edge](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)Toolkit。</span><span class="sxs-lookup"><span data-stu-id="315fb-105">Porting an extension from Chrome to Microsoft Edge is made easy with the help of the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span> <span data-ttu-id="315fb-106">此开发人员工具通过桥接 API 和显示文件的任何错误，将未打包的 Chrome 扩展转换为未打包的 Microsoft Edge `manifest.json` 扩展。</span><span class="sxs-lookup"><span data-stu-id="315fb-106">This developer tool converts an unpacked Chrome extension to an unpacked Microsoft Edge extension by bridging APIs and surfacing any errors in your `manifest.json` file.</span></span>


### <span data-ttu-id="315fb-107">API 桥</span><span class="sxs-lookup"><span data-stu-id="315fb-107">API bridges</span></span>
<span data-ttu-id="315fb-108">为了允许将 Chrome API 无缝移植到支持的 Microsoft Edge API，将两个脚本添加到扩展的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="315fb-108">In order to allow for seamless porting of Chrome APIs to supported Microsoft Edge APIs, two scripts are added to your extension's folder.</span></span> <span data-ttu-id="315fb-109">这些脚本在必要时 (将 API 桥接到) ，这意味着你无需担心更改后台脚本或内容脚本中任何 Chrome 特定代码。</span><span class="sxs-lookup"><span data-stu-id="315fb-109">These scripts bridge APIs (polyfiling where necessary), meaning you won't have to worry about changing any Chrome specific code in your background script or content scripts.</span></span>

<span data-ttu-id="315fb-110">转换后，你将看到它们包含在扩展的清单文件中，并包含 `"-ms-preload"` 密钥：</span><span class="sxs-lookup"><span data-stu-id="315fb-110">After conversion, you will see them included in the manifest file of your extension with the `"-ms-preload"` key:</span></span>

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## <span data-ttu-id="315fb-111">使用 Microsoft Edge 扩展Toolkit</span><span class="sxs-lookup"><span data-stu-id="315fb-111">Using the Microsoft Edge Extension Toolkit</span></span>

<span data-ttu-id="315fb-112">以下说明详细介绍了如何在 Windows 10 周年更新版本中将 Chrome 扩展转换为在 Microsoft Edge 上运行：</span><span class="sxs-lookup"><span data-stu-id="315fb-112">The following instructions detail how to convert your Chrome extension to run on Microsoft Edge in the Windows 10 Anniversary Update edition:</span></span>

1. <span data-ttu-id="315fb-113">安装[Microsoft Edge 扩展Toolkit。](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)</span><span class="sxs-lookup"><span data-stu-id="315fb-113">Install the [Microsoft Edge Extension Toolkit](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb).</span></span>
2. <span data-ttu-id="315fb-114">创建 Chrome 扩展文件夹的副本以安全保留。</span><span class="sxs-lookup"><span data-stu-id="315fb-114">Make a copy of your Chrome extension's folder for safe keeping.</span></span> <span data-ttu-id="315fb-115">转换过程将覆盖代码。</span><span class="sxs-lookup"><span data-stu-id="315fb-115">The conversion process will overwrite the code.</span></span> 
3. <span data-ttu-id="315fb-116">运行 Microsoft Edge 扩展Toolkit并加载扩展副本。</span><span class="sxs-lookup"><span data-stu-id="315fb-116">Run the Microsoft Edge Extension Toolkit and load the copy of your extension.</span></span>  
 ![加载扩展按钮](./../media/save-folder.png)
4. <span data-ttu-id="315fb-118">更正在工具的文本编辑器中报告的所有错误。</span><span class="sxs-lookup"><span data-stu-id="315fb-118">Correct all the errors that are reported within the tool's text editor.</span></span> <span data-ttu-id="315fb-119">选择"重新验证"以在更正错误后检查错误。</span><span class="sxs-lookup"><span data-stu-id="315fb-119">Select "Re-validate" to check for errors after making corrections.</span></span>  
 ![扩展工具包查找错误](./../media/extension-toolkit.png)
5. <span data-ttu-id="315fb-121">选择"保存文件"。</span><span class="sxs-lookup"><span data-stu-id="315fb-121">Select "Save files".</span></span>

<span data-ttu-id="315fb-122">现在可以退出工具包，在 Microsoft Edge 中加载扩展！</span><span class="sxs-lookup"><span data-stu-id="315fb-122">You can now exit out of the toolkit and load your extension in Microsoft Edge!</span></span> 

<span data-ttu-id="315fb-123">您可以使用 EdgeHTML 问题跟踪器搜索已知 [平台问题](http://issues.microsoftedge.com)。</span><span class="sxs-lookup"><span data-stu-id="315fb-123">You can search for known platform issues with the [EdgeHTML issue tracker](http://issues.microsoftedge.com).</span></span> <span data-ttu-id="315fb-124">如果认为你已找到新内容， [请打开一个问题](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)！</span><span class="sxs-lookup"><span data-stu-id="315fb-124">If you think you've found something new, [open an issue](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)!</span></span>
