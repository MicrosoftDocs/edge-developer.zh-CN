---
description: 了解如何静态链接 WebView2 加载程序库。
title: 如何静态链接 WebView2 加载程序库
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b7e0ec70cb00f318d4eb67254f37fcec79a5fcf6
ms.sourcegitcommit: 903524ab85321ade278facd741d6487e8cabe33f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100297"
---
# <span data-ttu-id="19ddd-104">如何静态链接 WebView2 加载程序库</span><span class="sxs-lookup"><span data-stu-id="19ddd-104">How to Statically link the WebView2 loader library</span></span>  

## <span data-ttu-id="19ddd-105">上下文</span><span class="sxs-lookup"><span data-stu-id="19ddd-105">Context</span></span>  

<span data-ttu-id="19ddd-106">什么是 WebView2Loader.dll？</span><span class="sxs-lookup"><span data-stu-id="19ddd-106">What is the WebView2Loader.dll?</span></span>  

*   <span data-ttu-id="19ddd-107">WebView2 SDK 包含一个头文件、一个 `WebView2Loader.dll.` 文件和一个 `IDL` 文件。</span><span class="sxs-lookup"><span data-stu-id="19ddd-107">The WebView2 SDK contains a header file, `WebView2Loader.dll.`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="19ddd-108">是一个小组件，可帮助应用在设备上找到 WebView2 运行时 (或非稳定 Microsoft Edge 通道) 。</span><span class="sxs-lookup"><span data-stu-id="19ddd-108">is a small component that helps apps locate the WebView2 Runtime (or non-stable Microsoft Edge channels) on the device.</span></span>  

<span data-ttu-id="19ddd-109">对于具有单个运行时且不希望发运的应用， `WebView2Loader.dll` 请完成以下 **过程** 步骤。</span><span class="sxs-lookup"><span data-stu-id="19ddd-109">For apps that have a single runtime, and do not want to ship a `WebView2Loader.dll`, complete the following **Procedure** steps.</span></span>  

## <span data-ttu-id="19ddd-110">过程</span><span class="sxs-lookup"><span data-stu-id="19ddd-110">Procedure</span></span>  

1.  <span data-ttu-id="19ddd-111">`.vcxproj`在文本编辑器（如 Visual Studio 代码）中打开应用的项目文件。</span><span class="sxs-lookup"><span data-stu-id="19ddd-111">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="19ddd-112">`.vcproj`项目文件可能是隐藏文件，这意味着它不会显示在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="19ddd-112">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="19ddd-113">使用命令行查找隐藏的文件。</span><span class="sxs-lookup"><span data-stu-id="19ddd-113">Use the command-line to find a hidden file.</span></span>  
    
1.  <span data-ttu-id="19ddd-114">在代码中找到包含 WebView2 NuGet 包目标文件的分区。</span><span class="sxs-lookup"><span data-stu-id="19ddd-114">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="19ddd-115">下图中突出显示了代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="19ddd-115">The location in the code is highlighted in the following figure.</span></span>  
    
    :::image type="complex" source="./media/inserthere.png" alt-text="项目文件代码片段" lightbox="./media/inserthere.png"::: 
       <span data-ttu-id="19ddd-117">项目文件代码片段</span><span class="sxs-lookup"><span data-stu-id="19ddd-117">Project Files code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="19ddd-118">复制以下代码片段，并将其粘贴到包含的任何位置 `Microsoft.Web.WebView2.targets` 。</span><span class="sxs-lookup"><span data-stu-id="19ddd-118">Copy the following code snippet and paste it everywhere the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="19ddd-119">例如，在以下代码块后包含它。</span><span class="sxs-lookup"><span data-stu-id="19ddd-119">For example, include it after the following code block.</span></span>  
    > 
    > ```csharp
    > <Import Project="..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets" Condition="Exists('..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets')" />
    > ```  
    
    ```csharp
    <PropertyGroup> <WebView2LoaderPreference>Static</WebView2LoaderPreference> </PropertyGroup>
    ```
    
    :::image type="complex" source="./media/staticlib.png" alt-text="项目文件代码片段" lightbox="./media/staticlib.png"::: 
       <span data-ttu-id="19ddd-121">插入的代码片段</span><span class="sxs-lookup"><span data-stu-id="19ddd-121">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="19ddd-122">编辑你的应用的生成配置的其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="19ddd-122">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="19ddd-123">若要开始，请查找所有 `<AdditionalDependencies>` 标记。</span><span class="sxs-lookup"><span data-stu-id="19ddd-123">To begin, find all of the `<AdditionalDependencies>` tags.</span></span>  
1.  <span data-ttu-id="19ddd-124">为 `version.lib` 应用的文件中的每个不同版本配置添加其他依赖项 `.vcxproj` 。</span><span class="sxs-lookup"><span data-stu-id="19ddd-124">Add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file for your app.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="项目文件代码片段" lightbox="./media/versionlib.png"::: 
       <span data-ttu-id="19ddd-126">添加 `version.lib` 到</span><span class="sxs-lookup"><span data-stu-id="19ddd-126">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="19ddd-127">WebView2 团队旨在在将来的版本中自动执行附加的相关性步骤。</span><span class="sxs-lookup"><span data-stu-id="19ddd-127">The WebView2 team aims to automate the additional dependency step in future releases.</span></span>  
    
<span data-ttu-id="19ddd-128">编译和部署你的应用。</span><span class="sxs-lookup"><span data-stu-id="19ddd-128">Compile and deploy your app.</span></span>  <span data-ttu-id="19ddd-129">成功。</span><span class="sxs-lookup"><span data-stu-id="19ddd-129">Success.</span></span>  

## <span data-ttu-id="19ddd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19ddd-130">See also</span></span>  

*   <span data-ttu-id="19ddd-131">若要开始使用 WebView2，请导航到 " [WebView2 入门指南][Webview2MainGettingStarted]"。</span><span class="sxs-lookup"><span data-stu-id="19ddd-131">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="19ddd-132">有关 WebView2 功能的完整示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 。</span><span class="sxs-lookup"><span data-stu-id="19ddd-132">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="19ddd-133">有关 WebView2 Api 的更多详细信息，请导航到 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="19ddd-133">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="19ddd-134">有关 WebView2 的详细信息，请导航到 " [WebView2 资源][Webview2MainNextSteps]"。</span><span class="sxs-lookup"><span data-stu-id="19ddd-134">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

## <span data-ttu-id="19ddd-135">与 WebView2 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="19ddd-135">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[Webview2ReferenceDotnet09628MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515-WebView2 for CoreWebView2EnvironmentOptions 类 |Microsoft 文档"  
[Webview2ReferenceWin3209622Webview2IdlParameters]: ../reference/win32/0-9-622/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-Globals |Microsoft 文档"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能-适用于 Visual Studio 代码的 JavaScript 调试程序-microsoft/vscode-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-Visual Studio 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
