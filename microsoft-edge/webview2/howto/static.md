---
description: 了解如何静态链接 WebView2 加载程序库。
title: 如何静态链接 WebView2 加载程序库
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 397c226eb958d1e656fb0ecb6dd8f1e2fe300746
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536332"
---
# <a name="statically-link-the-webview2-loader-library"></a><span data-ttu-id="a28bf-104">静态链接 WebView2 加载程序库</span><span class="sxs-lookup"><span data-stu-id="a28bf-104">Statically link the WebView2 loader library</span></span>  

<span data-ttu-id="a28bf-105">你可能希望使用单个可执行文件（而不是许多文件的包）来分发应用程序。</span><span class="sxs-lookup"><span data-stu-id="a28bf-105">You may want to distribute your application with a single executable file, instead of a package of many files.</span></span> <span data-ttu-id="a28bf-106">若要创建单个可执行文件或减小程序包的大小，应静态链接 WebView2Loader 文件。</span><span class="sxs-lookup"><span data-stu-id="a28bf-106">To create a single executable file, or to reduce the size of your package, you should statically link the WebView2Loader files.</span></span> <span data-ttu-id="a28bf-107">WebView2 SDK 包含头文件 、 `WebView2Loader.dll` 和 `IDL` 文件。</span><span class="sxs-lookup"><span data-stu-id="a28bf-107">The WebView2 SDK contains a header file, `WebView2Loader.dll`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="a28bf-108">是一个小型组件，可帮助应用在设备上找到 WebView2 运行时Microsoft Edge非稳定通道。</span><span class="sxs-lookup"><span data-stu-id="a28bf-108">is a small component that helps apps locate the WebView2 Runtime, or non-stable channels of Microsoft Edge, on the device.</span></span>  

<span data-ttu-id="a28bf-109">对于不希望提供 的应用， `WebView2Loader.dll` 请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a28bf-109">For apps that don't want to ship a `WebView2Loader.dll`, complete the following steps.</span></span>  

1.  <span data-ttu-id="a28bf-110">在 `.vcxproj` 文本编辑器（如文本编辑器）中打开应用Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="a28bf-110">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a28bf-111">项目 `.vcproj` 文件可能是隐藏文件，这意味着它不会显示在Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a28bf-111">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="a28bf-112">使用命令行查找隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="a28bf-112">Use the command-line to find hidden files.</span></span>  
    
1.  <span data-ttu-id="a28bf-113">在包含 WebView2 程序包目标文件的代码中找到NuGet部分。</span><span class="sxs-lookup"><span data-stu-id="a28bf-113">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="a28bf-114">代码中的位置在下图中突出显示。</span><span class="sxs-lookup"><span data-stu-id="a28bf-114">The location in the code is highlighted in the following figure.</span></span>  

    :::image type="complex" source="./media/inserthere.png" alt-text="Project文件代码段" lightbox="./media/inserthere.png":::
       <span data-ttu-id="a28bf-116">Project文件代码段</span><span class="sxs-lookup"><span data-stu-id="a28bf-116">Project Files code snippet</span></span>   
    :::image-end:::  
  
1.  <span data-ttu-id="a28bf-117">复制以下代码段并将其粘贴到包含 `Microsoft.Web.WebView2.targets` 位置。</span><span class="sxs-lookup"><span data-stu-id="a28bf-117">Copy the following code snippet and paste it where the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```
      
    :::image type="complex" source="./media/staticlib.png" alt-text="插入的代码段" lightbox="./media/staticlib.png":::
       <span data-ttu-id="a28bf-119">插入的代码段</span><span class="sxs-lookup"><span data-stu-id="a28bf-119">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a28bf-120">编辑应用生成配置的其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="a28bf-120">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="a28bf-121">首先，查找所有 `<AdditionalDependencies>` 标记。</span><span class="sxs-lookup"><span data-stu-id="a28bf-121">To begin, find all of the `<AdditionalDependencies>` tags.</span></span> <span data-ttu-id="a28bf-122">对于每个版本 `version.lib` ，将 作为附加依赖项添加到文件中每个不同的生成 `.vcxproj` 配置。</span><span class="sxs-lookup"><span data-stu-id="a28bf-122">For each, add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="将 version.lib 添加到 ItemDefinitionGroups" lightbox="./media/versionlib.png":::
       <span data-ttu-id="a28bf-124">添加到 `version.lib`</span><span class="sxs-lookup"><span data-stu-id="a28bf-124">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="a28bf-125">WebView2 团队旨在在未来版本中自动添加其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="a28bf-125">The WebView2 team aims to automate adding the additional dependency in future releases.</span></span>  
    
1. <span data-ttu-id="a28bf-126">编译并运行应用。</span><span class="sxs-lookup"><span data-stu-id="a28bf-126">Compile and run your app.</span></span>

### <a name="getting-in-touch-with-the-webview2-team"></a><span data-ttu-id="a28bf-127">与 WebView2 团队联系</span><span class="sxs-lookup"><span data-stu-id="a28bf-127">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

### <a name="see-also"></a><span data-ttu-id="a28bf-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a28bf-128">See also</span></span>  

*   <span data-ttu-id="a28bf-129">若要开始使用 WebView2，请导航到["WebView2 入门指南"。][Webview2MainGettingStarted]</span><span class="sxs-lookup"><span data-stu-id="a28bf-129">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="a28bf-130">有关 WebView2 功能的综合示例，请导航到[webView2 示例][GithubMicrosoftedgeWebview2samples]GitHub。</span><span class="sxs-lookup"><span data-stu-id="a28bf-130">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="a28bf-131">有关 WebView2 API 的更多详细信息，请导航到 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="a28bf-131">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="a28bf-132">有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2MainNextSteps]</span><span class="sxs-lookup"><span data-stu-id="a28bf-132">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft EdgeWebView2 API 参考|Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "下一步 - WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门 - WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能- 适用于 Visual Studio Code 的 JavaScript 调试程序 - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView 应用程序 - Visual Studio Code - 调试器 for Microsoft Edge - microsoft/vscode-edge-debug2 |GitHub"  
