---
description: 通过 Microsoft Store 分发 PWA，吸引 Windows 10 客户的世界
title: Microsoft Store 中的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、Microsoft Store、Bing PWA 索引
ms.openlocfilehash: a4491f19b89e8b0f6fa511f146744499e2074f22
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564560"
---
# Microsoft Store 中的渐进式 Web 应用

将渐进式 Web 应用（PWA）发布到[Microsoft Store](https://developer.microsoft.com/store)时，你的潜在应用受众将扩展到几乎700000000每月活动用户的整个 Windows 10 安装基础！ 

Microsoft Store 中的 PWAs 有许多优点：

- 可**发现**-Microsoft Store 中的应用通过不同的类别、特选集合和搜索筛选器者，从而为你的应用的潜在客户提供了一个简单的浏览和购物体验。 您甚至可以使用屏幕截图、英雄图像和视频预告[增强您的应用商店列表](/windows/uwp/publish/app-screenshots-and-images)！

- 可**信赖**-Windows 客户知道他们可以信任 Microsoft 应用商店购买和下载，因为它们遵守 microsoft 严格的[质量和安全标准](/legal/windows/agreements/store-policies)。

- **轻松安装**-Microsoft Store 在[所有 Windows 10 应用](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)中提供一致且用户友好的安装体验，让所有客户都可以轻松地安装 PWA，无论技术舒适的级别如何。

- **商业见解**-Microsoft Store 的[Windows 开发人员中心仪表板](/windows/uwp/publish/using-the-windows-dev-center-dashboard)为你提供有关从你的 PWA 已达到多少个 Windows 客户以及他们的使用方式以及所需含义的[详细分析](/windows/uwp/publish/analytics)。 你还可以在应用运行状况、广告使用等方面查找指标和遥测数据。

有两个选项可用于将 PWA 转到 Microsoft Store 中：

1. 你可以[手动提交它](#submitting-your-pwa-manually)，或者

2. 如果 PWA 满足[特定条件](#criteria-for-automatic-submission)，则可通过必应 web 爬网程序[自动编制索引](#automatic-pwa-importing-with-bing)。 （您还可以选择[退出](#opting-out-of-automatic-microsoft-store-import)自动提交。）

无论提交方法如何，在将 PWA 接受到 Microsoft Store 后，您将获得上述所有优点的访问权限。

## 手动提交 PWA

为了通过 Microsoft Store 分发和提升应用，你需要将其作为 Windows 应用包（*.appx*文件）提交。  对于服务器托管的 web 应用（如 PWAs），此程序包只包含应用元数据和主屏幕图标（而不是任何实际的应用程序代码）。 通过这种方式，你的 web 应用可以从主屏幕和其他[Windows 10 应用](/windows/uwp/get-started/whats-a-uwp)（通过在轻量级本机应用包装（*WWAHost*过程）中运行，与 Microsoft Edge 浏览器窗口分开安装和启动。  

> [!IMPORTANT]
> EdgeHTML web 平台引擎由 WWAHost 应用包装程序使用，这可能会为基于 Microsoft Edge （Chromium）的 PWA 引入兼容性差异。  请确保在将应用提交到 Microsoft store 之前使用 Microsoft Edge （EdgeHTML）对应用程序执行完整测试，因为 EdgeHTML 引擎不再使用较新的 web 标准进行更新。  

下面介绍了如何操作。

### 必备条件

- **现有 PWA**。 下面介绍了如何[将你的 web 应用转换为 PWA](./get-started.md) （如果它尚未有）。 
- **用于 PWAs 的 WINDOWS APPX 打包工具**。 下面介绍如何使用 Visual Studio[在 Windows 上生成和运行 PWA](./windows-features.md) 。 你还可以使用[PWA 生成器](https://www.pwabuilder.com/)生成 Windows 程序包。
- [**Microsoft 应用商店应用开发人员帐户**](/windows/uwp/publish/opening-a-developer-account)。 根据您所选择的帐户类型和位置有[一次的费用](/windows/uwp/publish/account-types-locations-and-fees)，注册需要有效的[Microsoft 帐户](https://account.microsoft.com/)。


### 通过*Visual Studio*提交应用商店 

按照以下步骤在 Visual Studio 中为 PWA[创建应用包上传文件](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file)。 有关此过程的更多常规概述，请参阅将[*UWP 应用打包到 Visual Studio*](/windows/uwp/packaging/packaging-uwp-apps) 。

说明还将指导你运行[**Windows 应用认证工具包**](https://developer.microsoft.com/windows/develop/app-certification-kit)，以测试你的应用是否符合 Microsoft Store 要求。 这是可选的，但强烈建议这样做。

### 通过*Windows 开发人员中心*提交应用商店

下面介绍了如何使用*PWA 生成器*生成用于上载到 Windows 开发人员中心的应用包。

1. 生成 Windows 10 应用。 下面介绍了如何[使用 Visual Studio 作为 Windows 应用运行 PWA](./windows-features.md)。 你还可以使用[PWA 生成器](https://www.pwabuilder.com/)生成 Windows 10 应用。

2. 通过使用您的帐户信息登录到[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)并按照步骤[通过保留名称创建你的应用](/windows/uwp/publish/create-your-app-by-reserving-a-name)，为 Microsoft Store 保留你的应用名称。 每个保留的名称在 Microsoft Store 中都必须是唯一的。

3. 当你上载应用的程序包时， *package.appxmanifest*文件中的*DisplayName*、 *Name*、 *Publisher*和*PublisherDisplayName*值必须与在保留其名称时在 Windows 开发人员中心仪表板中分配给你的应用的值相匹配。 

    登录到[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)，然后在 "**应用管理**  >  **应用标识**" 下找到你的应用标识值：

    ![Windows 开发人员中心仪表板，应用标识设置](./media/dashboard-app-identity.png)

    然后，找到你的 `appxmanifest.xml` 文件并将以下值替换为 Windows 开发人员中心仪表板中分配的值：

    - **<标识名称 = "** *程序包/标识/名称*
    - **<身份发布者 = "** *程序包/标识/发布者*
    - **<DisplayName** **>***为你的应用保留的名称* 
    - **<PublisherDisplayName** **>***软件包/Properties/PublisherDisplayName***</PublisherDisplayName>**

4. 现在，你可以将所有 PWA 资源编译为单个 `.appx` 文件，你可以上传到 Microsoft Store。 从命令提示符处，导航到 web 清单的目录并创建 Windows 10 程序包（在 "w/可选调试日志记录" 下方指定）：

    ```
    pwabuilder package -p windows10 -l debug
    ```

    您的 .appx 文件将生成到此位置： `PWA\Store packages\windows10\package\windows.appx` 。

5. 将 submisison 的应用上载到 Microsoft Store 之前，最好先测试你的应用是否符合 Microsoft 应用商店策略。 你可以通过以下方法执行此操作：下载[**Windows 应用认证工具包**](https://developer.microsoft.com/windows/develop/app-certification-kit)，启动它，然后选择你的应用的 *.appx*文件进行测试。 所有测试完成后，你将收到一个要解决的区域的报告。

6. 通过登录回[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)并在**Submissions**  >  **Submisison 1**面板中展开提交，即可上传程序包并完成提交。 按照清单完成[所需的应用商店清单信息](/windows/uwp/publish/app-submissions)并[上载你的应用包](/windows/uwp/publish/upload-app-packages)。

有关适用于 Microsoft Store 应用开发人员的所有功能和服务的详细信息，请参阅在[Windows 开发人员中心](https://developer.microsoft.com/windows)[*发布 windows 应用*](https://developer.microsoft.com/store/publish-apps)。

## 与 Bing 进行自动 PWA 导入

正如你的 PWA [web 应用清单](https://developer.mozilla.org/docs/Web/Manifest)是支持平台的一种信号，你的应用可以脱机使用，并准备好作为完全集成的应用体验，它也是对 Bing web 爬行者的提示，可将其视为自动包含在 Microsoft Store 中。 

如果 PWA 满足下面的要求，必应索引服务将自动将你的 PWA 打包为在 Windows 10 上安装所需的[*.appx*](#submitting-your-pwa-manually)格式，并基于其 web 应用清单中的元数据汇编应用的应用商店产品页面。 在申报你的 PWA 后，你将能够通过 Windows 开发人员中心仪表板进一步自定义你的应用商店页面并获取用户分析和其他应用管理工具的访问权限。

### 自动提交的条件

若要为 Microsoft Store 自动打包和列出，你的 PWA 将需要：

- [X] 非空 web 应用清单文件，至少：

  - 名称
  - 描述
  - 至少 512 x 512 像素的应用图标

- [X] 独特的核心逻辑（[应用样板](https://en.wikipedia.org/wiki/Boilerplate_code)模板中的代码不是最低修改）

- [X] 通过安全连接（HTTPS）进行服务

- [X] 服务工作者脚本

- [X] 不违反任何法律或[Microsoft Store 政策](/legal/windows/agreements/store-policies)。

我们不会收到满足这些条件的每个应用，但在我们逐渐扩展我们的计划的应聘中将包括这些应用。

### 退出自动 Microsoft Store 导入

通过提供包含以下内容的文件，你的 PWA 可以选择退出 Microsoft Store 的自动导入 `robots.txt` ：

```
User-agent: bingbot
Disallow: /manifest.json
```

这将指示 Bing web 爬行程序（Bingbot）忽略用于 PWA 索引目的的 web 清单文件。 这不会影响你的网站在 Bing 的常规[web 索引流程](https://www.bing.com/webmaster/help/help-center-661b2d18)中的搜索排名。
