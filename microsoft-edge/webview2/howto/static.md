---
description: 了解如何静态链接 WebView2 加载程序库。
title: 如何静态链接 WebView2 加载程序库
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/15/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 880e9ed809dc268ee0b30b6ee3b5996711f54300
ms.sourcegitcommit: 0ded671914aae231493f418dd7645a04361dca1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120122"
---
# <span data-ttu-id="c9040-104">静态链接 WebView2 加载程序库</span><span class="sxs-lookup"><span data-stu-id="c9040-104">Statically link the WebView2 loader library</span></span>  

<span data-ttu-id="c9040-105">你可能希望将应用程序与一个可执行文件（而不是包含许多文件的程序包）一起分发。</span><span class="sxs-lookup"><span data-stu-id="c9040-105">You may want to distribute your application with a single executable file, instead of a package of many files.</span></span> <span data-ttu-id="c9040-106">若要创建单个可执行文件或减小程序包的大小，应静态链接 WebView2Loader 文件。</span><span class="sxs-lookup"><span data-stu-id="c9040-106">To create a single executable file, or to reduce the size of your package, you should statically link the WebView2Loader files.</span></span> <span data-ttu-id="c9040-107">WebView2 SDK 包含一个头文件、一个 `WebView2Loader.dll` 文件和一个 `IDL` 文件。</span><span class="sxs-lookup"><span data-stu-id="c9040-107">The WebView2 SDK contains a header file, `WebView2Loader.dll`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="c9040-108">是一个小组件，可帮助应用在设备上找到 Microsoft Edge 的 WebView2 运行时或非稳定通道。</span><span class="sxs-lookup"><span data-stu-id="c9040-108">is a small component that helps apps locate the WebView2 Runtime, or non-stable channels of Microsoft Edge, on the device.</span></span>  

<span data-ttu-id="c9040-109">对于不希望发运的应用 `WebView2Loader.dll` ，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="c9040-109">For apps that don't want to ship a `WebView2Loader.dll`, complete the following steps.</span></span>  

1.  <span data-ttu-id="c9040-110">`.vcxproj`在文本编辑器（如 Visual Studio 代码）中打开应用的项目文件。</span><span class="sxs-lookup"><span data-stu-id="c9040-110">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c9040-111">`.vcproj`项目文件可能是隐藏文件，这意味着它不会显示在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="c9040-111">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="c9040-112">使用命令行查找隐藏的文件。</span><span class="sxs-lookup"><span data-stu-id="c9040-112">Use the command-line to find hidden files.</span></span>  
    
1.  <span data-ttu-id="c9040-113">在代码中找到包含 WebView2 NuGet 包目标文件的分区。</span><span class="sxs-lookup"><span data-stu-id="c9040-113">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="c9040-114">下图中突出显示了代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="c9040-114">The location in the code is highlighted in the following figure.</span></span>  

    :::image type="complex" source="./media/inserthere.png" alt-text="项目文件代码片段" lightbox="./media/inserthere.png":::
       <span data-ttu-id="c9040-116">项目文件代码片段</span><span class="sxs-lookup"><span data-stu-id="c9040-116">Project Files code snippet</span></span>   
    :::image-end:::  
  
1.  <span data-ttu-id="c9040-117">复制以下代码片段，并将其粘贴到 `Microsoft.Web.WebView2.targets` 包含的位置。</span><span class="sxs-lookup"><span data-stu-id="c9040-117">Copy the following code snippet and paste it where the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```
      
    :::image type="complex" source="./media/staticlib.png" alt-text="项目文件代码片段" lightbox="./media/staticlib.png":::
       <span data-ttu-id="c9040-119">插入的代码片段</span><span class="sxs-lookup"><span data-stu-id="c9040-119">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c9040-120">编辑你的应用的生成配置的其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="c9040-120">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="c9040-121">若要开始，请查找所有 `<AdditionalDependencies>` 标记。</span><span class="sxs-lookup"><span data-stu-id="c9040-121">To begin, find all of the `<AdditionalDependencies>` tags.</span></span> <span data-ttu-id="c9040-122">对于每个，添加一个 `version.lib` 对文件中每个不同的生成配置的附加依赖项 `.vcxproj` 。</span><span class="sxs-lookup"><span data-stu-id="c9040-122">For each, add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="项目文件代码片段" lightbox="./media/versionlib.png":::
       <span data-ttu-id="c9040-124">添加 `version.lib` 到</span><span class="sxs-lookup"><span data-stu-id="c9040-124">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="c9040-125">WebView2 团队旨在在将来的版本中自动添加其他相关性。</span><span class="sxs-lookup"><span data-stu-id="c9040-125">The WebView2 team aims to automate adding the additional dependency in future releases.</span></span>  
    
1. <span data-ttu-id="c9040-126">编译并运行你的应用。</span><span class="sxs-lookup"><span data-stu-id="c9040-126">Compile and run your app.</span></span>

### <span data-ttu-id="c9040-127">与 WebView2 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="c9040-127">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

### <span data-ttu-id="c9040-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9040-128">See also</span></span>  

*   <span data-ttu-id="c9040-129">若要开始使用 WebView2，请导航到 " [WebView2 入门指南][Webview2MainGettingStarted]"。</span><span class="sxs-lookup"><span data-stu-id="c9040-129">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="c9040-130">有关 WebView2 功能的完整示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 。</span><span class="sxs-lookup"><span data-stu-id="c9040-130">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="c9040-131">有关 WebView2 Api 的更多详细信息，请导航到 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="c9040-131">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="c9040-132">有关 WebView2 的详细信息，请导航到 " [WebView2 资源][Webview2MainNextSteps]"。</span><span class="sxs-lookup"><span data-stu-id="c9040-132">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能-适用于 Visual Studio 代码的 JavaScript 调试程序-microsoft/vscode-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-Visual Studio 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
