---
description: 通过 Microsoft Store 分发 PWA，覆盖 Windows 10 客户的世界
title: Microsoft Store 中的渐进 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， Microsoft Store， 必应 PWA 索引
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dae25bcdf37a2496e181ab915d1686fe5d3a4985
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232342"
---
# Microsoft Store 中的渐进 Web 应用

将渐进式 Web 应用 (PWA) 发布到 Microsoft [Store](https://developer.microsoft.com/store)时，潜在应用受众将扩展到整个 Windows 10 安装基础，每月有近 7 亿活跃用户！ 

Microsoft Store 中的 PWA 具有许多优势：

-   **可发现** 性 - Microsoft Store 中的应用通过不同的类别、特展的集合和搜索筛选器进行展示，为应用的潜在客户提供轻松的浏览和购物体验。 你甚至可以 [使用屏幕截图](/windows/uwp/publish/app-screenshots-and-images) 、人物图像和视频预告片增强应用商店一览！
-   **可信度** - Windows 客户知道他们可以信任 Microsoft Store 的购买和下载，因为他们遵守 Microsoft 严格的 [质量和安全标准](/legal/windows/agreements/store-policies)。
-   **易于安装** - Microsoft Store 在所有 [Windows 10](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)应用中提供一致且用户友好的安装体验，使所有客户都可以轻松安装 PWA，无论技术舒适级别如何。
-   业务见解 **-** 适用于 Microsoft Store 的[Windows](/windows/uwp/publish/using-the-windows-dev-center-dashboard)开发人员[](/windows/uwp/publish/analytics)中心仪表板提供有关所有内容的详细分析，从 PWA 已接触的 Windows 客户数到客户使用方式以及必须说出的信息。 还可以查找有关应用运行状况、广告使用情况等的指标和遥测数据。
    
有两个选项用于将 PWA 加入 Microsoft Store：

1.  你可以 [手动提交它](#submitting-your-pwa-manually)，或者
2.  如果您的 PWA 满足[特定条件](#criteria-for-automatic-submission)，则 Bing [](#automatic-pwa-importing-with-bing) Web 爬网程序可自动对 PWA 编制索引。  (还可以选择退出自动提交。) [](#opting-out-of-automatic-microsoft-store-import)
    
无论采用哪种提交方法，一旦将 PWA 接受到 Microsoft Store，你都将获得上述所有权益的访问权限。

## 手动提交 PWA

若要通过 Microsoft Store 分发和推广应用，你需要将其作为 Windows 应用包提交到 .appx (*.appx*) 。  对于服务器托管的 Web 应用（如 PWA），此包仅包含应用元数据和主屏幕图标 (而不包含任何实际应用程序) 。 这样，可以在独立于 Microsoft Edge 浏览器窗口的轻型本机应用包装器 (*WWAHost.exe*进程) 中运行，将 Web 应用与其他[Windows 10](/windows/uwp/get-started/whats-a-uwp)应用一起从主屏幕安装和启动。  

> [!IMPORTANT]
> EdgeHTML Web 平台引擎由 WWAHost 应用包装器使用，它可能会为基于 PWA 的 Microsoft Edge (Chromium) 兼容性差异。  在将应用提交到 Microsoft Store 之前，请确保使用 Microsoft Edge (EdgeHTML) 对应用程序执行完全测试，因为不再使用较新的 Web 标准更新 EdgeHTML 引擎。  

下面是如何执行。

### 必备条件

-   **现有的 PWA**。 下面将了解如何将 [Web 应用转换为 PWA（](./get-started.md) 如果尚未转换）。 
-   **适用于 PWA 的 Windows APPX 打包工具**。 下面将了解如何使用 Visual Studio 在 Windows 上生成和运行[PWA。](./windows-features.md) 您还可以使用 [PWA 生成器](https://www.pwabuilder.com/) 生成 Windows 程序包。
-   [**Microsoft Store 应用开发人员帐户**](/windows/uwp/publish/opening-a-developer-account)。 有一 [次费用](/windows/uwp/publish/account-types-locations-and-fees) ，具体取决于你选择的帐户类型和位置，注册需要有效的 [Microsoft 帐户](https://account.microsoft.com/)。
    
### 通过应用商店提交 *Visual Studio* 

按照以下步骤在应用程序中 [为](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) PWA 创建应用程序包Visual Studio。 有关 [*此过程的更一般Visual Studio，*](/windows/uwp/packaging/packaging-uwp-apps) 请参阅"将 UWP 应用打包"。

这些说明还将指导你运行 Windows [**应用认证工具包**](https://developer.microsoft.com/windows/develop/app-certification-kit) ，以测试你的应用是否符合 Microsoft Store 要求。 这是可选的，但强烈建议这样做。

### 通过 *Windows 开发人员中心进行应用商店提交*

下面将了解如何使用 *PWA 生成器* 生成要上传到 Windows 开发人员中心的应用包。

1.  生成 Windows 10 应用。 下面将说明如何将 PWA 作为 Windows 应用运行[，Visual Studio。](./windows-features.md) 您还可以使用 [PWA 生成器](https://www.pwabuilder.com/) 生成 Windows 10 应用。
2.  使用帐户信息登录到 [Windows](https://developer.microsoft.com/dashboard/windows/overview) 开发人员中心仪表板，然后按照步骤通过保留名称来创建应用，为 Microsoft Store [保留应用名称](/windows/uwp/publish/create-your-app-by-reserving-a-name)。 每个保留的名称在 Microsoft Store 中都必须是唯一的。
3.  上传应用包时 *，.appxmanifest*文件的*DisplayName、Name、Publisher*和*PublisherDisplayName*值必须与在 Windows 开发人员中心仪表板中分配给应用的值匹配，且保留其名称。 ** ** 
    
    登录到[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)，并找到应用管理应用标识****  >  **下的应用标识值**：
    
    ![Windows 开发人员中心仪表板，应用标识设置](./media/dashboard-app-identity.png)
    
    然后，找到你的文件，并将以下值替换为在 Windows 开发人员中心仪表板中分配 `appxmanifest.xml` 的值：
    
    -   **<Identity Name="** *Package/Identity/Name*
    -   **<Identity Publisher="** *Package/Identity/Publisher*
    -   **<DisplayName** **>***为应用保留的名称* 
    -   **<PublisherDisplayName** **>***Package/Properties/PublisherDisplayName***</PublisherDisplayName>**
        
4.  现在，你已准备好将你的所有 PWA 资源编译为可上载到 Microsoft Store 的单个 `.appx` 文件。 在命令提示符下，导航到 Web 清单的目录，并创建一个 Windows 10 程序包 (以下指定的调试日志记录) ：
    
    ```shell
    pwabuilder package -p windows10 -l debug
    ```  
    
    .appx 文件将生成到此 `PWA\Store packages\windows10\package\windows.appx` 位置：
    
5.  在将应用上载到 Microsoft Store 之前，建议测试你的应用是否符合 Microsoft Store 策略。 为此，你可以下载 [**Windows 应用**](https://developer.microsoft.com/windows/develop/app-certification-kit)认证工具包，启动它，然后选择应用的 *.appx* 文件进行测试。 完成所有测试后，您将收到要解决的区域报告。
6.  上传程序包并完成提交，方法为登录 Windows[开发人员](https://developer.microsoft.com/dashboard/windows/overview)中心仪表板并展开**提交**  >  **子组件 1**面板。 按照清单完成所需的应用商店[一览信息并](/windows/uwp/publish/app-submissions)[上传应用包](/windows/uwp/publish/upload-app-packages)。
    
有关可供 Microsoft Store 应用开发人员使用的所有功能和服务，请参阅在 [*Windows*](https://developer.microsoft.com/store/publish-apps) 开发人员中心上发布 [Windows 应用](https://developer.microsoft.com/windows)。

## 使用必应自动导入 PWA

正如 PWA 的 [Web](https://developer.mozilla.org/docs/Web/Manifest) 应用清单是支持平台的信号一样，你的应用支持脱机并且已准备好呈现为完全集成的应用体验，它还向必应 Web 爬网程序提供提示，提示应考虑将 PWA 自动包含在 Microsoft Store 中。 

如果您的 PWA 满足以下要求，必应索引服务将自动将 PWA 打包为在 Windows 10 上安装所需的 [*.appx*](#submitting-your-pwa-manually) 格式，并基于应用的 Web 应用清单中的元数据来组合应用的应用商店产品页面。 声明 PWA 后，你将能够进一步自定义应用商店页面，并通过 Windows 开发人员中心仪表板访问用户分析和其他应用管理工具。

### 自动提交的条件

若要自动打包并针对 Microsoft Store 列出，PWA 将需要：

-   非空 Web 应用清单文件，至少为：
    
    -   名称
    -   描述
    -   至少为 512 x 512 像素的应用图标
        
-   唯一的核心逻辑 (来自应用样本模板模板的最少修改) [](https://en.wikipedia.org/wiki/Boilerplate_code)
-   通过 HTTPS 安全连接 (服务) 
-   服务工作 (脚本) 
-   不违反任何法律或 [Microsoft Store 策略](/legal/windows/agreements/store-policies)。
    
我们不会将符合这些条件的每一个应用都考虑在内，但在逐步扩展计划时，我们会将它们包括在候选项的注意事项中。

### 选择退出 Microsoft Store 自动导入

PWA 可以通过提供包含以下内容的文件来选择退出自动导入到 Microsoft `robots.txt` Store：

```text
User-agent: bingbot
Disallow: /manifest.json
```  

这将指示必应 Web 爬网 (必应) 忽略 Web 清单文件以用于 PWA 索引。 这不会影响网站在必应常规 Web 索引进程中 [的搜索排名](https://www.bing.com/webmaster/help/help-center-661b2d18)。
