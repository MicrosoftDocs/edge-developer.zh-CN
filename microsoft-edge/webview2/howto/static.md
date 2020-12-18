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
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230927"
---
# <span data-ttu-id="8905f-104">静态链接 WebView2 加载程序库</span><span class="sxs-lookup"><span data-stu-id="8905f-104">Statically link the WebView2 loader library</span></span>  

<span data-ttu-id="8905f-105">你可能想要使用单个可执行文件（而不是包含许多文件的包）来分发应用程序。</span><span class="sxs-lookup"><span data-stu-id="8905f-105">You may want to distribute your application with a single executable file, instead of a package of many files.</span></span> <span data-ttu-id="8905f-106">若要创建单个可执行文件或减小程序包的大小，应静态链接 WebView2Loader 文件。</span><span class="sxs-lookup"><span data-stu-id="8905f-106">To create a single executable file, or to reduce the size of your package, you should statically link the WebView2Loader files.</span></span> <span data-ttu-id="8905f-107">WebView2 SDK 包含头文件和 `WebView2Loader.dll` `IDL` 文件。</span><span class="sxs-lookup"><span data-stu-id="8905f-107">The WebView2 SDK contains a header file, `WebView2Loader.dll`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="8905f-108">是一个小组件，可帮助应用在设备上找到 WebView2 运行时或非稳定 Microsoft Edge 通道。</span><span class="sxs-lookup"><span data-stu-id="8905f-108">is a small component that helps apps locate the WebView2 Runtime, or non-stable channels of Microsoft Edge, on the device.</span></span>  

<span data-ttu-id="8905f-109">对于不想发货的应用， `WebView2Loader.dll` 请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8905f-109">For apps that don't want to ship a `WebView2Loader.dll`, complete the following steps.</span></span>  

1.  <span data-ttu-id="8905f-110">在 `.vcxproj` 文本编辑器（如"代码"）中打开Visual Studio文件。</span><span class="sxs-lookup"><span data-stu-id="8905f-110">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8905f-111">项目 `.vcproj` 文件可能是一个隐藏文件，这意味着它不会显示在Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8905f-111">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="8905f-112">使用命令行查找隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="8905f-112">Use the command-line to find hidden files.</span></span>  
    
1.  <span data-ttu-id="8905f-113">在包含 WebView2 NuGet 程序包目标文件的代码中找到该部分。</span><span class="sxs-lookup"><span data-stu-id="8905f-113">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="8905f-114">下图中突出显示了代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="8905f-114">The location in the code is highlighted in the following figure.</span></span>  

    :::image type="complex" source="./media/inserthere.png" alt-text="Project 文件代码段" lightbox="./media/inserthere.png":::
       <span data-ttu-id="8905f-116">Project 文件代码段</span><span class="sxs-lookup"><span data-stu-id="8905f-116">Project Files code snippet</span></span>   
    :::image-end:::  
  
1.  <span data-ttu-id="8905f-117">复制以下代码段并将其粘贴到包含 `Microsoft.Web.WebView2.targets` 代码段的其中。</span><span class="sxs-lookup"><span data-stu-id="8905f-117">Copy the following code snippet and paste it where the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```
      
    :::image type="complex" source="./media/staticlib.png" alt-text="插入的代码段" lightbox="./media/staticlib.png":::
       <span data-ttu-id="8905f-119">插入的代码段</span><span class="sxs-lookup"><span data-stu-id="8905f-119">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8905f-120">编辑应用生成配置的其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="8905f-120">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="8905f-121">若要开始，请查找所有 `<AdditionalDependencies>` 标记。</span><span class="sxs-lookup"><span data-stu-id="8905f-121">To begin, find all of the `<AdditionalDependencies>` tags.</span></span> <span data-ttu-id="8905f-122">对于每个版本 `version.lib` ，将作为其他依赖项添加到文件中每个不同的生成 `.vcxproj` 配置。</span><span class="sxs-lookup"><span data-stu-id="8905f-122">For each, add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="将 version.lib 添加到 ItemDefinitionGroups" lightbox="./media/versionlib.png":::
       <span data-ttu-id="8905f-124">添加到 `version.lib`</span><span class="sxs-lookup"><span data-stu-id="8905f-124">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="8905f-125">WebView2 团队的目标是在未来版本中自动添加其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="8905f-125">The WebView2 team aims to automate adding the additional dependency in future releases.</span></span>  
    
1. <span data-ttu-id="8905f-126">编译并运行应用。</span><span class="sxs-lookup"><span data-stu-id="8905f-126">Compile and run your app.</span></span>

### <span data-ttu-id="8905f-127">与 WebView2 团队联系</span><span class="sxs-lookup"><span data-stu-id="8905f-127">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

### <span data-ttu-id="8905f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8905f-128">See also</span></span>  

*   <span data-ttu-id="8905f-129">若要开始使用 WebView2，请导航到 [WebView2 入门指南][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="8905f-129">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="8905f-130">有关 WebView2 功能的综合示例，请导航到 GitHub 上的[WebView2Samples。][GithubMicrosoftedgeWebview2samples]</span><span class="sxs-lookup"><span data-stu-id="8905f-130">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="8905f-131">有关 WebView2 API 的更多详细信息，请导航到 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="8905f-131">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="8905f-132">有关 WebView2 的信息，请导航到 [WebView2 资源][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="8905f-132">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能- JavaScript 调试器Visual Studio代码 - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView 应用程序 - Visual Studio 代码 - 适用于 Microsoft Edge 的调试器 - microsoft/vscode-edge-debug2 |GitHub"  
